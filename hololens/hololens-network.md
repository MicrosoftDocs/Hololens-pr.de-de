---
title: HoloLens mit einem Netzwerk verbinden
description: Hier erhalten Sie Informationen dazu, wie Sie HoloLens einrichten, eine Verbindung mit dem Internet herstellen, und die IP-Adresse des Geräts identifizieren.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, WLAN, drahtlos, Internet, IP, IP-Adresse
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 6d11ae0907aa82df71d7c86bb37996dcce71d845
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283976"
---
# <span data-ttu-id="fb9e6-104">HoloLens mit einem Netzwerk verbinden</span><span class="sxs-lookup"><span data-stu-id="fb9e6-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="fb9e6-105">Für die Durchführung der meisten Aufgaben auf Ihrer HoloLens müssen Sie mit einem Netzwerk verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="fb9e6-106">Dieses Handbuch hilft Ihnen bei Folgendem:</span><span class="sxs-lookup"><span data-stu-id="fb9e6-106">This guide will help you:</span></span>

- <span data-ttu-id="fb9e6-107">Herstellen einer Verbindung mit einem Netzwerk über WLAN oder (nur für HoloLens 2) Ethernet über USB-C</span><span class="sxs-lookup"><span data-stu-id="fb9e6-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="fb9e6-108">Deaktivieren und erneutes Aktivieren von WLAN</span><span class="sxs-lookup"><span data-stu-id="fb9e6-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="fb9e6-109">Weitere Informationen finden Sie unter [Verwenden von HoloLens Offline](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="fb9e6-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="fb9e6-110">Erstmaliges Herstellen einer Verbindung</span><span class="sxs-lookup"><span data-stu-id="fb9e6-110">Connecting for the first time</span></span>

<span data-ttu-id="fb9e6-111">Bei der ersten Verwendung von HoloLens werden Sie beim Herstellen einer Verbindung mit einem WLAN-Netzwerk angeleitet.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="fb9e6-112">Wenn beim Einrichten Probleme beim Herstellen einer Verbindung zu WLAN auftreten, stellen Sie sicher, dass es sich um ein offenes, kennwortgeschütztes Netzwerk oder ein Captive-Portalnetzwerk handelt.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="fb9e6-113">Stellen Sie sicher, dass für das Netzwerk kein Zertifikat zum Herstellen einer Verbindung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="fb9e6-114">Nach dem Einrichten können Sie eine Verbindung zu anderen Arten von WLAN-Netzwerken herstellen.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="fb9e6-115">Auf HoloLens2-Geräten kann ein Benutzer auch über einen [USB-C-zu-Ethernet-Adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) eine direkte Verbindung zu WLAN herstellen, um die Einrichtung des Geräts zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-115">On HoloLens 2 devices a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="fb9e6-116">Sobald das Gerät eingerichtet wurde, kann ein Benutzer den Adapter entweder weiter verwenden oder das Gerät vom Adapter trennen und [nach dem Einrichten eine Verbindung zu WLAN herstellen](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="fb9e6-116">Once the device has been set up a user may continue to user the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <span data-ttu-id="fb9e6-117">Herstellen einer Verbindung zu WLAN nach dem Einrichten</span><span class="sxs-lookup"><span data-stu-id="fb9e6-117">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="fb9e6-118">Führen Sie die **Startgeste** aus, und wählen Sie **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-118">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="fb9e6-119">Die Einstellungs-App wird automatisch vor Ihnen platziert.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-119">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="fb9e6-120">Wählen Sie **Netzwerk und Internet** > **WLAN** aus.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-120">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="fb9e6-121">Stellen Sie sicher, dass WLAN aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-121">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="fb9e6-122">Wenn Ihr Netzwerk nicht angezeigt wird, scrollen Sie die Liste nach unten.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-122">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="fb9e6-123">Wählen Sie ein Netzwerk und dann **Verbinden** aus.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-123">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="fb9e6-124">Wenn Sie zur Eingabe eines Netzwerkkennworts aufgefordert werden, geben Sie es ein, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-124">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="fb9e6-125">HoloLens verfügt über einen 802.11ac-fähiges 2x2-WLAN-Funkanschluss.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-125">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="fb9e6-126">Das Verbinden von HoloLens mit einem WLAN-Netzwerk ähnelt dem Verbinden eines Windows 10-Desktops oder mobilen Geräts mit einem WLAN-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-126">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![WLAN-Einstellungen für HoloLens](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="fb9e6-128">Sie können auch bestätigen, dass Sie mit einem WLAN-Netzwerk verbunden sind, indem Sie den WLAN-Status im **Startmenü** überprüfen:</span><span class="sxs-lookup"><span data-stu-id="fb9e6-128">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="fb9e6-129">Öffnen Sie das **Startmenü**.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-129">Open the **Start** menu.</span></span>
1. <span data-ttu-id="fb9e6-130">Suchen Sie oben links im **Startmenü** nach dem WLAN-Status.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-130">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="fb9e6-131">Der Status von WLAN und die SSID des verbundenen Netzwerks werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-131">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="fb9e6-132">Behandeln von Problemen mit Ihrer WLAN-Verbindung</span><span class="sxs-lookup"><span data-stu-id="fb9e6-132">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="fb9e6-133">Wenn Sie Probleme beim Herstellen einer WLAN-Verbindung haben, lesen Sie [Ich kann keine WLAN-Verbindung herstellen](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="fb9e6-133">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="fb9e6-134">Melden Sie sich mit dem Gerät bei einem Unternehmens- oder Organisationskonto an, kann auch die Richtlinie für die mobile Geräteverwaltung (Mobile Device Management, MDM) gelten, wenn die Richtlinie von Ihrem IT-Administrator konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-134">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="fb9e6-135">HoloLens mit Enterprise WLAN-Netzwerk verbinden</span><span class="sxs-lookup"><span data-stu-id="fb9e6-135">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="fb9e6-136">Enterprise WLAN-Profile verwenden das Extensible Authentication Protocol (EAP) zur Authentifizierung von WLAN-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-136">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="fb9e6-137">Das HoloLens Enterprise WLAN-Profil kann über MDM oder ein mit [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) erstelltes Bereitstellungspaket konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-137">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="fb9e6-138">Konfigurationsanweisungen für das von Microsoft Intune verwaltete Gerät finden Sie unter [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile).</span><span class="sxs-lookup"><span data-stu-id="fb9e6-138">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="fb9e6-139">Um ein WLAN-Bereitstellungspaket in WCD zu erstellen, ist eine vorkonfigurierte WLAN-Profil-XML-Datei erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-139">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="fb9e6-140">Hier ist ein Beispiel für ein WLAN-Profil für WPA2-Enterprise mit EAP-TLS-Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="fb9e6-140">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="fb9e6-141">Je nach EAP-Typ müssen möglicherweise das Server-Root-CA-Zertifikat und das Client-Zertifikat auf dem Gerät bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-141">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="fb9e6-142">Weitere Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="fb9e6-142">Additional resources:</span></span>

- <span data-ttu-id="fb9e6-143">WLANv1Profil-Schema: [[MS-GPWL]: Schema des WLAN-Profils v1 | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="fb9e6-143">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="fb9e6-144">EAP-TLS-Schema: [[MS-GPWL]: Microsoft EAP TLS-Schema | Microsoft Docs ](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="fb9e6-144">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

### <span data-ttu-id="fb9e6-145">EAP-Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="fb9e6-145">EAP Troubleshooting</span></span>

1. <span data-ttu-id="fb9e6-146">Überprüfen Sie noch einmal, ob das WLAN-Profil die richtigen Einstellungen hat:</span><span class="sxs-lookup"><span data-stu-id="fb9e6-146">Double check Wi-Fi profile has right settings:</span></span>
   1. <span data-ttu-id="fb9e6-147">EAP-Typ ist ordnungsgemäß konfiguriert, allgemeine EAP-Typen: EAP-TLS (13), EAP-TTLS (21) und PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="fb9e6-147">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
   1. <span data-ttu-id="fb9e6-148">Der WLAN-SSID-Name ist richtig und stimmt mit der HEX-Zeichenfolge überein.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-148">Wi-Fi SSID name is right and matches with HEX string.</span></span>
   1. <span data-ttu-id="fb9e6-149">Für EAP-TLS enthält TrustedRootCA den SHA-1-Hash des Zertifikats der vertrauenswürdigen Stammzertifizierungsstelle von Server&#39;.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-149">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server&#39;s trusted root CA certificate.</span></span> <span data-ttu-id="fb9e6-150">Auf Windows-PC zeigt der Befehl &quot;certutil.exe -dump cert\_file\_name&quot; eine SHA-1-Hash-Zeichenfolge des Zertifikats&#39;s SHA-1.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-150">On Windows PC &quot;certutil.exe -dump cert\_file\_name&quot; command will show a certificate&#39;s SHA-1 hash string.</span></span>
1. <span data-ttu-id="fb9e6-151">Sammeln Sie die Erfassung von Netzwerkpaketen auf den Protokollen des Access Points oder des Controllers oder des AAA-Servers, um herauszufinden, wo die EAP-Sitzung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-151">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
   1. <span data-ttu-id="fb9e6-152">Wenn die von HoloLens bereitgestellte EAP-Identität nicht erwartet wird, prüfen Sie, ob die Identität über das WLAN-Profil oder das Client-Zertifikat korrekt bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-152">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
   1. <span data-ttu-id="fb9e6-153">Wenn der Server das HoloLens-Client-Zertifikat ablehnt, prüfen Sie, ob das erforderliche Client-Zertifikat auf dem Gerät bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-153">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
   1. <span data-ttu-id="fb9e6-154">Wenn HoloLens das Server-Zertifikat ablehnt, prüfen Sie, ob das Root-CA-Zertifikat des Servers auf HoloLens bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-154">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
1. <span data-ttu-id="fb9e6-155">Wenn das Enterprise-Profil über ein WLAN-Bereitstellungspaket bereitgestellt wird, wenden Sie das Bereitstellungspaket auf einem Windows 10-PC an.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-155">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="fb9e6-156">Wenn es auch auf einem Windows 10 PC fehlschlägt, befolgen Sie die [Anleitung zur Problembehandlung bei der Windows-Client 802.1X-Authentifizierung](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span><span class="sxs-lookup"><span data-stu-id="fb9e6-156">If it also fails on Windows 10 PC, follow the [Windows client 802.1X authentication troubleshooting guide](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span></span>
1. <span data-ttu-id="fb9e6-157">Senden Sie uns Feedback über den [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span><span class="sxs-lookup"><span data-stu-id="fb9e6-157">Send us feedback through [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span></span>

### <span data-ttu-id="fb9e6-158">Weitere Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="fb9e6-158">Additional resources:</span></span>
- [<span data-ttu-id="fb9e6-159">WLAN-Einstellungen von einem Windows-Gerät exportieren</span><span class="sxs-lookup"><span data-stu-id="fb9e6-159">Export Wi-Fi settings from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <span data-ttu-id="fb9e6-160">VPN</span><span class="sxs-lookup"><span data-stu-id="fb9e6-160">VPN</span></span>
<span data-ttu-id="fb9e6-161">Eine VPN-Verbindung kann Ihnen dabei helfen, eine sicherere Verbindung herzustellen sowie auf das Netzwerk Ihres Unternehmens und das Internet zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-161">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="fb9e6-162">HoloLens2 unterstützt den integrierten VPN-Client und das VPN-Plug-In Universelle Windows-Plattform (UWP).</span><span class="sxs-lookup"><span data-stu-id="fb9e6-162">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="fb9e6-163">Unterstützte integrierte VPN-Protokolle:</span><span class="sxs-lookup"><span data-stu-id="fb9e6-163">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="fb9e6-164">IKEv2</span><span class="sxs-lookup"><span data-stu-id="fb9e6-164">IKEv2</span></span>
- <span data-ttu-id="fb9e6-165">L2TP</span><span class="sxs-lookup"><span data-stu-id="fb9e6-165">L2TP</span></span>
- <span data-ttu-id="fb9e6-166">PPTP</span><span class="sxs-lookup"><span data-stu-id="fb9e6-166">PPTP</span></span>

<span data-ttu-id="fb9e6-167">Wenn für die Authentifizierung des integrierten VPN-Clients ein Zertifikat verwendet wird, muss das erforderliche Clientzertifikat zum Benutzerzertifikatspeicher hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-167">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="fb9e6-168">Wenn Sie herausfinden möchten, ob das VPN-Plug-In eines Drittanbieters HoloLens2 unterstützt, wechseln Sie zu „Speicher“, um die VPN-App zu suchen, und überprüfen Sie, ob HoloLens als unterstütztes Gerät aufgeführt ist und ob die App auf der Seite „Systemanforderungen“ die ARM- oder ARM64-Architektur unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-168">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="fb9e6-169">HoloLens unterstützt nur Universelle Windows-Plattform-Anwendungen für VPN von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-169">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="fb9e6-170">VPN kann durch MDM über [Einstellungen/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) verwaltet und über die Richtlinie [Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-170">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="fb9e6-171">Weitere Informationen zum [Konfigurieren von VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) finden Sie in [diesen Handbüchern](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="fb9e6-171">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <span data-ttu-id="fb9e6-172">VPN über die Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="fb9e6-172">VPN via UI</span></span>

<span data-ttu-id="fb9e6-173">VPN ist standardmäßig nicht aktiviert, kann aber durch Öffnen der App **Einstellungen** und Navigieren zu **„Netzwerk und Internet“ –> „VPN“** manuell aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-173">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="fb9e6-174">Wählen Sie einen VPN-Anbieter aus.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-174">Select a VPN provider.</span></span>
1. <span data-ttu-id="fb9e6-175">Erstellen Sie einen Verbindungsnamen.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-175">Create a connection name.</span></span> 
1. <span data-ttu-id="fb9e6-176">Geben Sie Ihren Servernamen oder Ihre Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-176">Enter your server name or address.</span></span>
1. <span data-ttu-id="fb9e6-177">Wählen Sie den VPN-Typ aus.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-177">Select the VPN type.</span></span>
1. <span data-ttu-id="fb9e6-178">Wählen Sie die Anmeldeinformationen aus.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-178">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="fb9e6-179">Fügen Sie optional Benutzername und Kennwort hinzu.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-179">Optionally add user name and password.</span></span>
1. <span data-ttu-id="fb9e6-180">Wenden Sie die VPN-Einstellungen an.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-180">Apply the VPN settings.</span></span> 

![HoloLens VPN-Einstellungen](./images/vpn-settings-ui.jpg)

### <span data-ttu-id="fb9e6-182">VPN über Bereitstellungspaket einstellen</span><span class="sxs-lookup"><span data-stu-id="fb9e6-182">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="fb9e6-183">In der Windows Holographic Version 20H2 haben wir ein Problem mit der Proxy-Konfiguration für die VPN-Verbindung behoben.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-183">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="fb9e6-184">Wenn Sie diesen Datenstrom verwenden möchten, aktualisieren Sie Geräte auf diesen Build.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-184">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="fb9e6-185">Starten Sie den Windows Configuration Designer.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-185">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="fb9e6-186">Klicken Sie auf **HoloLens-Geräte bereitstellen** und wählen Sie dann das Zielgerät aus und klicken dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-186">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="fb9e6-187">Geben Sie Paketname und Pfad ein.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-187">Enter package name and path.</span></span>
1. <span data-ttu-id="fb9e6-188">Klicken Sie auf **Zum erweiterten Editor wechseln**.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-188">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="fb9e6-189">Öffnen Sie die **Laufzeiteinstellungen**  -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-189">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="fb9e6-190">VPNProfileName konfigurieren</span><span class="sxs-lookup"><span data-stu-id="fb9e6-190">Configure VPNProfileName</span></span>
1. <span data-ttu-id="fb9e6-191">Profiltyp auswählen: \*\*Nativ \*\* oder **Drittanbieter**.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-191">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="fb9e6-192">Wählen Sie unter Natives Profil die Option **NativeProtocolType** und konfigurieren Sie dann Server, Routing-Richtlinie, Authentifizierungstyp und andere Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-192">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="fb9e6-193">Konfigurieren Sie für Drittanbieter-Profile Server-URL, VPN-Plug-in-App-Paket Familienname (nur 3 vordefiniert) und benutzerdefinierte Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-193">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="fb9e6-194">Exportieren Sie Ihr Paket.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-194">Export your package.</span></span>
1. <span data-ttu-id="fb9e6-195">Schließen Sie HoloLens an und kopieren Sie die .ppkg-Datei auf das Gerät.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-195">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="fb9e6-196">Um auf HoloLens das VPN.ppkg anzuwenden, öffnen Sie im Startmenü **Einstellungen** -> \*\* Konto\*\* -> **Zugriff Arbeit oder Schule** -> **Bereitstellungspaket hinzufügen oder entfernen** -> Wählen Sie Ihr VPN-Paket aus.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-196">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <span data-ttu-id="fb9e6-197">VPN über Intune einrichten</span><span class="sxs-lookup"><span data-stu-id="fb9e6-197">Setting up VPN via Intune</span></span>
<span data-ttu-id="fb9e6-198">Folgen Sie zunächst der Intune-Anleitung.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-198">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="fb9e6-199">Beachten Sie bei der Durchführung dieser Schritte die eingebauten VPN-Protokolle, die HoloLens-Geräte unterstützen.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-199">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="fb9e6-200">[VPN-Profile zur Verbindung mit VPN-Servern in Intune erstellen](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="fb9e6-200">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="fb9e6-201">[Windows 10 und Windows Holographic-Geräteeinstellungen zum Hinzufügen von VPN-Verbindungen mit Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="fb9e6-201">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="fb9e6-202">Wenn Sie fertig sind, denken Sie daran, [das Profil zuzuweisen](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="fb9e6-202">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <span data-ttu-id="fb9e6-203">VPN über die MDM-Lösungen von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="fb9e6-203">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="fb9e6-204">Beispiel für eine VPN-Verbindung von Drittanbietern:</span><span class="sxs-lookup"><span data-stu-id="fb9e6-204">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="fb9e6-205">Natives IKEv2-VPN-Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fb9e6-205">Native IKEv2 VPN example:</span></span>
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
## <span data-ttu-id="fb9e6-206">WLAN auf HoloLens (1. Generation) deaktivieren</span><span class="sxs-lookup"><span data-stu-id="fb9e6-206">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="fb9e6-207">Verwenden der Einstellungs-App auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="fb9e6-207">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="fb9e6-208">Öffnen Sie das **Startmenü**.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-208">Open the **Start** menu.</span></span>
1. <span data-ttu-id="fb9e6-209">Wählen Sie die **Einstellungs**-App im **Startmenü** oder in der Liste **Alle Apps** auf der rechten Seite des **Startmenüs** aus.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-209">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="fb9e6-210">Die **Einstellungs**-App wird automatisch vor Ihnen platziert.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-210">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="fb9e6-211">Wählen Sie **Netzwerk und Internet** aus.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-211">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="fb9e6-212">Wählen Sie den WLAN-Schieberegler aus, um ihn in die Position **Off** (Aus) zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-212">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="fb9e6-213">Dadurch werden die HF-Komponenten des WLAN-Funkanschlusses ausgeschaltet und alle WLAN-Funktionen von HoloLens deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-213">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="fb9e6-214">Wenn der WLAN-Funkanschluss deaktiviert ist, kann HoloLens Ihre [Räume](hololens-spaces.md) nicht automatisch laden.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-214">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="fb9e6-215">Schieben Sie den Schieberegler in die Stellung **On** (Ein), um das WLAN zu aktivieren und die WLAN-Funktion auf Microsoft HoloLens wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-215">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="fb9e6-216">Der ausgewählte WLAN-Funkstatus (**Ein** oder **Aus**) bleibt bei einem Neustart erhalten.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-216">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="fb9e6-217">Identifizieren der IP-Adresse Ihrer HoloLens im WLAN-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="fb9e6-217">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="fb9e6-218">Mithilfe der Einstellungs-App</span><span class="sxs-lookup"><span data-stu-id="fb9e6-218">By using the Settings app</span></span>

1. <span data-ttu-id="fb9e6-219">Öffnen Sie das **Startmenü**.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-219">Open the **Start** menu.</span></span>
1. <span data-ttu-id="fb9e6-220">Wählen Sie die **Einstellungs**-App im **Startmenü** oder in der Liste **Alle Apps** auf der rechten Seite des **Startmenüs** aus.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-220">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="fb9e6-221">Die **Einstellungs**-App wird automatisch vor Ihnen platziert.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-221">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="fb9e6-222">Wählen Sie **Netzwerk und Internet** aus.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-222">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="fb9e6-223">Scrollen Sie nach unten unter die Liste der verfügbaren WLAN-Netzwerke und wählen Sie **Hardwareeigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-223">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Hardwareeigenschaften in WLAN-Einstellungen](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="fb9e6-225">Die IP-Adresse wird neben **IPv4-Adresse** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-225">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="fb9e6-226">Mithilfe von Sprachbefehlen</span><span class="sxs-lookup"><span data-stu-id="fb9e6-226">By using voice commands</span></span>

<span data-ttu-id="fb9e6-227">Je nach dem Build Ihres Geräts können Sie entweder mithilfe von integrierten Sprachbefehlen oder Cortana Ihre IP-Adresse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-227">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="fb9e6-228">Sprechen Sie bei Builds nach [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) „Wie lautet meine IP-Adresse?“</span><span class="sxs-lookup"><span data-stu-id="fb9e6-228">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="fb9e6-229">Dann wird sie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-229">and it will be displayed.</span></span> <span data-ttu-id="fb9e6-230">Sagen Sie bei früheren Builds oder HoloLens (1.Generation)„Hey Cortana, wie lautet meine IP-Adresse?”.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-230">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="fb9e6-231">und Cortana wird Ihre IP-Adresse anzeigen und vorlesen.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-231">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="fb9e6-232">Mithilfe des Windows-Geräteportals</span><span class="sxs-lookup"><span data-stu-id="fb9e6-232">By using Windows Device Portal</span></span>

1. <span data-ttu-id="fb9e6-233">Öffnen Sie in einem Webbrowser auf Ihrem PC das [Geräteportal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="fb9e6-233">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="fb9e6-234">Navigieren Sie zum Abschnitt **Netzwerk**.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-234">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="fb9e6-235">In diesem Abschnitt werden Ihre IP-Adresse und andere Netzwerkinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-235">This section displays your IP address and other network information.</span></span> <span data-ttu-id="fb9e6-236">Mithilfe dieser Methode können Sie die IP-Adresse auf Ihren Entwicklungscomputer kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="fb9e6-236">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
