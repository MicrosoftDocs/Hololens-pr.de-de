---
title: Übersicht über cloudbasierte HoloLens 2 mit Remote Assist
description: Erfahren Sie, wie Sie HoloLens 2 über ein mit der Cloud verbundenes Netzwerk registrieren, indem Sie Dynamics 365 Remote Assist.
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
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923532"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="bdc18-104">Bereitstellungshandbuch – Cloud connected HoloLens 2 with Remote Assist – Overview</span><span class="sxs-lookup"><span data-stu-id="bdc18-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="bdc18-105">Dieser Leitfaden hilft IT-Experten bei der Planung und Bereitstellung Microsoft HoloLens 2-Geräten mit Remote Assist in ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="bdc18-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="bdc18-106">Dies dient als Modell für Proof of Concept-Bereitstellungen für Ihre Organisation in einer Vielzahl HoloLens 2 Anwendungsfällen.</span><span class="sxs-lookup"><span data-stu-id="bdc18-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="bdc18-107">Das Setup ähnelt Szenario [A: Bereitstellen auf Cloud connect-Geräten.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)</span><span class="sxs-lookup"><span data-stu-id="bdc18-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="bdc18-108">Im Rahmen dieses Leitfadens erfahren Sie, wie Sie Ihre Geräte bei Ihrer Geräteverwaltung registrieren, lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer die Geräte bei der Geräteeinrichtung Remote Assist sofort verwenden können.</span><span class="sxs-lookup"><span data-stu-id="bdc18-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="bdc18-109">Hierzu gehen wir auf die wichtigen Infrastrukturteile ein, die erforderlich sind, um eingerichtet und ausgeführt zu werden– um eine Bedarfsbereitstellung mit HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="bdc18-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="bdc18-110">In diesem Leitfaden werden keine anderen Geräteeinschränkungen oder Konfigurationen angewendet. Wir empfehlen Ihnen jedoch, diese Optionen nach Abschluss des Handbuchs zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="bdc18-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bdc18-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="bdc18-111">Prerequisites</span></span>

<span data-ttu-id="bdc18-112">Die folgende Infrastruktur sollte zum Bereitstellen der -HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="bdc18-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="bdc18-113">Wenn dies nicht der Fall ist, ist das Einrichten von Azure und Intune in diesem Leitfaden enthalten:</span><span class="sxs-lookup"><span data-stu-id="bdc18-113">If not, setting up Azure and Intune is included in this guide:</span></span>

- <span data-ttu-id="bdc18-114">WLAN</span><span class="sxs-lookup"><span data-stu-id="bdc18-114">Wi-Fi</span></span>
    - <span data-ttu-id="bdc18-115">Netzwerke sind in der Regel für die Internet- und Clouddienste geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bdc18-115">Networks are typically open to the Internet and Cloud services</span></span>
- <span data-ttu-id="bdc18-116">Azure Active Directory (Azure AD) Join mit automatischer MDM-Registrierung ([Azure AD P1-Abonnement](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) erforderlich)</span><span class="sxs-lookup"><span data-stu-id="bdc18-116">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="bdc18-117">MDM (Intune) Verwaltet</span><span class="sxs-lookup"><span data-stu-id="bdc18-117">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="bdc18-118">Mindestens eine Anwendung wird über MDM bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bdc18-118">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="bdc18-119">Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="bdc18-119">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="bdc18-120">Einzelne oder mehrere Benutzer pro Gerät werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bdc18-120">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="Cloud verbundenes Szenario" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="bdc18-122">Weitere Informationen Remote Assist</span><span class="sxs-lookup"><span data-stu-id="bdc18-122">Learn about Remote Assist</span></span>

