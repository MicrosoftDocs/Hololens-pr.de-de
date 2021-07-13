---
title: 'Bereitstellungshandbuch : Bereitstellung mit Cloudverbindung HoloLens 2 im großen Stil mit Remote Assist – Verwalten'
description: Bleiben Sie mit unseren Tipps zur Wartung und Unterstützung von HoloLens Geräten über ein mit der Cloud verbundenes Netzwerk auf dem laufenden.
keywords: HoloLens, Verwaltung, cloudverbunden, Remote Assist, AAD, Azure AD, MDM, Mobile Geräteverwaltung
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635159"
---
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="b20cc-104">Verwalten – Leitfaden für cloudverknannte Verbindungen</span><span class="sxs-lookup"><span data-stu-id="b20cc-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="b20cc-105">Aktualisierungen</span><span class="sxs-lookup"><span data-stu-id="b20cc-105">Updates</span></span>

<span data-ttu-id="b20cc-106">Microsoft hat Windows Update for Business entwickelt, um IT-Administratoren weitere Verwaltungsfunktionen rund um Windows Update bereitzustellen, wie beispielsweise die Möglichkeit, Updates für Gruppen von Geräten bereitzustellen oder Wartungszeitfenster für die Installation von Updates festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b20cc-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="b20cc-107">Erfahren Sie, wie Sie [HoloLens Updates verwalten,](/hololens/hololens-updates) einschließlich geplanter Tage, geplanter Zeit und Festlegen der aktiven Stunden auf dem Gerät, damit es außerhalb der Arbeitszeit aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="b20cc-107">Learn how to [manage HoloLens updates](/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="b20cc-108">Remote Assist ist eine In-Box-App und kann über die Microsoft Store-App aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b20cc-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="b20cc-109">Für alle Apps, die über die Microsoft Store heruntergeladen werden, können sie [manuell über die Microsoft Store](/hololens/holographic-store-apps#update-apps) App selbst aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b20cc-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="b20cc-110">Supportplan</span><span class="sxs-lookup"><span data-stu-id="b20cc-110">Support Plan</span></span>

<span data-ttu-id="b20cc-111">Ein Supportplan ist eine hervorragende Möglichkeit.</span><span class="sxs-lookup"><span data-stu-id="b20cc-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="b20cc-112">Es ist hilfreich, jemanden oder eine Gruppe mit der Problembehandlung des Registrierungsprozesses auf HoloLens Geräten und der allgemeinen Verwendung des HoloLens Geräts in Ihrer Organisation zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="b20cc-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="b20cc-113">Damit Ihre Benutzer ihre Probleme schneller lösen können, wird empfohlen, dass Ihr Eskalationsprozess in ähnlicher Weise wie die folgende Reihenfolge behandelt wird:</span><span class="sxs-lookup"><span data-stu-id="b20cc-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="b20cc-114">Ihr Support-Desk.</span><span class="sxs-lookup"><span data-stu-id="b20cc-114">Your Support desk.</span></span>
2. <span data-ttu-id="b20cc-115">Ihr HoloLens Expert-Team</span><span class="sxs-lookup"><span data-stu-id="b20cc-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="b20cc-116">[HoloLens-Dokumentation](/hololens/)  /  [HoloLens-Dokumentation zur Problembehandlung](/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="b20cc-116">[HoloLens Docs](/hololens/) / [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="b20cc-117">Wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="b20cc-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="b20cc-118">Entwicklungsplan</span><span class="sxs-lookup"><span data-stu-id="b20cc-118">Development Plan</span></span>

<span data-ttu-id="b20cc-119">Nachdem Ihr Gerät erfolgreich registriert wurde, können Sie branchenspezifische Apps (LOB-Apps) auf Ihren Geräten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b20cc-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="b20cc-120">Dies sind benutzerdefinierte Apps, die für Ihre Organisation&#39;Anforderungen erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="b20cc-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="b20cc-121">Wenn Sie bereits über eine Branchen-App verfügen,&#39;Sie bereit sein, [Ihre App über MDM bereitzustellen.](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="b20cc-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](/hololens/app-deploy-intune).</span></span> <span data-ttu-id="b20cc-122">Wenn Sie eine andere Methode bevorzugen&#39;, lesen Sie die Übersicht über die [Anwendungsbereitstellung für HoloLens 2,](/hololens/app-deploy-overview) um weitere Methoden zum Bereitstellen Ihrer BRANCHEN-App auf Ihren Geräten zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="b20cc-122">If you&#39;d prefer a different method, then review the [application deployment overview for HoloLens 2](/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="b20cc-123">Wenn Sie&#39;ihre eigene BRANCHEN-App noch nicht erstellt haben oder sich noch in der Erstellung befinden, lesen Sie unsere Mixed Reality-Entwicklungsdokumente, um mit dem Entwerfen und Erstellen von Prototypen zu [beginnen,](/windows/mixed-reality/design/design) oder lernen Sie die grundlegenden Konzepte für den Einstieg in die [Mixed Reality-Entwicklung kennen.](/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="b20cc-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="b20cc-124">-Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="b20cc-124">Device Management</span></span> 

<span data-ttu-id="b20cc-125">In diesem Leitfaden wurde zwar das Einrichten von Mobile Geräteverwaltung (MDM) erläutert, es wurde jedoch nicht verwendet, um Geräteeinschränkungen anzuwenden, oder Richtlinien wurden auf Geräte angewendet.</span><span class="sxs-lookup"><span data-stu-id="b20cc-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="b20cc-126">Die Geräteverwaltung kann verwendet werden, um den Zugriff durch Pushen von Zertifikaten zuzulassen oder den Zugriff mit einer Vielzahl von Geräteeinschränkungen einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="b20cc-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="b20cc-127">In vielen Fällen können Geräte Konnektivitätseinschränkungen aufweisen, z. B. Bluetooth, VPN, USB oder sogar den Zugriff auf die Kamera oder das Mikrofon deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b20cc-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="b20cc-128">Wenn Sie eines dieser Interessen haben, empfehlen wir Ihnen, unsere Seite mit [allgemeinen Geräteeinschränkungen](hololens-common-device-restrictions.md)zu lesen.</span><span class="sxs-lookup"><span data-stu-id="b20cc-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="b20cc-129">Es gibt weitere komplexere Geräteeinschränkungen, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b20cc-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="b20cc-130">Also beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="b20cc-130">Such as:</span></span>

- <span data-ttu-id="b20cc-131">Einschränken der Seiten, die in der Einstellungen-App angezeigt werden können, indem [SettingsPageVisibility](settings-uri-list.md)verwendet wird, sodass Benutzer nur auf die Einstellungen zugreifen können, die sie anpassen müssen, z. B. das Ändern ihrer Wi-Fi Verbindung.</span><span class="sxs-lookup"><span data-stu-id="b20cc-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="b20cc-132">Verwenden Sie den [Kioskmodus,](hololens-kiosk.md) um die Benutzeroberfläche einzuschränken, die Benutzern auf einem Gerät angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b20cc-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="b20cc-133">Sie können Kiosks so festlegen, dass eine einzelne App oder mehrere Apps mit einer benutzerdefinierten Startseite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b20cc-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="b20cc-134">Kiosks können verschiedenen Benutzern auch unterschiedliche Benutzererlebnisse bieten.</span><span class="sxs-lookup"><span data-stu-id="b20cc-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="b20cc-135">[Windows Anwendungssteuerung (Application Control, WDAC),](windows-defender-application-control-wdac.md) damit bestimmte Apps oder Prozesse nicht vollständig gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="b20cc-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="b20cc-136">Wenn Sie mehr über verschiedene Methoden der Geräteverwaltung oder Geräteeinschränkungen erfahren möchten, fahren Sie mit dem nächsten Schritt fort, und lesen Sie unsere Geräteverwaltung Übersicht.</span><span class="sxs-lookup"><span data-stu-id="b20cc-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="b20cc-137">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b20cc-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b20cc-138">Lesen Sie die CSPs und Geräteverwaltung Overview (Übersicht über CSPs und Geräteverwaltung).</span><span class="sxs-lookup"><span data-stu-id="b20cc-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)