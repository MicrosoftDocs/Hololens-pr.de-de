---
title: Verwalten von benutzerdefinierten Apps für HoloLens
description: Seiten laden benutzerdefinierte apps auf HoloLens. Weitere Informationen zum Installieren und Deinstallieren von holographischen apps.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, querladen, Side Load, Side-Load, Store, UWP, APP, install
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
ms.openlocfilehash: 67a857eb35126435f5642ee60168128300401394
ms.sourcegitcommit: cd2071c12eaabe46c829b53c22d13e21b8af5b53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "11218632"
---
# <span data-ttu-id="5e390-105">Verwalten von benutzerdefinierten Apps für HoloLens</span><span class="sxs-lookup"><span data-stu-id="5e390-105">Manage custom apps for HoloLens</span></span>

<span data-ttu-id="5e390-106">HoloLens unterstützt viele vorhandene Anwendungen aus dem Microsoft-Shop sowie neue Apps, die speziell für HoloLens erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5e390-106">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="5e390-107">Dieser Artikel befasst sich mit benutzerdefinierten holographischen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="5e390-107">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="5e390-108">Weitere Informationen zu Store-Apps finden Sie unter [Verwalten von apps mit dem Store](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="5e390-108">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e390-109">Die folgenden Informationen wurden für die HoloLens (1st Generation) erstellt, die zu diesem Zeitpunkt auch als HoloLens Developer Edition bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="5e390-109">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="5e390-110">Als solche Sideloading-Apps über das Device Portal und die Installation von apps über Visual Studio waren dann alltäglich.</span><span class="sxs-lookup"><span data-stu-id="5e390-110">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="5e390-111">Für Unternehmensbereitstellungen wird nicht empfohlen, den Entwicklermodus zu aktivieren, den diese beiden Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="5e390-111">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="5e390-112">Wenn Sie an einer sicheren App-Bereitstellungsmethode interessiert sind, lesen Sie bitte unsere [App-Verwaltung: Übersicht](app-deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5e390-112">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="5e390-113">Wenn Sie nach einer der Entwickler Methoden für die APP-Installation für HoloLens 2-Geräte suchen, lesen Sie:</span><span class="sxs-lookup"><span data-stu-id="5e390-113">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="5e390-114">Geräte Portal: Installieren einer APP</span><span class="sxs-lookup"><span data-stu-id="5e390-114">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="5e390-115">Verwenden von Visual Studio zum Bereitstellen und Debuggen von apps</span><span class="sxs-lookup"><span data-stu-id="5e390-115">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <span data-ttu-id="5e390-116">Installieren benutzerdefinierter apps</span><span class="sxs-lookup"><span data-stu-id="5e390-116">Install custom apps</span></span>

<span data-ttu-id="5e390-117">Sie können Ihre eigenen Anwendungen auf HoloLens installieren, indem Sie entweder das Geräte Portal verwenden oder die Apps aus Visual Studio bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5e390-117">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="5e390-118">Installieren eines Anwendungspakets mit dem Geräte Portal</span><span class="sxs-lookup"><span data-stu-id="5e390-118">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="5e390-119">Herstellen einer Verbindung vom [Geräte Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) zur Ziel HoloLens</span><span class="sxs-lookup"><span data-stu-id="5e390-119">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>
1. <span data-ttu-id="5e390-120">Navigieren Sie in der linken Navigationsleiste zur Seite " **apps** ".</span><span class="sxs-lookup"><span data-stu-id="5e390-120">In the left navigation, navigate to the **Apps** page .</span></span>
1. <span data-ttu-id="5e390-121">Navigieren Sie unter **App-Paket** zu der AppX-Datei, die Ihrer Anwendung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="5e390-121">Under **App Package** browse to the .appx file that is associated with your application.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="5e390-122">Stellen Sie sicher, dass Sie auf alle zugehörigen Abhängigkeits-und Zertifikatdateien verweisen.</span><span class="sxs-lookup"><span data-stu-id="5e390-122">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="5e390-123">Wählen Sie **Gehe**zu aus.</span><span class="sxs-lookup"><span data-stu-id="5e390-123">Select **Go**.</span></span>
   ![Installieren des App-Formulars im Windows Device Portal auf Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="5e390-125">Bereitstellen von Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="5e390-125">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="5e390-126">Öffnen Sie die Visual Studio-Projektmappe (SLN-Datei) der app.</span><span class="sxs-lookup"><span data-stu-id="5e390-126">Open your app's Visual Studio solution (.sln file).</span></span>
1. <span data-ttu-id="5e390-127">Öffnen Sie die Projekt **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="5e390-127">Open the project's **Properties**.</span></span>
1. <span data-ttu-id="5e390-128">Wählen Sie die folgende Buildkonfiguration aus: **Master/x86/Remote Computer**.</span><span class="sxs-lookup"><span data-stu-id="5e390-128">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>
1. <span data-ttu-id="5e390-129">Wenn Sie **Remote Computer**auswählen:</span><span class="sxs-lookup"><span data-stu-id="5e390-129">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="5e390-130">Stellen Sie sicher, dass die Adresse auf die Wi-Fi IP-Adresse Ihres HoloLens verweist.</span><span class="sxs-lookup"><span data-stu-id="5e390-130">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="5e390-131">Setzen Sie die Authentifizierung auf **universell (unverschlüsseltes Protokoll)**.</span><span class="sxs-lookup"><span data-stu-id="5e390-131">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
1. <span data-ttu-id="5e390-132">Erstellen Sie Ihre Lösung.</span><span class="sxs-lookup"><span data-stu-id="5e390-132">Build your solution.</span></span>
1. <span data-ttu-id="5e390-133">Wenn Sie die APP von Ihrem Entwicklungscomputer auf Ihrem HoloLens bereitstellen möchten, wählen Sie **Remote Computer**aus.</span><span class="sxs-lookup"><span data-stu-id="5e390-133">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="5e390-134">Wenn Sie bereits über einen vorhandenen Build auf der HoloLens verfügen, wählen Sie **Ja** aus, um diese neuere Version zu installieren.</span><span class="sxs-lookup"><span data-stu-id="5e390-134">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Bereitstellung von Remote Computern für apps zu Microsoft HoloLens in Visual Studio](images/vs2015-remotedeployment.jpg)  
1. <span data-ttu-id="5e390-136">Die Anwendung wird auf Ihrem HoloLens installiert und automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="5e390-136">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="5e390-137">Nachdem Sie eine APP installiert haben, finden Sie Sie in der Liste **alle apps** (\*\*\*\*  >  **alle apps**starten).</span><span class="sxs-lookup"><span data-stu-id="5e390-137">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
