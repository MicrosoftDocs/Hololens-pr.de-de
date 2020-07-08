---
title: Allgemeine Szenarien für die Infrastrukturbereitstellung
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 6/30/2020
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
ms.openlocfilehash: f8d69fc988afabad5f4ae1cce9003381ceb8e68c
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857890"
---
# <span data-ttu-id="33a9a-103">Allgemeine Szenarien für die Infrastrukturbereitstellung</span><span class="sxs-lookup"><span data-stu-id="33a9a-103">Common Infrastructure Deployment Scenarios</span></span>
<span data-ttu-id="33a9a-104">Diese folgenden Informationen bieten eine allgemeine Architektur Übersicht für drei häufige Szenarien beim Bereitstellen und Verwalten von Microsoft HoloLens 2-Geräten innerhalb des Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="33a9a-104">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

## <span data-ttu-id="33a9a-105">Szenarien</span><span class="sxs-lookup"><span data-stu-id="33a9a-105">Scenarios</span></span>

<span data-ttu-id="33a9a-106">Das folgende Diagramm stellt drei typische Szenarien für HoloLens 2-Bereitstellungen dar.</span><span class="sxs-lookup"><span data-stu-id="33a9a-106">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span> 
![Szenarien](images/scenarios.jpg)

### <span data-ttu-id="33a9a-108">Szenario A</span><span class="sxs-lookup"><span data-stu-id="33a9a-108">Scenario A</span></span>

<span data-ttu-id="33a9a-109">HoloLens 2 wird für die Verwendung in erster Linie in Umgebungen außerhalb eines Unternehmensnetzwerks bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="33a9a-109">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="33a9a-110">Auf Unternehmensressourcen wird nicht zugegriffen, oder es ist möglich, dass Sie über VPN limitiert sind.</span><span class="sxs-lookup"><span data-stu-id="33a9a-110">Corporate resources are not accessed or may be limited through VPN.</span></span> <span data-ttu-id="33a9a-111">Hierbei handelt es sich um eine Bereitstellung, die mit verwalteten mobilen Geräten in einem Unternehmen vergleichbar ist.</span><span class="sxs-lookup"><span data-stu-id="33a9a-111">This is a deployment very similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="33a9a-112">Allgemeine Standardkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="33a9a-112">Basic Common Configurations</span></span>
   * <span data-ttu-id="33a9a-113">WLAN-Netzwerke sind in der Regel vollständig für das Internet und die Cloud-Dienste geöffnet.</span><span class="sxs-lookup"><span data-stu-id="33a9a-113">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="33a9a-114">Azure AD Join with MDM Auto Enrollment--MDM (InTune) verwaltet</span><span class="sxs-lookup"><span data-stu-id="33a9a-114">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
   * <span data-ttu-id="33a9a-115">Benutzer anmelden mit einem eigenen Unternehmenskonto (AAD)</span><span class="sxs-lookup"><span data-stu-id="33a9a-115">Users sign in with their own corporate account (AAD)</span></span> 
     * <span data-ttu-id="33a9a-116">Einzelne oder mehrere Benutzer pro Gerät unterstützt</span><span class="sxs-lookup"><span data-stu-id="33a9a-116">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="33a9a-117">Unterschiedliche Ebenen der Geräte Sperrungs Konfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, vom vollständig geöffneten zum einzelnen App-Kiosk.</span><span class="sxs-lookup"><span data-stu-id="33a9a-117">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="33a9a-118">Eine oder mehrere Anwendungen werden über MDM bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="33a9a-118">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="33a9a-119">Häufige Herausforderungen</span><span class="sxs-lookup"><span data-stu-id="33a9a-119">Common Challenges</span></span>
   * <span data-ttu-id="33a9a-120">Ermitteln, welche MDM-Konfigurationen auf das HoloLens 2 basierend auf den Szenarien erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="33a9a-120">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

### <span data-ttu-id="33a9a-121">Szenario B</span><span class="sxs-lookup"><span data-stu-id="33a9a-121">Scenario B</span></span>

