---
title: HoloLens-BitLocker-Verschlüsselung
description: Erfahren Sie, wie Sie die BitLocker-Geräteverschlüsselung aktivieren, um Dateien zu schützen, die auf Ihren HoloLens Mixed Reality-Geräten gespeichert sind.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 2929cbea826e0cc92a72550c7874995506b94257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397281"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="fdefd-103">HoloLens-BitLocker-Verschlüsselung (1. Generation)</span><span class="sxs-lookup"><span data-stu-id="fdefd-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="fdefd-104">HoloLens (1. Generation) und HoloLens 2 unterstützen beide die Geräteverschlüsselung mit BitLocker. BitLocker ist jedoch immer auf HoloLens 2 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fdefd-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="fdefd-105">Dieser Artikel unterstützt Sie beim Aktivieren und Verwalten von BitLocker auf HoloLens (1. Generation).</span><span class="sxs-lookup"><span data-stu-id="fdefd-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="fdefd-106">Auf HoloLens (1. Generation) können Sie die BitLocker-Geräteverschlüsselung manuell oder mithilfe der Verwaltung mobiler Geräte (Mobile Device Management, MDM) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fdefd-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="fdefd-107">Befolgen Sie diese Anweisungen, um die [BitLocker-Geräteverschlüsselung](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) zu aktivieren, um auf der HoloLens gespeicherte Dateien und Informationen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="fdefd-107">Follow these instructions to enable [BitLocker device encryption](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="fdefd-108">Die Geräteverschlüsselung trägt zum Schutz Ihrer Daten mithilfe der AES-CBC 128-Verschlüsselungsmethode bei, die [der EncryptionMethodByDriveType-Methode 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) im BitLocker-Konfigurationsdienstanbieter (CSP) entspricht.</span><span class="sxs-lookup"><span data-stu-id="fdefd-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="fdefd-109">Mitarbeiter, die über den richtigen Verschlüsselungsschlüssel (z. B. ein Kennwort) verfügen, können ihn entschlüsseln oder eine Datenwiederherstellung durchführen.</span><span class="sxs-lookup"><span data-stu-id="fdefd-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="fdefd-110">Aktivieren der Geräteverschlüsselung mit MDM</span><span class="sxs-lookup"><span data-stu-id="fdefd-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="fdefd-111">Sie können Ihren Mobile Geräteverwaltung(MDM)-Anbieter verwenden, um eine Richtlinie anzuwenden, die Geräteverschlüsselung erfordert.</span><span class="sxs-lookup"><span data-stu-id="fdefd-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="fdefd-112">Die zu verwendende Richtlinie ist die [Einstellung Security/RequireDeviceEncryption](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) im Richtlinien-CSP.</span><span class="sxs-lookup"><span data-stu-id="fdefd-112">The policy to use is the [Security/RequireDeviceEncryption setting](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="fdefd-113">Weitere Informationen finden Sie in den Anweisungen zum Aktivieren der Geräteverschlüsselung mithilfe von Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="fdefd-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="fdefd-114">Anweisungen für andere MDM-Tools finden Sie in der Dokumentation Ihres MDM-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="fdefd-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="fdefd-115">Wenn Ihr MDM-Anbieter einen benutzerdefinierten URI für die Geräteverschlüsselung erfordert, verwenden Sie die folgende Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="fdefd-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="fdefd-116">**Name:** Ein Name Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="fdefd-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="fdefd-117">**Beschreibung:** optional</span><span class="sxs-lookup"><span data-stu-id="fdefd-117">**Description**: optional</span></span>
- <span data-ttu-id="fdefd-118">**OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="fdefd-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="fdefd-119">**Datentyp:** integer</span><span class="sxs-lookup"><span data-stu-id="fdefd-119">**Data type**: integer</span></span>
- <span data-ttu-id="fdefd-120">**Wert**: `1`</span><span class="sxs-lookup"><span data-stu-id="fdefd-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="fdefd-121">Aktivieren der Geräteverschlüsselung mithilfe eines Bereitstellungspakets</span><span class="sxs-lookup"><span data-stu-id="fdefd-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="fdefd-122">Bereitstellungspakete sind Vom Windows-Konfigurations-Designer-Tool erstellte Dateien, die eine angegebene Konfiguration auf ein Gerät anwenden.</span><span class="sxs-lookup"><span data-stu-id="fdefd-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="fdefd-123">Erstellen eines Bereitstellungspakets, das ein Upgrade der Windows Holographic-Edition und die Verschlüsselung ermöglicht</span><span class="sxs-lookup"><span data-stu-id="fdefd-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="fdefd-124">Erstellen Sie ein Bereitstellungspaket für HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fdefd-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="fdefd-125">Wechseln Sie **zu Laufzeiteinstellungen**  >    >  **Richtliniensicherheit,** und wählen **Sie RequireDeviceEncryption aus.**</span><span class="sxs-lookup"><span data-stu-id="fdefd-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![Geräteverschlüsselungseinstellung erforderlich, die auf Ja konfiguriert ist](images/device-encryption.png)

