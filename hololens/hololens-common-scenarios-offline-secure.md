---
title: Häufige Szenarien – Offline Secure HoloLens 2
description: Erfahren Sie, wie Sie ein Szenario für eine sichere Offlinebereitstellung und eine App mit Bereitstellung für HoloLens-Geräte einrichten.
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
ms.openlocfilehash: 03003995f1e63708652955e6217e506d53555c1b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283416"
---
# <span data-ttu-id="23b90-104">Häufige Szenarien – Offline Secure HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="23b90-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <span data-ttu-id="23b90-105">Übersicht</span><span class="sxs-lookup"><span data-stu-id="23b90-105">Overview</span></span>

<span data-ttu-id="23b90-106">Dieses Handbuch enthält Anleitungen zum Anwenden eines Beispielbereitstellungspakets, das eine HoloLens 2 für die Verwendung in sicheren Umgebungen mit den folgenden Einschränkungen sperrt:</span><span class="sxs-lookup"><span data-stu-id="23b90-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>
-   <span data-ttu-id="23b90-107">Deaktivieren Sie WLAN.</span><span class="sxs-lookup"><span data-stu-id="23b90-107">Disable WiFi.</span></span>
-   <span data-ttu-id="23b90-108">Deaktivieren Sie BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="23b90-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="23b90-109">Deaktivieren Sie Mikrofone.</span><span class="sxs-lookup"><span data-stu-id="23b90-109">Disable Microphones.</span></span>
-   <span data-ttu-id="23b90-110">Verhindert das Hinzufügen oder Entfernen von Bereitstellungspaketen.</span><span class="sxs-lookup"><span data-stu-id="23b90-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="23b90-111">Kein Benutzer kann eine der oben genannten eingeschränkten Komponenten aktivieren.</span><span class="sxs-lookup"><span data-stu-id="23b90-111">No user can enable any of the above restricted components.</span></span>

## <span data-ttu-id="23b90-112">Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="23b90-112">Prepare</span></span>

