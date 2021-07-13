---
title: Effiziente Nutzung der Features von Windows Holographic for Business
description: Wenn Sie ein Upgrade auf Windows Holographic for Business durchführen, bietet HoloLens zusätzliche Features, die für Unternehmen konzipiert sind.
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
ms.openlocfilehash: b5ae9b0d6859c0f916b5b906e2e9ec54cad6cbd9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635193"
---
# <a name="unlock-windows-holographic-for-business-features"></a><span data-ttu-id="80591-103">Effiziente Nutzung der Features von Windows Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="80591-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80591-104">Diese Seite gilt nur für HoloLens 1. Generation.</span><span class="sxs-lookup"><span data-stu-id="80591-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="80591-105">Microsoft HoloLens ist in der *Development Edition* verfügbar, die Windows Holographic (eine Edition von Windows 10, die für HoloLens entwickelt wurde) und in der [Commercial Suite](hololens-commercial-features.md)ausgeführt wird, die zusätzliche Features für Unternehmen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="80591-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="80591-106">Wenn Sie die Commercial Suite erwerben, erhalten Sie eine Lizenz, die Windows Holographic auf Windows Holographic for Business aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="80591-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="80591-107">Sie können diese Lizenz auf das Gerät anwenden, indem Sie entweder den [MDM-Anbieter (Mobile Device Management)](#edition-upgrade-by-using-mdm) der Organisation oder ein [Bereitstellungspaket](#edition-upgrade-by-using-a-provisioning-package)verwenden.</span><span class="sxs-lookup"><span data-stu-id="80591-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="80591-108">In Windows 10 Version 1803 können Sie überprüfen, ob die HoloLens auf die Business Edition aktualisiert wurde, indem Sie **Einstellungen**  >  **System** auswählen.</span><span class="sxs-lookup"><span data-stu-id="80591-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <a name="edition-upgrade-by-using-mdm"></a><span data-ttu-id="80591-109">Editionsupgrade mit MDM</span><span class="sxs-lookup"><span data-stu-id="80591-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="80591-110">Die Enterprise-Lizenz kann von jedem MDM-Anbieter angewendet werden, der den [WindowsLicensing-Konfigurationsdienstanbieter (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="80591-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="80591-111">Die neueste Version der Microsoft-MDM-API unterstützt den WindowsLicensing CSP.</span><span class="sxs-lookup"><span data-stu-id="80591-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="80591-112">Eine Schritt-für-Schritt-Anleitung zum Aktualisieren von HoloLens mithilfe von Microsoft Intune finden Sie unter Upgrade devices [running Windows Holographic to Windows Holographic for Business](/intune/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="80591-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="80591-113">Im Fall anderer MDM-Anbieter können die einzelnen Schritte zum Einrichten und Bereitstellen der Richtlinie abweichen.</span><span class="sxs-lookup"><span data-stu-id="80591-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <a name="edition-upgrade-by-using-a-provisioning-package"></a><span data-ttu-id="80591-114">Editionsupgrade mithilfe eines Bereitstellungspakets</span><span class="sxs-lookup"><span data-stu-id="80591-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="80591-115">Bereitstellungspakete sind Dateien, die vom Windows-Konfigurations-Designer-Tool erstellt werden und eine angegebene Konfiguration auf ein Gerät anwenden.</span><span class="sxs-lookup"><span data-stu-id="80591-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a><span data-ttu-id="80591-116">Erstellen eines Bereitstellungspakets, das ein Upgrade der Windows Holographic Edition ausführt</span><span class="sxs-lookup"><span data-stu-id="80591-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="80591-117">Erstellen Sie ein Bereitstellungspaket für HoloLens.</span><span class="sxs-lookup"><span data-stu-id="80591-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="80591-118">Wechseln Sie zu **Runtimeeinstellungen**  >  **EditionUpgrade**, und wählen Sie **EditionUpgradeWithLicense** aus.</span><span class="sxs-lookup"><span data-stu-id="80591-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Editionsupgrade mit ausgewählter Lizenzeinstellung](images/icd1.png)

