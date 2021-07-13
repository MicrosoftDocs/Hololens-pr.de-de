---
title: Übersicht über cloudbasierte HoloLens 2 mit Remote Assist
description: Erfahren Sie, wie Sie HoloLens 2 über ein mit der Cloud verbundenes Netzwerk registrieren, indem Dynamics 365 Remote Assist.
keywords: HoloLens, Verwaltung, cloudgebunden, Remote Assist, AAD, Azure AD, MDM, Mobile Geräteverwaltung
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 26fd2def8ce1fa8f960ab930e209c74fb37e2e0a
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639759"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="13649-104">Bereitstellungshandbuch – Cloud connected HoloLens 2 with Remote Assist – Overview (Bereitstellungshandbuch – Cloud connected HoloLens 2 with Remote Assist – Übersicht)</span><span class="sxs-lookup"><span data-stu-id="13649-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="13649-105">Dieser Leitfaden hilft IT-Experten bei der Planung und Bereitstellung Microsoft HoloLens 2-Geräten mit Remote Assist in ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="13649-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="13649-106">Dies dient als Modell für Proof of Concept-Bereitstellungen für Ihre Organisation in verschiedenen HoloLens 2 Anwendungsfällen.</span><span class="sxs-lookup"><span data-stu-id="13649-106">This will serve as a model for proof-of-concept deployments to your organization across various HoloLens 2 use cases.</span></span> <span data-ttu-id="13649-107">Das Setup ähnelt Szenario [A: Bereitstellen auf Cloud connect-Geräten.](common-scenarios.md#scenario-a)</span><span class="sxs-lookup"><span data-stu-id="13649-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](common-scenarios.md#scenario-a).</span></span> 

<span data-ttu-id="13649-108">Im Rahmen dieses Leitfadens erfahren Sie, wie Sie Ihre Geräte bei Ihrer Geräteverwaltung registrieren, lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer die Geräte bei der Geräteeinrichtung Remote Assist sofort verwenden können.</span><span class="sxs-lookup"><span data-stu-id="13649-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="13649-109">Hierzu werden die wichtigen Infrastrukturteile, die für die Einrichtung und Ausführung erforderlich sind, durch die Bereitstellung im großen Stil mit HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="13649-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="13649-110">In diesem Leitfaden werden keine anderen Geräteeinschränkungen oder Konfigurationen angewendet. Wir empfehlen Ihnen jedoch, diese Optionen nach Abschluss des Handbuchs zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="13649-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="13649-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="13649-111">Prerequisites</span></span>

<span data-ttu-id="13649-112">Die folgende Infrastruktur sollte zum Bereitstellen der -HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="13649-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="13649-113">Wenn dies nicht der Fall ist, ist das Einrichten von Azure und Intune in diesem Leitfaden enthalten:</span><span class="sxs-lookup"><span data-stu-id="13649-113">If not, setting up Azure and Intune is included in this guide:</span></span>

<span data-ttu-id="13649-114">Dies ist ein ähnliches Setup wie Szenario [A:](/hololens/common-scenarios#scenario-a)Bereitstellen auf Cloud connect-Geräten. Dies ist eine gute Option für viele Proof of Concept-Bereitstellungen, die Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="13649-114">This is a setup similar to [Scenario A: Deploy to cloud connect devices](/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="13649-115">Wi-Fi-Netzwerke sind in der Regel vollständig für das Internet und cloudbasierte Dienste geöffnet.</span><span class="sxs-lookup"><span data-stu-id="13649-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="13649-116">Azure AD bei der automatischen MDM-Registrierung – MDM-verwaltet (Intune)</span><span class="sxs-lookup"><span data-stu-id="13649-116">Azure AD Join with MDM Auto Enrollment—MDM-managed (Intune)</span></span>
- <span data-ttu-id="13649-117">Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="13649-117">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="13649-118">Einzelne oder mehrere Benutzer pro Gerät werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="13649-118">Single or multiple users per device are supported.</span></span>

:::image type="content" alt-text="Cloud verbundenes Szenario" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="13649-120">Weitere Informationen Remote Assist</span><span class="sxs-lookup"><span data-stu-id="13649-120">Learn about Remote Assist</span></span>

<span data-ttu-id="13649-121">Remote Assist ermöglicht gemeinsame Wartung und Reparatur, Remoteüberprüfung sowie Wissensfreigabe und Schulungen.</span><span class="sxs-lookup"><span data-stu-id="13649-121">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="13649-122">Durch das Verbinden von Personen an verschiedenen Rollen und Standorten kann ein Techniker, der Remote Assist verwendet, eine Verbindung mit einem Remotemitarbeiter auf Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="13649-122">By connecting people in different roles and locations, a technician who uses Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="13649-123">Sie können Videos, Screenshots und Anmerkungen kombinieren, um Probleme auch dann in Echtzeit zu lösen, wenn sie sich nicht am gleichen Ort befinden.</span><span class="sxs-lookup"><span data-stu-id="13649-123">They can combine video, screenshots, and annotations to solve problems in real time even when they aren't in the same location.</span></span> <span data-ttu-id="13649-124">Remotemitarbeiter können Referenzbilder, Schemata und andere hilfreiche Informationen in den physischen Raum des Technikers einfügen, damit sie auf das Schema verweisen können, während sie kopfauf und frei bei der Arbeit HoloLens.</span><span class="sxs-lookup"><span data-stu-id="13649-124">Remote collaborators can insert reference images, schematics, and other helpful information the technician's physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="13649-125">Remote Assist Lizenzierung und Anforderungen</span><span class="sxs-lookup"><span data-stu-id="13649-125">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="13649-126">Azure AD -Konto (erforderlich für den Erwerb des Abonnements und das Zuweisen von Lizenzen)</span><span class="sxs-lookup"><span data-stu-id="13649-126">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="13649-127">[Remote Assist -Abonnement](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (oder [Remote Assist-Testversion)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="13649-127">[Remote Assist subscription](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="13649-128">Dynamics 365 Remote Assist Benutzer</span><span class="sxs-lookup"><span data-stu-id="13649-128">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="13649-129">Remote Assist Lizenz</span><span class="sxs-lookup"><span data-stu-id="13649-129">Remote Assist license</span></span>
- <span data-ttu-id="13649-130">Netzwerkverbindung</span><span class="sxs-lookup"><span data-stu-id="13649-130">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="13649-131">Microsoft Teams Benutzer</span><span class="sxs-lookup"><span data-stu-id="13649-131">Microsoft Teams user</span></span>

- <span data-ttu-id="13649-132">Microsoft Teams oder [Teams Freemium.](https://products.office.com/microsoft-teams/free)</span><span class="sxs-lookup"><span data-stu-id="13649-132">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="13649-133">Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="13649-133">Network connectivity</span></span>

<span data-ttu-id="13649-134">Wenn Sie dieses mandantenübergreifende [Szenario](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)implementieren möchten, benötigen Sie möglicherweise eine Lizenz für Informationsbarrieren.</span><span class="sxs-lookup"><span data-stu-id="13649-134">If you plan on implementing this [cross-tenant scenario](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="13649-135">Informationen dazu, ob eine Information Barrier License erforderlich ist, finden Sie unter Anbieter und Kunden, die vollständige Dynamics 365 Remote Assist [verwenden.](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation)</span><span class="sxs-lookup"><span data-stu-id="13649-135">To determine if an Information Barrier License is required, see [Vendors and customers use full Dynamics 365 Remote Assist capabilities](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation).</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="13649-136">In dieser Anleitung lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="13649-136">In this guide you will:</span></span>

<span data-ttu-id="13649-137">Vorbereiten:</span><span class="sxs-lookup"><span data-stu-id="13649-137">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="13649-138">Erfahren Sie mehr über die Infrastruktur essentials für HoloLens 2 Geräte.</span><span class="sxs-lookup"><span data-stu-id="13649-138">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="13649-139">Erfahren Sie mehr über Azure AD und richten Sie eine ein, wenn Sie&#39;nicht haben.</span><span class="sxs-lookup"><span data-stu-id="13649-139">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="13649-140">Erfahren Sie mehr über die Identitätsverwaltung und die optimale Einrichtung Azure AD Konten.</span><span class="sxs-lookup"><span data-stu-id="13649-140">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="13649-141">Erfahren Sie mehr über MDM, und richten Sie Intune ein,&#39;sie noch nicht bereit sind.</span><span class="sxs-lookup"><span data-stu-id="13649-141">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="13649-142">Erfahren Sie mehr über die Netzwerkanforderungen Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="13649-142">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="13649-143">Optional: VPN zum Herstellen einer Verbindung mit Organisationsressourcen</span><span class="sxs-lookup"><span data-stu-id="13649-143">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="13649-144">Konfiguration von:</span><span class="sxs-lookup"><span data-stu-id="13649-144">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="13649-145">Erstellen von Benutzern und Gruppen.</span><span class="sxs-lookup"><span data-stu-id="13649-145">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="13649-146">Einrichten der automatischen Registrierung in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="13649-146">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="13649-147">Zuweisen von Anwendungslizenzen</span><span class="sxs-lookup"><span data-stu-id="13649-147">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="13649-148">Bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="13649-148">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="13649-149">Richten Sie Ihre HoloLens 2 ein, und überprüfen Sie die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="13649-149">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="13649-150">Überprüfen Sie, ob Sie einen Remote Assist können.</span><span class="sxs-lookup"><span data-stu-id="13649-150">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="13649-151">Warten:</span><span class="sxs-lookup"><span data-stu-id="13649-151">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="13649-152">Aktualisieren von Remote Assist mithilfe der Microsoft Store-App.</span><span class="sxs-lookup"><span data-stu-id="13649-152">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="13649-153">Erstellen eines Supportplans.</span><span class="sxs-lookup"><span data-stu-id="13649-153">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="13649-154">Entwicklungsplan.</span><span class="sxs-lookup"><span data-stu-id="13649-154">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="13649-155">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="13649-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="13649-156">Mit der Cloud verbundene Bereitstellung: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="13649-156">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

