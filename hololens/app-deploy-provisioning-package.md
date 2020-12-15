---
title: Bereitstellungspaket
description: APP, App Deployment, Enterprise App demployment, Bereitstellung
keywords: APP, App Deployment, Enterprise App demployment, Bereitstellung
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 60efc454f9e1221372279401da9f8ee918e061e7
ms.sourcegitcommit: efa3fb7e353c5e56ee467cc7fd94ffdfaf46e2e5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "11219222"
---
# <span data-ttu-id="2019b-104">Bereitstellungspaket</span><span class="sxs-lookup"><span data-stu-id="2019b-104">Provisioning Package</span></span>

<span data-ttu-id="2019b-105">Bereitstellungspakete können zum Vorbereiten und Konfigurieren von Geräten in einer Umgebung ohne Zugriff auf die Endpunkt Verwaltung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2019b-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="2019b-106">Sie können auch unabhängig von der Identität des Benutzers, dem Registrierungsstatus, während der Out-of-Box-Umgebung (OOBE) oder durch [Anwenden eines Bereitstellungspakets während des Setups](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)auf einem Gerät bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2019b-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="2019b-107">Überlegungen zu Bereitstellungspaketen:</span><span class="sxs-lookup"><span data-stu-id="2019b-107">Provisioning Packages considerations:</span></span>
* <span data-ttu-id="2019b-108">Nicht öffentliche apps</span><span class="sxs-lookup"><span data-stu-id="2019b-108">Non-Public apps</span></span>
* <span data-ttu-id="2019b-109">Nur USB-Seite laden</span><span class="sxs-lookup"><span data-stu-id="2019b-109">USB side-load only</span></span>
* <span data-ttu-id="2019b-110">Keine automatische Aktualisierung (erfordert manuelle Updates über PPKGs)</span><span class="sxs-lookup"><span data-stu-id="2019b-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="2019b-111">Apps, die über ein Bereitstellungspaket installiert wurden, müssen mit einem Zertifikat im lokalen Computerspeicher signiert sein.</span><span class="sxs-lookup"><span data-stu-id="2019b-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="2019b-112">Bereitstellungspakete können nur Zertifikate auf dem Gerätespeicher (lokaler Computer) installieren, daher können die APP und das Zertifikat über dasselbe Bereitstellungspaket installiert werden.</span><span class="sxs-lookup"><span data-stu-id="2019b-112">Provisioning packages can only install certificates to the device (local machine) store, therefore the app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="2019b-113">Wenn Sie Ihr Zertifikat von MDM bereitstellen oder über den [Zertifikat-Manager](certificate-manager.md)installieren, stellen Sie sicher, dass Sie das Zertifikat im lokalen Computerspeicher bereitstellen, um auf diese Weise installierte apps zu signieren.</span><span class="sxs-lookup"><span data-stu-id="2019b-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), please make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="2019b-114">Informationen zu den Grundlagen zum Erstellen eines Bereitstellungspakets für HoloLens-Geräte finden Sie unter [HoloLens-Bereitstellung](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="2019b-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="2019b-115">Um eine APP bereitzustellen, müssen Sie mit der erweiterten Bereitstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="2019b-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="2019b-116">HoloLens (1st Generation) hat begrenzte Unterstützung bei der Installation von apps (**UniversalAppInstall**) mithilfe eines Bereitstellungspakets.</span><span class="sxs-lookup"><span data-stu-id="2019b-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="2019b-117">HoloLens (1st Gen)-Geräte unterstützen nur die Installation einer APP über PPKG nur während der OOBE und nur bei Installationen des Benutzerkontexts.</span><span class="sxs-lookup"><span data-stu-id="2019b-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <span data-ttu-id="2019b-118">Setup</span><span class="sxs-lookup"><span data-stu-id="2019b-118">Setup</span></span>

<span data-ttu-id="2019b-119">Führen Sie im [Windows-Konfigurations-Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) die folgenden vier Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="2019b-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following 4 steps.</span></span>

1. <span data-ttu-id="2019b-120">Setzen Sie ApplicationManagement/AllowAllTrustedApps auf "Ja".</span><span class="sxs-lookup"><span data-stu-id="2019b-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="2019b-121">Siehe: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="2019b-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="2019b-122">Geben Sie unter **UniversalAppInstall**  >  **UserContextAppLicense** die **PackageFamilyName**ein.</span><span class="sxs-lookup"><span data-stu-id="2019b-122">Under **UniversalAppInstall** > **UserContextAppLicense** please enter the **PackageFamilyName**.</span></span> <span data-ttu-id="2019b-123">Siehe [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="2019b-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="2019b-124">Siehe auch: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="2019b-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="2019b-125">Sie können Device Portal auf einem Gerät verwenden, auf dem Sie Ihre APP bereits installiert haben.</span><span class="sxs-lookup"><span data-stu-id="2019b-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="2019b-126">Besuchen Sie die Seite "Apps", und schauen Sie sich die PackageRelativeID-Zeile, alle Informationen vor dem "!" an. Ist Ihre **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="2019b-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>
    
3. <span data-ttu-id="2019b-127">Sie sehen dann, dass Sie einen neuen Abschnitt, " **applicationdatei**" haben.</span><span class="sxs-lookup"><span data-stu-id="2019b-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="2019b-128">In diesem Bereich können Sie Ihr AppX-Bundle hochladen.</span><span class="sxs-lookup"><span data-stu-id="2019b-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="2019b-129">Je nachdem, ob Sie Ihre APP gekauft oder eine eigene Branchen-App erstellt haben, müssen Sie die Lizenzdatei oder das Sicherheitszertifikat hochladen.</span><span class="sxs-lookup"><span data-stu-id="2019b-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="2019b-130">Für Lizenzdatei: unter **UniversalAppInstall**  >  **UserContextAppLience** , und navigieren Sie zum Speicherort Ihrer Lizenz, und laden Sie Sie hoch.</span><span class="sxs-lookup"><span data-stu-id="2019b-130">For license file: Under **UniversalAppInstall** > **UserContextAppLience** and browse to the location of your license and upload it.</span></span> 
    - <span data-ttu-id="2019b-131">Klicken Sie für Sicherheitsdatei auf **Zertifikate** , und wählen Sie das Zertifikat aus, das Sie neben Ihrem AppX-Paket installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="2019b-131">For security file navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="2019b-132">Stellen Sie sicher, dass Sie Ihr Projekt an einem sicheren Ort speichern.</span><span class="sxs-lookup"><span data-stu-id="2019b-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="2019b-133">**Exportieren** Sie Sie dann als **Bereitstellungspaket**.</span><span class="sxs-lookup"><span data-stu-id="2019b-133">Then **Export** it as a **Provisioning Package**.</span></span>  
    
<span data-ttu-id="2019b-134">Siehe auch: [Anwenden Ihres Provisiong-Pakets auf HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="2019b-134">See also: [Apply your provisiong package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
