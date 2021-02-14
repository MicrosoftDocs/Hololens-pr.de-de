---
title: Sichtbarkeit von Seiteneinstellungen
description: Bleiben Sie mit unserer Liste der unterstützten URIs für PageVisibilityList und Guide auf Mixed-Reality-HoloLens-Geräten auf dem Laufenden.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: HoloLens, HoloLens 2, zugewiesener Zugriff, Kiosk, Einstellungsseite
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f004f39f4b69748e8c36ad93111f4423d14c40f3
ms.sourcegitcommit: 23ee06b659d7a51f3000d386c8f67cbf212d5aa4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327389"
---
# <span data-ttu-id="d1b81-104">Sichtbarkeit von Seiteneinstellungen</span><span class="sxs-lookup"><span data-stu-id="d1b81-104">Page Settings Visibility</span></span>

<span data-ttu-id="d1b81-105">Zu den verwaltbaren Features für HoloLens-Geräte gehört die [Einstellungen/PageVisibilityList-Richtlinie](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist), mit der die in der App „Einstellungen“ angezeigten Seiten eingeschränkt werden können.</span><span class="sxs-lookup"><span data-stu-id="d1b81-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="d1b81-106">Die PageVisibilityList ist eine Richtlinie, die es IT-Administratoren ermöglicht, entweder zu verhindern, dass bestimmte Seiten in der Systemeinstellungs-App sichtbar oder zugänglich sind oder Sie können das für alle Seiten tun, außer den angegebenen.</span><span class="sxs-lookup"><span data-stu-id="d1b81-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="d1b81-107">Diese Funktion ist nur in [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) für HoloLens 2-Geräte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d1b81-107">This feature is only avalible in [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 devices.</span></span> <span data-ttu-id="d1b81-108">Stellen Sie sicher, dass die Geräte aktualisiert sind, wenn Sie die Funktion verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d1b81-108">Please ensure devices you intend to use this for are updated.</span></span>

> [!NOTE]
> <span data-ttu-id="d1b81-109">Mehr als 20 neue SettingsURIs werden in Kürze hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d1b81-109">20+ new SettingsURIs are being added soon.</span></span> <span data-ttu-id="d1b81-110">Wenn Sie diese Einstellung in der Vorschauversion auf einem [HoloLens Insider-Build](hololens-insider.md) ausprobieren möchten, sehen Sie sich bitte [die Windows Insider-Seite „Neue SettingsURIs für die Sichtbarkeit von Seiteneinstellungen](hololens-insider.md#new-settingsuris-for-page-settings-visibility) an.</span><span class="sxs-lookup"><span data-stu-id="d1b81-110">Please view [the Windows Insider page - New SettingsURIs for Page Settings Visibility](hololens-insider.md#new-settingsuris-for-page-settings-visibility) if you are interesting in previewing this setting on a [HoloLens Insider](hololens-insider.md) build.</span></span>

