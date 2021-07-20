---
title: Verbinden von HoloLens mit einem Netzwerk
description: Hier erhalten Sie Informationen dazu, wie Sie HoloLens einrichten, eine Verbindung mit dem Internet herstellen, und die IP-Adresse des Geräts identifizieren.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, WLAN, kabellos, Internet, IP, IP-Adresse
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: c2a2fe1a20a4e9baa194b1037ccb6649d324b990
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640218"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="0bcb4-104">Verbinden von HoloLens mit einem Netzwerk</span><span class="sxs-lookup"><span data-stu-id="0bcb4-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="0bcb4-105">Für die Durchführung der meisten Aufgaben auf Ihrer HoloLens müssen Sie mit einem Netzwerk verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="0bcb4-106">HoloLens enthält ein 802.11ac-fähigen, 2x2 WLAN-Funk. Das Herstellen einer Verbindung mit einem Netzwerk ähnelt dem Verbinden eines Windows 10-Desktop- oder mobilen Geräts mit einem WLAN-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="0bcb4-107">Dieses Handbuch wird Ihnen helfen:</span><span class="sxs-lookup"><span data-stu-id="0bcb4-107">This guide will help you:</span></span>

- <span data-ttu-id="0bcb4-108">Herstellen einer Verbindung mit einem Netzwerk über WLAN oder nur für HoloLens 2, Wi-Fi Direkt oder Ethernet über USB-C</span><span class="sxs-lookup"><span data-stu-id="0bcb4-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="0bcb4-109">Deaktivieren und erneutes Aktivieren von WLAN</span><span class="sxs-lookup"><span data-stu-id="0bcb4-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="0bcb4-110">Erfahren Sie mehr über die [Offline-Verwendung der HoloLens](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="0bcb4-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="0bcb4-111">Erstmaliges Herstellen einer Verbindung</span><span class="sxs-lookup"><span data-stu-id="0bcb4-111">Connecting for the first time</span></span>

<span data-ttu-id="0bcb4-112">Bei der ersten Verwendung von HoloLens werden Sie beim Herstellen einer Verbindung mit einem WLAN-Netzwerk angeleitet.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="0bcb4-113">Wenn während des Einrichtens Probleme beim Herstellen einer WLAN-Verbindung auftreten, stellen Sie sicher, dass es sich entweder um ein offenes, kennwortgeschütztes Netzwerk oder um ein Captive-Portalnetzwerk handelt.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="0bcb4-114">Stellen Sie außerdem sicher, dass für das Netzwerk kein Zertifikat zum Herstellen einer Verbindung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="0bcb4-115">Nach dem Einrichten können Sie eine Verbindung zu anderen Arten von WLAN-Netzwerken herstellen.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="0bcb4-116">Auf HoloLens 2 Geräten kann ein Benutzer auch einen [USB-C-zu-Ethernet-Adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) verwenden, um eine direkte Verbindung mit WLAN herzustellen, um die Einrichtung des Geräts zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="0bcb4-117">Sobald das Gerät eingerichtet wurde, kann ein Benutzer den Adapter entweder weiter verwenden oder das Gerät vom Adapter trennen und [nach der Einrichtung mit dem WLAN verbinden](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="0bcb4-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="0bcb4-118">Herstellen einer Verbindung zum WLAN nach dem Einrichten</span><span class="sxs-lookup"><span data-stu-id="0bcb4-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="0bcb4-119">Führen Sie die **Startgeste** aus und wählen Sie **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="0bcb4-120">Die Einstellungen-App wird automatisch vor Ihnen platziert.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="0bcb4-121">Wählen Sie **Netzwerk & Internet** > **WLAN** aus.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="0bcb4-122">Stellen Sie sicher, dass WLAN aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="0bcb4-123">Wenn Ihr Netzwerk nicht angezeigt wird, scrollen Sie in der Liste nach unten.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="0bcb4-124">Wählen Sie ein Netzwerk und dann **Verbinden** aus.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="0bcb4-125">Wenn Sie zur Eingabe eines Netzwerkkennworts aufgefordert werden, geben Sie es ein, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![WLAN-Einstellungen für HoloLens](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="0bcb4-127">Um zu bestätigen, dass Sie mit einem WLAN verbunden sind, überprüfen Sie den WLAN-Status im **Startmenü**:</span><span class="sxs-lookup"><span data-stu-id="0bcb4-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="0bcb4-128">Öffnen Sie das Menü **Start**.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="0bcb4-129">Suchen Sie oben links im **Startmenü** nach dem WLAN-Status.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="0bcb4-130">Der Status von WLAN und die SSID des verbundenen Netzwerks werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="0bcb4-131">Wenn Wi-Fi nicht verfügbar ist, können Sie auch eine [Verbindung mit Mobilfunk- und 5G-Netzwerken](hololens-cellular.md) herstellen.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](hololens-cellular.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bcb4-132">Die Benutzer können das WLAN-Roaming-Verhalten des HoloLens 2 absichtlich nicht optimieren.  **Die einzige Möglichkeit zum Aktualisieren der WLAN-Liste besteht im An- und Ausschalten des WLANs**.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="0bcb4-133">Dadurch werden viele Probleme verhindert, z. B. wenn ein Gerät bei einem Zugriffspunkt „hängenbleibt“, sobald dieser außer Reichweite ist.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="0bcb4-134">Verbinden von HoloLens mit einem Enterprise WLAN-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="0bcb4-134">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="0bcb4-135">WLAN-Profile von Unternehmen verwenden das Extensible Authentication Protocol (EAP) zur Authentifizierung von WLAN-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-135">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="0bcb4-136">Das HoloLens Enterprise WLAN-Profil kann über MDM oder mit einem Bereitstellungspaket das von [Windows Konfigurationsdesigner](/windows/configuration/provisioning-packages/provisioning-packages) erstellt wurde konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-136">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="0bcb4-137">Konfigurationsanweisungen für das von Microsoft Intune verwaltete Gerät finden Sie unter [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile).</span><span class="sxs-lookup"><span data-stu-id="0bcb4-137">For Microsoft Intune managed device, refer to [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="0bcb4-138">Um ein WLAN-Bereitstellungspaket in WCD zu erstellen, ist eine vorkonfigurierte WLAN-Profil.XML-Datei erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-138">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="0bcb4-139">Hier ist ein Beispiel für ein WLAN-Profil für ein Unternehmens-WPA2 mit EAP-TLS-Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="0bcb4-139">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


<span data-ttu-id="0bcb4-140">Je nach EAP-Typ müssen möglicherweise das Server-Root-CA-Zertifikat und das Client-Zertifikat auf dem Gerät bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-140">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="0bcb4-141">Zusätzliche Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="0bcb4-141">Additional resources:</span></span>

- <span data-ttu-id="0bcb4-142">WLANv1Profile Schema: [[MS-GPWL]: Kabellose LAN Profile v1 Schema | Microsoft-Dokumentation](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="0bcb4-142">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="0bcb4-143">EAP-TLS-Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft-Dokumentation](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="0bcb4-143">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

<span data-ttu-id="0bcb4-144">Lesen Sie unsere Seite [Problembehandlung](hololens2-enterprise-troubleshooting.md#), wenn Beim Herstellen einer Verbindung mit Ihrem WLAN Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-144">Check our [Troubleshooting](hololens2-enterprise-troubleshooting.md#) page if you are having problems connecting to your Wi-Fi.</span></span>

## <a name="configure-network-proxy"></a><span data-ttu-id="0bcb4-145">Konfigurieren des Netzwerkproxys</span><span class="sxs-lookup"><span data-stu-id="0bcb4-145">Configure Network Proxy</span></span>

<span data-ttu-id="0bcb4-146">In diesem Abschnitt wird der Netzwerkproxy für das HoloLens-Betriebssystem und UWP-Apps (Universelle Windows-Plattform) mit Windows HTTP-Stapel behandelt.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-146">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="0bcb4-147">Anwendungen, die nicht Windows HTTP-Stapel verwenden, verfügen möglicherweise über eine eigene Proxykonfiguration und -verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-147">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="0bcb4-148">Proxykonfigurationen</span><span class="sxs-lookup"><span data-stu-id="0bcb4-148">Proxy Configurations</span></span> 

- <span data-ttu-id="0bcb4-149">Proxy Autokonfigurationsskript (PAC): Eine [PAC-Datei](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (öffnet eine Nicht-Microsoft-Website) enthält eine JavaScript-Funktion FindProxyForURL(url, host).</span><span class="sxs-lookup"><span data-stu-id="0bcb4-149">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="0bcb4-150">Statischer Proxy: in Form von Server:Port.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-150">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="0bcb4-151">WebProxy Auto-Discovery Protocol (WPAD): Geben Sie die URL der Proxykonfigurationsdatei über DHCP oder DNS an.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-151">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="0bcb4-152">Bereitstellungsmethoden für Proxys</span><span class="sxs-lookup"><span data-stu-id="0bcb4-152">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="0bcb4-153">Es gibt drei Möglichkeiten zum Bereitstellen von Proxys:</span><span class="sxs-lookup"><span data-stu-id="0bcb4-153">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="0bcb4-154">**Benutzeroberfläche „Einstellungen“:**</span><span class="sxs-lookup"><span data-stu-id="0bcb4-154">**Settings UI:**</span></span> 
    1. <span data-ttu-id="0bcb4-155">Proxy pro Benutzer (20H2 oder früher):</span><span class="sxs-lookup"><span data-stu-id="0bcb4-155">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="0bcb4-156">Öffnen Sie das Startmenü und wählen Sie „Einstellungen“ aus.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-156">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="0bcb4-157">Wählen Sie „Netzwerk & Internet“ und dann „Proxy“ aus dem linken Menü.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-157">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="0bcb4-158">Scrollen Sie nach unten zu „Manuelle Proxyeinrichtung“, und klicken Sie bei „Proxyserver verwenden“ auf „Ein“.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-158">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="0bcb4-159">Geben Sie die IP-Adresse des Proxyservers ein.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-159">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="0bcb4-160">Geben Sie die Portnummer ein.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-160">Enter the port number.</span></span>
        6. <span data-ttu-id="0bcb4-161">Klicken Sie auf Speichern.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-161">Click Save.</span></span>
      1. <span data-ttu-id="0bcb4-162">WLAN-Proxy (21H1 oder höher):</span><span class="sxs-lookup"><span data-stu-id="0bcb4-162">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="0bcb4-163">Öffnen Sie das Startmenü, und wechseln Sie zur Seite der WLAN-Eigenschaften Ihres Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-163">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="0bcb4-164">Scrollen Sie nach unten zu Proxy</span><span class="sxs-lookup"><span data-stu-id="0bcb4-164">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="0bcb4-165">Wechseln Sie zu Manuelles Setup</span><span class="sxs-lookup"><span data-stu-id="0bcb4-165">Change to Manual Setup</span></span>
          1. <span data-ttu-id="0bcb4-166">Geben Sie die IP-Adresse des Proxyservers ein.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-166">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="0bcb4-167">Geben Sie die Portnummer ein.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-167">Enter the port number.</span></span>
          1. <span data-ttu-id="0bcb4-168">Klicken Sie auf „Übernehmen“.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-168">Click Apply.</span></span>
        
 2. <span data-ttu-id="0bcb4-169">**MDM**</span><span class="sxs-lookup"><span data-stu-id="0bcb4-169">**MDM**</span></span> 
     1. <span data-ttu-id="0bcb4-170">Intune: Verwenden Sie diese [Schritte](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile), um den Proxy in Intune zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-170">Intune - Use these [steps](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="0bcb4-171">Sie müssen im Abschnitt nach unten scrollen.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-171">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="0bcb4-172">Andere MDM-Lösungen von Drittanbietern: Verwenden Sie einen [WLAN-CSP](/windows/client-management/mdm/wifi-csp).</span><span class="sxs-lookup"><span data-stu-id="0bcb4-172">Other 3rd party MDM solutions - Use a [WiFi CSP](/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="0bcb4-173">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="0bcb4-173">**PPKG**</span></span> 
    1. <span data-ttu-id="0bcb4-174">Öffnen Sie den Windows-Konfigurationsdesigner</span><span class="sxs-lookup"><span data-stu-id="0bcb4-174">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="0bcb4-175">Klicken Sie auf Erweiterte Bereitstellung, geben Sie den Namen für Ihr neues Project ein und klicken Sie auf „Weiter“.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-175">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="0bcb4-176">Wählen Windows Holographic (HoloLens 2) aus, und klicken Sie auf „Weiter“.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-176">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="0bcb4-177">Importieren Sie Ihr PPKG (optional), und klicken Sie auf „Fertig stellen“.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-177">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="0bcb4-178">Erweitern Sie Laufzeiteinstellungen -> Verbindungsprofile -> WLAN -> WLAN-Proxy.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-178">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="0bcb4-179">Geben Sie die SSID Ihres WLAN-Netzwerks ein, und klicken Sie auf „Hinzufügen“.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-179">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="0bcb4-180">Wählen Sie Ihr WLAN-Netzwerk in dem linken Fenster aus, und geben Sie Ihre gewünschten Anpassungen ein.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-180">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="0bcb4-181">Die aktivierten Anpassungen werden im linken Menü in Fettschrift angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-181">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="0bcb4-182">Klicken Sie auf „Speichern und Schließen“.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-182">Click Save and Exit.</span></span>
    1. <span data-ttu-id="0bcb4-183">[Anwenden](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) des Bereitstellungspakets auf HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-183">[Apply](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="0bcb4-184">[CSPs](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) liegen vielen der Verwaltungsaufgaben und Richtlinien für Windows 10 in Microsoft Intune und Microsoft-fremden MDM-Dienstanbietern zugrunde.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-184">[CSPs](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="0bcb4-185">Sie können auch den [Windows-Konfigurationsdesigner](/windows/configuration/provisioning-packages/provisioning-install-icd) verwenden, um ein [Bereitstellungspaket](/windows/configuration/provisioning-packages/provisioning-packages) zu erstellen und es auf HoloLens 2 anwenden.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-185">You can also use [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="0bcb4-186">Die wahrscheinlichsten CSPs, die auf Ihre HoloLens 2 angewendet werden, sind:</span><span class="sxs-lookup"><span data-stu-id="0bcb4-186">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="0bcb4-187">[WLAN-CSP](/windows/client-management/mdm/wifi-csp): Pro Profil WLAN-Proxy</span><span class="sxs-lookup"><span data-stu-id="0bcb4-187">[WiFi CSP](/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="0bcb4-188">Andere in HoloLens-Geräten unterstützte CSPs</span><span class="sxs-lookup"><span data-stu-id="0bcb4-188">Other CSPs supported in HoloLens devices</span></span>](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="0bcb4-189">VPN</span><span class="sxs-lookup"><span data-stu-id="0bcb4-189">VPN</span></span>
<span data-ttu-id="0bcb4-190">Eine VPN-Verbindung kann Ihnen dabei helfen, eine sicherere Verbindung herzustellen sowie auf das Netzwerk Ihres Unternehmens und das Internet zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-190">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="0bcb4-191">HoloLens 2 unterstützt den integrierten VPN-Client und das VPN-Plug-In Universelle Windows-Plattform (UWP).</span><span class="sxs-lookup"><span data-stu-id="0bcb4-191">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="0bcb4-192">Unterstützt integrierte VPN-Protokolle:</span><span class="sxs-lookup"><span data-stu-id="0bcb4-192">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="0bcb4-193">IKEv2</span><span class="sxs-lookup"><span data-stu-id="0bcb4-193">IKEv2</span></span>
- <span data-ttu-id="0bcb4-194">L2TP</span><span class="sxs-lookup"><span data-stu-id="0bcb4-194">L2TP</span></span>
- <span data-ttu-id="0bcb4-195">PPTP</span><span class="sxs-lookup"><span data-stu-id="0bcb4-195">PPTP</span></span>

<span data-ttu-id="0bcb4-196">Wenn für die Authentifizierung des integrierten VPN-Clients ein Zertifikat verwendet wird, muss das erforderliche Clientzertifikat zum Benutzerzertifikatspeicher hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-196">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="0bcb4-197">Wenn Sie herausfinden möchten, ob das VPN-Plug-In eines Drittanbieters HoloLens 2 unterstützt, wechseln Sie zu „Speicher“, um die VPN-App zu suchen, und überprüfen Sie, ob HoloLens als unterstütztes Gerät aufgeführt ist und ob die App auf der Seite „Systemanforderungen“ die ARM- oder ARM64-Architektur unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-197">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="0bcb4-198">HoloLens unterstützt nur Universelle Windows-Plattform-Anwendungen für VPN von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-198">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="0bcb4-199">VPN kann von der MDM über [Einstellungen/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) verwaltet und über die [Vpnv2-csp-Richtlinie](/windows/client-management/mdm/vpnv2-csp) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-199">VPN can be managed by MDM via [Settings/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="0bcb4-200">Erfahren Sie mehr über das [Konfigurieren eines VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) mit [ diesen Leitfäden](/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="0bcb4-200">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="0bcb4-201">VPN über die Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="0bcb4-201">VPN via UI</span></span>

<span data-ttu-id="0bcb4-202">VPN ist standardmäßig nicht aktiviert, kann aber durch Öffnen der App **Einstellungen** und Navigieren zu **Netzwerk & Internet -> VPN** manuell aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-202">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="0bcb4-203">Auswählen eines VPN-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-203">Select a VPN provider.</span></span>
1. <span data-ttu-id="0bcb4-204">Erstellen eines Verbindungsnamen.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-204">Create a connection name.</span></span> 
1. <span data-ttu-id="0bcb4-205">Eingeben Ihres Servernamen oder Ihrer Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-205">Enter your server name or address.</span></span>
1. <span data-ttu-id="0bcb4-206">Auswählen des VPN-Typs.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-206">Select the VPN type.</span></span>
1. <span data-ttu-id="0bcb4-207">Auswählen der Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-207">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="0bcb4-208">Fügen Sie optional Benutzername und Kennwort hinzu.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-208">Optionally add user name and password.</span></span>
1. <span data-ttu-id="0bcb4-209">Anwenden der VPN-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-209">Apply the VPN settings.</span></span> 

![HoloLens VPN-Einstellungen](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="0bcb4-211">VPN über Bereitstellungspaket einstellen</span><span class="sxs-lookup"><span data-stu-id="0bcb4-211">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="0bcb4-212">In unserer Windows Holographic Version 20H2 haben wir ein Problem mit der Proxy-Konfiguration für die VPN-Verbindung behoben.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-212">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="0bcb4-213">Wenn Sie diesen Datenstrom verwenden möchten, aktualisieren Sie Ihre Geräte bitte auf diesen Build.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-213">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="0bcb4-214">Starten Sie den Windows Konfigurationsdesigner.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-214">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="0bcb4-215">Klicken Sie auf **Bereitstellung von HoloLens Geräten**, wählen Sie dann Zielgerät und **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-215">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="0bcb4-216">Geben Sie den Paketnamen und Pfad ein.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-216">Enter package name and path.</span></span>
1. <span data-ttu-id="0bcb4-217">Klicken Sie auf **Wechseln zum erweiterten Editor**.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-217">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="0bcb4-218">Öffnen Sie **Laufzeiteinstellungen** -> **Verbindungsprofile** ->  **VPN** -> **VPN-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-218">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="0bcb4-219">Configure VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="0bcb4-219">Configure VPNProfileName</span></span>
1. <span data-ttu-id="0bcb4-220">Wählen Sie den Profiltyp aus: **Nativ** oder **Drittanbieter**.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-220">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="0bcb4-221">Wählen Sie unter Natives Profil die Option **NativeProtocolType** und konfigurieren Sie dann Server, Routing-Richtlinie, Authentifizierungstyp und andere Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-221">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="0bcb4-222">Konfigurieren Sie für „Drittanbieter“-Profile Server-URL, VPN-Plug-in-App-Paket Familienname (es sind nur 3 vordefiniert) und benutzerdefinierte Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-222">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="0bcb4-223">Exportieren Sie Ihr Paket.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-223">Export your package.</span></span>
1. <span data-ttu-id="0bcb4-224">Verbinden Sie Ihr HoloLens und kopieren Sie die .ppkg-Datei auf das Gerät.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-224">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="0bcb4-225">Wenden Sie die VPN-.ppkg auf der HoloLens an, indem Sie das Startmenü öffnen und **Einstellungen** -> **Konto** -> **Geschäfts- oder Schulzugang** -> **Bereitstellungspaket hinzufügen oder entfernen** -> „Wählen Sie Ihr VPN Paket“ auswählen.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-225">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="0bcb4-226">Einrichten eines VPN über Intune</span><span class="sxs-lookup"><span data-stu-id="0bcb4-226">Setting up VPN via Intune</span></span>
<span data-ttu-id="0bcb4-227">Folgen Sie einfach der Intune-Anleitung um anzufangen.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-227">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="0bcb4-228">Beachten Sie bei der Durchführung dieser Schritte die eingebauten VPN-Protokolle, die HoloLens-Geräte unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-228">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="0bcb4-229">[Erstellen von VPN-Profilen zum Herstellen einer Verbindung mit VPN-Servern in Intune](/mem/intune/configuration/vpn-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="0bcb4-229">[Create VPN profiles to connect to VPN servers in Intune](/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="0bcb4-230">[Geräteeinstellungen für Windows 10 und Windows Holographic zum Hinzuzufügen von VPN-Verbindungen mit Intune](/mem/intune/configuration/vpn-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="0bcb4-230">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="0bcb4-231">Wenn Sie fertig sind, denken Sie bitte daran, das Sie das [Profil zuweisen](/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="0bcb4-231">When done please remember to [assign the profile](/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="0bcb4-232">VPN über die MDM-Lösungen von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="0bcb4-232">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="0bcb4-233">Beispiel für eine VPN-Verbindung von Drittanbietern:</span><span class="sxs-lookup"><span data-stu-id="0bcb4-233">3rd party VPN connection example:</span></span>
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

<span data-ttu-id="0bcb4-234">Natives IKEv2-VPN-Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0bcb4-234">Native IKEv2 VPN example:</span></span>
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="0bcb4-235">WLAN auf HoloLens (1. Generation) deaktivieren</span><span class="sxs-lookup"><span data-stu-id="0bcb4-235">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="0bcb4-236">Verwenden der Einstellungen-App auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="0bcb4-236">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="0bcb4-237">Öffnen Sie das Menü **Start**.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-237">Open the **Start** menu.</span></span>
1. <span data-ttu-id="0bcb4-238">Wählen Sie die App **Einstellungen** unter **Start** oder aus der Liste **Alle Apps** rechts im **Startmenü** aus.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-238">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="0bcb4-239">Die App **Einstellungen** wird automatisch vor Ihnen platziert.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-239">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="0bcb4-240">Wählen Sie **Netzwerk & Internet** aus.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-240">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="0bcb4-241">Wählen Sie den WLAN-Schieberegler aus, schieben Sie ihn auf **Aus**.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-241">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="0bcb4-242">Dadurch werden die HF-Komponenten des WLAN-Funks ausgeschaltet und alle WLAN-Funktionen von HoloLens deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-242">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="0bcb4-243">Wenn der WLAN-Funk deaktiviert ist, kann HoloLens Ihre [Räume](hololens-spaces.md) nicht automatisch laden.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-243">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="0bcb4-244">Schieben Sie den Schieberegler in die Stellung **Ein**, um das WLAN zu aktivieren und die WLAN-Funktion auf Microsoft HoloLens wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-244">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="0bcb4-245">Der ausgewählte WLAN-Funkstatus (**Ein** oder **Aus**) bleibt bei einem Neustart erhalten.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-245">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="0bcb4-246">Identifizieren der IP-Adresse Ihrer HoloLens im WLAN-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="0bcb4-246">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="0bcb4-247">Mit der Einstellungen-App</span><span class="sxs-lookup"><span data-stu-id="0bcb4-247">By using the Settings app</span></span>

1. <span data-ttu-id="0bcb4-248">Öffnen Sie das Menü **Start**.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-248">Open the **Start** menu.</span></span>
1. <span data-ttu-id="0bcb4-249">Wählen Sie die App **Einstellungen** unter **Start** oder aus der Liste **Alle Apps** rechts im **Startmenü** aus.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-249">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="0bcb4-250">Die App **Einstellungen** wird automatisch vor Ihnen platziert.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-250">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="0bcb4-251">Wählen Sie **Netzwerk & Internet** aus.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-251">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="0bcb4-252">Scrollen Sie nach unten unter die Liste der verfügbaren WLAN-Netzwerke und wählen Sie **Hardwareeigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-252">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Hardwareeigenschaften in WLAN-Einstellungen](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="0bcb4-254">Die IP-Adresse wird neben der **IPv4-Adresse** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-254">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="0bcb4-255">Mit Sprachbefehlen</span><span class="sxs-lookup"><span data-stu-id="0bcb4-255">By using voice commands</span></span>

<span data-ttu-id="0bcb4-256">Je nach Ihrem Geräte-Build können Sie entweder mit integrierten Sprachbefehlen oder Cortana Ihre IP-Adresse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-256">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="0bcb4-257">Bei Builds nach [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) sagen Sie „Wie lautet meine IP-Adresse?“</span><span class="sxs-lookup"><span data-stu-id="0bcb4-257">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="0bcb4-258">und sie wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-258">and it will be displayed.</span></span> <span data-ttu-id="0bcb4-259">Sagen Sie bei früheren Builds oder HoloLens (1. Generation): „Hey Cortana, wie lautet meine IP-Adresse?“,</span><span class="sxs-lookup"><span data-stu-id="0bcb4-259">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="0bcb4-260">und Cortana wird Ihre IP-Adresse anzeigen und vorlesen.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-260">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="0bcb4-261">Mit dem Windows-Geräteportals</span><span class="sxs-lookup"><span data-stu-id="0bcb4-261">By using Windows Device Portal</span></span>

1. <span data-ttu-id="0bcb4-262">Öffnen Sie in einem Webbrowser auf Ihrem PC das [Geräteportal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="0bcb4-262">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="0bcb4-263">Navigieren Sie zum Abschnitt **Netzwerk**.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-263">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="0bcb4-264">In diesem Abschnitt werden Ihre IP-Adresse und andere Netzwerkinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-264">This section displays your IP address and other network information.</span></span> <span data-ttu-id="0bcb4-265">Mit dieser Methode können Sie die IP-Adresse auf Ihren Entwicklungs-PC kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-265">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="0bcb4-266">IP-Adresse auf statische Adresse ändern</span><span class="sxs-lookup"><span data-stu-id="0bcb4-266">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="0bcb4-267">Mit Einstellungen</span><span class="sxs-lookup"><span data-stu-id="0bcb4-267">By using Settings</span></span>
 
1. <span data-ttu-id="0bcb4-268">Öffnen Sie das Menü **Start**.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-268">Open the **Start** menu.</span></span>
1. <span data-ttu-id="0bcb4-269">Wählen Sie die App **Einstellungen** unter **Start** oder aus der Liste **Alle Apps** rechts im **Startmenü** aus.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-269">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="0bcb4-270">Die App **Einstellungen** wird automatisch vor Ihnen platziert.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-270">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="0bcb4-271">Wählen Sie **Netzwerk & Internet** aus.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-271">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="0bcb4-272">Scrollen Sie nach unten unter die Liste der verfügbaren WLAN-Netzwerke und wählen Sie **Hardwareeigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-272">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="0bcb4-273">Ändern Sie das erste Feld auf **Manuell** im Fenster **IP-Einstellungen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-273">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="0bcb4-274">Geben Sie die gewünschte IP-Konfiguration in die verbleibenden Felder ein und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-274">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="0bcb4-275">Mit dem Windows-Geräteportals</span><span class="sxs-lookup"><span data-stu-id="0bcb4-275">By using Windows Device Portal</span></span>

1. <span data-ttu-id="0bcb4-276">Öffnen Sie in einem Webbrowser auf Ihrem PC das [Geräteportal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="0bcb4-276">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="0bcb4-277">Navigieren Sie zum Abschnitt **Netzwerk**.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-277">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="0bcb4-278">Wählen Sie die Schaltfläche **IPv4-Konfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-278">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="0bcb4-279">Wählen Sie **Verwenden der folgenden IP-Adresse** aus und geben Sie die gewünschte TCP/IP-Konfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-279">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="0bcb4-280">Wählen **Verwenden der folgenden DNS-Serveradressen** aus und geben Sie bei Bedarf die bevorzugten und alternativen DNS-Serveradressen ein.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-280">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="0bcb4-281">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="0bcb4-281">Click **Save**.</span></span> 
