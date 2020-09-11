---
title: Verwenden von Microsoft Endpoint Manager InTune zum Verwalten von HoloLens-Geräten
description: Verwenden von MDM zum Konfigurieren von CSP und Richtlinie sowie zum Verwalten von HoloLens im Maßstab.
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
ms.openlocfilehash: 4fda0b271e915e82350f806418d2f02cbdd5a796
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009637"
---
# Verwenden von Microsoft Endpoint Manager InTune zum Verwalten von HoloLens-Geräten

Es gibt zahlreiche verschiedene Einstellungen, die Sie über MDM verwalten können. Die Verwendung von InTune-Geräten kann gruppiert werden, und Konfigurationen können für diese Gruppen von Benutzern oder Geräten bereitgestellt werden. Apps können auch bereitgestellt und verwaltet werden, Geräte zum Herstellen einer Verbindung mit Ihrem Netzwerk einrichten sowie Updates zum gewünschten Zeitpunkt und auf dem erforderlichen Aktualisierungs Ring konfigurieren. 

## Verwalten über InTune

### Gerätekategorien und-Gruppen
Mithilfe von InTune können Sie Gerätekategorien erstellen, um automatisch Geräte zu Gruppen hinzuzufügen, die auf von Ihnen erstellten Kategorien basieren, wie etwa Engineering, Medical, Developers usw. Die Idee ist, die Verwaltung Ihrer Geräte mit Windows holographisch für Unternehmen zu vereinfachen.
Weitere Informationen finden Sie unter [Kategorisieren von Geräten in Gruppen](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping) .

### Geräte Konfigurationsprofile
InTune umfasst Einstellungen und Features, die Sie auf verschiedenen Geräten in Ihrer Organisation aktivieren oder deaktivieren können. Diese Einstellungen und Features werden mithilfe von Profilen verwaltet. So können Sie beispielsweise ein Profil erstellen, das Cortana aktiviert, oder Microsoft Defender Smart Screen auf Ihren Geräten mit Windows holographisch for Business verwendet.
In ihren Profilen können Sie Oma-URI verwenden, um einige Einstellungen anzupassen, Geräteeinschränkungen zu erstellen und ein VPN (virtuelles privates Netzwerk) und WLAN zu konfigurieren.
[Erste Schritte mit Konfigurationsprofilen](https://docs.microsoft.com/mem/intune/configuration/device-profiles)und [Profilübersicht](https://docs.microsoft.com/mem/intune/configuration/device-profile-create)

## Beispiele für das, was verwaltet und konfiguriert werden kann

Die Verwendung von MDM zum Verwalten von Geräten bietet eine breite Palette von Elementen, die ausgewählt werden können. 

### WLAN
[WLAN-Einstellungen](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) weist Benutzern und Geräten Drahtlosnetzwerkeinstellungen zu. Wenn Sie ein WLAN-Profil zuweisen, erhalten Benutzer Zugriff auf Ihr unternehmenseigenes WLAN, ohne es selbst konfigurieren zu müssen.
Weitere Informationen zum [Konfigurieren Ihres Netzwerks für HoloLens](hololens-commercial-infrastructure.md)

### Zertifikate
Zertifikate helfen, die Sicherheit zu verbessern, indem Sie Kontoauthentifizierung, Wi-Fi-Authentifizierung, VPN-Verschlüsselung und SSL-Verschlüsselung von Webinhalten bereitstellen. Obwohl Administratoren Zertifikate auf Geräten manuell über Bereitstellungspakete verwalten können, empfiehlt es sich, das MDM-System für die Verwaltung dieser Zertifikate während des gesamten Lebenszyklus zu verwenden – von der Registrierung bis zur Verlängerung und Sperrung. Ihr MDM-System kann diese Zertifikate nach der Registrierung des Geräts automatisch für die Zertifikatspeicher der Geräte bereitstellen (sofern das MDM-System das Simple Certificate Enrollment Protocol (SCEP) oder Public Key Cryptography Standards #12 (PKCS # 12) unterstützt). MDM kann auch angemeldete Clientzertifikate Abfragen und löschen oder eine neue Registrierungsanforderung auslösen, bevor das aktuelle Zertifikat abgelaufen ist. 

### Proxy
Die meisten Intranet-Netzwerke des Unternehmens nutzen einen Proxy, um internen Datenverkehr zu verwalten. Mit HoloLens 2 können Sie einen Proxy Server für Ethernet-und WLAN-Verbindungen konfigurieren. Diese Einstellungen gelten nicht für VPN-Verbindungen. Weitere Informationen zu Proxyeinstellungen für Windows 10 finden Sie unter [Netzwerkproxy-CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

### VPN
Organisationen verwenden häufig ein VPN, um den Zugriff auf Apps und Ressourcen im Intranet des Unternehmens zu steuern. HoloLens 2 unterstützt SSL-VPN-Verbindungen, die ein herunterladbares Plugin aus dem Microsoft Store erfordern und für den VPN-Anbieter Ihrer Wahl spezifisch sind. 
- Weitere Informationen zu [VPN finden Sie unter HoloLens](hololens-network.md#vpn).
- Weitere Informationen zu VPN-Profilen finden Sie im [VPNv2-CSP](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).

### Bereitstellen und Verwalten von apps
Mithilfe von InTune können Sie Ihren Geräten, auf denen Windows holographisch for Business ausgeführt wird, Apps hinzufügen. Mit einer MDM-Lösung können IT-Entscheider und Administratoren ihre in-House-, Branchen-apps privat automatisch installieren (pushen) oder Apps über den Store für eine Gruppe von Benutzern kaufen. Es gibt viele Möglichkeiten zum Bereitstellen von apps, einschließlich:
-   [InTune und Unternehmens Portal]( app-deploy-intune.md)
-   [Microsoft Store für Unternehmen]( app-deploy-store-business.md)

Weitere Informationen zur APP-Verwaltung über InTune.
-   [Hinzufügen von apps zu InTune](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [Hinzufügen von Microsoft Store-Apps](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [Hinzufügen von apps, die Sie erstellen](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [Zuweisen von apps zu Gruppen](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### Software Updates
InTune umfasst ein Feature namens Update Rings für Windows 10-Geräte. Diese Update Ringe enthalten eine Gruppe von Einstellungen, die bestimmen, wie Updates installiert werden. Sie können z. B. ein Wartungsfenster erstellen, um Updates zu installieren, oder Sie können nach der Installation von Updates einen Neustart auswählen. Ein Update Ring kann auf mehrere Geräte angewendet werden, auf denen Windows holographische for Business ausgeführt wird.
Weitere Informationen finden Sie unter [Verwalten von HoloLens-Updates](hololens-updates.md) und [Verwalten von Softwareupdates über InTune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).

### Kioskmodus konfigurieren
Mithilfe der in InTune verfügbaren freigegebenen oder Gast-PC-Features können Sie Windows holographische for Business-Geräte so konfigurieren, dass Sie als Kiosk ausgeführt werden. Auf diesen Geräten kann eine APP (einzelner App-Kioskmodus) oder mehrere Apps (Multi-App-Kioskmodus) ausgeführt werden. Der Kiosk Modus ist eine Benutzeroberfläche, um zu steuern, welche Identitäten standardmäßig auf welche apps zugreifen können.
Informationen zum [Einrichten von HoloLens als Kiosk]( hololens-kiosk.md)

