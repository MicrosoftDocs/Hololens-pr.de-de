---
title: Bereitstellungshandbuch – Mit der Cloud verbundene HoloLens 2 mit Remote Assist – Übersicht
description: Registrieren von HoloLens-Geräten über ein mit der Cloud verbundenes Netzwerk
keywords: HoloLens, Verwaltung, mit der Cloud verbunden, Remote Assist, AAD, Azure AD, MDM, Verwaltung mobiler Geräte
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
ms.openlocfilehash: fe83333c99f8dbf23b211c9b5155db256dcd20b3
ms.sourcegitcommit: 50e4d61a31b94d5007776064b4012e26cf9ecbbb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271673"
---
# <span data-ttu-id="e9429-104">Bereitstellungshandbuch – Mit der Cloud verbundene HoloLens 2 mit Remote Assist – Übersicht</span><span class="sxs-lookup"><span data-stu-id="e9429-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="e9429-105">Dieses Handbuch hilft IT-Experten bei der Planung und Bereitstellung von Microsoft HoloLens 2-Geräten in ihrer Organisation mit dem allgemeinen Ziel, dass diese Geräte cloudgebunden mit Ihrer Organisation mit Dynamics 365 Remote Assist betriebsbereit sind.</span><span class="sxs-lookup"><span data-stu-id="e9429-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="e9429-106">Beachten Sie, dass dies als Modell für die Bereitstellung von Proof-of-Concept-Bereitstellungen für Ihre Organisation in einer Vielzahl von HoloLens 2-Verwendungsfällen dient.</span><span class="sxs-lookup"><span data-stu-id="e9429-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="e9429-107">In diesem Leitfaden wird beschrieben, wie Sie Ihre Geräte bei der Geräteverwaltung registrieren, Lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer remote Assist sofort beim Einrichten des Geräts verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e9429-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="e9429-108">Dazu werden wir die wichtigen Infrastrukturteile durchgehen, die für die Einrichtung und Ausführung erforderlich sind – die Bereitstellung mit HoloLens 2 wird im großen Maßstab erreicht.</span><span class="sxs-lookup"><span data-stu-id="e9429-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

## <span data-ttu-id="e9429-109">In diesem Leitfaden</span><span class="sxs-lookup"><span data-stu-id="e9429-109">In this Guide</span></span>

<span data-ttu-id="e9429-110">Dieses Handbuch hat das spezifische Ziel, Remote Assist in Ihrer Organisation auf Ihren HoloLens-Geräten einrichten.</span><span class="sxs-lookup"><span data-stu-id="e9429-110">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="e9429-111">Wir werden die Notwendigkeiten zur Erreichung dieses Ziels abdecken.</span><span class="sxs-lookup"><span data-stu-id="e9429-111">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="e9429-112">Um den Fokus auf diesem Ziel zu behalten, werden bestimmte Vorbereitungen und Konfigurationen vorab ausgewählt, um die Bereitstellung zu optimieren oder die zu konfigurierenden Elemente zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="e9429-112">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="e9429-113">Sie werden über diese Auswahlmöglichkeiten informiert und können Ihre Bereitstellung an Ihre Geschäftlichen Anforderungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="e9429-113">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="e9429-114">Diese Einrichtung ähnelt Szenario [A: Bereitstellen](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)auf Cloud Connect-Geräten. Dies ist eine gute Option für viele Proof of Concept-Bereitstellungen, die Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="e9429-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="e9429-115">Wi-Fi sind in der Regel vollständig für internet- und cloudbasierte Dienste geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e9429-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="e9429-116">Azure AD Join mit automatischer MDM-Registrierung – MDM (Intune) Managed</span><span class="sxs-lookup"><span data-stu-id="e9429-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="e9429-117">Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="e9429-117">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="e9429-118">Einzelne oder mehrere Benutzer pro Gerät unterstützt</span><span class="sxs-lookup"><span data-stu-id="e9429-118">Single or multiple users per device supported</span></span>
- <span data-ttu-id="e9429-119">Unterschiedliche Stufen von Gerätesperrmoduskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von "Vollständig geöffnet" bis "Single App Kiosk".</span><span class="sxs-lookup"><span data-stu-id="e9429-119">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![Mit der Cloud verbundenes Szenario](./images/cloud-connected-guide-diagram.png)

