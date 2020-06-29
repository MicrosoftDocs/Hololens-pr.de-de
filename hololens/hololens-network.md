---
title: Verbindung mit einem Netzwerk herstellen
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
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0bc5a5f7f3eaf3d811da055a7bda664fd3f0daff
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828416"
---
# <span data-ttu-id="97563-104">Verbindung mit einem Netzwerk herstellen</span><span class="sxs-lookup"><span data-stu-id="97563-104">Connect to a network</span></span>

<span data-ttu-id="97563-105">Für die Durchführung der meisten Aufgaben auf Ihrer HoloLens müssen Sie mit einem Netzwerk verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="97563-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="97563-106">Dieses Handbuch hilft Ihnen bei Folgendem:</span><span class="sxs-lookup"><span data-stu-id="97563-106">This guide will help you:</span></span>

- <span data-ttu-id="97563-107">Herstellen einer Verbindung mit einem Netzwerk über WLAN oder (nur für HoloLens 2) Ethernet über USB-C</span><span class="sxs-lookup"><span data-stu-id="97563-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="97563-108">Deaktivieren und erneutes Aktivieren von WLAN</span><span class="sxs-lookup"><span data-stu-id="97563-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="97563-109">Weitere Informationen finden Sie unter [Verwenden von HoloLens Offline](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="97563-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="97563-110">Erstmaliges Herstellen einer Verbindung</span><span class="sxs-lookup"><span data-stu-id="97563-110">Connecting for the first time</span></span>

<span data-ttu-id="97563-111">Wenn Sie Ihre HoloLens zum ersten Mal verwenden, werden Sie durch die Verbindung mit einem WLAN-Netzwerk geführt.</span><span class="sxs-lookup"><span data-stu-id="97563-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="97563-112">Wenn beim Einrichten Probleme beim Herstellen einer Verbindung zu WLAN auftreten, stellen Sie sicher, dass es sich um ein offenes, kennwortgeschütztes Netzwerk oder ein Captive-Portalnetzwerk handelt.</span><span class="sxs-lookup"><span data-stu-id="97563-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="97563-113">Stellen Sie sicher, dass für das Netzwerk kein Zertifikat zum Herstellen einer Verbindung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="97563-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="97563-114">Nach dem Einrichten können Sie eine Verbindung zu anderen Arten von WLAN-Netzwerken herstellen.</span><span class="sxs-lookup"><span data-stu-id="97563-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

## <span data-ttu-id="97563-115">Herstellen einer Verbindung zu WLAN nach dem Einrichten</span><span class="sxs-lookup"><span data-stu-id="97563-115">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="97563-116">Wählen Sie **Start** > **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="97563-116">Select **Start** > **Settings**.</span></span>
   - <span data-ttu-id="97563-117">*Nur HoloLens (1. Generation)*: Verwenden Sie Anvisieren, um die Einstellungs-App zu positionieren, und tippen Sie dann in die Luft, um sie zu platzieren, oder sagen Sie „Platzieren”.</span><span class="sxs-lookup"><span data-stu-id="97563-117">*HoloLens (1st gen) only*: Use your gaze to position the Settings app, then air tap to place it, or say "Place."</span></span>
1. <span data-ttu-id="97563-118">Wählen Sie **Netzwerk und Internet** > **WLAN** aus.</span><span class="sxs-lookup"><span data-stu-id="97563-118">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="97563-119">Wenn Ihr Netzwerk nicht angezeigt wird, scrollen Sie die Liste nach unten.</span><span class="sxs-lookup"><span data-stu-id="97563-119">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="97563-120">Wählen Sie ein Netzwerk und dann **Verbinden** aus.</span><span class="sxs-lookup"><span data-stu-id="97563-120">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="97563-121">Wenn Sie zur Eingabe eines Netzwerkkennworts aufgefordert werden, geben Sie es ein, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="97563-121">If you are prompted for a network password type it and then select **Next**.</span></span>

## <span data-ttu-id="97563-122">Herstellen einer Verbindung zu WLAN auf HoloLens (1. Generation)</span><span class="sxs-lookup"><span data-stu-id="97563-122">Connecting to Wi-Fi on HoloLens (1st gen)</span></span>

<span data-ttu-id="97563-123">HoloLens verfügt über einen 802.11ac-fähiges 2x2-WLAN-Funkanschluss.</span><span class="sxs-lookup"><span data-stu-id="97563-123">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="97563-124">Das Verbinden von HoloLens mit einem WLAN-Netzwerk ähnelt dem Verbinden eines Windows 10-Desktops oder mobilen Geräts mit einem WLAN-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="97563-124">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![WLAN-Einstellungen für HoloLens](./images/wifi-hololens-600px.jpg)

1. <span data-ttu-id="97563-126">Öffnen Sie das **Startmenü**.</span><span class="sxs-lookup"><span data-stu-id="97563-126">Open the **Start** menu.</span></span>
1. <span data-ttu-id="97563-127">Wählen Sie die Einstellungs-App im **Startmenü** aus oder aus der Liste **Alle apps** auf der rechten Seite des **Startmenüs** aus.</span><span class="sxs-lookup"><span data-stu-id="97563-127">Select the Settings app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="97563-128">Die Einstellungs-App wird automatisch vor Ihnen platziert.</span><span class="sxs-lookup"><span data-stu-id="97563-128">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="97563-129">Wählen Sie **Netzwerk und Internet** aus.</span><span class="sxs-lookup"><span data-stu-id="97563-129">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="97563-130">Stellen Sie sicher, dass WLAN aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="97563-130">Make sure Wi-Fi is turned on.</span></span>
1. <span data-ttu-id="97563-131">Wählen Sie in der Liste ein WLAN-Netzwerk aus.</span><span class="sxs-lookup"><span data-stu-id="97563-131">Select a Wi-Fi network from the list.</span></span>
1. <span data-ttu-id="97563-132">Geben Sie bei Bedarf das Kennwort für das WLAN-Netzwerk ein.</span><span class="sxs-lookup"><span data-stu-id="97563-132">If needed, type in the Wi-Fi network password.</span></span>

<span data-ttu-id="97563-133">Sie können auch bestätigen, dass Sie mit einem WLAN-Netzwerk verbunden sind, indem Sie den WLAN-Status im **Startmenü** überprüfen:</span><span class="sxs-lookup"><span data-stu-id="97563-133">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="97563-134">Öffnen Sie das **Startmenü**.</span><span class="sxs-lookup"><span data-stu-id="97563-134">Open the **Start** menu.</span></span>
1. <span data-ttu-id="97563-135">Suchen Sie oben links im **Startmenü** nach dem WLAN-Status.</span><span class="sxs-lookup"><span data-stu-id="97563-135">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="97563-136">Der Status von WLAN und die SSID des verbundenen Netzwerks werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="97563-136">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="97563-137">Behandeln von Problemen mit Ihrer WLAN-Verbindung</span><span class="sxs-lookup"><span data-stu-id="97563-137">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="97563-138">Wenn Sie Probleme beim Herstellen einer WLAN-Verbindung haben, lesen Sie [Ich kann keine WLAN-Verbindung herstellen](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="97563-138">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="97563-139">Melden Sie sich mit dem Gerät bei einem Unternehmens- oder Organisationskonto an, kann auch die Richtlinie für die mobile Geräteverwaltung (Mobile Device Management, MDM) gelten, wenn die Richtlinie von Ihrem IT-Administrator konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="97563-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="97563-140">Deaktivieren von WLAN auf HoloLens (1. Generation)</span><span class="sxs-lookup"><span data-stu-id="97563-140">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="97563-141">Verwenden der Einstellungs-App auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="97563-141">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="97563-142">Öffnen Sie das **Startmenü**.</span><span class="sxs-lookup"><span data-stu-id="97563-142">Open the **Start** menu.</span></span>
1. <span data-ttu-id="97563-143">Wählen Sie die **Einstellungs**-App im **Startmenü** oder in der Liste **Alle Apps** auf der rechten Seite des **Startmenüs** aus.</span><span class="sxs-lookup"><span data-stu-id="97563-143">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="97563-144">Die **Einstellungs**-App wird automatisch vor Ihnen platziert.</span><span class="sxs-lookup"><span data-stu-id="97563-144">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="97563-145">Wählen Sie **Netzwerk und Internet** aus.</span><span class="sxs-lookup"><span data-stu-id="97563-145">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="97563-146">Wählen Sie den WLAN-Schieberegler aus, um ihn in die Position **Off** (Aus) zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="97563-146">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="97563-147">Dadurch werden die HF-Komponenten des WLAN-Funkanschlusses ausgeschaltet und alle WLAN-Funktionen von HoloLens deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="97563-147">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="97563-148">Wenn der WLAN-Funkanschluss deaktiviert ist, kann HoloLens Ihre [Räume](hololens-spaces.md) nicht automatisch laden.</span><span class="sxs-lookup"><span data-stu-id="97563-148">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="97563-149">Schieben Sie den Schieberegler in die Stellung **On** (Ein), um das WLAN zu aktivieren und die WLAN-Funktion auf Microsoft HoloLens wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="97563-149">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="97563-150">Der ausgewählte WLAN-Funkstatus (**Ein** oder **Aus**) bleibt bei einem Neustart erhalten.</span><span class="sxs-lookup"><span data-stu-id="97563-150">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="97563-151">Identifizieren der IP-Adresse Ihrer HoloLens im WLAN-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="97563-151">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="97563-152">Mithilfe der Einstellungs-App</span><span class="sxs-lookup"><span data-stu-id="97563-152">By using the Settings app</span></span>

1. <span data-ttu-id="97563-153">Öffnen Sie das **Startmenü**.</span><span class="sxs-lookup"><span data-stu-id="97563-153">Open the **Start** menu.</span></span>
1. <span data-ttu-id="97563-154">Wählen Sie die **Einstellungs**-App im **Startmenü** oder in der Liste **Alle Apps** auf der rechten Seite des **Startmenüs** aus.</span><span class="sxs-lookup"><span data-stu-id="97563-154">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="97563-155">Die **Einstellungs**-App wird automatisch vor Ihnen platziert.</span><span class="sxs-lookup"><span data-stu-id="97563-155">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="97563-156">Wählen Sie **Netzwerk und Internet** aus.</span><span class="sxs-lookup"><span data-stu-id="97563-156">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="97563-157">Scrollen Sie nach unten unter die Liste der verfügbaren WLAN-Netzwerke und wählen Sie **Hardwareeigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="97563-157">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Hardwareeigenschaften in WLAN-Einstellungen](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="97563-159">Die IP-Adresse wird neben **IPv4-Adresse** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="97563-159">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="97563-160">Mithilfe von Cortana</span><span class="sxs-lookup"><span data-stu-id="97563-160">By using Cortana</span></span>

<span data-ttu-id="97563-161">Sagen Sie „Hey Cortana, wie lautet meine IP-Adresse?”</span><span class="sxs-lookup"><span data-stu-id="97563-161">Say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="97563-162">und Cortana wird Ihre IP-Adresse anzeigen und vorlesen.</span><span class="sxs-lookup"><span data-stu-id="97563-162">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="97563-163">Mithilfe des Windows-Geräteportals</span><span class="sxs-lookup"><span data-stu-id="97563-163">By using Windows Device Portal</span></span>

1. <span data-ttu-id="97563-164">Öffnen Sie in einem Webbrowser auf Ihrem PC das [Geräteportal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="97563-164">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="97563-165">Navigieren Sie zum Abschnitt **Netzwerk**.</span><span class="sxs-lookup"><span data-stu-id="97563-165">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="97563-166">In diesem Abschnitt werden Ihre IP-Adresse und andere Netzwerkinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="97563-166">This section displays your IP address and other network information.</span></span> <span data-ttu-id="97563-167">Mithilfe dieser Methode können Sie die IP-Adresse auf Ihren Entwicklungscomputer kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="97563-167">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
