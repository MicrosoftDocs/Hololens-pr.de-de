---
title: Bereitstellungshandbuch – Mit der Cloud verbundene HoloLens 2-Bereitstellung im großen Maßstab mit Remote Assist – Wartung
description: Halten Sie sich mit unseren Tipps zur Wartung und Unterstützung von HoloLens-Geräten über ein cloudverbundenes Netzwerk auf dem Laufenden.
keywords: HoloLens, Verwaltung, mit der Cloud verbunden, Remote Assist, AAD, Azure AD, MDM, Verwaltung mobiler Geräte
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
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283896"
---
# <span data-ttu-id="50ec8-104">Verwalten – Leitfaden mit Verbindung mit der Cloud</span><span class="sxs-lookup"><span data-stu-id="50ec8-104">Maintain - Cloud connected Guide</span></span>

## <span data-ttu-id="50ec8-105">Updates</span><span class="sxs-lookup"><span data-stu-id="50ec8-105">Updates</span></span>

<span data-ttu-id="50ec8-106">Microsoft hat Windows Update for Business entwickelt, um IT-Administratoren weitere Verwaltungsfunktionen rund um Windows Update bereitzustellen, wie beispielsweise die Möglichkeit, Updates für Gruppen von Geräten bereitzustellen oder Wartungszeitfenster für die Installation von Updates festzulegen.</span><span class="sxs-lookup"><span data-stu-id="50ec8-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="50ec8-107">Erfahren Sie, wie [Sie HoloLens-Updates](https://docs.microsoft.com/hololens/hololens-updates) verwalten, einschließlich geplanter Tage, geplanter Zeit und Festlegen der Aktiven Stunden auf dem Gerät, damit sie außerhalb der Arbeitszeiten aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="50ec8-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="50ec8-108">Remote Assist ist eine In-Box App und kann über die Microsoft Store-App aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="50ec8-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="50ec8-109">Für alle Apps, die über den Microsoft Store heruntergeladen werden, können sie manuell über [die Microsoft](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) Store-App selbst aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="50ec8-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <span data-ttu-id="50ec8-110">Supportplan</span><span class="sxs-lookup"><span data-stu-id="50ec8-110">Support Plan</span></span>

<span data-ttu-id="50ec8-111">Ein Supportplan ist eine hervorragende Sache.</span><span class="sxs-lookup"><span data-stu-id="50ec8-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="50ec8-112">Es ist hilfreich, jemanden oder eine Gruppe in der Problembehandlung für den Registrierungsprozess auf HoloLens-Geräten und die allgemeine Verwendung des Geräts HoloLens in Ihrer Organisation zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="50ec8-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="50ec8-113">Damit Ihre Benutzer ihre Probleme schneller beheben können, empfehlen wir, dass Ihr Eskalationsprozess in ähnlicher Weise wie in dieser Reihenfolge behandelt wird:</span><span class="sxs-lookup"><span data-stu-id="50ec8-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="50ec8-114">Ihr Supportdesk.</span><span class="sxs-lookup"><span data-stu-id="50ec8-114">Your Support desk.</span></span>
2. <span data-ttu-id="50ec8-115">Ihr HoloLens -Expertenteam</span><span class="sxs-lookup"><span data-stu-id="50ec8-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="50ec8-116">[HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [Dokumentation zur Problembehandlung bei HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="50ec8-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="50ec8-117">Hilfe und Support zu Windows</span><span class="sxs-lookup"><span data-stu-id="50ec8-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <span data-ttu-id="50ec8-118">Entwicklungsplan</span><span class="sxs-lookup"><span data-stu-id="50ec8-118">Development Plan</span></span>

