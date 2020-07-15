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
ms.openlocfilehash: 734176dcf8a789f130aa8b010f5f3c9ec1d22c72
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857793"
---
# HoloLens mit einem Netzwerk verbinden

Für die Durchführung der meisten Aufgaben auf Ihrer HoloLens müssen Sie mit einem Netzwerk verbunden sein. Dieses Handbuch hilft Ihnen bei Folgendem:

- Herstellen einer Verbindung mit einem Netzwerk über WLAN oder (nur für HoloLens 2) Ethernet über USB-C
- Deaktivieren und erneutes Aktivieren von WLAN

Weitere Informationen finden Sie unter [Verwenden von HoloLens Offline](hololens-offline.md).

## Erstmaliges Herstellen einer Verbindung

Bei der ersten Verwendung von HoloLens werden Sie beim Herstellen einer Verbindung mit einem WLAN-Netzwerk angeleitet. Wenn beim Einrichten Probleme beim Herstellen einer Verbindung zu WLAN auftreten, stellen Sie sicher, dass es sich um ein offenes, kennwortgeschütztes Netzwerk oder ein Captive-Portalnetzwerk handelt. Stellen Sie sicher, dass für das Netzwerk kein Zertifikat zum Herstellen einer Verbindung benötigt wird. Nach dem Einrichten können Sie eine Verbindung zu anderen Arten von WLAN-Netzwerken herstellen.

## Herstellen einer Verbindung zu WLAN nach dem Einrichten

1. Wählen Sie **Start** > **Einstellungen** aus.
   - *Nur HoloLens (1. Generation)*: Verwenden Sie Anvisieren, um die Einstellungs-App zu positionieren, und tippen Sie dann in die Luft, um sie zu platzieren, oder sagen Sie „Platzieren”.
1. Wählen Sie **Netzwerk und Internet** > **WLAN** aus. Wenn Ihr Netzwerk nicht angezeigt wird, scrollen Sie die Liste nach unten.
1. Wählen Sie ein Netzwerk und dann **Verbinden** aus.
1. Wenn Sie zur Eingabe eines Netzwerkkennworts aufgefordert werden, geben Sie es ein, und wählen Sie dann **Weiter** aus.

## Herstellen einer Verbindung zu WLAN auf HoloLens (1. Generation)

HoloLens verfügt über einen 802.11ac-fähiges 2x2-WLAN-Funkanschluss. Das Verbinden von HoloLens mit einem WLAN-Netzwerk ähnelt dem Verbinden eines Windows 10-Desktops oder mobilen Geräts mit einem WLAN-Netzwerk.

![WLAN-Einstellungen für HoloLens](./images/wifi-hololens-600px.jpg)

1. Öffnen Sie das **Startmenü**.
1. Wählen Sie die Einstellungs-App im **Startmenü** aus oder aus der Liste **Alle apps** auf der rechten Seite des **Startmenüs** aus. Die Einstellungs-App wird automatisch vor Ihnen platziert.
1. Wählen Sie **Netzwerk und Internet** aus.
1. Stellen Sie sicher, dass WLAN aktiviert ist.
1. Wählen Sie in der Liste ein WLAN-Netzwerk aus.
1. Geben Sie bei Bedarf das Kennwort für das WLAN-Netzwerk ein.

Sie können auch bestätigen, dass Sie mit einem WLAN-Netzwerk verbunden sind, indem Sie den WLAN-Status im **Startmenü** überprüfen:

1. Öffnen Sie das **Startmenü**.
1. Suchen Sie oben links im **Startmenü** nach dem WLAN-Status. Der Status von WLAN und die SSID des verbundenen Netzwerks werden angezeigt.

## Behandeln von Problemen mit Ihrer WLAN-Verbindung

Wenn Sie Probleme beim Herstellen einer WLAN-Verbindung haben, lesen Sie [Ich kann keine WLAN-Verbindung herstellen](./hololens-faq.md#i-cant-connect-to-wi-fi).

Melden Sie sich mit dem Gerät bei einem Unternehmens- oder Organisationskonto an, kann auch die Richtlinie für die mobile Geräteverwaltung (Mobile Device Management, MDM) gelten, wenn die Richtlinie von Ihrem IT-Administrator konfiguriert wurde.

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

### Mithilfe von Cortana

Sagen Sie „Hey Cortana, wie lautet meine IP-Adresse?” und Cortana wird Ihre IP-Adresse anzeigen und vorlesen.

### Mithilfe des Windows-Geräteportals

1. Öffnen Sie in einem Webbrowser auf Ihrem PC das [Geräteportal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Navigieren Sie zum Abschnitt **Netzwerk**.  
   In diesem Abschnitt werden Ihre IP-Adresse und andere Netzwerkinformationen angezeigt. Mithilfe dieser Methode können Sie die IP-Adresse auf Ihren Entwicklungscomputer kopieren und einfügen.
