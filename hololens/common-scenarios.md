---
title: Szenarien für die Bereitstellung einer gemeinsamen Infrastruktur
description: Erfahren Sie mehr über einige der gängigsten Bereitstellungsszenarien, die auf unterschiedlichen Infrastrukturbereitstellungen für Mixed Reality basieren.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 11/04/2020
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
ms.openlocfilehash: 6f398327ba82e15a15da21c2b3f90222178d257a
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283626"
---
# <span data-ttu-id="bdd9f-104">Übersicht über allgemeine Infrastrukturbereitstellungsszenarien</span><span class="sxs-lookup"><span data-stu-id="bdd9f-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="bdd9f-105">Die folgenden Informationen bieten eine allgemeine Architekturübersicht für drei gängige Szenarien beim Bereitstellen und Verwalten von Microsoft HoloLens 2-Geräten innerhalb des Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="bdd9f-106">Wie Sie Ihre Geräte verwalten und wie Sie auf die Ressourcen Ihrer Organisation zugreifen, hängt häufig von faktoren ab, die bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="bdd9f-107">Basierend auf der vorhandenen Infrastruktur laden wir Sie ein, den gemeinsamen Geräteverwaltungsstil in den folgenden Szenarien zu überprüfen und unsere Anleitungen für die Bereitstellung in dem Szenario zu testen, das Ihren Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <span data-ttu-id="bdd9f-108">Szenarien</span><span class="sxs-lookup"><span data-stu-id="bdd9f-108">Scenarios</span></span>

<span data-ttu-id="bdd9f-109">Das folgende Diagramm stellt drei typische Szenarien für HoloLens 2-Bereitstellungen dar.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![Szenariodiagramm](images/scenarios.jpg)

