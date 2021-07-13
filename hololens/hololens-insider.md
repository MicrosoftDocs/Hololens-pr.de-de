---
title: Insider Preview für Microsoft HoloLens
description: Erfahren Sie, wie Sie mit Insider-Builds beginnen, und geben Sie wertvolles Feedback zu unserem nächsten wichtigen Betriebssystemupdate für HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 87b606e634d4035da02802ddd1a8e1a980f1f1d6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636092"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="d4fcc-103">Insider Preview für Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="d4fcc-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="d4fcc-104">Willkommen bei den neuesten Insider Preview-Builds für HoloLens!</span><span class="sxs-lookup"><span data-stu-id="d4fcc-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="d4fcc-105">Es ist einfach, [zu](hololens-insider.md#start-receiving-insider-builds) beginnen und wertvolles Feedback für unser nächstes größeres Betriebssystemupdate für HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="d4fcc-106">Windows Insider-Versionshinweise</span><span class="sxs-lookup"><span data-stu-id="d4fcc-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="d4fcc-107">Wir freuen uns, mit der Entwicklung neuer Features zu beginnen, Windows Insider zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="d4fcc-108">Neue Builds werden an die Entwicklungs- und Betakanäle übertragen, um die neuesten Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="d4fcc-109">Wir werden diese Seite weiterhin aktualisieren, wenn wir unseren Insider-Builds weitere Features und Windows hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="d4fcc-110">Lassen Sie sich freuen und bereit sein, diese Updates in Ihre Realität zu mischen.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="d4fcc-111">Feature</span><span class="sxs-lookup"><span data-stu-id="d4fcc-111">Feature</span></span>                 | <span data-ttu-id="d4fcc-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4fcc-112">Description</span></span>                | <span data-ttu-id="d4fcc-113">Benutzer oder Szenario</span><span class="sxs-lookup"><span data-stu-id="d4fcc-113">User or Scenario</span></span> | <span data-ttu-id="d4fcc-114">Build eingeführt</span><span class="sxs-lookup"><span data-stu-id="d4fcc-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| [<span data-ttu-id="d4fcc-115">CSP-Änderungen für die Berichterstellung HoloLens Details</span><span class="sxs-lookup"><span data-stu-id="d4fcc-115">CSP changes for reporting HoloLens details</span></span>](#csp-changes-for-reporting-hololens-details) | <span data-ttu-id="d4fcc-116">Neue CSPs für zum Abfragen von Daten</span><span class="sxs-lookup"><span data-stu-id="d4fcc-116">New CSPs for to query data</span></span> | <span data-ttu-id="d4fcc-117">IT-Administratoren</span><span class="sxs-lookup"><span data-stu-id="d4fcc-117">IT Admins</span></span>    | <span data-ttu-id="d4fcc-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="d4fcc-118">20348.1403</span></span>                 |
| [<span data-ttu-id="d4fcc-119">Richtlinie für die automatische Anmeldung, die von CSP gesteuert wird</span><span class="sxs-lookup"><span data-stu-id="d4fcc-119">Auto login policy controlled by CSP</span></span>](#auto-login-policy-controlled-by-csp) | <span data-ttu-id="d4fcc-120">Wird zum automatischen Anmelden eines Kontos verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-120">Used to log in an account automatically</span></span> | <span data-ttu-id="d4fcc-121">IT-Administratoren</span><span class="sxs-lookup"><span data-stu-id="d4fcc-121">IT Admins</span></span> | <span data-ttu-id="d4fcc-122">20348.1405</span><span class="sxs-lookup"><span data-stu-id="d4fcc-122">20348.1405</span></span> |
| [<span data-ttu-id="d4fcc-123">PFX-Dateiunterstützung für den Zertifikat-Manager</span><span class="sxs-lookup"><span data-stu-id="d4fcc-123">PFX file support for Certificate Manager</span></span>](#pfx-file-support-for-certificate-manager) | <span data-ttu-id="d4fcc-124">Hinzufügen von PFX-Zertifikaten über Einstellungen Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="d4fcc-124">Add PFX certs via Settings UI</span></span> | <span data-ttu-id="d4fcc-125">Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="d4fcc-125">End User</span></span> | <span data-ttu-id="d4fcc-126">20348.1405</span><span class="sxs-lookup"><span data-stu-id="d4fcc-126">20348.1405</span></span> |
| [<span data-ttu-id="d4fcc-127">Anzeigen des erweiterten Diagnoseberichts in Einstellungen auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="d4fcc-127">View advanced diagnostic report in Settings on HoloLens</span></span>](#view-advanced-diagnostic-report-in-settings-on-hololens) | <span data-ttu-id="d4fcc-128">Anzeigen von MDM-Diagnoseprotokollen auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="d4fcc-128">View MDM diagnostic logs on device</span></span> | <span data-ttu-id="d4fcc-129">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="d4fcc-129">Troubleshooting</span></span> | <span data-ttu-id="d4fcc-130">20348.1405</span><span class="sxs-lookup"><span data-stu-id="d4fcc-130">20348.1405</span></span> |
| [<span data-ttu-id="d4fcc-131">Offlinediagnosebenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="d4fcc-131">Offline Diagnostics notifications</span></span>](#offline-diagnostics-notifications) | <span data-ttu-id="d4fcc-132">Feedback zur Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="d4fcc-132">Audiovisual feedback for log collection</span></span> | <span data-ttu-id="d4fcc-133">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="d4fcc-133">Troubleshooting</span></span> | <span data-ttu-id="d4fcc-134">20348.1405</span><span class="sxs-lookup"><span data-stu-id="d4fcc-134">20348.1405</span></span> |


### <a name="csp-changes-for-reporting-hololens-details"></a><span data-ttu-id="d4fcc-135">CSP-Änderungen für die Berichterstellung HoloLens Details</span><span class="sxs-lookup"><span data-stu-id="d4fcc-135">CSP changes for reporting HoloLens details</span></span>

- <span data-ttu-id="d4fcc-136">Eingeführt in Windows Insider-Build, 20348.1403</span><span class="sxs-lookup"><span data-stu-id="d4fcc-136">Introduced in Windows Insider build, 20348.1403</span></span>

<span data-ttu-id="d4fcc-137">Die folgenden CSPs wurden mit neuen Möglichkeiten zum Melden von Informationen von Ihren HoloLens aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-137">The following CSPs have been updated with new ways to report information from your HoloLens devices.</span></span>

#### <a name="devdetail-csp---free-storage"></a><span data-ttu-id="d4fcc-138">DevDetail-CSP – kostenlose Storage</span><span class="sxs-lookup"><span data-stu-id="d4fcc-138">DevDetail CSP - Free Storage</span></span>

<span data-ttu-id="d4fcc-139">DevDetail-CSP meldet jetzt auch freien Speicherplatz auf HoloLens Gerät.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-139">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="d4fcc-140">Dies sollte ungefähr mit dem Wert übereinstimmen, der auf Einstellungen-Seite der App Storage wird.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-140">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="d4fcc-141">Im Folgenden finden Sie den spezifischen Knoten, der diese Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-141">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="d4fcc-142">./DevDetail/Ext/Microsoft/FreeStorage (nur GET-Vorgang)</span><span class="sxs-lookup"><span data-stu-id="d4fcc-142">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp---ssid-and-bssid"></a><span data-ttu-id="d4fcc-143">DeviceStatus-CSP: SSID und BSSID</span><span class="sxs-lookup"><span data-stu-id="d4fcc-143">DeviceStatus CSP - SSID and BSSID</span></span>

<span data-ttu-id="d4fcc-144">DeviceStatus-CSP meldet jetzt auch SSID und BSSID des Wi-Fi Netzwerks, mit dem HoloLens aktiv verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-144">DeviceStatus CSP now also reports SSID and BSSID of Wi-Fi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="d4fcc-145">Im Folgenden finden Sie die spezifischen Knoten, die diese Informationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-145">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="d4fcc-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span><span class="sxs-lookup"><span data-stu-id="d4fcc-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="d4fcc-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span><span class="sxs-lookup"><span data-stu-id="d4fcc-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="d4fcc-148">Beispiel für ein syncml-Blob (für MDM-Anbieter) zum Abfragen von NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="d4fcc-148">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a><span data-ttu-id="d4fcc-149">Richtlinie für die automatische Anmeldung, die von CSP gesteuert wird</span><span class="sxs-lookup"><span data-stu-id="d4fcc-149">Auto login policy controlled by CSP</span></span>

<span data-ttu-id="d4fcc-150">Diese neue AutoLogonUser-Richtlinie steuert, ob ein Benutzer automatisch angemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-150">This new AutoLogonUser policy controls whether a user will be automatically logged on.</span></span> <span data-ttu-id="d4fcc-151">Einige Kunden möchten Geräte einrichten, die an eine Identität gebunden sind, aber keine Anmeldeerfahrung wünschen.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-151">Some customers want to set up devices that are tied to an identity but don't want any sign-in experience.</span></span> <span data-ttu-id="d4fcc-152">Imagine sofort ein Gerät aufnehmen und die Remoteunterstützung verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-152">Imagine picking up a device and using remote assist immediately.</span></span> <span data-ttu-id="d4fcc-153">Oder sie haben den Vorteil, dass sie schnell HoloLens verteilen und ihren Endbenutzern ermöglichen, die Anmeldung zu beschleunigt.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-153">Or have a benefit of being able to rapidly  distribute HoloLens devices and enable their end users to expedite login.</span></span>

<span data-ttu-id="d4fcc-154">Wenn die Richtlinie auf einen nicht leeren Wert festgelegt ist, wird die E-Mail-Adresse des Benutzers mit automatischer Anmeldung angegeben.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-154">When the policy is set to a non-empty value, it specifies the email address of the auto-logon user.</span></span> <span data-ttu-id="d4fcc-155">Der angegebene Benutzer muss sich mindestens einmal beim Gerät anmelden, um die automatische Anmeldung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-155">The specified user must logon to the device at least once to enable auto-logon.</span></span>

<span data-ttu-id="d4fcc-156">Der OMA-URI des neuen `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` Richtlinienzeichenfolgenwerts</span><span class="sxs-lookup"><span data-stu-id="d4fcc-156">The OMA-URI of new policy `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` String value</span></span>

- <span data-ttu-id="d4fcc-157">Für Benutzer mit der gleichen E-Mail-Adresse ist die automatische Anmeldung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-157">User with the same email address will have auto logon enabled.</span></span>

<span data-ttu-id="d4fcc-158">Auf einem Gerät, auf dem diese Richtlinie konfiguriert ist, muss sich der in der Richtlinie angegebene Benutzer mindestens einmal anmelden.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-158">On a device where this policy is configured, the user specified in the policy will need to logon at least once.</span></span> <span data-ttu-id="d4fcc-159">Bei nachfolgenden Neustarts des Geräts nach der ersten Anmeldung wird der angegebene Benutzer automatisch angemeldet.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-159">Subsequent reboots of the device after the first logon will have the specified user automatically logged on.</span></span> <span data-ttu-id="d4fcc-160">Es wird nur ein einzelner Benutzer für die automatische Anmeldung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-160">Only a single auto-logon user is supported.</span></span> <span data-ttu-id="d4fcc-161">Nach der Aktivierung kann sich der automatisch angemeldete Benutzer nicht mehr manuell abmelden.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-161">Once enabled, the automatically logged on user will not be able to log out manually.</span></span> <span data-ttu-id="d4fcc-162">Um sich als anderer Benutzer zu anmelden, muss die Richtlinie zuerst deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-162">To logon as a different user, the policy must first be disabled.</span></span>

> [!NOTE]
> - <span data-ttu-id="d4fcc-163">Für einige Ereignisse, z. B. wichtige Betriebssystemupdates, muss sich der angegebene Benutzer möglicherweise erneut beim Gerät anmelden, um das Verhalten der automatischen Anmeldung wieder aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-163">Some events such as major OS updates may require the specified user to logon to the device again to resume auto-logon behavior.</span></span> 
> - <span data-ttu-id="d4fcc-164">Die automatische Anmeldung wird nur für MSA- und AAD-Benutzer unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-164">Auto-logon is only supported for MSA and AAD users.</span></span>

### <a name="pfx-file-support-for-certificate-manager"></a><span data-ttu-id="d4fcc-165">PFX-Dateiunterstützung für den Zertifikat-Manager</span><span class="sxs-lookup"><span data-stu-id="d4fcc-165">PFX file support for Certificate Manager</span></span>

<span data-ttu-id="d4fcc-166">Eingeführt in Windows Insider-Build 20348.1405.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-166">Introduced in Windows Insider build 20348.1405.</span></span> <span data-ttu-id="d4fcc-167">Wir haben dem [Zertifikat-Manager](certificate-manager.md) Unterstützung für die Verwendung von PFX-Zertifikaten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-167">We’ve added support to the [Certificate Manager](certificate-manager.md) to now use .pfx certificates.</span></span> <span data-ttu-id="d4fcc-168">Wenn Benutzer zu **Einstellungen** Update &-Sicherheitszertifikate navigieren und Zertifikat installieren auswählen, unterstützt die Benutzeroberfläche jetzt  >    >  die PFX-Zertifikatdatei. </span><span class="sxs-lookup"><span data-stu-id="d4fcc-168">When users navigate to **Settings** > **Update & Security** > **Certificates**, and select **Install a certificate** the UI now supports .pfx certificate file.</span></span>
<span data-ttu-id="d4fcc-169">Benutzer können das PFX-Zertifikat mit privatem Schlüssel in den Benutzer- oder Computerspeicher importieren.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-169">Users can import .pfx certificate, with private key, to user store or machine store.</span></span>

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a><span data-ttu-id="d4fcc-170">Anzeigen des erweiterten Diagnoseberichts in Einstellungen auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="d4fcc-170">View advanced diagnostic report in Settings on HoloLens</span></span>

<span data-ttu-id="d4fcc-171">Bei verwalteten Geräten bei der Problembehandlung ist die Bestätigung, dass eine erwartete Richtlinienkonfiguration angewendet wird, ein wichtiger Schritt.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-171">For managed devices when troubleshooting behavior, confirming that an expected policy configuration is applied is an important step.</span></span> <span data-ttu-id="d4fcc-172">Zuvor musste dies auf dem Gerät über MDM oder in der Nähe des Geräts erfolgen, nachdem mdm-Diagnoseprotokolle exportiert wurden, die über **Einstellungen-Konten** gesammelt wurden. Wählen Sie anschließend Die Verwaltungsprotokolle exportieren und auf einem pc in der Nähe anzeigen  ->    >  aus. </span><span class="sxs-lookup"><span data-stu-id="d4fcc-172">Previously to this new feature, this had to be done off device via MDM or near the device after exporting MDM diagnostic logs gathered via **Settings** -> **Accounts** > **Access work or school**, and select **Export your management logs** and viewed on a nearby PC.</span></span>

<span data-ttu-id="d4fcc-173">Die MDM-Diagnose kann nun mithilfe des Edge-Browsers auf dem Gerät angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-173">Now the MDM Diagnostics can be viewed on device using the Edge browser.</span></span> <span data-ttu-id="d4fcc-174">Um den MDM-Diagnosebericht einfacher anzuzeigen, navigieren Sie zur Seite Auf Arbeits- oder Schulsystem zugreifen, und wählen **Sie Erweiterten Diagnosebericht anzeigen aus.**</span><span class="sxs-lookup"><span data-stu-id="d4fcc-174">To more easily view the MDM Diagnostic report navigate to the Access work or school page, and select **View advanced diagnostic report**.</span></span> <span data-ttu-id="d4fcc-175">Dadurch wird der Bericht in einem neuen Edgefenster generiert und geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-175">This will generate and open the report in a new Edge window.</span></span>

![Zeigen Sie den erweiterten Diagnosebericht in Einstellungen an.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a><span data-ttu-id="d4fcc-177">Offlinediagnosebenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="d4fcc-177">Offline Diagnostics notifications</span></span>

<span data-ttu-id="d4fcc-178">Dies ist ein Update für ein vorhandenes Feature namens [Offlinediagnose.](hololens-diagnostic-logs.md#offline-diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d4fcc-178">This an update for an existing feature called [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> <span data-ttu-id="d4fcc-179">Zuvor gab es keinen eindeutigen Hinweis für Benutzer, dass sie die Diagnosesammlung ausgelöst oder abgeschlossen hatten.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-179">Previously, there was no clear indicator to users that they had triggered diagnostic collection or it had completed.</span></span>
<span data-ttu-id="d4fcc-180">Jetzt in Windows Insider-Builds hinzugefügt, gibt es zwei Formen von Feedback zur Offlinediagnose.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-180">Now added in Windows Insider builds, there are two forms of audiovisual feedback for Offline Diagnostics.</span></span> <span data-ttu-id="d4fcc-181">Das erste sind Popupbenachrichtigungen, die sowohl beim Start als auch beim Abschluss der Sammlung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-181">The first being toasts notifications displayed for both when collection starts and completes.</span></span> <span data-ttu-id="d4fcc-182">Diese werden angezeigt, wenn der Benutzer angemeldet ist und über Visuals verfügt.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-182">These will be displayed when the user is logged in and has visuals.</span></span>

![Popup zum Sammeln von Protokollen.](./images/logcollection1.jpg)

![Popup, wenn die Protokollsammlung abgeschlossen ist.](./images/logcollection2.jpg)
 
<span data-ttu-id="d4fcc-185">Da Benutzer die Offlinediagnose häufig als Mechanismus für die Fallbackprotokollsammlung verwenden, wenn sie keinen Zugriff auf eine Anzeige haben, sich nicht anmelden können oder sich noch in oobe befinden, wird auch ein Audio-Hinweis abgespielt, wenn Protokolle gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-185">Because users often use Offline Diagnostics as a fallback log gathering mechanism for when they don’t have access to a display, can’t log-in or are still in OOBE there will also be an audio cue played when logs are gathered.</span></span> <span data-ttu-id="d4fcc-186">Dieser Sound wird zusätzlich zur Popupbenachrichtigung abgespielt.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-186">This sound will be played in addition to the toast notification.</span></span>

<span data-ttu-id="d4fcc-187">Dieses neue Feature wird aktiviert, wenn Ihr Gerät aktualisiert wird, und muss nicht aktiviert oder verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-187">This new feature will be enabled when your device updates, and doesn’t need to be enabled or managed.</span></span> <span data-ttu-id="d4fcc-188">In jedem Fall, in dem dieses neue Feedback nicht angezeigt oder gehört werden kann, wird weiterhin die Offlinediagnose generiert.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-188">In any event that this new feedback cannot be displayed or heard, Offline Diagnostics will still be generated.</span></span>

<span data-ttu-id="d4fcc-189">Wir hoffen, dass es mit diesem neueren Feedback einfacher ist, Diagnosedaten zu sammeln und Ihre Probleme schneller beheben zu können.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-189">We hope with this newer addition of audiovisual feedback it is easier to gather diagnostic data, and more quickly be able to troubleshoot your problems.</span></span>



### <a name="fixes-and-improvements"></a><span data-ttu-id="d4fcc-190">Fehlerbehebungen und Verbesserungen:</span><span class="sxs-lookup"><span data-stu-id="d4fcc-190">Fixes and improvements:</span></span>

- <span data-ttu-id="d4fcc-191">Es wurde ein [bekanntes Problem für Geräteportal, bei dem keine Aufforderung zum Herunterladen gesperrter Dateien angezeigt wurde.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="d4fcc-191">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="d4fcc-192">Es wurde ein [bekanntes Problem bei Geräteportal dateiupload- und download-Time outs behoben.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="d4fcc-192">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>


## <a name="start-receiving-insider-builds"></a><span data-ttu-id="d4fcc-193">Starten des Empfangs von Insider-Builds</span><span class="sxs-lookup"><span data-stu-id="d4fcc-193">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="d4fcc-194">Wenn Sie vor Kurzem noch nicht aktualisiert haben, starten Sie Ihr Gerät neu, um den Status zu aktualisieren und den neuesten Build zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-194">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="d4fcc-195">Der Sprachbefehl "Gerät neu starten" funktioniert gut.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-195">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="d4fcc-196">Sie können auch die Schaltfläche "Neu starten" im Einstellungen/Windows Insider-Programm auswählen.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-196">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="d4fcc-197">Es ist ein Fehler auf dem Back-End aufgetreten, den Sie möglicherweise gefunden haben, damit Sie wieder auf Kurs sind.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-197">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="d4fcc-198">Wechseln Sie HoloLens 2 gerät zu Einstellungen  >  **Update & Security** Windows Insider Program, und wählen Sie Erste Schritte  >   **aus.**</span><span class="sxs-lookup"><span data-stu-id="d4fcc-198">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="d4fcc-199">Verknüpfen Sie das Konto, das Sie für die Registrierung als Windows Insider verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-199">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="d4fcc-200">Windows Insider geht jetzt zu Kanälen.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-200">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="d4fcc-201">Der **Fast-Ring** wird zum **Dev-Kanal,** der **langsame** Ring zum **Betakanal** und der **Release preview-Ring** zum **Releasevorschaukanal.**</span><span class="sxs-lookup"><span data-stu-id="d4fcc-201">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="d4fcc-202">Diese Zuordnung sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="d4fcc-202">Here is what that mapping looks like:</span></span>

![Windows Erklärung zu Insiderkanälen](images/WindowsInsiderChannels.png)

<span data-ttu-id="d4fcc-204">Weitere Informationen finden Sie unter [Introducing Windows Insider Channels (Einführung Windows Insider Channels)](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) in Windows Blogs.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-204">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="d4fcc-205">Wählen Sie dann **Aktive Entwicklung von Windows** aus, wählen Sie aus, ob Sie Dev **Channel** oder **Betakanal** Builds erhalten möchten, und überprüfen Sie die Programmbedingungen.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-205">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="d4fcc-206">Wählen Sie **Confirm > Restart Now (Jetzt neu starten)** aus, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-206">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="d4fcc-207">Wechseln Sie nach dem Neustart Ihres Geräts zu **Einstellungen > Update & Security > Suchen nach Updates,** um den neuesten Build zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-207">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="d4fcc-208">Updatefehler 0x80070490 Problembearbeitung</span><span class="sxs-lookup"><span data-stu-id="d4fcc-208">Update error 0x80070490 work-around</span></span>

<span data-ttu-id="d4fcc-209">Wenn beim Aktualisieren im Dev- oder Betakanal ein Updatefehler 0x80070490 wird, versuchen Sie es mit der folgenden kurzfristigen Problemumgemeinung.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-209">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="d4fcc-210">Dies umfasst das Verschieben Ihres Insider-Kanals, das Aufnehmen des Updates und das anschließende Verschieben Ihres Insider-Kanals zurück.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-210">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <a name="stage-one---release-preview"></a><span data-ttu-id="d4fcc-211">Phase 1: Releasevorschau</span><span class="sxs-lookup"><span data-stu-id="d4fcc-211">Stage one - Release Preview</span></span>

1.  <span data-ttu-id="d4fcc-212">Einstellungen, Update & Security, Windows Insider Program, wählen Sie **Release Preview Channel (Releasevorschaukanal)** aus.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-212">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>

2.  <span data-ttu-id="d4fcc-213">Einstellungen, Update & Security, Windows Update, Suchen **nach Updates.**</span><span class="sxs-lookup"><span data-stu-id="d4fcc-213">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="d4fcc-214">Fahren Sie nach dem Update mit Phase 2 fort.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-214">After the update, continue on to Stage two.</span></span>

#### <a name="stage-two---dev-channel"></a><span data-ttu-id="d4fcc-215">Phase 2: Entwicklungskanal</span><span class="sxs-lookup"><span data-stu-id="d4fcc-215">Stage two - Dev Channel</span></span>

1. <span data-ttu-id="d4fcc-216">Einstellungen, Update & Security, Windows Insider Program, wählen Sie **Dev Channel** aus.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-216">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>

2. <span data-ttu-id="d4fcc-217">Einstellungen, Update & Security, Windows Update, Suchen **nach Updates.**</span><span class="sxs-lookup"><span data-stu-id="d4fcc-217">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="d4fcc-218">FFU-Download und Flash-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="d4fcc-218">FFU download and flash directions</span></span>

<span data-ttu-id="d4fcc-219">Zum Testen mit einer Flugsignierungs-FFU müssen Sie zunächst ihr Gerät entsperren, bevor Sie die flugsigniert-FFU blinken lassen.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-219">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>

1. <span data-ttu-id="d4fcc-220">Auf dem PC:</span><span class="sxs-lookup"><span data-stu-id="d4fcc-220">On PC:</span></span>
    1. <span data-ttu-id="d4fcc-221">Laden Sie FFU von auf Ihren PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) herunter.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-221">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="d4fcc-222">Installieren Sie ARC (Advanced Recovery Companion) über die Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="d4fcc-222">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="d4fcc-223">Bei HoloLens – Flight Unlock: Öffnen **Sie Einstellungen** Update  >  **& Security** Windows Insider  >  **Program,** und starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-223">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="d4fcc-224">Flash-FFU: Jetzt können Sie die mit Flugsignieren signierte FFU mit ARC flashen.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-224">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="d4fcc-225">Bereitstellen von Feedback und Melden von Problemen</span><span class="sxs-lookup"><span data-stu-id="d4fcc-225">Provide feedback and report issues</span></span>

<span data-ttu-id="d4fcc-226">Verwenden Sie [die Feedback-Hub-App](hololens-feedback.md) auf Ihrem HoloLens, um Feedback zu geben und Probleme zu melden.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-226">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="d4fcc-227">Die Verwendung von Feedback-Hub stellt sicher, dass alle erforderlichen Diagnoseinformationen enthalten sind, damit unsere Techniker das Problem schnell debuggen und beheben können.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-227">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="d4fcc-228">Probleme mit der chinesischen und japanischen Version von HoloLens sollten auf die gleiche Weise gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-228">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="d4fcc-229">Achten Sie darauf, dass Sie die Eingabeaufforderung akzeptieren, in der Sie gefragt werden, ob sie Feedback-Hub möchten, auf Ihren Ordner Dokumente zuzugreifen (wählen Sie **Ja** aus, wenn Sie dazu aufgefordert werden).</span><span class="sxs-lookup"><span data-stu-id="d4fcc-229">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <a name="note-for-developers"></a><span data-ttu-id="d4fcc-230">Hinweis für Entwickler</span><span class="sxs-lookup"><span data-stu-id="d4fcc-230">Note for developers</span></span>

<span data-ttu-id="d4fcc-231">Sie sind willkommen und sollten versuchen, Ihre Anwendungen mit Insider-Builds von HoloLens zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-231">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="d4fcc-232">Sehen Sie sich die [HoloLens Developer-Dokumentation](https://developer.microsoft.com/windows/mixed-reality/development) an, um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-232">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="d4fcc-233">Die gleichen Anweisungen funktionieren mit Insider-Builds von HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-233">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="d4fcc-234">Sie können die gleichen Builds von Unity und Visual Studio verwenden, die Sie bereits für HoloLens Entwicklung verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-234">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="d4fcc-235">Beenden des Empfangs von Insider-Builds</span><span class="sxs-lookup"><span data-stu-id="d4fcc-235">Stop receiving Insider builds</span></span>

<span data-ttu-id="d4fcc-236">Wenn Sie keine Insider-Builds von Windows Holographic mehr erhalten möchten, können Sie sich abmelden, wenn Ihr HoloLens einen Produktionsbuild ausführt, oder Sie können Ihr Gerät mit dem Advanced Recovery Companion wiederherstellen, um Ihr Gerät in einer Nicht-Insider-Version von Windows Holographic [wiederherzustellen.](hololens-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="d4fcc-236">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="d4fcc-237">Es gibt ein bekanntes Problem, bei dem Benutzer, die die Registrierung bei Insider Preview-Builds nach der manuellen Neuinstallation eines neuen Vorschaubuilds aufheben, einen Bluescreen erhalten.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-237">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="d4fcc-238">Anschließend müssen sie ihr Gerät manuell wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-238">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="d4fcc-239">Ausführliche Informationen dazu, ob Sie betroffen sind oder nicht, finden Sie in diesem [bekannten Problem.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="d4fcc-239">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>

<span data-ttu-id="d4fcc-240">So überprüfen Sie, ob ihr HoloLens einen Produktionsbuild ausführt:</span><span class="sxs-lookup"><span data-stu-id="d4fcc-240">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="d4fcc-241">Wechseln Sie zu **Einstellungen > System > About**, und suchen Sie die Buildnummer.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-241">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="d4fcc-242">[Informationen zu den Buildnummern für die Produktion finden Sie in den Versionshinweisen.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="d4fcc-242">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="d4fcc-243">So deaktivieren Sie Insider-Builds:</span><span class="sxs-lookup"><span data-stu-id="d4fcc-243">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="d4fcc-244">Wechseln Sie auf einer HoloLens, die einen Produktionsbuild ausführt, zu **Einstellungen > Update & Security > Windows Insider Program,** und wählen Sie **Insider-Builds beenden** aus.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-244">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="d4fcc-245">Befolgen Sie die Anweisungen, um Ihr Gerät zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-245">Follow the instructions to opt out your device.</span></span>
