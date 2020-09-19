---
title: Herunterladen und Installieren von apps über das HoloLens 2-App-Installationsprogramm
description: Laden und Installieren von apps über die Benutzeroberfläche
keywords: App-Verwaltung, APP, hololens, App-Installationsprogramm
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2387c0eb65efc312db4eea7118f3cca44ce6d4b6
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027470"
---
# <span data-ttu-id="472a9-104">Installieren von apps auf HoloLens 2 über das App-Installationsprogramm</span><span class="sxs-lookup"><span data-stu-id="472a9-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="472a9-105">Benutzer können jetzt Apps über AppX-Bundles jetzt installieren, ohne den Entwicklermodus aktivieren oder Device Portal verwenden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="472a9-105">Users can now install Apps via Appx Bundles now without the need to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="472a9-106">Diese Vorgehensweise ist einfach für die Installation von apps auf lokalen Geräten oder das Freigeben einer APP für eine andere Person, die mit anderen APP-Installationsmethoden auf HoloLens nicht vertraut ist.</span><span class="sxs-lookup"><span data-stu-id="472a9-106">This experience is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="472a9-107">Dieses Feature ist derzeit nur avalible in Windows Insider-Builds 19041.1377 +.</span><span class="sxs-lookup"><span data-stu-id="472a9-107">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="472a9-108">[Weitere Informationen zum Registrieren von Windows Insider-Builds](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="472a9-108">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

> [!NOTE]
> <span data-ttu-id="472a9-109">Die Projektmappenkonfiguration der APP muss entweder **Master** oder **Release** sein, da vom APP-Installationsprogramm Abhängigkeiten aus dem Store verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="472a9-109">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="472a9-110">Weitere Informationen finden Sie unter [Erstellen von App-Paketen](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="472a9-110">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

1.  <span data-ttu-id="472a9-111">Stellen Sie sicher, dass Ihr HoloLens 2-Gerät eingeschaltet ist und Sie angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="472a9-111">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="472a9-112">Navigieren Sie auf Ihrem PC zu Ihrer benutzerdefinierten APP, und kopieren Sie yourapp. appxbundle nach yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="472a9-112">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="472a9-113">Nachdem Sie Ihre Datei fertig kopiert haben, können Sie Ihr Gerät trennen und die Installation später abschließen.</span><span class="sxs-lookup"><span data-stu-id="472a9-113">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="472a9-114">Öffnen Sie auf Ihrem HoloLens 2-Gerät das **Startmenü**, wählen Sie **alle apps** aus, und starten Sie die **Datei-Explorer** -app.</span><span class="sxs-lookup"><span data-stu-id="472a9-114">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="472a9-115">Navigieren Sie zum Ordner Downloads.</span><span class="sxs-lookup"><span data-stu-id="472a9-115">Navigate to the Downloads folder.</span></span> <span data-ttu-id="472a9-116">Möglicherweise müssen Sie auf der linken Seite der APP zuerst **dieses Gerät** auswählen und dann zu Downloads navigieren.</span><span class="sxs-lookup"><span data-stu-id="472a9-116">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="472a9-117">Wählen Sie die Datei "yourapp. appxbundle" aus.</span><span class="sxs-lookup"><span data-stu-id="472a9-117">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="472a9-118">Das App-Installationsprogramm wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="472a9-118">The App Installer will launch.</span></span> <span data-ttu-id="472a9-119">Wählen Sie die Schaltfläche **Installieren** aus, um Ihre APP zu installieren.</span><span class="sxs-lookup"><span data-stu-id="472a9-119">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="472a9-120">Die installierte APP wird nach Abschluss der Installation automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="472a9-120">The installed app will automatically launch upon the completion of installing.</span></span> 

![Installieren von MRTK-Beispielen über das App-Installationsprogramm](images/hololens-app-installer-picture.jpg)

<span data-ttu-id="472a9-122">Wenn Ihre APP nicht installiert werden konnte, prüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="472a9-122">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="472a9-123">Ihre APP ist entweder ein Master-oder Release-Build.</span><span class="sxs-lookup"><span data-stu-id="472a9-123">Your app is either a Master or Release build.</span></span>
-   <span data-ttu-id="472a9-124">Sie sind [mit dem Internet verbunden](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="472a9-124">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="472a9-125">Ihre [Endpunkte für den Microsoft Store](hololens-offline.md) sind ordnungsgemäß konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="472a9-125">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  