1. <span data-ttu-id="80591-120">Suchen Sie die XML-Lizenzdatei, die beim Erwerb der Commercial Suite bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="80591-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="80591-121">Sie können [zusätzliche Einstellungen im Bereitstellungspaket](hololens-provisioning.md) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="80591-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="80591-122">Klicken Sie im Menü **Datei** auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="80591-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="80591-123">Lesen Sie die Warnung, dass Projektdateien vertrauliche Informationen enthalten können, und klicken Sie auf **OK.**</span><span class="sxs-lookup"><span data-stu-id="80591-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="80591-124">Wenn Sie ein Bereitstellungspaket erstellen, können Sie vertrauliche Informationen in die Projektdateien und die Bereitstellungspaketdatei (PPKG) einschließen.</span><span class="sxs-lookup"><span data-stu-id="80591-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="80591-125">Obwohl Sie die PPKG-Datei verschlüsseln können, werden die Projektdateien nicht verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="80591-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="80591-126">Sie sollten die Projektdateien an einem sicheren Speicherort speichern und die Projektdateien löschen, wenn sie nicht mehr benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="80591-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="80591-127">Wählen Sie im Menü **Exportieren** die Option **Bereitstellungspaket** aus.</span><span class="sxs-lookup"><span data-stu-id="80591-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="80591-128">Ändern Sie **Besitzer** in **IT-Administrator,** wodurch die Rangfolge dieses Bereitstellungspakets höher ist als bei anderen, die auf dieses Gerät aus verschiedenen Quellen angewendet werden, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="80591-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="80591-129">Legen Sie einen Wert für **Paketversion** fest.</span><span class="sxs-lookup"><span data-stu-id="80591-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="80591-130">Sie können Änderungen an vorhandenen Paketen vornehmen und die Versionsnummer ändern, um bereits angewendete Pakete zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="80591-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="80591-131">Wählen Sie unter **Sicherheitsdetails für das Bereitstellungspaket** auswählen die Option **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="80591-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="80591-132">Wählen Sie **Weiter** aus, um den Ausgabespeicherort anzugeben, an den das Bereitstellungspaket nach derEntstellung wechseln soll.</span><span class="sxs-lookup"><span data-stu-id="80591-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="80591-133">Standardmäßig verwendet Windows ICD den Projektordner als Ausgabespeicherort.</span><span class="sxs-lookup"><span data-stu-id="80591-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="80591-134">Optional können Sie **Durchsuchen** auswählen, um den Standardausgabespeicherort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="80591-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="80591-135">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="80591-135">Select **Next**.</span></span>

1. <span data-ttu-id="80591-136">Wählen Sie **Erstellen** aus, um mit dem Erstellen des Pakets zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="80591-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="80591-137">Auf der Buildseite werden die Projektinformationen angezeigt, und die Statusanzeige gibt den Buildstatus an.</span><span class="sxs-lookup"><span data-stu-id="80591-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="80591-138">Wenn der Build abgeschlossen ist, wählen Sie **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="80591-138">When the build completes, select **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="80591-139">Anwenden des Bereitstellungspakets auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="80591-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="80591-140">Verbinden Sie das Gerät über das USB-Kabel mit einem PC.</span><span class="sxs-lookup"><span data-stu-id="80591-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="80591-141">Starten Sie das Gerät, aber fahren Sie nicht über die **Seite "Anpassen"** der anfänglichen Einrichtung hinaus (die erste Seite mit dem blauen Feld).</span><span class="sxs-lookup"><span data-stu-id="80591-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="80591-142">Auf dem PC wird HoloLens im Datei-Explorer als Gerät angezeigt.</span><span class="sxs-lookup"><span data-stu-id="80591-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="80591-143">Wenn auf dem HoloLens Gerät Windows 10 Version 1607 oder früher ausgeführt wird, öffnen Sie den Datei-Explorer, indem Sie auf dem Gerät die Schaltflächen **"Herunterfahren"** und **"Einschalten"** kurz drücken und loslassen.</span><span class="sxs-lookup"><span data-stu-id="80591-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="80591-144">Verschieben Sie das Bereitstellungspaket (.ppkg) im Datei-Explorer per Drag & Drop zum Gerätespeicher.</span><span class="sxs-lookup"><span data-stu-id="80591-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="80591-145">Während sich HoloLens noch auf der **Seite "Anpassen"** befindet, drücken sie kurz, und lassen Sie die Schaltflächen **"Herunterfahren"** und **"Einschaltfläche"** gleichzeitig wieder los.</span><span class="sxs-lookup"><span data-stu-id="80591-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="80591-146">HoloLens fragen Sie, ob Sie dem Paket vertrauen und es anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="80591-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="80591-147">Bestätigen Sie, dass Sie dem Paket vertrauen.</span><span class="sxs-lookup"><span data-stu-id="80591-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="80591-148">Sie können erkennen, ob das Paket erfolgreich angewendet wurde oder nicht.</span><span class="sxs-lookup"><span data-stu-id="80591-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="80591-149">Wenn es nicht erfolgreich angewendet wurde, können Sie das Paket korrigieren und es erneut versuchen.</span><span class="sxs-lookup"><span data-stu-id="80591-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="80591-150">Wenn dies erfolgreich ist, fahren Sie mit der Geräteeinrichtung fort.</span><span class="sxs-lookup"><span data-stu-id="80591-150">If successful, proceed with device setup.</span></span>