<span data-ttu-id="23b90-113">Windows 10-PC-Setup</span><span class="sxs-lookup"><span data-stu-id="23b90-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="23b90-114">[Laden Sie die neueste HoloLens 2-Betriebssystemdatei](https://aka.ms/hololens2download) direkt auf einen PC herunter.</span><span class="sxs-lookup"><span data-stu-id="23b90-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="23b90-115">Unterstützung für diese Konfiguration ist in Build 19041.1117 und höher enthalten.</span><span class="sxs-lookup"><span data-stu-id="23b90-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="23b90-116">Herunterladen/Installieren des Advanced Recovery Companion(ARC)-Tools [aus dem Microsoft Store auf](https://www.microsoft.com/store/productId/9P74Z35SFRS8) Ihren PC</span><span class="sxs-lookup"><span data-stu-id="23b90-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="23b90-117">Laden Sie das neueste [Windows Configuration Designer (WCD)-Tool aus](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) dem Microsoft Store auf Ihren PC herunter bzw. installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="23b90-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="23b90-118">[Laden Sie den OfflineSecureHL2_Sample mit den Projektdateien herunter,](https://aka.ms/HoloLensDocs-SecureOfflineSample) um die PPKG zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="23b90-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="23b90-119">Bereiten Sie Ihre [Offlineanwendung für die Bereitstellung von PPKG vor.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="23b90-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <span data-ttu-id="23b90-120">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="23b90-120">Configure</span></span>

<span data-ttu-id="23b90-121">Erstellen eines Bereitstellungspakets für die sichere Konfiguration</span><span class="sxs-lookup"><span data-stu-id="23b90-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="23b90-122">Starten Sie das Tool WCD auf Ihrem PC.</span><span class="sxs-lookup"><span data-stu-id="23b90-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="23b90-123">Select **File -> Open project**.</span><span class="sxs-lookup"><span data-stu-id="23b90-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="23b90-124">Navigieren Sie zum Speicherort des zuvor gespeicherten ordners OfflineSecureHL2_Sample, und wählen Sie: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="23b90-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="23b90-125">Das Projekt sollte geöffnet werden, und Sie sollten nun über eine Liste der verfügbaren Anpassungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="23b90-125">The project should open and you should now have a list of Available Customizations:</span></span> 

   > [!div class="mx-imgBorder"]
   > ![Screenshot des in WCD geöffneten Konfigurationspakets](images/offline-secure-sample-wcd.png)

<span data-ttu-id="23b90-127">Konfigurationen, die in diesem Bereitstellungspaket festgelegt sind:</span><span class="sxs-lookup"><span data-stu-id="23b90-127">Configurations set in this provisioning package:</span></span>

|     <span data-ttu-id="23b90-128">Element</span><span class="sxs-lookup"><span data-stu-id="23b90-128">Item</span></span>                                                |     <span data-ttu-id="23b90-129">Einstellung</span><span class="sxs-lookup"><span data-stu-id="23b90-129">Setting</span></span>                       |     <span data-ttu-id="23b90-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23b90-130">Description</span></span>                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="23b90-131">Konten/Benutzer</span><span class="sxs-lookup"><span data-stu-id="23b90-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="23b90-132">Lokales Kennwort für & Benutzernamen</span><span class="sxs-lookup"><span data-stu-id="23b90-132">Local User Name & Password</span></span>    |     <span data-ttu-id="23b90-133">Für diese Offlinegeräte müssen ein einzelner Benutzername und ein Kennwort festgelegt und von allen Benutzern des Geräts freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="23b90-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
|     <span data-ttu-id="23b90-134">First Experience / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="23b90-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="23b90-135">Wahr</span><span class="sxs-lookup"><span data-stu-id="23b90-135">True</span></span>                          |     <span data-ttu-id="23b90-136">Überspringt die Kalibrierung nur während der ersteinrichtung des Geräts</span><span class="sxs-lookup"><span data-stu-id="23b90-136">Skips calibration during initial device setup only</span></span>                                                                             |
|     <span data-ttu-id="23b90-137">First Experience / HoloLens / SkipTraining</span><span class="sxs-lookup"><span data-stu-id="23b90-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="23b90-138">Wahr</span><span class="sxs-lookup"><span data-stu-id="23b90-138">True</span></span>                          |     <span data-ttu-id="23b90-139">Überspringt Geräteschulungen während der ersteinrichtung des Geräts</span><span class="sxs-lookup"><span data-stu-id="23b90-139">Skips device training during initial device setup</span></span>                                                                              |
|     <span data-ttu-id="23b90-140">First Experience / HoloLens / WiFi</span><span class="sxs-lookup"><span data-stu-id="23b90-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="23b90-141">Wahr</span><span class="sxs-lookup"><span data-stu-id="23b90-141">True</span></span>                          |     <span data-ttu-id="23b90-142">Überspringt Wi-Fi Konfiguration während der ersteinrichtung des Geräts</span><span class="sxs-lookup"><span data-stu-id="23b90-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
|     <span data-ttu-id="23b90-143">Policies/Connectivity/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="23b90-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="23b90-144">Nein</span><span class="sxs-lookup"><span data-stu-id="23b90-144">No</span></span>                            |     <span data-ttu-id="23b90-145">Deaktiviert Bluetooth</span><span class="sxs-lookup"><span data-stu-id="23b90-145">Disables Bluetooth</span></span>                                                                                                             |
|     <span data-ttu-id="23b90-146">Richtlinien/Erfahrung/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="23b90-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="23b90-147">Nein</span><span class="sxs-lookup"><span data-stu-id="23b90-147">No</span></span>                            |     <span data-ttu-id="23b90-148">Deaktiviert Cortana (um potenzielle Probleme zu vermeiden, da die Mikrofone deaktiviert sind)</span><span class="sxs-lookup"><span data-stu-id="23b90-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
|     <span data-ttu-id="23b90-149">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="23b90-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="23b90-150">Ja</span><span class="sxs-lookup"><span data-stu-id="23b90-150">Yes</span></span>                           |     <span data-ttu-id="23b90-151">Deaktiviert mikrofon</span><span class="sxs-lookup"><span data-stu-id="23b90-151">Disables Microphone</span></span>                                                                                                            |
|     <span data-ttu-id="23b90-152">Richtlinien/Datenschutz/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="23b90-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="23b90-153">Verweigern erzwingen</span><span class="sxs-lookup"><span data-stu-id="23b90-153">Force deny</span></span>                    |     <span data-ttu-id="23b90-154">Verhindert, dass Apps versuchen, auf Standortdaten zu zugreifen (um potenzielle Probleme zu beseitigen, da die Standortverfolgung deaktiviert ist)</span><span class="sxs-lookup"><span data-stu-id="23b90-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
|     <span data-ttu-id="23b90-155">Richtlinien/Datenschutz/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="23b90-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="23b90-156">Verweigern erzwingen</span><span class="sxs-lookup"><span data-stu-id="23b90-156">Force deny</span></span>                    |     <span data-ttu-id="23b90-157">Verhindert, dass Apps versuchen, auf Mikrofone zu zugreifen (um potenzielle Probleme zu beseitigen, da die Mikrofone deaktiviert sind)</span><span class="sxs-lookup"><span data-stu-id="23b90-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
|     <span data-ttu-id="23b90-158">Richtlinien/Sicherheit/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="23b90-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="23b90-159">Nein</span><span class="sxs-lookup"><span data-stu-id="23b90-159">No</span></span>                            |     <span data-ttu-id="23b90-160">Verhindert das Hinzufügen von Bereitstellungspaketen, die möglicherweise versuchen, gesperrte Richtlinien außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="23b90-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
|     <span data-ttu-id="23b90-161">Richtlinien/Sicherheit/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="23b90-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="23b90-162">Nein</span><span class="sxs-lookup"><span data-stu-id="23b90-162">No</span></span>                            |     <span data-ttu-id="23b90-163">Verhindert, dass dieses gesperrte Bereitstellungspaket entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="23b90-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
|     <span data-ttu-id="23b90-164">Richtlinien/System/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="23b90-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="23b90-165">Nein</span><span class="sxs-lookup"><span data-stu-id="23b90-165">No</span></span>                            |     <span data-ttu-id="23b90-166">Verhindert, dass das Gerät versucht, Standortdaten nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="23b90-166">Prevents the device from trying to track location data.</span></span>                                                                        |
|     <span data-ttu-id="23b90-167">Richtlinien/WIFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="23b90-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="23b90-168">Nein</span><span class="sxs-lookup"><span data-stu-id="23b90-168">No</span></span>                            |     <span data-ttu-id="23b90-169">Deaktiviert Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="23b90-169">Disables Wi-Fi</span></span>                                                                                                                 |

4. <span data-ttu-id="23b90-170">Wählen Sie unter Laufzeiteinstellungen **"Konten/Benutzer/Benutzername: Holo/Kennwort" aus.**</span><span class="sxs-lookup"><span data-stu-id="23b90-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**</span></span> 
    - <span data-ttu-id="23b90-171">Notieren Sie sich das Kennwort, und setzen Sie es bei Bedarf zurück.</span><span class="sxs-lookup"><span data-stu-id="23b90-171">Note the password and reset if desired.</span></span>
5. <span data-ttu-id="23b90-172">Navigieren Sie zu "UniversalAppInstall/UserContextApp", und konfigurieren Sie die [Branchen-App,](app-deploy-provisioning-package.md) die Sie auf diesen Geräten bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="23b90-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp.png)

6. <span data-ttu-id="23b90-174">Wählen Sie nach Abschluss des Vorgangs die Schaltfläche "Exportieren" aus, und befolgen Sie alle Eingabeaufforderungen, bis das Bereitstellungspaket erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="23b90-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Screenshot der Schaltfläche "Exportieren" für dieses Paket in WCD.](images/offline-secure-sample-wcd-export.png)


## <span data-ttu-id="23b90-176">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="23b90-176">Deploy</span></span>

1. <span data-ttu-id="23b90-177">Schließen Sie das HL2 über ein #A0 an Ihren Windows 10-PC an.</span><span class="sxs-lookup"><span data-stu-id="23b90-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="23b90-178">Starten Sie das ARC-Tool, und wählen **Sie HoloLens 2 aus.**</span><span class="sxs-lookup"><span data-stu-id="23b90-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. <span data-ttu-id="23b90-179">Wählen Sie auf dem nächsten Bildschirm manuelle **Paketauswahl aus.**</span><span class="sxs-lookup"><span data-stu-id="23b90-179">On the next screen select **Manual package selection**.</span></span>
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. <span data-ttu-id="23b90-180">Navigieren Sie zur zuvor heruntergeladenen FFU-Datei, und wählen Sie **"Öffnen" aus.**</span><span class="sxs-lookup"><span data-stu-id="23b90-180">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="23b90-181">Wählen Sie auf der Warnseite **"Weiter" aus.**</span><span class="sxs-lookup"><span data-stu-id="23b90-181">At the Warning page select **Continue**.</span></span>

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. <span data-ttu-id="23b90-182">Warten Sie, bis das Tool ARC die Installation des HoloLens 2-Betriebssystems abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="23b90-182">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="23b90-183">Sobald das Gerät die Installation abgeschlossen und die Installation gestartet hat, navigieren Sie vom PC zum Datei-Explorer, und kopieren Sie die zuvor gespeicherte PPKG-Datei in den Geräteordner.</span><span class="sxs-lookup"><span data-stu-id="23b90-183">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![DATEI "PPKG" auf dem PC im Fenster "Datei-Explorer".](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="23b90-185">Drücken Sie auf HoloLens 2 die folgende Tastenkombination, \*\*\*\* um das \*\*\*\* Bereitstellungspaket ausführen zu können: Tippen Sie gleichzeitig auf "Lautstärke" und "Netzschalter".</span><span class="sxs-lookup"><span data-stu-id="23b90-185">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="23b90-186">Sie werden aufgefordert, das Bereitstellungspaket anzuwenden. Wählen Sie **"Bestätigen" aus.**</span><span class="sxs-lookup"><span data-stu-id="23b90-186">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="23b90-187">Sobald das Bereitstellungspaket abgeschlossen ist, wählen Sie **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="23b90-187">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="23b90-188">Sie sollten dann aufgefordert werden, sich mit dem freigegebenen lokalen Konto und Kennwort beim Gerät zu anmelden.</span><span class="sxs-lookup"><span data-stu-id="23b90-188">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <span data-ttu-id="23b90-189">Warten</span><span class="sxs-lookup"><span data-stu-id="23b90-189">Maintain</span></span>

<span data-ttu-id="23b90-190">Bei dieser Konfiguration wird empfohlen, den obigen Prozess neu zu starten und das Gerät mit dem Tool ARC neu zu schrägen und eine neue PPKG anzuwenden, um Aktualisierungen des Betriebssystems und/oder der Anwendung(en) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="23b90-190">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span> 

