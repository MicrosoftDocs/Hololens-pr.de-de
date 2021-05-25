---
title: 'Häufige Szenarien: Sichere offline HoloLens 2'
description: Erfahren Sie, wie Sie mit der Bereitstellung für HoloLens-Geräte ein Szenario für eine sichere Offlinebereitstellung und App-Bereitstellung einrichten.
keywords: HoloLens, Verwaltung, offline, offline sicher
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397881"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="d683f-104">Häufige Szenarien: Sichere offline HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="d683f-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="d683f-105">Überblick</span><span class="sxs-lookup"><span data-stu-id="d683f-105">Overview</span></span>

<span data-ttu-id="d683f-106">Dieser Leitfaden enthält Anleitungen zum Anwenden eines Beispielbereitstellungspakets, das eine HoloLens 2 für die Verwendung in sicheren Umgebungen mit den folgenden Einschränkungen sperrt:</span><span class="sxs-lookup"><span data-stu-id="d683f-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="d683f-107">Deaktivieren Sie WLAN.</span><span class="sxs-lookup"><span data-stu-id="d683f-107">Disable WiFi.</span></span>
-   <span data-ttu-id="d683f-108">Deaktivieren Sie BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="d683f-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="d683f-109">Deaktivieren Sie Mikrofone.</span><span class="sxs-lookup"><span data-stu-id="d683f-109">Disable Microphones.</span></span>
-   <span data-ttu-id="d683f-110">Verhindert das Hinzufügen oder Entfernen von Bereitstellungspaketen.</span><span class="sxs-lookup"><span data-stu-id="d683f-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="d683f-111">Benutzer können keine der oben genannten eingeschränkten Komponenten aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d683f-111">No user can enable any of the above restricted components.</span></span>