<span data-ttu-id="d1b81-111">Das folgende Beispiel zeigt eine Richtlinie, die nur Zugriff auf die Seiten „Über“ und „Bluetooth“ ermöglichen würde, die jeweils über URI „ms-settings:network-wifi“ und „ms-settings:bluetooth“ verfügen:</span><span class="sxs-lookup"><span data-stu-id="d1b81-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="d1b81-112">So legen Sie dies über ein Bereitstellungspaket fest:</span><span class="sxs-lookup"><span data-stu-id="d1b81-112">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="d1b81-113">Während Sie Ihr Paket im Windows Configuration Designer erstellen, navigieren Sie zu **Richtlinien > Einstellungen > PageVisibilityList**.</span><span class="sxs-lookup"><span data-stu-id="d1b81-113">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="d1b81-114">Geben Sie die folgende Zeichenfolge ein: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="d1b81-114">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="d1b81-115">Exportieren Sie Ihr Bereitstellungspaket.</span><span class="sxs-lookup"><span data-stu-id="d1b81-115">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="d1b81-116">Wenden Sie das Paket auf Ihr Gerät an.</span><span class="sxs-lookup"><span data-stu-id="d1b81-116">Apply the package to your device.</span></span>
<span data-ttu-id="d1b81-117">Ausführliche Informationen zum Erstellen und Anwenden eines Bereitstellungspakets finden Sie [auf dieser Seite.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="d1b81-117">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="d1b81-118">Dies kann über Intune mithilfe von OMA-URI durchgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="d1b81-118">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="d1b81-119">Erstellen Sie eine **benutzerdefinierte Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="d1b81-119">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="d1b81-120">Verwenden Sie beim Festlegen des OMA-URI die Zeichenfolge: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="d1b81-120">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="d1b81-121">Wählen Sie bei der Auswahl der Daten: **String**</span><span class="sxs-lookup"><span data-stu-id="d1b81-121">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="d1b81-122">Verwenden Sie beim Eingeben des Werts Folgendes: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="d1b81-122">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="d1b81-123">Stellen Sie sicher, dass die benutzerdefinierte Gerätekonfiguration einer Gruppe zugeordnet wird, zu der das Gerät gehören soll.</span><span class="sxs-lookup"><span data-stu-id="d1b81-123">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="d1b81-124">Weitere Informationen zu Intune-Gruppen und -Gerätekonfigurationen finden Sie unter [HoloLens MDM-Konfiguration.](hololens-mdm-configure.md)</span><span class="sxs-lookup"><span data-stu-id="d1b81-124">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="d1b81-125">Unabhängig von der gewählten Methode sollte Ihr Gerät jetzt die Änderungen erhalten, und den Benutzern wird die folgende Einstellungs-App angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d1b81-125">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Screenshot der Nutzungszeit, die in der Einstellungs-App geändert werden](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="d1b81-127">Um die Einstellungs-App-Seiten so zu konfigurieren, dass Ihre eigene Auswahl von Seiten ein- oder ausgeblendet wird, sehen Sie sich die Einstellungs-URIs an, die auf HoloLens verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d1b81-127">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <span data-ttu-id="d1b81-128">Einstellungs-URIs</span><span class="sxs-lookup"><span data-stu-id="d1b81-128">Settings URIs</span></span>

<span data-ttu-id="d1b81-129">HoloLens-Geräte und Windows 10-Geräte weisen in der App „Einstellungen“ eine unterschiedliche Seitenauswahl auf.</span><span class="sxs-lookup"><span data-stu-id="d1b81-129">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="d1b81-130">Auf dieser Seite finden Sie nur die Einstellungen, die auf HoloLens vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d1b81-130">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <span data-ttu-id="d1b81-131">Konten</span><span class="sxs-lookup"><span data-stu-id="d1b81-131">Accounts</span></span>
| <span data-ttu-id="d1b81-132">Einstellungsseite</span><span class="sxs-lookup"><span data-stu-id="d1b81-132">Settings page</span></span>           | <span data-ttu-id="d1b81-133">URI</span><span class="sxs-lookup"><span data-stu-id="d1b81-133">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="d1b81-134">Anmeldeoptionen</span><span class="sxs-lookup"><span data-stu-id="d1b81-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |
| <span data-ttu-id="d1b81-135">Iris-Registrierung</span><span class="sxs-lookup"><span data-stu-id="d1b81-135">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="d1b81-136">Geschäfts- oder Schulkonto öffnen</span><span class="sxs-lookup"><span data-stu-id="d1b81-136">Access work or school</span></span> | `ms-settings:workplace`                         |

### <span data-ttu-id="d1b81-137">Geräte</span><span class="sxs-lookup"><span data-stu-id="d1b81-137">Devices</span></span>
| <span data-ttu-id="d1b81-138">Einstellungsseite</span><span class="sxs-lookup"><span data-stu-id="d1b81-138">Settings page</span></span> | <span data-ttu-id="d1b81-139">URI</span><span class="sxs-lookup"><span data-stu-id="d1b81-139">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="d1b81-140">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="d1b81-140">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |

### <span data-ttu-id="d1b81-141">Datenschutz</span><span class="sxs-lookup"><span data-stu-id="d1b81-141">Privacy</span></span>
| <span data-ttu-id="d1b81-142">Einstellungsseite</span><span class="sxs-lookup"><span data-stu-id="d1b81-142">Settings page</span></span>            | <span data-ttu-id="d1b81-143">URI</span><span class="sxs-lookup"><span data-stu-id="d1b81-143">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="d1b81-144">Kontoinformationen</span><span class="sxs-lookup"><span data-stu-id="d1b81-144">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="d1b81-145">App-Diagnose</span><span class="sxs-lookup"><span data-stu-id="d1b81-145">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="d1b81-146">Hintergrund-Apps</span><span class="sxs-lookup"><span data-stu-id="d1b81-146">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="d1b81-147">Benutzerbewegungen</span><span class="sxs-lookup"><span data-stu-id="d1b81-147">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="d1b81-148">Dateisystem</span><span class="sxs-lookup"><span data-stu-id="d1b81-148">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="d1b81-149">Kalender</span><span class="sxs-lookup"><span data-stu-id="d1b81-149">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="d1b81-150">Anrufliste</span><span class="sxs-lookup"><span data-stu-id="d1b81-150">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="d1b81-151">Kontakte</span><span class="sxs-lookup"><span data-stu-id="d1b81-151">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="d1b81-152">Weitere Geräte</span><span class="sxs-lookup"><span data-stu-id="d1b81-152">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="d1b81-153">Dokumente</span><span class="sxs-lookup"><span data-stu-id="d1b81-153">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="d1b81-154">E-Mail</span><span class="sxs-lookup"><span data-stu-id="d1b81-154">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="d1b81-155">Diagnose und Feedback</span><span class="sxs-lookup"><span data-stu-id="d1b81-155">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="d1b81-156">Ort</span><span class="sxs-lookup"><span data-stu-id="d1b81-156">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="d1b81-157">Messaging</span><span class="sxs-lookup"><span data-stu-id="d1b81-157">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="d1b81-158">Mikrofon</span><span class="sxs-lookup"><span data-stu-id="d1b81-158">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="d1b81-159">Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="d1b81-159">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="d1b81-160">Bilder</span><span class="sxs-lookup"><span data-stu-id="d1b81-160">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="d1b81-161">Funkempfang</span><span class="sxs-lookup"><span data-stu-id="d1b81-161">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="d1b81-162">Spracherkennung</span><span class="sxs-lookup"><span data-stu-id="d1b81-162">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="d1b81-163">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="d1b81-163">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="d1b81-164">Videos</span><span class="sxs-lookup"><span data-stu-id="d1b81-164">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="d1b81-165">Stimmaktivierung</span><span class="sxs-lookup"><span data-stu-id="d1b81-165">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |
| <span data-ttu-id="d1b81-166">Kamera</span><span class="sxs-lookup"><span data-stu-id="d1b81-166">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |

### <span data-ttu-id="d1b81-167">Netzwerk und Internet</span><span class="sxs-lookup"><span data-stu-id="d1b81-167">Network & Internet</span></span>
| <span data-ttu-id="d1b81-168">Einstellungsseite</span><span class="sxs-lookup"><span data-stu-id="d1b81-168">Settings page</span></span> | <span data-ttu-id="d1b81-169">URI</span><span class="sxs-lookup"><span data-stu-id="d1b81-169">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="d1b81-170">WLAN</span><span class="sxs-lookup"><span data-stu-id="d1b81-170">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |
| <span data-ttu-id="d1b81-171">VPN</span><span class="sxs-lookup"><span data-stu-id="d1b81-171">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="d1b81-172">Proxy</span><span class="sxs-lookup"><span data-stu-id="d1b81-172">Proxy</span></span> | `ms-settings:network-proxy`        |

### <span data-ttu-id="d1b81-173">System</span><span class="sxs-lookup"><span data-stu-id="d1b81-173">System</span></span>
| <span data-ttu-id="d1b81-174">Einstellungsseite</span><span class="sxs-lookup"><span data-stu-id="d1b81-174">Settings page</span></span>      | <span data-ttu-id="d1b81-175">URI</span><span class="sxs-lookup"><span data-stu-id="d1b81-175">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="d1b81-176">Gemeinsame Nutzung</span><span class="sxs-lookup"><span data-stu-id="d1b81-176">Shared Experiences</span></span> | `ms-settings:crossdevice`            |
| <span data-ttu-id="d1b81-177">Farben</span><span class="sxs-lookup"><span data-stu-id="d1b81-177">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="d1b81-178">Benachrichtigungen & Infos</span><span class="sxs-lookup"><span data-stu-id="d1b81-178">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="d1b81-179">Speicher</span><span class="sxs-lookup"><span data-stu-id="d1b81-179">Storage</span></span>            | `ms-settings:storagesense`           |

### <span data-ttu-id="d1b81-180">Zeit & Sprache</span><span class="sxs-lookup"><span data-stu-id="d1b81-180">Time & Language</span></span>
| <span data-ttu-id="d1b81-181">Einstellungsseite</span><span class="sxs-lookup"><span data-stu-id="d1b81-181">Settings page</span></span> | <span data-ttu-id="d1b81-182">URI</span><span class="sxs-lookup"><span data-stu-id="d1b81-182">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="d1b81-183">Region</span><span class="sxs-lookup"><span data-stu-id="d1b81-183">Region</span></span>        | `ms-settings:regionformatting`                  |
| <span data-ttu-id="d1b81-184">Sprache</span><span class="sxs-lookup"><span data-stu-id="d1b81-184">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |

### <span data-ttu-id="d1b81-185">Update und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d1b81-185">Update & Security</span></span>
| <span data-ttu-id="d1b81-186">Einstellungsseite</span><span class="sxs-lookup"><span data-stu-id="d1b81-186">Settings page</span></span>                         | <span data-ttu-id="d1b81-187">URI</span><span class="sxs-lookup"><span data-stu-id="d1b81-187">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="d1b81-188">Windows-Insider-Programm</span><span class="sxs-lookup"><span data-stu-id="d1b81-188">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="d1b81-189">Windows Update</span><span class="sxs-lookup"><span data-stu-id="d1b81-189">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup><span data-ttu-id="d1b81-190">1</span><span class="sxs-lookup"><span data-stu-id="d1b81-190">1</span></span></sup>`ms-settings:windowsupdate-options`<br><sup><span data-ttu-id="d1b81-191">1</span><span class="sxs-lookup"><span data-stu-id="d1b81-191">1</span></span></sup>`ms-settings:windowsupdate-restartoptions` |
| <span data-ttu-id="d1b81-192">Windows Update – Suche nach Updates</span><span class="sxs-lookup"><span data-stu-id="d1b81-192">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |
| <span data-ttu-id="d1b81-193">Erweiterte Optionen</span><span class="sxs-lookup"><span data-stu-id="d1b81-193">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |

>  <sup><span data-ttu-id="d1b81-194">1 </sup> Die folgenden beiden URIs führen Sie nicht zu den Seiten **Erweiterte Optionen** oder **Optionen**; sie blockieren oder zeigen nur die Windows Update-Hauptseite an.</span><span class="sxs-lookup"><span data-stu-id="d1b81-194">1</sup> The following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
> - <span data-ttu-id="d1b81-195">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="d1b81-195">ms-settings:windowsupdate-options</span></span>
> - <span data-ttu-id="d1b81-196">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="d1b81-196">ms-settings:windowsupdate-restartoptions</span></span> 

<span data-ttu-id="d1b81-197">Eine vollständige Liste der URIs für Windows 10-Einstellungen finden Sie in der Dokumentation [Starteinstellungen](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).</span><span class="sxs-lookup"><span data-stu-id="d1b81-197">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
