---
title: Einrichten von HoloLens als Kiosk
description: Erfahren Sie, wie Sie eine Kioskkonfiguration einrichten und verwenden, um die Apps auf HoloLens-Geräten zu sperren.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 245de50fcaaf1235cce02cd1b6cae921b64f2851
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283986"
---
# Einrichten von HoloLens als Kiosk

Sie können ein HoloLens-Gerät so konfigurieren, dass es als ein Gerät mit festem Zweck, auch Kiosk *genannt,* funktioniert, indem Sie das Gerät so konfigurieren, dass es im Kioskmodus ausgeführt wird. Der Kioskmodus schränkt die Anwendungen (oder Benutzer) ein, die auf dem Gerät verfügbar sind. Der Kioskmodus ist ein praktisches Feature, das Sie verwenden können, um ein HoloLens-Gerät für Geschäfts-Apps zu verwenden oder das HoloLens-Gerät in einer App-Demo zu verwenden.

Dieser Artikel enthält Informationen zu Aspekten der Kioskkonfiguration, die spezifisch für HoloLens-Geräte sind. Allgemeine Informationen zu den verschiedenen Typen von Windows-basierten Kiosken und deren Konfiguration finden Sie unter "Konfigurieren von Kiosken und digitalen Zeichen [für Windows-Desktopeditionen".](https://docs.microsoft.com/windows/configuration/kiosk-methods)  

> [!IMPORTANT]  
> Der Kioskmodus bestimmt, welche Apps verfügbar sind, wenn sich ein Benutzer am Gerät an- oder ab meldet. Der Kioskmodus ist jedoch keine Sicherheitsmethode. Eine "zugelassene" App wird nicht daran erinnert, eine andere nicht zulässige App zu öffnen. Um das Öffnen von Apps oder Prozessen zu blockieren, verwenden Sie [Windows Defender Anwendungssteuerungs-CSP (WDAC),](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) um geeignete Richtlinien zu erstellen.
>
> Erfahren Sie mehr über die Microsoft-Dienste, um Benutzern ein erweitertes Sicherheitsniveau zu bieten, das HoloLens 2 verwendet, und erfahren Sie mehr über die Statustrennung und [-isolation – Defender-Schutz.](security-state-separation-isolation.md#defender-protections) Oder erfahren Sie, wie Sie WDAC und Windows PowerShell verwenden, um Apps auf [HoloLens 2-Geräten](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)mit Microsoft Intune zu erlauben oder zu blockieren.

Sie können den Kioskmodus entweder in einer Einzel- oder einer Multi-App-Konfiguration verwenden, und Sie können einen von drei Prozessen zum Einrichten und Bereitstellen der Kioskkonfiguration verwenden.

> [!IMPORTANT]  
> Beim Löschen der Multi-App-Konfiguration werden die Benutzersperrmodusprofile entfernt, die das Feature für den zugewiesenen Zugriff erstellt hat. Es werden jedoch nicht alle Richtlinienänderungen zurückgesetzt. Zum Wiederherstellen dieser Richtlinien müssen Sie das Gerät auf die Werkseinstellungen zurücksetzen.

## Planen der Kioskbereitstellung

Bei der Planung Ihres Kiosks müssen Sie in der Lage sein, die folgenden Fragen zu beantworten. Im Folgenden finden Sie einige Entscheidungen, die Sie beim Lesen dieser Seite berücksichtigen sollten, sowie einige Überlegungen zu diesen Fragen.
1. **Wer verwendet Ihren Kiosk, und welche [Kontotypen](hololens-identity.md) werden verwendet?** Dies ist eine Entscheidung, die Sie wahrscheinlich bereits getroffen haben und nicht für Ihren Kiosk angepasst werden sollten, sondern sich darauf auswirken, wie der Kiosk später zugewiesen wird.
1. **Benötigen Sie unterschiedliche Kioske pro Benutzer/Gruppe oder einen Kiosk, der für einige nicht aktiviert ist?** Wenn ja, möchten Sie Ihren Kiosk über XML erstellen. 
1. **Wie viele Apps werden in Ihrem Kiosk angezeigt?** Wenn Sie über mehr als eine App verfügen, benötigen Sie einen Kiosk mit mehreren Apps. 
1. **Welche Apps werden in Ihrem Kiosk angezeigt?** Verwenden Sie die folgende Liste von AUMIDs, um zusätzlich In-Box apps hinzuzufügen.
1. **Wie planen Sie die Bereitstellung Ihres Kiosks?** Wenn Sie ein Gerät bei MDM registrieren, empfehlen wir die Verwendung von MDM zum Bereitstellen Ihres Kiosks. Wenn Sie MDM nicht verwenden, ist die Bereitstellung mit dem Bereitstellungspaket verfügbar.  

### Anforderungen für den Kioskmodus

Sie können jedes HoloLens 2-Gerät für die Verwendung des Kioskmodus konfigurieren.

> [!IMPORTANT]
> Der Kioskmodus ist nur verfügbar, wenn das Gerät über Windows Holographic for Business verfügt. Alle HoloLens 2-Geräte sind mit Windows Holographic for Business erhältlich, und es gibt keine anderen Editionen. Auf allen HoloLens 2-Geräten kann der Kioskmodus von vorn ausgeführt werden.
>
> HoloLens (1. Generation)-Geräte müssen sowohl hinsichtlich des Betriebssystem-Build als auch der Betriebssystemedition aktualisiert werden. Hier finden Sie weitere Informationen zum Aktualisieren einer HoloLens (1. Generation) [auf die Windows Holographic for Business](hololens1-upgrade-enterprise.md) Edition. Um ein HoloLens (1. Generation)-Gerät für die Verwendung des Kioskmodus zu aktualisieren, müssen Sie zunächst sicherstellen, dass auf dem Gerät Windows 10, Version 1803 oder eine neuere Version ausgeführt wird. Wenn Sie das Windows Device Recovery Tool verwendet haben, um Ihr HoloLens (1. Generation)-Gerät im Standard build wiederhergestellt zu haben, oder wenn Sie die neuesten Updates installiert haben, kann Ihr Gerät konfiguriert werden.

> [!IMPORTANT]  
> Um Geräte zu schützen, die im Kioskmodus ausgeführt werden, sollten Sie Geräteverwaltungsrichtlinien hinzufügen, die Features wie die USB-Konnektivität deaktivieren. Überprüfen Sie außerdem die Updateringeinstellungen, um sicherzustellen, dass automatische Updates nicht während der Geschäftszeiten erfolgen.

### Entscheiden zwischen einem Kiosk mit einer einzigen App oder einem Kiosk mit mehreren Apps

Ein Kiosk mit einer einzigen App startet die angegebene App, wenn sich der Benutzer am Gerät meldet. Das Startmenü ist wie Cortana deaktiviert. Ein HoloLens 2-Gerät reagiert nicht auf die [Startgeste.](hololens2-basic-usage.md#start-gesture) Ein HoloLens (1. Generation)-Gerät reagiert nicht auf die [Aufblühbewegung.](hololens1-basic-usage.md) Da nur eine App ausgeführt werden kann, kann der Benutzer keine anderen Apps platzieren.

Ein Kiosk mit mehreren Apps zeigt das Startmenü an, wenn sich der Benutzer beim Gerät an- und ab meldet. Die Kioskkonfiguration bestimmt, welche Apps im Startmenü verfügbar sind. Sie können einen Kiosk mit mehreren Apps verwenden, um Benutzern ein leicht verständliches Erlebnis zu bieten, indem Sie ihnen nur die Dinge präsentieren, die sie verwenden müssen, und die Dinge entfernen, die sie nicht verwenden müssen.

In der folgenden Tabelle sind die Featurefunktionen in den verschiedenen Kioskmodi aufgeführt.

| &nbsp; |Startmenü |Menü "Schnellaktionen" |Kamera und Video |Miracast |Cortana |Integrierte Sprachbefehle |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|Single-App-Kiosk |Deaktiviert |Deaktiviert   |Deaktiviert |Deaktiviert   |Deaktiviert |Aktiviert <sup> 1</sup> |
|Multi-App-Kiosk |Aktiviert |Aktiviert <sup> 2</sup> |Verfügbar <sup> 2</sup> |Verfügbar <sup> 2</sup> |Verfügbar <sup> 2, 3</sup>  |Aktiviert <sup> 1</sup> |

> <sup>1 </sup> Sprachbefehle, die sich auf deaktivierte Funktionen beziehen, funktionieren nicht.  
> <sup>2 Weitere Informationen zum Konfigurieren dieser Features finden Sie unter </sup> [Auswählen von Kiosk-Apps.](#plan-kiosk-apps)  
> <sup>3 Auch wenn Cortana deaktiviert ist, sind die </sup> integrierten Sprachbefehle aktiviert.

In der folgenden Tabelle sind die Benutzerunterstützungsfunktionen der verschiedenen Kioskmodi aufgeführt.

| &nbsp; |Unterstützte Benutzertypen | Automatische Anmeldung | Mehrere Zugriffsebenen |
| --- | --- | --- | --- |
|Single-App-Kiosk |Verwaltetes Dienstkonto (Managed Service Account, MSA) in Azure Active Directory (Azure AD) oder lokales Konto |Ja |Nein |
|Multi-App-Kiosk |Azure AD-Konto |Nein |Ja |

Beispiele für die Verwendung dieser Funktionen finden Sie in der folgenden Tabelle.

|Verwenden Sie einen Single-App-Kiosk für: |Verwenden Sie einen Multi-App-Kiosk für: |
| --- | --- |
|Ein Gerät, auf dem nur ein Dynamics 365-Leitfaden für neue Mitarbeiter ausgeführt wird. |Ein Gerät, auf dem Handbücher und Remoteunterstützung für eine Reihe von Mitarbeitern ausgeführt werden. |
|Ein Gerät, auf dem nur eine benutzerdefinierte App ausgeführt wird. |Ein Gerät, das für die meisten Benutzer als Kiosk fungiert (nur eine benutzerdefinierte App ausgeführt wird), aber als Standardgerät für eine bestimmte Gruppe von Benutzern fungiert. |

### Planen von Kiosk-Apps

Allgemeine Informationen zur Auswahl von Kiosk-Apps finden Sie in den Richtlinien für die Auswahl einer App für den zugewiesenen Zugriff [(Kioskmodus).](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)

Wenn Sie das Windows Device Portal verwenden, um einen Kiosk mit einer einzigen App zu konfigurieren, wählen Sie die App während des Setupprozesses aus.  

Wenn Sie ein #A0 (Mobile Device Management) oder ein Bereitstellungspaket zum Konfigurieren des Kioskmodus verwenden, verwenden Sie den [#A1 (AssignedAccess Configuration Service Provider, CSP),](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) um Anwendungen anzugeben. Der CSP verwendet [Anwendungsbenutzermodell-IDs (Application User Model IDs, AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) zum Identifizieren von Anwendungen. In der folgenden Tabelle sind die AUMIDs einiger In-Box-Anwendungen aufgeführt, die Sie in einem Kiosk mit mehreren Apps verwenden können.

> [!IMPORTANT]
> Der Kioskmodus bestimmt, welche Apps verfügbar sind, wenn sich ein Benutzer am Gerät an- oder ab meldet. Der Kioskmodus ist jedoch keine Sicherheitsmethode. Eine "zugelassene" App wird nicht daran erinnert, eine andere nicht zulässige App zu öffnen. Da wir dieses Verhalten nicht einschränken, können Apps weiterhin über Edge, den Datei-Explorer und die Microsoft Store-Apps gestartet werden. Wenn es bestimmte Apps gibt, die nicht über einen Kiosk gestartet werden sollen, verwenden Sie Windows Defender #A0 [(WDAC),](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) um geeignete Richtlinien zu erstellen. 
> 
> Darüber hinaus kann das Mixed Reality Home nicht als Kiosk-App festgelegt werden.

<a id="aumids"></a>

|App-Name |AUMID |
| --- | --- |
|3D-Viewer |Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\! Microsoft.Microsoft3DViewer |
|Calendar |microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar |
|Kamera <sup> 1, 2</sup> |HoloCamera\_cw5n1h2txyewy\! HoloCamera |
|Cortana <sup> 3</sup> |Microsoft.549981C3F5F10\_8wekyb3d8bbwe\! App |
|Geräteauswahl auf HoloLens (1. Generation) |HoloDevicesFlow\_cw5n1h2txyewy\! HoloDevicesFlow |
|Geräteauswahl auf HoloLens 2 |Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\! Microsoft.Windows.DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\! Microsoft.RemoteAssist |
|Feedback &nbsp; Hub |Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\! App |
|Datei-Explorer |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast <sup> 4</sup> |&nbsp; |
|Filme & TV |Microsoft.ZuneVideo\_8wekyb3d8bbwe\! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive\_8wekyb3d8bbwe\! App |
|Fotos |Microsoft.Windows.Fotos\_8wekyb3d8bbwe\! App |
|Einstellungen |HolographicSystemSettings\_cw5n1h2txyewy\! App |
|Tipps |Microsoft.HoloLensTips\_8wekyb3d8bbwe\! HoloLensTips |

> <sup>1 Um die Foto- oder Videoaufnahme zu aktivieren, müssen Sie die </sup> Kamera-App als Kiosk-App aktivieren.  
> <sup>2 </sup> Beachten Sie beim Aktivieren der Kamera-App die folgenden Bedingungen:
> - Das Menü "Schnellaktionen" enthält die Schaltflächen "Foto" und "Video".  
> - Sie sollten auch eine App (z. B. Fotos, E-Mail oder OneDrive) aktivieren, die mit Bildern interagieren oder bilder abrufen kann.  
>  
> <sup>3 Auch wenn Sie Cortana nicht als </sup> Kiosk-App aktivieren, sind integrierte Sprachbefehle aktiviert. Befehle im Zusammenhang mit deaktivierten Features haben jedoch keine Auswirkung.  
> <sup>4 </sup> Sie können Miracast nicht direkt aktivieren. Aktivieren Sie zum Aktivieren von Miracast als Kiosk-App die Kamera-App und die Geräteauswahl-App.

### Planen von Kioskprofilen für Benutzer oder Gruppen

Wenn Sie entweder die XML-Datei erstellen oder die Benutzeroberfläche von Intune zum Einrichten eines Kiosks verwenden, müssen Sie überlegen, wer der Kioskbenutzer sein wird. Eine Kioskkonfiguration kann auf ein einzelnes Konto oder Azure AD-Gruppen beschränkt werden. 

In der Regel sind Kioske für einen Benutzer oder eine Benutzergruppe aktiviert. Wenn Sie jedoch planen, Ihren eigenen XML-Kiosk zu schreiben, sollten Sie den globalen zugewiesenen Zugriff in Betracht ziehen, in dem der Kiosk unabhängig von der Identität auf Geräteebene angewendet wird. Wenn Dies für Sie [spricht, lesen Sie mehr über globale Kioske mit zugewiesenem Zugriff.](hololens-global-assigned-access-kiosk.md)

#### Wenn Sie eine XML-Datei erstellen:
-   Sie erstellen viele Kioskprofile und weisen sie jeweils unterschiedlichen Benutzern/Gruppen zu. Beispielsweise ein Kiosk für Ihre Azure AD-Gruppe mit vielen Apps und ein Besucher, der über einen Kiosk mit mehreren Apps mit einer einzelnen App verfügt.
-   Ihre Kioskkonfiguration wird als **Profil-ID bezeichnet und** hat eine GUID.
-   Sie weisen dieses Profil im Abschnitt "Konfigurationen" zu, indem Sie den Benutzertyp angeben und dieselbe GUID für die **DefaultProfile-ID verwenden.**
- Eine XML-Datei kann erstellt, aber dennoch über MDM auf ein Gerät angewendet werden, indem ein benutzerdefiniertes OMA-URI-Gerätekonfigurationsprofil erstellt und mithilfe des URI-Werts auf die Gerätegruppe "HoloLens" angewendet wird: ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### Wenn Sie einen Kiosk in Intune erstellen.
-   Jedes Gerät kann nur ein einzelnes Kioskprofil empfangen, andernfalls wird ein Konflikt erstellt, und es werden keine Kioskkonfigurationen empfangen. 
    -   Andere Arten von Profilen und Richtlinien, z. B. Geräteeinschränkungen, die nicht mit dem Kioskkonfigurationsprofil in Zusammenhang stehen, stehen nicht in Konflikt mit dem Kioskkonfigurationsprofil.
-   Der Kiosk wird für alle Benutzer aktiviert, die Teil des Benutzeranmeldungstyps sind. Dies wird mit einem Benutzer oder einer Azure AD-Gruppe festgelegt. 
-   Nachdem die Kioskkonfiguration festgelegt **** wurde und der Benutzeranmeldungstyp (Benutzer, die sich am Kiosk anmelden können) und die Apps ausgewählt sind, muss die Gerätekonfiguration weiterhin einer Gruppe zugewiesen werden. Die zugewiesenen Gruppen bestimmen, welche Geräte die Konfiguration des Kioskgeräts erhalten, interagieren jedoch nicht, wenn der Kiosk aktiviert ist oder nicht. 
    - Eine vollständige Diskussion über die Auswirkungen des Zuweisens von Konfigurationsprofilen in Intune finden Sie unter Zuweisen von Benutzer- und [Geräteprofilen in Microsoft Intune.](https://docs.microsoft.com/intune/configuration/device-profile-assign)

### Auswählen einer Bereitstellungsmethode

Sie können eine der folgenden Methoden zum Bereitstellen von Kioskkonfigurationen auswählen:

- [Microsoft Intune oder anderer Mobile Device Management (MDM)-Dienst](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Bereitstellungspaket](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Geräteportal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Da diese Methode erfordert, dass der Entwicklermodus auf dem Gerät aktiviert ist, wird empfohlen, ihn nur für Demonstrationen zu verwenden.

In der folgenden Tabelle sind die Funktionen und Vorteile der einzelnen Bereitstellungsmethoden aufgeführt.

| &nbsp; |Bereitstellen über das Windows Device Portal |Bereitstellen mithilfe eines Bereitstellungspakets |Bereitstellen mithilfe von MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Bereitstellen von Single-App-Kiosks   | Ja           | Ja                  | Ja  |
|Bereitstellen von Kiosken mit mehreren Apps    | Nein            | Ja                  | Ja  |
|Nur auf lokalen Geräten bereitstellen | Ja           | Ja                  | Nein   |
|Bereitstellen mithilfe des Entwicklermodus |Erforderlich       | Nicht erforderlich            | Nicht erforderlich   |
|Bereitstellen mithilfe von Azure Active Directory (Azure AD)  | Nicht erforderlich            | Nicht erforderlich                   | Erforderlich  |
|Automatische Bereitstellung      | Nein            | Nein                   | Ja  |
|Bereitstellungsgeschwindigkeit            | Fast       | Fast                 | Verzögerte Anzeige |
|Bereitstellen im großen Maßstab | Nicht empfohlen    | Empfohlen        | Empfohlen |

## Verwenden von Microsoft Intune oder anderen MDM zum Einrichten eines Kiosks mit einer App oder mehreren Apps

Führen Sie die folgenden Schritte aus, um den Kioskmodus mithilfe von Microsoft Intune oder einem anderen MDM-System einrichten.

1. [Bereiten Sie die Registrierung der Geräte vor.](#mdmenroll)
1. [Erstellen Sie ein Kioskkonfigurationsprofil.](#mdmprofile)
1. Konfigurieren Sie den Kiosk.
   - [Konfigurieren Sie die Einstellungen für einen Single-App-Kiosk.](#mdmconfigsingle)
   - [Konfigurieren Sie die Einstellungen für einen Kiosk mit mehreren Apps.](#mdmconfigmulti)
1. [Weisen Sie das Kioskkonfigurationsprofil einer Gruppe zu.](#mdmassign)
1. Stellen Sie die Geräte zur Verfügung.
   - [Bereitstellen eines Single-App-Kiosks.](#mdmsingledeploy)
   - [Bereitstellen eines Kiosks mit mehreren Apps.](#mdmmultideploy)

### <a id="mdmenroll"></a>MDM, Schritt 1 &ndash; Vorbereiten der Registrierung der Geräte

Sie können Ihr MDM-System so konfigurieren, dass die Registrierung von HoloLens-Geräten automatisch erfolgt, wenn sich der Benutzer zum ersten Mal angemeldet hat, oder Benutzer manuell registrieren lassen. Die Geräte müssen außerdem mit Ihrer Azure AD-Domäne verbunden und den entsprechenden Gruppen zugewiesen werden.

Weitere Informationen zum Registrieren der Geräte finden Sie unter Registrieren von [HoloLens in MDM-](hololens-enroll-mdm.md) und Intune-Registrierungsmethoden [für Windows-Geräte.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)

### <a id="mdmprofile"></a>MDM, Schritt 2 &ndash; Erstellen eines Kioskkonfigurationsprofils

1. Öffnen Sie das [Azure-Portal,](https://portal.azure.com/) und melden Sie sich bei Ihrem Intune-Administratorkonto an.
1. Wählen **Sie "Microsoft**  >  **Intune-Gerätekonfiguration - Profile Erstellen**eines  >  **Profils" aus.**
1. Geben Sie einen Profilnamen ein.
1. Wählen **Sie Plattform**Windows  >  **10 und höher**aus, und wählen Sie dann Geräteeinschränkungen des ****  > **Profiltyps aus.**
1. Wählen **Sie**  >  **"Kiosk**konfigurieren" aus, und wählen Sie dann eine der folgenden Optionen aus:
   - Wählen Sie zum Erstellen eines Single-App-Kiosks den **Kioskmodus**  >  **für einzelne Apps aus.**
   - Um einen Kiosk mit mehreren Apps zu erstellen, wählen Sie ****  >  **Kioskmodus-Multi-App-Kiosk aus.**
1. Um mit der Konfiguration des Kiosks zu beginnen, wählen Sie **"Hinzufügen" aus.**

Die nächsten Schritte unterscheiden sich je nach Kiosktyp. Wählen Sie eine der folgenden Optionen aus, um weitere Informationen zu erhalten:  

- [Single-App-Kiosk](#mdmconfigsingle)
- [Multi-App-Kiosk](#mdmconfigmulti)

Weitere Informationen zum Erstellen eines Kioskkonfigurationsprofils finden Sie unter [Windows 10-](https://docs.microsoft.com/intune/configuration/kiosk-settings)und Windows Holographic for Business-Geräteeinstellungen, die als dedizierter Kiosk mit Intune ausgeführt werden.

### <a id="mdmconfigsingle"></a>MDM, Schritt 3 (Einzel-App) Konfigurieren der Einstellungen &ndash;  für einen Single-App-Kiosk

In diesem Abschnitt werden die Einstellungen zusammengefasst, die für einen Kiosk mit einer einzelnen App erforderlich sind. Weitere Informationen finden Sie in den folgenden Artikeln:

- Informationen zum Konfigurieren eines Kioskkonfigurationsprofils in Intune finden Sie unter ["Konfigurieren des Kioskmodus mit Microsoft Intune".](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)
- Weitere Informationen zu den verfügbaren Einstellungen für Single-App-Kioske in Intune finden Sie unter [Single Full-Screen App Kiosks](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Weitere MDM-Dienste finden Sie in der Dokumentation Ihres Anbieters. Wenn Sie eine benutzerdefinierte XML-Konfiguration zum Einrichten eines Kiosks in Ihrem MDM-Dienst verwenden müssen, erstellen Sie eine XML-Datei, die [die Kioskkonfiguration definiert.](#ppkioskconfig)

1. Wählen **Sie "Benutzeranmeldung "** Lokales Benutzerkonto" aus, und geben Sie dann den Benutzernamen des lokalen (Geräte-)Kontos oder des Microsoft-Kontos  >  ****(MSA) ein, das sich am Kiosk anmelden kann.
   > [!NOTE]  
   > **Automatische Anmeldebenutzerkontotypen** werden unter Windows Holographic for Business nicht unterstützt.
1. Wählen **Sie**  >  **anwendungstyp -Store-App,** und wählen Sie dann eine App aus der Liste.

Im nächsten Schritt wird [das Profil](#mdmassign) einer Gruppe zugewiesen.

### <a id="mdmconfigmulti"></a>MDM, Schritt 3 (Multi-App) &ndash; Konfigurieren der Einstellungen für einen Kiosk mit mehreren Apps

In diesem Abschnitt werden die Einstellungen zusammengefasst, die für einen Kiosk mit mehreren Apps erforderlich sind. Ausführlichere Informationen finden Sie in den folgenden Artikeln:

- Informationen zum Konfigurieren eines Kioskkonfigurationsprofils in Intune finden Sie unter ["Konfigurieren des Kioskmodus mit Microsoft Intune".](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)
- Weitere Informationen zu den verfügbaren Einstellungen für Multi-App-Kioske in Intune finden Sie unter [Multi-App-Kioske.](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Weitere MDM-Dienste finden Sie in der Dokumentation Ihres Anbieters. Wenn Sie eine benutzerdefinierte XML-Konfiguration zum Einrichten eines Kiosks in Ihrem MDM-Dienst verwenden müssen, erstellen Sie eine XML-Datei, die [die Kioskkonfiguration definiert.](#ppkioskconfig) Wenn Sie eine XML-Datei verwenden, stellen Sie sicher, dass Sie das [Startlayout enthalten.](#start-layout-for-hololens)  
- Optional können Sie ein benutzerdefiniertes Startlayout mit Intune oder anderen MDM-Diensten verwenden. Weitere Informationen finden Sie unter ["Startlayoutdatei" für MDM (Intune und andere).](#start-layout-file-for-mdm-intune-and-others)

1. Select **Target Windows 10 in S mode devices**  >  **No**.  
   >[!NOTE]  
   > Der S-Modus wird unter Windows Holographic for Business nicht unterstützt.
1. Wählen **Sie "Benutzeranmeldung" aus,** geben Sie den Azure AD-Benutzer- oder Gruppen- oder Benutzeranmeldungstyp  >  **** ****  >  **"HoloLens-Besucher"** ein, und fügen Sie dann eine oder mehrere Benutzergruppen oder Konten hinzu.  

   Die Kioskerfahrung kann nur von Benutzern verwendet werden, die zu den Gruppen oder Konten gehören, die Sie im **Benutzeranmeldungstyp** angeben.

1. Wählen Sie mithilfe der folgenden Optionen eine oder mehrere Apps aus:
   - Um eine hochgeladene Line-of-Business-App hinzuzufügen, wählen Sie **"Store-App** hinzufügen" und dann die app, die Sie möchten.
   - Wenn Sie eine App hinzufügen möchten, indem Sie ihre AUMID angeben, wählen Sie **"Von AUMID** hinzufügen" aus, und geben Sie dann die AUMID der App ein. [Liste der verfügbaren AUMIDs](#aumids)

Der nächste Schritt besteht im [Zuweisen des](#mdmassign) Profils zu einer Gruppe.

### <a id="mdmassign"></a>MDM, Schritt &ndash; 4: Zuweisen des Kioskkonfigurationsprofils zu einer Gruppe

Verwenden Sie **die Seite "Zuweisungen"** des Kioskkonfigurationsprofils, um den Ort für die Bereitstellung der Kioskkonfiguration zu festlegen. Im einfachsten Fall weisen Sie das Kioskkonfigurationsprofil einer Gruppe zu, die das HoloLens-Gerät enthält, wenn sich das Gerät bei MDM registriert.

### <a id="mdmsingledeploy"></a>MDM, Schritt 5 (Einzel-App) &ndash; Bereitstellen eines Single-App-Kiosks

Wenn Sie ein MDM-System verwenden, können Sie das Gerät während der OOBE bei MDM registrieren. Nach Abschluss der OOBE ist die Anmeldung am Gerät einfach.

Führen Sie während der OOBE die folgenden Schritte aus:

1. Melden Sie sich mit dem Konto an, das Sie im Kioskkonfigurationsprofil angegeben haben.
1. Registrieren Sie das Gerät. Stellen Sie sicher, dass das Gerät der Gruppe hinzugefügt wird, der das Kioskkonfigurationsprofil zugewiesen ist.
1. Warten Sie, bis die OOBE abgeschlossen ist, bis die Store-App heruntergeladen und installiert wird und dass Richtlinien angewendet werden. Starten Sie dann das Gerät neu.

Bei der nächsten Anmeldung am Gerät sollte die Kiosk-App automatisch gestartet werden.

Wenn Ihre Kioskkonfiguration zu diesem Zeitpunkt nicht angezeigt wird, [überprüfen Sie den Zuweisungsstatus.](https://docs.microsoft.com/intune/configuration/device-profile-monitor)

### <a id="mdmmultideploy"></a>MDM, Schritt 5 (Multi-App) &ndash; Bereitstellen eines Kiosks mit mehreren Apps

Wenn Sie ein MDM-System verwenden, können Sie das Gerät mit Ihrem Azure AD-Mandanten verbinden und das Gerät während der OOBE bei MDM registrieren. Geben Sie die Registrierungsinformationen gegebenenfalls den Benutzern an, damit sie sie während des Prozesses der OOBE zur Verfügung haben.

> [!NOTE]  
> Wenn Sie das Kioskkonfigurationsprofil einer Gruppe zugewiesen haben, die Benutzer enthält, stellen Sie sicher, dass eines dieser Benutzerkonten das erste Konto ist, das sich beim Gerät anmeldet.

Führen Sie während der OOBE die folgenden Schritte aus:

1. Melden Sie sich mit dem Konto an, das zur **Benutzeranmeldungstypgruppe** gehört.
1. Registrieren Sie das Gerät.
1. Warten Sie, bis Apps, die Teil des Kioskkonfigurationsprofils sind, heruntergeladen und installiert werden. Warten Sie außerdem, bis Richtlinien angewendet wurden.  
1. Nach Abschluss der OOBE können Sie zusätzliche Apps aus dem Microsoft Store oder durch Querladen installieren. [Erforderliche Apps](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) für die Gruppe, zu der das Gerät gehört, automatisch zu installieren.
1. Starten Sie das Gerät nach Abschluss der Installation neu.

Wenn Sie sich das nächste Mal mit einem Konto anmelden, das zum Benutzeranmeldetyp **gehört,** sollte die Kiosk-App automatisch gestartet werden.

Wenn Die Kioskkonfiguration zu diesem Zeitpunkt nicht angezeigt wird, [überprüfen Sie den Zuweisungsstatus.](https://docs.microsoft.com/intune/configuration/device-profile-monitor)

## Verwenden eines Bereitstellungspakets zum Einrichten eines Kiosks mit einer oder mehreren Apps

Führen Sie die folgenden Schritte aus, um den Kioskmodus mithilfe eines Bereitstellungspakets zu einrichten.

1. [Erstellen Sie eine XML-Datei, die die Kioskkonfiguration definiert.](#ppkioskconfig), einschließlich eines [Startlayouts.](#start-layout-for-hololens)
2. [Fügen Sie die XML-Datei einem Bereitstellungspaket hinzu.](#ppconfigadd)
3. [Wenden Sie das Bereitstellungspaket auf HoloLens an.](#ppapply)

### <a id="ppkioskconfig"></a>Bereitstellungspaket, Schritt 1 &ndash; Erstellen einer Kioskkonfigurations-XML-Datei

Befolgen [Sie die allgemeinen Anweisungen zum Erstellen einer Kioskkonfigurations-XML-Datei für Windows-Desktop,](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)mit Ausnahme der folgenden:

- Schließen Sie keine klassischen Windows-Anwendungen (Win32) ein. HoloLens unterstützt diese Anwendungen nicht.
- Verwenden Sie [die Platzhalter-Startlayout-XML](#start-layout-for-hololens) für HoloLens.
- Optional: Hinzufügen des Gastzugriffs auf die Kioskkonfiguration

#### <a id="ppkioskguest"></a>Optional: Hinzufügen des Gastzugriffs auf die Kioskkonfiguration

Im Abschnitt [ **"Configs"** der](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)XML-Datei können Sie eine spezielle Gruppe namens **"Besucher"** konfigurieren, damit Gäste den Kiosk verwenden können. Wenn der Kiosk für die **** Unterstützung der besonderen Gruppe "Besucher"**** konfiguriert ist, wird der Anmeldeseite die Option "Gast" hinzugefügt. Für **das Gastkonto** ist kein Kennwort erforderlich, und alle dem Konto zugeordneten Daten werden gelöscht, wenn sich das Konto ab meldet.

Um das Gastkonto **zu** aktivieren, fügen Sie den folgenden Codeausschnitt zu Ihrer Kioskkonfigurations-XML hinzu:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a>Platzhalterstartlayout für HoloLens

Wenn Sie ein [Bereitstellungspaket zum](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) Konfigurieren eines Kiosks mit mehreren Apps verwenden, erfordert das Verfahren ein Startlayout. Die Anpassung des Startlayouts wird in Windows Holographic for Business nicht unterstützt. Daher müssen Sie ein Platzhalter-Startlayout verwenden.

> [!NOTE]  
> Da ein Kiosk mit einer einzigen App die Kiosk-App startet, wenn sich ein Benutzer meldet, verwendet er kein Startmenü und muss kein Startlayout haben.

> [!NOTE]  
> Wenn Sie [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) zum Einrichten eines Kiosks mit mehreren Apps verwenden, können Sie optional ein Startlayout verwenden. Weitere Informationen finden Sie unter [Placeholder Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).

Fügen Sie für das Startlayout den folgenden **Abschnitt "StartLayout"** zur Kioskbereitstellungs-XML-Datei hinzu:

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a id="start-layout-file-for-mdm-intune-and-others"></a>Platzhalterstartlayoutdatei für MDM (Intune und andere)

Speichern Sie das folgende Beispiel als XML-Datei. Sie können diese Datei verwenden, wenn Sie den Kiosk mit mehreren Apps in Microsoft Intune (oder in einem anderen MDM-Dienst, der ein Kioskprofil bietet) konfigurieren.

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Einstellung und eine vollständige XML-Konfiguration verwenden müssen, um einen Kiosk in Ihrem MDM-Dienst einrichten zu können, verwenden Sie die Startlayoutanweisungen für ein [Bereitstellungspaket.](#start-layout-for-hololens)

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a id="ppconfigadd"></a>Prov. Paket, Schritt 2 &ndash; Hinzufügen der Kioskkonfigurations-XML-Datei zu einem Bereitstellungspaket

1. Öffnen [Sie Windows-Konfigurations-Designer.](https://www.microsoft.com/store/apps/9nblggh4tx22)
1. Wählen **Sie "Erweiterte Bereitstellung"** aus, geben Sie einen Namen für Ihr Projekt ein, und wählen Sie dann **"Weiter" aus.**
1. Wählen **Sie Windows 10 Holographic**und dann **"Weiter" aus.**
1. Select **Finish**. Der Arbeitsbereich für Ihr Paket wird geöffnet.
1. Wählen **Sie Laufzeiteinstellungen**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings aus.**
1. Wählen Sie im **** rechten Bereich "Durchsuchen" aus, um die erstellte Kioskkonfigurations-XML-Datei zu suchen und auszuwählen.

   ![Screenshot des Felds MultiAppAssignedAccessSettings im Windows-Konfigurations-Designer](./images/multiappassignedaccesssettings.png)

1. **Optional**. (Wenn Sie das Bereitstellungspaket nach der Ersteinrichtung des Geräts anwenden möchten und bereits ein Administratorbenutzer auf dem Kioskgerät verfügbar ist, überspringen Sie diesen Schritt.) Wählen **Sie Laufzeiteinstellungen** &gt; **"Benutzer"** &gt; **** aus, und erstellen Sie dann ein Benutzerkonto. Geben Sie einen Benutzernamen und ein Kennwort ein, und wählen Sie dann **UserGroup**  >  **Administrators aus.**  
  
     Mithilfe dieses Kontos können Sie den Bereitstellungsstatus und die Protokolle anzeigen.  
1. **Optional**. (Wenn Sie bereits über ein Konto ohne Administratorrechte auf dem Kioskgerät verfügen, überspringen Sie diesen Schritt.) Wählen **Sie Laufzeiteinstellungen** &gt; **"Kontenbenutzer"** &gt; **** aus, und erstellen Sie dann ein lokales Benutzerkonto. Stellen Sie sicher, dass der Benutzername mit dem Konto identisch ist, das Sie in der Konfigurations-XML angeben. Wählen Sie **UserGroup**  >  **Standard Users aus.**
1. Wählen Sie **"Datei**  >  **speichern" aus.**
1. Wählen **Sie**  >  **"Bereitstellungspaket exportieren"** und dann **"Besitzer-IT-Administrator"**  >  **aus.** Dadurch wird die Rangfolge dieses Bereitstellungspakets höher als die von anderen Quellen auf dieses Gerät angewendeten Bereitstellungspakete.
1. Wählen Sie **Weiter** aus.
1. Wählen Sie **auf der Seite "Sicherheit des** Bereitstellungspakets" eine Sicherheitsoption aus.
   > [!IMPORTANT]  
   > Wenn Sie **"Paketsignierung aktivieren"** auswählen, müssen Sie auch ein gültiges Zertifikat zum Signieren des Pakets auswählen. Wählen Sie dazu **"Durchsuchen"** aus, und wählen Sie das Zertifikat aus, das Sie zum Signieren des Pakets verwenden möchten.
   
   > [!CAUTION]  
   > Wählen Sie **"Paketverschlüsselung aktivieren" nicht aus.** Auf HoloLens-Geräten führt diese Einstellung zu einem Fehler bei der Bereitstellung.
1. Wählen Sie **Weiter** aus.
1. Geben Sie den Ausgabespeicherort an, an den das Bereitstellungspaket beim Erstellen gehen soll. Standardmäßig verwendet der Windows-Konfigurations-Designer den Projektordner als Ausgabespeicherort. Wenn Sie den Ausgabespeicherort ändern möchten, wählen Sie **Durchsuchen aus.** Wenn Sie fertig sind, wählen Sie **"Weiter" aus.**
1. Wählen **Sie Build** aus, um mit dem Erstellen des Pakets zu beginnen. Die Erstellung eines Bereitstellungspakets dauert nicht lange. Auf der Buildseite werden die Projektinformationen angezeigt, und die Statusanzeige gibt den Buildstatus an.

### <a id="ppapply"></a>Bereitstellungspaket, Schritt 3 &ndash; Anwenden des Bereitstellungspakets auf HoloLens

Der Artikel "Konfigurieren von HoloLens mithilfe eines Bereitstellungspakets" enthält ausführliche Anweisungen zum Anwenden des Bereitstellungspakets unter den folgenden Umständen:

- Sie können zunächst während des Setups ein [Bereitstellungspaket auf HoloLens anwenden.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

- Sie können nach dem Setup auch ein [Bereitstellungspaket auf HoloLens anwenden.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)

## Einrichten eines Single-App-Kiosks mithilfe des Windows Device Portal

Führen Sie die folgenden Schritte aus, um den Kioskmodus mithilfe des Windows Device Portals zu einrichten.

1. [Richten Sie das HoloLens-Gerät für die Verwendung des Windows Device Portal ein.](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal) Das Geräteportal ist ein Webserver auf der HoloLens, mit dem Sie über einen Webbrowser auf dem PC eine Verbindung herstellen können.

    > [!CAUTION]
    > Wenn Sie HoloLens für die Verwendung des Geräteportals einrichten, müssen Sie den Entwicklermodus auf dem Gerät aktivieren. Der Entwicklermodus auf einem Gerät mit Windows Holographic for Business ermöglicht das Sideloaden von Apps. Diese Einstellung besteht jedoch das Risiko, dass ein Benutzer Apps installieren kann, die nicht vom Microsoft Store zertifiziert wurden. Administratoren können die Aktivierung des Entwicklermodus mithilfe der **Einstellung "ApplicationManagement/AllowDeveloper Unlock"** im Richtlinien-CSP [blockieren.](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) [Weitere Informationen zum Entwicklermodus](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Stellen Sie auf einem Computer über [](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) WLAN oder USB eine Verbindung mit HoloLens [herzustellen.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)

1. Führen Sie eine der folgenden Aktionen aus:
   - Wenn Sie zum ersten Mal eine Verbindung mit dem Windows Device Portal herstellen, [erstellen Sie einen Benutzernamen und ein Kennwort.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Geben Sie den Benutzernamen und das Kennwort ein, die Sie zuvor eingerichtet haben.

    > [!TIP]
    > Wenn ein Zertifikatfehler im Browser angezeigt wird, führen Sie [diese Schrittezur Problembehandlung](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate) aus.

1. Wählen Sie im Windows Device Portal den **Kioskmodus aus.**

1. Wählen **Sie "Kioskmodus aktivieren",** wählen Sie eine App aus, die beim Starten des Geräts ausgeführt werden soll, und wählen Sie dann "Speichern" **aus.**

    ![Kioskmodus](images/kiosk.png)
1. Starten Sie HoloLens neu. Wenn Die Seite "Geräteportal" noch geöffnet ist, können Sie oben **auf** der Seite "Neu starten" auswählen.

> [!NOTE]
> Der Kioskmodus kann über die REST-API des Geräteportals festgelegt werden, indem ein POST zu /api/holographic/kioskmode/settings mit einem erforderlichen Abfragezeichenfolgenparameter ("kioskModeEnabled" mit dem Wert "true" oder "false") und einem optionalen Parameter ("startupApp" mit dem Wert eines Paketnamens) ausgeführt wird. Bitte beachten Sie, dass das Geräteportal nur für Entwickler vorgesehen ist und nicht auf Geräten ohne Entwickler aktiviert werden sollte. Die REST-API kann in zukünftigen Updates/Versionen geändert werden.

## Weitere Informationen

### Sehen Sie sich an, wie Sie einen Kiosk mithilfe eines Bereitstellungspakets konfigurieren.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### Global zugewiesener Zugriff – Kioskmodus
- Reduzierte Identitätsverwaltung für Kiosk, indem die neue Kioskmethode aktiviert wird, die den Kioskmodus auf Systemebene verwendet.

Dieses neue Feature ermöglicht es einem IT-Administrator, ein HoloLens 2-Gerät für den Kioskmodus mit mehreren Apps zu konfigurieren, der auf Systemebene anwendbar ist, keine Affinität mit einer Identität im System hat und für alle Benutzer gilt, die sich beim Gerät registrieren. Weitere Informationen zu diesem neuen Feature finden Sie in der Dokumentation zum weltweit zugewiesenen Zugriff von [HoloLens.](hololens-global-assigned-access-kiosk.md)

### Automatisches Starten einer Anwendung im Kioskmodus mit mehreren Apps 
- Fokussierte Erfahrung mit dem automatischen Starten von Apps, um die Auswahl der Benutzeroberfläche und der App weiter zu erhöhen, die für die Benutzeroberfläche des Kioskmodus ausgewählt wurden.

Gilt nur für den Kioskmodus mit mehreren Apps, und nur 1 App kann für den automatischen Start mit hervorgehobenen Attributen unten in der Konfiguration für zugewiesenen Zugriff festgelegt werden. 

Die Anwendung wird automatisch gestartet, wenn sich der Benutzer anmeldet. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### Verhaltensänderungen im Kioskmodus für die Behandlung von Fehlern
- Sichererer Kioskmodus durch Eliminieren verfügbarer Apps bei Kioskmodusfehlern. 

Vor dem Auftreten von Fehlern beim Anwenden des Kioskmodus hat HoloLens alle Anwendungen im Startmenü angezeigt. In Windows Holographic, Version 20H2, werden im Falle von Fehlern keine Apps im Startmenü wie folgt angezeigt: 

![Abbildung des Kioskmodus, der jetzt aussieht, wenn er fehlschlägt.](images/hololens-kiosk-failure-behavior.png )

### Azure AD-Gruppenmitgliedschaft für Offlinekiosk zwischenspeichern
- Aktivierte Offline kiosks für die Verwendung mit Azure AD-Gruppen für bis zu 60 Tage.

Diese Richtlinie steuert, wie viele Tage der Azure AD-Gruppenmitgliedschaftscache für Konfigurationen mit zugewiesenen Zugriffen für Azure AD-Gruppen für angemeldete Benutzer verwendet werden darf. Sobald dieser Richtlinienwert auf einen Wert größer als 0 festgelegt ist, wird der Cache andernfalls nicht verwendet.  

Name: AADGroupMembershipCacheValidityInDays URI-Wert: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min : 0 Tage  
Max . 60 Tage 

Schritte zur ordnungsgemäßen Verwendung dieser Richtlinie: 
1. Erstellen Sie ein Gerätekonfigurationsprofil für den Kiosk für Azure AD-Gruppen, und weisen Sie es holoLens-Geräten zu. 
1. Erstellen Sie eine benutzerdefinierte OMA-URI-basierte Gerätekonfiguration, mit der dieser Richtlinienwert auf die gewünschte Anzahl von Tagen (> 0) und holoLens-Geräten zugewiesen wird. 
    1. Der URI-Wert sollte im Textfeld "OMA-URI" als "./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays" eingegeben werden.
    1. Der Wert kann zwischen min/max allowed liegen.
1. Registrieren Sie HoloLens-Geräte, und überprüfen Sie, ob beide Konfigurationen auf das Gerät angewendet werden. 
1. Lassen Sie Azure AD Benutzer 1 anmelden, wenn das Internet verfügbar ist, sobald sich der Benutzer anmeldet und die Azure AD-Gruppenmitgliedschaft erfolgreich bestätigt wurde, wird der Cache erstellt. 
1. Jetzt kann Azure AD Benutzer 1 HoloLens offline schalten und für den Kioskmodus verwenden, solange der Richtlinienwert X Tage zulässt. 
1. Die Schritte 4 und 5 können für alle anderen Azure AD-Benutzer N wiederholt werden. Der wichtigste Punkt hier ist, dass sich jeder Azure AD-Benutzer über das Internet bei einem Gerät anmelden muss, damit wir mindestens einmal feststellen können, dass er Mitglied der Azure AD-Gruppe ist, für die die Kioskkonfiguration bestimmt ist. 
 
> [!NOTE]
> Bis Schritt 4 für einen Azure AD-Benutzer ausgeführt wird, tritt ein Fehlerverhalten auf, das in "getrennten" Umgebungen erwähnt wird. 


## CODEbeispiele für den XML-Kiosk für HoloLens

### Kioskmodus mit mehreren Apps für eine Azure AD-Gruppe. 
Dieser Kiosk stellt einen Kiosk bereit, der für Benutzer in der Azure AD-Gruppe einen Kiosk aktiviert hat, der die 3 Apps umfasst: Einstellungen, Remote assist und Feedback Hub. Um dieses Beispiel so zu ändern, dass es sofort verwendet wird, müssen Sie die unten hervorgehobene GUID so ändern, dass sie einer eigenen Azure AD-Gruppe zu entsprechen. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### Mehrere App-Kioskmodus für Azure AD-Konto.
Dieser Kiosk stellt einen Kiosk für einen einzelnen Benutzer zur Verfügung. Es ist ein Kiosk aktiviert, der die 3 Apps umfasst: Einstellungen, Remote assist und Feedback Hub. Um dieses Beispiel so zu ändern, dass es sofort verwendet wird, müssen Sie das unten hervorgehobene Konto so ändern, dass es einem eigenen Azure AD-Konto zu entsprechen. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

