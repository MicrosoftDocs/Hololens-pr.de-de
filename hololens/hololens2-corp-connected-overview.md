---
title: Bereitstellungshandbuch – Unternehmensverknte HoloLens 2 mit Dynamics 365-Anleitungen – Übersicht
description: Erfahren Sie, wie Sie HoloLens 2-Geräte mit Dynamics 365-Anleitungen über ein verbundenes Unternehmensnetzwerk registrieren.
keywords: HoloLens, Verwaltung, unternehmensgebunden, Dynamics 365-Anleitungen, AAD, Azure AD, MDM, Verwaltung mobiler Geräte
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
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448557"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="c09be-104">Bereitstellungshandbuch – Unternehmensverknnnte HoloLens 2 mit Dynamics 365-Anleitungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="c09be-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="c09be-105">Dieses Handbuch hilft IT-Experten bei der Planung und Bereitstellung von Microsoft HoloLens 2-Geräten mit Dynamics 365 Guides (Guides) in ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="c09be-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="c09be-106">Dieses Handbuch ist ideal für Piloten und Produktionsbereitstellungen und ähnelt dem [Szenario B: Bereitstellen](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) innerhalb des Netzwerkhandbuchs Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="c09be-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="c09be-107">Nach dem Testen Ihres Proof-of-Concept verwenden Sie dieses Handbuch, um mit der Integration von HoloLens in Ihre Organisation voran zu gehen.</span><span class="sxs-lookup"><span data-stu-id="c09be-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="c09be-108">In diesem Handbuch wird beschrieben, wie Sie Ihre Geräte bei Ihrer vorhandenen Geräteverwaltung registrieren, Lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer in der Lage sind, einen Dynamics 365-Leitfaden zu betreiben, sowie benutzerdefinierte Unternehmens-Apps nach der Geräteeinrichtung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c09be-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c09be-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c09be-109">Prerequisites</span></span>

<span data-ttu-id="c09be-110">Die folgende Infrastruktur sollte bereits vorhanden sein:</span><span class="sxs-lookup"><span data-stu-id="c09be-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="c09be-111">WLAN</span><span class="sxs-lookup"><span data-stu-id="c09be-111">Wi-Fi</span></span>
    - <span data-ttu-id="c09be-112">Internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen und eingeschränktem Zugriff auf das Internet oder Clouddienste</span><span class="sxs-lookup"><span data-stu-id="c09be-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="c09be-113">Gerätebasierte Zertifikatauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c09be-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="c09be-114">Azure Active Directory (Azure AD)-Beitritt mit automatischer MDM-Registrierung ([Azure AD P1-Abonnement](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) erforderlich)</span><span class="sxs-lookup"><span data-stu-id="c09be-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="c09be-115">Verwaltetes MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="c09be-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="c09be-116">Mindestens eine Anwendung wird über MDM bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c09be-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="c09be-117">Network</span><span class="sxs-lookup"><span data-stu-id="c09be-117">Network</span></span> 
    - <span data-ttu-id="c09be-118">Zertifikate (SCEP oder PKCS)</span><span class="sxs-lookup"><span data-stu-id="c09be-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="c09be-119">Proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="c09be-119">Proxy configuration</span></span>
- <span data-ttu-id="c09be-120">Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="c09be-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="c09be-121">Einzelne oder mehrere Benutzer pro Gerät werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c09be-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="c09be-122">Unterschiedliche Stufen von Gerätesperrungskonfigurationen, die basierend auf bestimmten Anwendungsfällen angewendet werden, von Fully Open bis Single App Kiosk.</span><span class="sxs-lookup"><span data-stu-id="c09be-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## [<a name="guides-licensing-and-requirements"></a><span data-ttu-id="c09be-123">Anleitungen für Lizenzierung und Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c09be-123">Guides Licensing and Requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- <span data-ttu-id="c09be-124">Azure AD-Konto</span><span class="sxs-lookup"><span data-stu-id="c09be-124">Azure AD account</span></span>
- <span data-ttu-id="c09be-125">Dynamics 365 Führt Anwendungen PC und HoloLens</span><span class="sxs-lookup"><span data-stu-id="c09be-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="c09be-126">Dynamics 365 Guides-Abonnement</span><span class="sxs-lookup"><span data-stu-id="c09be-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="c09be-127">Microsoft Dataverse (enthalten)</span><span class="sxs-lookup"><span data-stu-id="c09be-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="c09be-128">Power Apps (im Lieferumfang enthalten)</span><span class="sxs-lookup"><span data-stu-id="c09be-128">Power Apps (included)</span></span>
- <span data-ttu-id="c09be-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="c09be-129">Power BI Desktop</span></span>
- <span data-ttu-id="c09be-130">Netzwerkkonnektivität</span><span class="sxs-lookup"><span data-stu-id="c09be-130">Network Connectivity</span></span>

