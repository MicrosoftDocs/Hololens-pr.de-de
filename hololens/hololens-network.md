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
ms.openlocfilehash: 0f46ff4a1bef95d153d9fa93c746c8977dc49771
ms.sourcegitcommit: 47bc3b696936dd7011b3f9dd683deb872ed25b90
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2020
ms.locfileid: "10883149"
---
# <span data-ttu-id="676de-104">HoloLens mit einem Netzwerk verbinden</span><span class="sxs-lookup"><span data-stu-id="676de-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="676de-105">Für die Durchführung der meisten Aufgaben auf Ihrer HoloLens müssen Sie mit einem Netzwerk verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="676de-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="676de-106">Dieses Handbuch hilft Ihnen bei Folgendem:</span><span class="sxs-lookup"><span data-stu-id="676de-106">This guide will help you:</span></span>

- <span data-ttu-id="676de-107">Herstellen einer Verbindung mit einem Netzwerk über WLAN oder (nur für HoloLens 2) Ethernet über USB-C</span><span class="sxs-lookup"><span data-stu-id="676de-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="676de-108">Deaktivieren und erneutes Aktivieren von WLAN</span><span class="sxs-lookup"><span data-stu-id="676de-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="676de-109">Weitere Informationen finden Sie unter [Verwenden von HoloLens Offline](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="676de-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="676de-110">Erstmaliges Herstellen einer Verbindung</span><span class="sxs-lookup"><span data-stu-id="676de-110">Connecting for the first time</span></span>

<span data-ttu-id="676de-111">Bei der ersten Verwendung von HoloLens werden Sie beim Herstellen einer Verbindung mit einem WLAN-Netzwerk angeleitet.</span><span class="sxs-lookup"><span data-stu-id="676de-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="676de-112">Wenn beim Einrichten Probleme beim Herstellen einer Verbindung zu WLAN auftreten, stellen Sie sicher, dass es sich um ein offenes, kennwortgeschütztes Netzwerk oder ein Captive-Portalnetzwerk handelt.</span><span class="sxs-lookup"><span data-stu-id="676de-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="676de-113">Stellen Sie sicher, dass für das Netzwerk kein Zertifikat zum Herstellen einer Verbindung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="676de-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="676de-114">Nach dem Einrichten können Sie eine Verbindung zu anderen Arten von WLAN-Netzwerken herstellen.</span><span class="sxs-lookup"><span data-stu-id="676de-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

## <span data-ttu-id="676de-115">Herstellen einer Verbindung zu WLAN nach dem Einrichten</span><span class="sxs-lookup"><span data-stu-id="676de-115">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="676de-116">Führen Sie die **Startgeste** aus, und wählen Sie **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="676de-116">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="676de-117">Die Einstellungs-App wird automatisch vor Ihnen platziert.</span><span class="sxs-lookup"><span data-stu-id="676de-117">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="676de-118">Wählen Sie **Netzwerk und Internet** > **WLAN** aus.</span><span class="sxs-lookup"><span data-stu-id="676de-118">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="676de-119">Stellen Sie sicher, dass WLAN aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="676de-119">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="676de-120">Wenn Ihr Netzwerk nicht angezeigt wird, scrollen Sie die Liste nach unten.</span><span class="sxs-lookup"><span data-stu-id="676de-120">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="676de-121">Wählen Sie ein Netzwerk und dann **Verbinden** aus.</span><span class="sxs-lookup"><span data-stu-id="676de-121">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="676de-122">Wenn Sie zur Eingabe eines Netzwerkkennworts aufgefordert werden, geben Sie es ein, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="676de-122">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="676de-123">HoloLens verfügt über einen 802.11ac-fähiges 2x2-WLAN-Funkanschluss.</span><span class="sxs-lookup"><span data-stu-id="676de-123">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="676de-124">Das Verbinden von HoloLens mit einem WLAN-Netzwerk ähnelt dem Verbinden eines Windows 10-Desktops oder mobilen Geräts mit einem WLAN-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="676de-124">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![WLAN-Einstellungen für HoloLens](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="676de-126">Sie können auch bestätigen, dass Sie mit einem WLAN-Netzwerk verbunden sind, indem Sie den WLAN-Status im **Startmenü** überprüfen:</span><span class="sxs-lookup"><span data-stu-id="676de-126">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="676de-127">Öffnen Sie das **Startmenü**.</span><span class="sxs-lookup"><span data-stu-id="676de-127">Open the **Start** menu.</span></span>
1. <span data-ttu-id="676de-128">Suchen Sie oben links im **Startmenü** nach dem WLAN-Status.</span><span class="sxs-lookup"><span data-stu-id="676de-128">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="676de-129">Der Status von WLAN und die SSID des verbundenen Netzwerks werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="676de-129">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="676de-130">Behandeln von Problemen mit Ihrer WLAN-Verbindung</span><span class="sxs-lookup"><span data-stu-id="676de-130">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="676de-131">Wenn Sie Probleme beim Herstellen einer WLAN-Verbindung haben, lesen Sie [Ich kann keine WLAN-Verbindung herstellen](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="676de-131">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="676de-132">Melden Sie sich mit dem Gerät bei einem Unternehmens- oder Organisationskonto an, kann auch die Richtlinie für die mobile Geräteverwaltung (Mobile Device Management, MDM) gelten, wenn die Richtlinie von Ihrem IT-Administrator konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="676de-132">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="676de-133">VPN</span><span class="sxs-lookup"><span data-stu-id="676de-133">VPN</span></span>
<span data-ttu-id="676de-134">Eine VPN-Verbindung kann Ihnen dabei helfen, eine sicherere Verbindung herzustellen sowie auf das Netzwerk Ihres Unternehmens und das Internet zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="676de-134">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="676de-135">HoloLens2 unterstützt den integrierten VPN-Client und das VPN-Plug-In Universelle Windows-Plattform (UWP).</span><span class="sxs-lookup"><span data-stu-id="676de-135">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="676de-136">Unterstützte integrierte VPN-Protokolle:</span><span class="sxs-lookup"><span data-stu-id="676de-136">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="676de-137">IKEv2</span><span class="sxs-lookup"><span data-stu-id="676de-137">IKEv2</span></span>
- <span data-ttu-id="676de-138">L2TP</span><span class="sxs-lookup"><span data-stu-id="676de-138">L2TP</span></span>
- <span data-ttu-id="676de-139">PPTP</span><span class="sxs-lookup"><span data-stu-id="676de-139">PPTP</span></span>

<span data-ttu-id="676de-140">Wenn für die Authentifizierung des integrierten VPN-Clients ein Zertifikat verwendet wird, muss das erforderliche Clientzertifikat zum Benutzerzertifikatspeicher hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="676de-140">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="676de-141">Wenn Sie herausfinden möchten, ob das VPN-Plug-In eines Drittanbieters HoloLens2 unterstützt, wechseln Sie zu „Speicher“, um die VPN-App zu suchen, und überprüfen Sie, ob HoloLens als unterstütztes Gerät aufgeführt ist und ob die App auf der Seite „Systemanforderungen“ die ARM- oder ARM64-Architektur unterstützt.</span><span class="sxs-lookup"><span data-stu-id="676de-141">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="676de-142">HoloLens unterstützt nur Universelle Windows-Plattform-Anwendungen für VPN von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="676de-142">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

<span data-ttu-id="676de-143">VPN ist standardmäßig nicht aktiviert, kann aber durch Öffnen der App **Einstellungen** und Navigieren zu **„Netzwerk und Internet“ –> „VPN“** manuell aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="676de-143">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span> <span data-ttu-id="676de-144">VPN kann durch MDM über [Einstellungen/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) verwaltet und über die Richtlinie [Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="676de-144">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>
<span data-ttu-id="676de-145">Weitere Informationen zum [Konfigurieren von VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) finden Sie in [diesen Handbüchern](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="676de-145">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

## <span data-ttu-id="676de-146">Deaktivieren von WLAN auf HoloLens (1. Generation)</span><span class="sxs-lookup"><span data-stu-id="676de-146">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="676de-147">Verwenden der Einstellungs-App auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="676de-147">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="676de-148">Öffnen Sie das **Startmenü**.</span><span class="sxs-lookup"><span data-stu-id="676de-148">Open the **Start** menu.</span></span>
1. <span data-ttu-id="676de-149">Wählen Sie die **Einstellungs**-App im **Startmenü** oder in der Liste **Alle Apps** auf der rechten Seite des **Startmenüs** aus.</span><span class="sxs-lookup"><span data-stu-id="676de-149">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="676de-150">Die **Einstellungs**-App wird automatisch vor Ihnen platziert.</span><span class="sxs-lookup"><span data-stu-id="676de-150">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="676de-151">Wählen Sie **Netzwerk und Internet** aus.</span><span class="sxs-lookup"><span data-stu-id="676de-151">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="676de-152">Wählen Sie den WLAN-Schieberegler aus, um ihn in die Position **Off** (Aus) zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="676de-152">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="676de-153">Dadurch werden die HF-Komponenten des WLAN-Funkanschlusses ausgeschaltet und alle WLAN-Funktionen von HoloLens deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="676de-153">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="676de-154">Wenn der WLAN-Funkanschluss deaktiviert ist, kann HoloLens Ihre [Räume](hololens-spaces.md) nicht automatisch laden.</span><span class="sxs-lookup"><span data-stu-id="676de-154">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="676de-155">Schieben Sie den Schieberegler in die Stellung **On** (Ein), um das WLAN zu aktivieren und die WLAN-Funktion auf Microsoft HoloLens wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="676de-155">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="676de-156">Der ausgewählte WLAN-Funkstatus (**Ein** oder **Aus**) bleibt bei einem Neustart erhalten.</span><span class="sxs-lookup"><span data-stu-id="676de-156">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="676de-157">Identifizieren der IP-Adresse Ihrer HoloLens im WLAN-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="676de-157">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="676de-158">Mithilfe der Einstellungs-App</span><span class="sxs-lookup"><span data-stu-id="676de-158">By using the Settings app</span></span>

1. <span data-ttu-id="676de-159">Öffnen Sie das **Startmenü**.</span><span class="sxs-lookup"><span data-stu-id="676de-159">Open the **Start** menu.</span></span>
1. <span data-ttu-id="676de-160">Wählen Sie die **Einstellungs**-App im **Startmenü** oder in der Liste **Alle Apps** auf der rechten Seite des **Startmenüs** aus.</span><span class="sxs-lookup"><span data-stu-id="676de-160">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="676de-161">Die **Einstellungs**-App wird automatisch vor Ihnen platziert.</span><span class="sxs-lookup"><span data-stu-id="676de-161">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="676de-162">Wählen Sie **Netzwerk und Internet** aus.</span><span class="sxs-lookup"><span data-stu-id="676de-162">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="676de-163">Scrollen Sie nach unten unter die Liste der verfügbaren WLAN-Netzwerke und wählen Sie **Hardwareeigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="676de-163">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Hardwareeigenschaften in WLAN-Einstellungen](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="676de-165">Die IP-Adresse wird neben **IPv4-Adresse** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="676de-165">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="676de-166">Mithilfe von Sprachbefehlen</span><span class="sxs-lookup"><span data-stu-id="676de-166">By using voice commands</span></span>

<span data-ttu-id="676de-167">Je nach dem Build Ihres Geräts können Sie entweder mithilfe von integrierten Sprachbefehlen oder Cortana Ihre IP-Adresse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="676de-167">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="676de-168">Sprechen Sie bei Builds nach [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) „Wie lautet meine IP-Adresse?“</span><span class="sxs-lookup"><span data-stu-id="676de-168">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="676de-169">Dann wird sie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="676de-169">and it will be displayed.</span></span> <span data-ttu-id="676de-170">Sagen Sie bei früheren Builds oder HoloLens (1.Generation)„Hey Cortana, wie lautet meine IP-Adresse?”.</span><span class="sxs-lookup"><span data-stu-id="676de-170">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="676de-171">und Cortana wird Ihre IP-Adresse anzeigen und vorlesen.</span><span class="sxs-lookup"><span data-stu-id="676de-171">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="676de-172">Mithilfe des Windows-Geräteportals</span><span class="sxs-lookup"><span data-stu-id="676de-172">By using Windows Device Portal</span></span>

1. <span data-ttu-id="676de-173">Öffnen Sie in einem Webbrowser auf Ihrem PC das [Geräteportal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="676de-173">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="676de-174">Navigieren Sie zum Abschnitt **Netzwerk**.</span><span class="sxs-lookup"><span data-stu-id="676de-174">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="676de-175">In diesem Abschnitt werden Ihre IP-Adresse und andere Netzwerkinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="676de-175">This section displays your IP address and other network information.</span></span> <span data-ttu-id="676de-176">Mithilfe dieser Methode können Sie die IP-Adresse auf Ihren Entwicklungscomputer kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="676de-176">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
