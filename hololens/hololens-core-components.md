---
title: Planen einer HoloLens 2-Bereitstellung in einer kommerziellen Umgebung
description: Erfahren Sie mehr über die grundlegenden Anforderungen für die Bereitstellung und Verwaltung von HoloLens in Unternehmensumgebungen, einschließlich Infrastruktur, Azure Active Directory und Verwaltung mobiler Geräte.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 43162389eae82bc09135c62acd40d71048d14db1
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639079"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="039f6-103">Planen einer HoloLens 2-Bereitstellung in einer kommerziellen Umgebung</span><span class="sxs-lookup"><span data-stu-id="039f6-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="039f6-104">Überblick</span><span class="sxs-lookup"><span data-stu-id="039f6-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="039f6-105">Diese Übersicht soll IT-Experten dabei helfen, Überlegungen zum Bereitstellen und Verwalten von Microsoft HoloLens 2-Geräten in einer Organisation zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="039f6-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="039f6-106">Informationen zu Geräteendbenutzern finden Sie unter [Vorbereiten ihrer HoloLens 2 für](hololens2-setup.md) die ersten Schritte.</span><span class="sxs-lookup"><span data-stu-id="039f6-106">For device end users, see [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="039f6-107">HoloLens 2 wird auf Windows 10 Holographic ausgeführt, der Organisationen stabile, flexible, integrierte Technologien für die Verwaltung mobiler Geräte und Apps bietet.</span><span class="sxs-lookup"><span data-stu-id="039f6-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="039f6-108">Windows 10 Holographic unterstützt die End-to-End-Verwaltung des Gerätelebenszyklus, um Unternehmen die Kontrolle über ihre Geräte, Daten und Apps zu geben.</span><span class="sxs-lookup"><span data-stu-id="039f6-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="039f6-109">Die HoloLens 2 lassen sich problemlos in die Standardlebenszyklusmethoden integrieren– von der Geräteregistrierung, Konfiguration und Anwendungsverwaltung bis hin zu Wartung und Außerbetriebsetzung mithilfe einer umfassenden Lösung für die Verwaltung mobiler Geräte.</span><span class="sxs-lookup"><span data-stu-id="039f6-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="039f6-110">Die folgenden Schritte und Videos können Sie durch den Prozess der HoloLens 2 Einführung in Ihrer Organisation führen.</span><span class="sxs-lookup"><span data-stu-id="039f6-110">The following steps and video can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| &nbsp; | &nbsp; |
|--|--|
| ![Schritt 1](images/1green.png)| <br/> <span data-ttu-id="039f6-112">**[Allgemeine Bereitstellungsszenarien:](hololens-requirements.md)** Verstehen Sie Bereitstellungsszenarien, und untersuchen Sie die Kernkomponenten, die zum Bereitstellen HoloLens 2 Geräten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="039f6-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![Schritt 2](images/2green.png)| <br/> <span data-ttu-id="039f6-114">**[Vorbereiten:](#prepare)** Machen Sie sich mit den infrastrukturellen Grundlagen vertraut, die für HoloLens 2 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="039f6-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![Schritt 3](images/3green.png) | <br/> <span data-ttu-id="039f6-116">**[Konfigurieren:](#configure)** Erfahren Sie, wie Sie Ihre wesentlichen Komponenten für eine cloudbasierte Bereitstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="039f6-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![Schritt 4](images/4green.png) | <br/> <span data-ttu-id="039f6-118">**[Bereitstellen:](#deploy)** Erfahren Sie, wie Sie Ihre Geräte bereitstellen und Ihre Anwendungen sicher und effizient verteilen.</span><span class="sxs-lookup"><span data-stu-id="039f6-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![Schritt 5](images/5green.png) | <br/> <span data-ttu-id="039f6-120">**[Verwalten:](#maintain)** Ermitteln Sie, was erforderlich ist, um den Zustand Ihrer HoloLens 2 Geräte ordnungsgemäß zu verwalten und die Einhaltung der Unternehmensrichtlinie sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="039f6-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a><span data-ttu-id="039f6-121">Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="039f6-121">Prepare</span></span>

<span data-ttu-id="039f6-122">Erfahren Sie mehr über wichtige Infrastrukturdienste, die erforderlich sind, um den vollständigen Satz von HoloLens 2 Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="039f6-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span>

| <span data-ttu-id="039f6-123">Komponente</span><span class="sxs-lookup"><span data-stu-id="039f6-123">Component</span></span> | <span data-ttu-id="039f6-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="039f6-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="039f6-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="039f6-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="039f6-126">Ermöglicht die Identitäts- und Zugriffsverwaltung für die HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="039f6-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="039f6-127">Mobile Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="039f6-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="039f6-128">Verwaltet HoloLens 2 Geräte, die mit Ihrem Mandanten verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="039f6-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="039f6-129">WLAN-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="039f6-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="039f6-130">Wi-Fi ist verfügbar, und Geräte können mit dem Internet verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="039f6-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="039f6-131">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="039f6-131">Configure</span></span>

<span data-ttu-id="039f6-132">Verwenden Sie Intune und Autopilot als Low-Touch-Lösungen zum Registrieren und Konfigurieren von HoloLens 2 für den Azure AD Mandanten und mdm Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="039f6-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="039f6-133">Komponente</span><span class="sxs-lookup"><span data-stu-id="039f6-133">Component</span></span> | <span data-ttu-id="039f6-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="039f6-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="039f6-135">Automatische Registrierung</span><span class="sxs-lookup"><span data-stu-id="039f6-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="039f6-136">Nach der ersten Anmeldung registrieren sich Geräte automatisch bei Azure AD und registrieren sich bei MDM.</span><span class="sxs-lookup"><span data-stu-id="039f6-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="039f6-137">Anwendungslizenzen</span><span class="sxs-lookup"><span data-stu-id="039f6-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="039f6-138">Kann auf Benutzer, Benutzergruppen oder Gerätegruppen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="039f6-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="039f6-139">Azure-Benutzer und -Gruppen</span><span class="sxs-lookup"><span data-stu-id="039f6-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="039f6-140">Hilft beim Zuweisen von Konfigurationen und Lizenzen für die HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="039f6-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="039f6-141">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="039f6-141">Deploy</span></span>

<span data-ttu-id="039f6-142">Verteilen Sie Ihre HoloLens 2 Geräte, und überprüfen Sie deren Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="039f6-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="039f6-143">Komponente</span><span class="sxs-lookup"><span data-stu-id="039f6-143">Component</span></span> | <span data-ttu-id="039f6-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="039f6-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="039f6-145">Überprüfung der Registrierung</span><span class="sxs-lookup"><span data-stu-id="039f6-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="039f6-146">Vergewissern Sie sich, dass das Gerät über Einstellungen oder das Azure-Portal Azure AD eingebunden wurde.</span><span class="sxs-lookup"><span data-stu-id="039f6-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="039f6-147">Zertifikatüberprüfung</span><span class="sxs-lookup"><span data-stu-id="039f6-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="039f6-148">Überprüfen sie die Einstellungen, und überprüfen Sie, ob sie ordnungsgemäß verteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="039f6-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="039f6-149">Überprüfen von App-Installationen</span><span class="sxs-lookup"><span data-stu-id="039f6-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="039f6-150">Vergewissern Sie sich, dass die App vorhanden ist und an Ihrer HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="039f6-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="039f6-151">Verwalten</span><span class="sxs-lookup"><span data-stu-id="039f6-151">Maintain</span></span>

<span data-ttu-id="039f6-152">Verwenden Sie Windows Update for Business zusammen mit Ihrem MDM-System oder der Microsoft Store, um Ihre HoloLens 2 und Apps auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="039f6-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="039f6-153">Komponente</span><span class="sxs-lookup"><span data-stu-id="039f6-153">Component</span></span> | <span data-ttu-id="039f6-154">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="039f6-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="039f6-155">Aktualisieren HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="039f6-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="039f6-156">Konfigurieren von Updates nach Bedarf über Windows Updates for Business</span><span class="sxs-lookup"><span data-stu-id="039f6-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="039f6-157">Aktualisieren von Apps</span><span class="sxs-lookup"><span data-stu-id="039f6-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="039f6-158">Konfigurieren über Ihr MDM-System oder die Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="039f6-158">Configure through your MDM system or the Microsoft Store</span></span>
