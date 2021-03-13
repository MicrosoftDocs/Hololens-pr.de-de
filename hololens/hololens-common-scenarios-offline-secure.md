---
title: Gängige Szenarien – Offline sichere HoloLens2
description: Erfahren Sie, wie Sie ein Szenario für sichere Offlinebereitstellung und App-Bereitstellung mit Bereitstellung für HoloLens-Geräte einrichten.
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
ms.openlocfilehash: 7eb084d3de222581fd2b97eaa1c1e2812310810c
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407582"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="234d2-104">Gängige Szenarien – Offline sichere HoloLens2</span><span class="sxs-lookup"><span data-stu-id="234d2-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="234d2-105">Übersicht</span><span class="sxs-lookup"><span data-stu-id="234d2-105">Overview</span></span>

<span data-ttu-id="234d2-106">Dieses Handbuch enthält Anleitungen zum Anwenden eines Beispielbereitstellungspakets, das eine HoloLens 2 für die Verwendung in sicheren Umgebungen mit den folgenden Einschränkungen sperrt:</span><span class="sxs-lookup"><span data-stu-id="234d2-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="234d2-107">Deaktivieren Sie WLAN.</span><span class="sxs-lookup"><span data-stu-id="234d2-107">Disable WiFi.</span></span>
-   <span data-ttu-id="234d2-108">Deaktivieren Sie BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="234d2-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="234d2-109">Deaktivieren Sie Mikrofone.</span><span class="sxs-lookup"><span data-stu-id="234d2-109">Disable Microphones.</span></span>
-   <span data-ttu-id="234d2-110">Verhindert das Hinzufügen oder Entfernen von Bereitstellungspaketen.</span><span class="sxs-lookup"><span data-stu-id="234d2-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="234d2-111">Kein Benutzer kann eine der oben genannten eingeschränkten Komponenten aktivieren.</span><span class="sxs-lookup"><span data-stu-id="234d2-111">No user can enable any of the above restricted components.</span></span>

## <a name="prepare"></a><span data-ttu-id="234d2-112">Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="234d2-112">Prepare</span></span>

