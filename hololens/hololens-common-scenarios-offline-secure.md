---
title: Häufige Szenarien – Offline Secure HoloLens 2
description: Eine Offline sichere Bereitstellung und App-Bereitstellung über die Bereitstellung.
keywords: HoloLens, Verwaltung, offline, Offline sicher
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
ms.openlocfilehash: d53f9ce19b020a866770b756dde6ab97b8331362
ms.sourcegitcommit: e6885d03c980b33dd0bab5c418cbd1892d5ff123
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "11080493"
---
# <span data-ttu-id="6ee08-104">Häufige Szenarien – Offline Secure HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="6ee08-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <span data-ttu-id="6ee08-105">Übersicht</span><span class="sxs-lookup"><span data-stu-id="6ee08-105">Overview</span></span>
<span data-ttu-id="6ee08-106">Dieses Handbuch enthält Anleitungen zum Anwenden eines Beispiel Bereitstellungspakets, das eine HoloLens 2 für die Verwendung in sicheren Umgebungen mit den folgenden Einschränkungen sperrt:</span><span class="sxs-lookup"><span data-stu-id="6ee08-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>
-   <span data-ttu-id="6ee08-107">WLAN deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="6ee08-107">Disable WiFi.</span></span>
-   <span data-ttu-id="6ee08-108">Deaktivieren Sie Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="6ee08-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="6ee08-109">Mikrofone deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="6ee08-109">Disable Microphones.</span></span>
-   <span data-ttu-id="6ee08-110">Verhindert das Hinzufügen oder Entfernen von Bereitstellungspaketen.</span><span class="sxs-lookup"><span data-stu-id="6ee08-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="6ee08-111">Keine der oben genannten eingeschränkten Komponenten kann von Benutzern aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="6ee08-111">No user can enable any of the above restricted components.</span></span>

## <span data-ttu-id="6ee08-112">Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="6ee08-112">Prepare</span></span> 
<span data-ttu-id="6ee08-113">Windows 10-PC-Setup</span><span class="sxs-lookup"><span data-stu-id="6ee08-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="6ee08-114">[Laden Sie die neueste HoloLens 2-Betriebssystemdatei](https://aka.ms/hololens2download) direkt auf einen PC herunter.</span><span class="sxs-lookup"><span data-stu-id="6ee08-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="6ee08-115">Die Unterstützung für diese Konfiguration ist in Build 19041,1117 und höher enthalten.</span><span class="sxs-lookup"><span data-stu-id="6ee08-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="6ee08-116">Herunterladen/Installieren des Advanced Recovery Companion (ARC)-Tools [aus dem Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) auf Ihren PC</span><span class="sxs-lookup"><span data-stu-id="6ee08-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="6ee08-117">Laden Sie das neueste Tool für [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) aus dem Microsoft Store auf Ihren PC herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="6ee08-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="6ee08-118">[Laden Sie den OfflineSecureHL2_Sample-Ordner mit den Projektdateien herunter](https://aka.ms/HoloLensDocs-SecureOfflineSample) , um den PPKG zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6ee08-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="6ee08-119">Vorbereiten der Offline [Geschäftsanwendung für die PPKG-Bereitstellung](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="6ee08-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <span data-ttu-id="6ee08-120">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="6ee08-120">Configure</span></span>
<span data-ttu-id="6ee08-121">Erstellen eines sicheren Bereitstellungspakets für die Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6ee08-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="6ee08-122">Starten Sie das WCD-Tool auf Ihrem PC.</span><span class="sxs-lookup"><span data-stu-id="6ee08-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="6ee08-123">Wählen Sie **Datei – > Projekt öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="6ee08-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="6ee08-124">Navigieren Sie zum Speicherort des zuvor gespeicherten OfflineSecureHL2_Sample Ordners, und wählen Sie Folgendes aus: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="6ee08-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="6ee08-125">Das Projekt sollte geöffnet sein, und Sie sollten nun über eine Liste der verfügbaren Anpassungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="6ee08-125">The project should open and you should now have a list of Available Customizations:</span></span> 

   > [!div class="mx-imgBorder"]
   > ![Screenshot des in WCD geöffneten Konfigurationspakets](images/offline-secure-sample-wcd.png)

<span data-ttu-id="6ee08-127">In diesem Bereitstellungspaket eingestellte Konfigurationen:</span><span class="sxs-lookup"><span data-stu-id="6ee08-127">Configurations set in this provisioning package:</span></span>

