---
title: Bereitstellungshandbuch – Unternehmensverknannte HoloLens 2 mit Dynamics 365 Guides – Übersicht
description: Erfahren Sie, wie Sie HoloLens 2 Geräte mit Dynamics 365 Guides über ein verbundenes Unternehmensnetzwerk registrieren.
keywords: HoloLens, Verwaltung, unternehmensverbunden, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Geräteverwaltung
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f2f7e1425a208e1f466d995f66118b7e68984242
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637012"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="a781f-104">Bereitstellungshandbuch – Unternehmensverknannte HoloLens 2 mit Dynamics 365 Guides – Übersicht</span><span class="sxs-lookup"><span data-stu-id="a781f-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="a781f-105">Dieser Leitfaden unterstützt IT-Experten bei der Planung und Bereitstellung von Microsoft HoloLens 2-Geräten mit Dynamics 365 Guides (Handbüchern) für ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="a781f-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="a781f-106">Dieser Leitfaden eignet sich hervorragend für Pilot- und Produktionsbereitstellungen und ähnelt dem [Leitfaden Szenario B: Bereitstellen innerhalb des Netzwerks Ihrer Organisation.](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network)</span><span class="sxs-lookup"><span data-stu-id="a781f-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="a781f-107">Nachdem Sie Ihren Proof of Concept getestet haben, verwenden Sie diesen Leitfaden, um mit der Integration von HoloLens in Ihre Organisation fortzugehen.</span><span class="sxs-lookup"><span data-stu-id="a781f-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="a781f-108">In diesem Leitfaden erfahren Sie, wie Sie Ihre Geräte bei Ihrer vorhandenen Geräteverwaltung registrieren, Lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer nach der Geräteeinrichtung einen Dynamics 365-Leitfaden betreiben und benutzerdefinierte Branchen-Apps verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a781f-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a781f-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a781f-109">Prerequisites</span></span>

<span data-ttu-id="a781f-110">Die folgende Infrastruktur sollte bereits vorhanden sein:</span><span class="sxs-lookup"><span data-stu-id="a781f-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="a781f-111">WLAN</span><span class="sxs-lookup"><span data-stu-id="a781f-111">Wi-Fi</span></span>
    - <span data-ttu-id="a781f-112">Internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen und eingeschränktem Zugriff auf das Internet oder Clouddienste</span><span class="sxs-lookup"><span data-stu-id="a781f-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="a781f-113">Gerätebasierte Zertifikatauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="a781f-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="a781f-114">Azure Active Directory (Azure AD) Beitreten zur automatischen MDM-Registrierung[(Azure AD P1-Abonnement](/azure/active-directory/fundamentals/active-directory-whatis) erforderlich)</span><span class="sxs-lookup"><span data-stu-id="a781f-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="a781f-115">MDM (Intune) Verwaltet</span><span class="sxs-lookup"><span data-stu-id="a781f-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="a781f-116">Eine oder mehrere Anwendungen werden über MDM bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a781f-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="a781f-117">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="a781f-117">Network</span></span> 
    - <span data-ttu-id="a781f-118">Zertifikate (SCEP oder PKCS)</span><span class="sxs-lookup"><span data-stu-id="a781f-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="a781f-119">Proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="a781f-119">Proxy configuration</span></span>
- <span data-ttu-id="a781f-120">Benutzer melden sich mit ihrem eigenen Unternehmenskonto (Azure AD) an.</span><span class="sxs-lookup"><span data-stu-id="a781f-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="a781f-121">Einzelne oder mehrere Benutzer pro Gerät werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a781f-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="a781f-122">Unterschiedliche Ebenen von Gerätesperrungskonfigurationen, die basierend auf bestimmten Anwendungsfällen angewendet werden, von Vollständig geöffnet bis Kiosk mit einzelner App.</span><span class="sxs-lookup"><span data-stu-id="a781f-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="a781f-123">Handbücher – Lizenzierung und Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a781f-123">Guides Licensing and Requirements</span></span>](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- <span data-ttu-id="a781f-124">Azure AD-Konto</span><span class="sxs-lookup"><span data-stu-id="a781f-124">Azure AD account</span></span>
- <span data-ttu-id="a781f-125">pc und HoloLens Dynamics 365 Guides Anwendungen</span><span class="sxs-lookup"><span data-stu-id="a781f-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="a781f-126">Dynamics 365 Guides-Abonnement</span><span class="sxs-lookup"><span data-stu-id="a781f-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="a781f-127">Microsoft Dataverse (enthalten)</span><span class="sxs-lookup"><span data-stu-id="a781f-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="a781f-128">Power Apps (enthalten)</span><span class="sxs-lookup"><span data-stu-id="a781f-128">Power Apps (included)</span></span>
- <span data-ttu-id="a781f-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="a781f-129">Power BI Desktop</span></span>
- <span data-ttu-id="a781f-130">Netzwerkverbindung</span><span class="sxs-lookup"><span data-stu-id="a781f-130">Network Connectivity</span></span>

