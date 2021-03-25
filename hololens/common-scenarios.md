---
title: Szenarien für die Bereitstellung einer gemeinsamen Infrastruktur
description: Erfahren Sie mehr über einige der gängigsten Bereitstellungsszenarien, die auf unterschiedlichen Infrastrukturbereitstellungen für Mixed Reality basieren.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
keywords: hololens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448493"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="a36cb-104">Übersicht über allgemeine Infrastrukturbereitstellungsszenarien</span><span class="sxs-lookup"><span data-stu-id="a36cb-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="a36cb-105">Diese folgenden Informationen bieten eine allgemeine Architekturübersicht für drei gängige Szenarien beim Bereitstellen und Verwalten von Microsoft HoloLens 2-Geräten innerhalb des Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="a36cb-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="a36cb-106">Häufig wird die Verwaltung Ihrer Geräte und der Zugriff auf die Ressourcen Ihrer Organisation weitgehend von bereits vorhandenen Faktoren bestimmt.</span><span class="sxs-lookup"><span data-stu-id="a36cb-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="a36cb-107">Basierend auf der vorhandenen Infrastruktur laden wir Sie ein, den allgemeinen Geräteverwaltungsstil in den folgenden Szenarien zu überprüfen und unsere Anleitungen für die Bereitstellung in dem Szenario zu testen, das Ihren Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="a36cb-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="a36cb-108">Szenarien</span><span class="sxs-lookup"><span data-stu-id="a36cb-108">Scenarios</span></span>

