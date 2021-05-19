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
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="58e1e-103">Herstellen einer Verbindung mit Mobilfunk und 5G</span><span class="sxs-lookup"><span data-stu-id="58e1e-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="58e1e-104">HoloLens 2 unterstützt zwei Methoden für die Verbindung mit Mobilfunk- und 5G-Netzwerken:</span><span class="sxs-lookup"><span data-stu-id="58e1e-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="58e1e-105">Ein ad-hoc-WLAN-Netzwerk, das vom Mobilfunkgerät bereitgestellt wird, allgemein als „Hotspot“ bezeichnet</span><span class="sxs-lookup"><span data-stu-id="58e1e-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="58e1e-106">Eingeschränkte Unterstützung für USB-C-Tethering-Geräte</span><span class="sxs-lookup"><span data-stu-id="58e1e-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="58e1e-107">Hotspot (WLAN)</span><span class="sxs-lookup"><span data-stu-id="58e1e-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="58e1e-108">Die meisten Mobilfunkverbindungsanforderungen können mit einem Hotspot erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="58e1e-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="58e1e-109">HoloLens 2 WLAN unterstützt 802.11ac, wodurch die Bandbreiten- und Latenzanforderungen für die meisten gängigen Verwendungsfälle erfüllt werden können.</span><span class="sxs-lookup"><span data-stu-id="58e1e-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="58e1e-110">WLAN ist auch kabelfrei und bietet Kompatibilität mit der größten Anzahl von Mobilfunkgeräten.</span><span class="sxs-lookup"><span data-stu-id="58e1e-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="58e1e-111">Herstellen einer Verbindung mit einem Hotspot</span><span class="sxs-lookup"><span data-stu-id="58e1e-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="58e1e-112">Informationen zum Aktivieren des Hotspotmodus finden Sie im Handbuch Ihres Geräts.</span><span class="sxs-lookup"><span data-stu-id="58e1e-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="58e1e-113">Aktivieren Sie den Hotspotmodus, und geben Sie einen Namen für das Netzwerk sowie ein bekanntes Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="58e1e-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="58e1e-114">Suchen Sie in den HoloLens 2-Netzwerkeinstellungen nach dem in Schritt 2 erstellten WLAN-Netzwerk, und schließen Sie es an.</span><span class="sxs-lookup"><span data-stu-id="58e1e-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="58e1e-115">USB-C-Tethering</span><span class="sxs-lookup"><span data-stu-id="58e1e-115">USB-C Tethering</span></span>

<span data-ttu-id="58e1e-116">USB-C-Tethering kann erweiterten Workloads, die dies benötigen, eine niedrigere Latenz bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="58e1e-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="58e1e-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering) kann z. B. vom Tethering profitieren.</span><span class="sxs-lookup"><span data-stu-id="58e1e-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="58e1e-118">Beachten Sie, dass das Tethering eine Kabelverbindung zwischen dem Mobilfunkgerät und HoloLens erfordert, und dass das Tethering von einer begrenzten Anzahl von Geräten unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="58e1e-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="58e1e-119">USB-C-Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="58e1e-119">USB-C compatibility</span></span>

<span data-ttu-id="58e1e-120">Geräte, die sich selbst als Ethernetadapter präsentieren, können mit Windows Holographic, Version 2004 und höher, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="58e1e-120">Devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="58e1e-121">Geräte, die sich nicht als Ethernetadapter präsentieren, müssen den generischen [RNDIS-Treiber](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) von Microsoft unterstützen.</span><span class="sxs-lookup"><span data-stu-id="58e1e-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="58e1e-122">Bitte wenden Sie sich an den Hersteller Ihres Geräts, um Informationen zu erhalten, ob es den generischen Microsoft RNDIS-Treiber unterstützt.</span><span class="sxs-lookup"><span data-stu-id="58e1e-122">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="58e1e-123">Geräte, die nicht RNDIS-kompatibel sind oder die die Installation eines Treibers oder einer Anwendung erfordern, werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="58e1e-123">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="58e1e-124">Microsoft führt zwar keine Liste kompatibler Geräte, aber [hier](https://aka.ms/HLCommunityCell) gibt es eine Communitydiskussion zu diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="58e1e-124">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="58e1e-125">Herstellen einer Verbindung mit einem Tethering-Gerät</span><span class="sxs-lookup"><span data-stu-id="58e1e-125">Connecting to a tethered device</span></span>

1. <span data-ttu-id="58e1e-126">Informationen zum Aktivieren der Datenfreigabe über USB finden Sie im Handbuch Ihres Geräts.</span><span class="sxs-lookup"><span data-stu-id="58e1e-126">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="58e1e-127">Diese Einstellung wird häufig als „USB-Tethering“, „Datenfreigabe“ oder „USB-Modem“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="58e1e-127">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="58e1e-128">Aktivieren Sie die Datenfreigabe über USB.</span><span class="sxs-lookup"><span data-stu-id="58e1e-128">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="58e1e-129">Verbinden Sie Ihr Gerät mit dem HoloLens-USB-C-Port.</span><span class="sxs-lookup"><span data-stu-id="58e1e-129">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="58e1e-130">In den HoloLens 2-Netzwerkeinstellungen wird das Gerät automatisch als Ethernetverbindung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58e1e-130">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
