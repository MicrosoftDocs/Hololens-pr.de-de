---
title: Herstellen einer Verbindung mit Mobilfunk und 5G
description: Herstellen einer Verbindung mit Mobilfunknetzwerken von Ihren HoloLens Mixed Reality-Geräten.
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
ms.openlocfilehash: 6f7da0263e8637486f0151fd2b9da55da8feccc1
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635839"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="4192e-103">Herstellen einer Verbindung mit Mobilfunk und 5G</span><span class="sxs-lookup"><span data-stu-id="4192e-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="4192e-104">HoloLens 2 unterstützt zwei Methoden für die Verbindung mit Mobilfunk- und 5G-Netzwerken:</span><span class="sxs-lookup"><span data-stu-id="4192e-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="4192e-105">Ein ad-hoc-WLAN-Netzwerk, das vom Mobilfunkgerät bereitgestellt wird, allgemein als „Hotspot“ bezeichnet</span><span class="sxs-lookup"><span data-stu-id="4192e-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="4192e-106">Eingeschränkte Unterstützung für USB-C-Tethering-Geräte</span><span class="sxs-lookup"><span data-stu-id="4192e-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="4192e-107">Hotspot (WiFi)</span><span class="sxs-lookup"><span data-stu-id="4192e-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="4192e-108">Die meisten Mobilfunkverbindungsanforderungen können mit einem Hotspot erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="4192e-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="4192e-109">HoloLens 2 WLAN unterstützt 802.11ac, wodurch die Bandbreiten- und Latenzanforderungen für die meisten gängigen Verwendungen erfüllt werden können.</span><span class="sxs-lookup"><span data-stu-id="4192e-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="4192e-110">WLAN ist auch kabellos und bietet Kompatibilität mit der größten Anzahl von Mobilfunkgeräten.</span><span class="sxs-lookup"><span data-stu-id="4192e-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="4192e-111">Herstellen einer Verbindung mit einem Hotspot</span><span class="sxs-lookup"><span data-stu-id="4192e-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="4192e-112">Informationen zum Aktivieren des Hotspot-Modus finden Sie im Handbuch Ihres Geräts.</span><span class="sxs-lookup"><span data-stu-id="4192e-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="4192e-113">Aktivieren Sie den Hotspot-Modus, und geben Sie einen Namen für das Netzwerk sowie ein bekanntes Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="4192e-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="4192e-114">Suchen Sie in den HoloLens 2-Netzwerkeinstellungen nach dem in Schritt 2 erstellten WLAN-Netzwerk, und verbinden Sie sich damit.</span><span class="sxs-lookup"><span data-stu-id="4192e-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="4192e-115">USB-C-Tethering</span><span class="sxs-lookup"><span data-stu-id="4192e-115">USB-C Tethering</span></span>

<span data-ttu-id="4192e-116">Eine USB-C-Tethering kann erweiterten Workloads, die dies benötigen, eine niedrigere Latenz bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4192e-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="4192e-117">Z. B. kann [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering) von Tethering profitieren.</span><span class="sxs-lookup"><span data-stu-id="4192e-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="4192e-118">Beachten Sie, dass das Tethering eine Kabelverbindung zwischen dem Mobilfunkgerät und HoloLens erfordert, und dass das Tethering nur von einer begrenzten Anzahl von Geräten unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="4192e-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="4192e-119">USB-C-Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="4192e-119">USB-C compatibility</span></span>

<span data-ttu-id="4192e-120">Eine begrenzte Anzahl von Geräten, die sich als Ethernet-Adapter präsentieren, können mit Windows Holographic Version 2004 und höher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4192e-120">A limited number of devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="4192e-121">Geräte, die sich nicht als Ethernet-Adapter präsentieren, müssen den generischen [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) Treiber von Microsoft unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4192e-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="4192e-122">Allerdings ist nur eine begrenzte Anzahl dieser Geräte mit HoloLens 2 kompatibel.</span><span class="sxs-lookup"><span data-stu-id="4192e-122">But, only a limited number of those devices are compatible with HoloLens 2.</span></span> <span data-ttu-id="4192e-123">Bitte wenden Sie sich an den Hersteller Ihres Geräts, um Informationen zu erhalten, ob es den generischen Microsoft RNDIS-Treiber unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4192e-123">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="4192e-124">Geräte, die nicht RNDIS-kompatibel sind oder die Installation eines Treibers oder einer Anwendung erfordern, werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4192e-124">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="4192e-125">Microsoft führt zwar keine Liste kompatibler Geräte, aber [hier](https://aka.ms/HLCommunityCell) gibt es eine Community-Diskussion zu diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="4192e-125">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="4192e-126">Herstellen einer Verbindung mit einem Tethering-Gerät</span><span class="sxs-lookup"><span data-stu-id="4192e-126">Connecting to a tethered device</span></span>

1. <span data-ttu-id="4192e-127">Informationen zum Aktivieren der Datenfreigabe über USB finden Sie im Handbuch Ihres Geräts.</span><span class="sxs-lookup"><span data-stu-id="4192e-127">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="4192e-128">Diese Einstellung wird häufig als „USB-Tethering“, „Datenfreigabe“ oder „USB-Modem“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4192e-128">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="4192e-129">Aktivieren Sie die Datenfreigabe über USB.</span><span class="sxs-lookup"><span data-stu-id="4192e-129">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="4192e-130">Verbinden Sie Ihr Gerät mit dem HoloLens-USB-C-Port.</span><span class="sxs-lookup"><span data-stu-id="4192e-130">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="4192e-131">In den HoloLens 2-Netzwerkeinstellungen wird das Gerät automatisch als Ethernet-Verbindung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4192e-131">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
