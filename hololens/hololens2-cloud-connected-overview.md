---
title: Übersicht über cloudgebundene HoloLens 2 mit Remote Assist
description: Erfahren Sie, wie Sie HoloLens 2 Geräte über ein mit der Cloud verbundenes Netzwerk mithilfe von Dynamics 365 Remote Assist registrieren.
keywords: HoloLens, Verwaltung, cloudverbunden, Remote Assist, AAD, Azure AD, MDM, Mobile Geräteverwaltung
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
ms.openlocfilehash: 69b31657a7efaebd5b25b742023dc8767f9c5038
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308564"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="5edd7-104">Bereitstellungshandbuch – Cloud-verbundene HoloLens 2 mit Remote Assist – Übersicht</span><span class="sxs-lookup"><span data-stu-id="5edd7-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="5edd7-105">Dieser Leitfaden unterstützt IT-Experten bei der Planung und Bereitstellung von Microsoft HoloLens 2-Geräten in ihrer Organisation mit dem allgemeinen Ziel, dass diese Geräte in der Cloud mit Ihrer Organisation verbunden sind und Dynamics 365 Remote Assist einsatzbereit sind.</span><span class="sxs-lookup"><span data-stu-id="5edd7-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="5edd7-106">Beachten Sie, dass dies als Modell für Proof of Concept-Bereitstellungen in Ihrer Organisation in einer Vielzahl von HoloLens 2 Anwendungsfällen dient.</span><span class="sxs-lookup"><span data-stu-id="5edd7-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="5edd7-107">In diesem Leitfaden wird erläutert, wie Sie Ihre Geräte bei der Geräteverwaltung registrieren, Lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer Remote Assist sofort bei der Geräteeinrichtung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5edd7-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="5edd7-108">Zu diesem Zeitpunkt werden die wichtigen Teile der Infrastruktur behandelt, die für die Einrichtung und Ausführung erforderlich sind, um eine bedarfsorientierte Bereitstellung mit HoloLens 2 zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="5edd7-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

![Banner mit Cloudverbindung](./images/cloud-connected-hololens-large.png)

## <a name="in-this-guide"></a><span data-ttu-id="5edd7-110">In diesem Handbuch</span><span class="sxs-lookup"><span data-stu-id="5edd7-110">In this Guide</span></span>

<span data-ttu-id="5edd7-111">Dieser Leitfaden hat das spezifische Ziel, Remote Assist in Ihrer Organisation auf Ihren HoloLens-Geräten einzurichten.</span><span class="sxs-lookup"><span data-stu-id="5edd7-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="5edd7-112">Wir werden die Notwendigkeiten abdecken, die erforderlich sind, um dieses Ziel zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="5edd7-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="5edd7-113">Um den Fokus auf dieses Ziel zu behalten, werden bestimmte Vorbereitungen und Konfigurationen vorab ausgewählt, um für diese Bereitstellung zu optimieren oder die für die Konfiguration erforderlichen Elemente zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="5edd7-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="5edd7-114">Sie werden über diese Optionen informiert und können Ihre Bereitstellung an Ihre geschäftlichen Anforderungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="5edd7-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="5edd7-115">Dies ist eine Einrichtung, die dem [Szenario A: Bereitstellen auf Cloudverbindungsgeräten](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)ähnelt. Dies ist eine gute Option für viele Proof of Concept-Bereitstellungen, die Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="5edd7-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="5edd7-116">Wi-Fi Netzwerke sind in der Regel vollständig für internet- und cloudbasierte Dienste geöffnet.</span><span class="sxs-lookup"><span data-stu-id="5edd7-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="5edd7-117">Azure AD Beitreten zur automatischen MDM-Registrierung – MDM (Intune) verwaltet</span><span class="sxs-lookup"><span data-stu-id="5edd7-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="5edd7-118">Benutzer melden sich mit ihrem eigenen Unternehmenskonto (Azure AD) an.</span><span class="sxs-lookup"><span data-stu-id="5edd7-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="5edd7-119">Einzelne oder mehrere Benutzer pro Gerät unterstützt</span><span class="sxs-lookup"><span data-stu-id="5edd7-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="5edd7-120">Verschiedene Ebenen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von "Vollständig geöffnet" bis "Kiosk für einzelne Apps".</span><span class="sxs-lookup"><span data-stu-id="5edd7-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![Cloud verbundenes Szenario](./images/cloud-connected-guide-diagram.png)

