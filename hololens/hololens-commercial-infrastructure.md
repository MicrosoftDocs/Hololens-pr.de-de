---
title: Infrastruktur-Richtlinien für die HoloLens
description: ''
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 65403589fa3d612290fdd59a4843da27c12a956c
ms.sourcegitcommit: f3cda6c6b3bfb7ba4be5f4da66d8ed5b03ca807d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830149"
---
# <span data-ttu-id="701d6-102">Konfigurieren Ihres Netzwerks für HoloLens</span><span class="sxs-lookup"><span data-stu-id="701d6-102">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="701d6-103">Für diesen Teil des Dokuments werden die folgenden Personen benötigt:</span><span class="sxs-lookup"><span data-stu-id="701d6-103">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="701d6-104">Netzwerk-Administrator mit Berechtigungen zum Ändern des Proxys/der Firewall</span><span class="sxs-lookup"><span data-stu-id="701d6-104">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="701d6-105">Azure Active Directory-Administrator</span><span class="sxs-lookup"><span data-stu-id="701d6-105">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="701d6-106">Mobile Device Manager-Administrator</span><span class="sxs-lookup"><span data-stu-id="701d6-106">Mobile Device Manager Admin</span></span>

## <span data-ttu-id="701d6-107">Infrastruktur-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="701d6-107">Infrastructure Requirements</span></span>

<span data-ttu-id="701d6-108">HoloLens ist im Kern ein mobiles Windows-Gerät, das in Azure integriert ist.</span><span class="sxs-lookup"><span data-stu-id="701d6-108">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="701d6-109">Es funktioniert am besten in kommerziellen Umgebungen, in denen ein Drahtlosnetzwerk (WLAN) verfügbar und Zugriff auf Microsoft-Dienste möglich ist.</span><span class="sxs-lookup"><span data-stu-id="701d6-109">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="701d6-110">Zu den kritischen Cloud-Diensten zählen:</span><span class="sxs-lookup"><span data-stu-id="701d6-110">Critical cloud services include:</span></span>

- <span data-ttu-id="701d6-111">Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="701d6-111">Azure active directory (AAD)</span></span>
- <span data-ttu-id="701d6-112">Windows Update (WU)</span><span class="sxs-lookup"><span data-stu-id="701d6-112">Windows Update (WU)</span></span>

<span data-ttu-id="701d6-113">Kommerzielle Kunden benötigen die Enterprise Mobility Management (EMM)-Infrastruktur oder die Mobile Geräteverwaltung (MDM), um HoloLens-Geräte im großen Maßstab zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="701d6-113">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="701d6-114">In diesem Leitfaden wird [Microsoft Intune-](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) als Beispiel verwendet. HoloLens kann jedoch von einem beliebigen unterstützt werden, der die Microsoft-Richtlinie voll unterstützt.</span><span class="sxs-lookup"><span data-stu-id="701d6-114">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="701d6-115">Wenden Sie sich an Ihren Anbieter die Mobile Geräteverwaltung, wenn er HoloLens 2 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="701d6-115">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="701d6-116">HoloLens unterstützt eine begrenzte Anzahl von unterschiedlichen Cloud-Erlebnissen.</span><span class="sxs-lookup"><span data-stu-id="701d6-116">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <span data-ttu-id="701d6-117">EAP-Unterstützung von Drahtlosnetzwerken</span><span class="sxs-lookup"><span data-stu-id="701d6-117">Wireless network EAP support</span></span>

- <span data-ttu-id="701d6-118">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="701d6-118">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="701d6-119">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="701d6-119">PEAP-TLS</span></span>
- <span data-ttu-id="701d6-120">TLS</span><span class="sxs-lookup"><span data-stu-id="701d6-120">TLS</span></span>
- <span data-ttu-id="701d6-121">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="701d6-121">TTLS-CHAP</span></span>
- <span data-ttu-id="701d6-122">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="701d6-122">TTLS-CHAPv2</span></span>
- <span data-ttu-id="701d6-123">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="701d6-123">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="701d6-124">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="701d6-124">TTLS-PAP</span></span>
- <span data-ttu-id="701d6-125">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="701d6-125">TTLS-TLS</span></span>