<span data-ttu-id="e9429-121">In diesem Leitfaden werden keine weiteren Geräteeinschränkungen oder -konfigurationen angewendet, wir empfehlen Ihnen jedoch, diese Optionen nach abschluss zu erkunden.</span><span class="sxs-lookup"><span data-stu-id="e9429-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <span data-ttu-id="e9429-122">Erfahren Sie mehr über Remote Assist</span><span class="sxs-lookup"><span data-stu-id="e9429-122">Learn about Remote Assist</span></span>

<span data-ttu-id="e9429-123">Remote Assist ermöglicht gemeinsame Wartung und Reparatur, Remoteinspektion sowie Wissensfreigabe und Schulung.</span><span class="sxs-lookup"><span data-stu-id="e9429-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="e9429-124">Durch das Verbinden von Personen an verschiedenen Rollen und Standorten kann ein Techniker mit Remote Assist eine Verbindung mit einem Remotemitarbeiter in Microsoft Teams herstellen.</span><span class="sxs-lookup"><span data-stu-id="e9429-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="e9429-125">Sie können Videos, Screenshots und Anmerkungen kombinieren, um Probleme in Echtzeit zu lösen, auch wenn&#39;sich nicht am selben Speicherort befinden.</span><span class="sxs-lookup"><span data-stu-id="e9429-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="e9429-126">Remotemitarbeiter können Referenzbilder, Schemata und andere hilfreiche Informationen einfügen, die der Techniker&#39;den physischen Raum eingibt, damit sie auf das Schema beim Arbeiten mit Kopf und Freisprechen auf HoloLens verweisen können.</span><span class="sxs-lookup"><span data-stu-id="e9429-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <span data-ttu-id="e9429-127">In diesem Leitfaden werden Sie:</span><span class="sxs-lookup"><span data-stu-id="e9429-127">In this guide you will:</span></span>

<span data-ttu-id="e9429-128">Bereiten Sie dies vor:</span><span class="sxs-lookup"><span data-stu-id="e9429-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="e9429-129">Erfahren Sie mehr über die grundlegenden Infrastruktur für HoloLens 2-Geräte.</span><span class="sxs-lookup"><span data-stu-id="e9429-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="e9429-130">Erfahren Sie mehr über Azure AD, und richten Sie eins ein,&#39;nicht verfügen.</span><span class="sxs-lookup"><span data-stu-id="e9429-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="e9429-131">Erfahren Sie mehr über die Identitätsverwaltung und die beste Einrichtung von Azure AD-Konten.</span><span class="sxs-lookup"><span data-stu-id="e9429-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="e9429-132">Erfahren Sie mehr über MDM, und richten Sie Intune ein,&#39;sie noch nicht bereit sind.</span><span class="sxs-lookup"><span data-stu-id="e9429-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="e9429-133">Erfahren Sie mehr über die Netzwerkanforderungen von Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="e9429-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="e9429-134">Optional: VPN zum Herstellen einer Verbindung mit Organisationsressourcen</span><span class="sxs-lookup"><span data-stu-id="e9429-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="e9429-135">Konfigurieren Sie:</span><span class="sxs-lookup"><span data-stu-id="e9429-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="e9429-136">Erstellen von Benutzern und Gruppen.</span><span class="sxs-lookup"><span data-stu-id="e9429-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="e9429-137">Einrichten der automatischen Registrierung in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e9429-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="e9429-138">Zuweisen von Anwendungslizenzen.</span><span class="sxs-lookup"><span data-stu-id="e9429-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="e9429-139">Bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="e9429-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="e9429-140">Richten Sie HoloLens 2 ein, und überprüfen Sie die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="e9429-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="e9429-141">Überprüfen Sie, ob Sie einen Remote assist-Anruf machen können.</span><span class="sxs-lookup"><span data-stu-id="e9429-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="e9429-142">Warten Sie:</span><span class="sxs-lookup"><span data-stu-id="e9429-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="e9429-143">So aktualisieren Sie Remote Assist mithilfe der Microsoft Store-App.</span><span class="sxs-lookup"><span data-stu-id="e9429-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="e9429-144">Erstellen eines Supportplans.</span><span class="sxs-lookup"><span data-stu-id="e9429-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="e9429-145">Entwicklungsplan.</span><span class="sxs-lookup"><span data-stu-id="e9429-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <span data-ttu-id="e9429-146">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="e9429-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e9429-147">Mit der Cloud verbundene Bereitstellung – Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="e9429-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