<span data-ttu-id="d683f-112">[![Sicheres Offlineszenario ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d683f-112">[ ![Offline Secure scenario](./images/deployment-guides-revised-scenario-c-01.png) ](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

## <a name="prepare"></a><span data-ttu-id="d683f-113">Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="d683f-113">Prepare</span></span>

<span data-ttu-id="d683f-114">Windows 10 PC-Setup</span><span class="sxs-lookup"><span data-stu-id="d683f-114">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="d683f-115">[Laden Sie die neueste HoloLens 2 Betriebssystemdatei](https://aka.ms/hololens2download) direkt auf einen PC herunter.</span><span class="sxs-lookup"><span data-stu-id="d683f-115">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="d683f-116">Unterstützung für diese Konfiguration ist in Build 19041.1117 und höher enthalten.</span><span class="sxs-lookup"><span data-stu-id="d683f-116">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="d683f-117">Laden Sie das Advanced Recovery Companion(ARC)-Tool [von der Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) auf Ihren PC herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="d683f-117">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="d683f-118">Laden Sie das neueste [Windows Configuration Designer-Tool (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) von der Microsoft Store auf Ihren PC herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="d683f-118">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="d683f-119">[Laden Sie den Ordner OfflineSecureHL2_Sample mit den Projektdateien](https://aka.ms/HoloLensDocs-SecureOfflineSample) herunter, um das PPKG zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d683f-119">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="d683f-120">Bereiten Sie Ihre [Offline-Branchenanwendung für die PPKG-Bereitstellung](app-deploy-provisioning-package.md)vor.</span><span class="sxs-lookup"><span data-stu-id="d683f-120">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="d683f-121">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="d683f-121">Configure</span></span>

<span data-ttu-id="d683f-122">Erstellen eines Pakets für die sichere Konfigurationsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="d683f-122">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="d683f-123">Starten Sie das WCD-Tool auf Ihrem PC.</span><span class="sxs-lookup"><span data-stu-id="d683f-123">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="d683f-124">Wählen **Sie Datei -> Projekt öffnen aus.**</span><span class="sxs-lookup"><span data-stu-id="d683f-124">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="d683f-125">Navigieren Sie zum Speicherort des zuvor gespeicherten ordners OfflineSecureHL2_Sample, und wählen Sie: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="d683f-125">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="d683f-126">Das Projekt sollte geöffnet werden, und Sie sollten nun über eine Liste der verfügbaren Anpassungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="d683f-126">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d683f-127">![Screenshot des in WCD geöffneten Konfigurationspakets](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="d683f-127">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="d683f-128">Konfigurationen, die in diesem Bereitstellungspaket festgelegt sind:</span><span class="sxs-lookup"><span data-stu-id="d683f-128">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="d683f-129">Element</span><span class="sxs-lookup"><span data-stu-id="d683f-129">Item</span></span>                                                |     <span data-ttu-id="d683f-130">Einstellung</span><span class="sxs-lookup"><span data-stu-id="d683f-130">Setting</span></span>                       |     <span data-ttu-id="d683f-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d683f-131">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="d683f-132">Konten/Benutzer</span><span class="sxs-lookup"><span data-stu-id="d683f-132">Accounts / Users</span></span>                                    |     <span data-ttu-id="d683f-133">Lokaler Benutzername & Kennwort</span><span class="sxs-lookup"><span data-stu-id="d683f-133">Local User Name & Password</span></span>    |     <span data-ttu-id="d683f-134">Für diese Offlinegeräte müssen ein einzelner Benutzername und ein Kennwort festgelegt und von allen Benutzern des Geräts freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d683f-134">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="d683f-135">Erste Erfahrung/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="d683f-135">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="d683f-136">True</span><span class="sxs-lookup"><span data-stu-id="d683f-136">True</span></span>                          |     <span data-ttu-id="d683f-137">Überspringt die Kalibrierung nur während der anfänglichen Geräteeinrichtung.</span><span class="sxs-lookup"><span data-stu-id="d683f-137">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="d683f-138">Erste Erfahrung/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="d683f-138">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="d683f-139">True</span><span class="sxs-lookup"><span data-stu-id="d683f-139">True</span></span>                          |     <span data-ttu-id="d683f-140">Überspringt das Gerätetraining während der anfänglichen Geräteeinrichtung.</span><span class="sxs-lookup"><span data-stu-id="d683f-140">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="d683f-141">Erste Erfahrung/HoloLens/WLAN</span><span class="sxs-lookup"><span data-stu-id="d683f-141">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="d683f-142">True</span><span class="sxs-lookup"><span data-stu-id="d683f-142">True</span></span>                          |     <span data-ttu-id="d683f-143">Überspringt Wi-Fi Konfiguration während der anfänglichen Geräteeinrichtung</span><span class="sxs-lookup"><span data-stu-id="d683f-143">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="d683f-144">Policies/Connectivity/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="d683f-144">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="d683f-145">No</span><span class="sxs-lookup"><span data-stu-id="d683f-145">No</span></span>                            |     <span data-ttu-id="d683f-146">Deaktiviert Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="d683f-146">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="d683f-147">Policies/Experience/AllowCorglu</span><span class="sxs-lookup"><span data-stu-id="d683f-147">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="d683f-148">No</span><span class="sxs-lookup"><span data-stu-id="d683f-148">No</span></span>                            |     <span data-ttu-id="d683f-149">Deaktiviert Cortana (um potenzielle Probleme zu beseitigen, da die Mikrofone deaktiviert sind)</span><span class="sxs-lookup"><span data-stu-id="d683f-149">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="d683f-150">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="d683f-150">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="d683f-151">Yes</span><span class="sxs-lookup"><span data-stu-id="d683f-151">Yes</span></span>                           |     <span data-ttu-id="d683f-152">Deaktiviert das Mikrofon.</span><span class="sxs-lookup"><span data-stu-id="d683f-152">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="d683f-153">Richtlinien/Datenschutz/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="d683f-153">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="d683f-154">Verweigern erzwingen</span><span class="sxs-lookup"><span data-stu-id="d683f-154">Force deny</span></span>                    |     <span data-ttu-id="d683f-155">Verhindert, dass Apps versuchen, auf Standortdaten zuzugreifen (um potenzielle Probleme zu beseitigen, da die Standortnachverfolgung deaktiviert ist)</span><span class="sxs-lookup"><span data-stu-id="d683f-155">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="d683f-156">Richtlinien/Datenschutz/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="d683f-156">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="d683f-157">Verweigern erzwingen</span><span class="sxs-lookup"><span data-stu-id="d683f-157">Force deny</span></span>                    |     <span data-ttu-id="d683f-158">Verhindert, dass Apps versuchen, auf Mikrofone zuzugreifen (um potenzielle Probleme zu beseitigen, da die Mikrofone deaktiviert sind)</span><span class="sxs-lookup"><span data-stu-id="d683f-158">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="d683f-159">Richtlinien/Sicherheit/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="d683f-159">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="d683f-160">No</span><span class="sxs-lookup"><span data-stu-id="d683f-160">No</span></span>                            |     <span data-ttu-id="d683f-161">Verhindert das Hinzufügen von Bereitstellungspaketen, die möglicherweise versuchen, gesperrte Richtlinien außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="d683f-161">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="d683f-162">Richtlinien/Sicherheit/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="d683f-162">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="d683f-163">No</span><span class="sxs-lookup"><span data-stu-id="d683f-163">No</span></span>                            |     <span data-ttu-id="d683f-164">Verhindert, dass dieses gesperrte Bereitstellungspaket entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="d683f-164">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="d683f-165">Richtlinien/System/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="d683f-165">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="d683f-166">No</span><span class="sxs-lookup"><span data-stu-id="d683f-166">No</span></span>                            |     <span data-ttu-id="d683f-167">Verhindert, dass das Gerät versucht, Standortdaten nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="d683f-167">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="d683f-168">Richtlinien/WLAN/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="d683f-168">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="d683f-169">No</span><span class="sxs-lookup"><span data-stu-id="d683f-169">No</span></span>                            |     <span data-ttu-id="d683f-170">Deaktiviert Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="d683f-170">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="d683f-171">Wählen Sie unter Laufzeiteinstellungen die Option **Konten/Benutzer/Benutzername: Holo/Kennwort** aus.</span><span class="sxs-lookup"><span data-stu-id="d683f-171">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="d683f-172">Notieren Sie sich das Kennwort, und setzen Sie es bei Bedarf zurück.</span><span class="sxs-lookup"><span data-stu-id="d683f-172">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="d683f-173">Navigieren Sie zu UniversalAppInstall/UserContextApp, und konfigurieren Sie [die BRANCHEN-App, die](app-deploy-provisioning-package.md) Sie auf diesen Geräten bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="d683f-173">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d683f-174">![Screenshot: Hinzufügen Ihrer App in WCD](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="d683f-174">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="d683f-175">Wählen Sie nach Abschluss des Vorgangs die Schaltfläche "Exportieren" aus, und folgen Sie allen Aufforderungen, bis Das Bereitstellungspaket erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d683f-175">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d683f-176">![Screenshot: Schaltfläche "Exportieren" für dieses Paket in WCD](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="d683f-176">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="d683f-177">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="d683f-177">Deploy</span></span>

1. <span data-ttu-id="d683f-178">Schließen Sie hl2 über ein USB-Windows 10 an Ihren Windows 10-PC an.</span><span class="sxs-lookup"><span data-stu-id="d683f-178">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="d683f-179">Starten Sie das ARC-Tool, und wählen **Sie HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="d683f-179">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2 clean reflash initial screen](images/ARC2.png)

1. <span data-ttu-id="d683f-181">Wählen Sie auf dem nächsten Bildschirm **manuelle Paketauswahl aus.**</span><span class="sxs-lookup"><span data-stu-id="d683f-181">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 ARC-Infobildschirm](images/arc_device_info.png)

1. <span data-ttu-id="d683f-183">Navigieren Sie zur zuvor heruntergeladenen FFU-Datei, und wählen Sie **Öffnen aus.**</span><span class="sxs-lookup"><span data-stu-id="d683f-183">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="d683f-184">Wählen Sie auf der Seite Warnung die Option **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="d683f-184">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 ARC-Warnungsbildschirm](images/arc_warning.png)