|     <span data-ttu-id="6ee08-128">Element</span><span class="sxs-lookup"><span data-stu-id="6ee08-128">Item</span></span>                                                |     <span data-ttu-id="6ee08-129">Einstellung</span><span class="sxs-lookup"><span data-stu-id="6ee08-129">Setting</span></span>                       |     <span data-ttu-id="6ee08-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ee08-130">Description</span></span>                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="6ee08-131">Konten/Benutzer</span><span class="sxs-lookup"><span data-stu-id="6ee08-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="6ee08-132">Lokaler Benutzer Name & Kennwort</span><span class="sxs-lookup"><span data-stu-id="6ee08-132">Local User Name & Password</span></span>    |     <span data-ttu-id="6ee08-133">Bei diesen Offline Geräten müssen ein einzelner Benutzername und ein Kennwort für alle Benutzer des Geräts eingerichtet und freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6ee08-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
|     <span data-ttu-id="6ee08-134">First Experience/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="6ee08-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="6ee08-135">Wahr</span><span class="sxs-lookup"><span data-stu-id="6ee08-135">True</span></span>                          |     <span data-ttu-id="6ee08-136">Überspringt die Kalibrierung nur bei der erstmaligen Einrichtung des Geräts</span><span class="sxs-lookup"><span data-stu-id="6ee08-136">Skips calibration during initial device setup only</span></span>                                                                             |
|     <span data-ttu-id="6ee08-137">First Experience/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="6ee08-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="6ee08-138">Wahr</span><span class="sxs-lookup"><span data-stu-id="6ee08-138">True</span></span>                          |     <span data-ttu-id="6ee08-139">Überspringt die Geräteschulung während des anfänglichen Geräte Setups</span><span class="sxs-lookup"><span data-stu-id="6ee08-139">Skips device training during initial device setup</span></span>                                                                              |
|     <span data-ttu-id="6ee08-140">First Experience/HoloLens/WLAN</span><span class="sxs-lookup"><span data-stu-id="6ee08-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="6ee08-141">Wahr</span><span class="sxs-lookup"><span data-stu-id="6ee08-141">True</span></span>                          |     <span data-ttu-id="6ee08-142">Überspringt die Wi-Fi-Konfiguration während der ersten Einrichtung des Geräts</span><span class="sxs-lookup"><span data-stu-id="6ee08-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
|     <span data-ttu-id="6ee08-143">Richtlinien/Konnektivität/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="6ee08-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="6ee08-144">Nein</span><span class="sxs-lookup"><span data-stu-id="6ee08-144">No</span></span>                            |     <span data-ttu-id="6ee08-145">Deaktiviert Bluetooth</span><span class="sxs-lookup"><span data-stu-id="6ee08-145">Disables Bluetooth</span></span>                                                                                                             |
|     <span data-ttu-id="6ee08-146">Richtlinien/Erfahrung/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="6ee08-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="6ee08-147">Nein</span><span class="sxs-lookup"><span data-stu-id="6ee08-147">No</span></span>                            |     <span data-ttu-id="6ee08-148">Deaktiviert Cortana (um potenzielle Probleme zu eliminieren, da die Mikrofone deaktiviert sind)</span><span class="sxs-lookup"><span data-stu-id="6ee08-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
|     <span data-ttu-id="6ee08-149">Richtlinien/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="6ee08-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="6ee08-150">Ja</span><span class="sxs-lookup"><span data-stu-id="6ee08-150">Yes</span></span>                           |     <span data-ttu-id="6ee08-151">Deaktiviert das Mikrofon</span><span class="sxs-lookup"><span data-stu-id="6ee08-151">Disables Microphone</span></span>                                                                                                            |
|     <span data-ttu-id="6ee08-152">Richtlinien/Datenschutz/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="6ee08-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="6ee08-153">Verweigern erzwingen</span><span class="sxs-lookup"><span data-stu-id="6ee08-153">Force deny</span></span>                    |     <span data-ttu-id="6ee08-154">Verhindert, dass apps auf Standortdaten zugreifen können (um potenzielle Probleme zu eliminieren, da die Standortverfolgung deaktiviert ist)</span><span class="sxs-lookup"><span data-stu-id="6ee08-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
|     <span data-ttu-id="6ee08-155">Richtlinien/Datenschutz/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="6ee08-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="6ee08-156">Verweigern erzwingen</span><span class="sxs-lookup"><span data-stu-id="6ee08-156">Force deny</span></span>                    |     <span data-ttu-id="6ee08-157">Verhindert, dass apps auf Mikrofone zugreifen können (um potenzielle Probleme zu vermeiden, da die Mikrofone deaktiviert sind)</span><span class="sxs-lookup"><span data-stu-id="6ee08-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
|     <span data-ttu-id="6ee08-158">Richtlinien/Sicherheit/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="6ee08-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="6ee08-159">Nein</span><span class="sxs-lookup"><span data-stu-id="6ee08-159">No</span></span>                            |     <span data-ttu-id="6ee08-160">Verhindert, dass alle Bereitstellungspakete hinzugefügt werden, die möglicherweise versuchen, gesperrte Richtlinien zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="6ee08-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
|     <span data-ttu-id="6ee08-161">Richtlinien/Sicherheit/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="6ee08-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="6ee08-162">Nein</span><span class="sxs-lookup"><span data-stu-id="6ee08-162">No</span></span>                            |     <span data-ttu-id="6ee08-163">Verhindert, dass Benutzer dieses gesperrte Bereitstellungspaket entfernen.</span><span class="sxs-lookup"><span data-stu-id="6ee08-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
|     <span data-ttu-id="6ee08-164">Richtlinien/System-AllowLocation</span><span class="sxs-lookup"><span data-stu-id="6ee08-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="6ee08-165">Nein</span><span class="sxs-lookup"><span data-stu-id="6ee08-165">No</span></span>                            |     <span data-ttu-id="6ee08-166">Verhindert, dass das Gerät versucht, Standortdaten zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="6ee08-166">Prevents the device from trying to track location data.</span></span>                                                                        |
|     <span data-ttu-id="6ee08-167">Richtlinien/WLAN/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="6ee08-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="6ee08-168">Nein</span><span class="sxs-lookup"><span data-stu-id="6ee08-168">No</span></span>                            |     <span data-ttu-id="6ee08-169">Deaktiviert Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="6ee08-169">Disables Wi-Fi</span></span>                                                                                                                 |

