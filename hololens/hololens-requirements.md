---
title: Einrichten von HoloLens in einer geschäftlichen Umgebung
description: Weitere Informationen finden Sie unter Bereitstellen und Verwalten von HoloLens in Enterprise-Umgebungen.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.openlocfilehash: 8aa8e0f679ad18a2e47f34c5f1233435a502dc0c
ms.sourcegitcommit: f3cda6c6b3bfb7ba4be5f4da66d8ed5b03ca807d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830129"
---
# <span data-ttu-id="10b3b-103">Bereitstellen von HoloLens in einer kommerziellen Umgebung</span><span class="sxs-lookup"><span data-stu-id="10b3b-103">Deploy HoloLens in a commercial environment</span></span>

<span data-ttu-id="10b3b-104">Sie können HoloLens im Maßstab in einer kommerziellen Einstellung bereitstellen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="10b3b-104">You can deploy and configure HoloLens at scale in a commercial setting.</span></span> <span data-ttu-id="10b3b-105">Dieser Artikel enthält Anweisungen zum Bereitstellen von HoloLens-Geräten in einer geschäftlichen Umgebung.</span><span class="sxs-lookup"><span data-stu-id="10b3b-105">This article provides instructions for deploying HoloLens devices in a commercial environment.</span></span> <span data-ttu-id="10b3b-106">Dieser Leitfaden geht von grundlegender Vertrautheit mit HoloLens aus.</span><span class="sxs-lookup"><span data-stu-id="10b3b-106">This guide assumes basic familiarity with HoloLens.</span></span> <span data-ttu-id="10b3b-107">Folgen Sie dem Leitfaden "erste [Schritte](hololens1-setup.md) ", um HoloLens zum ersten Mal einzurichten.</span><span class="sxs-lookup"><span data-stu-id="10b3b-107">Follow the [get started guide](hololens1-setup.md) to set up HoloLens for the first time.</span></span>

<span data-ttu-id="10b3b-108">In diesem Dokument wird auch davon ausgegangen, dass das HoloLens von Sicherheitsteams als sicher für die Verwendung im Unternehmensnetzwerk ausgewertet wurde.</span><span class="sxs-lookup"><span data-stu-id="10b3b-108">This document also assumes that the HoloLens has been evaluated by security teams as safe to use on the corporate network.</span></span> <span data-ttu-id="10b3b-109">Häufig gestellte Fragen zur Sicherheit finden Sie [hier](hololens-faq-security.md) .</span><span class="sxs-lookup"><span data-stu-id="10b3b-109">Frequently asked security questions can be found [here](hololens-faq-security.md)</span></span>

## <span data-ttu-id="10b3b-110">Übersicht über Bereitstellungsschritte</span><span class="sxs-lookup"><span data-stu-id="10b3b-110">Overview of Deployment Steps</span></span>

