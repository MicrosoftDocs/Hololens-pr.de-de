---
title: HoloLens Kioskreferenzinformationen
description: Informationen und Beispiele für Kioske auf HoloLens Geräten.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f8cfd0013ac5b8cf85a334cbb89c458440820d9
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032566"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLens-Kiosk-Referenzinformationen

Diese Seite enthält hilfreiche Informationen zum Einrichten des Kioskmodus Ihres HoloLens Geräts. Zu diesen Verweisen gehören AUMIDs für Posteingangs-Apps und die Suche nach Ihren Sowie mehrere XML-Beispiele für den Kioskmodus, die nur wenige Bearbeitungen von der Verwendung für verschiedene Szenarien entfernt sind. Informationen zum Einrichten eines Kiosks finden Sie auf der [Seite Einrichten eines Kiosks.](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens Anwendungsbenutzermodell-IDs (AUMIDs)  

Allgemeine Informationen zum Auswählen von Kiosk-Apps finden Sie unter [Richtlinien zum Auswählen einer App für zugewiesenen Zugriff (Kioskmodus).](/windows/configuration/guidelines-for-assigned-access-app)

Wenn Sie ein Mobile Geräteverwaltung-System (MDM) oder ein Bereitstellungspaket zum Konfigurieren des Kioskmodus verwenden, verwenden Sie [den AssignedAccess-Konfigurationsdienstanbieter (AssignedAccess Configuration Service Provider, CSP),](/windows/client-management/mdm/assignedaccess-csp) um Anwendungen anzugeben. Der CSP verwendet [Anwendungsbenutzermodell-IDs (Application User Model IDs, AUMIDs),](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) um Anwendungen zu identifizieren. In der folgenden Tabelle sind die AUMIDs einiger In-Box-Anwendungen aufgeführt, die Sie in einem Kiosk mit mehreren Apps verwenden können.

<a id="aumids"></a>

|App-Name |AUMID |
| --- | --- |
|3D-Betrachter |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Kalender |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Kamera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|Geräteauswahl auf HoloLens (1. Generation) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Geräteauswahl auf HoloLens 2 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DevicesFlowHost |
|Dynamics 365-Leitfäden |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteRob \_ 8wekyb3d8bbwe \! Microsoft.RemoteRobin |
|&nbsp;Feedback-Hub |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe-App \! |
|Datei-Explorer |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|E-Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Alte Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Der neue Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast<sup>4</sup> | &nbsp; |
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

Darüber hinaus kann die Mixed Reality Home nicht als Kiosk-App festgelegt werden.

Kehren Sie basierend auf dem Identitätstyp zu [Unterstützte Szenarien für den Kioskmodus](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) zurück.

## <a name="kiosk-xml-code-samples"></a>Kiosk-XML-Codebeispiele

1. [Global zugewiesenes Zugriffsprofil für mehrere Apps](#multiple-app-global-assigned-access-profile)
1. [Mehrere global zugewiesene App-Zugriffsprofile ohne Gerätebesitzer](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [Mehrere app-zugewiesene Zugriffsprofile für ein lokales Konto oder ein AAD-Benutzerkonto](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [Mehrere app-zugewiesene Zugriffsprofile für zwei oder mehr AAD-Benutzer](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [Mehrere app-zugewiesene Zugriffsprofile für eine AAD-Gruppe](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [Mehrere app-zugewiesene Zugriffsprofile für zwei oder mehr AAD-Gruppen](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [Mehrere app-zugewiesene Zugriffsprofile für ein AAD-Konto und eine AAD-Gruppe](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [Mehrere app-zugewiesene Zugriffsprofile für Besucher](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> Ersetzen Sie TODO-Aktionen gemäß Ihren Anforderungen.

### <a name="multiple-app-global-assigned-access-profile"></a>Global zugewiesenes Zugriffsprofil für mehrere Apps

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[Zurück zur Liste](#kiosk-xml-code-samples) <br>
Kehren Sie basierend auf dem Identitätstyp zu [Unterstützte Szenarien für den Kioskmodus](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) zurück.

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>Mehrere global zugewiesene App-Zugriffsprofile ohne Gerätebesitzer

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[Zurück zur Liste](#kiosk-xml-code-samples) <br>
Kehren Sie basierend auf dem Identitätstyp zu [Unterstützte Szenarien für den Kioskmodus](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) zurück.

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>Mehrere app-zugewiesene Zugriffsprofile für ein lokales Konto oder ein AAD-Benutzerkonto

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[Zurück zur Liste](#kiosk-xml-code-samples) <br>
Kehren Sie basierend auf dem Identitätstyp zu [Unterstützte Szenarien für den Kioskmodus](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) zurück.

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>Mehrere app-zugewiesene Zugriffsprofile für zwei oder mehr AAD-Benutzer

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[Zurück zur Liste](#kiosk-xml-code-samples) <br>
Kehren Sie basierend auf dem Identitätstyp zu [Unterstützte Szenarien für den Kioskmodus](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) zurück.

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>Mehrere app-zugewiesene Zugriffsprofile für eine AAD-Gruppe

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[Zurück zur Liste](#kiosk-xml-code-samples) <br>
Kehren Sie basierend auf dem Identitätstyp zu [Unterstützte Szenarien für den Kioskmodus](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) zurück.

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>Mehrere app-zugewiesene Zugriffsprofile für zwei oder mehr AAD-Gruppen

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[Zurück zur Liste](#kiosk-xml-code-samples) <br>
Kehren Sie basierend auf dem Identitätstyp zu [Unterstützte Szenarien für den Kioskmodus](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) zurück.

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>Mehrere app-zugewiesene Zugriffsprofile für ein AAD-Konto und eine AAD-Gruppe

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[Zurück zur Liste](#kiosk-xml-code-samples) <br>
Kehren Sie basierend auf dem Identitätstyp zu [Unterstützte Szenarien für den Kioskmodus](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) zurück.

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>Mehrere app-zugewiesene Zugriffsprofile für Besucher

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[Zurück zur Liste](#kiosk-xml-code-samples) <br>
Kehren Sie basierend auf dem Identitätstyp zu [Unterstützte Szenarien für den Kioskmodus](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) zurück.