<span data-ttu-id="a781f-131">[![Diagramm des verbundenen Unternehmensnetzwerks, Phase 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a781f-131">[ ![Corp connected network diagram, stage 1](./images/deployment-guides-revised-scenario-b-01-1.png) ](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="a781f-132">[![Diagramm des verbundenen Unternehmensnetzwerks, Phase 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a781f-132">[ ![Corp connected network diagram, stage 2](./images/deployment-guides-revised-scenario-b-02-1.png) ](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="a781f-133">In dieser Anleitung lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a781f-133">In this guide you will:</span></span>
### <a name="prepare"></a><span data-ttu-id="a781f-134">Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="a781f-134">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="a781f-135">Erfahren Sie mehr über die Grundlegendes zur Infrastruktur für HoloLens 2 Geräte.</span><span class="sxs-lookup"><span data-stu-id="a781f-135">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="a781f-136">Erfahren Sie mehr über Azure AD, und richten Sie eine ein, wenn Sie sie nicht haben.</span><span class="sxs-lookup"><span data-stu-id="a781f-136">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="a781f-137">Erfahren Sie mehr über die Identitätsverwaltung und die optimale Einrichtung Azure AD Konten.</span><span class="sxs-lookup"><span data-stu-id="a781f-137">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="a781f-138">Erfahren Sie mehr über MDM, und richten Sie intune ein, wenn Sie noch keine bereit haben.</span><span class="sxs-lookup"><span data-stu-id="a781f-138">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="a781f-139">Machen Sie sich mit zertifikatbasiertem WLAN vertraut.</span><span class="sxs-lookup"><span data-stu-id="a781f-139">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="a781f-140">Machen Sie sich mit proxy vertraut.</span><span class="sxs-lookup"><span data-stu-id="a781f-140">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="a781f-141">Erfahren Sie, wie Sie Branchen-Apps verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a781f-141">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="a781f-142">Erfahren Sie mehr über die Verwendung von Handbüchern für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="a781f-142">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="a781f-143">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="a781f-143">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="a781f-144">Erstellen von Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="a781f-144">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="a781f-145">Einrichten der automatischen Registrierung.</span><span class="sxs-lookup"><span data-stu-id="a781f-145">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="a781f-146">Einrichten von Wi-Fi Zertifikaten und Profilen für unternehmensinterne Wi-Fi Konnektivität.</span><span class="sxs-lookup"><span data-stu-id="a781f-146">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="a781f-147">Hochladen und Zuweisen von LOB-App-Paketen (Line of Business).</span><span class="sxs-lookup"><span data-stu-id="a781f-147">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="a781f-148">Richten Sie Dynamics 365 Guides ein.</span><span class="sxs-lookup"><span data-stu-id="a781f-148">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="a781f-149">Konfigurieren des Kioskmodus (optional)</span><span class="sxs-lookup"><span data-stu-id="a781f-149">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="a781f-150">Konfigurieren von WDAC (optional).</span><span class="sxs-lookup"><span data-stu-id="a781f-150">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="a781f-151">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="a781f-151">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="a781f-152">Überprüfen Sie die Registrierung per Gerät und MDM.</span><span class="sxs-lookup"><span data-stu-id="a781f-152">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="a781f-153">Überprüfen Sie Wi-Fi Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="a781f-153">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="a781f-154">Überprüfen sie die Installation einer branchenspezifische App.</span><span class="sxs-lookup"><span data-stu-id="a781f-154">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="a781f-155">Überprüfen Von Handbüchern über Erstellung und Betrieb.</span><span class="sxs-lookup"><span data-stu-id="a781f-155">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="a781f-156">Verwalten</span><span class="sxs-lookup"><span data-stu-id="a781f-156">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="a781f-157">Aktualisieren Sie HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a781f-157">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="a781f-158">Aktualisieren von Handbüchern (Store-Apps).</span><span class="sxs-lookup"><span data-stu-id="a781f-158">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="a781f-159">Aktualisieren branchenspezifische Apps.</span><span class="sxs-lookup"><span data-stu-id="a781f-159">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="a781f-160">Entwicklungsplan:</span><span class="sxs-lookup"><span data-stu-id="a781f-160">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="a781f-161">Erstellen eines Supportplans.</span><span class="sxs-lookup"><span data-stu-id="a781f-161">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="a781f-162">Optionen für die Geräteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="a781f-162">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="a781f-163">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="a781f-163">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="a781f-164">Unternehmensverbundene Bereitstellung – Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="a781f-164">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