1. [<span data-ttu-id="10b3b-111">Ermitteln der benötigten Features</span><span class="sxs-lookup"><span data-stu-id="10b3b-111">Determine what features you need</span></span>](hololens-requirements.md#step-1-determine-what-you-need)
1. [<span data-ttu-id="10b3b-112">Ermitteln, welche Lizenzen erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="10b3b-112">Determine what licenses you need</span></span>](hololens-licenses-requirements.md)
1. <span data-ttu-id="10b3b-113">[Konfigurieren Sie Ihr Netzwerk für HoloLens](hololens-commercial-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="10b3b-113">[Configure your network for HoloLens](hololens-commercial-infrastructure.md).</span></span>
    1. <span data-ttu-id="10b3b-114">Dieser Abschnitt enthält Bandbreitenanforderungen, URL und Ports, die für Ihre Firewall zugelassen werden müssen. Azure AD-Anleitung; Anleitung zur Verwaltung mobiler Geräte (MDM); Anleitung zur Bereitstellung und Verwaltung von apps und Zertifikat Leit Faden.</span><span class="sxs-lookup"><span data-stu-id="10b3b-114">This section includes bandwidth requirements, URL, and ports that need to be allowed on your firewall; Azure AD guidance; Mobile Device Management (MDM) Guidance; app deployment/management guidance; and certificate guidance.</span></span>
1. <span data-ttu-id="10b3b-115">Optional [Konfigurieren von HoloLens mit einem Bereitstellungspaket](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="10b3b-115">(Optional) [Configure HoloLens using a provisioning package](hololens-provisioning.md)</span></span>
1. [<span data-ttu-id="10b3b-116">Gerät registrieren</span><span class="sxs-lookup"><span data-stu-id="10b3b-116">Enroll Device</span></span>](hololens-enroll-mdm.md)
1. [<span data-ttu-id="10b3b-117">Einrichten von ringbasierten Updates für HoloLens</span><span class="sxs-lookup"><span data-stu-id="10b3b-117">Set up ring based updates for HoloLens</span></span>](hololens-updates.md)
1. [<span data-ttu-id="10b3b-118">Aktivieren der Bitlocker-Geräteverschlüsselung für HoloLens</span><span class="sxs-lookup"><span data-stu-id="10b3b-118">Enable Bitlocker device encryption for HoloLens</span></span>](hololens-encryption.md)

## <span data-ttu-id="10b3b-119">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="10b3b-119">Step 1.</span></span> <span data-ttu-id="10b3b-120">Bestimmen, was Sie benötigen</span><span class="sxs-lookup"><span data-stu-id="10b3b-120">Determine what you need</span></span>

<span data-ttu-id="10b3b-121">Bevor Sie das HoloLens in Ihrer Umgebung bereitstellen, müssen Sie zunächst ermitteln, welche Features, Apps und Typen von Identitäten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="10b3b-121">Before deploying the HoloLens in your environment, it is important to first determine what features, apps, and type of identities are needed.</span></span> <span data-ttu-id="10b3b-122">Darüber hinaus ist es wichtig, sicherzustellen, dass Ihr Sicherheitsteam die Nutzung des HoloLens im Netzwerk des Unternehmens genehmigt hat.</span><span class="sxs-lookup"><span data-stu-id="10b3b-122">It is also important to ensure that your security team has approved of the use of the HoloLens on the company's network.</span></span> <span data-ttu-id="10b3b-123">Weitere Sicherheitsinformationen finden Sie unter Häufig gestellte Fragen zu [Sicherheitsfragen](hololens-faq-security.md) .</span><span class="sxs-lookup"><span data-stu-id="10b3b-123">Please see [Frequently ask security questions](hololens-faq-security.md) for additional security information.</span></span>

### <span data-ttu-id="10b3b-124">Art der Identität</span><span class="sxs-lookup"><span data-stu-id="10b3b-124">Type of Identity</span></span>

<span data-ttu-id="10b3b-125">Ermitteln Sie den Typ der Identität, die zum Anmelden beim Gerät verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="10b3b-125">Determine the type of identity that will be used to sign into the device.</span></span>

1. <span data-ttu-id="10b3b-126">**Lokale Konten:** Dieses Konto ist auf dem Gerät lokal (wie ein lokales Administratorkonto auf einem Windows-PC).</span><span class="sxs-lookup"><span data-stu-id="10b3b-126">**Local Accounts:** This account is local to the device (like a local admin account on a windows PC).</span></span> <span data-ttu-id="10b3b-127">Dadurch können sich nur 1 Benutzer beim Gerät anmelden.</span><span class="sxs-lookup"><span data-stu-id="10b3b-127">This will allow only 1 user to log into the device.</span></span>
2. <span data-ttu-id="10b3b-128">**MSA:** Hierbei handelt es sich um ein privates Konto (wie Outlook, Hotmail, Gmail, Yahoo usw.). Dadurch können sich nur 1 Benutzer beim Gerät anmelden.</span><span class="sxs-lookup"><span data-stu-id="10b3b-128">**MSA:** This is a personal account (like outlook, hotmail, gmail, yahoo, etc.) This will allow only 1 user to log into the device.</span></span>
3. <span data-ttu-id="10b3b-129">**Azure Active Directory-Konten (Azure AD):** Hierbei handelt es sich um ein in Azure AD erstelltes Konto.</span><span class="sxs-lookup"><span data-stu-id="10b3b-129">**Azure Active Directory (Azure AD) accounts:** This is an account created in Azure AD.</span></span> <span data-ttu-id="10b3b-130">Dies gewährt ihrem Unternehmen die Möglichkeit, das HoloLens-Gerät zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="10b3b-130">This grants your corporation the ability to manage the HoloLens device.</span></span> <span data-ttu-id="10b3b-131">Auf diese Weise können sich mehrere Benutzer bei der HoloLens 1st Gen Commercial Suite/dem HoloLens 2-Gerät anmelden.</span><span class="sxs-lookup"><span data-stu-id="10b3b-131">This will allow multiple users to log into the HoloLens 1st Gen Commercial Suite/the HoloLens 2 device.</span></span>

<span data-ttu-id="10b3b-132">Ausführlichere Informationen zu Identitätstypen finden Sie im Artikel [HoloLens Identity](hololens-identity.md) .</span><span class="sxs-lookup"><span data-stu-id="10b3b-132">For more detailed information about identity types, please visit our [HoloLens Identity](hololens-identity.md) article.</span></span>

### <span data-ttu-id="10b3b-133">Art der Features</span><span class="sxs-lookup"><span data-stu-id="10b3b-133">Type of Features</span></span>

<span data-ttu-id="10b3b-134">Ihre Funktionsanforderungen bestimmen, welche HoloLens Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="10b3b-134">Your feature requirements will determine which HoloLens you need.</span></span> <span data-ttu-id="10b3b-135">Eine beliebte Funktion, die in Kundenumgebungen häufig bereitgestellt wird, ist der Kiosk Modus.</span><span class="sxs-lookup"><span data-stu-id="10b3b-135">One popular feature that we see deployed in customer environments frequently is Kiosk Mode.</span></span> <span data-ttu-id="10b3b-136">Eine Liste der HoloLens-Schlüsselfeatures und die Editionen von HoloLens, die Sie unterstützen, finden Sie [hier](hololens-commercial-features.md).</span><span class="sxs-lookup"><span data-stu-id="10b3b-136">A list of HoloLens key features, and the editions of HoloLens that support them, can be found [here](hololens-commercial-features.md).</span></span>

**<span data-ttu-id="10b3b-137">Was ist der Kiosk Modus?</span><span class="sxs-lookup"><span data-stu-id="10b3b-137">What is Kiosk Mode?</span></span>**

<span data-ttu-id="10b3b-138">Der Kiosk Modus ist eine Möglichkeit, die apps zu beschränken, auf die ein Benutzer Zugriff hat.</span><span class="sxs-lookup"><span data-stu-id="10b3b-138">Kiosk mode is a way to restrict the apps that a user has access to.</span></span> <span data-ttu-id="10b3b-139">Das bedeutet, dass Benutzern nur der Zugriff auf bestimmte apps gestattet ist.</span><span class="sxs-lookup"><span data-stu-id="10b3b-139">This means that users will only be allowed to access certain apps.</span></span>

**<span data-ttu-id="10b3b-140">Welchen Kiosk Modus benötige ich?</span><span class="sxs-lookup"><span data-stu-id="10b3b-140">What Kiosk Mode do I require?</span></span>**

<span data-ttu-id="10b3b-141">Es gibt zwei Arten von Kiosk Modi: einzelne APP und Multi-app.</span><span class="sxs-lookup"><span data-stu-id="10b3b-141">There are two types of Kiosk Modes: Single app and multi-app.</span></span> <span data-ttu-id="10b3b-142">Mit einem einzelnen App-Kioskmodus kann der Benutzer nur auf eine App zugreifen, während der Multi-App-Kioskmodus Benutzern den Zugriff auf mehrere angegebene Apps ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="10b3b-142">Single app kiosk mode allows user to only access one app while multi-app kiosk mode allows users to access multiple, specified apps.</span></span> <span data-ttu-id="10b3b-143">Um festzustellen, welcher Kioskmodus für Ihr Unternehmen richtig ist, müssen die folgenden beiden Fragen beantwortet werden:</span><span class="sxs-lookup"><span data-stu-id="10b3b-143">To determine which kiosk mode is right for your corporation, the following two questions need to be answered:</span></span>

1. **<span data-ttu-id="10b3b-144">Erfordern verschiedene Benutzer unterschiedliche Erfahrungen/Einschränkungen?</span><span class="sxs-lookup"><span data-stu-id="10b3b-144">Do different users require different experiences/restrictions?</span></span>** <span data-ttu-id="10b3b-145">Das folgende Beispiel: Benutzer a ist ein Field Service Engineer, der nur Zugriff auf Remote Assist benötigt.</span><span class="sxs-lookup"><span data-stu-id="10b3b-145">Consider the following example: User A is a field service engineer who only needs access to Remote Assist.</span></span> <span data-ttu-id="10b3b-146">Benutzer B ist ein Praktikant, der nur Zugriff auf Leitfäden benötigt.</span><span class="sxs-lookup"><span data-stu-id="10b3b-146">User B is a trainee who only needs access to Guides.</span></span>
    1. <span data-ttu-id="10b3b-147">Wenn ja, benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="10b3b-147">If yes, you will require the following:</span></span>
        1. <span data-ttu-id="10b3b-148">Azure Ad-Konten als die Methode zum Anmelden beim Gerät.</span><span class="sxs-lookup"><span data-stu-id="10b3b-148">Azure AD Accounts as the method of signing into the device.</span></span>
        1. <span data-ttu-id="10b3b-149">**Multi-App-** Kioskmodus.</span><span class="sxs-lookup"><span data-stu-id="10b3b-149">**Multi-app** kiosk mode.</span></span>
    1. <span data-ttu-id="10b3b-150">Wenn Nein, fahren Sie mit der Frage zwei fort</span><span class="sxs-lookup"><span data-stu-id="10b3b-150">If no, continue to question two</span></span>
1. **<span data-ttu-id="10b3b-151">Benötigen Sie eine Multi-App-Umgebung?</span><span class="sxs-lookup"><span data-stu-id="10b3b-151">Do you require a multi-app experience?</span></span>**
    1. <span data-ttu-id="10b3b-152">Wenn ja, ist der Modus für **Multi-App-** Kiosk erforderlich.</span><span class="sxs-lookup"><span data-stu-id="10b3b-152">If yes, **Multi-app** kiosk is mode is needed</span></span>
    1. <span data-ttu-id="10b3b-153">Wenn Sie die Antwort auf Frage 1 und 2 nicht haben, kann der **Einzel-App-** Kioskmodus verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10b3b-153">If your answer to question 1 and 2 are both no, **single-app** kiosk mode can be used</span></span>

**<span data-ttu-id="10b3b-154">So konfigurieren Sie den Kiosk Modus:</span><span class="sxs-lookup"><span data-stu-id="10b3b-154">How to Configure Kiosk Mode:</span></span>**

<span data-ttu-id="10b3b-155">Es gibt zwei Hauptmethoden ([Bereitstellungspakete](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) und [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) zum Bereitstellen des Kioskmodus für HoloLens.</span><span class="sxs-lookup"><span data-stu-id="10b3b-155">There are two main ways ([provisioning packages](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) and [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) to deploy kiosk mode for HoloLens.</span></span> <span data-ttu-id="10b3b-156">Diese Optionen werden später im Dokument erläutert. Sie können jedoch die obigen Links verwenden, um zu den entsprechenden Abschnitten in diesem Dokument zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="10b3b-156">These options will be discussed later in the document; however, you can use the links above to jump to the respective sections in this doc.</span></span>

### <span data-ttu-id="10b3b-157">Spezifische Szenarien für apps und Apps</span><span class="sxs-lookup"><span data-stu-id="10b3b-157">Apps and App Specific Scenarios</span></span>

<span data-ttu-id="10b3b-158">Die meisten der in diesem Dokument gefundenen Schritte gelten auch für die folgenden apps:</span><span class="sxs-lookup"><span data-stu-id="10b3b-158">The majority of the steps found in this document will also apply to the following apps:</span></span>

| <span data-ttu-id="10b3b-159">App</span><span class="sxs-lookup"><span data-stu-id="10b3b-159">App</span></span> | <span data-ttu-id="10b3b-160">App-spezifische Szenarien</span><span class="sxs-lookup"><span data-stu-id="10b3b-160">App Specific Scenarios</span></span> |
| --- | --- |
| <span data-ttu-id="10b3b-161">Remote Unterstützung</span><span class="sxs-lookup"><span data-stu-id="10b3b-161">Remote Assist</span></span> | [<span data-ttu-id="10b3b-162">Mandantenübergreifende Kommunikation</span><span class="sxs-lookup"><span data-stu-id="10b3b-162">Cross Tenant Communication</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| <span data-ttu-id="10b3b-163">Handbücher</span><span class="sxs-lookup"><span data-stu-id="10b3b-163">Guides</span></span>  | *<span data-ttu-id="10b3b-164">Demnächst</span><span class="sxs-lookup"><span data-stu-id="10b3b-164">Coming Soon</span></span>* |
|<span data-ttu-id="10b3b-165">Benutzerdefinierte apps</span><span class="sxs-lookup"><span data-stu-id="10b3b-165">Custom Apps</span></span> | *<span data-ttu-id="10b3b-166">Demnächst</span><span class="sxs-lookup"><span data-stu-id="10b3b-166">Coming Soon</span></span>* |

### <span data-ttu-id="10b3b-167">Ermitteln der Registrierungsmethode</span><span class="sxs-lookup"><span data-stu-id="10b3b-167">Determine your enrollment method</span></span>

1. <span data-ttu-id="10b3b-168">Massenregistrierung mit einem Sicherheitstoken in einem Bereitstellungspaket.</span><span class="sxs-lookup"><span data-stu-id="10b3b-168">Bulk enrollment with a security token in a provisioning package.</span></span>  
  <span data-ttu-id="10b3b-169">Pros: Dies ist der automatisierte Ansatz </span><span class="sxs-lookup"><span data-stu-id="10b3b-169">Pros: this is the most automated approach</span></span>\
  <span data-ttu-id="10b3b-170">Cons: übernimmt das erste serverseitige Setup</span><span class="sxs-lookup"><span data-stu-id="10b3b-170">Cons: takes initial server-side setup</span></span>  
1. <span data-ttu-id="10b3b-171">Anmeldung für Benutzer automatisch registrieren.</span><span class="sxs-lookup"><span data-stu-id="10b3b-171">Auto-enroll on user sign in.</span></span>  
  <span data-ttu-id="10b3b-172">Pros: einfachster Ansatz</span><span class="sxs-lookup"><span data-stu-id="10b3b-172">Pros: easiest approach</span></span>  
  <span data-ttu-id="10b3b-173">Nachteile: die Benutzer müssen die Einrichtung abschließen, nachdem das Bereitstellungspaket angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="10b3b-173">Cons: users will need to complete set up after the provisioning package has been applied</span></span>
1. <span data-ttu-id="10b3b-174">_nicht empfohlen_ – Manuelles Registrieren des Post-Setups.</span><span class="sxs-lookup"><span data-stu-id="10b3b-174">_not recommended_ - Manually enroll post-setup.</span></span>  
  <span data-ttu-id="10b3b-175">Pros: nach der Einrichtung möglich registrieren</span><span class="sxs-lookup"><span data-stu-id="10b3b-175">Pros: possible to enroll after set up</span></span>  
  <span data-ttu-id="10b3b-176">Nachteile: die meisten manuellen Vorgehensweisen und Geräte sind erst dann zentral verwaltbar, wenn Sie manuell registriert werden.</span><span class="sxs-lookup"><span data-stu-id="10b3b-176">Cons: most manual approach and devices aren't centrally manageable until they're manually enrolled.</span></span>

  <span data-ttu-id="10b3b-177">Weitere Informationen finden Sie [hier](hololens-enroll-mdm.md) .</span><span class="sxs-lookup"><span data-stu-id="10b3b-177">More information can be found [here](hololens-enroll-mdm.md)</span></span>

### <span data-ttu-id="10b3b-178">Ermitteln, ob Sie ein Bereitstellungspaket erstellen müssen</span><span class="sxs-lookup"><span data-stu-id="10b3b-178">Determine if you need to create a provisioning package</span></span>

<span data-ttu-id="10b3b-179">Es gibt zwei Methoden zum Konfigurieren eines HoloLens-Geräts (Bereitstellungspakete und MDMs).</span><span class="sxs-lookup"><span data-stu-id="10b3b-179">There are two methods to configure a HoloLens device (Provisioning packages and MDMs).</span></span> <span data-ttu-id="10b3b-180">Wir empfehlen Ihnen, Ihr MDM-Gerät zum Konfigurieren Ihres HoloLens-Geräts zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="10b3b-180">We suggest using your MDM to configure you HoloLens device.</span></span> <span data-ttu-id="10b3b-181">Es gibt jedoch einige Szenarien, in denen die Verwendung eines Bereitstellungspakets die bessere Wahl ist:</span><span class="sxs-lookup"><span data-stu-id="10b3b-181">However, there are some scenarios where using a provisioning package is the better choice:</span></span>

1. <span data-ttu-id="10b3b-182">Sie möchten das HoloLens so konfigurieren, dass die Out-of-Box-Umgebung übersprungen wird (OOBE)</span><span class="sxs-lookup"><span data-stu-id="10b3b-182">You want to configure the HoloLens to skip the Out of Box Experience (OOBE)</span></span>
1. <span data-ttu-id="10b3b-183">Sie haben Probleme beim Bereitstellen von Zertifikaten in einem komplexen Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="10b3b-183">You are having trouble deploying certificate in a complex network.</span></span> <span data-ttu-id="10b3b-184">Die meiste Zeit können Sie Zertifikate mithilfe von MDM (auch in komplexen Umgebungen) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="10b3b-184">The majority of the time you can deploy certificates using MDM (even in complex environments).</span></span> <span data-ttu-id="10b3b-185">Einige Szenarien erfordern jedoch, dass Zertifikate über das Bereitstellungspaket bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="10b3b-185">However, some scenarios require certificates to be deployed through the provisioning package.</span></span>

<span data-ttu-id="10b3b-186">Einige der HoloLens-Konfigurationen, die in einem Bereitstellungspaket angewendet werden können:</span><span class="sxs-lookup"><span data-stu-id="10b3b-186">Some of the HoloLens configurations you can apply in a provisioning package:</span></span>

- <span data-ttu-id="10b3b-187">Anwenden von Zertifikaten auf das Gerät</span><span class="sxs-lookup"><span data-stu-id="10b3b-187">Apply certificates to the device</span></span>
- <span data-ttu-id="10b3b-188">Einrichten einer WLAN-Verbindung</span><span class="sxs-lookup"><span data-stu-id="10b3b-188">Set up a Wi-Fi connection</span></span>
- <span data-ttu-id="10b3b-189">Vorkonfigurieren von vordefinierten Fragen wie Sprache und Gebietsschema</span><span class="sxs-lookup"><span data-stu-id="10b3b-189">Pre-configure out of box questions like language and locale</span></span>
- <span data-ttu-id="10b3b-190">(HoloLens 2) Massenregistrieren für den Mobilgeräte-Verwaltungsdienst</span><span class="sxs-lookup"><span data-stu-id="10b3b-190">(HoloLens 2) bulk enroll in mobile device management</span></span>
- <span data-ttu-id="10b3b-191">(HoloLens v1) Anwenden des Schlüssels zum Aktivieren von Windows Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="10b3b-191">(HoloLens v1) Apply key to enable Windows Holographic for Business</span></span>

<span data-ttu-id="10b3b-192">Wenn Sie Bereitstellungspakete verwenden möchten, folgen Sie [diesem Leitfaden](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="10b3b-192">If you decide to use provisioning packages, follow [this guide](hololens-provisioning.md).</span></span>

## <span data-ttu-id="10b3b-193">Support erhalten</span><span class="sxs-lookup"><span data-stu-id="10b3b-193">Get support</span></span>

<span data-ttu-id="10b3b-194">Support erhalten Sie über die Microsoft-Support Website.</span><span class="sxs-lookup"><span data-stu-id="10b3b-194">Get support through the Microsoft support site.</span></span>

[<span data-ttu-id="10b3b-195">Support-Anfrage einreichen</span><span class="sxs-lookup"><span data-stu-id="10b3b-195">File a support request</span></span>](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
