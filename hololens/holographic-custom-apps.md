---
title: Verwalten von benutzerdefinierten Apps für HoloLens
description: Seiten laden benutzerdefinierte apps auf HoloLens. Weitere Informationen zum Installieren und Deinstallieren von holographischen apps.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 07/01/2019
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
- HoloLens 2
ms.openlocfilehash: 12c5eedfab580be8acea48c1fc19b56c1ead08ac
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828164"
---
# <span data-ttu-id="c849f-105">Verwalten von benutzerdefinierten Apps für HoloLens</span><span class="sxs-lookup"><span data-stu-id="c849f-105">Manage custom apps for HoloLens</span></span>

<span data-ttu-id="c849f-106">HoloLens unterstützt viele vorhandene Anwendungen aus dem Microsoft Store sowie neue apps, die speziell für HoloLens entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="c849f-106">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="c849f-107">Dieser Artikel befasst sich mit benutzerdefinierten holographischen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="c849f-107">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="c849f-108">Weitere Informationen zu Store-Apps finden Sie unter [Verwalten von apps mit dem Store](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="c849f-108">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

## <span data-ttu-id="c849f-109">Installieren benutzerdefinierter apps</span><span class="sxs-lookup"><span data-stu-id="c849f-109">Install custom apps</span></span>

<span data-ttu-id="c849f-110">Sie können Ihre eigenen Anwendungen auf HoloLens installieren, indem Sie entweder das Geräte Portal verwenden oder die Apps aus Visual Studio bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c849f-110">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="c849f-111">Installieren eines Anwendungspakets mit dem Geräte Portal</span><span class="sxs-lookup"><span data-stu-id="c849f-111">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="c849f-112">Herstellen einer Verbindung vom [Geräte Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) zur Ziel HoloLens</span><span class="sxs-lookup"><span data-stu-id="c849f-112">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>
1. <span data-ttu-id="c849f-113">Navigieren Sie in der linken Navigationsleiste zur Seite " **apps** ".</span><span class="sxs-lookup"><span data-stu-id="c849f-113">In the left navigation, navigate to the **Apps** page .</span></span>
1. <span data-ttu-id="c849f-114">Navigieren Sie unter **App-Paket** zu der AppX-Datei, die Ihrer Anwendung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c849f-114">Under **App Package** browse to the .appx file that is associated with your application.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="c849f-115">Stellen Sie sicher, dass Sie auf alle zugehörigen Abhängigkeits-und Zertifikatdateien verweisen.</span><span class="sxs-lookup"><span data-stu-id="c849f-115">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="c849f-116">Wählen Sie **Gehe**zu aus.</span><span class="sxs-lookup"><span data-stu-id="c849f-116">Select **Go**.</span></span>
   ![Installieren des App-Formulars im Windows Device Portal auf Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="c849f-118">Bereitstellen von Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="c849f-118">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="c849f-119">Öffnen Sie die Visual Studio-Projektmappe (SLN-Datei) der app.</span><span class="sxs-lookup"><span data-stu-id="c849f-119">Open your app's Visual Studio solution (.sln file).</span></span>
1. <span data-ttu-id="c849f-120">Öffnen Sie die Projekt **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="c849f-120">Open the project's **Properties**.</span></span>
1. <span data-ttu-id="c849f-121">Wählen Sie die folgende Buildkonfiguration aus: **Master/x86/Remote Computer**.</span><span class="sxs-lookup"><span data-stu-id="c849f-121">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>
1. <span data-ttu-id="c849f-122">Wenn Sie **Remote Computer**auswählen:</span><span class="sxs-lookup"><span data-stu-id="c849f-122">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="c849f-123">Stellen Sie sicher, dass die Adresse auf die Wi-Fi-IP-Adresse Ihres HoloLens verweist.</span><span class="sxs-lookup"><span data-stu-id="c849f-123">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="c849f-124">Setzen Sie die Authentifizierung auf **universell (unverschlüsseltes Protokoll)**.</span><span class="sxs-lookup"><span data-stu-id="c849f-124">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
1. <span data-ttu-id="c849f-125">Erstellen Sie Ihre Lösung.</span><span class="sxs-lookup"><span data-stu-id="c849f-125">Build your solution.</span></span>
1. <span data-ttu-id="c849f-126">Wenn Sie die APP von Ihrem Entwicklungscomputer auf Ihrem HoloLens bereitstellen möchten, wählen Sie **Remote Computer**aus.</span><span class="sxs-lookup"><span data-stu-id="c849f-126">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="c849f-127">Wenn Sie bereits über einen vorhandenen Build auf der HoloLens verfügen, wählen Sie **Ja** aus, um diese neuere Version zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c849f-127">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Bereitstellung von Remote Computern für apps zu Microsoft HoloLens in Visual Studio](images/vs2015-remotedeployment.jpg)  
1. <span data-ttu-id="c849f-129">Die Anwendung wird auf Ihrem HoloLens installiert und automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="c849f-129">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="c849f-130">Nachdem Sie eine APP installiert haben, finden Sie Sie in der Liste **alle apps** (**Start**  >  **alle apps**starten).</span><span class="sxs-lookup"><span data-stu-id="c849f-130">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
