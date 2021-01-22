---
title: Bereitstellungspaket
description: Erfahren Sie mehr über das Packen, Bereitstellen, Bereitstellen und Bereitstellen von Unternehmens-Apps für HoloLens-Geräte.
keywords: App, App-Bereitstellung, Enterprise-App-Bereitstellung, Bereitstellung
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
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283696"
---
# <span data-ttu-id="c8b8d-104">Bereitstellungspaket</span><span class="sxs-lookup"><span data-stu-id="c8b8d-104">Provisioning Package</span></span>

<span data-ttu-id="c8b8d-105">Bereitstellungspakete können zum Vorbereiten und Konfigurieren von Geräten in einer Umgebung ohne Zugriff auf die Endpunktverwaltung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c8b8d-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="c8b8d-106">Sie können auch auf einem Gerät bereitgestellt werden, unabhängig von der Identität des Benutzers, des Registrierungsstatus, während der Out of Box Experience (OOBE) oder durch Anwenden eines Bereitstellungspakets während des [Setups.](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="c8b8d-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="c8b8d-107">Überlegungen zu Bereitstellungspaketen:</span><span class="sxs-lookup"><span data-stu-id="c8b8d-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="c8b8d-108">Nicht öffentliche Apps</span><span class="sxs-lookup"><span data-stu-id="c8b8d-108">Non-Public apps</span></span>
* <span data-ttu-id="c8b8d-109">Nur usbseitiges Laden</span><span class="sxs-lookup"><span data-stu-id="c8b8d-109">USB side-load only</span></span>
* <span data-ttu-id="c8b8d-110">Kein automatisches Update (erfordert manuelle Updates über PPKGs)</span><span class="sxs-lookup"><span data-stu-id="c8b8d-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="c8b8d-111">Apps, die über ein Bereitstellungspaket installiert werden, müssen von einem Zertifikat im lokalen Computerspeicher signiert sein.</span><span class="sxs-lookup"><span data-stu-id="c8b8d-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="c8b8d-112">Bereitstellungspakete können nur Zertifikate im Speicher des Geräts (lokaler Computer) installieren, daher können eine App und ein Zertifikat über dasselbe Bereitstellungspaket installiert werden.</span><span class="sxs-lookup"><span data-stu-id="c8b8d-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="c8b8d-113">Wenn Sie Ihr Zertifikat von MDM bereitstellen oder über den [Zertifikat-Manager](certificate-manager.md)installieren, stellen Sie sicher, dass Sie das Zertifikat im lokalen Computerspeicher bereitstellen, um auf diese Weise installierte Apps zu signieren.</span><span class="sxs-lookup"><span data-stu-id="c8b8d-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="c8b8d-114">Informationen zu den Grundlagen des Erstellens eines Bereitstellungspakets für HoloLens-Geräte finden Sie unter [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="c8b8d-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="c8b8d-115">Um eine App bereitstellen zu können, müssen Sie mit der erweiterten Bereitstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="c8b8d-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="c8b8d-116">HoloLens (1. Generation) bietet eingeschränkte Unterstützung für die Installation von Apps (**UniversalAppInstall**) mithilfe eines Bereitstellungspakets.</span><span class="sxs-lookup"><span data-stu-id="c8b8d-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="c8b8d-117">HoloLens (1. Generation)-Geräte unterstützen nur die Installation einer App über PPKG nur während der OOBE und nur bei Installationen des Benutzerkontexts.</span><span class="sxs-lookup"><span data-stu-id="c8b8d-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <span data-ttu-id="c8b8d-118">Setup</span><span class="sxs-lookup"><span data-stu-id="c8b8d-118">Setup</span></span>

<span data-ttu-id="c8b8d-119">In [Windows-Konfigurations-Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="c8b8d-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="c8b8d-120">Legen Sie "ApplicationManagement/AllowAllTrustedApps" auf "Ja" fest.</span><span class="sxs-lookup"><span data-stu-id="c8b8d-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="c8b8d-121">Siehe: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="c8b8d-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="c8b8d-122">Navigieren Sie **zu "UniversalAppInstall**  >  **UserContextAppLicense"** und geben Sie **"PackageFamilyName" ein.**</span><span class="sxs-lookup"><span data-stu-id="c8b8d-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="c8b8d-123">Siehe [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="c8b8d-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="c8b8d-124">Siehe auch: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="c8b8d-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="c8b8d-125">Sie können device Portal auf einem Gerät verwenden, auf dem Sie Ihre App bereits installiert haben.</span><span class="sxs-lookup"><span data-stu-id="c8b8d-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="c8b8d-126">Besuchen Sie die Seite "Apps", und sehen Sie sich die Zeile "PackageRelativeID" an, alle Informationen vor dem "!" Ist Ihr **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="c8b8d-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="c8b8d-127">Sie werden dann sehen, dass Sie einen neuen Abschnitt haben, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="c8b8d-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="c8b8d-128">Verwenden Sie diesen Bereich, um Ihr appx-Bündel hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="c8b8d-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="c8b8d-129">Je nachdem, ob Sie Ihre App erworben oder Ihre eigene Branchen-App erstellt haben, müssen Sie die Lizenzdatei oder das Sicherheitszertifikat hochladen.</span><span class="sxs-lookup"><span data-stu-id="c8b8d-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="c8b8d-130">For license file: navigate to **UniversalAppInstall**  >  **UserContextAppLicence** and browse to the location of your license and upload it.</span><span class="sxs-lookup"><span data-stu-id="c8b8d-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="c8b8d-131">Navigieren Sie für die Sicherheitsdatei zu **"Zertifikate",** und wählen Sie Ihr Zertifikat aus, das Sie zusammen mit Ihrem .appx-Bundle installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c8b8d-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="c8b8d-132">Stellen Sie sicher, dass Sie Ihr Projekt an einem sicheren Ort speichern.</span><span class="sxs-lookup"><span data-stu-id="c8b8d-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="c8b8d-133">Exportieren Sie **es** dann als **Bereitstellungspaket.**</span><span class="sxs-lookup"><span data-stu-id="c8b8d-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="c8b8d-134">Siehe auch: [Wenden Sie Ihr Bereitstellungspaket auf HoloLens an.](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="c8b8d-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
