---
title: Effiziente Nutzung der Features von Windows Holographic for Business
description: Wenn Sie ein Upgrade auf Windows holographisch for Business durchführen, bietet HoloLens zusätzliche Features, die für Unternehmen entwickelt wurden.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829339"
---
# <span data-ttu-id="aed9a-103">Effiziente Nutzung der Features von Windows Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="aed9a-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aed9a-104">Diese Seite gilt nur für HoloLens 1st Gen.</span><span class="sxs-lookup"><span data-stu-id="aed9a-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="aed9a-105">Microsoft HoloLens steht in der *Development Edition*zur Verfügung, die Windows holographisch (eine Edition von Windows 10, die für HoloLens entwickelt wurde) und in der [kommerziellen Suite](hololens-commercial-features.md), die zusätzliche Features bietet, die für Unternehmen entwickelt wurden, ausführt.</span><span class="sxs-lookup"><span data-stu-id="aed9a-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="aed9a-106">Wenn Sie die Commercial Suite erwerben, erhalten Sie eine Lizenz, mit der Sie ein Upgrade von Windows Holographic auf Windows Holographic for Business ausführen können.</span><span class="sxs-lookup"><span data-stu-id="aed9a-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="aed9a-107">Sie können diese Lizenz auf das Gerät anwenden, indem Sie entweder den [MDM-Anbieter (Mobile Device Management)](#edition-upgrade-by-using-mdm) der Organisation oder ein [Bereitstellungspaket](#edition-upgrade-by-using-a-provisioning-package)verwenden.</span><span class="sxs-lookup"><span data-stu-id="aed9a-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="aed9a-108">In Windows 10, Version 1803, können Sie überprüfen, ob die HoloLens auf die Business Edition aktualisiert wurde, indem Sie **Einstellungen**  >  **System**auswählen.</span><span class="sxs-lookup"><span data-stu-id="aed9a-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <span data-ttu-id="aed9a-109">Editionsupgrade mithilfe von MDM</span><span class="sxs-lookup"><span data-stu-id="aed9a-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="aed9a-110">Die Enterprise-Lizenz kann von jedem MDM-Anbieter angewendet werden, der den [WindowsLicensing-Konfigurationsdienstanbieter (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aed9a-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="aed9a-111">Die neueste Version der Microsoft-MDM-API unterstützt den WindowsLicensing CSP.</span><span class="sxs-lookup"><span data-stu-id="aed9a-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="aed9a-112">Eine Schritt-für-Schritt-Anleitung zum Upgrade von HoloLens mithilfe von Microsoft InTune finden Sie unter [Aktualisieren von Geräten, auf denen Windows holographisch auf Windows holographisch für Unternehmen ausgeführt wird](https://docs.microsoft.com/intune/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="aed9a-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="aed9a-113">Im Fall anderer MDM-Anbieter können die einzelnen Schritte zum Einrichten und Bereitstellen der Richtlinie abweichen.</span><span class="sxs-lookup"><span data-stu-id="aed9a-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <span data-ttu-id="aed9a-114">Editionsupgrade mithilfe eines Bereitstellungspakets</span><span class="sxs-lookup"><span data-stu-id="aed9a-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="aed9a-115">Bereitstellungspakete sind Dateien, die vom Windows-Designer für die Konfiguration erstellt werden und eine spezifische Konfiguration auf ein Gerät anwenden.</span><span class="sxs-lookup"><span data-stu-id="aed9a-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <span data-ttu-id="aed9a-116">Erstellen eines Bereitstellungspakets, das ein Upgrade der Windows Holographic Edition ausführt</span><span class="sxs-lookup"><span data-stu-id="aed9a-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="aed9a-117">Erstellen Sie ein Bereitstellungspaket für HoloLens.</span><span class="sxs-lookup"><span data-stu-id="aed9a-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="aed9a-118">Navigieren Sie zu **Laufzeiteinstellungen** > **EditionUpgrade**, und wählen Sie **EditionUpgradeWithLicense** aus.</span><span class="sxs-lookup"><span data-stu-id="aed9a-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Editionsupgrade mit ausgewählter Lizenzeinstellung](images/icd1.png)

