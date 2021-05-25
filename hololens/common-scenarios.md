---
title: Allgemeine Bereitstellungsszenarien für die Infrastruktur
description: Erfahren Sie mehr über einige der gängigsten Bereitstellungsszenarien, die auf verschiedenen Infrastrukturbereitstellungen für Mixed Reality basieren.
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
ms.openlocfilehash: 30a35fb0fe5d5b669249df25ebff0228b552596c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397419"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="bbda3-104">Allgemeine Bereitstellungsszenarien für die Infrastruktur – Übersicht</span><span class="sxs-lookup"><span data-stu-id="bbda3-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="bbda3-105">Die folgenden Informationen bieten eine allgemeine Übersicht über die Architektur für drei gängige Szenarien beim Bereitstellen und Verwalten von Microsoft HoloLens 2 Geräten im Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="bbda3-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="bbda3-106">Häufig wird die Art und Weise, wie Sie Ihre Geräte verwalten und wie Sie auf die Ressourcen Ihrer Organisation zugreifen, größtenteils von bereits festgelegten Faktoren bestimmt.</span><span class="sxs-lookup"><span data-stu-id="bbda3-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="bbda3-107">Basierend auf der vorhandenen Infrastruktur laden wir Sie ein, den allgemeinen Geräteverwaltungsstil in den folgenden Szenarien zu überprüfen und unsere Leitfäden für die Bereitstellung in dem Szenario auszuprobieren, das Ihren Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="bbda3-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="bbda3-108">Szenarien</span><span class="sxs-lookup"><span data-stu-id="bbda3-108">Scenarios</span></span>

<span data-ttu-id="bbda3-109">Das folgende Diagramm zeigt zwei typische verwaltete Szenarien für HoloLens 2 Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="bbda3-109">The diagram below represents two typical managed scenarios for HoloLens 2 deployments.</span></span>
 

<span data-ttu-id="bbda3-110">Es gibt auch ein drittes Szenario, das sichere Offlinebereitstellungen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="bbda3-110">There is also third scenario that allows for offline secure deployments.</span></span>

### <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="bbda3-111">Szenario A: Bereitstellen auf mit der Cloud verbundenen Geräten</span><span class="sxs-lookup"><span data-stu-id="bbda3-111">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="bbda3-112">HoloLens 2 wird für die Verwendung in erster Linie in Umgebungen außerhalb eines Unternehmensnetzwerks bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bbda3-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="bbda3-113">Auf Unternehmensressourcen wird nicht zugegriffen oder kann über VPN eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="bbda3-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="bbda3-114">Diese Bereitstellung ähnelt verwalteten mobilen Geräten innerhalb eines Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="bbda3-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="bbda3-115">Grundlegende allgemeine Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="bbda3-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="bbda3-116">Wi-Fi-Netzwerke sind in der Regel vollständig für das Internet und cloudbasierte Dienste geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bbda3-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="bbda3-117">Azure AD join with Mobile Geräteverwaltung (MDM) Auto Enrollment –MDM (Intune) Managed</span><span class="sxs-lookup"><span data-stu-id="bbda3-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="bbda3-118">Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="bbda3-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="bbda3-119">Unterstützter Einzelbenutzer oder mehrere Benutzer pro Gerät</span><span class="sxs-lookup"><span data-stu-id="bbda3-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="bbda3-120">Verschiedene Ebenen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von Vollständig geöffnet bis Einzel-App-Kiosk.</span><span class="sxs-lookup"><span data-stu-id="bbda3-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="bbda3-121">Mindestens eine Anwendung wird über MDM bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bbda3-121">One or more applications are deployed via MDM</span></span>