### <span data-ttu-id="701d6-126">Spezifische Netzwerkanforderungen für HoloLens</span><span class="sxs-lookup"><span data-stu-id="701d6-126">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="701d6-127">Vergewissern Sie sich, dass [diese Liste](hololens-offline.md) der Endpunkte auf Ihrer Netzwerk-Firewall zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="701d6-127">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="701d6-128">Dies ermöglicht der HoloLens ordnungsgemäß zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="701d6-128">This will enable HoloLens to function properly.</span></span>

### <span data-ttu-id="701d6-129">Spezifische Netzwerkanforderungen für Remote Assist</span><span class="sxs-lookup"><span data-stu-id="701d6-129">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="701d6-130">Die empfohlene Bandbreite für eine optimale Leistung von Remote Assist beträgt 1,5 Mbps.</span><span class="sxs-lookup"><span data-stu-id="701d6-130">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="701d6-131">Detaillierte Netzwerkanforderungen und zusätzliche Informationen finden Sie [hier](https://docs.microsoft.com/MicrosoftTeams/prepare-network).</span><span class="sxs-lookup"><span data-stu-id="701d6-131">Detailed network requirements and additional information can be found [here](https://docs.microsoft.com/MicrosoftTeams/prepare-network).</span></span>
**<span data-ttu-id="701d6-132">(Bitte beachten Sie, dass Remote Assist auch dann noch funktioniert, wenn Ihr Netzwerk nicht über eine Netzwerkgeschwindigkeit von mindestens 1,5 Mbit/s verfügt.</span><span class="sxs-lookup"><span data-stu-id="701d6-132">(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work.</span></span> <span data-ttu-id="701d6-133">Allerdings kann die Qualität darunter leiden.)</span><span class="sxs-lookup"><span data-stu-id="701d6-133">However, quality may suffer).</span></span>**
1. <span data-ttu-id="701d6-134">Vergewissern Sie sich, dass diese Ports und URLs auf Ihrer Netzwerk-Firewall zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="701d6-134">Make sure that these ports and URLs are allowed on your network firewall.</span></span> <span data-ttu-id="701d6-135">Dies ermöglich Microsoft Teams zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="701d6-135">This will enable Microsoft Teams to function.</span></span> <span data-ttu-id="701d6-136">Die aktuelle Liste finden Sie [hier](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="701d6-136">The latest list can be found [here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

### <span data-ttu-id="701d6-137">Spezifische Netzwerkanforderungen für Guides</span><span class="sxs-lookup"><span data-stu-id="701d6-137">Guides Specific Network Requirements</span></span>

<span data-ttu-id="701d6-138">Guides benötigt nur einen Netzwerkzugang, um die App herunterzuladen und zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="701d6-138">Guides only require network access to download and use the app.</span></span>

## <span data-ttu-id="701d6-139">Azure Active Directory-Leitfaden</span><span class="sxs-lookup"><span data-stu-id="701d6-139">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="701d6-140">Dieser Schritt ist nur dann erforderlich, wenn Ihre Organisation die Verwaltung von HoloLens plant.</span><span class="sxs-lookup"><span data-stu-id="701d6-140">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="701d6-141">Stellen Sie sicher, dass Sie eine Azure AD-Lizenz besitzen.</span><span class="sxs-lookup"><span data-stu-id="701d6-141">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="701d6-142">Weitere Informationen finden Sie unter [HoloLens-Lizenzanforderungen](hololens-licenses-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="701d6-142">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="701d6-143">Wenn Sie die automatische Registrierung verwenden möchten, müssen Sie die [Azure AD-Registrierung konfigurieren](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment).</span><span class="sxs-lookup"><span data-stu-id="701d6-143">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="701d6-144">Stellen Sie sicher, dass die Benutzer Ihres Unternehmens sich im Azure Active Directory (Azure AD) befinden.</span><span class="sxs-lookup"><span data-stu-id="701d6-144">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="701d6-145">Anweisungen zum Hinzufügen von Benutzern finden Sie [hier](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory).</span><span class="sxs-lookup"><span data-stu-id="701d6-145">Instructions for adding users can be found [here](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory).</span></span>

1. <span data-ttu-id="701d6-146">Wir schlagen vor, dass Benutzer, die ähnliche Lizenzen benötigen, der gleichen Gruppe hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="701d6-146">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="701d6-147">Erstellen einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="701d6-147">Create a Group</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="701d6-148">Hinzufügen von Benutzern zu Gruppen</span><span class="sxs-lookup"><span data-stu-id="701d6-148">Add users to groups</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="701d6-149">Stellen Sie sicher, dass den Benutzern (oder Benutzergruppen) Ihres Unternehmens die nötigen Lizenzen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="701d6-149">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="701d6-150">Anweisungen für die Vergabe von Lizenzen finden Sie[hier](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span><span class="sxs-lookup"><span data-stu-id="701d6-150">Directions for assigning licenses can be found [here](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="701d6-151">Führen Sie diesen Schritt nur durch, wenn von den Benutzern erwartet wird, dass sie ihr HoloLens/Mobilgerät bei Ihnen registrieren (es gibt drei Optionen). Diese Schritte stellen sicher, dass die Benutzer (oder eine Gruppe von Benutzern) Ihres Unternehmens Geräte hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="701d6-151">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="701d6-152">**Option 1:**: Erteilen Sie allen Benutzern die Berechtigung zum Hinzufügen von Geräten zu Azure AD.</span><span class="sxs-lookup"><span data-stu-id="701d6-152">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="701d6-153">**Melden Sie sich im Azure-Portal als Administrator an** > **Azure Active Directory** > **Geräte** > **Geräteeinstellungen** >
**Benutzer festlegen, die Geräte zu Azure AD hinzufügen dürfen *Alle***</span><span class="sxs-lookup"><span data-stu-id="701d6-153">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="701d6-154">**Option 2:**: Ausgewählten Benutzern/Gruppen die Berechtigung zum Hinzufügen von Geräten zu Azure AD erteilen **Als Administrator im Azure-Portal anmelden** > **Azure Active Directory** > **Geräte** > **Geräteeinstellungen** >
**Die Option „Benutzer dürfen Geräte in Azure AD einbinden“ auf *Ausgewählt*** festlegen
![Abbildung, in der die Konfiguration von mit Azure AD verbundenen Geräten dargestellt ist</span><span class="sxs-lookup"><span data-stu-id="701d6-154">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices</span></span>](images/azure-ad-image.png)

    1. <span data-ttu-id="701d6-155">**Option 3:**: Sie können die Domäne so einstellen, dass kein Benutzer ein Gerät hinzufügen kann.</span><span class="sxs-lookup"><span data-stu-id="701d6-155">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="701d6-156">Dies bedeutet, dass alle Geräte manuell registriert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="701d6-156">This means that all devices will need to be manually enrolled.</span></span>

## <span data-ttu-id="701d6-157">Leitfaden zum Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="701d6-157">Mobile Device Manager Guidance</span></span>

### <span data-ttu-id="701d6-158">Fortlaufende Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="701d6-158">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="701d6-159">Dieser Schritt ist nur dann erforderlich, wenn Ihre Organisation die Verwaltung von HoloLens plant.</span><span class="sxs-lookup"><span data-stu-id="701d6-159">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="701d6-160">Die fortlaufende Geräteverwaltung hängt von ihrer Verwaltungsinfrastruktur für mobile Geräte ab.</span><span class="sxs-lookup"><span data-stu-id="701d6-160">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="701d6-161">Die meisten Infrastrukturen weisen die gleiche allgemeine Funktionalität auf, aber die Benutzeroberfläche kann stark variieren.</span><span class="sxs-lookup"><span data-stu-id="701d6-161">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="701d6-162">[CSPs (Configuration Service Providers, Kryptografiedienstanbieter)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) ermöglichen Ihnen das Erstellen und Bereitstellen von Verwaltungseinstellungen für die Geräte in Ihrem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="701d6-162">[CSPs (Configuration Service Providers)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) allows you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="701d6-163">Eine Liste der CSPs für HoloLens finden Sie [hier](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).</span><span class="sxs-lookup"><span data-stu-id="701d6-163">A list of CSPs for HoloLens can be found [here](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).</span></span>

1. <span data-ttu-id="701d6-164">[Compliance-Richtlinien](https://docs.microsoft.com/intune/device-compliance-get-started) sind Regeln und Einstellungen, die von Geräten erfüllt werden müssen, damit sie in Ihrer Unternehmensinfrastruktur kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="701d6-164">[Compliance policies](https://docs.microsoft.com/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="701d6-165">Verwenden Sie diese Richtlinien mit bedingtem Zugriff, um den Zugriff auf Unternehmensressourcen für Geräte zu blockieren, die nicht kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="701d6-165">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="701d6-166">So können Sie beispielsweise eine Richtlinie erstellen, die erfordert, dass BitLocker aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="701d6-166">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="701d6-167">[Erstellen einer Compliance-Richtlinie](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows)</span><span class="sxs-lookup"><span data-stu-id="701d6-167">[Create Compliance Policy](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="701d6-168">Bedingter Zugriff erlaubt/verweigert mobilen Geräten und mobilen Anwendungen den Zugriff auf Unternehmensressourcen.</span><span class="sxs-lookup"><span data-stu-id="701d6-168">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="701d6-169">Zwei Dokumente, die für Sie möglicherweise hilfreich sind: [Planen Sie Ihre Bereitstellung mit beschränktem Zugriff (CA, Conditional Access)](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) und [Bewährte Methoden](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span><span class="sxs-lookup"><span data-stu-id="701d6-169">Two documents you may find helpful are [Plan your CA Deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="701d6-170">[Dieser Artikel](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) befasst sich mit den Verwaltungstools von Intune für HoloLens.</span><span class="sxs-lookup"><span data-stu-id="701d6-170">[This article](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="701d6-171">Erstellen eines Marketingprofils</span><span class="sxs-lookup"><span data-stu-id="701d6-171">Create a device profile</span></span>](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <span data-ttu-id="701d6-172">Updates verwalten</span><span class="sxs-lookup"><span data-stu-id="701d6-172">Manage updates</span></span>

<span data-ttu-id="701d6-173">Intune enthält ein Feature namens „Updateringe“ für Windows 10-Geräte, einschließlich HoloLens 2 und HoloLens v1 (mit Holographic for Business).</span><span class="sxs-lookup"><span data-stu-id="701d6-173">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="701d6-174">Updateringe umfassen eine Gruppe von Einstellungen, mit denen festgelegt wird, wie und wann Updates installiert werden.</span><span class="sxs-lookup"><span data-stu-id="701d6-174">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="701d6-175">Sie können z. B. ein Wartungsfenster erstellen, um Updates zu installieren, oder Sie können nach der Installation von Updates einen Neustart auswählen.</span><span class="sxs-lookup"><span data-stu-id="701d6-175">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="701d6-176">Sie können auch beschließen, Updates für einen unbegrenzten Zeitraum anzuhalten, bis Sie bereit für die Aktualisierung sind.</span><span class="sxs-lookup"><span data-stu-id="701d6-176">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="701d6-177">Erfahren Sie mehr über das [Konfigurieren von Updateringen mit Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="701d6-177">Read more about [configuring update rings with Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

### <span data-ttu-id="701d6-178">Anwendungsverwaltung</span><span class="sxs-lookup"><span data-stu-id="701d6-178">Application management</span></span>

<span data-ttu-id="701d6-179">Verwalten von HoloLens-Anwendungen über:</span><span class="sxs-lookup"><span data-stu-id="701d6-179">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="701d6-180">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="701d6-180">Microsoft Store</span></span>  
  <span data-ttu-id="701d6-181">Der Microsoft Store ist die beste Möglichkeit, um Anwendungen auf HoloLens zu verteilen und zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="701d6-181">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="701d6-182">Es gibt eine großartige Gruppe von wichtigen HoloLens-Anwendungen, die bereits im Store verfügbar sind, oder Sie können [Ihre eigenen veröffentlichen](https://docs.microsoft.com/windows/uwp/publish/).</span><span class="sxs-lookup"><span data-stu-id="701d6-182">There is a great set of core HoloLens applications already available in the store or you can [publish your own](https://docs.microsoft.com/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="701d6-183">Alle Anwendungen im Store sind öffentlich für jeden verfügbar, wenn dies für Sie nicht akzeptabel ist, können Sie sich den Microsoft Store für Unternehmen ansehen.</span><span class="sxs-lookup"><span data-stu-id="701d6-183">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="701d6-184">Microsoft Store für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="701d6-184">Microsoft Store for Business</span></span>](https://docs.microsoft.com/microsoft-store/)  
  <span data-ttu-id="701d6-185">Der Microsoft Store für Unternehmen und Bildungseinrichtungen ist ein benutzerdefinierter Store für Ihre Unternehmensumgebung.</span><span class="sxs-lookup"><span data-stu-id="701d6-185">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="701d6-186">Sie können hier den in Windows 10 und HoloLens integrierten Microsoft Store verwenden, um Apps für Ihre Organisation zu suchen, zu erwerben, zu verteilen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="701d6-186">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="701d6-187">Sie können außerdem Apps bereitstellen, die für Ihre kommerzielle Umgebung spezifisch, aber für andere Personen nicht relevant sind.</span><span class="sxs-lookup"><span data-stu-id="701d6-187">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="701d6-188">Bereitstellung und Verwaltung von Anwendungen über Intune oder eine andere Lösung für die Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="701d6-188">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="701d6-189">Die meisten Lösungen für die Verwaltung mobiler Geräte, einschließlich Intune, bieten eine Möglichkeit zum direkten Bereitstellen von Branchenanwendungen für eine Reihe von registrierten Geräten.</span><span class="sxs-lookup"><span data-stu-id="701d6-189">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="701d6-190">Lesen Sie diesen Artikel für die [Intune-App-Installation](https://docs.microsoft.com/intune/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="701d6-190">See this article for [Intune app install](https://docs.microsoft.com/intune/apps-deploy).</span></span>

1. <span data-ttu-id="701d6-191">_nicht empfohlen_ Geräteportal</span><span class="sxs-lookup"><span data-stu-id="701d6-191">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="701d6-192">Anwendungen können mithilfe des Windows-Geräteportals auch direkt auf HoloLens installiert werden.</span><span class="sxs-lookup"><span data-stu-id="701d6-192">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="701d6-193">Dies wird nicht empfohlen, da der Entwicklermodus für die Verwendung des Geräteportals aktiviert sein muss.</span><span class="sxs-lookup"><span data-stu-id="701d6-193">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="701d6-194">Hier finden Sie weitere Informationen zum [Installieren von Apps auf HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span><span class="sxs-lookup"><span data-stu-id="701d6-194">Read more about [installing apps on HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span></span>

### <span data-ttu-id="701d6-195">Zertifikate</span><span class="sxs-lookup"><span data-stu-id="701d6-195">Certificates</span></span>

<span data-ttu-id="701d6-196">Sie können Zertifikate über Ihren MDM-Anbieter verteilen.</span><span class="sxs-lookup"><span data-stu-id="701d6-196">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="701d6-197">Wenn für Ihr Unternehmen Zertifikate erforderlich sind – Intune unterstützt PKCS, PFX und SCEP.</span><span class="sxs-lookup"><span data-stu-id="701d6-197">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="701d6-198">Es ist wichtig zu verstehen, welches Zertifikat für Ihr Unternehmen geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="701d6-198">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="701d6-199">Besuchen Sie bitte die Webseite unter [Hier](https://docs.microsoft.com/intune/protect/certificates-configure), um festzustellen, welches Zertifikat für Sie am besten geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="701d6-199">Please visit [here](https://docs.microsoft.com/intune/protect/certificates-configure) to determine which cert is best for you.</span></span> <span data-ttu-id="701d6-200">Wenn Sie beabsichtigen, Zertifikate für die HoloLens-Authentifizierung zu verwenden, eignen sich möglicherweise PFX oder SCEP für Sie.</span><span class="sxs-lookup"><span data-stu-id="701d6-200">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="701d6-201">Die Schritte für SCEP finden Sie [hier](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span><span class="sxs-lookup"><span data-stu-id="701d6-201">Steps for SCEP can be found [here](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span></span>

### <span data-ttu-id="701d6-202">Upgrade auf Holographics for Business Commercial Suite</span><span class="sxs-lookup"><span data-stu-id="701d6-202">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="701d6-203">Windows Holographics for Business Commercial Suite ist nur für HoloLens-Geräte der 1. Generation vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="701d6-203">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="701d6-204">Das Profil wird nicht auf HoloLens 2-Geräte angewendet.</span><span class="sxs-lookup"><span data-stu-id="701d6-204">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="701d6-205">Anweisungen für ein Upgrade auf die Commercial Suite finden [hier](https://docs.microsoft.com/intune/configuration/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="701d6-205">Directions for upgrading to the commercial suite can be found [here](https://docs.microsoft.com/intune/configuration/holographic-upgrade).</span></span>

### <span data-ttu-id="701d6-206">Konfigurieren des Kioskmodus mithilfe von Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="701d6-206">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="701d6-207">Synchronisieren Sie Microsoft Store mit Intune ([hier](https://docs.microsoft.com/intune/apps/windows-store-for-business))</span><span class="sxs-lookup"><span data-stu-id="701d6-207">Sync Microsoft Store to Intune ([Here](https://docs.microsoft.com/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="701d6-208">Prüfen Sie Ihre App-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="701d6-208">Check your app settings</span></span>
    1. <span data-ttu-id="701d6-209">Melden Sie sich bei Ihrem Microsoft Store Business-Konto an.</span><span class="sxs-lookup"><span data-stu-id="701d6-209">Log into your Microsoft Store Business account</span></span>
    1. **<span data-ttu-id="701d6-210">Verwalten > Produkte und Dienste > Apps und Software > Wählen Sie die App aus, die Sie synchronisieren möchten > Verfügbarkeit im Privaten Store > Wählen Sie "Alle" oder "Bestimmte Gruppen" aus.</span><span class="sxs-lookup"><span data-stu-id="701d6-210">Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"</span></span>**
        >[!NOTE]
        ><span data-ttu-id="701d6-211">Wenn die gewünschte App nicht angezeigt wird, müssen Sie die App "abrufen", indem Sie den Shop nach Ihrer App durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="701d6-211">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="701d6-212">**Klicken Sie auf die Leiste „Suchen“ in der oberen rechten Ecke > geben Sie den Namen der App ein > klicken Sie auf die App > wählen Sie „Abrufen“ aus**.</span><span class="sxs-lookup"><span data-stu-id="701d6-212">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="701d6-213">Wenn Ihre Apps unter **Intune > Client-Apps > Apps** nicht angezeigt werden, müssen Sie möglicherweise [Ihre Apps erneut synchronisieren](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps).</span><span class="sxs-lookup"><span data-stu-id="701d6-213">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="701d6-214">Erstellen eines Geräteprofils für den Kioskmodus</span><span class="sxs-lookup"><span data-stu-id="701d6-214">Create a device profile for Kiosk mode</span></span>](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="701d6-215">Sie können verschiedene Benutzer so konfigurieren, dass diese unterschiedliche Kioskmodus-Erlebnisse haben, indem Sie „Azure AD“ als „Benutzeranmeldungstyp“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="701d6-215">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="701d6-216">Diese Option steht jedoch nur im Multi-App-Kioskmodus zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="701d6-216">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="701d6-217">Der Multi-App-Kioskmodus funktioniert sowohl mit nur einer als auch mit mehreren Apps.</span><span class="sxs-lookup"><span data-stu-id="701d6-217">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![Abbildung, in der die Konfiguration des Kioskmodus in Intune dargestellt ist](images/aad-kioskmode.png)

<span data-ttu-id="701d6-219">Weitere MDM-Dienste finden Sie in der Dokumentation Ihres Anbieters.</span><span class="sxs-lookup"><span data-stu-id="701d6-219">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="701d6-220">Wenn Sie eine benutzerdefinierte Einstellung und eine vollständige XML-Konfiguration verwenden müssen, um einen Kiosk in Ihrem MDM-Dienst einzurichten, finden Sie [hier](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) weitere Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="701d6-220">If you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service, additional directions can be found [here](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)</span></span>

## <span data-ttu-id="701d6-221">Zertifikate und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="701d6-221">Certificates and Authentication</span></span>

<span data-ttu-id="701d6-222">Zertifikate können über Ihren MDM bereitgestellt werden (siehe "Zertifikate" im Abschnitt [MDM](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span><span class="sxs-lookup"><span data-stu-id="701d6-222">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="701d6-223">Zertifikate können auch über die Paketbereitstellung für HoloLens bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="701d6-223">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="701d6-224">Weitere Informationen finden Sie unter [HoloLens-Bereitstellung](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="701d6-224">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <span data-ttu-id="701d6-225">Weitere Intune-Quicklinks</span><span class="sxs-lookup"><span data-stu-id="701d6-225">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="701d6-226">[Profile erstellen:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profile ermöglichen es Ihnen, Einstellungen hinzuzufügen oder zu konfigurieren, die auf die Geräte in Ihrer Organisation verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="701d6-226">[Create Profiles:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

