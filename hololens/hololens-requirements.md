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
ms.openlocfilehash: e53e6575ef688e01ce2d1f6124f3214b18b05c95
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865564"
---
# <span data-ttu-id="358b4-103">Bereitstellen von HoloLens in einer kommerziellen Umgebung</span><span class="sxs-lookup"><span data-stu-id="358b4-103">Deploy HoloLens in a commercial environment</span></span>

<span data-ttu-id="358b4-104">Sie können HoloLens im Maßstab in einer kommerziellen Einstellung bereitstellen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="358b4-104">You can deploy and configure HoloLens at scale in a commercial setting.</span></span> <span data-ttu-id="358b4-105">Dieser Artikel enthält Anweisungen zum Bereitstellen von HoloLens-Geräten in einer geschäftlichen Umgebung.</span><span class="sxs-lookup"><span data-stu-id="358b4-105">This article provides instructions for deploying HoloLens devices in a commercial environment.</span></span> <span data-ttu-id="358b4-106">Dieser Leitfaden geht von grundlegender Vertrautheit mit HoloLens aus.</span><span class="sxs-lookup"><span data-stu-id="358b4-106">This guide assumes basic familiarity with HoloLens.</span></span> <span data-ttu-id="358b4-107">Folgen Sie dem Leitfaden "erste [Schritte](hololens1-setup.md) ", um HoloLens zum ersten Mal einzurichten.</span><span class="sxs-lookup"><span data-stu-id="358b4-107">Follow the [get started guide](hololens1-setup.md) to set up HoloLens for the first time.</span></span>