<span data-ttu-id="a36cb-109">Das folgende Diagramm stellt drei typische Szenarien für HoloLens 2-Bereitstellungen dar.</span><span class="sxs-lookup"><span data-stu-id="a36cb-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![Szenariodiagramm](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a><span data-ttu-id="a36cb-111">Szenario A: Bereitstellen auf Cloud-Connect-Geräten</span><span class="sxs-lookup"><span data-stu-id="a36cb-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="a36cb-112">HoloLens 2 wird für die Verwendung in erster Linie in Umgebungen außerhalb eines Unternehmensnetzwerks bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a36cb-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="a36cb-113">Auf Unternehmensressourcen wird nicht zugegriffen oder kann über VPN eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="a36cb-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="a36cb-114">Diese Bereitstellung ähnelt verwalteten mobilen Geräten in einem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="a36cb-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="a36cb-115">Grundlegende allgemeine Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="a36cb-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="a36cb-116">Wi-Fi sind in der Regel vollständig für das Internet und die Clouddienste geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a36cb-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="a36cb-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span><span class="sxs-lookup"><span data-stu-id="a36cb-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="a36cb-118">Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="a36cb-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="a36cb-119">Einzelne oder mehrere Benutzer pro unterstützten Gerät</span><span class="sxs-lookup"><span data-stu-id="a36cb-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="a36cb-120">Unterschiedliche Stufen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von Fully Open bis Single App Kiosk.</span><span class="sxs-lookup"><span data-stu-id="a36cb-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="a36cb-121">Eine oder mehrere Anwendungen werden über MDM bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="a36cb-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="a36cb-122">Allgemeine Herausforderungen</span><span class="sxs-lookup"><span data-stu-id="a36cb-122">Common Challenges</span></span>
   * <span data-ttu-id="a36cb-123">Bestimmen, welche MDM-Konfigurationen auf holoLens 2 basierend auf den Szenarioanforderungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a36cb-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="a36cb-124">Eine Bereitstellungsanleitung, die dem Szenario ähnelt, finden Sie in unserem Leitfaden für [cloudintehte HoloLens 2 mit Remote assist](hololens2-cloud-connected-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a36cb-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a36cb-125">Bereitstellungshandbuch – Cloud-verbundenes HoloLens 2 mit Remoteunterstützung</span><span class="sxs-lookup"><span data-stu-id="a36cb-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="a36cb-126">Szenario B: Bereitstellen im Netzwerk Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="a36cb-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="a36cb-127">HoloLens 2 wird für die Verwendung hauptsächlich im Unternehmensnetzwerk mit Zugriff auf interne Unternehmensressourcen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a36cb-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="a36cb-128">Internet- und Clouddienste können eingeschränkt sein.</span><span class="sxs-lookup"><span data-stu-id="a36cb-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="a36cb-129">Diese Bereitstellung ist eine typische Bereitstellung für die meisten Windows 10-PCs.</span><span class="sxs-lookup"><span data-stu-id="a36cb-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="a36cb-130">Grundlegende allgemeine Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="a36cb-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="a36cb-131">Wi-Fi ist ein internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen und eingeschränktem Zugriff auf das Internet oder Clouddienste.</span><span class="sxs-lookup"><span data-stu-id="a36cb-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="a36cb-132">Azure AD Join with MDM Auto Enrollment</span><span class="sxs-lookup"><span data-stu-id="a36cb-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="a36cb-133">Verwaltetes MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="a36cb-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="a36cb-134">Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="a36cb-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="a36cb-135">Einzelne oder mehrere Benutzer pro unterstützten Gerät</span><span class="sxs-lookup"><span data-stu-id="a36cb-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="a36cb-136">Unterschiedliche Stufen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von Fully Open bis Single App Kiosk.</span><span class="sxs-lookup"><span data-stu-id="a36cb-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="a36cb-137">Eine oder mehrere Anwendungen werden über MDM bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="a36cb-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="a36cb-138">Allgemeine Herausforderungen</span><span class="sxs-lookup"><span data-stu-id="a36cb-138">Common Challenges</span></span>
   * <span data-ttu-id="a36cb-139">HoloLens 2 unterstützt keine lokale AD-Verknüpfung oder SCCM.</span><span class="sxs-lookup"><span data-stu-id="a36cb-139">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="a36cb-140">Nur Azure AD tritt mit MDM bei.</span><span class="sxs-lookup"><span data-stu-id="a36cb-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="a36cb-141">Viele Unternehmen stellen in diesem Szenario weiterhin Windows 10-PCs als lokale AD-beigetretene Geräte zur Verfügung, die von System Center Configuration Manager (SCCM) verwaltet werden und möglicherweise nicht die Infrastruktur für die Verwaltung interner Windows 10-Geräte über cloudbasierte MDM-Lösungen bereitgestellt/konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="a36cb-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="a36cb-142">Da HoloLens 2 ein erstes Cloudgerät ist, basiert es in hohem Maße auf internet- und cloudgebundenen Diensten für die Benutzerauthentifizierung, Betriebssystemupdates, MDM-Verwaltung und so weiter.</span><span class="sxs-lookup"><span data-stu-id="a36cb-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="a36cb-143">Beim Herstellen einer Verbindung mit einem Unternehmensnetzwerk müssen Proxy-/Firewallregeln höchstwahrscheinlich angepasst werden, um den Zugriff für HoloLens 2 und die darauf ausgeführten Anwendungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a36cb-143">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="a36cb-144">Für Wi-Fi Unternehmensverbindung sind in der Regel Zertifikate erforderlich, um das Gerät oder den Benutzer beim Netzwerk zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="a36cb-144">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="a36cb-145">Die erforderliche Infrastruktur oder Einstellungen zum Bereitstellen von Zertifikaten auf Windows 10-Geräten über MDM kann schwierig zu konfigurieren sein.</span><span class="sxs-lookup"><span data-stu-id="a36cb-145">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a36cb-146">Bereitstellungshandbuch – Unternehmensintegte HoloLens 2 mit Dynamics 365-Anleitungen</span><span class="sxs-lookup"><span data-stu-id="a36cb-146">Deployment Guide – Corporate connected HoloLens 2 with Dynamics 365 Guides</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="a36cb-147">Szenario C: Bereitstellen in sicherer Offlineumgebung</span><span class="sxs-lookup"><span data-stu-id="a36cb-147">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="a36cb-148">HoloLens 2 wird für die Verwendung hauptsächlich offline ohne Netzwerk- oder Internetzugriff bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a36cb-148">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="a36cb-149">Dies ist eine typische Bereitstellung für besonders sichere oder vertrauliche Standorte.</span><span class="sxs-lookup"><span data-stu-id="a36cb-149">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="a36cb-150">Grundlegende allgemeine Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="a36cb-150">Basic Common Configurations</span></span>
   * <span data-ttu-id="a36cb-151">Wi-Fi Konnektivität ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a36cb-151">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="a36cb-152">Ethernet über USB kann bei Bedarf für die LAN-Verbindung aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="a36cb-152">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="a36cb-153">Nicht verwaltet.</span><span class="sxs-lookup"><span data-stu-id="a36cb-153">Not Managed.</span></span>
   * <span data-ttu-id="a36cb-154">Lokales Benutzerkonto für die Geräte-Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="a36cb-154">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="a36cb-155">HoloLens 2 unterstützt nur ein lokales Konto.</span><span class="sxs-lookup"><span data-stu-id="a36cb-155">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="a36cb-156">Unterschiedliche Stufen von Gerätesperrungskonfigurationen werden über Bereitstellungspakete basierend auf bestimmten Verwendungsfällen angewendet.</span><span class="sxs-lookup"><span data-stu-id="a36cb-156">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="a36cb-157">Diese Konfigurationen sind in der Regel aufgrund der Anforderungen an eine sichere Umgebung eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="a36cb-157">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="a36cb-158">Mindestens eine Anwendung wird über das Bereitstellungspaket bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a36cb-158">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="a36cb-159">Allgemeine Herausforderungen</span><span class="sxs-lookup"><span data-stu-id="a36cb-159">Common Challenges</span></span>
   * <span data-ttu-id="a36cb-160">Es gibt eine begrenzte Anzahl von Konfigurationen, die über Bereitstellungspakete verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="a36cb-160">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="a36cb-161">Clouddienste können nicht verwendet werden, was die HoloLens 2-Funktionen einschränkt.</span><span class="sxs-lookup"><span data-stu-id="a36cb-161">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="a36cb-162">Höherer Verwaltungsaufwand, da diese Geräte manuell eingerichtet, konfiguriert und aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a36cb-162">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="a36cb-163">Eine Bereitstellungsanleitung, die diesem Szenario ähnelt, finden Sie in [unserem Leitfaden für die sichere Offlinebereitstellung.](hololens-common-scenarios-offline-secure.md)</span><span class="sxs-lookup"><span data-stu-id="a36cb-163">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a36cb-164">Bereitstellungshandbuch – Offline Secure HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a36cb-164">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