![Verbundenes Netzwerkdiagramm der Corp](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a><span data-ttu-id="c09be-132">Phasen der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="c09be-132">Stages of Deployment</span></span>
### <a name="prepare"></a><span data-ttu-id="c09be-133">Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="c09be-133">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="c09be-134">Erfahren Sie mehr über die grundlegenden Infrastruktur für HoloLens 2-Geräte.</span><span class="sxs-lookup"><span data-stu-id="c09be-134">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="c09be-135">Erfahren Sie mehr über Azure AD, und richten Sie eins ein, wenn Sie es nicht haben.</span><span class="sxs-lookup"><span data-stu-id="c09be-135">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="c09be-136">Erfahren Sie mehr über die Identitätsverwaltung und die optimale Einrichtung von Azure AD-Konten.</span><span class="sxs-lookup"><span data-stu-id="c09be-136">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="c09be-137">Erfahren Sie mehr über MDM und richten Sie intune ein, wenn Sie noch nicht bereit sind.</span><span class="sxs-lookup"><span data-stu-id="c09be-137">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="c09be-138">Machen Sie sich mit zertifikatbasiertem WLAN vertraut.</span><span class="sxs-lookup"><span data-stu-id="c09be-138">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="c09be-139">Machen Sie sich mit Proxy vertraut.</span><span class="sxs-lookup"><span data-stu-id="c09be-139">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="c09be-140">Erfahren Sie, wie Sie Line of Business Apps verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c09be-140">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="c09be-141">Erfahren Sie mehr über die Verwendung von Handbüchern für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="c09be-141">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="c09be-142">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="c09be-142">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="c09be-143">Erstellen von Benutzern und Gruppen.</span><span class="sxs-lookup"><span data-stu-id="c09be-143">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="c09be-144">Einrichten der automatischen Registrierung.</span><span class="sxs-lookup"><span data-stu-id="c09be-144">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="c09be-145">Einrichten von Zertifikaten Wi-Fi Profilen für unternehmensWi-Fi Konnektivität.</span><span class="sxs-lookup"><span data-stu-id="c09be-145">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="c09be-146">Hochladen und Zuweisen von Branchen-App-Paketen.</span><span class="sxs-lookup"><span data-stu-id="c09be-146">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="c09be-147">Setup Dynamics 365 Guides.</span><span class="sxs-lookup"><span data-stu-id="c09be-147">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="c09be-148">Konfigurieren des Kioskmodus (optional).</span><span class="sxs-lookup"><span data-stu-id="c09be-148">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="c09be-149">Konfigurieren von WDAC (optional).</span><span class="sxs-lookup"><span data-stu-id="c09be-149">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="c09be-150">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="c09be-150">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="c09be-151">Überprüfen der Registrierung über Gerät und MDM.</span><span class="sxs-lookup"><span data-stu-id="c09be-151">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="c09be-152">Überprüfen Wi-Fi Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="c09be-152">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="c09be-153">Überprüfen der Branchen-App-Installation.</span><span class="sxs-lookup"><span data-stu-id="c09be-153">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="c09be-154">Überprüfen von Handbüchern über Die Erstellung und den Betrieb.</span><span class="sxs-lookup"><span data-stu-id="c09be-154">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="c09be-155">Warten</span><span class="sxs-lookup"><span data-stu-id="c09be-155">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="c09be-156">Aktualisieren Sie HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c09be-156">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="c09be-157">Aktualisieren von Handbüchern (Store-Apps).</span><span class="sxs-lookup"><span data-stu-id="c09be-157">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="c09be-158">Aktualisieren von Branchen-Apps.</span><span class="sxs-lookup"><span data-stu-id="c09be-158">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="c09be-159">Entwicklungsplan.</span><span class="sxs-lookup"><span data-stu-id="c09be-159">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="c09be-160">Erstellen eines Supportplans</span><span class="sxs-lookup"><span data-stu-id="c09be-160">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="c09be-161">Geräteverwaltungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="c09be-161">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="c09be-162">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="c09be-162">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="c09be-163">Unternehmensverkn nnte Bereitstellung – Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="c09be-163">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