* <span data-ttu-id="bbda3-122">Häufige Herausforderungen</span><span class="sxs-lookup"><span data-stu-id="bbda3-122">Common Challenges</span></span>
   * <span data-ttu-id="bbda3-123">Bestimmen der MDM-Konfigurationen, die auf die HoloLens 2 angewendet werden sollen, basierend auf den Szenarioanforderungen.</span><span class="sxs-lookup"><span data-stu-id="bbda3-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="bbda3-124">[![Szenario: Diagramm ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="bbda3-124">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="bbda3-125">Ein Bereitstellungshandbuch, das diesem Szenario ähnelt, ist in unserem Leitfaden für die [Bereitstellung der cloudfähigen Umgebung zu lesen.](hololens2-cloud-connected-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bbda3-125">For a deployment guide that is similar to this scenario review our guide for [Cloud connected environment deployment guide](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bbda3-126">Bereitstellungshandbuch für eine mit der Cloud verbundene Umgebung</span><span class="sxs-lookup"><span data-stu-id="bbda3-126">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="bbda3-127">Bereitstellungshandbuch für eine cloudverbundene Umgebung (externe Clients)</span><span class="sxs-lookup"><span data-stu-id="bbda3-127">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="bbda3-128">Szenario B: Bereitstellen innerhalb des Netzwerks Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="bbda3-128">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="bbda3-129">HoloLens 2 wird für die Verwendung in erster Linie im Unternehmensnetzwerk mit Zugriff auf interne Unternehmensressourcen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bbda3-129">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="bbda3-130">Internet- und Clouddienste können eingeschränkt sein.</span><span class="sxs-lookup"><span data-stu-id="bbda3-130">Internet and cloud services may be limited.</span></span> <span data-ttu-id="bbda3-131">Diese Bereitstellung ist eine typische Bereitstellung für die meisten Windows 10 PCs.</span><span class="sxs-lookup"><span data-stu-id="bbda3-131">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="bbda3-132">Grundlegende allgemeine Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="bbda3-132">Basic Common Configurations</span></span>
   * <span data-ttu-id="bbda3-133">Wi-Fi Netzwerk ist ein internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen und eingeschränktem Zugriff auf das Internet oder Clouddienste.</span><span class="sxs-lookup"><span data-stu-id="bbda3-133">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="bbda3-134">Azure AD Beitreten zur automatischen MDM-Registrierung</span><span class="sxs-lookup"><span data-stu-id="bbda3-134">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="bbda3-135">MDM (Intune) Verwaltet</span><span class="sxs-lookup"><span data-stu-id="bbda3-135">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="bbda3-136">Benutzer melden sich mit ihrem eigenen Unternehmenskonto (Azure AD) an.</span><span class="sxs-lookup"><span data-stu-id="bbda3-136">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="bbda3-137">Einzelne oder mehrere Benutzer pro Gerät unterstützt</span><span class="sxs-lookup"><span data-stu-id="bbda3-137">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="bbda3-138">Unterschiedliche Ebenen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von Vollständig geöffnet bis zu Kiosk mit einzelner App.</span><span class="sxs-lookup"><span data-stu-id="bbda3-138">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="bbda3-139">Eine oder mehrere Anwendungen werden über MDM bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bbda3-139">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="bbda3-140">Häufige Herausforderungen</span><span class="sxs-lookup"><span data-stu-id="bbda3-140">Common Challenges</span></span>
   * <span data-ttu-id="bbda3-141">HoloLens 2 unterstützt keine lokale AD-Verknüpfung oder SCCM.</span><span class="sxs-lookup"><span data-stu-id="bbda3-141">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="bbda3-142">Nur Azure AD mit MDM beitreten.</span><span class="sxs-lookup"><span data-stu-id="bbda3-142">Only Azure AD join with MDM.</span></span> <span data-ttu-id="bbda3-143">Viele Unternehmen stellen in diesem Szenario weiterhin Windows 10-PCs als lokale, in AD verbundene Geräte bereit, die von System Center Konfigurations-Manager (SCCM) verwaltet werden. Möglicherweise ist die Infrastruktur für die Verwaltung interner Windows 10-Geräte über cloudbasierte MDM-Lösungen nicht bereitgestellt/konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="bbda3-143">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="bbda3-144">Da HoloLens 2 ein cloudbasiertes Gerät ist, ist es stark von mit dem Internet und der Cloud verbundenen Diensten für Benutzerauthentifizierung, Betriebssystemupdates, MDM-Verwaltung und so weiter abhängig.</span><span class="sxs-lookup"><span data-stu-id="bbda3-144">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="bbda3-145">Beim Herstellen einer Verbindung mit einem Unternehmensnetzwerk müssen wahrscheinlich Proxy-/Firewallregeln angepasst werden, um den Zugriff für HoloLens 2 anwendungen zu ermöglichen, die darauf ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bbda3-145">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="bbda3-146">UnternehmensWi-Fi verbindung erfordert in der Regel Zertifikate, um das Gerät oder den Benutzer beim Netzwerk zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="bbda3-146">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="bbda3-147">Die erforderliche Infrastruktur oder Einstellungen zum Bereitstellen von Zertifikaten auf Windows 10 Geräten über MDM kann eine Herausforderung darstellen.</span><span class="sxs-lookup"><span data-stu-id="bbda3-147">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="bbda3-148">[![Diagramm zu Szenario B1 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="bbda3-148">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="bbda3-149">[![Diagramm zu Szenario B2 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="bbda3-149">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="bbda3-150">Ein Bereitstellungshandbuch, das diesem Szenario ähnelt, finden Sie in unserem Leitfaden für die [Bereitstellung von Unternehmensnetzwerken.](hololens2-corp-connected-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bbda3-150">For a deployment guide that is similar to this scenario review our guide for [Corporate network deployment guide](hololens2-corp-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bbda3-151">Handbuch zur Bereitstellung von Unternehmensnetzwerken</span><span class="sxs-lookup"><span data-stu-id="bbda3-151">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="bbda3-152">Szenario C: Bereitstellen in einer sicheren Offlineumgebung</span><span class="sxs-lookup"><span data-stu-id="bbda3-152">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="bbda3-153">HoloLens 2 wird für die Verwendung in erster Linie offline ohne Netzwerk- oder Internetzugriff bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bbda3-153">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="bbda3-154">Dies ist eine typische Bereitstellung für äußerst sichere oder vertrauliche Standorte.</span><span class="sxs-lookup"><span data-stu-id="bbda3-154">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="bbda3-155">Grundlegende allgemeine Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="bbda3-155">Basic Common Configurations</span></span>
   * <span data-ttu-id="bbda3-156">Wi-Fi Die Konnektivität ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="bbda3-156">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="bbda3-157">Ethernet über USB kann bei Bedarf für LAN-Verbindungen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="bbda3-157">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="bbda3-158">Nicht verwaltet.</span><span class="sxs-lookup"><span data-stu-id="bbda3-158">Not Managed.</span></span>
   * <span data-ttu-id="bbda3-159">Lokales Benutzerkonto für die Geräte-Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="bbda3-159">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="bbda3-160">HoloLens 2 unterstützt nur ein lokales Konto.</span><span class="sxs-lookup"><span data-stu-id="bbda3-160">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="bbda3-161">Unterschiedliche Ebenen von Gerätesperrungskonfigurationen werden über Bereitstellungspakete basierend auf bestimmten Anwendungsfällen angewendet.</span><span class="sxs-lookup"><span data-stu-id="bbda3-161">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="bbda3-162">Diese Konfigurationen sind in der Regel aufgrund sicherer Umgebungsanforderungen eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="bbda3-162">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="bbda3-163">Eine oder mehrere Anwendungen werden über das Bereitstellungspaket bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bbda3-163">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="bbda3-164">Häufige Herausforderungen</span><span class="sxs-lookup"><span data-stu-id="bbda3-164">Common Challenges</span></span>
   * <span data-ttu-id="bbda3-165">Über Bereitstellungspakete steht nur ein begrenzter Satz von Konfigurationen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bbda3-165">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="bbda3-166">Clouddienste können nicht verwendet werden, wodurch die HoloLens 2 Funktionen eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="bbda3-166">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="bbda3-167">Höherer Verwaltungsaufwand, da diese Geräte manuell eingerichtet, konfiguriert und aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="bbda3-167">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="bbda3-168">[![Sicheres Offlinediagramm 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="bbda3-168">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="bbda3-169">Ein Bereitstellungshandbuch, das diesem Szenario ähnelt, ist im [Bereitstellungshandbuch für die sichere Offlineumgebung zu lesen.](hololens-common-scenarios-offline-secure.md)</span><span class="sxs-lookup"><span data-stu-id="bbda3-169">For a deployment guide that is similar to this scenario review our [Offline secure environment deployment guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bbda3-170">Bereitstellungshandbuch für eine sichere Offlineumgebung</span><span class="sxs-lookup"><span data-stu-id="bbda3-170">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)