### <span data-ttu-id="bdd9f-111">Szenario A: Bereitstellen auf Cloud -Connect-Geräten</span><span class="sxs-lookup"><span data-stu-id="bdd9f-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="bdd9f-112">HoloLens 2 wird für die Verwendung in erster Linie in Umgebungen außerhalb eines Unternehmensnetzwerks bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="bdd9f-113">Auf Unternehmensressourcen wird nicht zugegriffen oder kann über VPN eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="bdd9f-114">Diese Bereitstellung ähnelt verwalteten mobilen Geräten in einem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="bdd9f-115">Grundlegende allgemeine Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="bdd9f-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="bdd9f-116">Wi-Fi sind in der Regel vollständig für internet- und cloudbasierte Dienste geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="bdd9f-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment --MDM (Intune) Managed</span><span class="sxs-lookup"><span data-stu-id="bdd9f-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="bdd9f-118">Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="bdd9f-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="bdd9f-119">Einzelne oder mehrere Benutzer pro Gerät unterstützt</span><span class="sxs-lookup"><span data-stu-id="bdd9f-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="bdd9f-120">Unterschiedliche Ebenen von Gerätesperrmoduskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von "Vollständig geöffnet" bis "Single App Kiosk".</span><span class="sxs-lookup"><span data-stu-id="bdd9f-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="bdd9f-121">Eine oder mehrere Anwendungen werden über MDM bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="bdd9f-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="bdd9f-122">Häufige Herausforderungen</span><span class="sxs-lookup"><span data-stu-id="bdd9f-122">Common Challenges</span></span>
   * <span data-ttu-id="bdd9f-123">Bestimmen der MDM-Konfigurationen, die auf HoloLens 2 angewendet werden, basierend auf den Szenarioanforderungen.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="bdd9f-124">Ein Bereitstellungshandbuch, das Szenario ähnelt. Lesen Sie unser Handbuch für mit der Cloud verbundene [HoloLens 2 mit Remote Assist.](hololens2-cloud-connected-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bdd9f-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bdd9f-125">Bereitstellungshandbuch – Mit der Cloud verbundene HoloLens 2 mit Remote Assist</span><span class="sxs-lookup"><span data-stu-id="bdd9f-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <span data-ttu-id="bdd9f-126">Szenario B: Bereitstellen innerhalb des Netzwerks Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="bdd9f-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="bdd9f-127">HoloLens 2 wird für die Verwendung in erster Linie im Unternehmensnetzwerk mit Zugriff auf interne Unternehmensressourcen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="bdd9f-128">Internet- und Clouddienste können eingeschränkt sein.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="bdd9f-129">Diese Bereitstellung ist eine typische Bereitstellung für die meisten Windows 10-PCs.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="bdd9f-130">Grundlegende allgemeine Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="bdd9f-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="bdd9f-131">Wi-Fi ist ein internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen und eingeschränktem Zugriff auf das Internet oder Clouddienste.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="bdd9f-132">Azure AD Join mit automatischer MDM-Registrierung</span><span class="sxs-lookup"><span data-stu-id="bdd9f-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="bdd9f-133">MDM (Intune) Managed</span><span class="sxs-lookup"><span data-stu-id="bdd9f-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="bdd9f-134">Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="bdd9f-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="bdd9f-135">Einzelne oder mehrere Benutzer pro Gerät unterstützt</span><span class="sxs-lookup"><span data-stu-id="bdd9f-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="bdd9f-136">Unterschiedliche Ebenen von Gerätesperrmoduskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von "Vollständig geöffnet" bis "Single App Kiosk".</span><span class="sxs-lookup"><span data-stu-id="bdd9f-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="bdd9f-137">Eine oder mehrere Anwendungen werden über MDM bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="bdd9f-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="bdd9f-138">Häufige Herausforderungen</span><span class="sxs-lookup"><span data-stu-id="bdd9f-138">Common Challenges</span></span>
   * <span data-ttu-id="bdd9f-139">HoloLens 2 unterstützt keine lokale AD-Verknüpfung oder SCCM.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-139">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="bdd9f-140">Nur Azure AD wird mit MDM beitreten.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="bdd9f-141">Viele Unternehmen stellen in diesem Szenario weiterhin Windows 10-PCs als lokale AD-beigetretene Geräte zur Verfügung, die von System Center Configuration Manager (SCCM) verwaltet werden und möglicherweise nicht die Infrastruktur für die Verwaltung interner Windows 10-Geräte über cloudbasierte MDM-Lösungen bereitgestellt/konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="bdd9f-142">Da HoloLens 2 ein erstes Cloudgerät ist, ist es in hohem Maße auf Internet- und Clouddienste für benutzerbasierte Authentifizierung, Betriebssystemupdates, die Verwaltung von MDM und vieles mehr angewiesen.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="bdd9f-143">Beim Herstellen einer Verbindung mit einem Unternehmensnetzwerk müssen Proxy-/Firewallregeln höchstwahrscheinlich angepasst werden, um den Zugriff für HoloLens 2 und die Darauf ausgeführten Anwendungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-143">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="bdd9f-144">Die Wi-Fi Unternehmensnetzwerk erfordert in der Regel Zertifikate, um das Gerät oder den Benutzer beim Netzwerk zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-144">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="bdd9f-145">Die erforderliche Infrastruktur oder einstellungen für die Bereitstellung von Zertifikaten auf Windows 10-Geräten über MDM kann eine Herausforderung darstellen.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-145">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="bdd9f-146">Szenario C: Bereitstellen in einer sicheren Offlineumgebung</span><span class="sxs-lookup"><span data-stu-id="bdd9f-146">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="bdd9f-147">HoloLens 2 wird für die Verwendung in erster Linie offline ohne Netzwerk- oder Internetzugriff bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-147">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="bdd9f-148">Dies ist eine typische Bereitstellung für hochgradig sichere oder vertrauliche Speicherorte.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-148">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="bdd9f-149">Grundlegende allgemeine Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="bdd9f-149">Basic Common Configurations</span></span>
   * <span data-ttu-id="bdd9f-150">Wi-Fi Konnektivität ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-150">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="bdd9f-151">Ethernet über USB kann bei Bedarf für die LAN-Konnektivität aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-151">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="bdd9f-152">Nicht verwaltet.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-152">Not Managed.</span></span>
   * <span data-ttu-id="bdd9f-153">Lokales Benutzerkonto für die Geräte-Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-153">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="bdd9f-154">HoloLens 2 unterstützt nur ein lokales Konto.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-154">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="bdd9f-155">Unterschiedliche Ebenen von Gerätesperrmoduskonfigurationen werden über Bereitstellungspakete basierend auf bestimmten Verwendungsfällen angewendet.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-155">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="bdd9f-156">Diese Konfigurationen sind in der Regel aufgrund sicherer Umgebungsanforderungen eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-156">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="bdd9f-157">Mindestens eine Anwendung wird über das Bereitstellungspaket bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="bdd9f-157">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="bdd9f-158">Häufige Herausforderungen</span><span class="sxs-lookup"><span data-stu-id="bdd9f-158">Common Challenges</span></span>
   * <span data-ttu-id="bdd9f-159">Es gibt eine begrenzte Anzahl von Konfigurationen, die über Bereitstellungspakete verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-159">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="bdd9f-160">Clouddienste können nicht verwendet werden, wodurch die HoloLens 2-Funktionen eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-160">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="bdd9f-161">Höherer Verwaltungsaufwand, da diese Geräte manuell eingerichtet, konfiguriert und aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="bdd9f-161">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="bdd9f-162">Ein Bereitstellungshandbuch, das diesem Szenario ähnelt, finden Sie im [Handbuch zur sicheren Offlinebereitstellung.](hololens-common-scenarios-offline-secure.md)</span><span class="sxs-lookup"><span data-stu-id="bdd9f-162">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bdd9f-163">Bereitstellungshandbuch – Offline Secure HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="bdd9f-163">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
