---
title: Bereitstellungspaket
description: Erfahren Sie mehr über app packaging, provisioning, deployment und enterprise app deployment for HoloLens devices (Packen, Bereitstellen, Bereitstellen und Bereitstellen von Unternehmens-Apps für HoloLens-Geräte).
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308731"
---
# <a name="provisioning-package"></a><span data-ttu-id="541b2-104">Bereitstellungspaket</span><span class="sxs-lookup"><span data-stu-id="541b2-104">Provisioning Package</span></span>

<span data-ttu-id="541b2-105">Bereitstellungspakete können verwendet werden, um Geräte in einer Umgebung ohne Zugriff auf die Endpunktverwaltung vorzubereiten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="541b2-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="541b2-106">Sie können auch auf einem Gerät bereitgestellt werden, unabhängig von der Identität des Benutzers, dem Registrierungsstatus, während der Out-of-Box-Benutzeroberfläche (OOBE) oder durch Anwenden eines Bereitstellungspakets während des [Setups.](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="541b2-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="541b2-107">Überlegungen zu Bereitstellungspaketen:</span><span class="sxs-lookup"><span data-stu-id="541b2-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="541b2-108">Nicht öffentliche Apps</span><span class="sxs-lookup"><span data-stu-id="541b2-108">Non-Public apps</span></span>
* <span data-ttu-id="541b2-109">Nur usbseitiges Laden</span><span class="sxs-lookup"><span data-stu-id="541b2-109">USB side-load only</span></span>
* <span data-ttu-id="541b2-110">Keine automatische Aktualisierung (erfordert manuelle Updates über PPKGs)</span><span class="sxs-lookup"><span data-stu-id="541b2-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="541b2-111">Apps, die über ein Bereitstellungspaket installiert werden, müssen durch ein Zertifikat im Speicher des lokalen Computers signiert werden.</span><span class="sxs-lookup"><span data-stu-id="541b2-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="541b2-112">Bereitstellungspakete können nur Zertifikate im Gerätespeicher (lokaler Computer) installieren, daher können eine App und ein Zertifikat über dasselbe Bereitstellungspaket installiert werden.</span><span class="sxs-lookup"><span data-stu-id="541b2-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="541b2-113">Wenn Sie Ihr Zertifikat über MDM bereitstellen oder über den [Zertifikat-Manager](certificate-manager.md)installieren, stellen Sie sicher, dass Sie das Zertifikat im lokalen Computerspeicher bereitstellen, um auf diese Weise installierte Apps zu signieren.</span><span class="sxs-lookup"><span data-stu-id="541b2-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="541b2-114">Informationen zu den Grundlagen zum Erstellen eines Bereitstellungspakets für HoloLens-Geräte finden Sie unter [HoloLens-Bereitstellung.](https://docs.microsoft.com/hololens/hololens-provisioning)</span><span class="sxs-lookup"><span data-stu-id="541b2-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="541b2-115">Um eine App bereitzustellen, müssen Sie mit der erweiterten Bereitstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="541b2-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="541b2-116">HoloLens (1. Generation) bietet eingeschränkte Unterstützung für die Installation von Apps (**UniversalAppInstall**) mithilfe eines Bereitstellungspakets.</span><span class="sxs-lookup"><span data-stu-id="541b2-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="541b2-117">HoloLens-Geräte (1. Generation) unterstützen nur die Installation einer App über PPKG nur während oobe und nur mit Benutzerkontext-Installationen.</span><span class="sxs-lookup"><span data-stu-id="541b2-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="541b2-118">Setup</span><span class="sxs-lookup"><span data-stu-id="541b2-118">Setup</span></span>

<span data-ttu-id="541b2-119">Gehen [Sie im Windows-Konfigurations-Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="541b2-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="541b2-120">Legen Sie ApplicationManagement/AllowAllTrustedApps auf "Ja" fest.</span><span class="sxs-lookup"><span data-stu-id="541b2-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="541b2-121">Siehe: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="541b2-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="541b2-122">Navigieren Sie zu **UniversalAppInstall**  >  **UserContextAppLicense,** und geben Sie **PackageFamilyName ein.**</span><span class="sxs-lookup"><span data-stu-id="541b2-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="541b2-123">Weitere Informationen finden Sie unter [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="541b2-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="541b2-124">Siehe auch: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="541b2-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="541b2-125">Sie können Geräteportal auf einem Gerät verwenden, auf dem Sie Ihre App bereits installiert haben.</span><span class="sxs-lookup"><span data-stu-id="541b2-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="541b2-126">Besuchen Sie die Seite Apps, und sehen Sie sich die Zeile PackageRelativeID an, alle Informationen vor dem "!" Ist Ihr **PackageFamilyName.**</span><span class="sxs-lookup"><span data-stu-id="541b2-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="541b2-127">Sie sehen dann, dass Sie über den neuen Abschnitt **ApplicationFile** verfügen.</span><span class="sxs-lookup"><span data-stu-id="541b2-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="541b2-128">Verwenden Sie diesen Bereich, um Ihr AppX-Paket hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="541b2-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="541b2-129">Je nachdem, ob Sie Ihre App erworben oder Ihre eigene BRANCHEN-App erstellt haben, müssen Sie die Lizenzdatei oder das Sicherheitszertifikat hochladen.</span><span class="sxs-lookup"><span data-stu-id="541b2-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="541b2-130">Lizenzdatei: Navigieren Sie zu **UniversalAppInstall**  >  **UserContextAppLicence,** navigieren Sie zum Speicherort Ihrer Lizenz, und laden Sie sie hoch.</span><span class="sxs-lookup"><span data-stu-id="541b2-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="541b2-131">Navigieren Sie für die Sicherheitsdatei zu **Zertifikate,** und wählen Sie Ihr Zertifikat aus, das Sie zusammen mit Ihrem APPX-Paket installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="541b2-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="541b2-132">Stellen Sie sicher, dass Sie Ihr Projekt an einem sicheren Speicherort speichern.</span><span class="sxs-lookup"><span data-stu-id="541b2-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="541b2-133">Exportieren **Sie** es dann als **Bereitstellungspaket.**</span><span class="sxs-lookup"><span data-stu-id="541b2-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="541b2-134">Siehe auch: [Anwenden Ihres Bereitstellungspakets auf HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="541b2-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
