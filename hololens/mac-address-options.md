---
title: Enterprise-Registrierung von HoloLens-Geräten in einer auf MAC-Adressen beschränkten WLAN-Umgebung
description: 'So wird es gemacht: MAC-Adresse für Netzwerk auf HoloLens 2-Geräten'
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2b0ed266389ccc5a21117a604a6eb0abd214d4d1
ms.sourcegitcommit: 1793f53f9e1cc63ac40edc09e65bb4beb80a4575
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "11093232"
---
# <span data-ttu-id="cbe5d-103">Enterprise-Registrierung von HoloLens-Geräten in einer auf MAC-Adressen beschränkten WLAN-Umgebung</span><span class="sxs-lookup"><span data-stu-id="cbe5d-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="cbe5d-104">In diesem Dokument wird ein gängiges Szenario beschrieben, das in Kundenumgebungen festgelegt wurde, in denen das WLAN-System durch MAC-Adressen eingeschränkt wird, oder Zertifikate für die Teilnahme an drahtlosen Netzwerken erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <span data-ttu-id="cbe5d-105">Beispielszenario</span><span class="sxs-lookup"><span data-stu-id="cbe5d-105">Example Scenario</span></span>

<span data-ttu-id="cbe5d-106">Viele Kunden in sicheren Umgebungen haben Beschränkungen in Ihren drahtlosen oder verkabelten Netzwerken, die nur genehmigten Geräten (basierend auf MAC-Adressen) das erfolgreiche Herstellen einer Verbindung ermöglichen (entweder mit der MAC-Adressfilterung auf einem Zugriffspunkt oder auf einem DHCP-Server).</span><span class="sxs-lookup"><span data-stu-id="cbe5d-106">Many customers in secure environments have restrictions on their Wireless or wired networks which will only allow approved devices (based on MAC Addresses) to connect successfully (either with MAC Address filtering on a Wireless Access Point or on a DHCP server).</span></span> <span data-ttu-id="cbe5d-107">Außerdem können einige drahtlose Netzwerke mit PEAP geschützt werden, was erfordert, dass ein Zertifikat auf das Gerät angewendet wird, bevor das drahtlose Netzwerk erfolgreich authentifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-107">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to being able to successfully authenticate the Wireless network.</span></span>

<span data-ttu-id="cbe5d-108">Bei HoloLens-Geräten können zwei wichtige Probleme auftreten, die zu Verzögerungen und manueller Arbeit beim Verbinden der HoloLens-Geräte mit dem Netzwerk führen können.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-108">Two key issues can arise with HoloLens devices, which can cause delays and manual work in joining the HoloLens Devices to the network.</span></span>

- <span data-ttu-id="cbe5d-109">Das drahtlose PEAP-Zertifikat muss auf das Gerät angewendet werden, bevor das Gerät erfolgreich mit dem drahtlosen Netzwerk verbunden wird.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-109">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="cbe5d-110">Die MAC-Adresse des HoloLens-WLAN-Adapters muss registriert werden.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-110">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="cbe5d-111">Die wichtigsten Herausforderungen hierfür sind:</span><span class="sxs-lookup"><span data-stu-id="cbe5d-111">The key challenges to this are:</span></span>

1. <span data-ttu-id="cbe5d-112">Die MAC-Adresse kann derzeit nur anhand der Einstellungs-App auf dem Gerät oder aus Intune nach einer erfolgreichen Intune-Registrierung bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-112">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful Intune enrollment.</span></span>
2. <span data-ttu-id="cbe5d-113">Ohne die MAC-Adresse kann das Gerät nicht mit dem WLAN-Netzwerk verbunden werden, um die Registrierung zu starten.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-113">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>
3. <span data-ttu-id="cbe5d-114">Manuelle Lösungen für diese Herausforderungen erfordern den Einsatz von Technikern an den Geräten.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-114">Manual Solutions to these challenges require technician involvement with the devices.</span></span>

## <span data-ttu-id="cbe5d-115">Lösungen</span><span class="sxs-lookup"><span data-stu-id="cbe5d-115">Solutions</span></span>

