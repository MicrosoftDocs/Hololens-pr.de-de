---
title: HoloLens mit einem Netzwerk verbinden
description: Anweisungen zum Herstellen einer Verbindung mit dem Internet mit HoloLens und zum Identifizieren der IP-Adresse des Geräts.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, WLAN, drahtlos, Internet, IP, IP-Adresse
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 0db64ffb4113ff948651c708c28b91da535cb09b
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009523"
---
# HoloLens mit einem Netzwerk verbinden

Für die Durchführung der meisten Aufgaben auf Ihrer HoloLens müssen Sie mit einem Netzwerk verbunden sein. Dieses Handbuch hilft Ihnen bei Folgendem:

- Herstellen einer Verbindung mit einem Netzwerk über WLAN oder (nur für HoloLens 2) Ethernet über USB-C
- Deaktivieren und erneutes Aktivieren von WLAN

Weitere Informationen finden Sie unter [Verwenden von HoloLens Offline](hololens-offline.md).

## Erstmaliges Herstellen einer Verbindung

Bei der ersten Verwendung von HoloLens werden Sie beim Herstellen einer Verbindung mit einem WLAN-Netzwerk angeleitet. Wenn beim Einrichten Probleme beim Herstellen einer Verbindung zu WLAN auftreten, stellen Sie sicher, dass es sich um ein offenes, kennwortgeschütztes Netzwerk oder ein Captive-Portalnetzwerk handelt. Stellen Sie sicher, dass für das Netzwerk kein Zertifikat zum Herstellen einer Verbindung benötigt wird. Nach dem Einrichten können Sie eine Verbindung zu anderen Arten von WLAN-Netzwerken herstellen.

