---
title: Einrichten von HoloLens als Kiosk
description: Verwenden Sie eine Kiosk-Konfiguration, um die apps auf HoloLens zu sperren.
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
ms.openlocfilehash: f560dae725cbce8658bdf2a135c5061b5332f797
ms.sourcegitcommit: 456a88907d606f4c4532b153d5a848e214b6b8e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "11182006"
---
# Einrichten von HoloLens als Kiosk

Sie können ein HoloLens-Gerät so konfigurieren, dass es als ein Gerät mit festem Zweck, auch als *Kiosk*bezeichnet, funktioniert, indem Sie das Gerät so konfigurieren, dass es im Kioskmodus ausgeführt wird. Der Kiosk Modus schränkt die auf dem Gerät verfügbaren Anwendungen (oder Benutzer) ein. Der Kiosk Modus ist eine nützliche Funktion, mit der Sie einem HoloLens-Gerät Geschäfts-apps widmen oder das HoloLens-Gerät in einer APP-Demo verwenden können.

Dieser Artikel enthält Informationen zu Aspekten der Kiosk Konfiguration, die für HoloLens-gerätespezifisch sind. Allgemeine Informationen zu den unterschiedlichen Typen von Windows-basierten Kiosken und deren Konfiguration finden Sie unter [Konfigurieren von Kiosken und digitalen Signalen auf Windows-Desktop-Editionen](https://docs.microsoft.com/windows/configuration/kiosk-methods).  

> [!IMPORTANT]  
> Im Kiosk Modus wird festgelegt, welche apps verfügbar sind, wenn sich ein Benutzer am Gerät anmeldet. Der Kioskmodus ist jedoch keine Sicherheitsmethode. Es wird nicht verhindert, dass eine APP, die nicht erlaubt ist, eine andere APP öffnen kann. Um apps oder Prozesse beim Öffnen zu blockieren, verwenden Sie [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) , um geeignete Richtlinien zu erstellen.
>
> Weitere Informationen zu den Microsoft-Diensten, um Benutzern eine erweiterte Sicherheitsstufe zur Verfügung zu stellen, die von HoloLens 2 verwendet wird, finden Sie weitere Informationen über den [Schutz von Zustands Trennungen und Isolierungs Verteidigern](security-state-separation-isolation.md#defender-protections). Oder erfahren Sie, wie Sie [WDAC und Windows PowerShell verwenden, um apps auf HoloLens 2-Geräten mit Microsoft InTune zuzulassen oder zu blockieren](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Sie können den Kioskmodus entweder in einer einzelnen APP-oder in einer Multi-App-Konfiguration verwenden, und Sie können einen von drei Prozessen zum Einrichten und Bereitstellen der Kiosk Konfiguration verwenden.

> [!IMPORTANT]  
> Durch das Löschen der Konfiguration mit mehreren apps werden die Benutzer Sperrungs Profile entfernt, die vom Feature zugewiesene Zugriffsrechte erstellt wurden. Allerdings werden nicht alle Richtlinienänderungen zurückgesetzt. Wenn Sie diese Richtlinien wiederherstellen möchten, müssen Sie das Gerät auf die Werkseinstellungen zurücksetzen.

## Planen der Kiosk Bereitstellung

Bei der Planung Ihres Kiosks müssen Sie in der Lage sein, die folgenden Fragen zu beantworten. Hier sind einige Entscheidungen, die Sie beim Lesen dieser Seite und einige Überlegungen zu diesen Fragen berücksichtigen sollten.
1. **Wer wird Ihren Kiosk nutzen, und welche [Art von Konto (n)](hololens-identity.md) werden Sie verwenden?** Dies ist eine Entscheidung, die Sie wahrscheinlich bereits getroffen haben und die nicht um Ihres Kiosks Willen angepasst werden sollte, sondern sich auf die spätere Zuweisung des Kiosks auswirkt.
1. **Müssen Sie entweder unterschiedliche Kioske pro Nutzer/Gruppe oder ein Kiosk für einige nicht aktiviert haben?** Wenn dies der Fall ist, sollten Sie Ihren Kiosk über XML erstellen. 
1. **Wie viele apps sind in Ihrem Kiosk zu finden?** Wenn Sie über mehr als eine APP verfügen, benötigen Sie einen Kiosk mit mehreren apps. 
1. **Welche app (s) befindet sich in Ihrem Kiosk?** Bitte verwenden Sie die unten aufgeführte Anwendungs-Liste, um zusätzlich zu ihren eigenen In-Box-apps hinzuzufügen.
1. **Wie planen Sie die Bereitstellung Ihres Kiosks?** Wenn Sie Device in MDM registrieren, empfehlen wir die Verwendung von MDM zur Bereitstellung Ihres Kiosks. Wenn Sie MDM nicht verwenden, steht die Bereitstellung mit Bereitstellungspaket zur Verfügung.  

### Anforderungen für den Kiosk Modus

Sie können ein beliebiges HoloLens 2-Gerät für die Verwendung des Kioskmodus konfigurieren.

> [!IMPORTANT]
> Der Kiosk Modus ist nur verfügbar, wenn das Gerät Windows holographisch für Unternehmen aufweist. Alle HoloLens 2-Geräte werden mit Windows holographisch für Unternehmen ausgeliefert, und es gibt keine anderen Editionen. Auf jedem HoloLens 2-Gerät kann der Kiosk-Modus ausgeführt werden.
>
> HoloLens (1st Gen)-Geräte müssen sowohl in Bezug auf den Betriebssystem-Build als auch die OS-Edition aktualisiert werden. Hier finden Sie weitere Informationen zum Aktualisieren einer HoloLens (1st Generation) auf [Windows holographische for Business](hololens1-upgrade-enterprise.md) Edition. Wenn Sie ein HoloLens-Gerät (1st Generation) für die Verwendung des Kioskmodus aktualisieren möchten, müssen Sie zuerst sicherstellen, dass auf dem Gerät Windows 10, Version 1803 oder eine neuere Version ausgeführt wird. Wenn Sie das Windows Device Recovery-Tool zum Wiederherstellen Ihres HoloLens-Geräts (1st Generation) mit dem standardmäßigen Build verwendet haben oder wenn Sie die neuesten Updates installiert haben, ist Ihr Gerät für die Konfiguration bereit.

> [!IMPORTANT]  
> Zum Schutz von Geräten, die im Kioskmodus ausgeführt werden, sollten Sie Geräteverwaltungsrichtlinien hinzufügen, die Features wie USB-Konnektivität deaktivieren. Überprüfen Sie außerdem die Einstellungen für den Update Ring, um sicherzustellen, dass die automatischen Updates während der Geschäftszeiten nicht erfolgen.

### Entscheiden zwischen einem Single-App-Kiosk oder einem Multi-App-Kiosk

Mit einem einzelnen App-Kiosk wird die angegebene App gestartet, wenn sich der Benutzer beim Gerät anmeldet. Das Startmenü ist deaktiviert, ebenso wie Cortana. Ein HoloLens 2-Gerät reagiert nicht auf die [Start](hololens2-basic-usage.md#start-gesture) Geste. Ein HoloLens (1st Generation)-Gerät reagiert nicht auf die [Bloom](hololens1-basic-usage.md) -Geste. Da nur eine app ausgeführt werden kann, kann der Benutzer keine anderen apps platzieren.

Ein Multi-App-Kiosk zeigt das Startmenü an, wenn sich der Benutzer beim Gerät anmeldet. Die Kiosk-Konfiguration bestimmt, welche apps im Startmenü zur Verfügung stehen. Sie können einen Kiosk mit mehreren Apps verwenden, um Benutzern eine leicht verständliche Benutzeroberfläche zu bieten, indem Sie Ihnen nur die Dinge präsentieren, die Sie verwenden müssen, und die Dinge entfernen, die Sie nicht verwenden müssen.

In der folgenden Tabelle sind die Funktions Funktionen in den verschiedenen Kiosk Modi aufgeführt.

| &nbsp; |Startmenü |Menü ' schnell Aktionen ' |Kamera und Video |Miracast |Cortana |Integrierte Sprachbefehle |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|Single-App-Kiosk |Deaktiviert |Deaktiviert   |Deaktiviert |Deaktiviert   |Deaktiviert |Aktiviert <sup> 1</sup> |
|Multi-App-Kiosk |Aktiviert |Aktiviert <sup> 2</sup> |Verfügbar <sup> 2</sup> |Verfügbar <sup> 2</sup> |Verfügbar <sup> 2, 3</sup>  |Aktiviert <sup> 1</sup> |

> <sup>1 </sup> Sprachbefehle, die sich auf deaktivierte Funktionen beziehen, funktionieren nicht.  
> <sup>2 weitere </sup> Informationen zum Konfigurieren dieser Features finden Sie unter Auswählen von [Kiosk-apps](#plan-kiosk-apps).  
> <sup>3 </sup> auch wenn Cortana deaktiviert ist, sind die integrierten Sprachbefehle aktiviert.

In der folgenden Tabelle sind die Benutzer Unterstützungsfunktionen der verschiedenen Kiosk Modi aufgeführt.

| &nbsp; |Unterstützte Benutzertypen | Automatische Anmeldung | Mehrere Zugriffsebenen |
| --- | --- | --- | --- |
|Single-App-Kiosk |Verwaltetes Dienstkonto (MSA) in Azure Active Directory (AAD) oder lokales Konto |Ja |Nein |
|Multi-App-Kiosk |Aad-Konto |Nein |Ja |

Beispiele für die Verwendung dieser Funktionen finden Sie in der folgenden Tabelle.

|Verwenden Sie einen Single-App-Kiosk für: |Verwenden Sie einen Multi-App-Kiosk für: |
| --- | --- |
|Ein Gerät, auf dem nur ein Dynamics 365-Leitfaden für neue Mitarbeiter ausgeführt wird. |Ein Gerät, das sowohl Führungslinien als auch Remote Unterstützung für eine Reihe von Mitarbeitern ausführt. |
|Ein Gerät, auf dem nur eine benutzerdefinierte app ausgeführt wird. |Ein Gerät, das für die meisten Benutzer als Kiosk fungiert (nur eine benutzerdefinierte App ausführt), aber als Standardgerät für eine bestimmte Benutzergruppe fungiert. |

### Planen von Kiosk-apps

Allgemeine Informationen dazu, wie Sie Kiosk-apps auswählen können, finden Sie unter [Richtlinien für das Auswählen einer APP für zugewiesenen Zugriff (Kioskmodus)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).

Wenn Sie das Windows-Geräte Portal verwenden, um einen einzelnen App-Kiosk zu konfigurieren, wählen Sie die APP während des Setupvorgangs aus.  

Wenn Sie ein MDM-System (Mobile Device Management) oder ein Bereitstellungspaket zum Konfigurieren des Kioskmodus verwenden, verwenden Sie den [AssignedAccess-Konfigurationsdienstanbieter (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) , um Anwendungen anzugeben. Der CSP verwendet [Anwendungsbenutzer Modell-IDs (Anwendungs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) , um Anwendungen zu identifizieren. In der folgenden Tabelle sind die Anwendungs einiger in-Box-Anwendungen aufgeführt, die Sie in einem Kiosk mit mehreren Apps verwenden können.

> [!IMPORTANT]
> Im Kiosk Modus wird festgelegt, welche apps verfügbar sind, wenn sich ein Benutzer am Gerät anmeldet. Der Kioskmodus ist jedoch keine Sicherheitsmethode. Es wird nicht verhindert, dass eine APP, die nicht erlaubt ist, eine andere APP öffnen kann. Da wir dieses Verhalten nicht einschränken, können apps weiterhin über Edge, den Datei-Explorer und die Microsoft Store-Apps gestartet werden. Wenn bestimmte apps nicht von einem Kiosk aus gestartet werden sollen, verwenden Sie [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) , um geeignete Richtlinien zu erstellen. 
> 
> Darüber hinaus kann das "Mixed Reality Home" nicht als Kiosk-App eingerichtet werden.

<a id="aumids"></a>

|App-Name |AUMID |
| --- | --- |
|3D-Viewer |Microsoft. Microsoft3DViewer \ _8wekyb3d8bbwe \! Microsoft. Microsoft3DViewer |
|Calendar |Microsoft. windowscommunicationsapps \ _8wekyb3d8bbwe \! Microsoft. Windows Live stürzen. Calendar |
|Kamera <sup> 1, 2</sup> |HoloCamera \ _cw5n1h2txyewy \! HoloCamera |
|Cortana <sup> 3</sup> |Microsoft. 549981C3F5F10 \ _8wekyb3d8bbwe \! App |
|Geräteauswahl auf HoloLens (1st Generation) |HoloDevicesFlow \ _cw5n1h2txyewy \! HoloDevicesFlow |
|Geräteauswahl auf HoloLens 2 |Microsoft. Windows. DevicesFlowHost \ _cw5n1h2txyewy \! Microsoft. Windows. DevicesFlowHost |
|Dynamics 365 Guides |Microsoft. Dynamics365. Guides \ _8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft. MicrosoftRemoteAssist \ _8wekyb3d8bbwe \! Microsoft. RemoteAssist |
|Feedback- &nbsp; Hub |Microsoft. WindowsFeedbackHub \ _8wekyb3d8bbwe \! App |
|Datei-Explorer |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|Mail |Microsoft.windowscommunicationsapps_8wekyb3d8bbwe! Microsoft. Windows Live stürzen. Mail |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast <sup> 4</sup> |&nbsp; |
|Filme & TV |Microsoft. ZuneVideo \ _8wekyb3d8bbwe \! Microsoft. ZuneVideo |
|OneDrive |Microsoft. microsoftskydrive \ _8wekyb3d8bbwe \! App |
|Fotos |Microsoft. Windows. Fotos \ _8wekyb3d8bbwe \! App |
|Einstellungen |HolographicSystemSettings \ _cw5n1h2txyewy \! App |
|Tipps |Microsoft. HoloLensTips \ _8wekyb3d8bbwe \! HoloLensTips |

> <sup>1 </sup> um die Foto-oder Videoaufnahme zu aktivieren, müssen Sie die Kamera-APP als Kiosk-App aktivieren.  
> <sup>2 </sup> Wenn Sie die Kamera-APP aktivieren, beachten Sie die folgenden Bedingungen:
> - Das Menü "schnelle Aktionen" enthält die Schaltflächen "Foto" und "Video".  
> - Sie sollten auch eine APP (beispielsweise Fotos, e-Mail oder OneDrive) aktivieren, die mit Bildern interagieren oder Bilder abrufen kann.  
>  
> <sup>3 </sup> auch wenn Sie Cortana nicht als Kiosk-App aktivieren, sind integrierte Sprachbefehle aktiviert. Befehle, die mit deaktivierten Features verknüpft sind, haben jedoch keine Auswirkungen.  
> <sup>4 </sup> Sie können Miracast nicht direkt aktivieren. Aktivieren Sie die Kamera-APP und die Geräteauswahl-APP, um Miracast als Kiosk-APP zu aktivieren.

### Planen von Kiosk Profilen für Benutzer oder Gruppen

Wenn Sie entweder die XML-Datei erstellen oder die Benutzeroberfläche von InTune verwenden, um einen Kiosk einzurichten, müssen Sie berücksichtigen, wer der Kiosk sein soll. Eine Kiosk Konfiguration kann auf ein einzelnes Konto oder auf Azure AD Groups begrenzt werden. 

In der Regel sind Kioske entweder für einen Benutzer oder eine Benutzergruppe aktiviert. Wenn Sie jedoch beabsichtigen, ihren eigenen XML-Kiosk zu schreiben, sollten Sie möglicherweise den Global zugewiesenen Zugriff in Frage stellen, in dem der Kiosk unabhängig von der Identität auf Geräteebene angewendet wird. Wenn Ihnen dies gefällt, [Lesen Sie mehr über global zugewiesene Access-Kioske.](hololens-global-assigned-access-kiosk.md)

#### Wenn Sie eine XML-Datei erstellen:
-   Sie erstellen viele verschiedene Kiosk-Profile und weisen diese einzelnen Benutzern/Gruppen zu. Wie einen Kiosk für Ihre Aad-Gruppe, der viele apps enthält, und einen Besucher, der über einen mehr-App-Kiosk mit einer einmaligen App verfügt.
-   Ihre Kiosk-Konfiguration wird als **Profil-ID** bezeichnet und besitzt eine GUID.
-   Sie weisen dieses Profil im Abschnitt configs zu, indem Sie den Benutzertyp angeben und die gleiche GUID für die **DefaultProfile-ID**verwenden.
- Eine XML-Datei kann erstellt, aber weiterhin auf ein Gerät über MDM angewendet werden, indem ein benutzerdefiniertes Oma-URI-Geräte Konfigurationsprofil erstellt und auf die HoloLens-Gerätegruppe mit dem URI-Wert angewendet wird:./Device/Vendor/MSFT/AssignedAccess/Configuration

#### Wenn Sie einen Kiosk in InTune erstellen.
-   Jedes Gerät erhält möglicherweise nur ein einzelnes Kiosk-Profil, da es sonst zu einem Konflikt führt und überhaupt keine Kiosk-Konfigurationen mehr erhält. 
    -   Andere Arten von Profilen und Richtlinien, wie Geräteeinschränkungen, die nicht mit dem Kiosk-Konfigurationsprofil verknüpft sind, haben keinen Konflikt mit dem Kiosk-Konfigurationsprofil.
-   Der Kiosk wird für alle Benutzer aktiviert, die Teil des Benutzeranmelde Typs sind, der für einen Benutzer oder eine Aad-Gruppe eingerichtet wird. 
-   Nachdem die Kiosk Konfiguration eingestellt wurde und der **Benutzer Anmeldetyp** (Benutzer, die sich beim Kiosk anmelden können) und die apps ausgewählt sind, muss die Gerätekonfiguration weiterhin einer Gruppe zugewiesen werden. Die zugewiesene Gruppe (n) bestimmt, welche Geräte die Konfiguration des Kiosk Geräts empfangen, interagiert jedoch nicht mit, wenn der Kiosk aktiviert ist oder nicht. 
    - Eine vollständige Erläuterung der Auswirkungen der Zuweisung von Konfigurationsprofilen in InTune finden Sie unter [Zuweisen von Benutzer-und Geräteprofilen in Microsoft InTune](https://docs.microsoft.com/intune/configuration/device-profile-assign).

### Auswählen einer Bereitstellungsmethode

Sie können eine der folgenden Methoden zum Bereitstellen von Kiosk Konfigurationen auswählen:

- [Microsoft InTune oder anderer MDM-Dienst (Mobile Device Management)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Bereitstellungspaket](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Geräteportal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Da diese Methode erfordert, dass der Entwicklermodus auf dem Gerät aktiviert ist, empfehlen wir, Sie nur für Demos zu verwenden.

In der folgenden Tabelle sind die Funktionen und Vorteile der einzelnen Bereitstellungsmethoden aufgelistet.

| &nbsp; |Bereitstellen mithilfe des Windows Device Portals |Bereitstellen mithilfe eines Bereitstellungspakets |Bereitstellen mithilfe von MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Bereitstellen von Kiosken für einzelne apps   | Ja           | Ja                  | Ja  |
|Bereitstellen von Multi-App-Kiosken    | Nein            | Ja                  | Ja  |
|Nur auf lokalen Geräten bereitstellen | Ja           | Ja                  | Nein   |
|Bereitstellen mithilfe des Entwicklermodus |Erforderlich       | Nicht erforderlich            | Nicht erforderlich   |
|Bereitstellen mithilfe von Azure Active Directory (AAD)  | Nicht erforderlich            | Nicht erforderlich                   | Erforderlich  |
|Automatisches Bereitstellen      | Nein            | Nein                   | Ja  |
|Bereitstellungsgeschwindigkeit            | Fast       | Fast                 | Verzögerte Anzeige |
|Bereitstellen im Maßstab | Nicht empfohlen    | Empfohlen        | Empfohlen |

## Verwenden von Microsoft InTune oder einem anderen MDM zum Einrichten einer einzelnen APP oder eines Multi-App-Kiosks

Führen Sie die folgenden Schritte aus, um den Kioskmodus mithilfe von Microsoft InTune oder einem anderen MDM-System einzurichten.

1. [Bereiten Sie die Registrierung der Geräte vor](#mdmenroll).
1. [Erstellen Sie ein Kiosk-Konfigurationsprofil](#mdmprofile).
1. Konfigurieren Sie den Kiosk.
   - [Konfigurieren Sie die Einstellungen für einen einzelnen App-Kiosk](#mdmconfigsingle).
   - [Konfigurieren Sie die Einstellungen für einen Kiosk mit mehreren apps](#mdmconfigmulti).
1. [Weisen Sie das Kiosk-Konfigurationsprofil einer Gruppe zu](#mdmassign).
1. Stellen Sie die Geräte bereit.
   - [Bereitstellen eines Single-App-Kiosks](#mdmsingledeploy)
   - [Bereitstellen eines Multi-App-Kiosks](#mdmmultideploy)

### <a id="mdmenroll"></a>MDM, Schritt 1 &ndash; Vorbereiten der Registrierung der Geräte

Sie können Ihr MDM-System so konfigurieren, dass HoloLens-Geräte automatisch registriert werden, wenn sich der Benutzer zum ersten Mal anmeldet oder wenn Benutzer Geräte manuell registrieren. Die Geräte müssen ebenfalls mit ihrer Azure AD-Domäne verbunden und den entsprechenden Gruppen zugewiesen werden.

Weitere Informationen zum Registrieren der Geräte finden Sie unter Registrieren von [HoloLens in MDM](hololens-enroll-mdm.md) -und [InTune-Registrierungsmethoden für Windows-Geräte](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).

### <a id="mdmprofile"></a>MDM, Schritt 2: &ndash; Erstellen eines Kiosk-Konfigurationsprofils

1. Öffnen Sie das [Azure](https://portal.azure.com/) -Portal, und registrieren Sie sich bei Ihrem InTune-Administratorkonto.
1. Wählen Sie **Microsoft InTune**  >  **Device Configuration (Profile**  >  **Create profile**) aus.
1. Geben Sie einen Profilnamen ein.
1. Wählen Sie **Platform**  >  **Windows 10 und höher**aus, und wählen Sie dann **Profiltyp**-  > **Geräteeinschränkungen**aus.
1. Wählen **Configure**Sie  >  **Kiosk**konfigurieren aus, und wählen Sie dann eine der folgenden Optionen aus:
   - Zum Erstellen eines Single-App-Kiosks wählen Sie **Kioskmodus**  >  **Single-App Kiosk**aus.
   - Zum Erstellen eines Multi-App-Kiosks wählen Sie **Kioskmodus**  >  **-Multi-App-Kiosk**aus.
1. Um mit der Konfiguration des Kiosks zu beginnen, wählen Sie **Hinzufügen**aus.

Die nächsten Schritte unterscheiden sich je nach Art des gewünschten Kiosks. Wenn Sie weitere Informationen wünschen, wählen Sie eine der folgenden Optionen aus:  

- [Single-App-Kiosk](#mdmconfigsingle)
- [Multi-App-Kiosk](#mdmconfigmulti)

Weitere Informationen dazu, wie Sie ein Kiosk-Konfigurationsprofil erstellen, finden Sie unter [Windows 10 und Windows holographische Geräteeinstellungen für Unternehmen, die mithilfe von InTune als dedizierter Kiosk ausgeführt](https://docs.microsoft.com/intune/configuration/kiosk-settings)werden können.

### <a id="mdmconfigsingle"></a>MDM, Schritt 3 (Single-APP) &ndash;  Konfigurieren der Einstellungen für einen einzelnen App-Kiosk

In diesem Abschnitt werden die Einstellungen zusammengefasst, die für einen einzelnen App-Kiosk erforderlich sind. Weitere Informationen finden Sie in den folgenden Artikeln:

- Informationen dazu, wie Sie ein Kiosk-Konfigurationsprofil in InTune konfigurieren, finden Sie unter [Konfigurieren des Kioskmodus mit Microsoft InTune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Weitere Informationen zu den verfügbaren Einstellungen für Single-App-Kioske in InTune finden Sie unter [einzelne APP-Kioske im Vollbildmodus](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks) .
- Weitere MDM-Dienste finden Sie in der Dokumentation Ihres Anbieters. Wenn Sie eine benutzerdefinierte XML-Konfiguration verwenden müssen, um einen Kiosk in Ihrem MDM-Dienst einzurichten, [Erstellen Sie eine XML-Datei, die die Kiosk Konfiguration definiert](#ppkioskconfig).

1. Wählen Sie **Benutzer Anmeldetyp**  >  **Lokales Benutzerkonto**aus, und geben Sie dann den Benutzernamen des lokalen (Geräte-) Kontos oder des Microsoft-Kontos (MSA) ein, das sich beim Kiosk anmelden kann.
   > [!NOTE]  
   > Die Typen von **Autologon** -Benutzerkonten werden in Windows holographisch für Unternehmen nicht unterstützt.
1. Wählen **Application type**Sie  >  **App**-Typ Store-App aus, und wählen Sie dann in der Liste eine APP aus.

Der nächste Schritt besteht darin, das Profil einer Gruppe [zuzuweisen](#mdmassign) .

### <a id="mdmconfigmulti"></a>MDM, Schritt 3 (Multi-APP) &ndash; Konfigurieren der Einstellungen für einen Multi-App-Kiosk

In diesem Abschnitt werden die Einstellungen zusammengefasst, die ein Multi-App-Kiosk erfordert. Ausführlichere Informationen finden Sie in den folgenden Artikeln:

- Informationen dazu, wie Sie ein Kiosk-Konfigurationsprofil in InTune konfigurieren, finden Sie unter [Konfigurieren des Kioskmodus mit Microsoft InTune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Weitere Informationen zu den verfügbaren Einstellungen für Multi-App-Kioske in InTune finden Sie unter [Multi-App-Kioske](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Weitere MDM-Dienste finden Sie in der Dokumentation Ihres Anbieters. Wenn Sie eine benutzerdefinierte XML-Konfiguration verwenden müssen, um einen Kiosk in Ihrem MDM-Dienst einzurichten, [Erstellen Sie eine XML-Datei, die die Kiosk Konfiguration definiert](#ppkioskconfig). Wenn Sie eine XML-Datei verwenden, stellen Sie sicher, dass Sie das [Start Layout](#start-layout-for-hololens)einbeziehen.  
- Optional können Sie ein benutzerdefiniertes Start Layout für InTune oder andere MDM-Dienste verwenden. Weitere Informationen finden Sie unter [Starten der Layoutdatei für MDM (InTune und andere)](#start-layout-file-for-mdm-intune-and-others).

1. Wählen Sie **Windows 10 im S-Modus für Geräte**  >  **Nein**aus.  
   >[!NOTE]  
   > Der S-Modus wird für Windows holographische for Business nicht unterstützt.
1. Wählen Sie **Benutzer Anmeldetyp**  >  **Azure AD-Benutzer oder-Gruppe** oder **Benutzer Anmeldetyp**  >  **HoloLens-Besucher**aus, und fügen Sie dann eine oder mehrere Benutzergruppen oder-Konten hinzu.  

   Nur Benutzer, die zu den Gruppen oder Konten gehören, die Sie in der **Benutzer Anmeldeart** angeben, können die Funktionalität des Kiosks nutzen.

1. Wählen Sie eine oder mehrere Apps mithilfe der folgenden Optionen aus:
   - Wenn Sie eine hochgeladene Branchen-app hinzufügen möchten, wählen Sie **Store-App hinzufügen** und dann die gewünschte App aus.
   - Wenn Sie eine APP durch Angabe Ihres AUMID hinzufügen möchten, wählen Sie **Add by AUMID** aus, und geben Sie dann den AUMID der APP ein. [Anzeigen der Liste der verfügbaren Anwendungs](#aumids)

Der nächste Schritt besteht darin, das Profil einer Gruppe [zuzuweisen](#mdmassign) .

### <a id="mdmassign"></a>MDM, Schritt 4 &ndash; Zuweisen des Kiosk-Konfigurationsprofils zu einer Gruppe

Auf der Seite " **Aufgaben** " des Kiosk-Konfigurationsprofils können Sie bestimmen, wo die Kiosk-Konfiguration bereitgestellt werden soll. Im einfachsten Fall weisen Sie das Kiosk-Konfigurationsprofil einer Gruppe zu, die das HoloLens-Gerät enthält, wenn das Gerät in MDM registriert wird.

### <a id="mdmsingledeploy"></a>MDM, Schritt 5 (Single-APP) &ndash; Bereitstellen eines Single-App-Kiosks

Wenn Sie ein MDM-System verwenden, können Sie das Gerät in MDM während OOBE registrieren. Nachdem OOBE abgeschlossen ist, ist das Anmelden auf dem Gerät einfach.

Führen Sie während OOBE die folgenden Schritte aus:

1. Anmelden mit dem Konto, das Sie im Kiosk-Konfigurationsprofil angegeben haben.
1. Registrieren Sie das Gerät. Stellen Sie sicher, dass das Gerät der Gruppe hinzugefügt wird, der das Kiosk-Konfigurationsprofil zugewiesen ist.
1. Warten Sie, bis OOBE beendet wird, damit die Store-App heruntergeladen und installiert werden kann und Richtlinien angewendet werden. Starten Sie dann das Gerät neu.

Wenn Sie sich das nächste Mal beim Gerät anmelden, sollte die Kiosk-App automatisch gestartet werden.

Wenn Ihre Kiosk-Konfiguration zu diesem Zeitpunkt nicht angezeigt wird, [Überprüfen Sie den Zuordnungsstatus](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

### <a id="mdmmultideploy"></a>MDM, Schritt 5 (Multi-APP) &ndash; Bereitstellen eines Multi-App-Kiosks

Wenn Sie ein MDM-System verwenden, können Sie das Gerät an Ihren Azure AD-Mandanten anschließen und das Gerät während OOBE in MDM registrieren. Geben Sie bei Bedarf die Registrierungsinformationen für die Benutzer an, damit Sie während des OOBE-Prozesses zur Verfügung stehen.

> [!NOTE]  
> Wenn Sie das Kiosk-Konfigurationsprofil einer Gruppe zugeordnet haben, die Benutzer enthält, stellen Sie sicher, dass eines dieser Benutzerkonten das erste Konto ist, das sich beim Gerät anmeldet.

Führen Sie während OOBE die folgenden Schritte aus:

1. Melden Sie sich mit dem Konto an, das zur Gruppe der **Benutzeranmelde Typen** gehört.
1. Registrieren Sie das Gerät.
1. Warten Sie, bis alle apps, die Teil des Kiosk-Konfigurationsprofils sind, heruntergeladen und installiert werden. Warten Sie auch, bis Richtlinien angewendet werden.  
1. Nachdem OOBE beendet wurde, können Sie weitere Apps aus dem Microsoft Store oder von Sideloading installieren. [Erforderliche apps](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) für die Gruppe, zu der das Gerät gehört, wird automatisch installiert.
1. Nachdem die Installation abgeschlossen ist, starten Sie das Gerät neu.

Wenn Sie sich das nächste Mal mit einem Konto, das zum **Anmeldetyp des Benutzers**gehört, beim Gerät anmelden, sollte die Kiosk-App automatisch gestartet werden.

Wenn Ihre Kiosk-Konfiguration zu diesem Zeitpunkt nicht angezeigt wird, [Überprüfen Sie den Zuordnungsstatus](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

## Verwenden eines Bereitstellungspakets zum Einrichten einer einzelnen APP oder eines Multi-App-Kiosks

Führen Sie die folgenden Schritte aus, um den Kioskmodus mithilfe eines Bereitstellungspakets einzurichten.

1. [Erstellen Sie eine XML-Datei, die die Kiosk Konfiguration definiert](#ppkioskconfig), einschließlich eines [Start Layouts](#start-layout-for-hololens).
2. [Fügen Sie die XML-Datei zu einem Bereitstellungspaket hinzu.](#ppconfigadd)
3. [Wenden Sie das Bereitstellungspaket auf HoloLens an.](#ppapply)

### <a id="ppkioskconfig"></a>Bereitstellungspaket, Schritt 1 &ndash; Erstellen einer XML-Datei für die Kiosk-Konfiguration

Befolgen Sie [die allgemeinen Anweisungen zum Erstellen einer XML-Datei für die Kiosk-Konfiguration für Windows Desktop](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), mit Ausnahme der folgenden:

- Schließen Sie keine klassischen Windows-Anwendungen (Win32) ein. HoloLens unterstützt diese Anwendungen nicht.
- Verwenden Sie den [Platzhalter Start Layout XML](#start-layout-for-hololens) für HoloLens.
- Optional: Gastzugriff auf die Kiosk-Konfiguration hinzufügen

#### <a id="ppkioskguest"></a>Optional: Gastzugriff auf die Kiosk-Konfiguration hinzufügen

Im Abschnitt [ **configs** der XML-Datei](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)können Sie eine spezielle Gruppe mit dem Namen " **Besucher** " konfigurieren, um den Gästen die Verwendung des Kiosks zu ermöglichen. Wenn der Kiosk so konfiguriert ist, dass er die spezielle Gruppe " **Besucher** " unterstützt, wird der Anmeldeseite eine Option "**Gast**" hinzugefügt. Das **Gastkonto erfordert** kein Kennwort, und alle Daten, die dem Konto zugeordnet sind, werden gelöscht, wenn sich das Konto abmeldet.

Zum Aktivieren des **Gastkontos** fügen Sie den folgenden Codeausschnitt zu Ihrem Kiosk-Konfigurations-XML hinzu:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a>Platzhalter Anfangslayout für HoloLens

Wenn Sie ein [Bereitstellungspaket](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) zum Konfigurieren eines Multi-App-Kiosks verwenden, ist für das Verfahren ein Start Layout erforderlich. Die Anpassung des Start Layouts wird in Windows holographisch für Unternehmen nicht unterstützt. Daher müssen Sie ein Platzhalter Anfangslayout verwenden.

> [!NOTE]  
> Da ein Single-App-Kiosk die Kiosk-App startet, wenn sich ein Benutzer anmeldet, wird kein Startmenü verwendet, und es muss kein Start Layout vorhanden sein.

> [!NOTE]  
> Wenn Sie [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) zum Einrichten eines Multi-App-Kiosks verwenden, können Sie optional ein Start Layout verwenden. Weitere Informationen finden Sie unter [Layoutdatei für den Platzhalter Anfang für MDM (InTune und andere)](#start-layout-file-for-mdm-intune-and-others).

Fügen Sie für das Start Layout den folgenden **StartLayout** -Abschnitt zur Bereitstellungs-XML-Datei von Kiosk hinzu:

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

#### <a id="start-layout-file-for-mdm-intune-and-others"></a>Platzhalter-Start-Layoutdatei für MDM (InTune und andere)

Speichern Sie das folgende Beispiel als XML-Datei. Sie können diese Datei verwenden, wenn Sie den Multi-App-Kiosk in Microsoft InTune konfigurieren (oder in einem anderen MDM-Dienst, der ein Kiosk-Profil bereitstellt).

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Einstellung und eine vollständige XML-Konfiguration verwenden müssen, um einen Kiosk in Ihrem MDM-Dienst einzurichten, verwenden Sie die [Anweisungen zum Starten des Layouts für ein Bereitstellungspaket](#start-layout-for-hololens).

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

### <a id="ppconfigadd"></a>Prov. Paket, Schritt 2: &ndash; Hinzufügen der XML-Datei für die Kiosk-Konfiguration zu einem Bereitstellungspaket

1. Öffnen Sie den [Windows-Konfigurations-Designer](https://www.microsoft.com/store/apps/9nblggh4tx22).
1. Wählen Sie **Erweiterte Bereitstellung**aus, geben Sie einen Namen für Ihr Projekt ein, und wählen Sie dann **weiter**aus.
1. Wählen Sie **Windows 10 holographisch**aus, und wählen Sie dann **weiter**aus.
1. Wählen Sie **Fertig stellen**aus. Der Arbeitsbereich für Ihr Paket wird geöffnet.
1. Wählen Sie **Laufzeiteinstellungen**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**aus.
1. Wählen Sie im mittleren Bereich **Durchsuchen** aus, um die von Ihnen erstellte Kiosk-Konfigurationsdatei zu suchen und auszuwählen.

   ![Screenshot des Felds MultiAppAssignedAccessSettings im Windows-Konfigurations-Designer](./images/multiappassignedaccesssettings.png)

1. **Optional**. (Wenn Sie das Bereitstellungspaket nach der ersten Einrichtung des Geräts anwenden möchten und ein Administrator Benutzer bereits auf dem Kiosk Gerät verfügbar ist, überspringen Sie diesen Schritt.) Wählen Sie Benutzer der **Laufzeiteinstellungen** - &gt; **Konten** aus &gt; **Users**, und erstellen Sie dann ein Benutzerkonto. Geben Sie einen Benutzernamen und ein Kennwort ein, und wählen Sie dann **Benutzer**  >  **Gruppe-Administratoren**aus.  
  
     Mithilfe dieses Kontos können Sie den Bereitstellungsstatus und die Protokolle anzeigen.  
1. **Optional**. (Wenn Sie bereits über ein Konto ohne Administratorrechte auf dem Kiosk Gerät verfügen, überspringen Sie diesen Schritt.) Wählen Sie Benutzer der **Laufzeiteinstellungen** - &gt; **Konten** aus &gt; **Users**, und erstellen Sie dann ein lokales Benutzerkonto. Stellen Sie sicher, dass der Benutzername mit dem Konto identisch ist, das Sie im Konfigurations-XML angeben. Wählen Sie **Benutzer**  >  **gruppenstandard-Benutzer**aus.
1. Wählen Sie **Datei**  >  **Speichern**aus.
1. Wählen **Export**Sie  >  **Bereitstellungspaket**exportieren aus, und wählen Sie dann **Besitzer**  >  **IT-Administrator**aus. Dadurch wird die Rangfolge dieses Bereitstellungspakets höher als Bereitstellungspakete festgelegt, die auf dieses Gerät aus anderen Quellen angewendet werden.
1. Wählen Sie **Weiter** aus.
1. Wählen Sie auf der Seite **Bereitstellungspaket Sicherheit** eine Sicherheitsoption aus.
   > [!IMPORTANT]  
   > Wenn Sie **Paketsignierung aktivieren**auswählen, müssen Sie auch ein gültiges Zertifikat auswählen, das zum Signieren des Pakets verwendet werden soll. Wählen Sie dazu **Durchsuchen** aus, und wählen Sie das Zertifikat aus, das Sie zum Signieren des Pakets verwenden möchten.
   
   > [!CAUTION]  
   > Wählen Sie **Paketverschlüsselung nicht aktivieren**aus. Bei HoloLens-Geräten führt diese Einstellung zu einem Fehler bei der Bereitstellung.
1. Wählen Sie **Weiter** aus.
1. Geben Sie den Ausgabespeicherort an, an dem das Bereitstellungspaket nach dem Aufbau ablaufen soll. Standardmäßig verwendet der Windows-Konfigurations-Designer den Projektordner als Ausgabespeicherort. Wenn Sie den Ausgabespeicherort ändern möchten, wählen Sie **Durchsuchen**aus. Wenn Sie den Vorgang beenden, wählen Sie **weiter**aus.
1. Wählen Sie **Erstellen** aus, um mit dem Erstellen des Pakets zu beginnen. Die Erstellung eines Bereitstellungspakets dauert nicht lange. Auf der Seite "erstellen" werden die Projektinformationen angezeigt, und die Statusleiste zeigt den Buildstatus an.

### <a id="ppapply"></a>Bereitstellungspaket, Schritt 3 &ndash; Anwenden des Bereitstellungspakets auf HoloLens

Der Artikel "Konfigurieren der HoloLens mithilfe eines Bereitstellungspakets" enthält detaillierte Anweisungen zum Anwenden des Bereitstellungspakets unter den folgenden Bedingungen:

- Sie können [ein Bereitstellungspaket zunächst während des Setups auf HoloLens anwenden](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

- Sie können [ein Bereitstellungspaket auch nach dem Setup auf HoloLens anwenden](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup).

## Verwenden des Windows-Geräte Portals zum Einrichten eines Single-App-Kiosks

Führen Sie die folgenden Schritte aus, um den Kioskmodus mithilfe des Windows-Geräte Portals einzurichten.

1. [Einrichten des HoloLens-Geräts zur Verwendung des Windows-Geräte Portals](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal) Das Geräteportal ist ein Webserver auf der HoloLens, mit dem Sie über einen Webbrowser auf dem PC eine Verbindung herstellen können.

    > [!CAUTION]
    > Wenn Sie HoloLens für die Verwendung des Geräte Portals einrichten, müssen Sie den Entwicklermodus auf dem Gerät aktivieren. Der Entwicklermodus auf einem Gerät, das über Windows holographische for Business verfügt, ermöglicht Ihnen das Laden von apps mit der Seite. Mit dieser Einstellung wird jedoch das Risiko verursacht, dass Benutzer apps installieren können, die nicht vom Microsoft Store zertifiziert wurden. Administratoren können die Möglichkeit zum Aktivieren des Entwicklermodus mithilfe der **ApplicationManagement/AllowDeveloper-Einstellung Sperre** im [Richtlinien-CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)blockieren. [Weitere Informationen zum Entwicklermodus](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Stellen Sie auf einem Computer mithilfe von [WLAN](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) oder [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)eine Verbindung mit dem HoloLens her.

1. Führen Sie eine der folgenden Aktionen aus:
   - Wenn Sie zum ersten Mal eine Verbindung mit dem Windows-Geräte Portal herstellen, [Erstellen Sie einen Benutzernamen und ein Kennwort](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password) .
   - Geben Sie den Benutzernamen und das Kennwort ein, die Sie zuvor eingerichtet haben.

    > [!TIP]
    > Wenn ein Zertifikatfehler im Browser angezeigt wird, führen Sie [diese Schrittezur Problembehandlung](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate) aus.

1. Wählen Sie im Windows-Geräte Portal **Kiosk Modus**aus.

1. Wählen Sie **Kiosk Modus aktivieren**aus, wählen Sie eine APP aus, die beim Start des Geräts ausgeführt werden soll, und wählen Sie dann **Speichern**aus.

    ![Kioskmodus](images/kiosk.png)
1. Starten Sie HoloLens neu. Wenn Ihre Geräte Portal Seite weiterhin geöffnet ist, können Sie oben auf der Seite " **neu starten** " auswählen.

> [!NOTE]
> Der Kiosk Modus kann über die restliche API des Geräte Portals festgelegt werden, indem ein Beitrag zu/API/Holographic/kioskmode/Settings mit einem erforderlichen Abfragezeichenfolgenparameter ("kioskModeEnabled" mit dem Wert "true" oder "false") und einem optionalen Parameter ("startupApp" mit dem Wert eines Paket namens) ausgeführt wird. Beachten Sie bitte, dass Device Portal nur für Entwickler gedacht ist und nicht auf nicht-Entwickler Geräten aktiviert werden sollte. Die restliche API unterliegt Änderungen in zukünftigen Updates/Versionen.

## Weitere Informationen

### Schauen Sie sich an, wie Sie einen Kiosk mithilfe eines Bereitstellungspakets konfigurieren.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### Global zugewiesener Zugriff – Kiosk Modus
- Reduzierte Identitätsverwaltung für Kiosk durch Aktivieren der neuen Kiosk Methode, die den Kioskmodus auf Systemebene anwendet.

Diese neue Funktion ermöglicht es einem IT-Administrator, ein HoloLens 2-Gerät für den Multi-App-Kioskmodus zu konfigurieren, das auf Systemebene anwendbar ist, keine Affinität zu einer beliebigen Identität im System hat und für alle Personen gilt, die sich beim Gerät anmelden. Informieren Sie sich [hier](hololens-global-assigned-access-kiosk.md)ausführlich über dieses neue Feature.

### Automatischer Start einer Anwendung im Kioskmodus mit mehreren apps 
- Mit der automatischen App-Einführung wird die Benutzeroberfläche und die APP-Auswahl für die Erfahrungen im Kiosk Modus weiter verbessert.

Gilt nur für den Kioskmodus mit mehreren apps, und nur 1 App kann mithilfe des hervorgehobenen Attributs unten in zugewiesener Zugriffskonfiguration automatisch gestartet werden. 

Die Anwendung wird automatisch gestartet, wenn sich der Benutzer anmeldet. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### Verhaltensänderungen im Kiosk Modus zur Behandlung von Fehlern
- Sicherer Kioskmodus durch Eliminierung verfügbarer apps im Kioskmodus-Fehler. 

Zu einem früheren Zeitpunkt, zu dem Fehler bei der Anwendung des Kioskmodus aufgetreten sind, wurden im Startmenü alle Anwendungen HoloLens angezeigt. Jetzt in Windows holographische Version 20H2 im Fall von Fehlern werden keine apps im Startmenü wie folgt angezeigt: 

![Abbildung dessen, was der Kiosk Modus jetzt sieht, wenn er fehlschlägt.](images/hololens-kiosk-failure-behavior.png )

### Cache-Aad-Gruppenmitgliedschaft für Offline-Kiosk
- Ermöglicht das Verwenden von Offline-Kiosken für Aad-Gruppen für bis zu 60 Tage.

Diese Richtlinie steuert, wie viele Tage der Aad-Gruppen Mitgliedschafts Cache für zugewiesene Zugriffs Konfigurationen verwendet werden kann, die für Aad-Gruppen für signierten Benutzer vorgesehen sind. Sobald dieser Richtlinienwert auf den Wert größer als 0 gesetzt ist, wird der Cache andernfalls verwendet.  

Name: AADGroupMembershipCacheValidityInDays URI-Wert:./Vendor/MSFT/Policy/config/MixedReality/AADGroupMembershipCacheValidityInDays

Min-0 Tage  
Max-60 Tage 

Schritte zur korrekten Verwendung dieser Richtlinie: 
1. Erstellen Sie ein Device-Konfigurationsprofil für Kiosk-Targeting-Aad-Gruppen, und weisen Sie es HoloLens-Geräten zu. 
1. Erstellen Sie eine benutzerdefinierte Oma-URI-basierte Gerätekonfiguration, die diesen Richtlinienwert auf die gewünschte Anzahl von Tagen (> 0) festlegt und HoloLens-Device (s) zuweist. 
    1. Der URI-Wert sollte in Oma-URI-Textfeld als./Vendor/MSFT/Policy/config/MixedReality/AADGroupMembershipCacheValidityInDays eingegeben werden.
    1. Der Wert kann zwischen min/max zulässig sein.
1. Registrieren Sie HoloLens-Geräte, und überprüfen Sie, ob beide Konfigurationen auf das Gerät angewendet werden. 
1. Lassen Sie Aad Benutzer 1 anmelden, wenn Internet verfügbar ist, sobald die Benutzeranmeldung und die Aad-Gruppenmitgliedschaft erfolgreich bestätigt wurde, wird der Cache erstellt. 
1. Jetzt kann Aad User 1 HoloLens offline schalten und für den Kioskmodus verwenden, solange der Richtlinienwert X Anzahl von Tagen zulässt. 
1. Die Schritte 4 und 5 können für jeden anderen Aad-Benutzer N. entscheidend ist hier, dass sich jeder Aad-Benutzer bei einem Gerät mit Internet anmelden muss, damit mindestens einmal festgestellt werden kann, dass Sie Mitglied der Aad-Gruppe sind, auf die die Kiosk Konfiguration ausgerichtet ist. 
 
> [!NOTE]
> Bis zum Ausführen von Schritt 4 für einen Aad-Benutzer tritt ein Fehler Verhalten auf, das in "getrennte" Umgebungen erwähnt wird. 


## XML-Kiosk Code Beispiele für HoloLens

### Mehrere App-Kioskmodus, der auf eine Aad-Gruppe ausgerichtet ist. 
Dieser Kiosk stellt einen Kiosk bereit, der für Benutzer in der Aad-Gruppe einen Kiosk aktiviert hat, der die drei apps: Einstellungen, Remote Unterstützung und Feedback-Hub umfasst. Um dieses Beispiel für die sofortige Verwendung zu ändern, stellen Sie sicher, dass Sie die unten hervorgehobene GUID so ändern, dass Sie einer eigenen Aad-Gruppe entspricht. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### Mehrere App-Kioskmodus, der auf das Aad-Konto ausgerichtet ist.
Dieser Kiosk stellt einen Kiosk für einen einzelnen Benutzer bereit, auf dem ein Kiosk aktiviert ist, der die drei apps: Einstellungen, Remote Unterstützung und Feedback-Hub umfasst. Um dieses Beispiel für die sofortige Verwendung zu ändern, stellen Sie sicher, dass Sie das unten hervorgehobene Konto so ändern, dass es einem eigenen Aad-Konto entspricht. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