<span data-ttu-id="cbe5d-116">Es gibt eine Reihe von Möglichkeiten, diese Situation zu verbessern, abhängig von der in der Umgebung verfügbaren Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-116">There are a number of ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="cbe5d-117">Lösung</span><span class="sxs-lookup"><span data-stu-id="cbe5d-117">Solution</span></span> | <span data-ttu-id="cbe5d-118">Vorteile</span><span class="sxs-lookup"><span data-stu-id="cbe5d-118">Benefits</span></span> | <span data-ttu-id="cbe5d-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cbe5d-119">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cbe5d-120">Bereitstellungspaket mit Ethernet-Adapter</span><span class="sxs-lookup"><span data-stu-id="cbe5d-120">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="cbe5d-121">Verbessert die OOBE-Erfahrung und ermöglicht eine schnellere Techniker-Erfahrung.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-121">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="cbe5d-122">HoloLens kompatibler USB-C-Hub. Der Techniker muss für die MAC-Erfassung und OOBE-Fertigstellung noch mit dem Gerät interagieren</span><span class="sxs-lookup"><span data-stu-id="cbe5d-122">HoloLens compatible USB C HubTechnician will still need to interact with the device for MAC Capture and OOBE finalisation</span></span> |
| <span data-ttu-id="cbe5d-123">Autopilot mit Intune-Registrierung über Ethernet</span><span class="sxs-lookup"><span data-stu-id="cbe5d-123">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="cbe5d-124">Einstufige Verbindung und Registrierung des Geräts an die Kundenumgebung. Die MAC-Erfassung kann ohne Interaktion mit dem Gerät durchgeführt werden</span><span class="sxs-lookup"><span data-stu-id="cbe5d-124">Single Step connection and registration of the device to the customer environmentMAC capture can be completed without interacting with the device</span></span> | <span data-ttu-id="cbe5d-125">Intune für den Kunden aktiviert. AAD TenantHoloLens kompatibler USB-C-Netzwerkadapter</span><span class="sxs-lookup"><span data-stu-id="cbe5d-125">Intune enabled for the customer AAD TenantHoloLens Compatible USB-C network adaptor</span></span> |
| <span data-ttu-id="cbe5d-126">Automatisierte Berichterstattung von MAC-Adressen</span><span class="sxs-lookup"><span data-stu-id="cbe5d-126">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="cbe5d-127">Wenn Geräte innerhalb des Intune-Mandanten registriert wurden, skripten Sie die Berichterstattung der MAC-Adresse an den Techniker.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-127">When devices have been registered within the Intune Tenant, Script the reporting of the MAC address to the technician.</span></span> | <span data-ttu-id="cbe5d-128">Intune PowerShell-Commandlets</span><span class="sxs-lookup"><span data-stu-id="cbe5d-128">Intune Powershell Commandlets</span></span> |

## <span data-ttu-id="cbe5d-129">Bereitstellungspaket mit Ethernet-Adapter</span><span class="sxs-lookup"><span data-stu-id="cbe5d-129">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="cbe5d-130">Wenn das verkabelte Netzwerk auch MAC-Beschränkungen unterliegt, muss die MAC-Adresse des USB-C-Ethernet-Adapters/-Hubs vorab genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-130">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Ethernet adaptor / Hub will need to be pre-approved.</span></span> <span data-ttu-id="cbe5d-131">Bei diesem Hub sollten Sie darauf achten, dass der Zugriff auf das Netzwerk von anderen Geräten aus ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-131">Care should be taken with this hub as it will allow access to the network from other devices.</span></span>

### <span data-ttu-id="cbe5d-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cbe5d-132">Requirements</span></span>