<span data-ttu-id="50ec8-119">Nachdem Ihr Gerät erfolgreich registriert wurde, sind Sie nun bereit, Branchen-Apps (Line of Business Apps) auf Ihren Geräten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="50ec8-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="50ec8-120">Dabei handelt es sich um benutzerdefinierte Apps, die für ihre&#39;erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="50ec8-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="50ec8-121">Wenn Sie bereits über eine Line-of-Business-App verfügen, können&#39;Über [MDM bereitstellen.](https://docs.microsoft.com/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="50ec8-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="50ec8-122">Wenn Sie&#39;eine andere Methode bevorzugen, lesen Sie die Übersicht über die Anwendungsbereitstellung für [HoloLens 2,](https://docs.microsoft.com/hololens/app-deploy-overview) um weitere Methoden zum Bereitstellen Ihrer Branchen-App auf Ihren Geräten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="50ec8-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="50ec8-123">Wenn Sie&#39;ihre eigene Branchen-App noch nicht erstellt haben oder sich noch im Erstellungsprozess [](https://docs.microsoft.com/windows/mixed-reality/design/design) befinden, lesen Sie unsere Mixed Reality-Entwicklungs-Dokumente, um mit dem Entwerfen und Erstellen von Prototypen zu beginnen oder die Kernkonzepte für die ersten Schritte bei der [Mixed -Reality-Entwicklung](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr) zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="50ec8-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <span data-ttu-id="50ec8-124">-Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="50ec8-124">Device Management</span></span> 

<span data-ttu-id="50ec8-125">In diesem Handbuch wurde zwar von der Einrichtung der Mobile Device Management (MDM) gesprochen, es wurde jedoch nicht zum Anwenden von Geräteeinschränkungen oder Richtlinien auf Geräte verwendet.</span><span class="sxs-lookup"><span data-stu-id="50ec8-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="50ec8-126">Die Geräteverwaltung kann verwendet werden, um den Zugriff durch Pushen von Zertifikaten zu ermöglichen oder den Zugriff mit einer Vielzahl von Geräteeinschränkungen einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="50ec8-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="50ec8-127">In vielen Fällen können Geräte Konnektivitätseinschränkungen haben, z. B. Bluetooth, VPN, USB oder sogar das Deaktivieren des Zugriffs auf die Kamera oder das Mikrofon.</span><span class="sxs-lookup"><span data-stu-id="50ec8-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="50ec8-128">Wenn Sie eines dieser Interessen haben, empfehlen wir Ihnen, unsere Seite mit den allgemeinen [Geräteeinschränkungen zu lesen.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="50ec8-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="50ec8-129">Es gibt weitere komplexere Geräteeinschränkungen, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="50ec8-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="50ec8-130">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="50ec8-130">Such as:</span></span>

- <span data-ttu-id="50ec8-131">Beschränken der Seiten, die in der App "Einstellungen" angezeigt werden können, mithilfe von [SettingsPageVisibility,](settings-uri-list.md)sodass Benutzer nur auf die Einstellungen zugreifen können, die sie anpassen müssen, z. B. ändern Wi-Fi Verbindung.</span><span class="sxs-lookup"><span data-stu-id="50ec8-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="50ec8-132">Verwenden [Sie den Kioskmodus,](hololens-kiosk.md) um die Benutzeroberfläche für Benutzer auf einem Gerät zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="50ec8-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="50ec8-133">Sie können kiosks so festlegen, dass eine einzelne App oder mehrere Apps mit einer benutzerdefinierten Startseite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="50ec8-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="50ec8-134">Kioske können auch verschiedenen Benutzern unterschiedliche Erfahrungen bieten.</span><span class="sxs-lookup"><span data-stu-id="50ec8-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="50ec8-135">[Windows-Anwendungssteuerung (Windows Application Control, WDAC),](windows-defender-application-control-wdac.md) damit bestimmte Apps oder Prozesse nicht vollständig gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="50ec8-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="50ec8-136">Wenn Sie mehr über die verschiedenen Methoden der Geräteverwaltung oder Geräteeinschränkungen erfahren möchten, gehen Sie wie im nächsten Schritt vor, und lesen Sie die Übersicht über die Geräteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="50ec8-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <span data-ttu-id="50ec8-137">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="50ec8-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="50ec8-138">CsPs und Geräteverwaltung (Übersicht) lesen</span><span class="sxs-lookup"><span data-stu-id="50ec8-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)