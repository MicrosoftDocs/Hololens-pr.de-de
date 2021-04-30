---
title: Verwenden des microsoft-Endpoint Manager Intune zum Verwalten von HoloLens-Geräten
description: Erfahren Sie, wie Sie MDM verwenden, um CSP- und Richtlinienfunktionen zu konfigurieren und HoloLens Mixed Reality-Geräte mit Intune im großen Stil zu verwalten.
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
ms.openlocfilehash: ce288afdcb112c17ffde75078d641f3637a8448c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308839"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>Verwenden des microsoft-Endpoint Manager Intune zum Verwalten von HoloLens-Geräten

Es gibt zahlreiche verschiedene Einstellungen, die Sie über MDM verwalten können. Die Verwendung von Intune-Geräten kann gruppiert werden, und Konfigurationen können für diese Benutzer- oder Gerätegruppen bereitgestellt werden. Apps können auch bereitgestellt und verwaltet werden, um Geräte für die Verbindung mit Ihrem Netzwerk einzurichten und Updates so zu konfigurieren, dass sie zum gewünschten Zeitpunkt und auf dem benötigten Updatering erfolgen. 

## <a name="how-to-manage-via-intune"></a>Verwalten über Intune

### <a name="device-categories-and-groups"></a>Gerätekategorien und Gruppen
Mit Intune können Sie Gerätekategorien erstellen, um Geräte basierend auf von Ihnen erstellten Kategorien wie Engineering, Medical, Developers usw. automatisch Gruppen hinzuzufügen. Dadurch soll das Verwalten der Geräte, auf denen Windows Holographic for Business ausgeführt wird, erleichtert werden.
Weitere Informationen: [Kategorisieren von Geräten in Gruppen](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>Gerätekonfigurierungsprofile
Intune umfasst Einstellungen und Features, die Sie auf unterschiedlichen Geräten in Ihrer Organisation aktivieren oder deaktivieren können. Diese Einstellungen und Features werden mithilfe von Profilen verwaltet. Sie können beispielsweise ein Profil erstellen, das Cortana aktiviert, oder Microsoft Defender SmartScreen auf Ihren Geräten mit Windows Holographic for Business verwenden.
Sie können OMA-URI in Ihren Profilen verwenden, um einige Einstellungen anzupassen, Geräteeinschränkungen zu erstellen und VPN und WLAN zu konfigurieren.
[Erste Schritte mit Konfigurationsprofilen](https://docs.microsoft.com/mem/intune/configuration/device-profiles)und [Profilübersicht.](https://docs.microsoft.com/mem/intune/configuration/device-profile-create)

## <a name="examples-of-what-can-be-managed-and-configured"></a>Beispiele dafür, was verwaltet und konfiguriert werden kann

Die Verwendung von MDM zum Verwalten von Geräten bietet eine Vielzahl von Elementen, die ausgewählt werden können. 

### <a name="wi-fi"></a>WLAN
Mit [WLAN-Einstellungen](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) können Sie Benutzern und Geräten WLAN-Einstellungen zuweisen. Wenn Sie ein Wi-Fi Profil zuweisen, erhalten Benutzer Zugriff auf Ihre Unternehmens-Wi-Fi, ohne es selbst konfigurieren zu müssen.
Weitere Informationen [zum Konfigurieren Ihres Netzwerks für HoloLens](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>Zertifikate
Zertifikate verbessern die Sicherheit, indem sie Kontoauthentifizierung, Wi-Fi Authentifizierung, VPN-Verschlüsselung und SSL-Verschlüsselung von Webinhalten bereitstellen. Obwohl Administratoren Zertifikate auf Geräten manuell über Bereitstellungspakete verwalten können, ist es eine bewährte Methode, Ihr MDM-System zu verwenden, um diese Zertifikate während ihres gesamten Lebenszyklus zu verwalten – von der Registrierung über die Verlängerung und Sperrung. Ihr MDM-System kann diese Zertifikate automatisch in den Zertifikatspeichern der Geräte bereitstellen, nachdem Sie das Gerät registriert haben (sofern das MDM-System die Simple Certificate Enrollment-Protokoll (SCEP) oder Public Key Cryptography Standards #12 (PKCS #12) unterstützt). MDM kann auch registrierte Clientzertifikate abfragen und löschen oder eine neue Registrierungsanforderung auslösen, bevor das aktuelle Zertifikat abgelaufen ist. 

### <a name="proxy"></a>Proxy
Die meisten Intranetnetzwerke des Unternehmens nutzen einen Proxy zum Verwalten des internen Datenverkehrs. Mit HoloLens 2 können Sie einen Proxyserver für Ethernet- und Wi-Fi konfigurieren. Diese Einstellungen gelten nicht für VPN-Verbindungen. Weitere Informationen zu Proxyeinstellungen für Windows 10 finden Sie unter [NetworkProxy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

### <a name="vpn"></a>VPN
Organisationen verwenden häufig ein VPN, um den Zugriff auf Apps und Ressourcen im Intranet des Unternehmens zu steuern. HoloLens 2 unterstützt SSL-VPN-Verbindungen, die ein herunterladbares Plug-In aus dem Microsoft Store erfordern und für den VPN-Anbieter Ihrer Wahl spezifisch sind. 
- Erfahren Sie mehr [über VPN auf HoloLens.](hololens-network.md#vpn)
- Weitere Informationen zu VPN-Profilen finden Sie im [VPNv2-CSP.](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)

### <a name="deploy-and-manage-apps"></a>Bereitstellen und Verwalten von Apps
Mithilfe von Intune können Sie Apps zu Ihren Geräten hinzufügen, auf denen Windows Holographic for Business ausgeführt wird. Mit einer MDM-Lösung können IT-Entscheidungsträger und Administratoren ihre unternehmensspezifischen Apps privat automatisch installieren (pushen) oder Apps über den Store für eine Gruppe von Benutzern erwerben. Es gibt unter anderem folgende Möglichkeiten, um Apps bereitzustellen:
-   [Intune und Unternehmensportal]( app-deploy-intune.md)
-   [Microsoft Store für Unternehmen]( app-deploy-store-business.md)

Erfahren Sie mehr über die App-Verwaltung über Intune.
-   [Hinzufügen von Apps zu Intune](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [Das Hinzufügen von Microsoft Store-Apps](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [Das Hinzufügen von Apps, die Sie erstellt haben](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [Das Zuweisen von Apps zu Gruppen](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>Softwareupdates
Intune enthält ein Feature namens „Updateringe“ für Windows 10-Geräte. Diese Updateringe enthalten Einstellungen, durch die bestimmt wird, wie Updates installiert werden. Sie können beispielsweise ein Wartungsfenster zum Installieren von Updates erstellen oder einen Neustart durchführen, nachdem Updates installiert wurden. Ein Updatering kann auf mehreren Geräte angewendet werden, auf denen Windows Holographic for Business ausgeführt wird.
Erfahren Sie mehr über das Verwalten [von HoloLens-Updates und](hololens-updates.md) [das Verwalten von Softwareupdates über Intune.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)

### <a name="configure-kiosk-mode"></a>Konfigurieren des Kioskmodus
Mithilfe der in Intune verfügbaren Funktionen für freigegebene oder Gast-PCs können Sie Windows Holographic for Business-Geräte so konfigurieren, dass sie als Kiosk ausgeführt werden. Diese Geräte können eine App (Einzel-App-Kioskmodus) oder mehrere Apps (Multi-App-Kioskmodus) ausführen. Der Kioskmodus ist eine Benutzeroberfläche, mit der sie steuern können, welche Identitäten standardmäßig Zugriff auf welche Apps haben.
Erfahren Sie, [wie Sie HoloLens als Kiosk einrichten.]( hololens-kiosk.md)

