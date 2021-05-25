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
ms.openlocfilehash: 347501c3ac8f1b115b0d537332a17938a99d3257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397801"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Einrichten von HoloLens als Kiosk

Sie können ein HoloLens-Gerät so konfigurieren, dass es als Gerät mit festem Zweck (auch als Kiosk bezeichnet) verwendet wird, indem Sie das Gerät für die Ausführung im Kioskmodus konfigurieren. Der Kioskmodus schränkt die Anwendungen (oder Benutzer) ein, die auf dem Gerät verfügbar sind. Der Kioskmodus ist ein praktisches Feature, mit dem Sie ein HoloLens-Gerät für Geschäfts-Apps verwenden oder das HoloLens-Gerät in einer App-Demo verwenden können.

Dieser Artikel enthält Informationen zu Aspekten der Kioskkonfiguration, die spezifisch für HoloLens-Geräte sind. Allgemeine Informationen zu den verschiedenen Typen von Windows-basierten Kiosken und deren Konfiguration finden Sie unter Konfigurieren von Kiosken und digitalen Schildern [in Windows-Desktopeditionen.](https://docs.microsoft.com/windows/configuration/kiosk-methods)  

> [!IMPORTANT]  
> Der Kioskmodus bestimmt, welche Apps verfügbar sind, wenn sich ein Benutzer beim Gerät ankn.) Der Kioskmodus ist jedoch keine Sicherheitsmethode. Sie hält eine "zulässige" App nicht daran, eine andere App zu öffnen, die nicht zulässig ist. Um das Öffnen von Apps oder Prozessen zu blockieren, verwenden Sie Windows Defender [Application Control (WDAC)-CSP,](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) um geeignete Richtlinien zu erstellen.
>
> Erfahren Sie mehr über die Microsoft-Dienste, um Benutzern ein erweitertes Maß an Sicherheit zu bieten, das HoloLens 2 verwendet. Weitere Informationen finden Sie unter [Zustandstrennung und -isolation – Defender-Schutz.](security-state-separation-isolation.md#defender-protections) Oder erfahren Sie, wie Sie WDAC und [Windows PowerShell verwenden,](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)um Apps auf HoloLens 2-Geräten mit Microsoft Intune.

Sie können den Kioskmodus entweder in einer Einzel-App- oder in einer Konfiguration mit mehreren Apps verwenden, und Sie können einen von drei Prozessen verwenden, um die Kioskkonfiguration zu einrichten und bereitzustellen.

> [!IMPORTANT]  
> Durch das Löschen der Konfiguration mit mehreren Apps werden die Benutzersperrungsprofile entfernt, die von der zugewiesenen Zugriffsfunktion erstellt wurden. Allerdings werden nicht alle Richtlinienänderungen rückgängig machen. Um diese Richtlinien rückgängig zu machen, müssen Sie das Gerät auf die Werkseinstellungen zurücksetzen.

## <a name="plan-the-kiosk-deployment"></a>Planen der Kioskbereitstellung

Bei der Planung Ihres Kiosks müssen Sie die folgenden Fragen beantworten können. Hier sind einige Entscheidungen, die Beim Lesen dieser Seite zu berücksichtigen sind, und einige Überlegungen zu diesen Fragen.
1. **Wer verwendet Ihren Kiosk, und welche [Art von Konto(n)](hololens-identity.md) werden sie verwenden?** Dies ist eine Entscheidung, die Sie wahrscheinlich bereits getroffen haben und nicht für Ihren Kiosk angepasst werden sollten. Sie wirkt sich jedoch darauf aus, wie der Kiosk später zugewiesen wird.
1. **Benötigen Sie entweder unterschiedliche Kiosks pro Benutzer/Gruppe oder einen Kiosk, der für einige nicht aktiviert ist?** Wenn ja, sollten Sie Ihren Kiosk über XML erstellen. 
1. **Wie viele Apps sind in Ihrem Kiosk enthalten?** Wenn Sie über mehr als eine App verfügen, benötigen Sie einen Kiosk mit mehreren Apps. 
1. **Welche Apps sind in Ihrem Kiosk enthalten?** Verwenden Sie unsere nachstehende Liste mit AUMIDs, um zusätzlich zu Ihren eigenen In-Box Apps hinzuzufügen.
1. **Wie planen Sie die Bereitstellung Ihres Kiosks?** Wenn Sie ein Gerät bei MDM registrieren, wird die Verwendung von MDM zum Bereitstellen Ihres Kiosks empfohlen. Wenn Sie MDM nicht verwenden, ist die Bereitstellung mit dem Bereitstellungspaket verfügbar.  

### <a name="kiosk-mode-requirements"></a>Kioskmodusanforderungen

Sie können jedes HoloLens 2 Gerät für die Verwendung des Kioskmodus konfigurieren.

> [!IMPORTANT]
> Der Kioskmodus ist nur verfügbar, wenn das Gerät über Windows Holographic for Business verfügt. Alle HoloLens 2 Geräte werden mit Windows Holographic for Business versendet, und es gibt keine anderen Editionen. Alle HoloLens 2 Geräte können den Kioskmodus sofort ausführen.
>
> HoloLens-Geräte (1. Generation) müssen sowohl im Hinblick auf den Betriebssystembuild als auch die Betriebssystemedition aktualisiert werden. Hier finden Sie weitere Informationen zum Aktualisieren einer HoloLens (1. Generation) auf [Windows Holographic for Business](hololens1-upgrade-enterprise.md) Edition. Um ein HoloLens-Gerät (1. Generation) für die Verwendung des Kioskmodus zu aktualisieren, müssen Sie zunächst sicherstellen, dass das Gerät Windows 10 Version 1803 oder höher ausgeführt wird. Wenn Sie das Windows Device Recovery Tool verwendet haben, um Ihr HoloLens-Gerät (1. Generation) auf den Standard-Build wiederhergestellt zu haben, oder wenn Sie die neuesten Updates installiert haben, kann Ihr Gerät konfiguriert werden.

> [!IMPORTANT]  
> Um Geräte zu schützen, die im Kioskmodus ausgeführt werden, sollten Sie Geräteverwaltungsrichtlinien hinzufügen, die Features wie USB-Konnektivität deaktivieren. Überprüfen Sie außerdem die Einstellungen ihres Updaterings, um sicherzustellen, dass keine automatischen Updates während der Geschäftszeiten erfolgen.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Entscheiden zwischen einem Kiosk mit nur einer App oder einem Kiosk mit mehreren Apps

Ein Kiosk mit einer einzelnen App startet die angegebene App, wenn sich der Benutzer beim Gerät anknappt. Die Startmenü ist deaktiviert, ebenso wie Cortana. Ein HoloLens 2 reagiert nicht auf die [Startgeste.](hololens2-basic-usage.md#start-gesture) Ein HoloLens-Gerät (1. Generation) reagiert nicht auf die [Blume.](hololens1-basic-usage.md) Da nur eine App ausgeführt werden kann, kann der Benutzer keine anderen Apps platzieren.

Ein Kiosk mit mehreren Apps zeigt die Startmenü wenn sich der Benutzer beim Gerät anknappt. Die Kioskkonfiguration bestimmt, welche Apps auf dem Gerät verfügbar Startmenü. Sie können einen Kiosk mit mehreren Apps verwenden, um benutzern eine leicht verständliche Erfahrung zu bieten, indem Sie ihnen nur die Dinge präsentieren, die sie verwenden müssen, und die Dinge entfernen, die sie nicht verwenden müssen.

In der folgenden Tabelle sind die Featurefunktionen in den verschiedenen Kioskmodi aufgeführt.

| &nbsp; |Startmenü |Menü "Schnellaktionen" |Kamera und Video |Miracast |Cortana |Integrierte Sprachbefehle |
| --- | --- | --- | --- | --- | --- | --- | 
|Kiosk mit nur einer App |Disabled |Disabled |Disabled |Disabled   |Disabled |Aktiviert<sup>1</sup> |
|Kiosk mit mehreren Apps |Aktiviert |Aktiviert<sup>2</sup> |Verfügbar<sup>2</sup> |Verfügbar<sup>2</sup> |Verfügbar<sup>2, 3</sup>  |Aktiviert<sup>1</sup> |

> <sup>1</sup> Sprachbefehle, die sich auf deaktivierte Features beziehen, funktionieren nicht.  
> <sup>2</sup> Weitere Informationen zum Konfigurieren dieser Features finden Sie unter [Auswählen von Kiosk-Apps.](#plan-kiosk-apps)  
> <sup>3</sup> Auch wenn Cortana deaktiviert ist, sind die integrierten Sprachbefehle aktiviert.

In der folgenden Tabelle sind die Benutzerunterstützungsfeatures der verschiedenen Kioskmodi aufgeführt.

| &nbsp; |Unterstützte Benutzertypen | Automatische Anmeldung | Mehrere Zugriffsebenen |
| --- | --- | --- | --- |
|Kiosk mit einzelner App |Verwaltetes Dienstkonto (Managed Service Account, MSA) in Azure Active Directory (Azure AD) oder lokalem Konto |Ja |Nein |
|Kiosk mit mehreren Apps |Azure AD-Konto |Nein |Ja |

Beispiele für die Verwendung dieser Funktionen finden Sie in der folgenden Tabelle.

|Verwenden Sie einen Kiosk mit einer einzelnen App für: |Verwenden Sie einen Kiosk mit mehreren Apps für: |
| --- | --- |
|Ein Gerät, auf dem nur ein Dynamics 365-Leitfaden für neue Mitarbeiter ausgeführt wird. |Ein Gerät, das sowohl Leitfäden als auch Remoteunterstützung für eine Reihe von Mitarbeitern ausführt. |
|Ein Gerät, auf dem nur eine benutzerdefinierte App ausgeführt wird. |Ein Gerät, das für die meisten Benutzer als Kiosk fungiert (nur eine benutzerdefinierte App ausführt), aber als Standardgerät für eine bestimmte Benutzergruppe fungiert. |

### <a name="plan-kiosk-apps"></a>Planen von Kiosk-Apps

Allgemeine Informationen zum Auswählen von Kiosk-Apps finden Sie unter Richtlinien für die Auswahl einer App für den zugewiesenen [Zugriff (Kioskmodus).](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)

Wenn Sie die Windows-Geräteportal zum Konfigurieren eines Kiosks mit einer einzelnen App verwenden, wählen Sie die App während des Setupvorgangs aus.  

Wenn Sie ein Mobile Geräteverwaltung-System (MDM) oder ein Bereitstellungspaket zum Konfigurieren des Kioskmodus verwenden, verwenden Sie [den AssignedAccess Configuration Service Provider (CSP),](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) um Anwendungen anzugeben. Der CSP verwendet [Anwendungsbenutzermodell-IDs (Application User Model IDs, AUMIDs), um](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) Anwendungen zu identifizieren. In der folgenden Tabelle sind die AUMIDs einiger In-Box-Anwendungen aufgeführt, die Sie in einem Kiosk mit mehreren Apps verwenden können.

> [!IMPORTANT]
> Der Kioskmodus bestimmt, welche Apps verfügbar sind, wenn sich ein Benutzer beim Gerät ankn.) Der Kioskmodus ist jedoch keine Sicherheitsmethode. Sie hält eine "zulässige" App nicht daran, eine andere App zu öffnen, die nicht zulässig ist. Da wir dieses Verhalten nicht einschränken, können Apps weiterhin über Edge, den Datei-Explorer und die Microsoft Store werden. Wenn bestimmte Apps nicht über einen Kiosk gestartet werden sollen, verwenden Sie den [Windows Defender Application Control (WDAC)-CSP,](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) um geeignete Richtlinien zu erstellen. 
> 
> Darüber hinaus kann das Mixed Reality Home nicht als Kiosk-App festgelegt werden.

<a id="aumids"></a>

|App-Name |AUMID |
| --- | --- |
|3D-Viewer |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Kalender |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Kamera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|Geräteauswahl auf HoloLens (1. Generation) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Geräteauswahl auf HoloLens 2 |Microsoft.Windows.DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows.DevicesFlowHost |
|Dynamics 365-Leitfäden |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteRob \_ 8wekyb3d8bbwe \! Microsoft.RemoteRobin |
|&nbsp;Feedback-Hub |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe-App \! |
|Datei-Explorer |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|E-Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Alte Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Neue Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast<sup>4</sup> |&nbsp; |
|Filme & TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Fotos |Microsoft.Windows.Photos \_ 8wekyb3d8bbwe-App \! |
|Alte Einstellungen |HolographicSystemSettings_cw5n1h2txyewy! App |
|Neue Einstellungen |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|Tipps |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Zum Aktivieren der Foto- oder Videoaufnahme müssen Sie die Kamera-App als Kiosk-App aktivieren.  
> <sup>2</sup> Wenn Sie die Kamera-App aktivieren, beachten Sie die folgenden Bedingungen:
> - Das Menü Schnellaktionen enthält die Schaltflächen Foto und Video.  
> - Sie sollten auch eine App (z. B. Fotos, E-Mail oder OneDrive) aktivieren, die mit Bildern interagieren oder diese abrufen kann.  
>  
> <sup>3</sup> Auch wenn Sie Cortana nicht als Kiosk-App aktivieren, sind integrierte Sprachbefehle aktiviert. Befehle im Zusammenhang mit deaktivierten Features haben jedoch keine Auswirkungen.  
> <sup>4</sup> Sie können Miracast nicht direkt aktivieren. Aktivieren Sie die Kamera-App und die Geräteauswahl-App, um Miracast als Kiosk-App zu aktivieren.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Planen von Kioskprofilen für Benutzer oder Gruppen

Wenn Sie entweder die XML-Datei erstellen oder die Benutzeroberfläche von Intune zum Einrichten eines Kiosks verwenden, müssen Sie berücksichtigen, wer der Benutzer des Kiosks sein wird. Eine Kioskkonfiguration kann entweder auf ein einzelnes Konto oder auf Azure AD beschränkt werden. 

Kioske sind in der Regel entweder für einen Benutzer oder eine Benutzergruppe aktiviert. Wenn Sie jedoch einen eigenen XML-Kiosk schreiben möchten, sollten Sie den global zugewiesenen Zugriff in Betracht ziehen, bei dem der Kiosk unabhängig von der Identität auf Geräteebene angewendet wird. Wenn dies für Sie vonn sprechend [ist, lesen Sie mehr über Kioske mit global zugewiesenem Zugriff.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>Wenn Sie eine XML-Datei erstellen:
-   Sie erstellen mehrere Kioskprofile und weisen diese verschiedenen Benutzern/Gruppen zu. Beispielsweise ein Kiosk für Ihre Azure AD-Gruppe mit vielen Apps und ein Besucher, der über einen Kiosk mit mehreren Apps mit einer einzelnen App verfügt.
-   Ihre Kioskkonfiguration wird als **Profil-ID bezeichnet** und hat eine GUID.
-   Sie weisen dieses Profil im Abschnitt configs zu, indem Sie den Benutzertyp angeben und dieselbe GUID für die **DefaultProfile-ID verwenden.**
- Eine XML-Datei kann erstellt, aber trotzdem über MDM auf ein Gerät angewendet werden, indem ein benutzerdefiniertes OMA-URI-Gerätekonfigurationsprofil erstellt und mithilfe des URI-Werts auf die HoloLens-Gerätegruppe angewendet wird: ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Wenn Sie einen Kiosk in Intune erstellen.
-   Jedes Gerät erhält möglicherweise nur ein einzelnes Kioskprofil, andernfalls führt dies zu einem Konflikt und empfängt überhaupt keine Kioskkonfigurationen. 
    -   Andere Arten von Profilen und Richtlinien, z. B. Geräteeinschränkungen, die nicht mit dem Kioskkonfigurationsprofil in Zusammenhang stehen, stehen nicht in Konflikt mit dem Kioskkonfigurationsprofil.
-   Der Kiosk wird für alle Benutzer aktiviert, die Teil des Benutzeranmeldungstyps sind. Dies wird mit einem Benutzer oder Azure AD Gruppe festgelegt. 
-   Nachdem die Kioskkonfiguration festgelegt und der **Benutzeranmeldungstyp** (Benutzer, die sich am Kiosk anmelden können) und die Apps ausgewählt sind, muss die Gerätekonfiguration weiterhin einer Gruppe zugewiesen werden. Die zugewiesenen Gruppen bestimmen, welche Geräte die Kioskgerätekonfiguration erhalten, interagieren jedoch nicht mit , wenn der Kiosk aktiviert ist oder nicht. 
    - Eine vollständige Erläuterung der Auswirkungen der Zuweisung von Konfigurationsprofilen in Intune finden Sie unter [Zuweisen von Benutzer- und Geräteprofilen in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).

### <a name="select-a-deployment-method"></a>Auswählen einer Bereitstellungsmethode

Sie können eine der folgenden Methoden zum Bereitstellen von Kioskkonfigurationen auswählen:

- [Microsoft Intune oder anderer Mdm-Dienst (Mobile Device Management, Verwaltung mobiler Geräte)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Bereitstellungspaket](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows-Geräteportal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Da diese Methode erfordert, dass der Entwicklermodus auf dem Gerät aktiviert ist, wird empfohlen, sie nur für Demonstrationen zu verwenden.

In der folgenden Tabelle sind die Funktionen und Vorteile der einzelnen Bereitstellungsmethoden aufgeführt.

| &nbsp; |Bereitstellen mithilfe von Windows-Geräteportal |Bereitstellen mithilfe eines Bereitstellungspakets |Bereitstellen mithilfe von MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Bereitstellen von Kiosken mit nur einer App   | Ja           | Ja                  | Ja  |
|Bereitstellen von Kiosken mit mehreren Apps    | Nein            | Ja                  | Ja  |
|Nur auf lokalen Geräten bereitstellen | Ja           | Ja                  | Nein   |
|Bereitstellen im Entwicklermodus |Erforderlich       | Nicht erforderlich            | Nicht erforderlich   |
|Bereitstellen mithilfe von Azure Active Directory (Azure AD)  | Nicht erforderlich            | Nicht erforderlich                   | Erforderlich  |
|Automatische Bereitstellung      | Nein            | Nein                   | Ja  |
|Bereitstellungsgeschwindigkeit            | Schnell       | Schnell                 | Langsam |
|Bedarfsorientiertes Bereitstellen | Nicht empfohlen    | Empfohlen        | Empfohlen |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Verwenden Microsoft Intune oder einer anderen MDM zum Einrichten eines Kiosks mit nur einer App oder mehreren Apps

Führen Sie die folgenden Schritte aus, um den Kioskmodus mit Microsoft Intune oder einem anderen MDM-System einrichten.

1. [Bereiten Sie die Registrierung der Geräte vor.](#mdmenroll)
1. [Erstellen Sie ein Kioskkonfigurationsprofil.](#mdmprofile)
1. Konfigurieren Sie den Kiosk.
   - [Konfigurieren Sie die Einstellungen für einen Kiosk mit einer einzelnen App.](#mdmconfigsingle)
   - [Konfigurieren Sie die Einstellungen für einen Kiosk mit mehreren Apps.](#mdmconfigmulti)
1. [Weisen Sie das Kioskkonfigurationsprofil einer Gruppe zu.](#mdmassign)
1. Stellen Sie die Geräte zur Verfügung.
   - [Bereitstellen eines Kiosks mit nur einer App.](#mdmsingledeploy)
   - [Bereitstellen eines Kiosks mit mehreren Apps.](#mdmmultideploy)

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, Schritt 1: &ndash; Vorbereiten der Registrierung der Geräte

Sie können Ihr MDM-System so konfigurieren, dass HoloLens-Geräte automatisch registriert werden, wenn sich der Benutzer zum ersten Mal anmelden, oder Benutzer geräte manuell registrieren lassen. Die Geräte müssen außerdem ihrer Domäne Azure AD und den entsprechenden Gruppen zugewiesen werden.

Weitere Informationen zum Registrieren der Geräte finden Sie unter [Registrieren von HoloLens in MDM](hololens-enroll-mdm.md) und [Intune-Registrierungsmethoden für Windows-Geräte.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, Schritt 2: &ndash; Erstellen eines Kioskkonfigurationsprofils

1. Öffnen Sie das [Azure-Portal,](https://portal.azure.com/) und melden Sie sich bei Ihrem Intune-Administrator an.
1. Wählen **Microsoft Intune**  >  **Gerätekonfiguration – Profile Profil** erstellen  >  **aus.**
1. Geben Sie einen Profilnamen ein.
1. Wählen Sie **Plattform**  >  **Windows 10 und höher und** dann **Profiltyp**  > **Geräteeinschränkungen** aus.
1. Wählen Sie Kiosk **konfigurieren**  >  und dann eine der folgenden Optionen aus:
   - Um einen Kiosk mit einer einzelnen App zu erstellen, wählen Sie **Kioskmodus** Kiosk kiosk  >  **(Einzel-App-Kiosk)** aus.
   - Um einen Kiosk mit mehreren Apps zu erstellen, wählen Sie **Kioskmodus**  >  **Multi-App-Kiosk** aus.
1. Wählen Sie **hinzufügen** aus, um mit der Konfiguration des Kiosks zu beginnen.

Die nächsten Schritte unterscheiden sich je nach gewünschtem Kiosktyp. Wählen Sie eine der folgenden Optionen aus, um weitere Informationen zu erfahren:  

- [Kiosk mit einzelner App](#mdmconfigsingle)
- [Kiosk mit mehreren Apps](#mdmconfigmulti)

Weitere Informationen zum Erstellen eines Kioskkonfigurationsprofils finden Sie unter [Windows 10 und Windows Holographic for Business Geräteeinstellungen für die Ausführung als dedizierter Kiosk mit Intune.](https://docs.microsoft.com/intune/configuration/kiosk-settings)

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, Schritt 3 (Einzel-App) &ndash;  Konfigurieren der Einstellungen für einen Kiosk mit einer einzelnen App

In diesem Abschnitt werden die Einstellungen zusammengefasst, die für einen Kiosk mit einer einzelnen App erforderlich sind. Weitere Informationen finden Sie in den folgenden Artikeln:

- Informationen zum Konfigurieren eines Kioskkonfigurationsprofils in Intune finden Sie unter Konfigurieren des [Kioskmodus mit Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Weitere Informationen zu den verfügbaren Einstellungen für Kioske mit nur einer App in Intune finden Sie unter Kioske für [Einzel-Vollbild-Apps.](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Informationen zu anderen MDM-Diensten finden Sie in der Dokumentation Ihres Anbieters. Wenn Sie eine benutzerdefinierte XML-Konfiguration zum Einrichten eines Kiosks in Ihrem MDM-Dienst verwenden müssen, [erstellen Sie eine XML-Datei, die die Kioskkonfiguration definiert.](#ppkioskconfig)

1. Wählen Sie **Benutzeranmeldung geben**  >  **Sie Lokales Benutzerkonto** ein, und geben Sie dann den Benutzernamen des lokalen (Geräte-)Kontos oder des Microsoft-Kontos (MSA) ein, das sich beim Kiosk anmelden kann.
   > [!NOTE]  
   > Der Typ **Autologon** wird unter Windows Holographic for Business nicht unterstützt.
1. Wählen Sie **Anwendungstyp**  >  **Store-App** und dann eine App aus der Liste aus.

Der nächste Schritt besteht darin, das Profil einer Gruppe [zuzuweisen.](#mdmassign)

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, Schritt 3 (Multi-App) &ndash; Konfigurieren der Einstellungen für einen Kiosk mit mehreren Apps

In diesem Abschnitt werden die Einstellungen zusammengefasst, die für einen Kiosk mit mehreren Apps erforderlich sind. Ausführlichere Informationen finden Sie in den folgenden Artikeln:

- Informationen zum Konfigurieren eines Kioskkonfigurationsprofils in Intune finden Sie unter [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Weitere Informationen zu den verfügbaren Einstellungen für Kioske mit mehreren Apps in Intune finden Sie unter [Kiosks mit mehreren Apps.](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Anweisungen für andere MDM-Dienste finden Sie in der Dokumentation Ihres Anbieters. Wenn Sie eine benutzerdefinierte XML-Konfiguration zum Einrichten eines Kiosks in Ihrem MDM-Dienst verwenden müssen, erstellen Sie eine XML-Datei, die [die Kioskkonfiguration definiert.](#ppkioskconfig) Wenn Sie eine XML-Datei verwenden, stellen Sie sicher, dass Sie das [Startlayout enthalten.](#start-layout-for-hololens)  
- Optional können Sie ein benutzerdefiniertes Startlayout mit Intune oder anderen MDM-Diensten verwenden. Weitere Informationen finden Sie unter [Starten der Layoutdatei für MDM (Intune und andere).](#start-layout-file-for-mdm-intune-and-others)

1. Wählen **Sie Ziel Windows 10 im S Modus Geräte Nein**  >  **aus.**  
>[!NOTE]  
> Der S Modus wird unter Windows Holographic for Business nicht unterstützt.

1. Wählen **Sie Benutzeranmeldungstyp** Azure AD Oder Benutzeranmeldungstyp  >     >  **HoloLens-Besucher** aus, und fügen Sie dann mindestens eine Benutzergruppe oder ein Konto hinzu.  

   Nur Benutzer, die den Gruppen oder Konten angehören, die Sie unter **Benutzeranmeldungstyp** angeben, können die Kiosk-Benutzeroberfläche verwenden.

1. Wählen Sie eine oder mehrere Apps aus, indem Sie die folgenden Optionen verwenden:
   - Um eine hochgeladene Line-of-Business-App hinzuzufügen, wählen Sie **Store-App hinzufügen** und dann die app aus, die Sie möchten.
   - Um eine App durch Angabe ihrer AUMID hinzuzufügen, wählen Sie **Nach AUMID hinzufügen** aus, und geben Sie dann die AUMID der App ein. [Sehen Sie sich die Liste der verfügbaren AUMIDs an.](#aumids)

Der nächste Schritt besteht im [Zuweisen des](#mdmassign) Profils zu einer Gruppe.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, Schritt 4 &ndash; Zuweisen des Kioskkonfigurationsprofils zu einer Gruppe

Auf der **Seite Zuweisungen** des Kioskkonfigurationsprofils können Sie festlegen, wo die Kioskkonfiguration bereitgestellt werden soll. Im einfachsten Fall weisen Sie das Kioskkonfigurationsprofil einer Gruppe zu, die das HoloLens-Gerät enthält, wenn das Gerät bei MDM registriert wird.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, Schritt 5 (Einzel-App) &ndash; Bereitstellen eines Kiosks mit einer einzelnen App

Wenn Sie ein MDM-System verwenden, können Sie das Gerät während der OOBE bei MDM registrieren. Nachdem OOBE abgeschlossen ist, ist die Anmeldung beim Gerät einfach.

Führen Sie während der OOBE die folgenden Schritte aus:

1. Melden Sie sich mit dem Konto an, das Sie im Kioskkonfigurationsprofil angegeben haben.
1. Registrieren Sie das Gerät. Stellen Sie sicher, dass das Gerät der Gruppe hinzugefügt wird, der das Kioskkonfigurationsprofil zugewiesen ist.
1. Warten Sie, bis OOBE abgeschlossen ist, bis die Store-App heruntergeladen und installiert wird und bis Richtlinien angewendet werden. Starten Sie dann das Gerät neu.

Wenn Sie sich das nächste Mal beim Gerät anmelden, sollte die Kiosk-App automatisch gestartet werden.

Wenn Ihre Kioskkonfiguration zu diesem Zeitpunkt nicht angezeigt wird, [überprüfen Sie den Zuweisungsstatus](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, Schritt 5 (mehrere Apps) &ndash; Bereitstellen eines Kiosks mit mehreren Apps

Wenn Sie ein MDM-System verwenden, können Sie das Gerät mit Ihrem Azure AD Mandanten verbinden und das Gerät während der OoBE bei MDM registrieren. Stellen Sie ggf. die Registrierungsinformationen für die Benutzer bereit, damit sie während des OOBE-Prozesses verfügbar sind.

> [!NOTE]  
> Wenn Sie das Kioskkonfigurationsprofil einer Gruppe zugewiesen haben, die Benutzer enthält, stellen Sie sicher, dass eines dieser Benutzerkonten das erste Konto ist, das sich beim Gerät anmeldet.

Führen Sie während der OOBE die folgenden Schritte aus:

1. Melden Sie sich mit dem Konto an, das zur Gruppe **Benutzeranmeldung** gehört.
1. Registrieren Sie das Gerät.
1. Warten Sie, bis alle Apps, die Teil des Kioskkonfigurationsprofils sind, heruntergeladen und installiert werden. Warten Sie außerdem, bis Richtlinien angewendet werden.  
1. Nach Abschluss von OOBE können Sie zusätzliche Apps aus dem Microsoft Store installieren oder querladen. [Erforderliche Apps](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) für die Gruppe, zu der das Gerät gehört, werden automatisch installiert.
1. Starten Sie das Gerät nach Abschluss der Installation neu.

Wenn Sie sich das nächste Mal mit einem Konto beim Gerät anmelden, das zum Anmeldetyp Benutzer **gehört,** sollte die Kiosk-App automatisch gestartet werden.

Wenn Ihre Kioskkonfiguration an diesem Punkt nicht angezeigt wird, überprüfen [Sie den Zuweisungsstatus](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Verwenden eines Bereitstellungspakets zum Einrichten eines Kiosks mit nur einer App oder mehreren Apps

Führen Sie zum Einrichten des Kioskmodus mithilfe eines Bereitstellungspakets die folgenden Schritte aus.

1. [Erstellen Sie eine XML-Datei, die die Kioskkonfiguration definiert.](#ppkioskconfig), einschließlich [eines Startlayouts.](#start-layout-for-hololens)
2. [Fügen Sie die XML-Datei einem Bereitstellungspaket hinzu.](#ppconfigadd)
3. [Wenden Sie das Bereitstellungspaket auf HoloLens an.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Bereitstellungspaket, Schritt 1: Erstellen &ndash; einer XML-Datei für die Kioskkonfiguration

Befolgen [Sie die allgemeinen Anweisungen, um eine XML-Datei für die Kioskkonfiguration für Windows-Desktop](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)zu erstellen, mit Ausnahme der folgenden:

- Schließen Sie keine klassischen Windows-Anwendungen (Win32) ein. HoloLens unterstützt diese Anwendungen nicht.
- Verwenden Sie [den Platzhalter Startlayout-XML](#start-layout-for-hololens) für HoloLens.
- Optional: Hinzufügen von Gastzugriff zur Kioskkonfiguration

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>Optional: Hinzufügen von Gastzugriff zur Kioskkonfiguration

Im Abschnitt [ **Configs der** XML-Datei](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)können Sie eine spezielle Gruppe mit dem Namen **Besucher** konfigurieren, damit Gäste den Kiosk verwenden können. Wenn der Kiosk so konfiguriert ist, dasser die spezielle Gruppe **"Besucher"** unterstützt, wird der Anmeldeseite die Option "Gast" hinzugefügt. Für **das Gastkonto** ist kein Kennwort erforderlich, und alle daten, die dem Konto zugeordnet sind, werden gelöscht, wenn sich das Konto abschreibt.

Um das **Gastkonto zu** aktivieren, fügen Sie ihrer Kioskkonfigurations-XML den folgenden Codeausschnitt hinzu:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a>Automatische Anmeldung für Besucher aktivieren

Auf builds [Windows Holographic, Version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) und höher:
- AAD- und Nicht-ADD-Konfigurationen unterstützen die automatische Anmeldung von Besucherkonten für Kioskmodi.

##### <a name="non-aad-configuration"></a>Nicht-AAD-Konfiguration

1. Erstellen Sie ein Bereitstellungspaket, das:
    1. Konfiguriert Laufzeiteinstellungen/AssignedAccess, um Besucherkonten zuzulassen.
    1. Registriert das Gerät optional bei MDM (Laufzeiteinstellungen/Arbeitsplatz/Registrierungen), damit es später verwaltet werden kann.
    1. Erstellen Sie kein lokales Konto.
2. [Wenden Sie das Bereitstellungspaket an.](https://docs.microsoft.com/hololens/hololens-provisioning)

##### <a name="aad-configuration"></a>AAD-Konfiguration

In AAD eingebundene Geräte, die für den Kioskmodus konfiguriert sind, können sich mit einer einzigen Schaltfläche vom Anmeldebildschirm aus bei einem Besucherkonto anmelden. Nach der Anmeldung beim Besucherkonto fordert das Gerät erst dann zur erneuten Anmeldung auf, wenn der Besucher explizit über das Startmenü abgemeldet oder das Gerät neu gestartet wurde.

Die automatische Anmeldung des Besuchers kann über [eine benutzerdefinierte OMA-URI-Richtlinie](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)verwaltet werden:

- URI-Wert: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon


| Richtlinie |BESCHREIBUNG |Configurations 
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Ermöglicht einem Besucher die automatische Anmeldung bei einem Kiosk. | 1 (Ja), 0 (Nein, Standard) |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>Platzhalterstartlayout für HoloLens

Wenn Sie ein [Bereitstellungspaket](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) verwenden, um einen Kiosk mit mehreren Apps zu konfigurieren, ist für das Verfahren ein Startlayout erforderlich. Die Anpassung des Startlayouts wird in Windows Holographic for Business nicht unterstützt. Daher müssen Sie einen Platzhalter Startlayout verwenden.

> [!NOTE]  
> Da ein Kiosk mit nur einer App die Kiosk-App startet, wenn sich ein Benutzer anknappt, verwendet er keine Startmenü und muss kein Startlayout haben.

> [!NOTE]  
> Wenn Sie [MDM zum](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) Einrichten eines Kiosks mit mehreren Apps verwenden, können Sie optional ein Startlayout verwenden. Weitere Informationen finden Sie unter [Platzhalter-Startlayoutdatei für MDM (Intune und andere).](#start-layout-file-for-mdm-intune-and-others)

Fügen Sie für das Startlayout der XML-Datei für die Kioskbereitstellung den folgenden **StartLayout-Abschnitt** hinzu:

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

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>Platzhalter- Startlayoutdatei für MDM (Intune und andere)

Speichern Sie das folgende Beispiel als XML-Datei. Sie können diese Datei verwenden, wenn Sie den Kiosk mit mehreren Apps in Microsoft Intune (oder in einem anderen MDM-Dienst, der ein Kioskprofil bietet) konfigurieren.

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Einstellung und eine vollständige XML-Konfiguration zum Einrichten eines Kiosks in Ihrem MDM-Dienst verwenden müssen, verwenden Sie die Anweisungen zum Startlayout für [ein Bereitstellungspaket.](#start-layout-for-hololens)

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

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. Package, Schritt 2: &ndash; Hinzufügen der XML-Datei für die Kioskkonfiguration zu einem Bereitstellungspaket

1. Öffnen Sie [den Windows-Konfigurations-Designer.](https://www.microsoft.com/store/apps/9nblggh4tx22)
1. Wählen **Sie Erweiterte Bereitstellung aus,** geben Sie einen Namen für Ihr Projekt ein, und wählen Sie dann Weiter **aus.**
1. Wählen **Windows 10 Holographic** aus, und klicken Sie dann auf **Weiter.**
1. Wählen Sie **Fertig stellen** aus. Der Arbeitsbereich für das Paket wird geöffnet.
1. Wählen **Sie Runtimeeinstellungen**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings aus.**
1. Wählen Sie im  mittelpunkten Bereich Durchsuchen aus, um die erstellte XML-Datei für die Kioskkonfiguration zu suchen und auszuwählen.

   ![Screenshot des Felds "MultiAppAssignedAccessSettings" im Windows-Konfigurations-Designer](./images/multiappassignedaccesssettings.png)

1. **Optional:** (Wenn Sie das Bereitstellungspaket nach der anfänglichen Einrichtung des Geräts anwenden möchten und bereits ein Administratorbenutzer auf dem Kioskgerät verfügbar ist, überspringen Sie diesen Schritt.) Wählen **Sie Laufzeiteinstellungen** &gt; **Konten** &gt; **Benutzer** aus, und erstellen Sie dann ein Benutzerkonto. Geben Sie einen Benutzernamen und ein Kennwort an, und wählen Sie **dann UserGroup-Administratoren**  >  **aus.**  
  
     Mit diesem Konto können Sie den Bereitstellungsstatus und die Protokolle anzeigen.  
1. **Optional:** (Wenn Sie bereits über ein Konto ohne Administratorrechte auf dem Kioskgerät verfügen, überspringen Sie diesen Schritt.) Wählen Sie **Laufzeiteinstellungen** &gt;  &gt; **KontenBenutzer** aus, und erstellen Sie dann ein lokales Benutzerkonto. Stellen Sie sicher, dass der Benutzername mit dem für das Konto identisch ist, das Sie in der XML-Konfigurationsdatei angeben. Wählen Sie **UserGroup**  >  **Standard Users aus.**
1. Wählen Sie **Datei** > **Speichern** aus.
1. Wählen Sie  >  **Bereitstellungspaket** exportieren und dann   >  **BESITZER IT-Administrator** aus. Dadurch wird die Rangfolge dieses Bereitstellungspakets höher als die Rangfolge der Bereitstellungspakete festgelegt, die auf dieses Gerät aus anderen Quellen angewendet werden.
1. Wählen Sie **Weiter** aus.
1. Wählen Sie auf der Seite Sicherheit des **Bereitstellungspakets** eine Sicherheitsoption aus.
   > [!IMPORTANT]  
   > Wenn Sie **Paketsignatur aktivieren** auswählen, müssen Sie auch ein gültiges Zertifikat auswählen, das zum Signieren des Pakets verwendet werden soll. Wählen Sie hierzu **Durchsuchen** aus, und wählen Sie das Zertifikat aus, das Sie zum Signieren des Pakets verwenden möchten.
   
   > [!CAUTION]  
   > Wählen Sie nicht **Paketverschlüsselung aktivieren** aus. Auf HoloLens-Geräten führt diese Einstellung dazu, dass die Bereitstellung fehlschlägt.
1. Wählen Sie **Weiter** aus.
1. Geben Sie den Ausgabespeicherort an, an dem das Bereitstellungspaket bei der Erstellung enthalten sein soll. Standardmäßig verwendet der Windows-Konfigurations-Designer den Projektordner als Ausgabespeicherort. Wenn Sie den Ausgabespeicherort ändern möchten, wählen **Sie Durchsuchen aus.** Wenn Sie fertig sind, klicken Sie auf **Weiter**.
1. Wählen Sie **Erstellen** aus, um mit dem Erstellen des Pakets zu beginnen. Die Erstellung eines Bereitstellungspakets dauert nicht lange. Auf der Buildseite werden die Projektinformationen angezeigt, und die Statusanzeige gibt den Buildstatus an.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Bereitstellungspaket, Schritt &ndash; 3: Anwenden des Bereitstellungspakets auf HoloLens

Der Artikel "Konfigurieren von HoloLens mithilfe eines Bereitstellungspakets" enthält ausführliche Anweisungen zum Anwenden des Bereitstellungspakets unter den folgenden Umständen:

- Sie können während des Setups zunächst [ein Bereitstellungspaket auf HoloLens anwenden.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

- Sie können nach dem Setup auch [ein Bereitstellungspaket auf HoloLens anwenden.](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Verwenden des Windows-Geräteportal zum Einrichten eines Kiosks mit einer einzelnen App

Führen Sie die folgenden Schritte aus, um den Kioskmodus mithilfe der Windows-Geräteportal einzurichten.

1. [Richten Sie das HoloLens-Gerät für die Verwendung des Windows-Geräteportal.](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal) Das Geräteportal ist ein Webserver auf der HoloLens, mit dem Sie über einen Webbrowser auf dem PC eine Verbindung herstellen können.

    > [!CAUTION]
    > Wenn Sie HoloLens für die Verwendung der Geräteportal einrichten, müssen Sie den Entwicklermodus auf dem Gerät aktivieren. Im Entwicklermodus auf einem Gerät mit Windows Holographic for Business können Sie Apps seitlich laden. Diese Einstellung stellt jedoch das Risiko dar, dass ein Benutzer Apps installieren kann, die nicht vom Benutzer zertifiziert Microsoft Store. Administratoren können die Möglichkeit zum Aktivieren des Entwicklermodus blockieren, indem sie die **Einstellung ApplicationManagement/AllowDeveloper Unlock** im [Richtlinien-CSP verwenden.](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) [Weitere Informationen zum Entwicklermodus](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Stellen Sie auf einem Computer über [](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) WLAN oder USB eine Verbindung mit HoloLens [herstellen.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)

1. Führen Sie eines der folgenden Verfahren aus:
   - Wenn Sie zum ersten Mal eine Verbindung mit dem Windows-Geräteportal herstellen, erstellen [Sie einen Benutzernamen und ein Kennwort.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Geben Sie den Benutzernamen und das Kennwort ein, die Sie zuvor eingerichtet haben.

    > [!TIP]
    > Wenn ein Zertifikatfehler im Browser angezeigt wird, führen Sie [diese Schritte zur Problembehandlung](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate) aus.

1. Wählen Sie im Windows-Geräteportal Kioskmodus **aus.**

1. Wählen **Sie Kioskmodus aktivieren** aus, wählen Sie eine App aus, die beim Starten des Geräts ausgeführt werden soll, und wählen Sie dann Speichern **aus.**

    ![Kioskmodus](images/kiosk.png)
1. Starten Sie HoloLens neu. Wenn Ihre Seite Geräteportal geöffnet ist, können  Sie oben auf der Seite neu starten auswählen.

> [!NOTE]
> Der Kioskmodus kann über die REST-API von Geräteportal festgelegt werden, indem post to /api/holographic/kioskmode/settings mit einem erforderlichen Abfragezeichenfolgenparameter ("kioskModeEnabled&quot; mit dem Wert &quot;true&quot; oder &quot;false") und einem optionalen Parameter ("startupApp" mit einem Wert eines Paketnamens) ausgeführt wird. Beachten Sie, dass Geräteportal nur für Entwickler vorgesehen ist und nicht auf Nicht-Entwicklergeräten aktiviert werden sollte. Die REST-API kann sich in zukünftigen Updates/Releases ändern.

## <a name="more-information"></a>Weitere Informationen

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Sehen Sie sich an, wie Sie einen Kiosk mithilfe eines Bereitstellungspakets konfigurieren.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Global zugewiesener Zugriff – Kioskmodus
- Reduzierte Identitätsverwaltung für Kiosk, indem die neue Kioskmethode aktiviert wird, die den Kioskmodus auf Systemebene verwendet.

Mit diesem neuen Feature kann ein IT-Administrator ein HoloLens 2-Gerät für den Kioskmodus für mehrere Apps konfigurieren, der auf Systemebene anwendbar ist, keine Affinität mit einer Identität im System auf hat und für alle Benutzer gilt, die sich am Gerät befinden. Weitere Informationen zu diesem neuen Feature finden Sie in der Dokumentation zum Kiosk mit [global zugewiesenem HoloLens-Zugriff.](hololens-global-assigned-access-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Automatisches Starten einer Anwendung im Kioskmodus mit mehreren Apps 
- Fokussierte Erfahrung mit dem automatischen App-Start, wodurch die Benutzeroberflächen- und App-Auswahl für Kioskmodus-Benutzeroberflächen weiter erhöht wird.

Gilt nur für den Kioskmodus mit mehreren Apps, und nur eine App kann mithilfe des hervorgehobenen Attributs unten in der Konfiguration des zugewiesenen Zugriffs für den automatischen Start festgelegt werden. 

Die Anwendung wird automatisch gestartet, wenn sich der Benutzer anmeldet. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Änderungen am Kioskmodusverhalten für die Behandlung von Fehlern
Wenn beim Anwenden des Kioskmodus Fehler auftreten, wird das folgende Verhalten angezeigt:

- Vor Windows Holographic zeigt Version 20H2 – HoloLens alle Anwendungen im Startmenü an.
- Windows Holographic, Version 20H2: Wenn ein Gerät über eine Kioskkonfiguration verfügt, bei der es sich um eine Kombination aus global zugewiesenem Zugriff und zugewiesenem Zugriff durch AAD-Gruppenmitglied handelt, wird dem Benutzer im Startmenü nichts angezeigt, wenn die Ermittlung der AAD-Gruppenmitgliedschaft fehlschlägt.

![Abbildung, wie der Kioskmodus jetzt aussieht, wenn ein Fehler auftritt.](images/hololens-kiosk-failure-behavior.png )


- Ab [Windows Holographic, Version 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)sucht der Kioskmodus nach global zugewiesenem Zugriff, bevor ein leeres Startmenü angezeigt wird. Die Kioskbenutzeroberfläche wird bei Ausfällen während des Kioskmodus der AAD-Gruppe auf eine globale Kioskkonfiguration (falls vorhanden) zurückgreifen.

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Cache Azure AD Gruppenmitgliedschaft für Offlinekiosk

- Sichererer Kioskmodus, indem verfügbare Apps bei Kioskmodusfehlern beseitigt werden.
- Offlinekiosks können bis zu 60 Tage lang mit Azure AD Gruppen verwendet werden.

Diese Richtlinie steuert, wie viele Tage Azure AD Gruppenmitgliedschaftscache für Konfigurationen des zugewiesenen Zugriffs verwendet werden darf, die auf Azure AD Gruppen für angemeldete Benutzer ausgerichtet sind. Sobald dieser Richtlinienwert nur auf einen Wert größer als 0 festgelegt ist, wird der Cache verwendet, andernfalls nicht.  

Name: AADGroupMembershipCacheCacheInDays-URI-Wert: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCache UsernameInDays

Min. – 0 Tage  
Max. – 60 Tage 

Schritte zur ordnungsgemäßen Verwendung dieser Richtlinie: 
1. Erstellen Sie ein Gerätekonfigurationsprofil für Kiosk-Azure AD Gruppen, und weisen Sie es HoloLens-Geräten zu. 
1. Erstellen Sie eine benutzerdefinierte OMA-URI-basierte Gerätekonfiguration, mit der dieser Richtlinienwert auf die gewünschte Anzahl von Tagen (> 0) und den HoloLens-Geräten zugewiesen wird. 
    1. Der URI-Wert sollte im Textfeld OMA-URI als ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays eingegeben werden.
    1. Der Wert kann zwischen min und max zulässig sein.
1. Registrieren Sie HoloLens-Geräte, und überprüfen Sie, ob beide Konfigurationen auf das Gerät angewendet werden. 
1. Lassen Azure AD Benutzer 1 anmelden, wenn das Internet verfügbar ist. Sobald sich der Benutzer anmeldet und Azure AD die Gruppenmitgliedschaft bestätigt wurde, wird der Cache erstellt. 
1. Jetzt Azure AD Benutzer 1 HoloLens offline schalten und für den Kioskmodus verwenden, solange der Richtlinienwert X Tage zulässt. 
1. Die Schritte 4 und 5 können für alle anderen Azure AD-Benutzer N wiederholt werden. Der wichtigste Punkt hierbei ist, dass sich jeder Azure AD-Benutzer über das Internet bei dem Gerät anmelden muss. So können wir mindestens einmal feststellen, dass er Mitglied der Azure AD-Gruppe ist, für die die Kioskkonfiguration bestimmt wird. 
 
> [!NOTE]
> Bis Schritt 4 für einen Benutzer ausgeführt wird Azure AD tritt in "getrennten" Umgebungen ein Fehlerverhalten auf. 


## <a name="xml-kiosk-code-samples-for-hololens"></a>XML-Kioskcodebeispiele für HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Mehrere App-Kioskmodus für eine Azure AD Gruppe. 
Dieser Kiosk stellt einen Kiosk für Benutzer in der Azure AD-Gruppe zur Verfügung, für die ein Kiosk aktiviert ist, der die drei Apps enthält: Einstellungen, Remote Assist und Feedback-Hub. Um dieses Beispiel so zu ändern, dass es sofort verwendet wird, stellen Sie sicher, dass Sie die unten hervorgehobene GUID so ändern, dass sie einer eigenen Azure AD-Gruppe gleicht. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Mehrere App-Kioskmodus für Azure AD Konto.
Dieser Kiosk stellt einen Kiosk für einen einzelnen Benutzer zur Verfügung. Er verfügt über einen aktivierten Kiosk, der die 3 Apps enthält: Einstellungen, Remote Assist und Feedback-Hub. Um dieses Beispiel so zu ändern, dass es sofort verwendet wird, stellen Sie sicher, dass Sie das unten hervorgehobene Konto so ändern, dass es Azure AD ihrem eigenen Konto abgleicht. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

