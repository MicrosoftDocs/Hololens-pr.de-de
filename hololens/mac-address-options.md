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
ms.openlocfilehash: fe365248332f8e78b15ab362f169b84e48dfe594
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393839"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="4265b-103">Enterprise-Registrierung von HoloLens-Geräten in einer auf MAC-Adressen beschränkten WLAN-Umgebung</span><span class="sxs-lookup"><span data-stu-id="4265b-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="4265b-104">In diesem Dokument wird ein gängiges Szenario beschrieben, das in Kundenumgebungen festgelegt wurde, in denen das WLAN-System durch MAC-Adressen eingeschränkt wird, oder Zertifikate für die Teilnahme an drahtlosen Netzwerken erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4265b-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="4265b-105">Beispielszenario</span><span class="sxs-lookup"><span data-stu-id="4265b-105">Example Scenario</span></span>

<span data-ttu-id="4265b-106">Viele Kunden in sicheren Umgebungen haben Einschränkungen in ihren drahtlosen oder kabelgebundenen Netzwerken, sodass nur zugelassene Geräte (basierend auf MAC-Adressen) eine erfolgreiche Verbindung herstellen können.</span><span class="sxs-lookup"><span data-stu-id="4265b-106">Many customers in secure environments have restrictions on their Wireless or wired networks which will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="4265b-107">Dies kann durch MAC-Adressfilterung auf einem Wireless Access Point oder über einen DHCP-Server erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="4265b-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="4265b-108">Darüber hinaus können einige drahtlose Netzwerke mit PEAP geschützt werden. Daher muss vor der Authentifizierung im drahtlosen Netzwerk ein Zertifikat auf das Gerät angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="4265b-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="4265b-109">In diesem Szenario können zwei Hauptanforderungen zu Verzögerungen führen oder manuelle Eingriffe erfordern, wenn HoloLens-Geräte mit dem Netzwerk verbunden werden:</span><span class="sxs-lookup"><span data-stu-id="4265b-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="4265b-110">Das drahtlose PEAP-Zertifikat muss auf das Gerät angewendet werden, bevor das Gerät erfolgreich mit dem drahtlosen Netzwerk verbunden wird.</span><span class="sxs-lookup"><span data-stu-id="4265b-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="4265b-111">Die MAC-Adresse des HoloLens-WLAN-Adapters muss registriert werden.</span><span class="sxs-lookup"><span data-stu-id="4265b-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="4265b-112">Die Kernherausforderungen mit den oben genannten Anforderungen sind:</span><span class="sxs-lookup"><span data-stu-id="4265b-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="4265b-113">Die MAC-Adresse kann derzeit nur über die Einstellungen-App auf dem Gerät oder über Intune nach erfolgreicher Registrierung identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="4265b-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>
2. <span data-ttu-id="4265b-114">Ohne die MAC-Adresse kann das Gerät nicht mit dem WLAN-Netzwerk verbunden werden, um die Registrierung zu starten.</span><span class="sxs-lookup"><span data-stu-id="4265b-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>
3. <span data-ttu-id="4265b-115">Manuelle Problemumgehungen für diese Herausforderungen erfordern, dass ein Techniker mit dem Gerät interagiert.</span><span class="sxs-lookup"><span data-stu-id="4265b-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="4265b-116">Lösungen</span><span class="sxs-lookup"><span data-stu-id="4265b-116">Solutions</span></span>

