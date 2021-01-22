---
title: Verwalten von benutzerdefinierten Apps für HoloLens (1. Generation)
description: Erfahren Sie, wie Sie benutzerdefinierte holografische Apps auf HoloLens-Geräten mithilfe des Geräteportals und der Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: HoloLens, Querladen, Querladen, Querladen, Store, UWP, App, installieren
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
ms.sourcegitcommit: 4c6d982bee72195bef955532738711f2b00ac8be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "11296988"
---
# <span data-ttu-id="69617-104">Verwalten von benutzerdefinierten Apps für HoloLens (1. Generation)</span><span class="sxs-lookup"><span data-stu-id="69617-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="69617-105">HoloLens unterstützt viele vorhandene Anwendungen aus dem Microsoft-Shop sowie neue Apps, die speziell für HoloLens erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="69617-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="69617-106">Dieser Artikel befasst sich mit benutzerdefinierten holografischen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="69617-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="69617-107">Weitere Informationen zu Store-Apps finden Sie unter ["Verwalten von Apps mit dem Store".](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="69617-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69617-108">Die folgenden Informationen wurden für HoloLens (1. Generation) erstellt, die zu diesem Zeitpunkt auch als HoloLens Developer Edition bezeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="69617-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="69617-109">Das Querladen von Apps über das Geräteportal und das Installieren von Apps über Visual Studio waren dann üblich.</span><span class="sxs-lookup"><span data-stu-id="69617-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="69617-110">Für Unternehmensbereitstellungen wird die Aktivierung des Entwicklermodus, der von beiden Methoden verwendet wird, nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="69617-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="69617-111">Wenn Sie an einer sicheren Bereitstellungsmethode für Apps interessiert sind, lesen Sie unsere [App-Verwaltung: Übersicht](app-deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="69617-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="69617-112">Wenn Sie nach einer der Entwicklerverfahren für die Installation von Apps für HoloLens 2-Geräte suchen, lesen Sie bitte:</span><span class="sxs-lookup"><span data-stu-id="69617-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="69617-113">Geräteportal: Installieren einer App</span><span class="sxs-lookup"><span data-stu-id="69617-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="69617-114">Verwenden Visual Studio zum Bereitstellen und Debuggen von Apps</span><span class="sxs-lookup"><span data-stu-id="69617-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <span data-ttu-id="69617-115">Installieren benutzerdefinierter Apps</span><span class="sxs-lookup"><span data-stu-id="69617-115">Install custom apps</span></span>

<span data-ttu-id="69617-116">Sie können Ihre eigenen Anwendungen auf HoloLens entweder über das Geräteportal oder durch Bereitstellen der Apps von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="69617-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="69617-117">Installieren eines Anwendungspakets mit dem Geräteportal</span><span class="sxs-lookup"><span data-stu-id="69617-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="69617-118">Stellen Sie eine Verbindung vom [Geräteportal mit](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) der HoloLens-Zielwebsite fest.</span><span class="sxs-lookup"><span data-stu-id="69617-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="69617-119">Navigieren Sie im linken Navigationsbereich zur **Seite "Apps".**</span><span class="sxs-lookup"><span data-stu-id="69617-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="69617-120">Navigieren **Sie unter "App-Paket"** zu der APPX-Datei, die Ihrer Anwendung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="69617-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="69617-121">Verweisen Sie unbedingt auf alle zugeordneten Abhängigkeits- und Zertifikatdateien.</span><span class="sxs-lookup"><span data-stu-id="69617-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="69617-122">Select **Go**.</span><span class="sxs-lookup"><span data-stu-id="69617-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Installieren des App-Formulars im Windows Device Portal auf Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="69617-124">Bereitstellen von Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="69617-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="69617-125">Öffnen Sie die Visual Studio Ihrer App (SLN-Datei).</span><span class="sxs-lookup"><span data-stu-id="69617-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="69617-126">Öffnen Sie die Eigenschaften des **Projekts.**</span><span class="sxs-lookup"><span data-stu-id="69617-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="69617-127">Wählen Sie die folgende Buildkonfiguration aus: **Master/x86/Remote Machine**.</span><span class="sxs-lookup"><span data-stu-id="69617-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="69617-128">Wenn Sie **Remotecomputer auswählen:**</span><span class="sxs-lookup"><span data-stu-id="69617-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="69617-129">Stellen Sie sicher, dass die Adresse auf die Wi-Fi Ihrer HoloLens verweist.</span><span class="sxs-lookup"><span data-stu-id="69617-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="69617-130">Legen Sie die **Authentifizierung auf "Universal (Unencrypted Protocol)" (unverschlüsseltes Protokoll) festgelegt.**</span><span class="sxs-lookup"><span data-stu-id="69617-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="69617-131">Erstellen Sie Ihre Lösung.</span><span class="sxs-lookup"><span data-stu-id="69617-131">Build your solution.</span></span>

1. <span data-ttu-id="69617-132">Um die App von Ihrem Entwicklungs-PC auf Ihrer HoloLens bereitstellen möchten, wählen Sie **Remotecomputer aus.**</span><span class="sxs-lookup"><span data-stu-id="69617-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="69617-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span><span class="sxs-lookup"><span data-stu-id="69617-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Remotecomputerbereitstellung für Apps für Microsoft HoloLens in Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="69617-135">Die Anwendung wird auf Ihrer HoloLens installiert und automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="69617-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="69617-136">Nachdem Sie eine App installiert haben, finden Sie sie in der Liste **"Alle Apps"** **(Alle**  >  **Apps starten).**</span><span class="sxs-lookup"><span data-stu-id="69617-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
