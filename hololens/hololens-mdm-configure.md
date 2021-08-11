---
title: Verwenden der Microsoft-Endpoint Manager Intune zum Verwalten HoloLens Geräten
description: Erfahren Sie, wie Sie MDM verwenden, um CSP, Richtlinien und mixed reality-Geräte HoloLens Intune zu konfigurieren und zu verwalten.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/9/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0a0f26750ff6ea881babfab44af95cbbefa0574674336934ccf1443df1701a96
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663270"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>Verwenden der Microsoft-Endpoint Manager Intune zum Verwalten HoloLens Geräten

Es gibt zahlreiche verschiedene Einstellungen, die Sie über MDM verwalten können. Die Verwendung von Intune-Geräten kann gruppiert werden, und Konfigurationen können für diese Gruppen von Benutzern oder Geräten bereitgestellt werden. Apps können auch bereitgestellt und verwaltet werden, um Geräte für die Verbindung mit Ihrem Netzwerk zu konfigurieren sowie Updates so zu konfigurieren, dass sie zum gewünschten Zeitpunkt und auf dem benötigten Updatering erfolgen. 

## <a name="how-to-manage-via-intune"></a>Verwalten über Intune

### <a name="device-categories-and-groups"></a>Gerätekategorien und Gruppen
Mit Intune können Sie Gerätekategorien erstellen, um Geräte basierend auf von Ihnen erstellten Kategorien wie Engineering, Medical, Developers und so weiter automatisch Gruppen hinzuzufügen. Dadurch soll das Verwalten der Geräte, auf denen Windows Holographic for Business ausgeführt wird, erleichtert werden.
Weitere Informationen: [Kategorisieren von Geräten in Gruppen](/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>Gerätekonfigurierungsprofile
Intune umfasst Einstellungen und Features, die Sie auf unterschiedlichen Geräten in Ihrer Organisation aktivieren oder deaktivieren können. Diese Einstellungen und Features werden mithilfe von Profilen verwaltet. Sie können beispielsweise ein Profil erstellen, das Cortana aktiviert, oder Microsoft Defender SmartScreen auf Ihren Geräten mit Windows Holographic for Business verwenden.
Sie können OMA-URI in Ihren Profilen verwenden, um einige Einstellungen anzupassen, Geräteeinschränkungen zu erstellen und VPN und WLAN zu konfigurieren.
[Erste Schritte mit Konfigurationsprofilen](/mem/intune/configuration/device-profiles)und [Profilübersicht.](/mem/intune/configuration/device-profile-create)

## <a name="examples-of-what-can-be-managed-and-configured"></a>Beispiele dafür, was verwaltet und konfiguriert werden kann

Die Verwendung von MDM zum Verwalten von Geräten bietet eine Vielzahl von Elementen, die ausgewählt werden können. 

### <a name="wi-fi"></a>WLAN
Mit [WLAN-Einstellungen](/mem/intune/configuration/wi-fi-settings-configure) können Sie Benutzern und Geräten WLAN-Einstellungen zuweisen. Wenn Sie ein profil Wi-Fi zuweisen, erhalten Benutzer Zugriff auf Ihre UnternehmensdatenWi-Fi ohne sie selbst konfigurieren zu müssen.
Erfahren Sie mehr [über das Konfigurieren Ihres Netzwerks für HoloLens](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>Zertifikate
Zertifikate tragen zur Verbesserung der Sicherheit bei, indem sie Kontoauthentifizierung, Wi-Fi Authentifizierung, VPN-Verschlüsselung und SSL-Verschlüsselung von Webinhalten bereitstellen. Obwohl Administratoren Zertifikate auf Geräten manuell über Bereitstellungspakete verwalten können, ist es eine bewährte Methode, ihr MDM-System zu verwenden, um diese Zertifikate während ihres gesamten Lebenszyklus zu verwalten – von der Registrierung über die Verlängerung bis hin zur Sperrung. Ihr MDM-System kann diese Zertifikate automatisch in den Zertifikatspeichern der Geräte bereitstellen, nachdem Sie das Gerät registriert haben (solange das MDM-System die Simple Certificate Enrollment-Protokoll (SCEP) oder Public Key Cryptography Standards #12 (PKCS #12)) unterstützt. MDM kann auch registrierte Clientzertifikate abfragen und löschen oder eine neue Registrierungsanforderung auslösen, bevor das aktuelle Zertifikat abgelaufen ist. 

### <a name="proxy"></a>Proxy
Die meisten Intranetnetzwerke des Unternehmens nutzen einen Proxy zum Verwalten des internen Datenverkehrs. Mit HoloLens 2 können Sie einen Proxyserver für Ethernet- und Wi-Fi konfigurieren. Diese Einstellungen gelten nicht für VPN-Verbindungen. Weitere Informationen zu Proxyeinstellungen für Windows 10 finden Sie unter [NetworkProxy CSP](/windows/client-management/mdm/networkproxy-csp).

### <a name="vpn"></a>VPN
Organisationen verwenden häufig ein VPN, um den Zugriff auf Apps und Ressourcen im Intranet des Unternehmens zu steuern. HoloLens 2 unterstützt SSL-VPN-Verbindungen, die ein herunterladbares Plug-In aus dem Microsoft Store erfordern und für den VPN-Anbieter Ihrer Wahl spezifisch sind. 
- Erfahren Sie mehr [über VPN auf HoloLens](hololens-network.md#vpn).
- Weitere Informationen zu VPN-Profilen finden Sie im [VPNv2-CSP.](/windows/client-management/mdm/vpnv2-csp)

### <a name="deploy-and-manage-apps"></a>Bereitstellen und Verwalten von Apps
Mithilfe von Intune können Sie Apps zu Ihren Geräten hinzufügen, auf denen Windows Holographic for Business ausgeführt wird. Mit einer MDM-Lösung können IT-Entscheidungsträger und Administratoren ihre unternehmensspezifischen Apps privat automatisch installieren (pushen) oder Apps über den Store für eine Gruppe von Benutzern erwerben. Es gibt unter anderem folgende Möglichkeiten, um Apps bereitzustellen:
-   [Intune und Unternehmensportal]( app-deploy-intune.md)
-   [Microsoft Store für Unternehmen]( app-deploy-store-business.md)

Erfahren Sie mehr über die App-Verwaltung über Intune.
-   [Hinzufügen von Apps zu Intune](/mem/intune/apps/apps-add)
-   [Das Hinzufügen von Microsoft Store-Apps](/mem/intune/apps/store-apps-windows)
-   [Das Hinzufügen von Apps, die Sie erstellt haben](/mem/intune/apps/lob-apps-windows)
- [Das Zuweisen von Apps zu Gruppen](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>Softwareupdates
Intune enthält ein Feature namens „Updateringe“ für Windows 10-Geräte. Diese Updateringe enthalten Einstellungen, durch die bestimmt wird, wie Updates installiert werden. Sie können beispielsweise ein Wartungsfenster zum Installieren von Updates erstellen oder einen Neustart durchführen, nachdem Updates installiert wurden. Ein Updatering kann auf mehreren Geräte angewendet werden, auf denen Windows Holographic for Business ausgeführt wird.
Weitere Informationen finden Sie unter Verwalten [HoloLens Updates](hololens-updates.md) und Verwalten [von Softwareupdates über Intune.](/mem/intune/protect/windows-update-for-business-configure)

### <a name="configure-kiosk-mode"></a>Konfigurieren des Kioskmodus
Mithilfe der in Intune verfügbaren Funktionen für freigegebene oder Gast-PCs können Sie Windows Holographic for Business-Geräte so konfigurieren, dass sie als Kiosk ausgeführt werden. Diese Geräte können eine App (Einzel-App-Kioskmodus) oder mehrere Apps (Multi-App-Kioskmodus) ausführen. Der Kioskmodus ist eine Benutzeroberfläche, mit der sie steuern können, welche Identitäten standardmäßig Zugriff auf welche Apps haben.
Erfahren Sie, [wie Sie HoloLens als Kiosk einrichten.]( hololens-kiosk.md)

