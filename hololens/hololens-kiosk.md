---
title: Einrichten von HoloLens als Kiosk
description: Erfahren Sie, wie Sie eine Kioskkonfiguration einrichten und verwenden, um die Apps auf HoloLens Geräten zu sperren.
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
ms.openlocfilehash: e7f1efa99cc16b1003bd7063817451013ed2ec2661dbdf02edcd89c7984d0980
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664008"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Einrichten von HoloLens als Kiosk

Sie können ein HoloLens Gerät so konfigurieren, dass es als Gerät mit festem Zweck funktioniert, das auch als *Kiosk* bezeichnet wird, indem Sie das Gerät so konfigurieren, dass es im Kioskmodus ausgeführt wird. Der Kioskmodus schränkt die Anwendungen (oder Benutzer) ein, die auf dem Gerät verfügbar sind. Der Kioskmodus ist ein praktisches Feature, mit dem Sie ein HoloLens Gerät für Geschäfts-Apps oder das HoloLens Gerät in einer App-Demo verwenden können.

Dieser Artikel enthält Informationen zu Aspekten der Kioskkonfiguration, die für HoloLens Geräte spezifisch sind. Allgemeine Informationen zu den verschiedenen Arten von Windows-basierten Kiosken und deren Konfiguration finden Sie unter [Konfigurieren von Kiosken und digitalen Schildern auf Windows Desktopeditionen.](/windows/configuration/kiosk-methods)  