- <span data-ttu-id="cbe5d-133">Verkabelter Netzwerk-Port mit Zugriff auf das Kundennetzwerk</span><span class="sxs-lookup"><span data-stu-id="cbe5d-133">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="cbe5d-134">HoloLens kompatibler USB-C-Hub mit einem Ethernet-Adapter – Jeder Hub, der keine zusätzlichen Treiber oder Anwendungsinstallationen erfordert, sollte geeignet sein.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-134">HoloLens Compatible USB-C Hub containing an Ethernet adaptor – Any hub that doesn&#39;t require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="cbe5d-135">Bereitstellungspaket enthält:</span><span class="sxs-lookup"><span data-stu-id="cbe5d-135">Provisioning Package containing:</span></span>
  - <span data-ttu-id="cbe5d-136">Informationen zum drahtlosen Netzwerk und Zertifikat</span><span class="sxs-lookup"><span data-stu-id="cbe5d-136">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="cbe5d-137">Informationen zur Registrierung für Azure AD der Organisation (optional)</span><span class="sxs-lookup"><span data-stu-id="cbe5d-137">Optionally containing enrollment information for the Organisation&#39;s Azure AD</span></span>
  - <span data-ttu-id="cbe5d-138">Alle anderen erforderlichen Bereitstellungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="cbe5d-138">Containing any other required provisioning settings</span></span>

### <span data-ttu-id="cbe5d-139">Process</span><span class="sxs-lookup"><span data-stu-id="cbe5d-139">Process</span></span>