<span data-ttu-id="4265b-117">Es gibt viele Möglichkeiten, diese Situation zu verbessern, abhängig von der in der Umgebung verfügbaren Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="4265b-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="4265b-118">Lösung</span><span class="sxs-lookup"><span data-stu-id="4265b-118">Solution</span></span> | <span data-ttu-id="4265b-119">Vorteile</span><span class="sxs-lookup"><span data-stu-id="4265b-119">Benefits</span></span> | <span data-ttu-id="4265b-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4265b-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="4265b-121">Bereitstellungspaket mit Ethernet-Adapter</span><span class="sxs-lookup"><span data-stu-id="4265b-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="4265b-122">Verbessert die OOBE-Erfahrung und ermöglicht eine schnellere Techniker-Erfahrung.</span><span class="sxs-lookup"><span data-stu-id="4265b-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="4265b-123">Der HoloLens-kompatible USB-C Hub + Ethernet-Adapter und der Techniker müssen weiterhin mit dem Gerät interagieren, um die MAC-Erfassung und die OOBE-Finalisierung durchzuführen</span><span class="sxs-lookup"><span data-stu-id="4265b-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalisation</span></span> |
| <span data-ttu-id="4265b-124">Autopilot mit Intune-Registrierung über Ethernet</span><span class="sxs-lookup"><span data-stu-id="4265b-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="4265b-125">Dies ist eine einstufige Verbindung und Registrierung des Geräts in der Kundenumgebung.</span><span class="sxs-lookup"><span data-stu-id="4265b-125">This is a single step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="4265b-126">Die MAC-Erfassung kann abgeschlossen werden, ohne dass eine Interaktion mit dem Gerät erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="4265b-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="4265b-127">Intune aktiviert für den AAD-Mandanten des Kunden und einen HoloLens-kompatiblen USB-C-Ethernet-Adapter</span><span class="sxs-lookup"><span data-stu-id="4265b-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="4265b-128">Automatisierte Berichterstattung von MAC-Adressen</span><span class="sxs-lookup"><span data-stu-id="4265b-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="4265b-129">Wenn Geräte beim Intune-Mandanten registriert sind, kann ein Skript die MAC-Adresse dem Techniker melden.</span><span class="sxs-lookup"><span data-stu-id="4265b-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="4265b-130">Intune PowerShell-Commandlets</span><span class="sxs-lookup"><span data-stu-id="4265b-130">Intune Powershell Commandlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="4265b-131">Bereitstellungspaket mit Ethernet-Adapter</span><span class="sxs-lookup"><span data-stu-id="4265b-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="4265b-132">Wenn für das kabelgebundene Netzwerk auch MAC-Einschränkungen gelten, muss auch die MAC-Adresse des USB-C Hub + Ethernet-Adapters vorab genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="4265b-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="4265b-133">Bei diesem Adapter ist Vorsicht geboten, da er den Zugriff auf das Netzwerk von anderen Geräten aus ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="4265b-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="4265b-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4265b-134">Requirements</span></span>

- <span data-ttu-id="4265b-135">Verkabelter Netzwerk-Port mit Zugriff auf das Kundennetzwerk</span><span class="sxs-lookup"><span data-stu-id="4265b-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="4265b-136">HoloLens-kompatibler USB-C-Hub mit Ethernet-Adapter – Jeder Adapter, für den keine zusätzlicher Treiber oder Anwendungsinstallationen erforderlich sind, sollte geeignet sein.</span><span class="sxs-lookup"><span data-stu-id="4265b-136">HoloLens Compatible USB-C Hub with Ethernet adaptor – Any adapter that doesn&#39;t require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="4265b-137">Bereitstellungspaket enthält:</span><span class="sxs-lookup"><span data-stu-id="4265b-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="4265b-138">Informationen zum drahtlosen Netzwerk und Zertifikat</span><span class="sxs-lookup"><span data-stu-id="4265b-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="4265b-139">Informationen zur Registrierung für Azure AD der Organisation&#39;s (optional)</span><span class="sxs-lookup"><span data-stu-id="4265b-139">Optionally containing enrollment information for the Organization&#39;s Azure AD</span></span>
  - <span data-ttu-id="4265b-140">Alle anderen erforderlichen Bereitstellungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="4265b-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="4265b-141">Process</span><span class="sxs-lookup"><span data-stu-id="4265b-141">Process</span></span>

<span data-ttu-id="4265b-142">Der Vorgang kann je nach Softwareebene des Geräts variieren.</span><span class="sxs-lookup"><span data-stu-id="4265b-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="4265b-143">Wenn auf dem Gerät das [Mai 2004 Update](hololens-release-notes.md#windows-holographic-version-2004) vorhanden ist, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="4265b-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="4265b-144">Platzieren Sie das Bereitstellungspaket auf dem Stamm eines USB-Sticks und schließen Sie es an den Hub an.</span><span class="sxs-lookup"><span data-stu-id="4265b-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="4265b-145">Schließen Sie das Ethernet-Kabel an den Hub + Ethernet-Adapter an.</span><span class="sxs-lookup"><span data-stu-id="4265b-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="4265b-146">Schließen Sie den USB-C-Hub an das HoloLens-Gerät an.</span><span class="sxs-lookup"><span data-stu-id="4265b-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="4265b-147">Schalten Sie die HoloLens ein und setzen Sie das Gerät auf.</span><span class="sxs-lookup"><span data-stu-id="4265b-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="4265b-148">Drücken Sie die **Lautstärke-nach-unten-Taste**, um das Bereitstellungspaket anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="4265b-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="4265b-149">Der Techniker kann nun OOBE folgen und nach Abschluss die Einstellungen-App öffnen, um die MAC-Adresse des Geräts abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4265b-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="4265b-150">Wenn auf dem Gerät ein Betriebssystem-Build vor dem [Mai 2004 Update](hololens-release-notes.md#windows-holographic-version-2004) vorhanden ist, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="4265b-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="4265b-151">Schalten Sie die HoloLens ein und schließen Sie das Gerät an einen PC an.</span><span class="sxs-lookup"><span data-stu-id="4265b-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="4265b-152">Das Gerät sollte auf dem PC als Datei-Speichervorrichtung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4265b-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="4265b-153">Kopieren Sie das Bereitstellungspaket auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="4265b-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="4265b-154">Verbinden Sie das Ethernet-Kabel mit dem Hub.</span><span class="sxs-lookup"><span data-stu-id="4265b-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="4265b-155">Schließen Sie den USB-C-Hub an das HoloLens-Gerät an.</span><span class="sxs-lookup"><span data-stu-id="4265b-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="4265b-156">Setzen Sie die HoloLens auf</span><span class="sxs-lookup"><span data-stu-id="4265b-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="4265b-157">Drücken Sie die **Lautstärke-nach-unten-Taste**, um das Bereitstellungspaket anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="4265b-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="4265b-158">Der Techniker kann nun OOBE folgen und nach Abschluss die Einstellungen-App öffnen, um die MAC-Adresse des Geräts abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4265b-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="4265b-159">Vorteile</span><span class="sxs-lookup"><span data-stu-id="4265b-159">Benefits</span></span>

