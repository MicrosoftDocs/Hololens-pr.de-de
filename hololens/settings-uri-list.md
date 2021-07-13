---
title: Sichtbarkeit von Seiteneinstellungen
description: Bleiben Sie mit unserer Liste der unterstützten URIs für PageVisibilityList und Guide auf Mixed-Reality-HoloLens-Geräten auf dem Laufenden.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: HoloLens, HoloLens 2, zugewiesener Zugriff, Kiosk, Einstellungsseite
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924331"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="7d1cd-104">Sichtbarkeit von Seiteneinstellungen</span><span class="sxs-lookup"><span data-stu-id="7d1cd-104">Page Settings Visibility</span></span>

<span data-ttu-id="7d1cd-105">Eine der verwaltbaren Funktionen für HoloLens Geräte ist die Verwendung der [Richtlinie Einstellungen/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) um die Seiten einzuschränken, die in der Einstellungen-App angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="7d1cd-106">Die PageVisibilityList ist eine Richtlinie, die es IT-Administratoren ermöglicht, entweder zu verhindern, dass bestimmte Seiten in der Systemeinstellungen-App sichtbar oder zugänglich sind oder Sie können das für alle Seiten tun, mit Ausnahme der angegebenen Seiten.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="7d1cd-107">Diese Funktion ist nur in [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) oder höher, für HoloLens 2-Geräte geeignet.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="7d1cd-108">Stellen Sie bitte sicher, dass die Geräte, für die Sie diese Funktion verwenden möchten, aktualisiert sind.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-108">Please ensure devices you intend to use this for are updated.</span></span>