<span data-ttu-id="cbe5d-140">Der Vorgang kann je nach Softwareebene des Geräts variieren.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-140">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="cbe5d-141">Wenn auf dem Gerät das [Mai 2004 Update](hololens-release-notes.md#windows-holographic-version-2004) vorhanden ist, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-141">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="cbe5d-142">Platzieren Sie das Bereitstellungspaket auf dem Stamm eines USB-Sticks und schließen Sie es an den Hub an.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-142">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="cbe5d-143">Verbinden Sie das Ethernet-Kabel mit dem Hub.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-143">Connect Ethernet cable to the hub.</span></span>
3. <span data-ttu-id="cbe5d-144">Verbinden Sie den USB-C-Hub mit dem HoloLens-Gerät.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-144">Connect USB-C hub to HoloLens device.</span></span>
4. <span data-ttu-id="cbe5d-145">Schalten Sie das HoloLens-Gerät ein, und tragen Sie das Gerät.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-145">Turn on HoloLens Device and wear the device.</span></span>
5. <span data-ttu-id="cbe5d-146">Drücken Sie die **Lautstärke-nach-unten-Taste**, um das Bereitstellungspaket anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-146">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="cbe5d-147">Der Techniker kann nun die OOBE verfolgen und nach Fertigstellung die Einstellungs-App öffnen und die MAC-Adresse des Geräts abrufen.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-147">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="cbe5d-148">Wenn auf dem Gerät ein Betriebssystem-Build vor dem [Mai 2004 Update](hololens-release-notes.md#windows-holographic-version-2004) vorhanden ist, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-148">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="cbe5d-149">Schalten Sie das HoloLens-Gerät ein und schließen Sie das Gerät an einen PC an.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-149">Turn on the HoloLens Device, and plug the device into a PC.</span></span>
2. <span data-ttu-id="cbe5d-150">Das Gerät sollte auf dem PC als Datei-Speichervorrichtung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-150">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="cbe5d-151">Kopieren Sie das Bereitstellungspaket auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="cbe5d-151">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="cbe5d-152">Verbinden Sie das Ethernet-Kabel mit dem Hub.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-152">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="cbe5d-153">Verbinden Sie den USB-C-Hub mit dem HoloLens-Gerät.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-153">Connect USB-C hub to HoloLens device.</span></span>
6. <span data-ttu-id="cbe5d-154">Tragen Sie das Gerät.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-154">Wear the device.</span></span>
7. <span data-ttu-id="cbe5d-155">Drücken Sie die **Lautstärke-nach-unten-Taste**, um das Bereitstellungspaket anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-155">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="cbe5d-156">Der Techniker kann nun die OOBE verfolgen und nach Fertigstellung die Einstellungs-App öffnen und die MAC-Adresse des Geräts abrufen.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-156">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

### <span data-ttu-id="cbe5d-157">Vorteile</span><span class="sxs-lookup"><span data-stu-id="cbe5d-157">Benefits</span></span>

<span data-ttu-id="cbe5d-158">Auf diese Weise kann mit einer &quot;einzigen Berührung&quot; des Geräts das korrekte Bereitstellungspaket angewendet und die MAC-Adresse des Geräts erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-158">This will allow a &quot;Single touch&quot; of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="cbe5d-159">Bereitstellungspakete können entsprechend der hier aufgeführten Anleitung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-159">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <span data-ttu-id="cbe5d-160">Autopilot mit Intune-Registrierung</span><span class="sxs-lookup"><span data-stu-id="cbe5d-160">Autopilot with Intune Enrolment</span></span>

### <span data-ttu-id="cbe5d-161">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cbe5d-161">Requirements</span></span>

- <span data-ttu-id="cbe5d-162">Verkabelter Netzwerk-Port mit Zugriff auf das Kundennetzwerk</span><span class="sxs-lookup"><span data-stu-id="cbe5d-162">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="cbe5d-163">HoloLens-Geräte unter Windows holographisch 2004</span><span class="sxs-lookup"><span data-stu-id="cbe5d-163">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="cbe5d-164">HoloLens kompatibler USB-C-Hub</span><span class="sxs-lookup"><span data-stu-id="cbe5d-164">HoloLens Compatible USB-C Hub</span></span>
- <span data-ttu-id="cbe5d-165">Intune eingerichtet und für den Kundenmandanten aktiviert</span><span class="sxs-lookup"><span data-stu-id="cbe5d-165">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="cbe5d-166">Für Autopilot registriertes und in den Kundenmandanten importiertes Gerät</span><span class="sxs-lookup"><span data-stu-id="cbe5d-166">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="cbe5d-167">Für das Gerät definierte Intune-Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="cbe5d-167">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="cbe5d-168">Informationen zum drahtlosen Netzwerk und Zertifikat</span><span class="sxs-lookup"><span data-stu-id="cbe5d-168">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="cbe5d-169">Alle anderen erforderlichen Bereitstellungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="cbe5d-169">Containing any other required provisioning settings</span></span>

<span data-ttu-id="cbe5d-170">Auf diese Weise kann ein Kunde mit fortgeschrittenen Netzwerkanforderungen die Geräte in einem praktischen, skalierbaren Ansatz registrieren.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-170">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="cbe5d-171">Weitere Voraussetzungen sind wie unten aufgeführt erforderlich:</span><span class="sxs-lookup"><span data-stu-id="cbe5d-171">Additional pre-requisites will be needed as below:</span></span>
1. [<span data-ttu-id="cbe5d-172">Aktivieren des Mandanten für die Autopilot-Vorschau</span><span class="sxs-lookup"><span data-stu-id="cbe5d-172">Enable the Tenant for the Autopilot preview</span></span>](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. <span data-ttu-id="cbe5d-173">Erstellen der HoloLens-Richtlinien, um das Bereitstellungspaket in Intune zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-173">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="cbe5d-174">Erstellen der HoloLens-Intune-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-174">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="cbe5d-175">Zuordnen der Geräte zur richtigen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-175">Assign the devices to the correct group.</span></span>

### <span data-ttu-id="cbe5d-176">Process</span><span class="sxs-lookup"><span data-stu-id="cbe5d-176">Process</span></span>

1. <span data-ttu-id="cbe5d-177">Schließen Sie den USB-C-Hub und das Ethernet-Kabel an das HoloLens 2-Gerät an.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-177">Plug the USB-C hub and ethernet cable into the HoloLens 2 device.</span></span>
2. <span data-ttu-id="cbe5d-178">Schalten Sie HoloLens 2 ein.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-178">Turn on the HoloLens 2.</span></span>
3. <span data-ttu-id="cbe5d-179">Das Gerät sollte sich bei der OOBE über den Ethernet-Adapter automatisch mit dem Internet verbinden, die Autopilot-Konfiguration erkennen und sich automatisch bei Azure AD und Intune registrieren</span><span class="sxs-lookup"><span data-stu-id="cbe5d-179">The device should automatically connect to the internet at OOBE via the Ethernet adaptor, detect the Autopilot configuration, and automatically register with Azure AD and Intune</span></span>
4. <span data-ttu-id="cbe5d-180">Das Gerät wendet die erforderlichen WLAN-Zertifikate und andere Konfigurationen nach Bedarf über Intune an</span><span class="sxs-lookup"><span data-stu-id="cbe5d-180">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune</span></span>
5. <span data-ttu-id="cbe5d-181">Nach Fertigstellung kann der Techniker das Intune (Endpunkt-Manager)-Portal laden und die Seite "Geräteeigenschaften" unter **Start -> Geräte -> Gerätename -> Hardware** aufrufen</span><span class="sxs-lookup"><span data-stu-id="cbe5d-181">When complete, the technician will be able to load the Intune (Endpoint Manager) Portal, and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**</span></span>
6. <span data-ttu-id="cbe5d-182">Die WLAN-MAC-Adresse wird im Intune-Portal angezeigt</span><span class="sxs-lookup"><span data-stu-id="cbe5d-182">The Wifi MAC address will be visible within the Intune Portal</span></span>

![MAC-Adresse über Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="cbe5d-184">Der Techniker wird diese MAC-Adresse als zulässiges Gerät hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-184">The technician will add this MAC address as an allowed device.</span></span>

### <span data-ttu-id="cbe5d-185">Vorteile</span><span class="sxs-lookup"><span data-stu-id="cbe5d-185">Benefits</span></span>

<span data-ttu-id="cbe5d-186">Dies ermöglicht dem Techniker eine &quot;"Heads off"&quot;-Bereitstellungserfahrung, bei der das Gerät von der Box zum AAD und Intune übergehen kann, ohne dass der Techniker das Gerät tragen oder manuell mit der HoloLens-Umgebung interagieren muss.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-186">This will allow a &quot;Heads off&quot; deployment experience for the Technician, with the device being able to go from the box to enrolled in AAD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <span data-ttu-id="cbe5d-187">Berichterstattung von MAC-Adressen an den Techniker</span><span class="sxs-lookup"><span data-stu-id="cbe5d-187">Reporting of MAC addresses to the Technician</span></span>

### <span data-ttu-id="cbe5d-188">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cbe5d-188">Requirements</span></span>

- <span data-ttu-id="cbe5d-189">Autorisierung der &quot;Intune Graph-Powershell&quot; gegenüber dem Kundenmandanten</span><span class="sxs-lookup"><span data-stu-id="cbe5d-189">Authorisation of the &quot;Intune Graph Powershell&quot; against the customer Tenant</span></span>
- <span data-ttu-id="cbe5d-190">Installation der Intune Graph-PowerShell auf dem Computer des Technikers.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-190">Installation of the Intune Graph Powershell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="cbe5d-191">Lesezugriff auf die Elemente &quot;Verwaltete Geräte&quot; von Intune.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-191">Read access to the &quot;Managed Devices&quot; elements of Intune.</span></span> <span data-ttu-id="cbe5d-192">(Helpdesk-Operator oder höher oder eine benutzerdefinierte Rolle)</span><span class="sxs-lookup"><span data-stu-id="cbe5d-192">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="cbe5d-193">Derzeit gibt es keine &quot;einfache&quot; Möglichkeit, einen Automatisierungsbefehl basierend auf der Registrierung eines neuen Geräts in Intune auszulösen.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-193">At present, there is no &quot;simple&quot; way to trigger an automation command based on the enrolment of a new device within Intune.</span></span> <span data-ttu-id="cbe5d-194">Daher bietet dieser Befehl dem Techniker eine einfache Möglichkeit, die MAC-Adresse abzurufen, ohne dass er sich am Portal anmelden und sie manuell abrufen muss.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-194">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="cbe5d-195">Dadurch werden der Name und die MAC-Adresse aller HoloLens-Geräte zurückgegeben, die in den letzten 30 Tagen registriert wurden.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-195">This will return the name and MAC address of any HoloLens devices which have been enrolled in the last 30 days.</span></span>

![Mac-Adresse über PowerShell](images/mac-address-powershell.jpg)

### <span data-ttu-id="cbe5d-197">Process</span><span class="sxs-lookup"><span data-stu-id="cbe5d-197">Process</span></span>

<span data-ttu-id="cbe5d-198">Nachdem die Intune-Registrierung abgeschlossen ist, wird der Techniker das obige Skript ausführen, um die MAC-Adresse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="cbe5d-198">After the Intune enrolment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
