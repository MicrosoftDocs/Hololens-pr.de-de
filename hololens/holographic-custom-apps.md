---
title: Verwalten benutzerdefinierter Apps für HoloLens (1. Generation)
description: Erfahren Sie, wie Sie benutzerdefinierte holografische Apps auf HoloLens-Geräten mithilfe der Geräteportal und Visual Studio installieren, deinstallieren und querladen.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side-load, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308659"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="5ff84-104">Verwalten benutzerdefinierter Apps für HoloLens (1. Generation)</span><span class="sxs-lookup"><span data-stu-id="5ff84-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="5ff84-105">HoloLens unterstützt viele vorhandene Anwendungen aus dem Microsoft Store sowie neue Apps, die speziell für HoloLens erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5ff84-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="5ff84-106">Dieser Artikel konzentriert sich auf benutzerdefinierte holografische Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="5ff84-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="5ff84-107">Weitere Informationen zu Store-Apps finden Sie unter [Verwalten von Apps mit dem Store.](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="5ff84-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ff84-108">Die folgenden Informationen wurden für HoloLens (1. Generation) erstellt, die zu diesem Zeitpunkt auch als HoloLens Developer Edition bezeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="5ff84-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="5ff84-109">Daher war das Querladen von Apps über das Geräteportal und das Installieren von Apps über Visual Studio dann üblich.</span><span class="sxs-lookup"><span data-stu-id="5ff84-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="5ff84-110">Für Unternehmensbereitstellungen wird nicht empfohlen, den Entwicklermodus zu aktivieren, der von beiden Methoden verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5ff84-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="5ff84-111">Wenn Sie an einer sicheren App-Bereitstellungsmethode interessiert sind, lesen Sie unsere [App-Verwaltung: Übersicht](app-deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5ff84-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="5ff84-112">Wenn Sie nach einer der Entwicklermethoden für die App-Installation für HoloLens 2 Geräte suchen, finden Sie weitere Informationen unter:</span><span class="sxs-lookup"><span data-stu-id="5ff84-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="5ff84-113">Geräteportal: Installieren einer App</span><span class="sxs-lookup"><span data-stu-id="5ff84-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="5ff84-114">Verwenden von Visual Studio zum Bereitstellen und Debuggen von Apps</span><span class="sxs-lookup"><span data-stu-id="5ff84-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="5ff84-115">Installieren von benutzerdefinierten Apps</span><span class="sxs-lookup"><span data-stu-id="5ff84-115">Install custom apps</span></span>

<span data-ttu-id="5ff84-116">Sie können Ihre eigenen Anwendungen auf HoloLens installieren, indem Sie entweder die Geräteportal verwenden oder die Apps über Visual Studio bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5ff84-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="5ff84-117">Installieren eines Anwendungspakets mit dem Geräteportal</span><span class="sxs-lookup"><span data-stu-id="5ff84-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="5ff84-118">Stellen Sie eine Verbindung zwischen [Geräteportal und](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) der HoloLens-Zieldatenbank her.</span><span class="sxs-lookup"><span data-stu-id="5ff84-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="5ff84-119">Navigieren Sie im linken Navigationsbereich zur Seite **Apps.**</span><span class="sxs-lookup"><span data-stu-id="5ff84-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="5ff84-120">Navigieren Sie unter **App-Paket** zur APPX-Datei, die Ihrer Anwendung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="5ff84-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="5ff84-121">Stellen Sie sicher, dass Sie auf alle zugeordneten Abhängigkeits- und Zertifikatdateien verweisen.</span><span class="sxs-lookup"><span data-stu-id="5ff84-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="5ff84-122">Klicken Sie auf **Starten**.</span><span class="sxs-lookup"><span data-stu-id="5ff84-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5ff84-123">![Installieren des App-Formulars in Windows-Geräteportal auf Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="5ff84-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="5ff84-124">Bereitstellung über Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="5ff84-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="5ff84-125">Öffnen Sie die Projektmappe Visual Studio App (SLN-Datei).</span><span class="sxs-lookup"><span data-stu-id="5ff84-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="5ff84-126">Öffnen Sie die Eigenschaften des **Projekts.**</span><span class="sxs-lookup"><span data-stu-id="5ff84-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="5ff84-127">Wählen Sie die folgende Buildkonfiguration aus: **Master/x86/Remotecomputer**.</span><span class="sxs-lookup"><span data-stu-id="5ff84-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="5ff84-128">Wenn Sie **Remotecomputer auswählen:**</span><span class="sxs-lookup"><span data-stu-id="5ff84-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="5ff84-129">Stellen Sie sicher, dass die Adresse auf die Wi-Fi IP-Adresse Ihrer HoloLens verweist.</span><span class="sxs-lookup"><span data-stu-id="5ff84-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="5ff84-130">Legen Sie die **Authentifizierung auf Universell (unverschlüsselte Protokoll) fest.**</span><span class="sxs-lookup"><span data-stu-id="5ff84-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="5ff84-131">Erstellen Sie Ihre Lösung.</span><span class="sxs-lookup"><span data-stu-id="5ff84-131">Build your solution.</span></span>

1. <span data-ttu-id="5ff84-132">Um die App von Ihrem Entwicklungs-PC auf Ihrer HoloLens bereitzustellen, wählen Sie **Remotecomputer aus.**</span><span class="sxs-lookup"><span data-stu-id="5ff84-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="5ff84-133">Wenn Sie bereits über einen vorhandenen Build auf der HoloLens verfügen, wählen Sie **Ja aus,** um diese neuere Version zu installieren.</span><span class="sxs-lookup"><span data-stu-id="5ff84-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Remote Machine deployment for apps to Microsoft HoloLens in Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="5ff84-135">Die Anwendung wird auf Ihrer HoloLens installiert und automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="5ff84-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="5ff84-136">Nachdem Sie eine App installiert haben, finden Sie  sie in der liste Alle Apps (**Start**  >  **Alle Apps**).</span><span class="sxs-lookup"><span data-stu-id="5ff84-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
