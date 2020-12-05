---
title: Bereitstellungshandbuch – Cloud Connected HoloLens 2 mit Remote Assist – Übersicht
description: Registrieren von HoloLens-Geräten über ein in der Cloud verbundenes Netzwerk
keywords: HoloLens, Verwaltung, Cloud Connected, Remote Assist, AAD, Azure AD, MDM, Verwaltung mobiler Geräte
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
ms.openlocfilehash: ba3f826360f999a72e671166af7a19d19ce9c567
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196314"
---
# <span data-ttu-id="7cba9-104">Bereitstellungshandbuch – Cloud Connected HoloLens 2 mit Remote Assist – Übersicht</span><span class="sxs-lookup"><span data-stu-id="7cba9-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="7cba9-105">Dieser Leitfaden unterstützt IT-Experten beim Planen und Bereitstellen von Microsoft HoloLens 2-Geräten für Ihre Organisation mit dem Gesamtziel, dass diese Geräte mit Ihrer Organisation in Verbindung mit der Dynamics 365-Remote Unterstützung einsatzbereit sind.</span><span class="sxs-lookup"><span data-stu-id="7cba9-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="7cba9-106">Beachten Sie, dass dies als Modell für Machbarkeits orientierte Bereitstellungen für Ihre Organisation in einer Vielzahl von HoloLens 2-Anwendungsfällen dienen kann.</span><span class="sxs-lookup"><span data-stu-id="7cba9-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="7cba9-107">Während des Leitfadens wird erläutert, wie Sie Ihre Geräte in der Geräteverwaltung registrieren, Lizenzen nach Bedarf anwenden und überprüfen können, ob Ihre Endbenutzer die Remote Unterstützung sofort nach der Einrichtung des Geräts verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7cba9-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device set up.</span></span> <span data-ttu-id="7cba9-108">Zu diesem Zweck gehen wir auf die wichtigen Infrastrukturkomponenten ein, die für die Einrichtung und Ausführung erforderlich sind, um die Bereitstellung im Maßstab mit HoloLens 2 zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="7cba9-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

## <span data-ttu-id="7cba9-109">In diesem Leitfaden</span><span class="sxs-lookup"><span data-stu-id="7cba9-109">In this Guide</span></span>

<span data-ttu-id="7cba9-110">Dieser Leitfaden hat das spezifische Ziel, den Remote-Support in Ihrer Organisation auf Ihren HoloLens-Geräten einzurichten.</span><span class="sxs-lookup"><span data-stu-id="7cba9-110">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="7cba9-111">Wir werden die Notwendigkeiten decken, die erforderlich sind, um dieses Ziel zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="7cba9-111">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="7cba9-112">Um die Fokussierung auf dieses Ziel zu gewährleisten, sind bestimmte Vorbereitungen und Konfigurationen vorselektiert, um diese Bereitstellung zu optimieren oder die für die Konfiguration erforderlichen Elemente zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="7cba9-112">In order to maintain focus on this goal certain preparations and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="7cba9-113">Sie werden über diese Auswahlmöglichkeiten informiert und können Ihre Bereitstellung auf der Grundlage ihrer geschäftlichen Anforderungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="7cba9-113">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="7cba9-114">Hierbei handelt es sich um eine Einrichtung, die mit [Szenario a vergleichbar ist: Bereitstellen auf Cloud Connect-Geräten](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), was eine gute Option für viele Konzepte zur Machbarkeitsstudie ist, die Folgendes beinhalten:</span><span class="sxs-lookup"><span data-stu-id="7cba9-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments which will include:</span></span>

- <span data-ttu-id="7cba9-115">Wi-Fi Netzwerke sind in der Regel vollständig für das Internet und die Cloud-Dienste geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7cba9-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="7cba9-116">Azure AD Join with MDM Auto Enrollment--MDM (InTune) verwaltet</span><span class="sxs-lookup"><span data-stu-id="7cba9-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="7cba9-117">Benutzer anmelden mit einem eigenen Unternehmenskonto (AAD)</span><span class="sxs-lookup"><span data-stu-id="7cba9-117">Users sign in with their own corporate account (AAD)</span></span>
  - <span data-ttu-id="7cba9-118">Einzelne oder mehrere Benutzer pro Gerät unterstützt</span><span class="sxs-lookup"><span data-stu-id="7cba9-118">Single or multiple users per device supported</span></span>
- <span data-ttu-id="7cba9-119">Unterschiedliche Ebenen der Geräte Sperrungs Konfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, vom vollständigen öffnen zum einzelnen App-Kiosk</span><span class="sxs-lookup"><span data-stu-id="7cba9-119">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![Szenario mit Cloud-Verbindung](./images/cloud-connected-deployment-chart.png)