<span data-ttu-id="5edd7-122">In diesem Leitfaden werden keine anderen Geräteeinschränkungen oder Konfigurationen angewendet. Wir empfehlen Ihnen jedoch, diese Optionen nach Abschluss des Handbuchs zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="5edd7-122">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <a name="learn-about-remote-assist"></a><span data-ttu-id="5edd7-123">Weitere Informationen Remote Assist</span><span class="sxs-lookup"><span data-stu-id="5edd7-123">Learn about Remote Assist</span></span>

<span data-ttu-id="5edd7-124">Remote Assist ermöglicht gemeinsame Wartung und Reparatur, Remoteüberprüfung sowie Wissensfreigabe und Schulungen.</span><span class="sxs-lookup"><span data-stu-id="5edd7-124">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="5edd7-125">Durch Verbinden von Personen in verschiedenen Rollen und Standorten kann ein Techniker Remote Assist mit einem Remotemitarbeiter in Microsoft Teams eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="5edd7-125">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="5edd7-126">Sie können Videos, Screenshots und Anmerkungen kombinieren, um Probleme auch dann in Echtzeit zu lösen, wenn&#39;sich nicht am gleichen Ort befinden.</span><span class="sxs-lookup"><span data-stu-id="5edd7-126">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="5edd7-127">Remotemitarbeiter können Referenzbilder, Schemata und andere hilfreiche Informationen einfügen, die der Techniker&#39;physischem Raum enthält, damit sie auf das Schema verweisen können, während sie auf HoloLens kopf- und händefrei arbeiten.</span><span class="sxs-lookup"><span data-stu-id="5edd7-127">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="5edd7-128">In dieser Anleitung lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5edd7-128">In this guide you will:</span></span>

<span data-ttu-id="5edd7-129">Vorbereiten:</span><span class="sxs-lookup"><span data-stu-id="5edd7-129">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="5edd7-130">Erfahren Sie mehr über die Infrastruktur essentials für HoloLens 2 Geräte.</span><span class="sxs-lookup"><span data-stu-id="5edd7-130">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="5edd7-131">Erfahren Sie mehr über Azure AD und richten Sie eine ein, wenn Sie&#39;nicht haben.</span><span class="sxs-lookup"><span data-stu-id="5edd7-131">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="5edd7-132">Erfahren Sie mehr über die Identitätsverwaltung und die optimale Einrichtung Azure AD Konten.</span><span class="sxs-lookup"><span data-stu-id="5edd7-132">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="5edd7-133">Erfahren Sie mehr über MDM, und richten Sie Intune ein,&#39;sie noch nicht bereit sind.</span><span class="sxs-lookup"><span data-stu-id="5edd7-133">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="5edd7-134">Erfahren Sie mehr über die Netzwerkanforderungen Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="5edd7-134">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="5edd7-135">Optional: VPN zum Herstellen einer Verbindung mit Organisationsressourcen</span><span class="sxs-lookup"><span data-stu-id="5edd7-135">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="5edd7-136">Konfiguration von:</span><span class="sxs-lookup"><span data-stu-id="5edd7-136">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="5edd7-137">Erstellen von Benutzern und Gruppen.</span><span class="sxs-lookup"><span data-stu-id="5edd7-137">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="5edd7-138">Einrichten der automatischen Registrierung in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5edd7-138">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="5edd7-139">Zuweisen von Anwendungslizenzen</span><span class="sxs-lookup"><span data-stu-id="5edd7-139">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="5edd7-140">Bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="5edd7-140">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="5edd7-141">Richten Sie Ihre HoloLens 2 ein, und überprüfen Sie die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="5edd7-141">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="5edd7-142">Überprüfen Sie, ob Sie einen Remote Assist können.</span><span class="sxs-lookup"><span data-stu-id="5edd7-142">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="5edd7-143">Warten:</span><span class="sxs-lookup"><span data-stu-id="5edd7-143">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="5edd7-144">Aktualisieren von Remote Assist mithilfe der Microsoft Store-App.</span><span class="sxs-lookup"><span data-stu-id="5edd7-144">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="5edd7-145">Erstellen eines Supportplans.</span><span class="sxs-lookup"><span data-stu-id="5edd7-145">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="5edd7-146">Entwicklungsplan:</span><span class="sxs-lookup"><span data-stu-id="5edd7-146">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="5edd7-147">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="5edd7-147">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5edd7-148">Bereitstellung mit Cloudverbindung – Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="5edd7-148">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