<span data-ttu-id="234d2-113">Windows 10 PC Setup</span><span class="sxs-lookup"><span data-stu-id="234d2-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="234d2-114">[Laden Sie die neueste HoloLens 2-Betriebssystemdatei](https://aka.ms/hololens2download) direkt auf einen PC herunter.</span><span class="sxs-lookup"><span data-stu-id="234d2-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="234d2-115">Unterstützung für diese Konfiguration ist in Build 19041.1117 und höher enthalten.</span><span class="sxs-lookup"><span data-stu-id="234d2-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="234d2-116">Herunterladen/Installieren des Advanced Recovery Companion(ARC)-Tools [aus dem Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) auf Ihren PC</span><span class="sxs-lookup"><span data-stu-id="234d2-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="234d2-117">Laden Sie das neueste [Windows Configuration Designer (WCD)-Tool aus](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) dem Microsoft Store auf Ihren PC herunter.</span><span class="sxs-lookup"><span data-stu-id="234d2-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="234d2-118">[Laden Sie den OfflineSecureHL2_Sample mit den Projektdateien herunter, um](https://aka.ms/HoloLensDocs-SecureOfflineSample) das PPKG zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="234d2-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="234d2-119">Bereiten Sie Ihre [Offline-Line-of-Business-Anwendung für die PPKG-Bereitstellung vor.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="234d2-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="234d2-120">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="234d2-120">Configure</span></span>

<span data-ttu-id="234d2-121">Erstellen eines Pakets für die Bereitstellung sicherer Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="234d2-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="234d2-122">Starten Sie das WCD-Tool auf Ihrem PC.</span><span class="sxs-lookup"><span data-stu-id="234d2-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="234d2-123">Wählen **Sie Datei -> Projekt öffnen aus.**</span><span class="sxs-lookup"><span data-stu-id="234d2-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="234d2-124">Navigieren Sie zum Speicherort des zuvor gespeicherten OfflineSecureHL2_Sample, und wählen Sie: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="234d2-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="234d2-125">Das Projekt sollte geöffnet werden, und Sie sollten nun über eine Liste der verfügbaren Anpassungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="234d2-125">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > ![Screenshot des in WCD geöffneten Konfigurationspakets](images/offline-secure-sample-wcd.png)

   <span data-ttu-id="234d2-127">In diesem Bereitstellungspaket festgelegte Konfigurationen:</span><span class="sxs-lookup"><span data-stu-id="234d2-127">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="234d2-128">Element</span><span class="sxs-lookup"><span data-stu-id="234d2-128">Item</span></span>                                                |     <span data-ttu-id="234d2-129">Einstellung</span><span class="sxs-lookup"><span data-stu-id="234d2-129">Setting</span></span>                       |     <span data-ttu-id="234d2-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="234d2-130">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="234d2-131">Konten /Benutzer</span><span class="sxs-lookup"><span data-stu-id="234d2-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="234d2-132">Local User Name & Password</span><span class="sxs-lookup"><span data-stu-id="234d2-132">Local User Name & Password</span></span>    |     <span data-ttu-id="234d2-133">Für diese Offlinegeräte müssen ein einzelner Benutzername und ein kennwort für alle Benutzer des Geräts festgelegt und freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="234d2-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="234d2-134">Erste Erfahrung / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="234d2-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="234d2-135">Wahr</span><span class="sxs-lookup"><span data-stu-id="234d2-135">True</span></span>                          |     <span data-ttu-id="234d2-136">Überspringt die Kalibrierung nur während der ersteinrichtung des Geräts</span><span class="sxs-lookup"><span data-stu-id="234d2-136">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="234d2-137">First Experience / HoloLens / SkipTraining</span><span class="sxs-lookup"><span data-stu-id="234d2-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="234d2-138">Wahr</span><span class="sxs-lookup"><span data-stu-id="234d2-138">True</span></span>                          |     <span data-ttu-id="234d2-139">Überspringt Geräteschulungen während der ersten Geräteeinrichtung</span><span class="sxs-lookup"><span data-stu-id="234d2-139">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="234d2-140">First Experience / HoloLens / WiFi</span><span class="sxs-lookup"><span data-stu-id="234d2-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="234d2-141">Wahr</span><span class="sxs-lookup"><span data-stu-id="234d2-141">True</span></span>                          |     <span data-ttu-id="234d2-142">Überspringt Wi-Fi Konfiguration während der ersten Geräteeinrichtung</span><span class="sxs-lookup"><span data-stu-id="234d2-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="234d2-143">Richtlinien/Konnektivität/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="234d2-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="234d2-144">Nein</span><span class="sxs-lookup"><span data-stu-id="234d2-144">No</span></span>                            |     <span data-ttu-id="234d2-145">Deaktiviert Bluetooth</span><span class="sxs-lookup"><span data-stu-id="234d2-145">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="234d2-146">Richtlinien/Erfahrung/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="234d2-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="234d2-147">Nein</span><span class="sxs-lookup"><span data-stu-id="234d2-147">No</span></span>                            |     <span data-ttu-id="234d2-148">Deaktiviert Cortana (um potenzielle Probleme zu vermeiden, da die Mikrofone deaktiviert sind)</span><span class="sxs-lookup"><span data-stu-id="234d2-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="234d2-149">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="234d2-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="234d2-150">Ja</span><span class="sxs-lookup"><span data-stu-id="234d2-150">Yes</span></span>                           |     <span data-ttu-id="234d2-151">Deaktiviert Mikrofon</span><span class="sxs-lookup"><span data-stu-id="234d2-151">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="234d2-152">Richtlinien/Datenschutz/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="234d2-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="234d2-153">Erzwingen des Verweigerns</span><span class="sxs-lookup"><span data-stu-id="234d2-153">Force deny</span></span>                    |     <span data-ttu-id="234d2-154">Verhindert, dass Apps versuchen, auf Standortdaten zu zugreifen (um potenzielle Probleme zu beseitigen, da die Standortverfolgung deaktiviert ist)</span><span class="sxs-lookup"><span data-stu-id="234d2-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="234d2-155">Richtlinien/Datenschutz/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="234d2-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="234d2-156">Erzwingen des Verweigerns</span><span class="sxs-lookup"><span data-stu-id="234d2-156">Force deny</span></span>                    |     <span data-ttu-id="234d2-157">Verhindert, dass Apps versuchen, auf Mikrofone zu zugreifen (um potenzielle Probleme zu beheben, da die Mikrofone deaktiviert sind)</span><span class="sxs-lookup"><span data-stu-id="234d2-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="234d2-158">Richtlinien/Sicherheit/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="234d2-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="234d2-159">Nein</span><span class="sxs-lookup"><span data-stu-id="234d2-159">No</span></span>                            |     <span data-ttu-id="234d2-160">Verhindert das Hinzufügen von Bereitstellungspaketen, die möglicherweise versuchen, gesperrte Richtlinien außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="234d2-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="234d2-161">Richtlinien/Sicherheit/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="234d2-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="234d2-162">Nein</span><span class="sxs-lookup"><span data-stu-id="234d2-162">No</span></span>                            |     <span data-ttu-id="234d2-163">Verhindert, dass dieses gesperrte Bereitstellungspaket entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="234d2-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="234d2-164">Policies/System/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="234d2-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="234d2-165">Nein</span><span class="sxs-lookup"><span data-stu-id="234d2-165">No</span></span>                            |     <span data-ttu-id="234d2-166">Verhindert, dass das Gerät versucht, Standortdaten nachverfolgt zu werden.</span><span class="sxs-lookup"><span data-stu-id="234d2-166">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="234d2-167">Policies/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="234d2-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="234d2-168">Nein</span><span class="sxs-lookup"><span data-stu-id="234d2-168">No</span></span>                            |     <span data-ttu-id="234d2-169">Deaktiviert Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="234d2-169">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="234d2-170">Wählen Sie unter Laufzeiteinstellungen **Konten / Benutzer / Benutzername: Holo / Kennwort aus.**</span><span class="sxs-lookup"><span data-stu-id="234d2-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="234d2-171">Notieren Sie sich das Kennwort, und setzen Sie es bei Bedarf zurück.</span><span class="sxs-lookup"><span data-stu-id="234d2-171">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="234d2-172">Navigieren Sie zu UniversalAppInstall /UserContextApp, und konfigurieren Sie die [Branchen-App,](app-deploy-provisioning-package.md) die Sie auf diesen Geräten bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="234d2-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Screenshot des Orts, an dem Ihre App in WCD hinzugefügt werden soll.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. <span data-ttu-id="234d2-174">Wählen Sie nach Abschluss die Schaltfläche "Exportieren" aus, und folgen Sie allen Eingabeaufforderungen, bis Das Bereitstellungspaket erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="234d2-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Screenshot der Schaltfläche Exportieren für dieses Paket in WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a><span data-ttu-id="234d2-176">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="234d2-176">Deploy</span></span>

1. <span data-ttu-id="234d2-177">Verbinden Sie das HL2 über ein #A0 mit Ihrem Windows 10-PC.</span><span class="sxs-lookup"><span data-stu-id="234d2-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="234d2-178">Starten Sie das ARC-Tool, und wählen **Sie HoloLens 2 aus.**</span><span class="sxs-lookup"><span data-stu-id="234d2-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![„Clean Reflash“ für HoloLens 2 – Startbildschirm](images/ARC2.png)

1. <span data-ttu-id="234d2-180">Wählen Sie auf dem nächsten Bildschirm **Manuelle Paketauswahl aus.**</span><span class="sxs-lookup"><span data-stu-id="234d2-180">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 ARC-Infobildschirm](images/arc_device_info.png)