1. <span data-ttu-id="d683f-186">Warten Sie, bis das ARC-Tool die HoloLens 2 des Betriebssystems abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="d683f-186">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="d683f-187">Nachdem das Gerät die Installation abgeschlossen und den Back-Up-Start abgeschlossen hat, navigieren Sie von Ihrem PC zum Datei-Explorer, und kopieren Sie die zuvor gespeicherte PPKG-Datei in den Geräteordner.</span><span class="sxs-lookup"><span data-stu-id="d683f-187">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d683f-188">![PPKG-Datei auf dem PC im Datei-Explorer-Fenster.](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="d683f-188">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="d683f-189">Klicken Sie auf HoloLens 2 Schaltflächenkombination, um das Bereitstellungspaket ausführen:  Tippen Sie gleichzeitig auf **Volume** herunter und Netzschalter.</span><span class="sxs-lookup"><span data-stu-id="d683f-189">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="d683f-190">Sie werden aufgefordert, das Bereitstellungspaket anzuwenden, und wählen Sie Bestätigen **aus.**</span><span class="sxs-lookup"><span data-stu-id="d683f-190">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="d683f-191">Wählen Sie nach Abschluss des Bereitstellungspakets **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="d683f-191">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="d683f-192">Sie sollten dann aufgefordert werden, sich mit dem freigegebenen lokalen Konto und Kennwort beim Gerät zu anmelden.</span><span class="sxs-lookup"><span data-stu-id="d683f-192">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="d683f-193">Verwalten</span><span class="sxs-lookup"><span data-stu-id="d683f-193">Maintain</span></span>

<span data-ttu-id="d683f-194">Bei dieser Konfiguration wird empfohlen, den oben genannten Prozess neu zu starten und das Gerät mit dem ARC-Tool neu zu starten und ein neues PPKG anzuwenden, um Updates für das Betriebssystem und/oder die Anwendung(en) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d683f-194">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