1. <span data-ttu-id="aed9a-120">Suchen Sie die XML-Lizenzdatei, die beim Kauf der kommerziellen Suite zur Verfügung gestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="aed9a-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="aed9a-121">Sie können [zusätzliche Einstellungen im Bereitstellungspaket](hololens-provisioning.md) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="aed9a-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="aed9a-122">Wählen Sie im Menü **Datei** die Option **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="aed9a-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="aed9a-123">Lesen Sie die Warnung, dass Projektdateien vertrauliche Informationen enthalten können, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="aed9a-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="aed9a-124">Wenn Sie ein Bereitstellungspaket erstellen, können Sie vertrauliche Informationen in die Datei "Projektdateien und Bereitstellungspaket" (ppkg) einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="aed9a-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="aed9a-125">Obwohl Sie die PPKG-Datei verschlüsseln können, werden die Projektdateien nicht verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="aed9a-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="aed9a-126">Speichern Sie die Projektdateien an einem sicheren Speicherort, und löschen Sie die Projektdateien, wenn Sie nicht mehr benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="aed9a-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="aed9a-127">Wählen Sie im Menü **Exportieren** die Option **Bereitstellungspaket**aus.</span><span class="sxs-lookup"><span data-stu-id="aed9a-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="aed9a-128">Ändern Sie den **Besitzer** in den **IT-Administrator**, wodurch die Rangfolge dieses Bereitstellungspakets höher ist als bei anderen Benutzern, die auf dieses Gerät aus unterschiedlichen Quellen angewendet wurden, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="aed9a-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="aed9a-129">Legen Sie einen Wert für **Paketversion**fest.</span><span class="sxs-lookup"><span data-stu-id="aed9a-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="aed9a-130">Sie können Änderungen an vorhandenen Paketen vornehmen und die Versionsnummer ändern, um bereits angewendete Pakete zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="aed9a-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="aed9a-131">Wählen Sie unter **Sicherheitsdetails für das Bereitstellungspaket auswählen die**Option **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="aed9a-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="aed9a-132">Wählen Sie **weiter** aus, um den Ausgabespeicherort anzugeben, an dem das Bereitstellungspaket nach dem Aufbau ablaufen soll.</span><span class="sxs-lookup"><span data-stu-id="aed9a-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="aed9a-133">Standardmäßig verwendet Windows ICD den Projektordner als Ausgabespeicherort.</span><span class="sxs-lookup"><span data-stu-id="aed9a-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="aed9a-134">Optional können Sie **Durchsuchen** auswählen, um den Standardausgabe Speicherort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="aed9a-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="aed9a-135">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="aed9a-135">Select **Next**.</span></span>

1. <span data-ttu-id="aed9a-136">Wählen Sie **Erstellen** aus, um mit dem Erstellen des Pakets zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="aed9a-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="aed9a-137">Auf der Seite "erstellen" werden die Projektinformationen angezeigt, und die Statusleiste zeigt den Buildstatus an.</span><span class="sxs-lookup"><span data-stu-id="aed9a-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="aed9a-138">Wenn der Build abgeschlossen ist, wählen Sie **Fertig stellen**aus.</span><span class="sxs-lookup"><span data-stu-id="aed9a-138">When the build completes, select **Finish**.</span></span>

### <span data-ttu-id="aed9a-139">Anwenden des Bereitstellungspakets auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="aed9a-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="aed9a-140">Schließen Sie das Gerät über das USB-Kabel an einen PC an.</span><span class="sxs-lookup"><span data-stu-id="aed9a-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="aed9a-141">Starten Sie das Gerät, aber gehen Sie nicht über die Seite " **Anpassen** " der anfänglichen Setup-Umgebung (die erste Seite mit dem blauen Feld) hinaus.</span><span class="sxs-lookup"><span data-stu-id="aed9a-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="aed9a-142">Auf dem PC wird HoloLens im Datei-Explorer als Gerät angezeigt.</span><span class="sxs-lookup"><span data-stu-id="aed9a-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="aed9a-143">Wenn auf dem HoloLens-Gerät Windows 10, Version 1607 oder früher ausgeführt wird, öffnen Sie den Datei-Explorer, indem Sie die **Lautstärke** Taste und die **Power** -Taste gleichzeitig auf dem Gerät freigeben.</span><span class="sxs-lookup"><span data-stu-id="aed9a-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="aed9a-144">Verschieben Sie das Bereitstellungspaket (.ppkg) im Datei-Explorer per Drag & Drop zum Gerätespeicher.</span><span class="sxs-lookup"><span data-stu-id="aed9a-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="aed9a-145">Während sich HoloLens noch auf der Seite " **Anpassen** " befindet, drücken Sie kurz die **Lautstärke** Taste und die **Power** -Taste gleichzeitig wieder.</span><span class="sxs-lookup"><span data-stu-id="aed9a-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="aed9a-146">HoloLens fragt Sie, ob Sie dem Paket Vertrauen und es anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="aed9a-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="aed9a-147">Bestätigen Sie, dass Sie dem Paket vertrauen.</span><span class="sxs-lookup"><span data-stu-id="aed9a-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="aed9a-148">Sie können erkennen, ob das Paket erfolgreich angewendet wurde oder nicht.</span><span class="sxs-lookup"><span data-stu-id="aed9a-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="aed9a-149">Wenn Sie nicht erfolgreich angewendet wurde, können Sie das Paket beheben und es erneut versuchen.</span><span class="sxs-lookup"><span data-stu-id="aed9a-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="aed9a-150">Wenn Sie erfolgreich sind, fahren Sie mit der Einrichtung des Geräts fort.</span><span class="sxs-lookup"><span data-stu-id="aed9a-150">If successful, proceed with device setup.</span></span>