> [!IMPORTANT]  
> Der Kioskmodus bestimmt, welche Apps verfügbar sind, wenn sich ein Benutzer beim Gerät anmeldet. Der Kioskmodus ist jedoch keine Sicherheitsmethode. Es verhindert nicht, dass eine "zulässige" App eine andere App öffnet, die nicht zulässig ist. Um das Öffnen von Apps oder Prozessen zu blockieren, verwenden [Sie Windows Defender Application Control (WDAC)-CSP,](/windows/client-management/mdm/applicationcontrol-csp) um entsprechende Richtlinien zu erstellen.
>
> Erfahren Sie mehr über die Microsoft-Dienste, um Benutzern ein erweitertes Sicherheitsniveau zu bieten, das HoloLens 2 verwendet. Weitere Informationen finden Sie unter [Zustandstrennung und -isolation – Defender-Schutz.](security-state-separation-isolation.md#defender-protections) Oder erfahren Sie, wie Sie [WDAC und Windows PowerShell verwenden, um Apps auf HoloLens 2 Geräten mit Microsoft Intune zuzulassen oder zu blockieren.](/mem/intune/configuration/custom-profile-hololens)

Sie können den Kioskmodus entweder in einer Einzel-App- oder einer Multi-App-Konfiguration verwenden, und Sie können einen von drei Prozessen verwenden, um die Kioskkonfiguration einzurichten und bereitzustellen.

> [!IMPORTANT]  
> Durch das Löschen der Konfiguration mit mehreren Apps werden die Benutzersperrprofile entfernt, die von der zugewiesenen Zugriffsfunktion erstellt wurden. Es werden jedoch nicht alle Richtlinienänderungen rückgängig macht. Um diese Richtlinien rückgängig zu machen, müssen Sie das Gerät auf die Werkseinstellungen zurücksetzen.

## <a name="plan-the-kiosk-deployment"></a>Planen der Kioskbereitstellung

Bei der Planung Ihres Kiosks müssen Sie die folgenden Fragen beantworten können. Hier sind einige Entscheidungen, die Beim Lesen dieser Seite zu berücksichtigen sind, und einige Überlegungen zu diesen Fragen.
1. **Wer ihren Kiosk verwenden, und welche [Art von Konto(en)](hololens-identity.md) werden sie verwenden?** Dies ist eine Entscheidung, die Sie wahrscheinlich bereits getroffen haben und nicht für Ihren Kiosk angepasst werden sollten. Sie wirkt sich jedoch darauf aus, wie der Kiosk später zugewiesen wird.
1. **Benötigen Sie entweder unterschiedliche Kiosks pro Benutzer/Gruppe oder einen Kiosk, der für einige nicht aktiviert ist?** Wenn ja, sollten Sie Ihren Kiosk über XML erstellen. 
1. **Wie viele Apps werden in Ihrem Kiosk enthalten sein?** Wenn Sie über mehr als eine App verfügen, benötigen Sie einen Kiosk mit mehreren Apps. 
1. **Welche Apps sind in Ihrem Kiosk enthalten?** Verwenden Sie unsere nachstehende Liste der AUMIDs, um zusätzlich zu Ihren eigenen In-Box Apps hinzuzufügen.
1. **Wie planen Sie die Bereitstellung Ihres Kiosks?** Wenn Sie ein Gerät bei MDM registrieren, wird die Verwendung von MDM zum Bereitstellen Ihres Kiosks empfohlen. Wenn Sie MDM nicht verwenden, ist die Bereitstellung mit dem Bereitstellungspaket verfügbar.  

### <a name="kiosk-mode-requirements"></a>Kioskmodusanforderungen

Sie können jedes HoloLens 2 Gerät für die Verwendung des Kioskmodus konfigurieren.

> [!IMPORTANT]
> Der Kioskmodus ist nur verfügbar, wenn das Gerät über Windows Holographic for Business verfügt. Alle HoloLens 2-Geräte werden mit Windows Holographic for Business versendet, und es gibt keine anderen Editionen. Alle HoloLens 2 Geräte können den Kioskmodus sofort ausführen.
>
> HoloLens -Geräte (1. Generation) müssen sowohl im Hinblick auf den Betriebssystembuild als auch die Betriebssystemedition aktualisiert werden. Hier finden Sie weitere Informationen zum Aktualisieren eines HoloLens (1. Generation) auf [Windows Holographic for Business](hololens1-upgrade-enterprise.md) Edition. Um ein HoloLens Gerät (1. Generation) für die Verwendung des Kioskmodus zu aktualisieren, müssen Sie zunächst sicherstellen, dass das Gerät Windows 10 Version 1803 oder höher ausgeführt wird. Wenn Sie das Windows Device Recovery Tool verwendet haben, um Ihr HoloLens Gerät (1. Generation) auf den Standardbuild wiederherzustellen, oder wenn Sie die neuesten Updates installiert haben, kann Ihr Gerät konfiguriert werden.

> [!IMPORTANT]  
> Um Geräte zu schützen, die im Kioskmodus ausgeführt werden, sollten Sie Geräteverwaltungsrichtlinien hinzufügen, die Features wie USB-Konnektivität deaktivieren. Überprüfen Sie außerdem ihre Updateringeinstellungen, um sicherzustellen, dass keine automatischen Updates während der Geschäftszeiten erfolgen.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Entscheiden zwischen einem Kiosk mit einer einzelnen App oder einem Kiosk mit mehreren Apps

Ein Kiosk mit einer einzelnen App startet die angegebene App, wenn sich der Benutzer beim Gerät anmeldet. Die Startmenü ist deaktiviert, ebenso wie Cortana. Ein HoloLens 2 Gerät reagiert nicht auf [](hololens2-basic-usage.md#start-gesture) die Startgeste. Ein HoloLens Gerät (1. Generation) reagiert nicht auf die [Geste der Blume.](hololens1-basic-usage.md) Da nur eine App ausgeführt werden kann, kann der Benutzer keine anderen Apps platzieren.

Ein Kiosk mit mehreren Apps zeigt die Startmenü an, wenn sich der Benutzer beim Gerät anmeldet. Die Kioskkonfiguration bestimmt, welche Apps auf dem Startmenü verfügbar sind. Sie können einen Kiosk mit mehreren Apps verwenden, um Benutzern eine leicht verständliche Erfahrung zu bieten, indem Sie ihnen nur die Dinge präsentieren, die sie verwenden müssen, und die Dinge entfernen, die sie nicht verwenden müssen.

In der folgenden Tabelle sind die Featurefunktionen in den verschiedenen Kioskmodi aufgeführt.

| &nbsp; |Startmenü |Menü "Schnelle Aktionen" |Kamera und Video |Miracast |Cortana |Integrierte Sprachbefehle |
| --- | --- | --- | --- | --- | --- | --- | 
|Kiosk mit einzelner App |Disabled |Disabled |Disabled |Disabled   |Disabled |Aktiviert<sup>1</sup> |
|Kiosk mit mehreren Apps |Aktiviert |Aktiviert<sup>2</sup> |Verfügbar<sup>2</sup> |Verfügbar<sup>2</sup> |Verfügbar<sup>2, 3</sup>  |Aktiviert<sup>1</sup> |

> <sup>1</sup> Sprachbefehle, die sich auf deaktivierte Features beziehen, funktionieren nicht.  
> <sup>2</sup> Weitere Informationen zum Konfigurieren dieser Features finden Sie unter [Auswählen von Kiosk-Apps.](#plan-kiosk-apps)  
> <sup>3</sup> Auch wenn Cortana deaktiviert ist, sind die integrierten Sprachbefehle aktiviert.

In der folgenden Tabelle sind die Benutzerunterstützungsfeatures der verschiedenen Kioskmodi aufgeführt.

| &nbsp; |Unterstützte Benutzertypen | Automatische Anmeldung | Mehrere Zugriffsebenen |
| --- | --- | --- | --- |
|Kiosk mit einzelner App | Microsoft-Konto (MSA) in Azure Active Directory (Azure AD) oder lokalem Konto |Ja |Nein |
|Kiosk mit mehreren Apps |Azure AD-Konto |Nein |Ja |

Beispiele für die Verwendung dieser Funktionen finden Sie in der folgenden Tabelle.

|Verwenden Sie einen Kiosk mit einer einzelnen App für: |Verwenden Sie einen Kiosk mit mehreren Apps für: |
| --- | --- |
|Ein Gerät, auf dem nur ein Dynamics 365-Leitfaden für neue Mitarbeiter ausgeführt wird. |Ein Gerät, auf dem sowohl Leitfäden als auch Remoteunterstützung für eine Reihe von Mitarbeitern ausgeführt werden. |
|Ein Gerät, auf dem nur eine benutzerdefinierte App ausgeführt wird. |Ein Gerät, das für die meisten Benutzer als Kiosk fungiert (nur eine benutzerdefinierte App ausführt), aber als Standardgerät für eine bestimmte Benutzergruppe fungiert. |

### <a name="plan-kiosk-apps"></a>Planen von Kiosk-Apps

Allgemeine Informationen zum Auswählen von Kiosk-Apps finden Sie unter [Richtlinien zum Auswählen einer App für zugewiesenen Zugriff (Kioskmodus).](/windows/configuration/guidelines-for-assigned-access-app)

Wenn Sie die Windows Geräteportal verwenden, um einen Kiosk mit einer einzelnen App zu konfigurieren, wählen Sie die App während des Setupvorgangs aus.  

Wenn Sie ein Mobile Geräteverwaltung-System (MDM) oder ein Bereitstellungspaket zum Konfigurieren des Kioskmodus verwenden, verwenden Sie [den AssignedAccess-Konfigurationsdienstanbieter (AssignedAccess Configuration Service Provider, CSP),](/windows/client-management/mdm/assignedaccess-csp) um Anwendungen anzugeben. Der CSP verwendet [Anwendungsbenutzermodell-IDs (Application User Model IDs, AUMIDs),](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) um Anwendungen zu identifizieren. In der folgenden Tabelle sind die AUMIDs einiger In-Box-Anwendungen aufgeführt, die Sie in einem Kiosk mit mehreren Apps verwenden können.

> [!IMPORTANT]
> Der Kioskmodus bestimmt, welche Apps verfügbar sind, wenn sich ein Benutzer beim Gerät anmeldet. Der Kioskmodus ist jedoch keine Sicherheitsmethode. Es verhindert nicht, dass eine "zulässige" App eine andere App öffnet, die nicht zulässig ist. Da wir dieses Verhalten nicht einschränken, können Apps weiterhin über Edge, den Datei-Explorer und die Microsoft Store-Apps gestartet werden. Wenn es bestimmte Apps gibt, die nicht über einen Kiosk gestartet werden sollen, verwenden Sie [Windows Defender Application Control (WDAC)-CSP,](/windows/client-management/mdm/applicationcontrol-csp) um entsprechende Richtlinien zu erstellen. 
> 
> Darüber hinaus kann die Mixed Reality Home nicht als Kiosk-App festgelegt werden.

<a id="aumids"></a>

|App-Name |AUMID |
| --- | --- |
|3D-Betrachter |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Calendar |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Kamera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|Geräteauswahl auf HoloLens (1. Generation) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Geräteauswahl auf HoloLens 2 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DevicesFlowHost |
|Dynamics 365-Leitfäden |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteRob \_ 8wekyb3d8bbwe \! Microsoft.RemoteDiagnose |
|&nbsp;Feedback-Hub |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe-App \! |
|Datei-Explorer |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Alte Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Neue Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast<sup>4</sup> |&nbsp; |
|Filme & TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Fotos |Microsoft. Windows. \_Fotos 8wekyb3d8bbwe-App \! |
|Alte Einstellungen |HolographicSystemSettings_cw5n1h2txyewy! App |
|Neue Einstellungen |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|Tipps |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Zum Aktivieren der Foto- oder Videoaufnahme müssen Sie die Kamera-App als Kiosk-App aktivieren.  
> <sup>2</sup> Wenn Sie die Kamera-App aktivieren, beachten Sie die folgenden Bedingungen:
> - Das Menü Schnellaktionen enthält die Schaltflächen Foto und Video.  
> - Sie sollten auch eine App (z. B. Fotos, E-Mail oder OneDrive) aktivieren, die mit Bildern interagieren oder diese abrufen kann.  
>  
> <sup>3</sup> Auch wenn Sie Cortana nicht als Kiosk-App aktivieren, sind integrierte Sprachbefehle aktiviert. Befehle, die sich auf deaktivierte Features beziehen, haben jedoch keine Auswirkungen.  
> <sup>4</sup> Sie können Miracast nicht direkt aktivieren. Um Miracast als Kiosk-App zu aktivieren, aktivieren Sie die Kamera-App und die Geräteauswahl-App.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Planen von Kioskprofilen für Benutzer oder Gruppen

Wenn Sie entweder die XML-Datei erstellen oder die Intune-Benutzeroberfläche zum Einrichten eines Kiosks verwenden, müssen Sie berücksichtigen, wer der Benutzer des Kiosks sein wird. Eine Kioskkonfiguration kann entweder auf ein einzelnes Konto oder auf Azure AD Gruppen beschränkt werden. 

Kiosks sind in der Regel für einen Benutzer oder eine Benutzergruppe aktiviert. Wenn Sie jedoch ihren eigenen XML-Kiosk schreiben möchten, sollten Sie den global zugewiesenen Zugriff in Betracht ziehen, bei dem der Kiosk unabhängig von der Identität auf Geräteebene angewendet wird. Wenn ihnen dies gefällt, lesen Sie [weitere Informationen zu Kiosks mit global zugewiesenem Zugriff.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>Wenn Sie eine XML-Datei erstellen:
-   Viele erstellen mehrere Kioskprofile und weisen sie jeweils verschiedenen Benutzern/Gruppen zu. Beispielsweise ein Kiosk für Ihre Azure AD-Gruppe mit vielen Apps und ein Besucher, der über einen Kiosk mit mehreren Apps mit einer einzelnen App verfügt.
-   Ihre Kioskkonfiguration wird als **Profil-ID** bezeichnet und hat eine GUID.
-   Sie weisen dieses Profil im Abschnitt configs zu, indem Sie den Benutzertyp angeben und dieselbe GUID für die **DefaultProfile-ID** verwenden.
- Eine XML-Datei kann erstellt, aber trotzdem über MDM auf ein Gerät angewendet werden, indem ein benutzerdefiniertes OMA-URI-Gerätekonfigurationsprofil erstellt und mithilfe des URI-Werts auf HoloLens Gerätegruppe angewendet wird: ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Wenn Sie einen Kiosk in Intune erstellen.
-   Jedes Gerät erhält möglicherweise nur ein einzelnes Kioskprofil, andernfalls führt dies zu einem Konflikt und empfängt überhaupt keine Kioskkonfigurationen. 
    -   Andere Arten von Profilen und Richtlinien, z. B. Geräteeinschränkungen, die nicht mit dem Kioskkonfigurationsprofil in Zusammenhang stehen, stehen nicht in Konflikt mit dem Kioskkonfigurationsprofil.
-   Der Kiosk wird für alle Benutzer aktiviert, die Teil des Benutzeranmeldungstyps sind. Dies wird mit einem Benutzer oder Azure AD Gruppe festgelegt. 
-   Nachdem die Kioskkonfiguration festgelegt und der **Benutzeranmeldungstyp** (Benutzer, die sich am Kiosk anmelden können) und die Apps ausgewählt sind, muss die Gerätekonfiguration weiterhin einer Gruppe zugewiesen werden. Die zugewiesenen Gruppen bestimmen, welche Geräte die Kioskgerätekonfiguration erhalten, interagieren jedoch nicht mit , wenn der Kiosk aktiviert ist oder nicht. 
    - Eine vollständige Erläuterung der Auswirkungen der Zuweisung von Konfigurationsprofilen in Intune finden Sie unter [Zuweisen von Benutzer- und Geräteprofilen in Microsoft Intune](/intune/configuration/device-profile-assign).

### <a name="select-a-deployment-method"></a>Auswählen einer Bereitstellungsmethode

Sie können eine der folgenden Methoden zum Bereitstellen von Kioskkonfigurationen auswählen:

- [Microsoft Intune oder anderer Mdm-Dienst (Mobile Device Management, Verwaltung mobiler Geräte)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Bereitstellungspaket](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Geräteportal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Da diese Methode erfordert, dass der Entwicklermodus auf dem Gerät aktiviert ist, wird empfohlen, sie nur für Demonstrationen zu verwenden.

In der folgenden Tabelle sind die Funktionen und Vorteile der einzelnen Bereitstellungsmethoden aufgeführt.

| &nbsp; |Bereitstellen mithilfe von Windows Geräteportal |Bereitstellen mithilfe eines Bereitstellungspakets |Bereitstellen mithilfe von MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Bereitstellen von Kiosken mit nur einer App   | Ja           | Ja                  | Ja  |
|Bereitstellen von Kiosken mit mehreren Apps    | Nein            | Ja                  | Ja  |
|Nur auf lokalen Geräten bereitstellen | Ja           | Ja                  | Nein   |
|Bereitstellen im Entwicklermodus |Erforderlich       | Nicht erforderlich            | Nicht erforderlich   |
|Bereitstellen mithilfe von Azure Active Directory (Azure AD)  | Nicht erforderlich            | Nicht erforderlich                   | Erforderlich  |
|Automatische Bereitstellung      | Nein            | Nein                   | Ja  |
|Bereitstellungsgeschwindigkeit            | Schnell       | Schnell                 | Langsam |
|Bedarfsorientiertes Bereitstellen | Nicht empfohlen    | Empfohlen        | Empfohlen |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Verwenden von Microsoft Intune oder einer anderen MDM zum Einrichten eines Kiosks mit einer app oder mehreren Apps

Führen Sie die folgenden Schritte aus, um den Kioskmodus mit Microsoft Intune oder einem anderen MDM-System einzurichten.

1. [Bereiten Sie die Registrierung der Geräte](#mdmenroll)vor.
1. [Erstellen Sie ein Kioskkonfigurationsprofil.](#mdmprofile)
1. Konfigurieren Sie den Kiosk.
   - [Konfigurieren Sie die Einstellungen für einen Kiosk mit einer einzelnen App.](#mdmconfigsingle)
   - [Konfigurieren Sie die Einstellungen für einen Kiosk mit mehreren Apps.](#mdmconfigmulti)
1. [Weisen Sie das Kioskkonfigurationsprofil einer Gruppe zu.](#mdmassign)
1. Stellen Sie die Geräte bereit.
   - [Stellen Sie einen Kiosk](#mdmsingledeploy)mit einer einzelnen App bereit.
   - [Stellen Sie einen Kiosk mit mehreren Apps](#mdmmultideploy)bereit.

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, Schritt &ndash; 1: Vorbereiten der Registrierung der Geräte

Sie können Ihr MDM-System so konfigurieren, dass HoloLens Geräte automatisch registriert werden, wenn sich der Benutzer zum ersten Mal anmeldet, oder Benutzer geräte manuell registrieren lassen. Die Geräte müssen außerdem Ihrer Azure AD Domäne angehören und den entsprechenden Gruppen zugewiesen werden.

Weitere Informationen zum Registrieren der Geräte finden Sie unter [Registrieren von HoloLens bei MDM-](hololens-enroll-mdm.md) und [Intune-Registrierungsmethoden für Windows Geräte.](/mem/intune/enrollment/windows-enrollment-methods)

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, Schritt &ndash; 2: Erstellen eines Kioskkonfigurationsprofils

1. Öffnen [](https://portal.azure.com/) Sie das Azure-Portal, und melden Sie sich bei Ihrem Intune-Administrator-Konto an.
1. Wählen Sie **Microsoft Intune**  >  **Gerätekonfiguration – Profile** Profil  >  **erstellen** aus.
1. Geben Sie einen Profilnamen ein.
1. Wählen Sie **Plattform**  >  **Windows 10 und höher und** dann **Profiltyp**  > **Geräteeinschränkungen** aus.
1. Wählen Sie Kiosk **konfigurieren**  >  und dann eine der folgenden Optionen aus:
   - Um einen Kiosk mit einer einzelnen App zu erstellen, wählen Sie **Kioskmodus** Kiosk kiosk  >  **(Einzel-App-Kiosk)** aus.
   - Um einen Kiosk mit mehreren Apps zu erstellen, wählen Sie **Kioskmodus**  >  **Multi-App-Kiosk** aus.
1. Wählen Sie **Hinzufügen** aus, um mit der Konfiguration des Kiosks zu beginnen.

Die nächsten Schritte unterscheiden sich je nach gewünschtem Kiosktyp. Wählen Sie eine der folgenden Optionen aus, um weitere Informationen zu erfahren:  

- [Kiosk mit einzelner App](#mdmconfigsingle)
- [Kiosk mit mehreren Apps](#mdmconfigmulti)

Weitere Informationen zum Erstellen eines Kioskkonfigurationsprofils finden Sie unter [Windows 10 und Windows Holographic for Business Geräteeinstellungen für die Ausführung als dedizierter Kiosk mit Intune.](/intune/configuration/kiosk-settings)

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, Schritt 3 (Einzel-App) &ndash;  Konfigurieren der Einstellungen für einen Kiosk mit einer einzelnen App

In diesem Abschnitt werden die Einstellungen zusammengefasst, die für einen Kiosk mit einer einzelnen App erforderlich sind. Weitere Informationen finden Sie in den folgenden Artikeln:

- Informationen zum Konfigurieren eines Kioskkonfigurationsprofils in Intune finden Sie unter Konfigurieren des [Kioskmodus mit Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Weitere Informationen zu den verfügbaren Einstellungen für Kioske mit nur einer App in Intune finden Sie unter Kioske für [Einzel-Vollbild-Apps.](/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Anweisungen zu weiteren MDM-Diensten finden Sie in der Dokumentation Ihres Anbieters. Wenn Sie eine benutzerdefinierte XML-Konfiguration zum Einrichten eines Kiosks in Ihrem MDM-Dienst verwenden müssen, [erstellen Sie eine XML-Datei, die die Kioskkonfiguration definiert.](#ppkioskconfig)

1. Wählen Sie **Benutzeranmeldung geben**  >  **Sie Lokales Benutzerkonto** ein, und geben Sie dann den Benutzernamen des lokalen (Geräte-)Kontos oder des Microsoft-Kontos (MSA) ein, das sich beim Kiosk anmelden kann.
   > [!NOTE]  
   > Der Typ **Autologon** wird unter Windows Holographic for Business nicht unterstützt.
1. Wählen Sie **Anwendungstyp**  >  **Store App** aus, und wählen Sie dann eine App aus der Liste aus.

Der nächste Schritt besteht darin, das Profil einer Gruppe [zuzuweisen.](#mdmassign)

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, Schritt 3 (mehrere Apps) &ndash; Konfigurieren der Einstellungen für einen Kiosk mit mehreren Apps

In diesem Abschnitt werden die Einstellungen zusammengefasst, die für einen Kiosk mit mehreren Apps erforderlich sind. Ausführlichere Informationen finden Sie in den folgenden Artikeln:

- Informationen zum Konfigurieren eines Kioskkonfigurationsprofils in Intune finden Sie unter Konfigurieren des [Kioskmodus mit Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Weitere Informationen zu den verfügbaren Einstellungen für Kioske mit mehreren Apps in Intune finden Sie unter Kioske mit [mehreren Apps.](/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Anweisungen zu weiteren MDM-Diensten finden Sie in der Dokumentation Ihres Anbieters. Wenn Sie eine benutzerdefinierte XML-Konfiguration zum Einrichten eines Kiosks in Ihrem MDM-Dienst verwenden müssen, [erstellen Sie eine XML-Datei, die die Kioskkonfiguration definiert.](#ppkioskconfig) Wenn Sie eine XML-Datei verwenden, stellen Sie sicher, dass Sie das [Startlayout](#start-layout-for-hololens)einschließen.  
- Sie können optional ein benutzerdefiniertes Startlayout mit Intune oder anderen MDM-Diensten verwenden. Weitere Informationen finden Sie unter Starten der [Layoutdatei für MDM (Intune und andere).](#start-layout-file-for-mdm-intune-and-others)

1. Wählen Sie **Ziel Windows 10 im S Modus Geräte**  >  **Nein** aus.  
>[!NOTE]  
> Der S Modus wird unter Windows Holographic for Business nicht unterstützt.

1. Wählen Sie **Benutzeranmeldungstyp**  >  **Azure AD Benutzer oder Gruppe** oder **Benutzeranmeldungstyp**  >  **HoloLens Besucher** aus, und fügen Sie dann eine oder mehrere Benutzergruppen oder Konten hinzu.  

   Nur Benutzer, die zu den Gruppen oder Konten gehören, die Sie unter **Benutzeranmeldungstyp** angeben, können die Kioskerfahrung verwenden.

1. Wählen Sie mithilfe der folgenden Optionen eine oder mehrere Apps aus:
   - Um eine hochgeladene branchenspezifische App hinzuzufügen, wählen **Sie Store-App hinzufügen** und dann die gewünschte App aus.
   - Um eine App durch Angabe ihrer AUMID hinzuzufügen, wählen **Sie Von AUMID hinzufügen aus,** und geben Sie dann die AUMID der App ein. [Sehen Sie sich die Liste der verfügbaren AUMIDs an.](#aumids)

Der nächste Schritt besteht darin, das Profil einer Gruppe [zuzuweisen.](#mdmassign)

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, Schritt &ndash; 4: Zuweisen des Kioskkonfigurationsprofils zu einer Gruppe

Auf der Seite Zuweisungen des **Kioskkonfigurationsprofils** können Sie festlegen, wo die Kioskkonfiguration bereitgestellt werden soll. Im einfachsten Fall weisen Sie das Kioskkonfigurationsprofil einer Gruppe zu, die das HoloLens Gerät enthält, wenn das Gerät bei MDM registriert wird.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, Schritt 5 (Einzel-App) &ndash; Bereitstellen eines Kiosks mit einer einzelnen App

Wenn Sie ein MDM-System verwenden, können Sie das Gerät während der OOBE bei MDM registrieren. Nach Abschluss der OOBE-Ausführung ist die Anmeldung beim Gerät ganz einfach.

Führen Sie während der OOBE die folgenden Schritte aus:

1. Melden Sie sich mit dem Konto an, das Sie im Kioskkonfigurationsprofil angegeben haben.
1. Registrieren Sie das Gerät. Stellen Sie sicher, dass das Gerät der Gruppe hinzugefügt wird, der das Kioskkonfigurationsprofil zugewiesen ist.
1. Warten Sie, bis OOBE abgeschlossen ist, bis die Store-App heruntergeladen und installiert wird und bis Richtlinien angewendet werden. Starten Sie dann das Gerät neu.

Wenn Sie sich das nächste Mal beim Gerät anmelden, sollte die Kiosk-App automatisch gestartet werden.

Wenn Ihre Kioskkonfiguration zu diesem Zeitpunkt nicht angezeigt wird, [überprüfen Sie den Zuweisungsstatus](/intune/configuration/device-profile-monitor).

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, Schritt 5 (mehrere Apps) &ndash; Bereitstellen eines Kiosks mit mehreren Apps

Wenn Sie ein MDM-System verwenden, können Sie das Gerät mit Ihrem Azure AD Mandanten verbinden und das Gerät während der OOBE bei MDM registrieren. Stellen Sie ggf. die Registrierungsinformationen für die Benutzer bereit, damit sie während des OOBE-Prozesses verfügbar sind.

> [!NOTE]  
> Wenn Sie das Kioskkonfigurationsprofil einer Gruppe zugewiesen haben, die Benutzer enthält, stellen Sie sicher, dass eines dieser Benutzerkonten das erste Konto ist, das sich beim Gerät anmeldet.

Führen Sie während der OOBE die folgenden Schritte aus:

1. Melden Sie sich mit dem Konto an, das zur Gruppe **Benutzeranmeldung** gehört.
1. Registrieren Sie das Gerät.
1. Warten Sie, bis alle Apps, die Teil des Kioskkonfigurationsprofils sind, heruntergeladen und installiert werden. Warten Sie außerdem, bis Richtlinien angewendet werden.  
1. Nach Abschluss von OOBE können Sie zusätzliche Apps aus dem Microsoft Store installieren oder querladen. [Erforderliche Apps](/mem/intune/apps/apps-deploy#assign-an-app) für die Gruppe, zu der das Gerät gehört, werden automatisch installiert.
1. Starten Sie das Gerät nach Abschluss der Installation neu.

Bei der nächsten Anmeldung beim Gerät mit einem Konto, das zum **Benutzeranmeldetyp** gehört, sollte die Kiosk-App automatisch gestartet werden.

Wenn Ihre Kioskkonfiguration zu diesem Zeitpunkt nicht angezeigt wird, [überprüfen Sie den Zuweisungsstatus](/intune/configuration/device-profile-monitor).

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Verwenden eines Bereitstellungspakets zum Einrichten eines Kiosks mit einer oder mehreren Apps

Führen Sie die folgenden Schritte aus, um den Kioskmodus mithilfe eines Bereitstellungspakets einzurichten.

1. [Erstellen Sie eine XML-Datei, die die Kioskkonfiguration definiert.](#ppkioskconfig), einschließlich eines [Startlayouts.](#start-layout-for-hololens)
2. [Fügen Sie die XML-Datei einem Bereitstellungspaket hinzu.](#ppconfigadd)
3. [Wenden Sie das Bereitstellungspaket auf HoloLens an.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Bereitstellungspaket, Schritt &ndash; 1: Erstellen einer KIOSK-Konfigurations-XML-Datei

Befolgen Sie [die allgemeinen Anweisungen, um eine XML-Datei für die Kioskkonfiguration für Windows Desktop zu erstellen,](/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)mit Ausnahme der folgenden:

- Schließen Sie keine klassischen Windows Anwendungen (Win32) ein. HoloLens unterstützt diese Anwendungen nicht.
- Verwenden Sie den [Platzhalter STARTLAYOUT-XML](#start-layout-for-hololens) für HoloLens.
- Optional: Hinzufügen von Gastzugriff zur Kioskkonfiguration

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>Optional: Hinzufügen von Gastzugriff zur Kioskkonfiguration

Im [Abschnitt **Configs** der XML-Datei](/windows/configuration/lock-down-windows-10-to-specific-apps#configs)können Sie eine spezielle Gruppe mit dem Namen **Visitor** konfigurieren, damit Gäste den Kiosk verwenden können. Wenn der Kiosk für die Unterstützung der speziellen Gruppe **Besucher** konfiguriert ist, wird der Anmeldeseite die Option **"Gast"** hinzugefügt. Das **Gastkonto** erfordert kein Kennwort, und alle daten, die dem Konto zugeordnet sind, werden gelöscht, wenn sich das Konto abmeldet.

Um das **Gastkonto** zu aktivieren, fügen Sie den folgenden Codeausschnitt zu Ihrer Kioskkonfigurations-XML hinzu:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a>Aktivieren der automatischen Anmeldung von Besuchern

Auf Builds [Windows Holographic, Version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) und höher:
- AAD- und Nicht-ADD-Konfigurationen unterstützen die automatische Anmeldung von Besucherkonten für Kioskmodi.

##### <a name="non-aad-configuration"></a>Nicht-AAD-Konfiguration

1. Erstellen Sie ein Bereitstellungspaket, das:
    1. Konfiguriert Laufzeiteinstellungen/AssignedAccess, um Besucherkonten zuzulassen.
    1. Registriert das Gerät optional bei MDM (Laufzeiteinstellungen/Arbeitsplatz/Registrierungen), damit es später verwaltet werden kann.
    1. Erstellen Sie kein lokales Konto.
2. [Wenden Sie das Bereitstellungspaket an.](hololens-provisioning.md)

##### <a name="aad-configuration"></a>AAD-Konfiguration

In AAD eingebundene Geräte, die für den Kioskmodus konfiguriert sind, können sich mit einer einzigen Schaltfläche vom Anmeldebildschirm aus bei einem Besucherkonto anmelden. Nach der Anmeldung beim Besucherkonto fordert das Gerät erst dann zur erneuten Anmeldung auf, wenn der Besucher explizit über das Startmenü abgemeldet oder das Gerät neu gestartet wurde.

Die automatische Anmeldung des Besuchers kann über [eine benutzerdefinierte OMA-URI-Richtlinie](/mem/intune/configuration/custom-settings-windows-10)verwaltet werden:

- URI-Wert: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon


| Richtlinie |BESCHREIBUNG |Configurations 
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Ermöglicht es einem Besucher, sich automatisch bei einem Kiosk zu anmelden. | 1 (Ja), 0 (Nein, Standard) |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>Platzhalter: Startlayout für HoloLens

Wenn Sie ein [Bereitstellungspaket](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) verwenden, um einen Kiosk mit mehreren Apps zu konfigurieren, ist für das Verfahren ein Startlayout erforderlich. Die Anpassung des Startlayouts wird in Windows Holographic for Business nicht unterstützt. Daher müssen Sie einen Platzhalter Startlayout verwenden.

> [!NOTE]  
> Da ein Kiosk mit einer einzelnen App die Kiosk-App startet, wenn sich ein Benutzer anmeldet, verwendet er keine Startmenü und muss nicht über ein Startlayout verfügen.

> [!NOTE]  
> Wenn Sie [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) zum Einrichten eines Kiosks mit mehreren Apps verwenden, können Sie optional ein Startlayout verwenden. Weitere Informationen finden Sie unter [PlatzhalterStartlayoutdatei für MDM (Intune und andere)](#start-layout-file-for-mdm-intune-and-others).

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

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>Platzhalter Startlayoutdatei für MDM (Intune und andere)

Speichern Sie das folgende Beispiel als XML-Datei. Sie können diese Datei verwenden, wenn Sie den Kiosk mit mehreren Apps in Microsoft Intune konfigurieren (oder in einem anderen MDM-Dienst, der ein Kioskprofil bereitstellt).

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Einstellung und eine vollständige XML-Konfiguration zum Einrichten eines Kiosks in Ihrem MDM-Dienst verwenden müssen, verwenden Sie die [Anweisungen zum Startlayout für ein Bereitstellungspaket.](#start-layout-for-hololens)

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

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. Paket, Schritt &ndash; 2: Hinzufügen der XML-Datei für die Kioskkonfiguration zu einem Bereitstellungspaket

1. Öffnen [Sie Windows-Konfigurations-Designer.](https://www.microsoft.com/store/apps/9nblggh4tx22)
1. Wählen Sie **Erweiterte Bereitstellung** aus, geben Sie einen Namen für Ihr Projekt ein, und wählen Sie dann **Weiter** aus.
1. Wählen Sie **Windows 10 Holographic** und dann **Weiter** aus.
1. Wählen Sie **Fertig stellen** aus. Der Arbeitsbereich für das Paket wird geöffnet.
1. Wählen Sie **Laufzeiteinstellungen**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings aus.**
1. Wählen Sie im mittleren Bereich **Durchsuchen** aus, um die von Ihnen erstellte Kioskkonfigurations-XML-Datei zu suchen und auszuwählen.

   ![Screenshot des Felds "MultiAppAssignedAccessSettings" in Windows-Konfigurations-Designer](./images/multiappassignedaccesssettings.png)

1. **Optional:** (Wenn Sie das Bereitstellungspaket nach der anfänglichen Einrichtung des Geräts anwenden möchten und bereits ein Administratorbenutzer auf dem Kioskgerät verfügbar ist, überspringen Sie diesen Schritt.) Wählen Sie **Laufzeiteinstellungen** &gt;  &gt; **KontenBenutzer** aus, und erstellen Sie dann ein Benutzerkonto. Geben Sie einen Benutzernamen und ein Kennwort an, und wählen Sie dann UserGroup Administrators **(Benutzergruppenadministratoren)**  >  **aus.**  
  
     Mit diesem Konto können Sie den Bereitstellungsstatus und die Protokolle anzeigen.  
1. **Optional:** (Wenn Sie bereits über ein Konto ohne Administratorrechte auf dem Kioskgerät verfügen, überspringen Sie diesen Schritt.) Wählen Sie **Laufzeiteinstellungen** &gt;  &gt; **KontenBenutzer** aus, und erstellen Sie dann ein lokales Benutzerkonto. Stellen Sie sicher, dass der Benutzername mit dem für das Konto identisch ist, das Sie in der XML-Konfigurationsdatei angeben. Wählen Sie **UserGroup**  >  **Standard Users aus.**
1. Wählen Sie **Datei** > **Speichern** aus.
1. Wählen Sie  >  **Bereitstellungspaket** exportieren und dann   >  **BESITZER IT-Administrator** aus. Dadurch wird die Rangfolge dieses Bereitstellungspakets höher als die Rangfolge der Bereitstellungspakete festgelegt, die auf dieses Gerät aus anderen Quellen angewendet werden.
1. Wählen Sie **Weiter** aus.
1. Wählen Sie auf der Seite Sicherheit des **Bereitstellungspakets** eine Sicherheitsoption aus.
   > [!IMPORTANT]  
   > Wenn Sie **Paketsignatur aktivieren** auswählen, müssen Sie auch ein gültiges Zertifikat auswählen, das zum Signieren des Pakets verwendet werden soll. Wählen Sie hierzu **Durchsuchen** aus, und wählen Sie das Zertifikat aus, das Sie zum Signieren des Pakets verwenden möchten.
   
   > [!CAUTION]  
   > Wählen Sie nicht **Paketverschlüsselung aktivieren** aus. Auf HoloLens Geräten führt diese Einstellung dazu, dass die Bereitstellung fehlschlägt.
1. Wählen Sie **Weiter** aus.
1. Geben Sie den Ausgabespeicherort an, an dem das Bereitstellungspaket bei der Erstellung enthalten sein soll. Standardmäßig verwendet Windows-Konfigurations-Designer den Projektordner als Ausgabespeicherort. Wenn Sie den Ausgabespeicherort ändern möchten, wählen **Sie Durchsuchen** aus. Wenn Sie fertig sind, klicken Sie auf **Weiter**.
1. Wählen Sie **Erstellen** aus, um mit dem Erstellen des Pakets zu beginnen. Die Erstellung eines Bereitstellungspakets dauert nicht lange. Auf der Buildseite werden die Projektinformationen angezeigt, und die Statusanzeige gibt den Buildstatus an.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Bereitstellungspaket, Schritt 3 &ndash; Anwenden des Bereitstellungspakets auf HoloLens

Der Artikel "Konfigurieren HoloLens mithilfe eines Bereitstellungspakets" enthält ausführliche Anweisungen zum Anwenden des Bereitstellungspakets unter den folgenden Umständen:

- Sie können während des Setups zunächst [ein Bereitstellungspaket auf HoloLens anwenden.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

- Sie können nach dem Setup auch [ein Bereitstellungspaket auf HoloLens anwenden.](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Verwenden des Windows Geräteportal zum Einrichten eines Kiosks mit einer einzelnen App

Führen Sie die folgenden Schritte aus, um den Kioskmodus mithilfe der Windows Geräteportal einzurichten.

1. [Richten Sie das HoloLens Gerät für die Verwendung des Windows Geräteportal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)ein. Das Geräteportal ist ein Webserver auf der HoloLens, mit dem Sie über einen Webbrowser auf dem PC eine Verbindung herstellen können.

    > [!CAUTION]
    > Wenn Sie HoloLens für die Verwendung des Geräteportal einrichten, müssen Sie den Entwicklermodus auf dem Gerät aktivieren. Im Entwicklermodus auf einem Gerät mit Windows Holographic for Business können Sie Apps querladen. Diese Einstellung birgt jedoch das Risiko, dass ein Benutzer Apps installieren kann, die nicht vom Microsoft Store zertifiziert wurden. Administratoren können die Möglichkeit zum Aktivieren des Entwicklermodus mithilfe der Einstellung **ApplicationManagement/AllowDeveloper Unlock** im [Richtlinien-CSP](/windows/client-management/mdm/policy-configuration-service-provider)blockieren. [Weitere Informationen zum Entwicklermodus](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Stellen Sie auf einem Computer eine Verbindung mit dem HoloLens [mithilfe von WLAN oder](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) [USB herstellen.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)

1. Führen Sie eines der folgenden Verfahren aus:
   - Wenn Sie zum ersten Mal eine Verbindung mit dem Windows Geräteportal herstellen, erstellen [Sie einen Benutzernamen und ein Kennwort.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Geben Sie den Benutzernamen und das Kennwort ein, die Sie zuvor eingerichtet haben.

    > [!TIP]
    > Wenn ein Zertifikatfehler im Browser angezeigt wird, führen Sie [diese Schritte zur Problembehandlung](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate) aus.

1. Wählen Sie im Windows Geräteportal Kioskmodus **aus.**

1. Wählen **Sie Kioskmodus aktivieren** aus, wählen Sie eine App aus, die beim Starten des Geräts ausgeführt werden soll, und wählen Sie dann Speichern **aus.**

    ![Kioskmodus](images/kiosk.png)
1. Starten Sie HoloLens. Wenn Die Seite Geräteportal geöffnet ist, können  Sie oben auf der Seite neu starten auswählen.

> [!NOTE]
> Der Kioskmodus kann über die REST-API von Geräteportal festgelegt werden, indem post to /api/holographic/kioskmode/settings mit einem erforderlichen Abfragezeichenfolgenparameter ("kioskModeEnabled&quot; mit dem Wert &quot;true&quot; oder &quot;false") und einem optionalen Parameter ("startupApp" mit einem Wert eines Paketnamens) ausgeführt wird. Beachten Sie, dass Geräteportal nur für Entwickler vorgesehen ist und nicht auf Nicht-Entwicklergeräten aktiviert werden sollte. Die REST-API kann sich in zukünftigen Updates/Releases ändern.

## <a name="more-information"></a>Weitere Informationen

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Sehen Sie sich an, wie Sie einen Kiosk mithilfe eines Bereitstellungspakets konfigurieren.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Global zugewiesener Zugriff – Kioskmodus
- Reduzierte Identitätsverwaltung für Kiosk, indem die neue Kioskmethode aktiviert wird, die den Kioskmodus auf Systemebene verwendet.

Mit diesem neuen Feature kann ein IT-Administrator ein HoloLens 2-Gerät für den Kioskmodus für mehrere Apps konfigurieren, der auf Systemebene anwendbar ist, keine Affinität mit einer Identität im System auft und für alle Benutzer gilt, die sich am Gerät befinden. Weitere Informationen [zu HoloLens neuen Funktion](hololens-global-assigned-access-kiosk.md) finden Sie in der Dokumentation zum Kiosk mit global zugewiesenem Zugriff.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Automatischer Start einer Anwendung im Kioskmodus mit mehreren Apps 
- Fokussierte Erfahrung mit dem automatischen App-Start, die die Auswahl von Benutzeroberfläche und App für Kioskmodus-Benutzeroberflächen weiter erhöht.

Gilt nur für den Kioskmodus mit mehreren Apps, und nur eine App kann mithilfe des hervorgehobenen Attributs unten in der Konfiguration zugewiesener Zugriff für den automatischen Start festgelegt werden. 

Die Anwendung wird automatisch gestartet, wenn sich der Benutzer anmeldet. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Verhaltensänderungen im Kioskmodus für die Behandlung von Fehlern
Wenn beim Anwenden des Kioskmodus Fehler auftreten, wird das folgende Verhalten angezeigt:

- Vor der Windows Holographic zeigt Version 20H2 – HoloLens alle Anwendungen in der Startmenü.
- Windows Holographic, Version 20H2: Wenn ein Gerät über eine Kioskkonfiguration verfügt, bei der es sich um eine Kombination aus global zugewiesenem Zugriff und zugewiesenem Zugriff für AAD-Gruppenmitglied handelt, wird dem Benutzer im Menü "Im Startmenü wird nichts angezeigt" angezeigt, wenn die Bestimmung der AAD-Gruppenmitgliedschaft fehlschlägt.

![Abbildung des Kioskmodus, der jetzt aussieht, wenn ein Fehler auftritt.](images/hololens-kiosk-failure-behavior.png )


- Ab Windows [Holographic, Version 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)sucht der Kioskmodus nach Global Assigned Access, bevor ein leeres Startmenü angezeigt wird. Die Kioskerfahrung wird bei Ausfällen im Kioskmodus der AAD-Gruppe auf eine globale Kioskkonfiguration (falls vorhanden) umgeschaltet.

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Cache Azure AD Gruppenmitgliedschaft für Offlinekiosk

- Sichererer Kioskmodus, indem verfügbare Apps bei Fehlern im Kioskmodus beseitigt werden.
- Aktivierte Offlinekiosks, die bis zu Azure AD 60 Tage lang mit Gruppen verwendet werden können.

Diese Richtlinie steuert, wie viele Tage Azure AD Gruppenmitgliedschaftscache für Konfigurationen des zugewiesenen Zugriffs verwendet werden darf, die auf Azure AD gruppen für angemeldete Benutzer abzielen. Sobald dieser Richtlinienwert auf einen Wert größer als 0 festgelegt ist, wird der Cache andernfalls nicht verwendet.  

Name: AADGroupMembershipCacheValidityInDays-URI-Wert: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min– 0 Tage  
Max– 60 Tage 

Schritte zur ordnungsgemäßen Verwendung dieser Richtlinie: 
1. Erstellen Sie ein Gerätekonfigurationsprofil für Kiosk-Azure AD Gruppen, und weisen Sie es HoloLens Geräten zu. 
1. Erstellen Sie eine benutzerdefinierte OMA-URI-basierte Gerätekonfiguration, die diesen Richtlinienwert auf die gewünschte Anzahl von Tagen (> 0) legt und sie HoloLens Geräten zu. 
    1. Der URI-Wert sollte im Textfeld OMA-URI als ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays eingegeben werden.
    1. Der Wert kann zwischen min und max zulässig sein.
1. Registrieren HoloLens Geräte und Überprüfen, ob beide Konfigurationen auf das Gerät angewendet werden. 
1. Lassen Azure AD Benutzer 1 anmelden, wenn das Internet verfügbar ist. Sobald sich der Benutzer anmeldet und Azure AD die Gruppenmitgliedschaft bestätigt wurde, wird der Cache erstellt. 
1. Nun Azure AD Benutzer 1 HoloLens offline schalten und für den Kioskmodus verwenden, solange der Richtlinienwert X Tage zulässt. 
1. Die Schritte 4 und 5 können für alle anderen Azure AD-Benutzer N wiederholt werden. Der wichtigste Punkt hierbei ist, dass sich jeder Azure AD-Benutzer über das Internet bei dem Gerät anmelden muss. So können wir mindestens einmal feststellen, dass er Mitglied der Azure AD-Gruppe ist, für die die Kioskkonfiguration bestimmt wird. 
 
> [!NOTE]
> Bis Schritt 4 für einen Benutzer ausgeführt Azure AD in "getrennten" Umgebungen ein Fehlerverhalten angezeigt. 


## <a name="xml-kiosk-code-samples-for-hololens"></a>XML Kiosk Code Samples for HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Mehrere App-Kioskmodus für eine Azure AD Gruppe. 
Dieser Kiosk stellt einen Kiosk für Benutzer in der Azure AD-Gruppe zur Verfügung, für die ein Kiosk aktiviert ist, der die drei Apps Einstellungen, Remote Assist und Feedback-Hub. Um dieses Beispiel so zu ändern, dass es sofort verwendet wird, stellen Sie sicher, dass Sie die unten hervorgehobene GUID so ändern, dass sie einer eigenen Azure AD-Gruppe gleicht. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Mehrere App-Kioskmodus für Azure AD Konto.
Dieser Kiosk stellt einen Kiosk für einen einzelnen Benutzer zur Verfügung. Er verfügt über einen Kiosk, der die drei Apps enthält: Einstellungen, Remote Assist und Feedback-Hub. Um dieses Beispiel so zu ändern, dass es sofort verwendet wird, stellen Sie sicher, dass Sie das unten hervorgehobene Konto so ändern, dass es Azure AD ihrem eigenen Konto abgleicht. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