<span data-ttu-id="358b4-108">In diesem Dokument wird auch davon ausgegangen, dass das HoloLens von Sicherheitsteams als sicher für die Verwendung im Unternehmensnetzwerk ausgewertet wurde.</span><span class="sxs-lookup"><span data-stu-id="358b4-108">This document also assumes that the HoloLens has been evaluated by security teams as safe to use on the corporate network.</span></span>  
> [!Tip]
> <span data-ttu-id="358b4-109">Weitere Informationen zur [HoloLens-Sicherheit](security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="358b4-109">Learn more about [HoloLens security](security-overview.md).</span></span>
> <span data-ttu-id="358b4-110">Für HoloLens (1st Gen)-Sicherheit lesen Sie bitte [diese FAQ](hololens1-faq-security.md).</span><span class="sxs-lookup"><span data-stu-id="358b4-110">For HoloLens (1st Gen) security please review [this FAQ](hololens1-faq-security.md).</span></span>

## <span data-ttu-id="358b4-111">Übersicht über Bereitstellungsschritte</span><span class="sxs-lookup"><span data-stu-id="358b4-111">Overview of Deployment Steps</span></span>

1. [<span data-ttu-id="358b4-112">Ermitteln der benötigten Features</span><span class="sxs-lookup"><span data-stu-id="358b4-112">Determine what features you need</span></span>](hololens-requirements.md#step-1-determine-what-you-need)
1. [<span data-ttu-id="358b4-113">Ermitteln, welche Lizenzen erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="358b4-113">Determine what licenses you need</span></span>](hololens-licenses-requirements.md)
1. <span data-ttu-id="358b4-114">[Konfigurieren Sie Ihr Netzwerk für HoloLens](hololens-commercial-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="358b4-114">[Configure your network for HoloLens](hololens-commercial-infrastructure.md).</span></span>
    1. <span data-ttu-id="358b4-115">Dieser Abschnitt enthält Bandbreitenanforderungen, URL und Ports, die für Ihre Firewall zugelassen werden müssen. Azure AD-Anleitung; Anleitung zur Verwaltung mobiler Geräte (MDM); Anleitung zur Bereitstellung und Verwaltung von apps und Zertifikat Leit Faden.</span><span class="sxs-lookup"><span data-stu-id="358b4-115">This section includes bandwidth requirements, URL, and ports that need to be allowed on your firewall; Azure AD guidance; Mobile Device Management (MDM) Guidance; app deployment/management guidance; and certificate guidance.</span></span>
1. <span data-ttu-id="358b4-116">Optional [Konfigurieren von HoloLens mit einem Bereitstellungspaket](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="358b4-116">(Optional) [Configure HoloLens using a provisioning package](hololens-provisioning.md)</span></span>
1. [<span data-ttu-id="358b4-117">Gerät registrieren</span><span class="sxs-lookup"><span data-stu-id="358b4-117">Enroll Device</span></span>](hololens-enroll-mdm.md)
1. [<span data-ttu-id="358b4-118">Einrichten von ringbasierten Updates für HoloLens</span><span class="sxs-lookup"><span data-stu-id="358b4-118">Set up ring based updates for HoloLens</span></span>](hololens-updates.md)
1. [<span data-ttu-id="358b4-119">Aktivieren der Bitlocker-Geräteverschlüsselung für HoloLens</span><span class="sxs-lookup"><span data-stu-id="358b4-119">Enable Bitlocker device encryption for HoloLens</span></span>](security-encryption-data-protection.md)

## <span data-ttu-id="358b4-120">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="358b4-120">Step 1.</span></span> <span data-ttu-id="358b4-121">Bestimmen, was Sie benötigen</span><span class="sxs-lookup"><span data-stu-id="358b4-121">Determine what you need</span></span>

<span data-ttu-id="358b4-122">Bevor Sie das HoloLens in Ihrer Umgebung bereitstellen, müssen Sie zunächst ermitteln, welche Features, Apps und Typen von Identitäten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="358b4-122">Before deploying the HoloLens in your environment, it is important to first determine what features, apps, and type of identities are needed.</span></span> <span data-ttu-id="358b4-123">Darüber hinaus ist es wichtig, sicherzustellen, dass Ihr Sicherheitsteam die Nutzung des HoloLens im Netzwerk des Unternehmens genehmigt hat.</span><span class="sxs-lookup"><span data-stu-id="358b4-123">It is also important to ensure that your security team has approved of the use of the HoloLens on the company's network.</span></span> <span data-ttu-id="358b4-124">Weitere Sicherheitsinformationen finden Sie unter [HoloLens2-Sicherheit](security-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="358b4-124">Please see [HoloLens2 security](security-overview.md) for additional security information.</span></span>

### <span data-ttu-id="358b4-125">Art der Identität</span><span class="sxs-lookup"><span data-stu-id="358b4-125">Type of Identity</span></span>

<span data-ttu-id="358b4-126">Ermitteln Sie den Typ der Identität, die zum Anmelden beim Gerät verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="358b4-126">Determine the type of identity that will be used to sign into the device.</span></span>

1. <span data-ttu-id="358b4-127">**Lokale Konten:** Dieses Konto ist auf dem Gerät lokal (wie ein lokales Administratorkonto auf einem Windows-PC).</span><span class="sxs-lookup"><span data-stu-id="358b4-127">**Local Accounts:** This account is local to the device (like a local admin account on a windows PC).</span></span> <span data-ttu-id="358b4-128">Dadurch können sich nur 1 Benutzer beim Gerät anmelden.</span><span class="sxs-lookup"><span data-stu-id="358b4-128">This will allow only 1 user to log into the device.</span></span>
2. <span data-ttu-id="358b4-129">**MSA:** Hierbei handelt es sich um ein privates Konto (wie Outlook, Hotmail, Gmail, Yahoo usw.). Dadurch können sich nur 1 Benutzer beim Gerät anmelden.</span><span class="sxs-lookup"><span data-stu-id="358b4-129">**MSA:** This is a personal account (like outlook, hotmail, gmail, yahoo, etc.) This will allow only 1 user to log into the device.</span></span>
3. <span data-ttu-id="358b4-130">**Azure Active Directory-Konten (Azure AD):** Hierbei handelt es sich um ein in Azure AD erstelltes Konto.</span><span class="sxs-lookup"><span data-stu-id="358b4-130">**Azure Active Directory (Azure AD) accounts:** This is an account created in Azure AD.</span></span> <span data-ttu-id="358b4-131">Dies gewährt ihrem Unternehmen die Möglichkeit, das HoloLens-Gerät zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="358b4-131">This grants your corporation the ability to manage the HoloLens device.</span></span> <span data-ttu-id="358b4-132">Auf diese Weise können sich mehrere Benutzer bei der HoloLens 1st Gen Commercial Suite/dem HoloLens 2-Gerät anmelden.</span><span class="sxs-lookup"><span data-stu-id="358b4-132">This will allow multiple users to log into the HoloLens 1st Gen Commercial Suite/the HoloLens 2 device.</span></span>

<span data-ttu-id="358b4-133">Ausführlichere Informationen zu Identitätstypen finden Sie im Artikel [HoloLens Identity](hololens-identity.md) .</span><span class="sxs-lookup"><span data-stu-id="358b4-133">For more detailed information about identity types, please visit our [HoloLens Identity](hololens-identity.md) article.</span></span>

### <span data-ttu-id="358b4-134">Art der Features</span><span class="sxs-lookup"><span data-stu-id="358b4-134">Type of Features</span></span>

<span data-ttu-id="358b4-135">Ihre Funktionsanforderungen bestimmen, welche HoloLens Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="358b4-135">Your feature requirements will determine which HoloLens you need.</span></span> <span data-ttu-id="358b4-136">Eine beliebte Funktion, die in Kundenumgebungen häufig bereitgestellt wird, ist der Kiosk Modus.</span><span class="sxs-lookup"><span data-stu-id="358b4-136">One popular feature that we see deployed in customer environments frequently is Kiosk Mode.</span></span> <span data-ttu-id="358b4-137">Eine Liste der HoloLens-Schlüsselfeatures und die Editionen von HoloLens, die Sie unterstützen, finden Sie [hier](hololens-commercial-features.md).</span><span class="sxs-lookup"><span data-stu-id="358b4-137">A list of HoloLens key features, and the editions of HoloLens that support them, can be found [here](hololens-commercial-features.md).</span></span>

**<span data-ttu-id="358b4-138">Was ist der Kiosk Modus?</span><span class="sxs-lookup"><span data-stu-id="358b4-138">What is Kiosk Mode?</span></span>**

<span data-ttu-id="358b4-139">Der Kiosk Modus ist eine Möglichkeit, die apps zu beschränken, auf die ein Benutzer Zugriff hat.</span><span class="sxs-lookup"><span data-stu-id="358b4-139">Kiosk mode is a way to restrict the apps that a user has access to.</span></span> <span data-ttu-id="358b4-140">Das bedeutet, dass Benutzern nur der Zugriff auf bestimmte apps gestattet ist.</span><span class="sxs-lookup"><span data-stu-id="358b4-140">This means that users will only be allowed to access certain apps.</span></span>

**<span data-ttu-id="358b4-141">Welchen Kiosk Modus benötige ich?</span><span class="sxs-lookup"><span data-stu-id="358b4-141">What Kiosk Mode do I require?</span></span>**

<span data-ttu-id="358b4-142">Es gibt zwei Arten von Kiosk Modi: einzelne APP und Multi-app.</span><span class="sxs-lookup"><span data-stu-id="358b4-142">There are two types of Kiosk Modes: Single app and multi-app.</span></span> <span data-ttu-id="358b4-143">Mit einem einzelnen App-Kioskmodus kann der Benutzer nur auf eine App zugreifen, während der Multi-App-Kioskmodus Benutzern den Zugriff auf mehrere angegebene Apps ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="358b4-143">Single app kiosk mode allows user to only access one app while multi-app kiosk mode allows users to access multiple, specified apps.</span></span> <span data-ttu-id="358b4-144">Um festzustellen, welcher Kioskmodus für Ihr Unternehmen richtig ist, müssen die folgenden beiden Fragen beantwortet werden:</span><span class="sxs-lookup"><span data-stu-id="358b4-144">To determine which kiosk mode is right for your corporation, the following two questions need to be answered:</span></span>

1. **<span data-ttu-id="358b4-145">Erfordern verschiedene Benutzer unterschiedliche Erfahrungen/Einschränkungen?</span><span class="sxs-lookup"><span data-stu-id="358b4-145">Do different users require different experiences/restrictions?</span></span>** <span data-ttu-id="358b4-146">Das folgende Beispiel: Benutzer a ist ein Field Service Engineer, der nur Zugriff auf Remote Assist benötigt.</span><span class="sxs-lookup"><span data-stu-id="358b4-146">Consider the following example: User A is a field service engineer who only needs access to Remote Assist.</span></span> <span data-ttu-id="358b4-147">Benutzer B ist ein Praktikant, der nur Zugriff auf Leitfäden benötigt.</span><span class="sxs-lookup"><span data-stu-id="358b4-147">User B is a trainee who only needs access to Guides.</span></span>
    1. <span data-ttu-id="358b4-148">Wenn ja, benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="358b4-148">If yes, you will require the following:</span></span>
        1. <span data-ttu-id="358b4-149">Azure Ad-Konten als die Methode zum Anmelden beim Gerät.</span><span class="sxs-lookup"><span data-stu-id="358b4-149">Azure AD Accounts as the method of signing into the device.</span></span>
        1. <span data-ttu-id="358b4-150">**Multi-App-** Kioskmodus.</span><span class="sxs-lookup"><span data-stu-id="358b4-150">**Multi-app** kiosk mode.</span></span>
    1. <span data-ttu-id="358b4-151">Wenn Nein, fahren Sie mit der Frage zwei fort</span><span class="sxs-lookup"><span data-stu-id="358b4-151">If no, continue to question two</span></span>
1. **<span data-ttu-id="358b4-152">Benötigen Sie eine Multi-App-Umgebung?</span><span class="sxs-lookup"><span data-stu-id="358b4-152">Do you require a multi-app experience?</span></span>**
    1. <span data-ttu-id="358b4-153">Wenn ja, ist der Modus für **Multi-App-** Kiosk erforderlich.</span><span class="sxs-lookup"><span data-stu-id="358b4-153">If yes, **Multi-app** kiosk is mode is needed</span></span>
    1. <span data-ttu-id="358b4-154">Wenn Sie die Antwort auf Frage 1 und 2 nicht haben, kann der **Einzel-App-** Kioskmodus verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="358b4-154">If your answer to question 1 and 2 are both no, **single-app** kiosk mode can be used</span></span>

**<span data-ttu-id="358b4-155">So konfigurieren Sie den Kiosk Modus:</span><span class="sxs-lookup"><span data-stu-id="358b4-155">How to Configure Kiosk Mode:</span></span>**

<span data-ttu-id="358b4-156">Es gibt zwei Hauptmethoden ([Bereitstellungspakete](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) und [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) zum Bereitstellen des Kioskmodus für HoloLens.</span><span class="sxs-lookup"><span data-stu-id="358b4-156">There are two main ways ([provisioning packages](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) and [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) to deploy kiosk mode for HoloLens.</span></span> <span data-ttu-id="358b4-157">Diese Optionen werden später im Dokument erläutert. Sie können jedoch die obigen Links verwenden, um zu den entsprechenden Abschnitten in diesem Dokument zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="358b4-157">These options will be discussed later in the document; however, you can use the links above to jump to the respective sections in this doc.</span></span>

### <span data-ttu-id="358b4-158">Spezifische Szenarien für apps und Apps</span><span class="sxs-lookup"><span data-stu-id="358b4-158">Apps and App Specific Scenarios</span></span>

<span data-ttu-id="358b4-159">Die meisten der in diesem Dokument gefundenen Schritte gelten auch für die folgenden apps:</span><span class="sxs-lookup"><span data-stu-id="358b4-159">The majority of the steps found in this document will also apply to the following apps:</span></span>

| <span data-ttu-id="358b4-160">App</span><span class="sxs-lookup"><span data-stu-id="358b4-160">App</span></span> | <span data-ttu-id="358b4-161">App-spezifische Szenarien</span><span class="sxs-lookup"><span data-stu-id="358b4-161">App Specific Scenarios</span></span> |
| --- | --- |
| <span data-ttu-id="358b4-162">Remote Unterstützung</span><span class="sxs-lookup"><span data-stu-id="358b4-162">Remote Assist</span></span> | [<span data-ttu-id="358b4-163">Mandantenübergreifende Kommunikation</span><span class="sxs-lookup"><span data-stu-id="358b4-163">Cross Tenant Communication</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| <span data-ttu-id="358b4-164">Handbücher</span><span class="sxs-lookup"><span data-stu-id="358b4-164">Guides</span></span>  | *<span data-ttu-id="358b4-165">Demnächst</span><span class="sxs-lookup"><span data-stu-id="358b4-165">Coming Soon</span></span>* |
|<span data-ttu-id="358b4-166">Benutzerdefinierte apps</span><span class="sxs-lookup"><span data-stu-id="358b4-166">Custom Apps</span></span> | *<span data-ttu-id="358b4-167">Demnächst</span><span class="sxs-lookup"><span data-stu-id="358b4-167">Coming Soon</span></span>* |

### <span data-ttu-id="358b4-168">Ermitteln der Registrierungsmethode</span><span class="sxs-lookup"><span data-stu-id="358b4-168">Determine your enrollment method</span></span>

1. <span data-ttu-id="358b4-169">Massenregistrierung mit einem Sicherheitstoken in einem Bereitstellungspaket.</span><span class="sxs-lookup"><span data-stu-id="358b4-169">Bulk enrollment with a security token in a provisioning package.</span></span>  
  <span data-ttu-id="358b4-170">Pros: Dies ist der automatisierte Ansatz </span><span class="sxs-lookup"><span data-stu-id="358b4-170">Pros: this is the most automated approach</span></span>\
  <span data-ttu-id="358b4-171">Cons: übernimmt das erste serverseitige Setup</span><span class="sxs-lookup"><span data-stu-id="358b4-171">Cons: takes initial server-side setup</span></span>  
1. <span data-ttu-id="358b4-172">Anmeldung für Benutzer automatisch registrieren.</span><span class="sxs-lookup"><span data-stu-id="358b4-172">Auto-enroll on user sign in.</span></span>  
  <span data-ttu-id="358b4-173">Pros: einfachster Ansatz</span><span class="sxs-lookup"><span data-stu-id="358b4-173">Pros: easiest approach</span></span>  
  <span data-ttu-id="358b4-174">Nachteile: die Benutzer müssen die Einrichtung abschließen, nachdem das Bereitstellungspaket angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="358b4-174">Cons: users will need to complete set up after the provisioning package has been applied</span></span>
1. <span data-ttu-id="358b4-175">_nicht empfohlen_ – Manuelles Registrieren des Post-Setups.</span><span class="sxs-lookup"><span data-stu-id="358b4-175">_not recommended_ - Manually enroll post-setup.</span></span>  
  <span data-ttu-id="358b4-176">Pros: nach der Einrichtung möglich registrieren</span><span class="sxs-lookup"><span data-stu-id="358b4-176">Pros: possible to enroll after set up</span></span>  
  <span data-ttu-id="358b4-177">Nachteile: die meisten manuellen Vorgehensweisen und Geräte sind erst dann zentral verwaltbar, wenn Sie manuell registriert werden.</span><span class="sxs-lookup"><span data-stu-id="358b4-177">Cons: most manual approach and devices aren't centrally manageable until they're manually enrolled.</span></span>

  <span data-ttu-id="358b4-178">Weitere Informationen finden Sie [hier](hololens-enroll-mdm.md) .</span><span class="sxs-lookup"><span data-stu-id="358b4-178">More information can be found [here](hololens-enroll-mdm.md)</span></span>

### <span data-ttu-id="358b4-179">Ermitteln, ob Sie ein Bereitstellungspaket erstellen müssen</span><span class="sxs-lookup"><span data-stu-id="358b4-179">Determine if you need to create a provisioning package</span></span>

<span data-ttu-id="358b4-180">Es gibt zwei Methoden zum Konfigurieren eines HoloLens-Geräts (Bereitstellungspakete und MDMs).</span><span class="sxs-lookup"><span data-stu-id="358b4-180">There are two methods to configure a HoloLens device (Provisioning packages and MDMs).</span></span> <span data-ttu-id="358b4-181">Wir empfehlen Ihnen, Ihr MDM-Gerät zum Konfigurieren Ihres HoloLens-Geräts zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="358b4-181">We suggest using your MDM to configure you HoloLens device.</span></span> <span data-ttu-id="358b4-182">Es gibt jedoch einige Szenarien, in denen die Verwendung eines Bereitstellungspakets die bessere Wahl ist:</span><span class="sxs-lookup"><span data-stu-id="358b4-182">However, there are some scenarios where using a provisioning package is the better choice:</span></span>

1. <span data-ttu-id="358b4-183">Sie möchten das HoloLens so konfigurieren, dass die Out-of-Box-Umgebung übersprungen wird (OOBE)</span><span class="sxs-lookup"><span data-stu-id="358b4-183">You want to configure the HoloLens to skip the Out of Box Experience (OOBE)</span></span>
1. <span data-ttu-id="358b4-184">Sie haben Probleme beim Bereitstellen von Zertifikaten in einem komplexen Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="358b4-184">You are having trouble deploying certificate in a complex network.</span></span> <span data-ttu-id="358b4-185">Die meiste Zeit können Sie Zertifikate mithilfe von MDM (auch in komplexen Umgebungen) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="358b4-185">The majority of the time you can deploy certificates using MDM (even in complex environments).</span></span> <span data-ttu-id="358b4-186">Einige Szenarien erfordern jedoch, dass Zertifikate über das Bereitstellungspaket bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="358b4-186">However, some scenarios require certificates to be deployed through the provisioning package.</span></span>

<span data-ttu-id="358b4-187">Einige der HoloLens-Konfigurationen, die in einem Bereitstellungspaket angewendet werden können:</span><span class="sxs-lookup"><span data-stu-id="358b4-187">Some of the HoloLens configurations you can apply in a provisioning package:</span></span>

- <span data-ttu-id="358b4-188">Anwenden von Zertifikaten auf das Gerät</span><span class="sxs-lookup"><span data-stu-id="358b4-188">Apply certificates to the device</span></span>
- <span data-ttu-id="358b4-189">Einrichten einer WLAN-Verbindung</span><span class="sxs-lookup"><span data-stu-id="358b4-189">Set up a Wi-Fi connection</span></span>
- <span data-ttu-id="358b4-190">Vorkonfigurieren von vordefinierten Fragen wie Sprache und Gebietsschema</span><span class="sxs-lookup"><span data-stu-id="358b4-190">Pre-configure out of box questions like language and locale</span></span>
- <span data-ttu-id="358b4-191">(HoloLens 2) Massenregistrieren für den Mobilgeräte-Verwaltungsdienst</span><span class="sxs-lookup"><span data-stu-id="358b4-191">(HoloLens 2) bulk enroll in mobile device management</span></span>
- <span data-ttu-id="358b4-192">(HoloLens v1) Anwenden des Schlüssels zum Aktivieren von Windows Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="358b4-192">(HoloLens v1) Apply key to enable Windows Holographic for Business</span></span>

<span data-ttu-id="358b4-193">Wenn Sie Bereitstellungspakete verwenden möchten, folgen Sie [diesem Leitfaden](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="358b4-193">If you decide to use provisioning packages, follow [this guide](hololens-provisioning.md).</span></span>

## <span data-ttu-id="358b4-194">Support erhalten</span><span class="sxs-lookup"><span data-stu-id="358b4-194">Get support</span></span>

<span data-ttu-id="358b4-195">Support erhalten Sie über die Microsoft-Support Website.</span><span class="sxs-lookup"><span data-stu-id="358b4-195">Get support through the Microsoft support site.</span></span>

[<span data-ttu-id="358b4-196">Support-Anfrage einreichen</span><span class="sxs-lookup"><span data-stu-id="358b4-196">File a support request</span></span>](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