<span data-ttu-id="4265b-160">Auf diese Weise kann mit einer &quot;einzigen Berührung&quot; des Geräts das korrekte Bereitstellungspaket angewendet und die MAC-Adresse des Geräts erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="4265b-160">This will allow a &quot;Single touch&quot; of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="4265b-161">Bereitstellungspakete können entsprechend der hier aufgeführten Anleitung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4265b-161">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="4265b-162">Autopilot mit Intune-Registrierung</span><span class="sxs-lookup"><span data-stu-id="4265b-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="4265b-163">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4265b-163">Requirements</span></span>

- <span data-ttu-id="4265b-164">Verkabelter Netzwerk-Port mit Zugriff auf das Kundennetzwerk</span><span class="sxs-lookup"><span data-stu-id="4265b-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="4265b-165">HoloLens-Geräte unter Windows holographisch 2004</span><span class="sxs-lookup"><span data-stu-id="4265b-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="4265b-166">HoloLens-kompatibler USB-C-Ethernet-Adapter</span><span class="sxs-lookup"><span data-stu-id="4265b-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="4265b-167">Intune eingerichtet und für den Kundenmandanten aktiviert</span><span class="sxs-lookup"><span data-stu-id="4265b-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="4265b-168">Für Autopilot registriertes und in den Kundenmandanten importiertes Gerät</span><span class="sxs-lookup"><span data-stu-id="4265b-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="4265b-169">Für das Gerät definierte Intune-Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="4265b-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="4265b-170">Informationen zum drahtlosen Netzwerk und Zertifikat</span><span class="sxs-lookup"><span data-stu-id="4265b-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="4265b-171">Alle anderen erforderlichen Bereitstellungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="4265b-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="4265b-172">Auf diese Weise kann ein Kunde mit fortgeschrittenen Netzwerkanforderungen die Geräte in einem praktischen, skalierbaren Ansatz registrieren.</span><span class="sxs-lookup"><span data-stu-id="4265b-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="4265b-173">Weitere Voraussetzungen sind wie unten aufgeführt erforderlich:</span><span class="sxs-lookup"><span data-stu-id="4265b-173">Additional pre-requisites will be needed as below:</span></span>
1. [<span data-ttu-id="4265b-174">Aktivieren des Mandanten für die Autopilot-Vorschau</span><span class="sxs-lookup"><span data-stu-id="4265b-174">Enable the Tenant for the Autopilot preview</span></span>](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. <span data-ttu-id="4265b-175">Erstellen der HoloLens-Richtlinien, um das Bereitstellungspaket in Intune zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="4265b-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="4265b-176">Erstellen der HoloLens-Intune-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="4265b-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="4265b-177">Zuordnen der Geräte zur richtigen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="4265b-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="4265b-178">Verfahren</span><span class="sxs-lookup"><span data-stu-id="4265b-178">Process</span></span>

1. <span data-ttu-id="4265b-179">Schließen Sie das Ethernet-Kabel an den Adapter an und stecken Sie den Adapter in den USB-C-Anschluss des HoloLens 2-Geräts.</span><span class="sxs-lookup"><span data-stu-id="4265b-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>
2. <span data-ttu-id="4265b-180">Schalten Sie die HoloLens ein.</span><span class="sxs-lookup"><span data-stu-id="4265b-180">Turn on the HoloLens.</span></span>
3. <span data-ttu-id="4265b-181">Das Gerät sollte während der OOBE über den Ethernet-Adapter automatisch eine Verbindung zum Internet herstellen.</span><span class="sxs-lookup"><span data-stu-id="4265b-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="4265b-182">Es sollte die Autopilot-Konfiguration erkennen und sich automatisch bei Azure AD und Intune registrieren</span><span class="sxs-lookup"><span data-stu-id="4265b-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune</span></span>
4. <span data-ttu-id="4265b-183">Das Gerät wendet die erforderlichen WLAN-Zertifikate und andere Konfigurationen nach Bedarf über Intune an</span><span class="sxs-lookup"><span data-stu-id="4265b-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune</span></span>
5. <span data-ttu-id="4265b-184">Nach Fertigstellung kann der Techniker das Intune (Endpunkt-Manager)-Portal laden und die Seite "Geräteeigenschaften" unter **Start -> Geräte -> Gerätename -> Hardware** aufrufen</span><span class="sxs-lookup"><span data-stu-id="4265b-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**</span></span>
6. <span data-ttu-id="4265b-185">Die WLAN-MAC-Adresse wird im Intune-Portal angezeigt</span><span class="sxs-lookup"><span data-stu-id="4265b-185">The Wifi MAC address will be visible within the Intune Portal</span></span>

![MAC-Adresse über Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="4265b-187">Der Techniker wird diese MAC-Adresse als zulässiges Gerät hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4265b-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="4265b-188">Vorteile</span><span class="sxs-lookup"><span data-stu-id="4265b-188">Benefits</span></span>

<span data-ttu-id="4265b-189">Dies ermöglicht dem Techniker eine &quot;"Heads off"&quot;-Bereitstellungserfahrung, bei der das Gerät von der Box zum Azure AD und Intune übergehen kann, ohne dass der Techniker das Gerät tragen oder manuell mit der HoloLens-Umgebung interagieren muss.</span><span class="sxs-lookup"><span data-stu-id="4265b-189">This will allow a &quot;Heads off&quot; deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="4265b-190">Berichterstattung von MAC-Adressen an den Techniker</span><span class="sxs-lookup"><span data-stu-id="4265b-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="4265b-191">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4265b-191">Requirements</span></span>

- <span data-ttu-id="4265b-192">Autorisierung der &quot;Intune Graph-PowerShell&quot; gegenüber dem Kundenmandanten</span><span class="sxs-lookup"><span data-stu-id="4265b-192">Authorization of the &quot;Intune Graph PowerShell&quot; against the customer Tenant</span></span>
- <span data-ttu-id="4265b-193">Installation der Intune Graph-PowerShell auf dem Computer des Technikers.</span><span class="sxs-lookup"><span data-stu-id="4265b-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="4265b-194">Lesezugriff auf die Elemente &quot;Verwaltete Geräte&quot; von Intune.</span><span class="sxs-lookup"><span data-stu-id="4265b-194">Read access to the &quot;Managed Devices&quot; elements of Intune.</span></span> <span data-ttu-id="4265b-195">(Helpdesk-Operator oder höher oder eine benutzerdefinierte Rolle)</span><span class="sxs-lookup"><span data-stu-id="4265b-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="4265b-196">Derzeit gibt es keine &quot;einfache&quot; Möglichkeit, einen Automatisierungsbefehl basierend auf der Registrierung eines neuen Geräts in Intune auszulösen.</span><span class="sxs-lookup"><span data-stu-id="4265b-196">At present, there is no &quot;simple&quot; way to trigger an automation command based on the enrolment of a new device within Intune.</span></span> <span data-ttu-id="4265b-197">Daher bietet dieser Befehl dem Techniker eine einfache Möglichkeit, die MAC-Adresse abzurufen, ohne dass er sich am Portal anmelden und sie manuell abrufen muss.</span><span class="sxs-lookup"><span data-stu-id="4265b-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="4265b-198">Dadurch werden der Name und die MAC-Adresse aller HoloLens-Geräte zurückgegeben, die in den letzten 30 Tagen registriert wurden.</span><span class="sxs-lookup"><span data-stu-id="4265b-198">This will return the name and MAC address of any HoloLens devices which have been enrolled in the last 30 days.</span></span>

![Mac-Adresse über PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="4265b-200">Process</span><span class="sxs-lookup"><span data-stu-id="4265b-200">Process</span></span>

<span data-ttu-id="4265b-201">Nachdem die Intune-Registrierung abgeschlossen ist, wird der Techniker das obige Skript ausführen, um die MAC-Adresse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4265b-201">After the Intune enrolment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