<span data-ttu-id="7cba9-121">In diesem Leitfaden werden keine zusätzlichen Geräteeinschränkungen oder-Konfigurationen angewendet, wir empfehlen Ihnen jedoch, diese Optionen nach Abschluss zu erkunden.</span><span class="sxs-lookup"><span data-stu-id="7cba9-121">No additional device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <span data-ttu-id="7cba9-122">Informationen zu Remote Unterstützung</span><span class="sxs-lookup"><span data-stu-id="7cba9-122">Learn about Remote Assist</span></span>

<span data-ttu-id="7cba9-123">Der Remote-Assistent ermöglicht die gemeinsame Wartung und Reparatur, die Remote Inspektion sowie den Austausch von Wissen und Schulungen.</span><span class="sxs-lookup"><span data-stu-id="7cba9-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="7cba9-124">Durch die Verbindung von Personen mit unterschiedlichen Rollen und Speicherorten kann ein Techniker mit Remoteunterstützung eine Verbindung mit einem Remotemitarbeiter in Microsoft Teams herstellen.</span><span class="sxs-lookup"><span data-stu-id="7cba9-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="7cba9-125">Sie können Video, Screenshots und Anmerkungen kombinieren, um Probleme in Echtzeit zu lösen, auch wenn Sie nicht am selben Ort&#39;t sind.</span><span class="sxs-lookup"><span data-stu-id="7cba9-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="7cba9-126">Remote-Mitarbeiter können Referenzbilder, schematische und andere hilfreiche Informationen einfügen, um den physikalischen Platz des Technikers&#39;, damit Sie sich auf die Schaltplan Funktion beziehen können, während Sie Heads-up und freihändig auf HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7cba9-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <span data-ttu-id="7cba9-127">In diesem Leitfaden finden Sie folgende Informationen:</span><span class="sxs-lookup"><span data-stu-id="7cba9-127">In this guide you will:</span></span>

<span data-ttu-id="7cba9-128">Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="7cba9-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="7cba9-129">Erfahren Sie mehr über die Infrastruktur-Grundlagen für HoloLens 2-Geräte.</span><span class="sxs-lookup"><span data-stu-id="7cba9-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="7cba9-130">Erfahren Sie mehr über Aad und richten Sie eine ein, wenn Sie&#39;t haben.</span><span class="sxs-lookup"><span data-stu-id="7cba9-130">Learn more about AAD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="7cba9-131">Informieren Sie sich über die Identitätsverwaltung und die optimale Einrichtung von Aad-Konten.</span><span class="sxs-lookup"><span data-stu-id="7cba9-131">Learn about Identity management and how to best set up AAD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="7cba9-132">Weitere Informationen zu MDM und zum Einrichten von InTune, wenn Sie&#39;t bereits eine bereit haben.</span><span class="sxs-lookup"><span data-stu-id="7cba9-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="7cba9-133">Informieren Sie sich über die Netzwerkanforderungen der Remote Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="7cba9-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="7cba9-134">Optional: VPN zum Herstellen einer Verbindung mit organisatorischen Ressourcen</span><span class="sxs-lookup"><span data-stu-id="7cba9-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="7cba9-135">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="7cba9-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="7cba9-136">Erstellen von Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="7cba9-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="7cba9-137">Einrichten der automatischen Registrierung in Aad</span><span class="sxs-lookup"><span data-stu-id="7cba9-137">How to set up Auto-enrollment within AAD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="7cba9-138">So weisen Sie Ihre Anwendungslizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="7cba9-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="7cba9-139">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="7cba9-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="7cba9-140">Richten Sie Ihre HoloLens 2 ein, und überprüfen Sie die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="7cba9-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="7cba9-141">Überprüfen Sie können einen Remote Unterstützungs Anruf führen.</span><span class="sxs-lookup"><span data-stu-id="7cba9-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="7cba9-142">Pflegen</span><span class="sxs-lookup"><span data-stu-id="7cba9-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="7cba9-143">Aktualisieren von Remote Unterstützung mithilfe der Microsoft Store-App</span><span class="sxs-lookup"><span data-stu-id="7cba9-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="7cba9-144">Erstellen eines Support Plans</span><span class="sxs-lookup"><span data-stu-id="7cba9-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="7cba9-145">Entwicklungsplan.</span><span class="sxs-lookup"><span data-stu-id="7cba9-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <span data-ttu-id="7cba9-146">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="7cba9-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7cba9-147">Cloud Connected-Bereitstellung – vorbereiten</span><span class="sxs-lookup"><span data-stu-id="7cba9-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

