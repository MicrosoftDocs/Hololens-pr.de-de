---
title: Bereitstellungspaket
description: APP, App Deployment, Enterprise App demployment, Bereitstellung
keywords: APP, App Deployment, Enterprise App demployment, Bereitstellung
author: v-jodben
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
ms.openlocfilehash: 7417f9e8cf1921d9fdb57dbd96fff094e21c44f9
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857910"
---
# <span data-ttu-id="82d57-104">Bereitstellungspaket</span><span class="sxs-lookup"><span data-stu-id="82d57-104">Provisioning Package</span></span>

<span data-ttu-id="82d57-105">Bereitstellungspakete können zum Vorbereiten und Konfigurieren von Geräten in einer Umgebung ohne Zugriff auf die Endpunkt Verwaltung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="82d57-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="82d57-106">Sie können auch unabhängig von der Identität des Benutzers, dem Registrierungsstatus, während der Out-of-Box-Umgebung (OOBE) oder durch [Anwenden eines Bereitstellungspakets während des Setups](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)auf einem Gerät bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="82d57-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="82d57-107">Überlegungen zu Bereitstellungspaketen:</span><span class="sxs-lookup"><span data-stu-id="82d57-107">Provisioning Packages considerations:</span></span>
* <span data-ttu-id="82d57-108">Nicht öffentliche apps</span><span class="sxs-lookup"><span data-stu-id="82d57-108">Non-Public apps</span></span>
* <span data-ttu-id="82d57-109">Nur USB-Seite laden</span><span class="sxs-lookup"><span data-stu-id="82d57-109">USB side-load only</span></span>
* <span data-ttu-id="82d57-110">Keine automatische Aktualisierung (erfordert manuelle Updates über PPKGs)</span><span class="sxs-lookup"><span data-stu-id="82d57-110">No auto update (requires manual updates via PPKGs)</span></span>

> [!NOTE] 
> <span data-ttu-id="82d57-111">Informationen zu den Grundlagen zum Erstellen eines Bereitstellungspakets für HoloLens-Geräte finden Sie unter [HoloLens-Bereitstellung](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="82d57-111">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="82d57-112">Um eine APP bereitzustellen, müssen Sie mit der erweiterten Bereitstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="82d57-112">To deploy an app, you must start with advanced provisioning.</span></span> 

## <span data-ttu-id="82d57-113">Setup</span><span class="sxs-lookup"><span data-stu-id="82d57-113">Setup</span></span>

<span data-ttu-id="82d57-114">Führen Sie im [Windows-Konfigurations-Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) die folgenden vier Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="82d57-114">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following 4 steps.</span></span>

1. <span data-ttu-id="82d57-115">Setzen Sie ApplicationManagement/AllowAllTrustedApps auf "Ja".</span><span class="sxs-lookup"><span data-stu-id="82d57-115">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="82d57-116">Siehe: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="82d57-116">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>
2. <span data-ttu-id="82d57-117">Geben Sie unter **UniversalAppInstall**  >  **UserContextAppLicense** die **PackageFamilyName**ein.</span><span class="sxs-lookup"><span data-stu-id="82d57-117">Under **UniversalAppInstall** > **UserContextAppLicense** please enter the **PackageFamilyName**.</span></span> <span data-ttu-id="82d57-118">Siehe [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="82d57-118">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="82d57-119">Siehe auch: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="82d57-119">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>
    - <span data-ttu-id="82d57-120">Wenn Sie dies nicht wissen, können Sie Device Portal auf einem Gerät verwenden, auf dem Sie Ihre APP bereits installiert haben.</span><span class="sxs-lookup"><span data-stu-id="82d57-120">If you don’t know this, you can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="82d57-121">Besuchen Sie die Seite "Apps", und schauen Sie sich die PackageRelativeID-Zeile, alle Informationen vor dem "!" an. Ist Ihre **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="82d57-121">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>
3. <span data-ttu-id="82d57-122">Sie sehen dann, dass Sie einen neuen Abschnitt, " **applicationdatei**" haben.</span><span class="sxs-lookup"><span data-stu-id="82d57-122">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="82d57-123">In diesem Bereich können Sie Ihr AppX-Bundle hochladen.</span><span class="sxs-lookup"><span data-stu-id="82d57-123">Use this area to upload your appx bundle.</span></span> 
4. <span data-ttu-id="82d57-124">Je nachdem, ob Sie Ihre APP gekauft oder eine eigene Branchen-App erstellt haben, müssen Sie die Lizenzdatei oder das Sicherheitszertifikat hochladen.</span><span class="sxs-lookup"><span data-stu-id="82d57-124">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>
    - <span data-ttu-id="82d57-125">Für Lizenzdatei: unter **UniversalAppInstall**  >  **UserContextAppLience** , und navigieren Sie zum Speicherort Ihrer Lizenz, und laden Sie Sie hoch.</span><span class="sxs-lookup"><span data-stu-id="82d57-125">For license file: Under **UniversalAppInstall** > **UserContextAppLience** and browse to the location of your license and upload it.</span></span> 
    - <span data-ttu-id="82d57-126">Klicken Sie für Sicherheitsdatei auf **Zertifikate** , und wählen Sie das Zertifikat aus, das Sie neben Ihrem AppX-Paket installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="82d57-126">For security file navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span> 

<span data-ttu-id="82d57-127">Stellen Sie sicher, dass Sie Ihr Projekt an einem sicheren Ort speichern.</span><span class="sxs-lookup"><span data-stu-id="82d57-127">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="82d57-128">**Exportieren** Sie Sie dann als **Bereitstellungspaket**.</span><span class="sxs-lookup"><span data-stu-id="82d57-128">Then **Export** it as a **Provisioning Package**.</span></span>  
    
<span data-ttu-id="82d57-129">Siehe auch: [Anwenden Ihres Provisiong-Pakets auf HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="82d57-129">See also: [Apply your provisiong package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
