---
title: Herstellen einer Verbindung mit Mobilfunk und 5G
description: Herstellen einer Verbindung mit Mobilfunknetzwerken von Ihren HoloLens Mixed Reality-Geräten aus.
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 3fd5f6baf05277bcbf2bf4152ba4735ca91e5bd0
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385641"
---
# <a name="connect-to-cellular-and-5g"></a>Herstellen einer Verbindung mit Mobilfunk und 5G

HoloLens 2 unterstützt zwei Methoden für die Verbindung mit Mobilfunk- und 5G-Netzwerken:

- Ein ad-hoc-WLAN-Netzwerk, das vom Mobilfunkgerät bereitgestellt wird, allgemein als „Hotspot“ bezeichnet
- Eingeschränkte Unterstützung für USB-C-Tethering-Geräte

## <a name="hotspot-wifi"></a>Hotspot (WLAN)

Die meisten Mobilfunkverbindungsanforderungen können mit einem Hotspot erfüllt werden. HoloLens 2 WLAN unterstützt 802.11ac, wodurch die Bandbreiten- und Latenzanforderungen für die meisten gängigen Verwendungsfälle erfüllt werden können. WLAN ist auch kabelfrei und bietet Kompatibilität mit der größten Anzahl von Mobilfunkgeräten.

### <a name="connecting-to-a-hotspot"></a>Herstellen einer Verbindung mit einem Hotspot

1. Informationen zum Aktivieren des Hotspotmodus finden Sie im Handbuch Ihres Geräts.
1. Aktivieren Sie den Hotspotmodus, und geben Sie einen Namen für das Netzwerk sowie ein bekanntes Kennwort an.
1. Suchen Sie in den HoloLens 2-Netzwerkeinstellungen nach dem in Schritt 2 erstellten WLAN-Netzwerk, und schließen Sie es an.

## <a name="usb-c-tethering"></a>USB-C-Tethering

USB-C-Tethering kann erweiterten Workloads, die dies benötigen, eine niedrigere Latenz bereitstellen. [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering) kann z. B. vom Tethering profitieren. Beachten Sie, dass das Tethering eine Kabelverbindung zwischen dem Mobilfunkgerät und HoloLens erfordert, und dass das Tethering von einer begrenzten Anzahl von Geräten unterstützt wird.

### <a name="usb-c-compatibility"></a>USB-C-Kompatibilität

Geräte, die sich selbst als Ethernetadapter präsentieren, können mit Windows Holographic, Version 2004 und höher, verwendet werden.

Geräte, die sich nicht als Ethernetadapter präsentieren, müssen den generischen [RNDIS-Treiber](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) von Microsoft unterstützen. Bitte wenden Sie sich an den Hersteller Ihres Geräts, um Informationen zu erhalten, ob es den generischen Microsoft RNDIS-Treiber unterstützt.

Geräte, die nicht RNDIS-kompatibel sind oder die die Installation eines Treibers oder einer Anwendung erfordern, werden nicht unterstützt.

Microsoft führt zwar keine Liste kompatibler Geräte, aber [hier](https://aka.ms/HLCommunityCell) gibt es eine Communitydiskussion zu diesem Thema.

### <a name="connecting-to-a-tethered-device"></a>Herstellen einer Verbindung mit einem Tethering-Gerät

1. Informationen zum Aktivieren der Datenfreigabe über USB finden Sie im Handbuch Ihres Geräts. Diese Einstellung wird häufig als „USB-Tethering“, „Datenfreigabe“ oder „USB-Modem“ bezeichnet.
1. Aktivieren Sie die Datenfreigabe über USB.
1. Verbinden Sie Ihr Gerät mit dem HoloLens-USB-C-Port.
1. In den HoloLens 2-Netzwerkeinstellungen wird das Gerät automatisch als Ethernetverbindung angezeigt.
