---
title: Verwenden von Microsoft Endpoint Manager Intune zum Verwalten von HoloLens-Geräten
description: 'Erfahren Sie, wie Sie MIT MDM verwenden, um CSP, Richtlinien und die Verwaltung von Mixed #A0 von HoloLens im großen Maßstab mithilfe von Intune zu konfigurieren.'
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283956"
---
# Verwenden von Microsoft Endpoint Manager Intune zum Verwalten von HoloLens-Geräten

Es gibt zahlreiche verschiedene Einstellungen, die Sie über MDM verwalten können. Mithilfe von Intune können Geräte gruppieren und Konfigurationen für diese Benutzer- oder Gerätegruppen bereitgestellt werden. Apps können auch bereitgestellt und verwaltet werden, Geräte für die Verbindung mit Ihrem Netzwerk einrichten sowie Updates so konfigurieren, dass sie zum gewünschten Zeitpunkt und im benötigten Updatering auftreten. 

## Verwalten über Intune

### Gerätekategorien und -gruppen
Mithilfe von Intune können Sie Gerätekategorien erstellen, um Geräte basierend auf von Ihnen erstellten Kategorien automatisch zu Gruppen hinzuzufügen, z. B. Engineering, Medical, Developers und so weiter. Die Idee besteht in der einfacheren Verwaltung Ihrer Geräte unter Windows Holographic for Business.
Weitere Informationen: [Kategorisieren von Geräten in Gruppen](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### Gerätekonfigurationsprofile
Intune enthält Einstellungen und Features, die Sie auf verschiedenen Geräten in Ihrer Organisation aktivieren oder deaktivieren können. Diese Einstellungen und Features werden mithilfe von Profilen verwaltet. Beispielsweise können Sie ein Profil erstellen, das Cortana aktiviert, oder Microsoft Defender Smart Screen auf Ihren Geräten mit Windows Holographic for Business verwenden.
In Ihren Profilen können Sie OMA-URI verwenden, um einige Einstellungen anzupassen, Geräteeinschränkungen zu erstellen und ein virtuelles privates Netzwerk (VPN) und WLAN zu konfigurieren.
[Erste Schritte mit Konfigurationsprofilen](https://docs.microsoft.com/mem/intune/configuration/device-profiles)und [Profilübersicht](https://docs.microsoft.com/mem/intune/configuration/device-profile-create).

## Beispiele für das, was verwaltet und konfiguriert werden kann

Die Verwendung von MDM zum Verwalten von Geräten bietet eine Vielzahl von Elementen, die ausgewählt werden können. 

### WLAN
[Wlaneinstellungen weisen](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) Benutzern und Geräten Drahtlosnetzwerkeinstellungen zu. Wenn Sie ein Wi-Fi zuweisen, erhalten Benutzer Zugriff auf Ihre Wi-Fi, ohne sie selbst konfigurieren zu müssen.
Weitere Informationen zum [Konfigurieren Ihres Netzwerks für HoloLens](hololens-commercial-infrastructure.md)

### Zertifikate
Zertifikate tragen zur Verbesserung der Sicherheit bei, indem sie die Kontoauthentifizierung, Wi-Fi A0, die VPN-Verschlüsselung und die SSL-Verschlüsselung von Webinhalten bereitstellen. Auch wenn Administratoren Zertifikate auf Geräten manuell über Bereitstellungspakete verwalten können, ist es eine bewährte Methode, diese Zertifikate über ihren gesamten Lebenszyklus hinweg mithilfe Ihres MDM-Systems zu verwalten – von der Registrierung über die Verlängerung bis hin zur Sperrung. Ihr #A0 kann diese Zertifikate automatisch in den Zertifikatspeichern der Geräte bereitstellen, nachdem Sie das Gerät registriert haben (solange das #A1 das Simple Certificate Enrollment Protocol (SCEP) oder public Key Cryptography Standards #12 (PKCS#12)) unterstützt. MDM kann auch registrierte Clientzertifikate abfragen und löschen oder eine neue Registrierungsanforderung auslösen, bevor das aktuelle Zertifikat abläuft. 

### Proxy
Die meisten Unternehmensintranetnetzwerke nutzen einen Proxy zum Verwalten des internen Datenverkehrs. Mit HoloLens 2 können Sie einen Proxyserver für Ethernet- und Wi-Fi konfigurieren. Diese Einstellungen gelten nicht für VPN-Verbindungen. Weitere Informationen zu Proxyeinstellungen für Windows 10 finden Sie unter [NetworkProxy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

### VPN
Organisationen verwenden häufig ein VPN, um den Zugriff auf Apps und Ressourcen im Intranet des Unternehmens zu steuern. HoloLens 2 unterstützt SSL-VPN-Verbindungen, die ein herunterladbares Plug-In aus dem Microsoft Store erfordern und spezifisch für den jeweiligen VPN-Anbieter sind. 
- Erfahren Sie mehr über [VPN auf HoloLens.](hololens-network.md#vpn)
- Weitere Informationen zu #A0 finden Sie im [VPNv2-CSP.](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)

### Bereitstellen und Verwalten von Apps
Mit Intune können Sie Ihren Geräten mit Windows Holographic for Business Apps hinzufügen. Eine MDM-Lösung ermöglicht es IT-Entscheidungsträgern und Administratoren, ihre eigenen ,Line-of-Business-Apps privat zu installieren (pushen) oder Apps über den Store für eine Gruppe von Benutzern zu erwerben. Es gibt viele Möglichkeiten zum Bereitstellen von Apps, darunter:
-   [Intune und Unternehmensportal]( app-deploy-intune.md)
-   [Microsoft Store für Unternehmen]( app-deploy-store-business.md)

Erfahren Sie mehr über die Verwaltung von Apps über Intune.
-   [Hinzufügen von Apps zu Intune](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [Hinzufügen von Microsoft Store-Apps](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [Hinzufügen von Apps, die Sie erstellen](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [Zuweisen von Apps zu Gruppen](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### Softwareupdates
Intune enthält ein Feature namens Updateringe für Windows 10-Geräte. Diese Updateringe enthalten eine Gruppe von Einstellungen, die bestimmen, wie Updates installiert werden. Sie können z. B. ein Wartungsfenster erstellen, um Updates zu installieren, oder Sie können nach der Installation von Updates einen Neustart auswählen. Ein Updatering kann auf mehrere Geräte mit Windows Holographic for Business angewendet werden.
Erfahren Sie mehr über die Verwaltung [von HoloLens-Updates](hololens-updates.md) und [Softwareupdates über Intune.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)

### Kioskmodus konfigurieren
Mithilfe der gemeinsam genutzten oder Gast-PC-Funktionen, die in Intune verfügbar sind, können Sie Windows Holographic for Business-Geräte so konfigurieren, dass sie als Kiosk ausgeführt werden. Diese Geräte können eine App (Single-App-Kioskmodus) oder mehrere Apps (Multi-App-Kioskmodus) ausführen. Der Kioskmodus ist eine Benutzeroberfläche, mit der sie steuern können, welche Identitäten standardmäßig auf welche Apps zugreifen können.
Informationen zum Einrichten [von HoloLens als Kiosk]( hololens-kiosk.md)