4. <span data-ttu-id="6ee08-170">Wählen Sie unter Laufzeiteinstellungen die Option **Konten/Benutzer/Benutzername: Holo/Kennwort** aus.</span><span class="sxs-lookup"><span data-stu-id="6ee08-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**</span></span> 
    - <span data-ttu-id="6ee08-171">Notieren Sie sich das Kennwort und zurücksetzen, falls gewünscht.</span><span class="sxs-lookup"><span data-stu-id="6ee08-171">Note the password and reset if desired.</span></span>
5. <span data-ttu-id="6ee08-172">Navigieren Sie zu UniversalAppInstall/UserContextApp, und [Konfigurieren Sie die Lob-APP, die](app-deploy-provisioning-package.md) Sie auf diesen Geräten bereitstellen werden.</span><span class="sxs-lookup"><span data-stu-id="6ee08-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Screenshot der Stelle, an der Ihre APP in WCD hinzugefügt werden soll.](images/offline-secure-sample-wcd-usercontextapp.png)

6. <span data-ttu-id="6ee08-174">Wenn Sie den Vorgang abgeschlossen haben, wählen Sie die Schaltfläche "Exportieren" aus, und folgen Sie allen Eingabeaufforderungen, bis Ihr Bereitstellungspaket erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="6ee08-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Screenshot der Schaltfläche "Exportieren" für dieses Paket in WCD](images/offline-secure-sample-wcd-export.png)


## <span data-ttu-id="6ee08-176">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="6ee08-176">Deploy</span></span>
1. <span data-ttu-id="6ee08-177">Verbinden Sie das HL2 mit Ihrem Windows 10-PC über ein USB-Kabel.</span><span class="sxs-lookup"><span data-stu-id="6ee08-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="6ee08-178">Starten des Bogen Tools und Auswählen von **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="6ee08-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. <span data-ttu-id="6ee08-179">Wählen Sie auf dem nächsten Bildschirm **Manuelle Paketauswahl**aus.</span><span class="sxs-lookup"><span data-stu-id="6ee08-179">On the next screen select **Manual package selection**.</span></span>
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. <span data-ttu-id="6ee08-180">Navigieren Sie zu der zuvor heruntergeladenen FFU-Datei, und wählen Sie **Öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="6ee08-180">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="6ee08-181">Klicken Sie auf der Seite Warnung auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="6ee08-181">At the Warning page select **Continue**.</span></span>

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. <span data-ttu-id="6ee08-182">Warten Sie, bis das Arc-Tool die HoloLens 2-Betriebssysteminstallation abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="6ee08-182">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="6ee08-183">Nachdem das Gerät die Installation abgeschlossen und die Wiedergabe gestartet hat, navigieren Sie von Ihrem PC zum Datei-Explorer, und kopieren Sie die zuvor gespeicherte PPKG-Datei in den Geräteordner.</span><span class="sxs-lookup"><span data-stu-id="6ee08-183">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![PPKG-Datei auf dem PC im Datei-Explorer-Fenster.](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="6ee08-185">Drücken Sie auf der HoloLens 2 die folgende Tastenkombination, um das Bereitstellungspaket auszuführen: Tippen Sie auf die Schaltfläche " **Lautstärke** **" und "Netzschalter"** gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="6ee08-185">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="6ee08-186">Sie werden aufgefordert, das Bereitstellungspaket anzuwenden, wählen Sie **bestätigen** aus.</span><span class="sxs-lookup"><span data-stu-id="6ee08-186">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="6ee08-187">Nachdem das Bereitstellungspaket abgeschlossen ist, wählen Sie **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="6ee08-187">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="6ee08-188">Sie sollten dann aufgefordert werden, sich mit dem freigegebenen lokalen Konto und Kennwort beim Gerät anzumelden.</span><span class="sxs-lookup"><span data-stu-id="6ee08-188">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <span data-ttu-id="6ee08-189">Warten</span><span class="sxs-lookup"><span data-stu-id="6ee08-189">Maintain</span></span>
<span data-ttu-id="6ee08-190">Bei dieser Konfiguration wird empfohlen, den Vorgang oben neu zu starten und das Gerät mit dem Arc-Tool erneut zu blinken und ein neues PPKG anzuwenden, um alle Updates für das Betriebssystem und/oder die Anwendung (en) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6ee08-190">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span> 