1. <span data-ttu-id="fdefd-127">Suchen Sie die XML-Lizenzdatei, die beim Kauf der Commercial Suite bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fdefd-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="fdefd-128">Navigieren Sie zu der XML-Lizenzdatei, die beim Kauf der Commercial Suite bereitgestellt wurde, und wählen Sie diese aus.</span><span class="sxs-lookup"><span data-stu-id="fdefd-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="fdefd-129">Sie können [zusätzliche Einstellungen im Bereitstellungspaket](hololens-provisioning.md) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fdefd-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="fdefd-130">Klicken Sie im Menü **Datei** auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fdefd-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="fdefd-131">Lesen Sie die Warnung, in der erläutert wird, dass Projektdateien vertrauliche Informationen enthalten können, und klicken Sie auf **OK.**</span><span class="sxs-lookup"><span data-stu-id="fdefd-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fdefd-132">Wenn Sie ein Bereitstellungspaket erstellen, können Sie vertrauliche Informationen in die Projektdateien und die Bereitstellungspaketdatei (PPKG-Datei) einverpacken.</span><span class="sxs-lookup"><span data-stu-id="fdefd-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="fdefd-133">Obwohl Sie die PPKG-Datei verschlüsseln können, werden die Projektdateien nicht verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="fdefd-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="fdefd-134">Sie sollten die Projektdateien an einem sicheren Speicherort speichern und die Projektdateien löschen, wenn sie nicht mehr benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="fdefd-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="fdefd-135">Klicken Sie im Menü **Exportieren** auf **Bereitstellungspaket**.</span><span class="sxs-lookup"><span data-stu-id="fdefd-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="fdefd-136">Ändern **Sie Besitzer** in **IT-Administrator,** wodurch die Rangfolge dieses Bereitstellungspakets höher als die bereitstellungspakete festgelegt wird, die auf dieses Gerät aus anderen Quellen angewendet werden, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="fdefd-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="fdefd-137">Legen Sie einen Wert für **Paketversion** fest.</span><span class="sxs-lookup"><span data-stu-id="fdefd-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="fdefd-138">Sie können Änderungen an vorhandenen Paketen vornehmen und die Versionsnummer ändern, um bereits angewendete Pakete zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="fdefd-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="fdefd-139">Klicken Sie unter **Sicherheitsdetails für das Bereitstellungspaket auswählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fdefd-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="fdefd-140">Klicken Sie auf **Weiter**, um den Ausgabespeicherort anzugeben, an dem das Bereitstellungspaket nach dem Erstellen gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="fdefd-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="fdefd-141">Standardmäßig verwendet Windows ICD den Projektordner als Ausgabespeicherort.</span><span class="sxs-lookup"><span data-stu-id="fdefd-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="fdefd-142">Klicken Sie optional auf Durchsuchen , um den Standardausgabespeicherort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fdefd-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="fdefd-143">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fdefd-143">Click **Next**.</span></span>
1. <span data-ttu-id="fdefd-144">Klicken Sie auf **Erstellen** , um mit der Paketerstellung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="fdefd-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="fdefd-145">Die Projektinformationen werden auf der Buildseite angezeigt, und die Statusanzeige gibt den Buildstatus an.</span><span class="sxs-lookup"><span data-stu-id="fdefd-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="fdefd-146">Wenn der Build abgeschlossen ist, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="fdefd-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="fdefd-147">Anwenden des Bereitstellungspakets auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="fdefd-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="fdefd-148">Verbinden Sie das Gerät über USB mit einem PC,  und starten Sie das Gerät, aber fahren Sie nicht über die Anpassungsseite der anfänglichen Einrichtung hinaus (die erste Seite mit dem blauen Feld).</span><span class="sxs-lookup"><span data-stu-id="fdefd-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="fdefd-149">Drücken Sie die Tasten **Leiser** und **Ein/Aus** kurz gleichzeitig, und geben Sie sie anschließend wieder frei.</span><span class="sxs-lookup"><span data-stu-id="fdefd-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="fdefd-150">HoloLens wird im Datei-Explorer auf dem PC als Gerät angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fdefd-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="fdefd-151">Verschieben Sie das Bereitstellungspaket (.ppkg) im Datei-Explorer per Drag & Drop zum Gerätespeicher.</span><span class="sxs-lookup"><span data-stu-id="fdefd-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="fdefd-152">Drücken Sie erneut die Tasten **Leiser** und **Ein/Aus** kurz gleichzeitig, während Sie sich auf der Seite **Anpassen** befinden, und geben Sie sie anschließend wieder frei.</span><span class="sxs-lookup"><span data-stu-id="fdefd-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="fdefd-153">Das Gerät wird Sie fragen, ob Sie dem Paket vertrauen und es anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="fdefd-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="fdefd-154">Bestätigen Sie, dass Sie dem Paket vertrauen.</span><span class="sxs-lookup"><span data-stu-id="fdefd-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="fdefd-155">Sie können erkennen, ob das Paket erfolgreich angewendet wurde oder nicht.</span><span class="sxs-lookup"><span data-stu-id="fdefd-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="fdefd-156">Wenn das Paket nicht erfolgreich angewendet wurde, können Sie es korrigieren und den Vorgang wiederholen.</span><span class="sxs-lookup"><span data-stu-id="fdefd-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="fdefd-157">Wenn dies erfolgreich war, fahren Sie mit der Geräteeinrichtung fort.</span><span class="sxs-lookup"><span data-stu-id="fdefd-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="fdefd-158">Wenn das Gerät vor August 2016 erworben wurde, müssen Sie sich mit einem Microsoft-Konto beim Gerät anmelden, das neueste Betriebssystemupdate erhalten und dann das Betriebssystem zurücksetzen, um das Bereitstellungspaket anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="fdefd-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="fdefd-159">Überprüfen der Geräteverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="fdefd-159">Verify device encryption</span></span>

<span data-ttu-id="fdefd-160">Die Verschlüsselung wird auf HoloLens im Hintergrund verwendet.</span><span class="sxs-lookup"><span data-stu-id="fdefd-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="fdefd-161">So überprüfen Sie den Verschlüsselungsstatus des Geräts:</span><span class="sxs-lookup"><span data-stu-id="fdefd-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="fdefd-162">Wechseln Sie auf HoloLens zu **Settings** System About  >  **(Systemeinstellungen**  >  **über**).</span><span class="sxs-lookup"><span data-stu-id="fdefd-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="fdefd-163">**BitLocker** ist **aktiviert,** wenn das Gerät verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="fdefd-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![Bildschirm "Informationen" mit aktivierter BitLocker-Option](images/about-encryption.png)