<span data-ttu-id="bdc18-123">Remote Assist ermöglicht gemeinsame Wartung und Reparatur, Remoteüberprüfung sowie Wissensfreigabe und Schulungen.</span><span class="sxs-lookup"><span data-stu-id="bdc18-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="bdc18-124">Durch Verbinden von Personen in verschiedenen Rollen und Standorten kann ein Techniker Remote Assist mit einem Remotemitarbeiter in Microsoft Teams eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="bdc18-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="bdc18-125">Sie können Videos, Screenshots und Anmerkungen kombinieren, um Probleme auch dann in Echtzeit zu lösen, wenn&#39;sich nicht am gleichen Ort befinden.</span><span class="sxs-lookup"><span data-stu-id="bdc18-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="bdc18-126">Remotemitarbeiter können Referenzbilder, Schemata und andere hilfreiche Informationen einfügen, die der Techniker&#39;physischem Raum enthält, damit sie auf das Schema verweisen können, während sie auf HoloLens kopf- und händefrei arbeiten.</span><span class="sxs-lookup"><span data-stu-id="bdc18-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="bdc18-127">Remote Assist Lizenzierung und Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bdc18-127">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="bdc18-128">Azure AD -Konto (erforderlich für den Erwerb des Abonnements und das Zuweisen von Lizenzen)</span><span class="sxs-lookup"><span data-stu-id="bdc18-128">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="bdc18-129">[Remote Assist -Abonnement](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (oder [Remote Assist-Testversion)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="bdc18-129">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="bdc18-130">Dynamics 365 Remote Assist Benutzer</span><span class="sxs-lookup"><span data-stu-id="bdc18-130">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="bdc18-131">Remote Assist Lizenz</span><span class="sxs-lookup"><span data-stu-id="bdc18-131">Remote Assist license</span></span>
- <span data-ttu-id="bdc18-132">Netzwerkverbindung</span><span class="sxs-lookup"><span data-stu-id="bdc18-132">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="bdc18-133">Microsoft Teams-Benutzer</span><span class="sxs-lookup"><span data-stu-id="bdc18-133">Microsoft Teams user</span></span>

- <span data-ttu-id="bdc18-134">Microsoft Teams oder [Teams Freemium](https://products.office.com/microsoft-teams/free).</span><span class="sxs-lookup"><span data-stu-id="bdc18-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="bdc18-135">Netzwerkkonnektivität</span><span class="sxs-lookup"><span data-stu-id="bdc18-135">Network connectivity</span></span>

<span data-ttu-id="bdc18-136">Wenn Sie dieses mandantenübergreifende [Szenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)implementieren möchten, benötigen Sie möglicherweise eine Lizenz für Informationsbarrieren.</span><span class="sxs-lookup"><span data-stu-id="bdc18-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="bdc18-137">In [diesem Artikel erfahren](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) Sie, ob eine Information Barrier License erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="bdc18-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="bdc18-138">In dieser Anleitung lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bdc18-138">In this guide you will:</span></span>

<span data-ttu-id="bdc18-139">Vorbereiten:</span><span class="sxs-lookup"><span data-stu-id="bdc18-139">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="bdc18-140">Erfahren Sie mehr über die Infrastruktur essentials für HoloLens 2 Geräte.</span><span class="sxs-lookup"><span data-stu-id="bdc18-140">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="bdc18-141">Erfahren Sie mehr über Azure AD und richten Sie eine ein, wenn Sie&#39;nicht haben.</span><span class="sxs-lookup"><span data-stu-id="bdc18-141">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="bdc18-142">Erfahren Sie mehr über die Identitätsverwaltung und die optimale Einrichtung Azure AD Konten.</span><span class="sxs-lookup"><span data-stu-id="bdc18-142">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="bdc18-143">Erfahren Sie mehr über MDM, und richten Sie Intune ein,&#39;sie noch nicht bereit sind.</span><span class="sxs-lookup"><span data-stu-id="bdc18-143">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="bdc18-144">Erfahren Sie mehr über die Netzwerkanforderungen Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="bdc18-144">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="bdc18-145">Optional: VPN zum Herstellen einer Verbindung mit Organisationsressourcen</span><span class="sxs-lookup"><span data-stu-id="bdc18-145">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="bdc18-146">Konfiguration von:</span><span class="sxs-lookup"><span data-stu-id="bdc18-146">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="bdc18-147">Erstellen von Benutzern und Gruppen.</span><span class="sxs-lookup"><span data-stu-id="bdc18-147">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="bdc18-148">Einrichten der automatischen Registrierung in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bdc18-148">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="bdc18-149">Zuweisen von Anwendungslizenzen</span><span class="sxs-lookup"><span data-stu-id="bdc18-149">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="bdc18-150">Bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="bdc18-150">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="bdc18-151">Richten Sie Ihre HoloLens 2 ein, und überprüfen Sie die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="bdc18-151">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="bdc18-152">Überprüfen Sie, ob Sie einen Remote Assist können.</span><span class="sxs-lookup"><span data-stu-id="bdc18-152">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="bdc18-153">Warten:</span><span class="sxs-lookup"><span data-stu-id="bdc18-153">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="bdc18-154">Aktualisieren von Remote Assist mithilfe der Microsoft Store-App.</span><span class="sxs-lookup"><span data-stu-id="bdc18-154">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="bdc18-155">Erstellen eines Supportplans.</span><span class="sxs-lookup"><span data-stu-id="bdc18-155">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="bdc18-156">Entwicklungsplan.</span><span class="sxs-lookup"><span data-stu-id="bdc18-156">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="bdc18-157">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="bdc18-157">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bdc18-158">Mit der Cloud verbundene Bereitstellung: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="bdc18-158">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

