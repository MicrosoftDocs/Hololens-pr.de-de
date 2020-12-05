---
title: Szenarien für die Bereitstellung einer gemeinsamen Infrastruktur
description: Einige häufige Bereitstellungsszenarien auf Grundlage unterschiedlicher allgemeiner Infrastrukturen
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
ms.openlocfilehash: e9e91535bb49b5076547e8b9934bdc86808d41fc
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195568"
---
# <span data-ttu-id="5d810-104">Übersicht über die allgemeinen Infrastruktur Bereitstellungsszenarien</span><span class="sxs-lookup"><span data-stu-id="5d810-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="5d810-105">Diese folgenden Informationen bieten eine allgemeine Architektur Übersicht für drei häufige Szenarien beim Bereitstellen und Verwalten von Microsoft HoloLens 2-Geräten innerhalb des Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="5d810-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="5d810-106">Häufig wird die Art und Weise, wie Sie Ihre Geräte verwalten, und wie der Zugriff auf die Ressourcen Ihrer Organisation überwiegend durch bereits vorhandene Faktoren bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="5d810-106">Often how you manage your devices and how access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="5d810-107">Basierend auf der vorhandenen Infrastruktur laden wir Sie ein, den allgemeinen Geräte Verwaltungsstil in den folgenden Szenarien zu überprüfen und unsere Leitfäden für die Bereitstellung in dem Szenario zu testen, das Ihren Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="5d810-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <span data-ttu-id="5d810-108">Szenarien</span><span class="sxs-lookup"><span data-stu-id="5d810-108">Scenarios</span></span>

<span data-ttu-id="5d810-109">Das folgende Diagramm stellt drei typische Szenarien für HoloLens 2-Bereitstellungen dar.</span><span class="sxs-lookup"><span data-stu-id="5d810-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![Szenarien-Diagramm](images/scenarios.jpg)