<span data-ttu-id="33a9a-122">HoloLens 2 wird für die Verwendung in erster Linie im Unternehmensnetzwerk mit Zugriff auf interne Unternehmensressourcen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="33a9a-122">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="33a9a-123">Internet-und Cloud-Services sind möglicherweise limitiert.</span><span class="sxs-lookup"><span data-stu-id="33a9a-123">Internet and cloud services may be limited.</span></span> <span data-ttu-id="33a9a-124">Dies ist eine typische Bereitstellung für die meisten Windows 10-PCs.</span><span class="sxs-lookup"><span data-stu-id="33a9a-124">This is a typical deployment for most Windows 10 PCs.</span></span>
 * <span data-ttu-id="33a9a-125">Allgemeine Standardkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="33a9a-125">Basic Common Configurations</span></span>
   * <span data-ttu-id="33a9a-126">Das Wi-Fi-Netzwerk ist ein internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen und begrenztem Zugriff auf das Internet oder Cloud-Dienste.</span><span class="sxs-lookup"><span data-stu-id="33a9a-126">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="33a9a-127">Azure AD-Join mit automatischer MDM-Registrierung</span><span class="sxs-lookup"><span data-stu-id="33a9a-127">Azure AD Join with MDM Auto Enrollment</span></span> 
   * <span data-ttu-id="33a9a-128">MDM (InTune) verwaltet</span><span class="sxs-lookup"><span data-stu-id="33a9a-128">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="33a9a-129">Benutzer anmelden mit einem eigenen Unternehmenskonto (AAD)</span><span class="sxs-lookup"><span data-stu-id="33a9a-129">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="33a9a-130">Einzelne oder mehrere Benutzer pro Gerät unterstützt</span><span class="sxs-lookup"><span data-stu-id="33a9a-130">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="33a9a-131">Unterschiedliche Ebenen der Geräte Sperrungs Konfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, vom vollständig geöffneten zum einzelnen App-Kiosk.</span><span class="sxs-lookup"><span data-stu-id="33a9a-131">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="33a9a-132">Eine oder mehrere Anwendungen werden über MDM bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="33a9a-132">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="33a9a-133">Häufige Herausforderungen</span><span class="sxs-lookup"><span data-stu-id="33a9a-133">Common Challenges</span></span>
   * <span data-ttu-id="33a9a-134">HoloLens 2 unterstützt keine lokale Ad Join-oder SCCM-Funktion.</span><span class="sxs-lookup"><span data-stu-id="33a9a-134">HoloLens 2 does not support on premises AD join or SCCM.</span></span> <span data-ttu-id="33a9a-135">Nur Azure AD-Join mit MDM.</span><span class="sxs-lookup"><span data-stu-id="33a9a-135">Only Azure AD join with MDM.</span></span> <span data-ttu-id="33a9a-136">Viele Unternehmen stellen heute weiterhin Windows 10-PCs in diesem Szenario bereit, wie auf lokalen AD-Join-Geräten, die von System Center Configuration Manager (SCCM) verwaltet werden und möglicherweise nicht über die Infrastruktur bereitgestellt/konfiguriert sind, um interne Windows 10-Geräte über Cloud-basierte MDM-Lösungen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="33a9a-136">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud based MDM solutions.</span></span>
   * <span data-ttu-id="33a9a-137">Da es sich bei HoloLens 2 um ein Cloud-First-Device handelt, basiert es stark auf Internet-und Cloud-verbundenen Diensten für Benutzerauthentifizierung, Betriebssystemupdates, MDM-Verwaltung usw. Beim Herstellen einer Verbindung mit einem Unternehmensnetzwerk müssen Proxy/Firewall-Regeln höchstwahrscheinlich angepasst werden, um den Zugriff auf HoloLens 2 und die darauf ausgeführten Anwendungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="33a9a-137">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, etc. When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span> 
   * <span data-ttu-id="33a9a-138">Für die Wi-Fi-Verbindung in Unternehmen sind in der Regel Zertifikate erforderlich, um das Gerät oder den Benutzer im Netzwerk zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="33a9a-138">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="33a9a-139">Die erforderliche Infrastruktur oder Einstellungen zum Bereitstellen von Zertifikaten auf Windows 10-Geräten über MDM können eine Herausforderung für die Konfiguration darstellen.</span><span class="sxs-lookup"><span data-stu-id="33a9a-139">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="33a9a-140">Szenario C</span><span class="sxs-lookup"><span data-stu-id="33a9a-140">Scenario C</span></span>

<span data-ttu-id="33a9a-141">HoloLens 2 wird für die Verwendung in erster Linie offline ohne Netzwerk-oder Internetzugriff bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="33a9a-141">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="33a9a-142">Hierbei handelt es sich um eine typische Bereitstellung für hochsichere oder vertrauliche Speicherorte.</span><span class="sxs-lookup"><span data-stu-id="33a9a-142">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="33a9a-143">Allgemeine Standardkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="33a9a-143">Basic Common Configurations</span></span>
   * <span data-ttu-id="33a9a-144">Wi-Fi-Konnektivität ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="33a9a-144">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="33a9a-145">Ethernet über USB kann bei Bedarf für LAN-Konnektivität aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="33a9a-145">Ethernet via USB may be enabled for LAN connectivity if required.</span></span>
   * <span data-ttu-id="33a9a-146">Nicht verwaltet.</span><span class="sxs-lookup"><span data-stu-id="33a9a-146">Not Managed.</span></span>
   * <span data-ttu-id="33a9a-147">Lokales Benutzerkonto für Geräte Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="33a9a-147">Local user account for device sign in.</span></span>
     * <span data-ttu-id="33a9a-148">HoloLens 2 unterstützt nur 1 lokales Konto.</span><span class="sxs-lookup"><span data-stu-id="33a9a-148">HoloLens 2 supports only 1 local account.</span></span>
   * <span data-ttu-id="33a9a-149">Unterschiedliche Ebenen der Geräte Sperrungs Konfigurationen werden über Bereitstellungspakete basierend auf bestimmten Anwendungsfällen angewendet.</span><span class="sxs-lookup"><span data-stu-id="33a9a-149">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="33a9a-150">Diese Konfigurationen sind in der Regel aufgrund sicherer Umgebungsanforderungen sehr eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="33a9a-150">These configurations are typically very restricted due to secure environment requirements.</span></span>
   * <span data-ttu-id="33a9a-151">Eine oder mehrere Anwendungen werden über das Bereitstellungspaket bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="33a9a-151">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="33a9a-152">Häufige Herausforderungen</span><span class="sxs-lookup"><span data-stu-id="33a9a-152">Common Challenges</span></span>
   * <span data-ttu-id="33a9a-153">Es gibt eine begrenzte Anzahl von Konfigurationen, die über Bereitstellungspakete zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="33a9a-153">There are a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="33a9a-154">Cloud-Dienste sind nicht in der Lage, Leveraged zu nutzen, wodurch die HoloLens 2-Funktionen eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="33a9a-154">Cloud services are not able to be leveraged, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="33a9a-155">Höherer Verwaltungsaufwand, da diese Geräte manuell eingerichtet, konfiguriert und aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="33a9a-155">Higher administrative overhead since these devices have to be setup, configured, and updated manually.</span></span>
