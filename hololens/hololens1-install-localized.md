---
title: Installieren lokalisierter Versionen von HoloLens
description: Informationen zum Installieren der chinesischen oder japanischen Version von HoloLens
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: high
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 9ccee2e11650926a5570967f1de5f6b341a17ae6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829559"
---
# <span data-ttu-id="40e4c-103">Installieren lokalisierter Versionen von HoloLens (1. Generation)</span><span class="sxs-lookup"><span data-stu-id="40e4c-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="40e4c-104">Um zur chinesischen oder japanischen Version von HoloLens zu wechseln, müssen Sie das Windows Device Recovery Tool (WDRT) verwenden, um den Build für die Sprache auf einem PC herunterzuladen und dann auf Ihrer HoloLens zu installieren.</span><span class="sxs-lookup"><span data-stu-id="40e4c-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40e4c-105">Wenn Sie WDRT verwenden, um die chinesischen oder japanischen Builds von HoloLens zu installieren, werden vorhandene Daten wie persönliche Dateien und Einstellungen aus Ihrer HoloLens gelöscht.</span><span class="sxs-lookup"><span data-stu-id="40e4c-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="40e4c-106">Laden Sie auf Ihrem PC das [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="40e4c-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="40e4c-107">Laden Sie das Paket für die gewünschte Sprache auf Ihren PC herunter: [Chinesisch (vereinfacht](https://aka.ms/hololensdownload-ch) ) oder [Japanisch](https://aka.ms/hololensdownload-jp).</span><span class="sxs-lookup"><span data-stu-id="40e4c-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="40e4c-108">Wenn der Download abgeschlossen ist, wählen Sie **Datei-Explorer** > **Downloads** aus.</span><span class="sxs-lookup"><span data-stu-id="40e4c-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="40e4c-109">Klicken Sie mit der rechten Maustaste auf den soeben heruntergeladenen gezippten Ordner, und wählen Sie **Alle extrahieren** > **Extrahieren** aus, um die Dateien zu entpacken.</span><span class="sxs-lookup"><span data-stu-id="40e4c-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="40e4c-110">Schließen Sie Ihre HoloLens mit dem mitgelieferten Micro-USB-Kabel an Ihren PC an.</span><span class="sxs-lookup"><span data-stu-id="40e4c-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="40e4c-111">(Auch wenn Sie Ihre HoloLens mit anderen Kabeln verbunden haben, funktioniert dies am besten.)</span><span class="sxs-lookup"><span data-stu-id="40e4c-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="40e4c-112">Nachdem das Tool Ihre HoloLens automatisch erkannt hat, wählen Sie die Kachel „Microsoft HoloLens” aus.</span><span class="sxs-lookup"><span data-stu-id="40e4c-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="40e4c-113">Wählen Sie auf dem nächsten Bildschirm  **Manuelle Paketauswahl**  aus, und wählen Sie die Installationsdatei aus, die sich in dem Ordner befindet, den Sie in Schritt 4 entpackt haben.</span><span class="sxs-lookup"><span data-stu-id="40e4c-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="40e4c-114">(Suchen Sie nach einer Datei mit der Erweiterung „FFU”.)</span><span class="sxs-lookup"><span data-stu-id="40e4c-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="40e4c-115">Wählen Sie  **Software installieren** aus, und folgen Sie den Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="40e4c-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="40e4c-116">Nachdem der Build installiert wurde, wird das Einrichten der HoloLens automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="40e4c-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="40e4c-117">Schalten Sie das Gerät ein und folgen Sie den Anweisungen für die Einrichtung.</span><span class="sxs-lookup"><span data-stu-id="40e4c-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="40e4c-118">Wenn Sie mit dem Einrichten fertig sind, wechseln Sie zu **Einstellungen** > **Update und Sicherheit** > **Windows-Insider-Programm** und überprüfen Sie, ob alles so konfiguriert ist, dass Sie die neuesten Preview-Builds erhalten.</span><span class="sxs-lookup"><span data-stu-id="40e4c-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="40e4c-119">Wie bei den englischen Preview-Builds werden mit dem Windows-Insider-Programm die chinesischen und japanischen Versionen von HoloLens mit den neuesten Preview-Builds auf dem neuesten Stand gehalten.</span><span class="sxs-lookup"><span data-stu-id="40e4c-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="40e4c-120">Sie können die Einstellungs-App nicht verwenden, um die Systemsprache zwischen Englisch, Japanisch und Chinesisch zu ändern.</span><span class="sxs-lookup"><span data-stu-id="40e4c-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="40e4c-121">Das Flashen eines neuen Builds ist die einzige unterstützte Möglichkeit, die Systemsprache des Geräts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="40e4c-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="40e4c-122">Sie können zwar die Pinyin-Bildschirmtastatur zur Eingabe von vereinfachtem Chinesisch oder Japanisch verwenden, die Verwendung einer Bluetooth-Hardwaretastatur zur Eingabe von vereinfachtem Chinesisch oder Japanisch wird derzeit jedoch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="40e4c-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="40e4c-123">Bei chinesischen oder japanischen HoloLens können Sie jedoch weiterhin eine Bluetooth-Tastatur verwenden, um Englisch einzugeben (um auf eine Hardwaretastatur auf Englisch umzuschalten, drücken Sie die Taste „~”).</span><span class="sxs-lookup"><span data-stu-id="40e4c-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
