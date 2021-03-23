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
ms.openlocfilehash: a043b2f96bec6127d52622b4662279c777df6f8f
ms.sourcegitcommit: e1dd3d79d763d02d4fe04c82d8f49e8f9d85ee4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "11445375"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Einrichten von HoloLens als Kiosk

Sie können ein HoloLens-Gerät so konfigurieren, dass es als Einzweckgerät, auch Kiosk *genannt,* funktioniert, indem Sie das Gerät so konfigurieren, dass es im Kioskmodus ausgeführt wird. Der Kioskmodus schränkt die Auf dem Gerät verfügbaren Anwendungen (oder Benutzer) ein. Der Kioskmodus ist ein praktisches Feature, mit dem Sie ein HoloLens-Gerät Geschäfts-Apps widmen oder das HoloLens-Gerät in einer App-Demo verwenden können.

Dieser Artikel enthält Informationen zu Aspekten der Kioskkonfiguration, die für HoloLens-Geräte spezifisch sind. Allgemeine Informationen zu den verschiedenen Typen von Windows-basierten Kiosken und deren Konfiguration finden Sie unter [Configure kiosks and digital signs on Windows desktop editions](https://docs.microsoft.com/windows/configuration/kiosk-methods).  

> [!IMPORTANT]  
> Der Kioskmodus bestimmt, welche Apps verfügbar sind, wenn sich ein Benutzer beim Gerät einschreibt. Der Kioskmodus ist jedoch keine Sicherheitsmethode. Es wird nicht beendet, dass eine "zulässige" App eine andere App öffnet, die nicht zulässig ist. Um das Öffnen von Apps oder Prozessen zu blockieren, verwenden Sie [Windows Defender #A0 (Application Control, WDAC),](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) um geeignete Richtlinien zu erstellen.
>
> Erfahren Sie mehr über die Microsoft-Dienste, um Benutzern ein erweitertes Sicherheitsniveau zu bieten, das HoloLens 2 verwendet. Weitere Informationen finden Sie unter [State separation and isolation - Defender protections](security-state-separation-isolation.md#defender-protections). Oder erfahren Sie, wie Sie WDAC und Windows PowerShell verwenden, um Apps auf [HoloLens 2-Geräten](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)mit Microsoft Intune zu erlauben oder zu blockieren.

Sie können den Kioskmodus entweder in einer Einzel- oder einer Multi-App-Konfiguration verwenden, und Sie können einen von drei Prozessen zum Einrichten und Bereitstellen der Kioskkonfiguration verwenden.

> [!IMPORTANT]  
> Durch löschen der Multi-App-Konfiguration werden die Benutzersperrenprofile entfernt, die das Feature für den zugewiesenen Zugriff erstellt hat. Es werden jedoch nicht alle Richtlinienänderungen zurückgesetzt. Zum Wiederherstellen dieser Richtlinien müssen Sie das Gerät auf die Werkseinstellungen zurücksetzen.

## <a name="plan-the-kiosk-deployment"></a>Planen der Kioskbereitstellung

Bei der Planung Ihres Kiosks müssen Sie die folgenden Fragen beantworten können. Im Folgenden finden Sie einige Entscheidungen, die Sie beim Lesen dieser Seite berücksichtigen sollten, sowie einige Überlegungen zu diesen Fragen.
1. **Wer verwendet Ihren Kiosk, und welche [Kontotypen](hololens-identity.md) werden verwendet?** Dies ist eine Entscheidung, die Sie wahrscheinlich bereits getroffen haben und nicht zum Wohle Ihres Kiosks angepasst werden sollten, sondern sich darauf auswirken, wie der Kiosk später zugewiesen wird.
1. **Benötigen Sie unterschiedliche Kioske pro Benutzer/Gruppe oder einen Kiosk, der für einige nicht aktiviert ist?** Wenn ja, möchten Sie Ihren Kiosk über XML erstellen. 
1. **Wie viele Apps werden in Ihrem Kiosk installiert sein?** Wenn Sie über mehr als 1 App verfügen, benötigen Sie einen Kiosk mit mehreren Apps. 
1. **Welche Apps werden in Ihrem Kiosk angezeigt?** Verwenden Sie unsere Liste der AUMIDs unten, um In-Box apps zusätzlich zu Ihren eigenen hinzuzufügen.
1. **Wie planen Sie die Bereitstellung Ihres Kiosks?** Wenn Sie das Gerät bei MDM registrieren, empfehlen wir die Verwendung von MDM zur Bereitstellung Ihres Kiosks. Wenn Sie MDM nicht verwenden, ist die Bereitstellung mit Bereitstellungspaket verfügbar.  

### <a name="kiosk-mode-requirements"></a>Kioskmodusanforderungen

Sie können jedes HoloLens 2-Gerät für die Verwendung des Kioskmodus konfigurieren.

> [!IMPORTANT]
> Der Kioskmodus ist nur verfügbar, wenn das Gerät über Windows Holographic for Business verfügt. Alle HoloLens 2-Geräte sind mit Windows Holographic for Business enthalten, und es gibt keine anderen Editionen. Auf allen HoloLens 2-Geräten kann der Kioskmodus von vorn ausgeführt werden.
>
> HoloLens-Geräte (1. Generation) müssen sowohl im Hinblick auf den Betriebssystemaufbau als auch auf die Betriebssystemversion aktualisiert werden. Hier finden Sie weitere Informationen zum Aktualisieren einer HoloLens (1. Generation) auf [Windows Holographic for Business](hololens1-upgrade-enterprise.md) Edition. Um ein HoloLens-Gerät (1. Generation) für den Kioskmodus zu aktualisieren, müssen Sie zunächst sicherstellen, dass auf dem Gerät Windows 10, Version 1803 oder eine neuere Version ausgeführt wird. Wenn Sie das Windows Device Recovery Tool verwendet haben, um Ihr HoloLens-Gerät (1. Generation) auf seinen Standard build wiederhergestellt zu haben, oder wenn Sie die neuesten Updates installiert haben, kann Ihr Gerät konfiguriert werden.

> [!IMPORTANT]  
> Um Geräte zu schützen, die im Kioskmodus ausgeführt werden, sollten Sie Geräteverwaltungsrichtlinien hinzufügen, die Features wie die USB-Konnektivität deaktivieren. Überprüfen Sie außerdem die Updateringeinstellungen, um sicherzustellen, dass während der Geschäftszeiten keine automatischen Updates auftreten.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Entscheidung zwischen einem Kiosk mit einer app oder einem Kiosk mit mehreren Apps

Ein Kiosk mit einer einzelnen App startet die angegebene App, wenn sich der Benutzer beim Gerät einschreibt. Das Startmenü ist deaktiviert, ebenso Cortana. Ein HoloLens 2-Gerät reagiert nicht auf die [Startgeste.](hololens2-basic-usage.md#start-gesture) Ein HoloLens-Gerät (1. Generation) reagiert nicht auf die [Blühgeste.](hololens1-basic-usage.md) Da nur eine App ausgeführt werden kann, kann der Benutzer keine anderen Apps platzieren.

Ein Kiosk mit mehreren Apps zeigt das Startmenü an, wenn sich der Benutzer beim Gerät einschreibt. Die Kioskkonfiguration bestimmt, welche Apps im Startmenü verfügbar sind. Sie können einen Multi-App-Kiosk verwenden, um Benutzern eine leicht verständliche Benutzererfahrung zu bieten, indem Sie ihnen nur die Dinge präsentieren, die sie verwenden müssen, und die Dinge entfernen, die sie nicht verwenden müssen.

In der folgenden Tabelle sind die Featurefunktionen in den verschiedenen Kioskmodi aufgeführt.

| &nbsp; |Startmenü |Menü "Schnellaktionen" |Kamera und Video |Miracast |Cortana |Integrierte Sprachbefehle |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|Single-App-Kiosk |Deaktiviert |Deaktiviert   |Deaktiviert |Deaktiviert   |Deaktiviert |Aktiviert <sup> 1</sup> |
|Multi-App-Kiosk |Aktiviert |Aktiviert <sup> 2</sup> |Verfügbar <sup> 2</sup> |Verfügbar <sup> 2</sup> |Verfügbar <sup> 2, 3</sup>  |Aktiviert <sup> 1</sup> |

> <sup>1 </sup> Sprachbefehle, die sich auf deaktivierte Features beziehen, funktionieren nicht.  
> <sup>2 Weitere Informationen zum Konfigurieren dieser Features finden Sie </sup> unter Select kiosk [apps](#plan-kiosk-apps).  
> <sup>3 </sup> Selbst wenn Cortana deaktiviert ist, sind die integrierten Sprachbefehle aktiviert.

In der folgenden Tabelle sind die Benutzerunterstützungsfeatures der verschiedenen Kioskmodi aufgeführt.

| &nbsp; |Unterstützte Benutzertypen | Automatische Anmeldung | Mehrere Zugriffsebenen |
| --- | --- | --- | --- |
|Single-App-Kiosk |Verwaltetes Dienstkonto (Managed Service Account, MSA) in Azure Active Directory (Azure AD) oder lokales Konto |Ja |Nein |
|Multi-App-Kiosk |Azure AD-Konto |Nein |Ja |

Beispiele für die Verwendung dieser Funktionen finden Sie in der folgenden Tabelle.

|Verwenden Sie einen Kiosk mit einer einzigen App für: |Verwenden Sie einen Multi-App-Kiosk für: |
| --- | --- |
|Ein Gerät, auf dem nur ein Dynamics 365-Leitfaden für neue Mitarbeiter ausgeführt wird. |Ein Gerät, auf dem Führungslinien und Remoteunterstützung für eine Reihe von Mitarbeitern ausgeführt werden. |
|Ein Gerät, auf dem nur eine benutzerdefinierte App ausgeführt wird. |Ein Gerät, das für die meisten Benutzer als Kiosk fungiert (nur eine benutzerdefinierte App ausgeführt wird), aber als Standardgerät für eine bestimmte Gruppe von Benutzern fungiert. |

### <a name="plan-kiosk-apps"></a>Planen von Kiosk-Apps

Allgemeine Informationen zur Auswahl von Kiosk-Apps finden Sie unter Richtlinien für die Auswahl einer App für den zugewiesenen [Zugriff (Kioskmodus).](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)

Wenn Sie das Windows-Geräteportal verwenden, um einen Kiosk mit einer einzigen App zu konfigurieren, wählen Sie die App während des Setupvorgangs aus.  

Wenn Sie ein Mobile Device Management (MDM)-System oder ein Bereitstellungspaket zum Konfigurieren des Kioskmodus verwenden, verwenden Sie den [AssignedAccess Configuration Service Provider (CSP),](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) um Anwendungen anzugeben. Der CSP verwendet [Anwendungsbenutzermodell-IDs (Application User Model IDs, AUMIDs),](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) um Anwendungen zu identifizieren. In der folgenden Tabelle sind die AUMIDs einiger in-Box-Anwendungen aufgeführt, die Sie in einem Kiosk mit mehreren Apps verwenden können.

> [!IMPORTANT]
> Der Kioskmodus bestimmt, welche Apps verfügbar sind, wenn sich ein Benutzer beim Gerät einschreibt. Der Kioskmodus ist jedoch keine Sicherheitsmethode. Es wird nicht beendet, dass eine "zulässige" App eine andere App öffnet, die nicht zulässig ist. Da wir dieses Verhalten nicht einschränken, können Apps weiterhin über Edge, den Datei-Explorer und die Microsoft Store-Apps gestartet werden. Wenn bestimmte Apps nicht von einem Kiosk aus gestartet werden sollen, verwenden Sie Windows Defender [#A0 (Application Control, WDAC),](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) um geeignete Richtlinien zu erstellen. 
> 
> Darüber hinaus kann das Mixed Reality Home nicht als Kiosk-App festgelegt werden.

<a id="aumids"></a>

|App-Name |AUMID |
| --- | --- |
|3D-Viewer |Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\! Microsoft.Microsoft3DViewer |
|Kalender |microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar |
|Kamera <sup> 1, 2</sup> |HoloCamera\_cw5n1h2txyewy\! HoloCamera |
|Cortana <sup> 3</sup> |Microsoft.549981C3F5F10\_8wekyb3d8bbwe\! App |
|Geräteauswahl auf HoloLens (1. Generation) |HoloDevicesFlow\_cw5n1h2txyewy\! HoloDevicesFlow |
|Geräteauswahl auf HoloLens 2 |Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\! Microsoft.Windows.DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\! MicrosoftGuides |
|Dynamics365 Remote Assist |Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\! Microsoft.RemoteAssist |
|Feedback &nbsp; Hub |Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\! App |
|Datei-Explorer |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast <sup> 4</sup> |&nbsp; |
|Filme & TV |Microsoft.ZuneVideo\_8wekyb3d8bbwe\! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive\_8wekyb3d8bbwe\! App |
|Fotos |Microsoft.Windows.Fotos\_8wekyb3d8bbwe\! App |
|Einstellungen |HolographicSystemSettings\_cw5n1h2txyewy\! App |
|Tipps |Microsoft.HoloLensTips\_8wekyb3d8bbwe\! HoloLensTips |

> <sup>1 Zum Aktivieren der Foto- oder Videoaufnahme müssen Sie die </sup> Kamera-App als Kiosk-App aktivieren.  
> <sup>2 </sup> Wenn Sie die Kamera-App aktivieren, beachten Sie die folgenden Bedingungen:
> - Das Menü Schnellaktionen enthält die Schaltflächen Foto und Video.  
> - Sie sollten auch eine App aktivieren (z. B. Fotos, Mail oder OneDrive), die mit Bildern interagieren oder bilder abrufen kann.  
>  
> <sup>3 Auch wenn Sie Cortana nicht als </sup> Kiosk-App aktivieren, sind integrierte Sprachbefehle aktiviert. Befehle im Zusammenhang mit deaktivierten Features haben jedoch keine Auswirkung.  
> <sup>4 </sup> Miracast kann nicht direkt aktiviert werden. Um Miracast als Kiosk-App zu aktivieren, aktivieren Sie die Kamera-App und die Geräteauswahl-App.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Planen von Kioskprofilen für Benutzer oder Gruppen

Wenn Sie entweder die XML-Datei erstellen oder die Benutzeroberfläche von Intune zum Einrichten eines Kiosks verwenden, müssen Sie überlegen, wer der Benutzer des Kiosks sein wird. Eine Kioskkonfiguration kann entweder auf ein einzelnes Konto oder Azure AD-Gruppen beschränkt werden. 

In der Regel sind Kioske entweder für einen Benutzer oder eine Benutzergruppe aktiviert. Wenn Sie jedoch einen eigenen XML-Kiosk schreiben möchten, sollten Sie den globalen zugewiesenen Zugriff in Betracht ziehen, bei dem der Kiosk unabhängig von Der Identität auf Geräteebene angewendet wird. Wenn dies für Sie [spricht, lesen Sie mehr über Globale Kioske mit zugewiesenem Zugriff.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>Wenn Sie eine XML-Datei erstellen:
-   Viele erstellen mehrere Kioskprofile, und weisen sie jeweils unterschiedlichen Benutzern/Gruppen zu. Beispielsweise ein Kiosk für Ihre Azure AD-Gruppe mit vielen Apps und ein Besucher, der über einen Kiosk mit mehreren Apps mit einer einzelnen App verfügt.
-   Ihre Kioskkonfiguration wird als **Profil-ID bezeichnet** und hat eine GUID.
-   Sie weisen dieses Profil im Abschnitt configs zu, indem Sie den Benutzertyp angeben und dieselbe GUID für die **DefaultProfile-ID verwenden.**
- Eine XML-Datei kann über MDM erstellt, aber dennoch auf ein Gerät angewendet werden, indem ein benutzerdefiniertes OMA-URI-Gerätekonfigurationsprofil erstellt und mithilfe des URI-Werts auf die HoloLens-Gerätegruppe angewendet wird: ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Wenn Sie einen Kiosk in Intune erstellen.
-   Jedes Gerät kann nur ein einzelnes Kioskprofil erhalten, andernfalls wird ein Konflikt erstellt und keine Kioskkonfigurationen empfangen. 
    -   Andere Arten von Profilen und Richtlinien, z. B. Geräteeinschränkungen, die nicht mit dem Kioskkonfigurationsprofil in Zusammenhang stehen, stehen nicht im Konflikt mit dem Kioskkonfigurationsprofil.
-   Der Kiosk wird für alle Benutzer aktiviert, die Teil des Benutzeranmeldungstyps sind. Dies wird mit einem Benutzer oder einer Azure AD-Gruppe festgelegt. 
-   Nachdem die Kioskkonfiguration festgelegt **** und der Benutzeranmeldungstyp (Benutzer, die sich am Kiosk anmelden können) und die Apps ausgewählt sind, muss die Gerätekonfiguration weiterhin einer Gruppe zugewiesen werden. Die zugewiesenen Gruppen bestimmen, welche Geräte die Kioskgerätekonfiguration empfangen, interagieren jedoch nicht, wenn der Kiosk aktiviert ist oder nicht. 
    - Eine vollständige Diskussion über die Auswirkungen der Zuweisung von Konfigurationsprofilen in Intune finden Sie unter [Assign user and device profiles in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).

### <a name="select-a-deployment-method"></a>Auswählen einer Bereitstellungsmethode

Sie können eine der folgenden Methoden zum Bereitstellen von Kioskkonfigurationen auswählen:

- [Microsoft Intune oder ein anderer Mobile Device Management (MDM)-Dienst](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Bereitstellungspaket](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Geräteportal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Da diese Methode erfordert, dass der Entwicklermodus auf dem Gerät aktiviert ist, wird empfohlen, ihn nur für Demonstrationen zu verwenden.

In der folgenden Tabelle sind die Funktionen und Vorteile der einzelnen Bereitstellungsmethoden aufgeführt.

| &nbsp; |Bereitstellen mithilfe des Windows-Geräteportals |Bereitstellen mithilfe eines Bereitstellungspakets |Bereitstellen mithilfe von MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Bereitstellen von Single-App-Kiosken   | Ja           | Ja                  | Ja  |
|Bereitstellen von Multi-App-Kiosken    | Nein            | Ja                  | Ja  |
|Nur auf lokalen Geräten bereitstellen | Ja           | Ja                  | Nein   |
|Bereitstellen mithilfe des Entwicklermodus |Erforderlich       | Nicht erforderlich            | Nicht erforderlich   |
|Bereitstellen mithilfe von Azure Active Directory (Azure AD)  | Nicht erforderlich            | Nicht erforderlich                   | Erforderlich  |
|Automatische Bereitstellung      | Nein            | Nein                   | Ja  |
|Bereitstellungsgeschwindigkeit            | Fast       | Fast                 | Verzögerte Anzeige |
|Bereitstellen im Großen und Umfang | Nicht empfohlen    | Empfohlen        | Empfohlen |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Einrichten eines Kiosks mit einer app oder mehreren Apps mithilfe von Microsoft Intune oder anderen MDM

Führen Sie die folgenden Schritte aus, um den Kioskmodus mithilfe von Microsoft Intune oder einem anderen MDM-System einrichten.

1. [Bereiten Sie die Registrierung der Geräte vor.](#mdmenroll)
1. [Erstellen Eines Kioskkonfigurationsprofils](#mdmprofile).
1. Konfigurieren Sie den Kiosk.
   - [Konfigurieren Sie die Einstellungen für einen Kiosk mit einer einzigen App.](#mdmconfigsingle)
   - [Konfigurieren Sie die Einstellungen für einen Multi-App-Kiosk.](#mdmconfigmulti)
1. [Weisen Sie das Kioskkonfigurationsprofil einer Gruppe zu.](#mdmassign)
1. Stellen Sie die Geräte zur Verfügung.
   - [Bereitstellen eines Kiosks mit einer einzigen App](#mdmsingledeploy).
   - [Bereitstellen eines Multi-App-Kiosks](#mdmmultideploy).

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, Schritt 1 &ndash; Vorbereiten der Registrierung der Geräte

Sie können Ihr MDM-System so konfigurieren, dass HoloLens-Geräte automatisch registriert werden, wenn sich der Benutzer zum ersten Mal meldet oder Benutzer Geräte manuell registrieren lassen. Die Geräte müssen außerdem Ihrer Azure AD-Domäne beigetreten und den entsprechenden Gruppen zugewiesen werden.

Weitere Informationen zum Registrieren der Geräte finden Sie unter [Enroll HoloLens in MDM](hololens-enroll-mdm.md) and [Intune enrollment methods for Windows devices](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, Schritt 2 &ndash; Erstellen eines Kioskkonfigurationsprofils

1. Öffnen [](https://portal.azure.com/) Sie das Azure-Portal, und melden Sie sich bei Ihrem Intune-Administratorkonto an.
1. Wählen **Sie Microsoft Intune**Device configuration - Profiles  >  **Create**profile  >  **aus.**
1. Geben Sie einen Profilnamen ein.
1. Wählen **Sie Plattform**Windows  >  **10 und höher**aus, und wählen Sie dann **Profiltyp**  > **Geräteeinschränkungen aus.**
1. Wählen **Sie**  >  **Kiosk**konfigurieren aus, und wählen Sie dann eine der folgenden Optionen aus:
   - Um einen Kiosk mit einer einzigen App zu erstellen, wählen Sie **Kioskmodus**  >  **Single-App-Kiosk aus.**
   - Zum Erstellen eines Multi-App-Kiosks wählen Sie **Kioskmodus**  >  **Multi-App-Kiosk aus.**
1. Wählen Sie Hinzufügen aus, um mit der Konfiguration des Kiosks **zu beginnen.**

Die nächsten Schritte unterscheiden sich je nach Dem Typ des Kiosks, den Sie wünschen. Wählen Sie eine der folgenden Optionen aus, um weitere Informationen zu erhalten:  

- [Single-App-Kiosk](#mdmconfigsingle)
- [Multi-App-Kiosk](#mdmconfigmulti)

Weitere Informationen zum Erstellen eines Kioskkonfigurationsprofils finden Sie unter [Windows 10-](https://docs.microsoft.com/intune/configuration/kiosk-settings)und Windows Holographic for Business-Geräteeinstellungen, die als dedizierter Kiosk mit Intune ausgeführt werden.

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, Schritt 3 (Einzel-App) Konfigurieren der Einstellungen &ndash;  für einen Kiosk mit einer app

In diesem Abschnitt werden die Einstellungen zusammengefasst, die für einen Kiosk mit einer einzelnen App erforderlich sind. Weitere Informationen finden Sie in den folgenden Artikeln:

- Informationen zum Konfigurieren eines Kioskkonfigurationsprofils in Intune finden Sie unter [Konfigurieren des Kioskmodus mithilfe von Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Weitere Informationen zu den verfügbaren Einstellungen für Single-App-Kioske in Intune finden Sie unter [Single full-screen app kiosks.](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Weitere MDM-Dienste finden Sie in der Dokumentation Ihres Anbieters. Wenn Sie eine benutzerdefinierte XML-Konfiguration zum Einrichten eines Kiosks in Ihrem MDM-Dienst verwenden müssen, erstellen Sie eine XML-Datei, die [die Kioskkonfiguration definiert.](#ppkioskconfig)

1. Wählen **Sie Benutzeranmeldung typ**Lokales Benutzerkonto aus, und geben Sie dann den Benutzernamen des lokalen (Geräte-) Kontos oder des  >  **** Microsoft-Kontos (MSA) ein, das sich am Kiosk anmelden kann.
   > [!NOTE]  
   > **Automatische** Anmeldebenutzerkontotypen werden unter Windows Holographic for Business nicht unterstützt.
1. Wählen **Sie**  >  **Anwendungstyp Store-App**aus, und wählen Sie dann eine App aus der Liste aus.

Im nächsten Schritt weisen [Sie das](#mdmassign) Profil einer Gruppe zu.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, Schritt 3 (Multi-App) &ndash; Konfigurieren der Einstellungen für einen Multi-App-Kiosk

In diesem Abschnitt werden die Einstellungen zusammengefasst, die für einen Kiosk mit mehreren Apps erforderlich sind. Weitere Informationen finden Sie in den folgenden Artikeln:

- Informationen zum Konfigurieren eines Kioskkonfigurationsprofils in Intune finden Sie unter [Konfigurieren des Kioskmodus mithilfe von Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Weitere Informationen zu den verfügbaren Einstellungen für Multi-App-Kioske in Intune finden Sie unter [Multi-App-Kioske.](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Weitere MDM-Dienste finden Sie in der Dokumentation Ihres Anbieters. Wenn Sie eine benutzerdefinierte XML-Konfiguration zum Einrichten eines Kiosks in Ihrem MDM-Dienst verwenden müssen, erstellen Sie eine XML-Datei, die [die Kioskkonfiguration definiert.](#ppkioskconfig) Wenn Sie eine XML-Datei verwenden, stellen Sie sicher, dass Sie das [Startlayout enthalten.](#start-layout-for-hololens)  
- Optional können Sie ein benutzerdefiniertes Startlayout mit Intune oder anderen MDM-Diensten verwenden. Weitere Informationen finden Sie unter [Startlayoutdatei für MDM (Intune und andere).](#start-layout-file-for-mdm-intune-and-others)

1. Wählen **Sie Ziel windows 10 im S-Modus Geräte**Nein  >  **aus.**  
   >[!NOTE]  
   > Der S-Modus wird unter Windows Holographic for Business nicht unterstützt.
1. Wählen **Sie Benutzeranmeldung typ**Azure AD Benutzer oder Gruppe oder Benutzeranmeldung Typ HoloLens besucher , und fügen Sie dann eine oder mehrere  >  **** ****  >  **** Benutzergruppen oder Konten hinzu.  

   Nur Benutzer, die zu den Gruppen oder Konten gehören, die Sie im **Benutzeranmeldungstyp** angeben, können die Kioskerfahrung verwenden.

1. Wählen Sie eine oder mehrere Apps mithilfe der folgenden Optionen aus:
   - Wenn Sie eine hochgeladene Line-of-Business-App hinzufügen möchten, wählen Sie **Store-App** hinzufügen aus, und wählen Sie dann die app aus, die Sie möchten.
   - Wenn Sie eine App hinzufügen möchten, indem Sie ihre AUMID angeben, wählen Sie **Hinzufügen durch AUMID** aus, und geben Sie dann die AUMID der App ein. [Siehe liste der verfügbaren AUMIDs](#aumids)

Im nächsten Schritt weisen [Sie das](#mdmassign) Profil einer Gruppe zu.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, Schritt 4 &ndash; Zuweisen des Kioskkonfigurationsprofils zu einer Gruppe

Verwenden Sie die **Seite Zuweisungen** des Kioskkonfigurationsprofils, um die Stelle zu festlegen, an der die Kioskkonfiguration bereitgestellt werden soll. Im einfachsten Fall weisen Sie das Kioskkonfigurationsprofil einer Gruppe zu, die das HoloLens-Gerät enthält, wenn sich das Gerät bei MDM registriert.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, Schritt 5 (Einzel-App) &ndash; Bereitstellen eines Kiosks mit einer App

Wenn Sie ein MDM-System verwenden, können Sie das Gerät während der OOBE bei MDM registrieren. Nach Abschluss von OOBE ist die Anmeldung beim Gerät einfach.

Führen Sie während der OOBE die folgenden Schritte aus:

1. Melden Sie sich mit dem Konto an, das Sie im Kioskkonfigurationsprofil angegeben haben.
1. Registrieren Sie das Gerät. Stellen Sie sicher, dass das Gerät der Gruppe hinzugefügt wird, der das Kioskkonfigurationsprofil zugewiesen ist.
1. Warten Sie, bis OOBE abgeschlossen ist, bis die Store-App heruntergeladen und installiert wurde und dass Richtlinien angewendet werden. Starten Sie das Gerät neu.

Wenn Sie sich das nächste Mal beim Gerät anmelden, sollte die Kiosk-App automatisch gestartet werden.

Wenn Die Kioskkonfiguration zu diesem Zeitpunkt nicht angezeigt wird, [überprüfen Sie den Zuweisungsstatus](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, Schritt 5 (Multi-App) &ndash; Bereitstellen eines Multi-App-Kiosks

Wenn Sie ein MDM-System verwenden, können Sie das Gerät ihrem Azure AD-Mandanten beitreten und das Gerät während der OOBE bei MDM registrieren. Geben Sie den Benutzern gegebenenfalls die Registrierungsinformationen an, damit sie während des OOBE-Prozesses zur Verfügung stehen.

> [!NOTE]  
> Wenn Sie das Kioskkonfigurationsprofil einer Gruppe zugewiesen haben, die Benutzer enthält, stellen Sie sicher, dass eines dieser Benutzerkonten das erste Konto ist, das sich beim Gerät anmeldet.

Führen Sie während der OOBE die folgenden Schritte aus:

1. Melden Sie sich mit dem Konto an, das zur **Benutzeranmeldungstypgruppe** gehört.
1. Registrieren Sie das Gerät.
1. Warten Sie, bis apps, die Teil des Kioskkonfigurationsprofils sind, heruntergeladen und installiert werden. Warten Sie außerdem, bis Richtlinien angewendet werden.  
1. Nach Abschluss von OOBE können Sie zusätzliche Apps aus dem Microsoft Store oder durch Querladen installieren. [Erforderliche Apps](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) für die Gruppe, zu der das Gerät gehört, automatisch zu installieren.
1. Starten Sie das Gerät nach Abschluss der Installation neu.

Wenn Sie sich das nächste Mal mit einem Konto anmelden, das zum Benutzeranmeldetyp **gehört,** sollte die Kiosk-App automatisch gestartet werden.

Wenn Die Kioskkonfiguration zu diesem Zeitpunkt nicht angezeigt wird, [überprüfen Sie den Zuweisungsstatus](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Verwenden eines Bereitstellungspakets zum Einrichten eines Kiosks mit einer oder mehreren Apps

Führen Sie die folgenden Schritte aus, um den Kioskmodus mithilfe eines Bereitstellungspakets zu einrichten.

1. [Erstellen Sie eine XML-Datei, die die Kioskkonfiguration definiert.](#ppkioskconfig), einschließlich eines [Startlayouts](#start-layout-for-hololens).
2. [Fügen Sie die XML-Datei einem Bereitstellungspaket hinzu.](#ppconfigadd)
3. [Wenden Sie das Bereitstellungspaket auf HoloLens an.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Bereitstellungspaket, Schritt 1 &ndash; Erstellen einer KIOSKkonfigurations-XML-Datei

Befolgen [Sie die allgemeinen Anweisungen zum Erstellen einer XML-Datei für die Kioskkonfiguration für Windows-Desktop,](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)mit Ausnahme der folgenden:

- Schließen Sie keine klassischen Windows-Anwendungen (Win32) ein. HoloLens unterstützt diese Anwendungen nicht.
- Verwenden Sie [die Platzhalter-Startlayout-XML](#start-layout-for-hololens) für HoloLens.
- Optional: Hinzufügen des Gastzugriffs zur Kioskkonfiguration

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>Optional: Hinzufügen des Gastzugriffs zur Kioskkonfiguration

Im [ **Abschnitt Configs** der XML-Datei](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)können Sie eine spezielle Gruppe namens **Visitor** konfigurieren, damit Gäste den Kiosk verwenden können. Wenn der Kiosk für die Unterstützung der Sondergruppe **"Besucher"** konfiguriert ist, wird der Anmeldeseite eine**Option**"Gast" hinzugefügt. Für **das Gastkonto** ist kein Kennwort erforderlich, und alle dem Konto zugeordneten Daten werden gelöscht, wenn sich das Konto ab meldet.

Um das **Gastkonto zu** aktivieren, fügen Sie ihrem Kioskkonfigurations-XML den folgenden Codeausschnitt hinzu:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>Platzhalter-Startlayout für HoloLens

Wenn Sie ein [Bereitstellungspaket zum](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) Konfigurieren eines Kiosks mit mehreren Apps verwenden, erfordert das Verfahren ein Startlayout. Die Anpassung des Startlayouts wird in Windows Holographic for Business nicht unterstützt. Daher müssen Sie ein Platzhalter-Startlayout verwenden.

> [!NOTE]  
> Da ein Kiosk mit einer einzelnen App die Kiosk-App startet, wenn sich ein Benutzer meldet, verwendet er kein Startmenü und muss kein Startlayout haben.

> [!NOTE]  
> Wenn Sie [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) zum Einrichten eines Multi-App-Kiosks verwenden, können Sie optional ein Startlayout verwenden. Weitere Informationen finden Sie unter [Placeholder Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).

Fügen Sie für das Startlayout der **XML-Datei** für die Kioskbereitstellung den folgenden Abschnitt StartLayout hinzu:

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

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>Platzhalter-Startlayoutdatei für MDM (Intune und andere)

Speichern Sie das folgende Beispiel als XML-Datei. Sie können diese Datei verwenden, wenn Sie den Kiosk mit mehreren Apps in Microsoft Intune (oder in einem anderen MDM-Dienst, der ein Kioskprofil bietet) konfigurieren.

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Einstellung und eine vollständige XML-Konfiguration zum Einrichten eines Kiosks in Ihrem MDM-Dienst verwenden müssen, verwenden Sie die Startlayoutanweisungen für ein [Bereitstellungspaket.](#start-layout-for-hololens)

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

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. Paket, Schritt 2 &ndash; Hinzufügen der XML-Datei für die Kioskkonfiguration zu einem Bereitstellungspaket

1. Öffnen [Sie Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22).
1. Wählen **Sie Erweiterte Bereitstellung**aus, geben Sie einen Namen für Ihr Projekt ein, und wählen Sie dann Weiter **aus.**
1. Wählen **Sie Windows 10 Holographic**aus, und wählen Sie dann **Weiter aus.**
1. Wählen Sie **Fertig stellen**aus. Der Arbeitsbereich für Ihr Paket wird geöffnet.
1. Wählen **Sie Laufzeiteinstellungen**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings aus.**
1. Wählen Sie im Mittelpunktbereich **Durchsuchen** aus, um die erstellte XML-Datei für die Kioskkonfiguration zu suchen und auszuwählen.

   ![Screenshot des Felds MultiAppAssignedAccessSettings im Windows-Konfigurations-Designer](./images/multiappassignedaccesssettings.png)

1. **Optional**. (Wenn Sie das Bereitstellungspaket nach der erst eingerichteten Einrichtung des Geräts anwenden möchten und bereits ein Administratorbenutzer auf dem Kioskgerät verfügbar ist, überspringen Sie diesen Schritt.) Wählen **Sie Laufzeiteinstellungen** &gt; **Konten** &gt; **Benutzer**aus, und erstellen Sie dann ein Benutzerkonto. Geben Sie einen Benutzernamen und ein Kennwort an, und wählen Sie **dann UserGroup**  >  **Administrators aus.**  
  
     Mithilfe dieses Kontos können Sie den Bereitstellungsstatus und die Protokolle anzeigen.  
1. **Optional**. (Wenn Sie bereits über ein Konto ohne Administratorrechte auf dem Kioskgerät verfügen, überspringen Sie diesen Schritt.) Wählen **Sie Laufzeiteinstellungen** &gt; **Konten** &gt; **Benutzer**aus, und erstellen Sie dann ein lokales Benutzerkonto. Stellen Sie sicher, dass der Benutzername mit dem Konto identisch ist, das Sie im Konfigurations-XML angeben. Wählen **Sie UserGroup**  >  **Standard Users aus.**
1. Wählen **Sie Datei**speichern  >  **aus.**
1. Wählen **Sie**  >  **Bereitstellungspaket exportieren**aus, und wählen Sie dann **Besitzer-IT-Administrator**  >  **aus.** Dadurch wird die Rangfolge dieses Bereitstellungspakets höher als die Bereitstellungspakete, die auf dieses Gerät aus anderen Quellen angewendet werden.
1. Wählen Sie **Weiter** aus.
1. Wählen Sie auf der **Seite Sicherheit des Bereitstellungspakets** eine Sicherheitsoption aus.
   > [!IMPORTANT]  
   > Wenn Sie **Paketsignatur aktivieren**auswählen, müssen Sie auch ein gültiges Zertifikat auswählen, das zum Signieren des Pakets verwendet werden soll. Wählen Sie dazu Durchsuchen **aus,** und wählen Sie das Zertifikat aus, das Sie zum Signieren des Pakets verwenden möchten.
   
   > [!CAUTION]  
   > Wählen Sie paketverschlüsselung **aktivieren nicht aus.** Auf HoloLens-Geräten führt diese Einstellung zu einem Fehler bei der Bereitstellung.
1. Wählen Sie **Weiter** aus.
1. Geben Sie den Ausgabespeicherort an, an dem das Bereitstellungspaket beim Erstellen verwendet werden soll. Standardmäßig verwendet der Windows-Konfigurations-Designer den Projektordner als Ausgabespeicherort. Wenn Sie den Ausgabespeicherort ändern möchten, wählen Sie **Durchsuchen aus.** Wenn Sie fertig sind, wählen Sie **Weiter aus.**
1. Wählen **Sie Build** aus, um mit dem Erstellen des Pakets zu beginnen. Die Erstellung eines Bereitstellungspakets dauert nicht lange. Auf der Buildseite werden die Projektinformationen angezeigt, und die Statusleiste gibt den Buildstatus an.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Bereitstellungspaket, Schritt 3 &ndash; Anwenden des Bereitstellungspakets auf HoloLens

Der Artikel "Konfigurieren von HoloLens mithilfe eines Bereitstellungspakets" enthält ausführliche Anweisungen zum Anwenden des Bereitstellungspakets unter den folgenden Umständen:

- Sie können während des Setups zunächst ein [Bereitstellungspaket auf HoloLens anwenden.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

- Sie können nach dem Setup auch ein [Bereitstellungspaket auf HoloLens anwenden.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Einrichten eines Single-App-Kiosks mithilfe des Windows-Geräteportals

Führen Sie die folgenden Schritte aus, um den Kioskmodus mithilfe des Windows-Geräteportals zu einrichten.

1. [Richten Sie das HoloLens-Gerät für die Verwendung des Windows-Geräteportals ein.](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal) Das Geräteportal ist ein Webserver auf der HoloLens, mit dem Sie über einen Webbrowser auf dem PC eine Verbindung herstellen können.

    > [!CAUTION]
    > Wenn Sie HoloLens für die Verwendung des Geräteportals einrichten, müssen Sie den Entwicklermodus auf dem Gerät aktivieren. Der Entwicklermodus auf einem Gerät mit Windows Holographic for Business ermöglicht das Sideloaden von Apps. Diese Einstellung führt jedoch zu dem Risiko, dass ein Benutzer Apps installieren kann, die nicht vom Microsoft Store zertifiziert wurden. Administratoren können die Aktivierung des Entwicklermodus mithilfe der **Einstellung ApplicationManagement/AllowDeveloper Unlock** im [Richtlinien-CSP blockieren.](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) [Weitere Informationen zum Entwicklermodus](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Stellen Sie auf einem Computer mithilfe [](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) von WLAN oder USB eine Verbindung mit holoLens [herzustellen.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)

1. Führen Sie eine der folgenden Aktionen aus:
   - Wenn Sie zum ersten Mal eine Verbindung mit dem Windows-Geräteportal herstellen, erstellen Sie [einen Benutzernamen und ein Kennwort.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Geben Sie den Benutzernamen und das Kennwort ein, die Sie zuvor eingerichtet haben.

    > [!TIP]
    > Wenn ein Zertifikatfehler im Browser angezeigt wird, führen Sie [diese Schrittezur Problembehandlung](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate) aus.

1. Wählen Sie im Windows-Geräteportal **kioskmodus aus.**

1. Wählen **Sie Kioskmodus aktivieren**aus, wählen Sie eine App aus, die beim Starten des Geräts ausgeführt werden soll, und wählen Sie dann Speichern **aus.**

    ![Kioskmodus](images/kiosk.png)
1. Starten Sie HoloLens neu. Wenn Die Seite Geräteportal noch geöffnet ist, können Sie **oben** auf der Seite Neu starten auswählen.

> [!NOTE]
> Der Kioskmodus kann über die REST-API des Geräteportals festgelegt werden, indem ein POST an /api/holographic/kioskmode/settings mit einem erforderlichen Abfragezeichenfolgenparameter ("kioskModeEnabled" mit dem Wert "true" oder "false") und einem optionalen Parameter ("startupApp" mit dem Wert eines Paketnamens) ausgeführt wird. Beachten Sie, dass das Geräteportal nur für Entwickler vorgesehen ist und nicht auf Geräten ohne Entwickler aktiviert werden sollte. Die REST-API kann in zukünftigen Updates/Versionen geändert werden.

## <a name="more-information"></a>Weitere Informationen

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Sehen Sie sich an, wie Sie einen Kiosk mithilfe eines Bereitstellungspakets konfigurieren.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Globaler zugewiesener Zugriff – Kioskmodus
- Reduzierte Identitätsverwaltung für Kiosk, indem die neue Kioskmethode aktiviert wird, die den Kioskmodus auf Systemebene verwendet.

Dieses neue Feature ermöglicht es einem IT-Administrator, ein HoloLens 2-Gerät für den Kioskmodus mit mehreren Apps zu konfigurieren, der auf Systemebene anwendbar ist, keine Affinität mit einer Identität im System hat und für alle Benutzer gilt, die sich beim Gerät registrieren. Weitere Informationen zu diesem neuen Feature finden Sie in der Dokumentation zu [holoLens global assigned access kiosk.](hololens-global-assigned-access-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Automatisches Starten einer Anwendung im Kioskmodus mit mehreren Apps 
- Fokussierte Erfahrung mit der automatischen App-Start, eine weitere Erhöhung der Benutzeroberflächen- und App-Auswahl, die für die Kioskmoduserfahrung ausgewählt wurde.

Gilt nur für den Kioskmodus mit mehreren Apps, und nur 1 App kann für den automatischen Start mithilfe des hervorgehobenen Attributs unten unter Konfiguration mit zugewiesenen Zugriff festgelegt werden. 

Die Anwendung wird automatisch gestartet, wenn sich der Benutzer anmeldet. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Verhaltensänderungen im Kioskmodus für die Behandlung von Fehlern
- Sichererer Kioskmodus durch Eliminieren verfügbarer Apps im Kioskmodus. 

Vor dem Auftreten von Fehlern beim Anwenden des Kioskmodus hat HoloLens alle Anwendungen im Startmenü angezeigt. In Windows Holographic, Version 20H2, werden im Falle von Fehlern keine Apps wie unten im Startmenü angezeigt: 

![Abbildung des Kioskmodus, der jetzt angezeigt wird, wenn er ausfällt.](images/hololens-kiosk-failure-behavior.png )

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Azure AD-Gruppenmitgliedschaft für Offlinekiosk zwischenspeichern
- Aktivierte Offlinekiosk für die Verwendung mit Azure AD-Gruppen für bis zu 60 Tage.

Diese Richtlinie steuert, wie viele Tage der Azure AD-Gruppenmitgliedschaftscache für Konfigurationen mit zugewiesenen Zugriffen für Azure AD-Gruppen für angemeldete Benutzer verwendet werden darf. Sobald dieser Richtlinienwert auf einen Wert größer als 0 festgelegt ist, wird der Cache andernfalls nicht verwendet.  

Name: AADGroupMembershipCacheValidityInDays URI-Wert: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min. – 0 Tage  
Max. - 60 Tage 

Schritte zum ordnungsgemäßen Verwenden dieser Richtlinie: 
1. Erstellen Sie ein Gerätekonfigurationsprofil für Kiosk für Azure AD-Gruppen, und weisen Sie es HoloLens-Geräten zu. 
1. Erstellen Sie eine benutzerdefinierte OMA-URI-basierte Gerätekonfiguration, die diesen Richtlinienwert auf die gewünschte Anzahl von Tagen (> 0) legt, und weisen Sie ihn HoloLens-Geräten zu. 
    1. Der URI-Wert sollte im Textfeld OMA-URI als ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays eingegeben werden.
    1. Der Wert kann zwischen min/max zulässig sein.
1. Registrieren Sie HoloLens-Geräte, und überprüfen Sie, ob beide Konfigurationen auf das Gerät angewendet werden. 
1. Lassen Sie Azure AD User 1 anmelden, wenn das Internet verfügbar ist, sobald sich der Benutzer anmeldet und die Azure AD-Gruppenmitgliedschaft erfolgreich bestätigt wurde, wird der Cache erstellt. 
1. Jetzt kann Azure AD-Benutzer 1 HoloLens offline schalten und für den Kioskmodus verwenden, solange der Richtlinienwert X Anzahl von Tagen zulässt. 
1. Die Schritte 4 und 5 können für jeden anderen Azure AD-Benutzer N wiederholt werden. Der entscheidende Punkt hier ist, dass sich jeder Azure AD-Benutzer über das Internet bei einem Gerät anmelden muss, damit wir feststellen können, dass er Mitglied der Azure AD-Gruppe ist, auf die die Kioskkonfiguration ausgerichtet ist. 
 
> [!NOTE]
> Bis Schritt 4 für einen Azure AD-Benutzer ausgeführt wird, tritt ein Fehlerverhalten auf, das in "getrennten" Umgebungen erwähnt wird. 


## <a name="xml-kiosk-code-samples-for-hololens"></a>XML-Kioskcodebeispiele für HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Mehrere App-Kioskmodus für eine Azure AD-Gruppe. 
Dieser Kiosk stellt einen Kiosk bereit, der für Benutzer in der Azure AD-Gruppe einen Kiosk aktiviert hat, der die 3 Apps enthält: Einstellungen, Remoteunterstützung und Feedbackhub. Um dieses Beispiel so zu ändern, dass es sofort verwendet wird, müssen Sie die unten hervorgehobene GUID so ändern, dass sie einer eigenen Azure AD-Gruppe zu entsprechen. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Mehrere App-Kioskmodus für Azure AD-Konto.
Dieser Kiosk stellt einen Kiosk für einen einzelnen Benutzer zur Verfügung, er hat einen Kiosk aktiviert, der die 3 Apps enthält: Einstellungen, Remoteunterstützung und FeedbackHub. Um dieses Beispiel so zu ändern, dass es sofort verwendet wird, müssen Sie das unten hervorgehobene Konto so ändern, dass es mit einem eigenen Azure AD-Konto übereinstimmen kann. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