<span data-ttu-id="7d1cd-109">Das folgende Beispiel zeigt eine Richtlinie, die nur Zugriff auf die Seiten „Über“ und „Bluetooth“ ermöglichen würde, die jeweils über URI „ms-settings:network-wifi“ und „ms-settings:bluetooth“ verfügen:</span><span class="sxs-lookup"><span data-stu-id="7d1cd-109">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="7d1cd-110">So legen Sie dies über ein Bereitstellungspaket fest:</span><span class="sxs-lookup"><span data-stu-id="7d1cd-110">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="7d1cd-111">Während Sie Ihr Paket im Windows Configuration Designer erstellen, navigieren Sie zu **Richtlinien > Einstellungen > PageVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="7d1cd-111">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="7d1cd-112">Geben Sie die folgende Zeichenfolge ein: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="7d1cd-112">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="7d1cd-113">Exportieren Sie Ihr Bereitstellungspaket.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-113">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="7d1cd-114">Wenden Sie das Paket auf Ihr Gerät an.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-114">Apply the package to your device.</span></span>
<span data-ttu-id="7d1cd-115">Ausführliche Informationen zum Erstellen und Anwenden eines Bereitstellungspakets finden Sie auf [dieser Seite](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="7d1cd-115">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="7d1cd-116">Dies kann über Intune mit OMA-URI durchgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="7d1cd-116">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="7d1cd-117">Eine **Benutzerdefinierte Richtlinie** erstellen.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-117">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="7d1cd-118">Verwenden Sie beim Festlegen des OMA-URI die Zeichenfolge: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="7d1cd-118">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="7d1cd-119">Wählen Sie bei der Datenauswahl: **Zeichenfolge**</span><span class="sxs-lookup"><span data-stu-id="7d1cd-119">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="7d1cd-120">Verwenden Sie beim Eingeben des Werts: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="7d1cd-120">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="7d1cd-121">Stellen Sie sicher, dass die benutzerdefinierte Gerätekonfiguration einer Gruppe zugeordnet wird, zu der das Gerät gehören soll.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-121">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="7d1cd-122">Weitere Informationen zu Intune-Gruppen und Gerätekonfigurationen finden Sie unter [HoloLens MDM-Konfiguration](hololens-mdm-configure.md).</span><span class="sxs-lookup"><span data-stu-id="7d1cd-122">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="7d1cd-123">Unabhängig von der gewählten Methode sollte Ihr Gerät jetzt die Änderungen erhalten, und den Benutzern wird die folgende Einstellungen-App angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-123">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Screenshot der Nutzungszeit, die in der Einstellungen-App geändert werden](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="7d1cd-125">Um die Einstellungen-App-Seiten so zu konfigurieren, dass Ihre eigene Auswahl von Seiten ein- oder ausgeblendet wird, sehen Sie sich die Einstellungen-URIs an, die auf HoloLens verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-125">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="7d1cd-126">Einstellungen-URIs</span><span class="sxs-lookup"><span data-stu-id="7d1cd-126">Settings URIs</span></span>

<span data-ttu-id="7d1cd-127">HoloLens-Geräte und Windows 10-Geräte weisen in der App „Einstellungen“ eine unterschiedliche Seitenauswahl auf.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-127">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="7d1cd-128">Auf dieser Seite finden Sie nur die auf HoloLens vorhandenen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-128">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="7d1cd-129">Konten</span><span class="sxs-lookup"><span data-stu-id="7d1cd-129">Accounts</span></span>
| <span data-ttu-id="7d1cd-130">Seite "Einstellungen"</span><span class="sxs-lookup"><span data-stu-id="7d1cd-130">Settings page</span></span>           | <span data-ttu-id="7d1cd-131">URI</span><span class="sxs-lookup"><span data-stu-id="7d1cd-131">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="7d1cd-132">Auf Arbeits- oder Schulkonto zugreifen</span><span class="sxs-lookup"><span data-stu-id="7d1cd-132">Access work or school</span></span> | `ms-settings:workplace`                         |
| <span data-ttu-id="7d1cd-133">Iris-Registrierung</span><span class="sxs-lookup"><span data-stu-id="7d1cd-133">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="7d1cd-134">Anmeldeoptionen</span><span class="sxs-lookup"><span data-stu-id="7d1cd-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="7d1cd-135">Apps</span><span class="sxs-lookup"><span data-stu-id="7d1cd-135">Apps</span></span>
| <span data-ttu-id="7d1cd-136">Seite "Einstellungen"</span><span class="sxs-lookup"><span data-stu-id="7d1cd-136">Settings page</span></span> | <span data-ttu-id="7d1cd-137">URI</span><span class="sxs-lookup"><span data-stu-id="7d1cd-137">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="7d1cd-138">Apps & Funktionen<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-138">Apps & features<sup>2</sup></span></span>     | `ms-settings:appsfeatures` <br> |
| <span data-ttu-id="7d1cd-139">Apps & Funktionen > Erweiterte Optionen <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-139">Apps & features > Advanced Options <sup>2</sup></span></span>     | `ms-settings::appsfeatures-app` <br> |
| <span data-ttu-id="7d1cd-140">Apps & Funktionen > Offline Azure Maps<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-140">Apps & features > Offline Maps <sup>2</sup></span></span>     | `ms-settings:maps-maps` <br> |
| <span data-ttu-id="7d1cd-141">Apps & Funktionen > Offline Azure Maps > Download Azure Maps <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-141">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="7d1cd-142">Geräte</span><span class="sxs-lookup"><span data-stu-id="7d1cd-142">Devices</span></span>
| <span data-ttu-id="7d1cd-143">Seite "Einstellungen"</span><span class="sxs-lookup"><span data-stu-id="7d1cd-143">Settings page</span></span> | <span data-ttu-id="7d1cd-144">URI</span><span class="sxs-lookup"><span data-stu-id="7d1cd-144">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="7d1cd-145">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="7d1cd-145">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| <span data-ttu-id="7d1cd-146">Maus <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-146">Mouse <sup>2</sup></span></span>      | `ms-settings:mouse` <br>  |
| <span data-ttu-id="7d1cd-147">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-147">USB <sup>2</sup></span></span>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="7d1cd-148">Datenschutz</span><span class="sxs-lookup"><span data-stu-id="7d1cd-148">Privacy</span></span>
| <span data-ttu-id="7d1cd-149">Seite "Einstellungen"</span><span class="sxs-lookup"><span data-stu-id="7d1cd-149">Settings page</span></span>            | <span data-ttu-id="7d1cd-150">URI</span><span class="sxs-lookup"><span data-stu-id="7d1cd-150">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="7d1cd-151">Kontoinformationen</span><span class="sxs-lookup"><span data-stu-id="7d1cd-151">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="7d1cd-152">App-Diagnose</span><span class="sxs-lookup"><span data-stu-id="7d1cd-152">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="7d1cd-153">Hintergrund-Apps</span><span class="sxs-lookup"><span data-stu-id="7d1cd-153">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="7d1cd-154">Kalender</span><span class="sxs-lookup"><span data-stu-id="7d1cd-154">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="7d1cd-155">Anrufliste</span><span class="sxs-lookup"><span data-stu-id="7d1cd-155">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="7d1cd-156">Kamera</span><span class="sxs-lookup"><span data-stu-id="7d1cd-156">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |
| <span data-ttu-id="7d1cd-157">Kontakte</span><span class="sxs-lookup"><span data-stu-id="7d1cd-157">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="7d1cd-158">Diagnose & Feedback</span><span class="sxs-lookup"><span data-stu-id="7d1cd-158">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="7d1cd-159">Dokumente</span><span class="sxs-lookup"><span data-stu-id="7d1cd-159">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="7d1cd-160">E-Mail</span><span class="sxs-lookup"><span data-stu-id="7d1cd-160">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="7d1cd-161">Dateisystem</span><span class="sxs-lookup"><span data-stu-id="7d1cd-161">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="7d1cd-162">Allgemein <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-162">General <sup>2</sup></span></span>             | `ms-settings:privacy-general`       |
| <span data-ttu-id="7d1cd-163">Personalisierung von Freihand- & Tastatureingaben <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-163">Ink & typing personalization <sup>2</sup></span></span>             | `ms-settings:privacy-speechtyping`       |
| <span data-ttu-id="7d1cd-164">Ort</span><span class="sxs-lookup"><span data-stu-id="7d1cd-164">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="7d1cd-165">Nachrichten</span><span class="sxs-lookup"><span data-stu-id="7d1cd-165">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="7d1cd-166">Mikrofon</span><span class="sxs-lookup"><span data-stu-id="7d1cd-166">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="7d1cd-167">Bewegung <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-167">Motion <sup>2</sup></span></span>               | `ms-settings:privacy-motion`                  |
| <span data-ttu-id="7d1cd-168">Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="7d1cd-168">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="7d1cd-169">Weitere Geräte</span><span class="sxs-lookup"><span data-stu-id="7d1cd-169">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="7d1cd-170">Bilder</span><span class="sxs-lookup"><span data-stu-id="7d1cd-170">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="7d1cd-171">Funkempfang</span><span class="sxs-lookup"><span data-stu-id="7d1cd-171">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="7d1cd-172">Screenshot Ränder <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-172">Screenshot borders <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="7d1cd-173">Screenshots und Apps <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-173">Screenshots and apps <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="7d1cd-174">Spracheingabe</span><span class="sxs-lookup"><span data-stu-id="7d1cd-174">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="7d1cd-175">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="7d1cd-175">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="7d1cd-176">Benutzerbewegungen</span><span class="sxs-lookup"><span data-stu-id="7d1cd-176">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="7d1cd-177">Videos</span><span class="sxs-lookup"><span data-stu-id="7d1cd-177">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="7d1cd-178">Voice-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="7d1cd-178">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="7d1cd-179">Netzwerk und Internet</span><span class="sxs-lookup"><span data-stu-id="7d1cd-179">Network & Internet</span></span>
| <span data-ttu-id="7d1cd-180">Seite "Einstellungen"</span><span class="sxs-lookup"><span data-stu-id="7d1cd-180">Settings page</span></span> | <span data-ttu-id="7d1cd-181">URI</span><span class="sxs-lookup"><span data-stu-id="7d1cd-181">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="7d1cd-182">Flugmodus <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-182">Airplane Mode <sup>2</sup></span></span> | `ms-settings:network-airplanemode`        |
| <span data-ttu-id="7d1cd-183">Proxy</span><span class="sxs-lookup"><span data-stu-id="7d1cd-183">Proxy</span></span> | `ms-settings:network-proxy`        |
| <span data-ttu-id="7d1cd-184">VPN</span><span class="sxs-lookup"><span data-stu-id="7d1cd-184">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="7d1cd-185">WLAN</span><span class="sxs-lookup"><span data-stu-id="7d1cd-185">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="7d1cd-186">System</span><span class="sxs-lookup"><span data-stu-id="7d1cd-186">System</span></span>
| <span data-ttu-id="7d1cd-187">Seite "Einstellungen"</span><span class="sxs-lookup"><span data-stu-id="7d1cd-187">Settings page</span></span>      | <span data-ttu-id="7d1cd-188">URI</span><span class="sxs-lookup"><span data-stu-id="7d1cd-188">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="7d1cd-189">Akku <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-189">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver`<br>|
| <span data-ttu-id="7d1cd-190">Akku <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-190">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver-settings`<br>|
| <span data-ttu-id="7d1cd-191">Farben</span><span class="sxs-lookup"><span data-stu-id="7d1cd-191">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="7d1cd-192">Hologramme <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-192">Holograms <sup>2</sup></span></span>  |  `ms-settings:holograms`  |
| <span data-ttu-id="7d1cd-193">Kalibrierung <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-193">Calibration <sup>2</sup></span></span> |  `ms-settings:calibration` |
| <span data-ttu-id="7d1cd-194">Benachrichtigungen & Infos</span><span class="sxs-lookup"><span data-stu-id="7d1cd-194">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="7d1cd-195">Gemeinsame Erfahrungen</span><span class="sxs-lookup"><span data-stu-id="7d1cd-195">Shared Experiences</span></span> | `ms-settings:crossdevice` 
| <span data-ttu-id="7d1cd-196">Sound <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-196">Sound <sup>2</sup></span></span>           | `ms-settings:sound`<br>|
| <span data-ttu-id="7d1cd-197">Sound > App-Lautstärke und Geräteeinstellung <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-197">Sound > App volume and device preference <sup>2</sup></span></span>           | `ms-settings:apps-volume`<br>|
| <span data-ttu-id="7d1cd-198">Sound > Verwalten von Soundgeräten <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-198">Sound > Manage sound devices <sup>2</sup></span></span>           | `ms-settings:sound-devices`<br>|
| <span data-ttu-id="7d1cd-199">Storage</span><span class="sxs-lookup"><span data-stu-id="7d1cd-199">Storage</span></span>            | `ms-settings:storagesense`           |
| <span data-ttu-id="7d1cd-200">Speicher > Konfigurieren Speicheroptimierung <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-200">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="7d1cd-201">Uhrzeit und Sprache</span><span class="sxs-lookup"><span data-stu-id="7d1cd-201">Time & Language</span></span>
| <span data-ttu-id="7d1cd-202">Seite "Einstellungen"</span><span class="sxs-lookup"><span data-stu-id="7d1cd-202">Settings page</span></span> | <span data-ttu-id="7d1cd-203">URI</span><span class="sxs-lookup"><span data-stu-id="7d1cd-203">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="7d1cd-204">Datum/Uhrzeit: <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-204">Date & time <sup>2</sup></span></span> | `ms-settings:dateandtime`                  |
| <span data-ttu-id="7d1cd-205">Tastatur <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-205">Keyboard <sup>2</sup></span></span> | `ms-settings:keyboard`                  |
| <span data-ttu-id="7d1cd-206">Sprache <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-206">Language <sup>2</sup></span></span> | `ms-settings:language`                  |
| <span data-ttu-id="7d1cd-207">Sprache <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-207">Language <sup>2</sup></span></span> | `ms-settings:regionlanguage-languageoptions`                  |
| <span data-ttu-id="7d1cd-208">Sprache</span><span class="sxs-lookup"><span data-stu-id="7d1cd-208">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="7d1cd-209">Region</span><span class="sxs-lookup"><span data-stu-id="7d1cd-209">Region</span></span>        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="7d1cd-210">Update & Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7d1cd-210">Update & Security</span></span>
| <span data-ttu-id="7d1cd-211">Seite "Einstellungen"</span><span class="sxs-lookup"><span data-stu-id="7d1cd-211">Settings page</span></span>                         | <span data-ttu-id="7d1cd-212">URI</span><span class="sxs-lookup"><span data-stu-id="7d1cd-212">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="7d1cd-213">Erweiterte Optionen</span><span class="sxs-lookup"><span data-stu-id="7d1cd-213">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |
| <span data-ttu-id="7d1cd-214">Zurücksetzen & Wiederherstellen <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7d1cd-214">Reset & Recovery <sup>2</sup></span></span>      | `ms-settings:reset`         |
| <span data-ttu-id="7d1cd-215">Windows-Insider-Programm</span><span class="sxs-lookup"><span data-stu-id="7d1cd-215">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="7d1cd-216">Windows-Update</span><span class="sxs-lookup"><span data-stu-id="7d1cd-216">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><span data-ttu-id="7d1cd-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="7d1cd-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span></span><br><span data-ttu-id="7d1cd-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="7d1cd-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="7d1cd-219">Windows Update – Sucht nach Updates</span><span class="sxs-lookup"><span data-stu-id="7d1cd-219">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |


- <span data-ttu-id="7d1cd-220"><sup>1</sup> – Bei Versionen vor Windows Holographic, Version 21H1, werden Sie durch die folgenden beiden URIs nicht zu den Seiten **Erweiterte Optionen** oder **Optionen** geführt. Sie blockieren oder zeigen nur die Hauptseite Windows Update an.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-220"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="7d1cd-221">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="7d1cd-221">ms-settings:windowsupdate-options</span></span>
  -  <span data-ttu-id="7d1cd-222">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="7d1cd-222">ms-settings:windowsupdate-restartoptions</span></span>

- <span data-ttu-id="7d1cd-223"><sup>2</sup> – Verfügbar in Windows Holographic 21H1 oder höher.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-223"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="7d1cd-224">Eine vollständige Liste der URIs für Windows 10-Einstellungen finden Sie in der Dokumentation [Starteinstellungen](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).</span><span class="sxs-lookup"><span data-stu-id="7d1cd-224">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