1. <span data-ttu-id="234d2-182">Navigieren Sie zur zuvor heruntergeladenen FFU-Datei, und wählen Sie **Öffnen aus.**</span><span class="sxs-lookup"><span data-stu-id="234d2-182">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="234d2-183">Wählen Sie auf der Seite Warnung die Option **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="234d2-183">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 ARC-Warnbildschirm](images/arc_warning.png)

1. <span data-ttu-id="234d2-185">Warten Sie, bis das ARC-Tool die HoloLens 2-Betriebssysteminstallation abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="234d2-185">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="234d2-186">Nachdem das Gerät die Installation abgeschlossen und die Sicherungskopie gestartet hat, navigieren Sie von Ihrem PC zum Datei-Explorer, und kopieren Sie die zuvor gespeicherte PPKG-Datei in den Geräteordner.</span><span class="sxs-lookup"><span data-stu-id="234d2-186">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![PPKG-Datei auf dem PC im Datei-Explorer-Fenster.](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="234d2-188">Drücken Sie in HoloLens 2 die folgende Tastenkombination, um das Bereitstellungspaket ausführen zu können: Tippen Sie gleichzeitig auf **Volume Down** und **Power Button.**</span><span class="sxs-lookup"><span data-stu-id="234d2-188">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="234d2-189">Sie werden aufgefordert, das Bereitstellungspaket anzuwenden, wählen Sie **Bestätigen aus.**</span><span class="sxs-lookup"><span data-stu-id="234d2-189">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="234d2-190">Sobald das Bereitstellungspaket abgeschlossen ist, wählen Sie **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="234d2-190">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="234d2-191">Sie sollten dann aufgefordert werden, sich mit dem freigegebenen lokalen Konto und Kennwort beim Gerät zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="234d2-191">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="234d2-192">Warten</span><span class="sxs-lookup"><span data-stu-id="234d2-192">Maintain</span></span>

<span data-ttu-id="234d2-193">Bei dieser Konfiguration wird empfohlen, den oben beschriebenen Prozess neu zu starten und das Gerät mit dem ARC-Tool neu zu schrägen und ein neues PPKG anzuwenden, um Updates für das Betriebssystem und/oder die Anwendung(en) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="234d2-193">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