Auf HoloLens2-Geräten kann ein Benutzer auch über einen [USB-C-zu-Ethernet-Adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) eine direkte Verbindung zu WLAN herstellen, um die Einrichtung des Geräts zu unterstützen. Sobald das Gerät eingerichtet wurde, kann ein Benutzer den Adapter entweder weiter verwenden oder das Gerät vom Adapter trennen und [nach dem Einrichten eine Verbindung zu WLAN herstellen](hololens-network.md#connecting-to-wi-fi-after-setup). 

## Herstellen einer Verbindung zu WLAN nach dem Einrichten

1. Führen Sie die **Startgeste** aus, und wählen Sie **Einstellungen** aus. Die Einstellungs-App wird automatisch vor Ihnen platziert.
1. Wählen Sie **Netzwerk und Internet** > **WLAN** aus. Stellen Sie sicher, dass WLAN aktiviert ist. Wenn Ihr Netzwerk nicht angezeigt wird, scrollen Sie die Liste nach unten.
1. Wählen Sie ein Netzwerk und dann **Verbinden** aus.
1. Wenn Sie zur Eingabe eines Netzwerkkennworts aufgefordert werden, geben Sie es ein, und wählen Sie dann **Weiter** aus.

HoloLens verfügt über einen 802.11ac-fähiges 2x2-WLAN-Funkanschluss. Das Verbinden von HoloLens mit einem WLAN-Netzwerk ähnelt dem Verbinden eines Windows 10-Desktops oder mobilen Geräts mit einem WLAN-Netzwerk.

![WLAN-Einstellungen für HoloLens](./images/wifi-hololens-600px.jpg)

Sie können auch bestätigen, dass Sie mit einem WLAN-Netzwerk verbunden sind, indem Sie den WLAN-Status im **Startmenü** überprüfen:

1. Öffnen Sie das **Startmenü**.
1. Suchen Sie oben links im **Startmenü** nach dem WLAN-Status. Der Status von WLAN und die SSID des verbundenen Netzwerks werden angezeigt.

## Behandeln von Problemen mit Ihrer WLAN-Verbindung

Wenn Sie Probleme beim Herstellen einer WLAN-Verbindung haben, lesen Sie [Ich kann keine WLAN-Verbindung herstellen](./hololens-faq.md#i-cant-connect-to-wi-fi).

Melden Sie sich mit dem Gerät bei einem Unternehmens- oder Organisationskonto an, kann auch die Richtlinie für die mobile Geräteverwaltung (Mobile Device Management, MDM) gelten, wenn die Richtlinie von Ihrem IT-Administrator konfiguriert wurde.

## VPN
Eine VPN-Verbindung kann Ihnen dabei helfen, eine sicherere Verbindung herzustellen sowie auf das Netzwerk Ihres Unternehmens und das Internet zuzugreifen. HoloLens2 unterstützt den integrierten VPN-Client und das VPN-Plug-In Universelle Windows-Plattform (UWP). 

Unterstützte integrierte VPN-Protokolle:
- IKEv2
- L2TP
- PPTP

Wenn für die Authentifizierung des integrierten VPN-Clients ein Zertifikat verwendet wird, muss das erforderliche Clientzertifikat zum Benutzerzertifikatspeicher hinzugefügt werden. Wenn Sie herausfinden möchten, ob das VPN-Plug-In eines Drittanbieters HoloLens2 unterstützt, wechseln Sie zu „Speicher“, um die VPN-App zu suchen, und überprüfen Sie, ob HoloLens als unterstütztes Gerät aufgeführt ist und ob die App auf der Seite „Systemanforderungen“ die ARM- oder ARM64-Architektur unterstützt. HoloLens unterstützt nur Universelle Windows-Plattform-Anwendungen für VPN von Drittanbietern.

VPN ist standardmäßig nicht aktiviert, kann aber durch Öffnen der App **Einstellungen** und Navigieren zu **„Netzwerk und Internet“ –> „VPN“** manuell aktiviert werden. VPN kann durch MDM über [Einstellungen/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) verwaltet und über die Richtlinie [Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp) festgelegt werden.
Weitere Informationen zum [Konfigurieren von VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) finden Sie in [diesen Handbüchern](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).  

## Deaktivieren von WLAN auf HoloLens (1. Generation)

### Verwenden der Einstellungs-App auf HoloLens

1. Öffnen Sie das **Startmenü**.
1. Wählen Sie die **Einstellungs**-App im **Startmenü** oder in der Liste **Alle Apps** auf der rechten Seite des **Startmenüs** aus. Die **Einstellungs**-App wird automatisch vor Ihnen platziert.
1. Wählen Sie **Netzwerk und Internet** aus.
1. Wählen Sie den WLAN-Schieberegler aus, um ihn in die Position **Off** (Aus) zu verschieben. Dadurch werden die HF-Komponenten des WLAN-Funkanschlusses ausgeschaltet und alle WLAN-Funktionen von HoloLens deaktiviert.

    > [!WARNING]
    > Wenn der WLAN-Funkanschluss deaktiviert ist, kann HoloLens Ihre [Räume](hololens-spaces.md) nicht automatisch laden.

1. Schieben Sie den Schieberegler in die Stellung **On** (Ein), um das WLAN zu aktivieren und die WLAN-Funktion auf Microsoft HoloLens wiederherzustellen. Der ausgewählte WLAN-Funkstatus (**Ein** oder **Aus**) bleibt bei einem Neustart erhalten.

## Identifizieren der IP-Adresse Ihrer HoloLens im WLAN-Netzwerk

### Mithilfe der Einstellungs-App

1. Öffnen Sie das **Startmenü**.
1. Wählen Sie die **Einstellungs**-App im **Startmenü** oder in der Liste **Alle Apps** auf der rechten Seite des **Startmenüs** aus. Die **Einstellungs**-App wird automatisch vor Ihnen platziert.
1. Wählen Sie **Netzwerk und Internet** aus.
1. Scrollen Sie nach unten unter die Liste der verfügbaren WLAN-Netzwerke und wählen Sie **Hardwareeigenschaften** aus.

    ![Hardwareeigenschaften in WLAN-Einstellungen](./images/wifi-hololens-hwdetails.jpg)

   Die IP-Adresse wird neben **IPv4-Adresse** angezeigt.

### Mithilfe von Sprachbefehlen

Je nach dem Build Ihres Geräts können Sie entweder mithilfe von integrierten Sprachbefehlen oder Cortana Ihre IP-Adresse anzeigen. Sprechen Sie bei Builds nach [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) „Wie lautet meine IP-Adresse?“ Dann wird sie angezeigt. Sagen Sie bei früheren Builds oder HoloLens (1.Generation)„Hey Cortana, wie lautet meine IP-Adresse?”. und Cortana wird Ihre IP-Adresse anzeigen und vorlesen.

### Mithilfe des Windows-Geräteportals

1. Öffnen Sie in einem Webbrowser auf Ihrem PC das [Geräteportal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Navigieren Sie zum Abschnitt **Netzwerk**.  
   In diesem Abschnitt werden Ihre IP-Adresse und andere Netzwerkinformationen angezeigt. Mithilfe dieser Methode können Sie die IP-Adresse auf Ihren Entwicklungscomputer kopieren und einfügen.