### <span data-ttu-id="5d810-111">Szenario A: Bereitstellen auf Cloud Connect-Geräten</span><span class="sxs-lookup"><span data-stu-id="5d810-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="5d810-112">HoloLens 2 wird für die Verwendung in erster Linie in Umgebungen außerhalb eines Unternehmensnetzwerks bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5d810-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="5d810-113">Auf Unternehmensressourcen wird nicht zugegriffen, oder es ist möglich, dass Sie über VPN limitiert sind.</span><span class="sxs-lookup"><span data-stu-id="5d810-113">Corporate resources are not accessed or may be limited through VPN.</span></span> <span data-ttu-id="5d810-114">Hierbei handelt es sich um eine Bereitstellung, die mit verwalteten mobilen Geräten in einem Unternehmen vergleichbar ist.</span><span class="sxs-lookup"><span data-stu-id="5d810-114">This is a deployment very similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="5d810-115">Allgemeine Standardkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="5d810-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="5d810-116">Wi-Fi Netzwerke sind in der Regel vollständig für das Internet und die Cloud-Dienste geöffnet.</span><span class="sxs-lookup"><span data-stu-id="5d810-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="5d810-117">Azure AD Join with MDM Auto Enrollment--MDM (InTune) verwaltet</span><span class="sxs-lookup"><span data-stu-id="5d810-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
   * <span data-ttu-id="5d810-118">Benutzer anmelden mit einem eigenen Unternehmenskonto (AAD)</span><span class="sxs-lookup"><span data-stu-id="5d810-118">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="5d810-119">Einzelne oder mehrere Benutzer pro Gerät unterstützt</span><span class="sxs-lookup"><span data-stu-id="5d810-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="5d810-120">Unterschiedliche Ebenen der Geräte Sperrungs Konfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, vom vollständig geöffneten zum einzelnen App-Kiosk.</span><span class="sxs-lookup"><span data-stu-id="5d810-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="5d810-121">Eine oder mehrere Anwendungen werden über MDM bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5d810-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="5d810-122">Häufige Herausforderungen</span><span class="sxs-lookup"><span data-stu-id="5d810-122">Common Challenges</span></span>
   * <span data-ttu-id="5d810-123">Ermitteln, welche MDM-Konfigurationen auf das HoloLens 2 basierend auf den Szenarien erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5d810-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="5d810-124">Ein Bereitstellungshandbuch, das diesem Szenario ähnelt, finden Sie in unserem Leitfaden für [Cloud Connected HoloLens 2 mit Remote Unterstützung](hololens2-cloud-connected-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5d810-124">For a deployment guide that is similar to this scenario please review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5d810-125">Bereitstellungshandbuch – Cloud Connected HoloLens 2 mit Remote Unterstützung</span><span class="sxs-lookup"><span data-stu-id="5d810-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <span data-ttu-id="5d810-126">Szenario B: Bereitstellen im Netzwerk Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="5d810-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="5d810-127">HoloLens 2 wird für die Verwendung in erster Linie im Unternehmensnetzwerk mit Zugriff auf interne Unternehmensressourcen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5d810-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="5d810-128">Internet-und Cloud-Services sind möglicherweise limitiert.</span><span class="sxs-lookup"><span data-stu-id="5d810-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="5d810-129">Dies ist eine typische Bereitstellung für die meisten Windows 10-PCs.</span><span class="sxs-lookup"><span data-stu-id="5d810-129">This is a typical deployment for most Windows 10 PCs.</span></span>
 * <span data-ttu-id="5d810-130">Allgemeine Standardkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="5d810-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="5d810-131">Wi-Fi Netzwerk ist ein internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen sowie begrenztem Zugriff auf das Internet oder Cloud-Dienste.</span><span class="sxs-lookup"><span data-stu-id="5d810-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="5d810-132">Azure AD-Join mit automatischer MDM-Registrierung</span><span class="sxs-lookup"><span data-stu-id="5d810-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="5d810-133">MDM (InTune) verwaltet</span><span class="sxs-lookup"><span data-stu-id="5d810-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="5d810-134">Benutzer anmelden mit einem eigenen Unternehmenskonto (AAD)</span><span class="sxs-lookup"><span data-stu-id="5d810-134">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="5d810-135">Einzelne oder mehrere Benutzer pro Gerät unterstützt</span><span class="sxs-lookup"><span data-stu-id="5d810-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="5d810-136">Unterschiedliche Ebenen der Geräte Sperrungs Konfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, vom vollständig geöffneten zum einzelnen App-Kiosk.</span><span class="sxs-lookup"><span data-stu-id="5d810-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="5d810-137">Eine oder mehrere Anwendungen werden über MDM bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5d810-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="5d810-138">Häufige Herausforderungen</span><span class="sxs-lookup"><span data-stu-id="5d810-138">Common Challenges</span></span>
   * <span data-ttu-id="5d810-139">HoloLens 2 unterstützt keine lokale Ad Join-oder SCCM-Funktion.</span><span class="sxs-lookup"><span data-stu-id="5d810-139">HoloLens 2 does not support on premises AD join or SCCM.</span></span> <span data-ttu-id="5d810-140">Nur Azure AD-Join mit MDM.</span><span class="sxs-lookup"><span data-stu-id="5d810-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="5d810-141">Viele Unternehmen stellen heute weiterhin Windows 10-PCs in diesem Szenario bereit, wie auf lokalen AD-Join-Geräten, die von System Center Configuration Manager (SCCM) verwaltet werden und möglicherweise nicht über die Infrastruktur bereitgestellt/konfiguriert sind, um interne Windows 10-Geräte über Cloud-basierte MDM-Lösungen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="5d810-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud based MDM solutions.</span></span>
   * <span data-ttu-id="5d810-142">Da es sich bei HoloLens 2 um ein Cloud-First-Device handelt, basiert es stark auf Internet-und Cloud-verbundenen Diensten für Benutzerauthentifizierung, Betriebssystemupdates, MDM-Verwaltung usw. Beim Herstellen einer Verbindung mit einem Unternehmensnetzwerk müssen Proxy/Firewall-Regeln höchstwahrscheinlich angepasst werden, um den Zugriff auf HoloLens 2 und die darauf ausgeführten Anwendungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5d810-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, etc. When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="5d810-143">Für Unternehmens Wi-Fi Verbindungen sind in der Regel Zertifikate erforderlich, um das Gerät oder den Benutzer im Netzwerk zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="5d810-143">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="5d810-144">Die erforderliche Infrastruktur oder Einstellungen zum Bereitstellen von Zertifikaten auf Windows 10-Geräten über MDM können eine Herausforderung für die Konfiguration darstellen.</span><span class="sxs-lookup"><span data-stu-id="5d810-144">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="5d810-145">Szenario C: Bereitstellen in einer sicheren Offlineumgebung</span><span class="sxs-lookup"><span data-stu-id="5d810-145">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="5d810-146">HoloLens 2 wird für die Verwendung in erster Linie offline ohne Netzwerk-oder Internetzugriff bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5d810-146">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="5d810-147">Hierbei handelt es sich um eine typische Bereitstellung für hochsichere oder vertrauliche Speicherorte.</span><span class="sxs-lookup"><span data-stu-id="5d810-147">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="5d810-148">Allgemeine Standardkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="5d810-148">Basic Common Configurations</span></span>
   * <span data-ttu-id="5d810-149">Wi-Fi Konnektivität ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5d810-149">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="5d810-150">Ethernet über USB kann bei Bedarf für LAN-Konnektivität aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="5d810-150">Ethernet via USB may be enabled for LAN connectivity if required.</span></span>
   * <span data-ttu-id="5d810-151">Nicht verwaltet.</span><span class="sxs-lookup"><span data-stu-id="5d810-151">Not Managed.</span></span>
   * <span data-ttu-id="5d810-152">Lokales Benutzerkonto für Geräte Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="5d810-152">Local user account for device sign in.</span></span>
     * <span data-ttu-id="5d810-153">HoloLens 2 unterstützt nur 1 lokales Konto.</span><span class="sxs-lookup"><span data-stu-id="5d810-153">HoloLens 2 supports only 1 local account.</span></span>
   * <span data-ttu-id="5d810-154">Unterschiedliche Ebenen der Geräte Sperrungs Konfigurationen werden über Bereitstellungspakete basierend auf bestimmten Anwendungsfällen angewendet.</span><span class="sxs-lookup"><span data-stu-id="5d810-154">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="5d810-155">Diese Konfigurationen sind in der Regel aufgrund sicherer Umgebungsanforderungen sehr eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="5d810-155">These configurations are typically very restricted due to secure environment requirements.</span></span>
   * <span data-ttu-id="5d810-156">Eine oder mehrere Anwendungen werden über das Bereitstellungspaket bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5d810-156">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="5d810-157">Häufige Herausforderungen</span><span class="sxs-lookup"><span data-stu-id="5d810-157">Common Challenges</span></span>
   * <span data-ttu-id="5d810-158">Es gibt eine begrenzte Anzahl von Konfigurationen, die über Bereitstellungspakete zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="5d810-158">There are a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="5d810-159">Cloud-Dienste sind nicht in der Lage, Leveraged zu nutzen, wodurch die HoloLens 2-Funktionen eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="5d810-159">Cloud services are not able to be leveraged, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="5d810-160">Höherer Verwaltungsaufwand, da diese Geräte manuell eingerichtet, konfiguriert und aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="5d810-160">Higher administrative overhead since these devices have to be setup, configured, and updated manually.</span></span>

<span data-ttu-id="5d810-161">Ein Bereitstellungshandbuch, das mit diesem Szenario vergleichbar ist, finden Sie in unserem [Leitfaden zur sicheren Bereitstellung in der Offline Bereitstellung](hololens-common-scenarios-offline-secure.md).</span><span class="sxs-lookup"><span data-stu-id="5d810-161">For a deployment guide that is similar to this scenario please review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5d810-162">Bereitstellungshandbuch – Offline Secure HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="5d810-162">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
