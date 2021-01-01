---
title: Bereitstellungshandbuch – Cloud Connected HoloLens 2-Bereitstellung im Maßstab mit Remote Unterstützung – verwalten
description: Tipps zum Verwalten von HoloLens-Geräten über ein mit der Cloud verbundenes Netzwerk
keywords: HoloLens, Verwaltung, Cloud Connected, Remote Assist, AAD, Azure AD, MDM, Verwaltung mobiler Geräte
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
ms.openlocfilehash: 8117c73516d2775ec67f37bad524bcf377ece2e5
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252696"
---
# <span data-ttu-id="414fb-104">Verwalten-Cloud Connected-Leitfaden</span><span class="sxs-lookup"><span data-stu-id="414fb-104">Maintain - Cloud connected Guide</span></span>

## <span data-ttu-id="414fb-105">Updates</span><span class="sxs-lookup"><span data-stu-id="414fb-105">Updates</span></span>

<span data-ttu-id="414fb-106">Microsoft hat Windows Update for Business entwickelt, um IT-Administratoren weitere Verwaltungsfunktionen rund um Windows Update bereitzustellen, wie beispielsweise die Möglichkeit, Updates für Gruppen von Geräten bereitzustellen oder Wartungszeitfenster für die Installation von Updates festzulegen.</span><span class="sxs-lookup"><span data-stu-id="414fb-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="414fb-107">Hier erfahren Sie, wie Sie [HoloLens-Updates verwalten](https://docs.microsoft.com/hololens/hololens-updates) , einschließlich geplanter Tage, geplanter Zeit und festlegen aktiver Stunden auf dem Gerät, damit es außerhalb der Arbeitszeiten aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="414fb-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="414fb-108">Bei der Remote Unterstützung handelt es sich um eine In-Box-APP, die über die Microsoft Store-APP aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="414fb-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="414fb-109">Für alle apps, die über den Microsoft Store heruntergeladen werden, können Sie [über die Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) -APP selbst manuell aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="414fb-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <span data-ttu-id="414fb-110">Supportplan</span><span class="sxs-lookup"><span data-stu-id="414fb-110">Support Plan</span></span>

<span data-ttu-id="414fb-111">Ein Support Plan eignet sich hervorragend für den richtigen Ort.</span><span class="sxs-lookup"><span data-stu-id="414fb-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="414fb-112">Wenn Sie eine Person oder eine Gruppe haben, die bei der Problembehandlung des Registrierungsvorgangs auf HoloLens-Geräten geschult wurde, und auch die allgemeine Verwendung des HoloLens-Geräts in Ihrer Organisation ist hilfreich.</span><span class="sxs-lookup"><span data-stu-id="414fb-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="414fb-113">Damit Ihre Benutzer eine schnellere Lösung ihrer Probleme erhalten können, empfehlen wir, dass Ihr Eskalationsprozess auf ähnliche Weise wie in dieser Reihenfolge gehandhabt wird:</span><span class="sxs-lookup"><span data-stu-id="414fb-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="414fb-114">Ihr Support-Desk.</span><span class="sxs-lookup"><span data-stu-id="414fb-114">Your Support desk.</span></span>
2. <span data-ttu-id="414fb-115">Ihr HoloLens-Expertenteam</span><span class="sxs-lookup"><span data-stu-id="414fb-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="414fb-116">[HoloLens-Dokumente](https://docs.microsoft.com/hololens/)  /  [HoloLens-Problembehandlungsdokumentation](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="414fb-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="414fb-117">Hilfe und Support zu Windows</span><span class="sxs-lookup"><span data-stu-id="414fb-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <span data-ttu-id="414fb-118">Entwicklungs Plan</span><span class="sxs-lookup"><span data-stu-id="414fb-118">Development Plan</span></span>

<span data-ttu-id="414fb-119">Nachdem Sie Ihr Gerät erfolgreich registriert haben, sind Sie nun bereit, Geschäftsbereichs-Apps (Lob-Apps) auf Ihren Geräten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="414fb-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="414fb-120">Hierbei handelt es sich um benutzerdefinierte apps, die für Ihre Organisation&#39;Anforderungen entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="414fb-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="414fb-121">Wenn Sie bereits über eine Branchen-App verfügen,&#39;Sie bereit, [Ihre APP über MDM bereitzustellen](https://docs.microsoft.com/hololens/app-deploy-intune).</span><span class="sxs-lookup"><span data-stu-id="414fb-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="414fb-122">Wenn Sie eine andere Methode&#39;d bevorzugen, lesen Sie die [Übersicht zur Anwendungsbereitstellung für HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) , um weitere Methoden zum Bereitstellen Ihrer Lob-App auf Ihren Geräten zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="414fb-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="414fb-123">Wenn Sie noch keine eigene Lob-app erstellen oder sich noch im Prozess der Erstellung befinden&#39;, überprüfen Sie unsere Dokumentation zur Mixed-Reality-Entwicklung, um mit dem [Entwerfen und Prototypen zu beginnen](https://docs.microsoft.com/windows/mixed-reality/design/design) oder die grundlegenden Konzepte für den Einstieg in die [Mixed-Reality-Entwicklung kennenzulernen.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="414fb-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <span data-ttu-id="414fb-124">-Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="414fb-124">Device Management</span></span> 

<span data-ttu-id="414fb-125">Während dieses Leitfadens zum Einrichten der Verwaltung mobiler Geräte (MDM) gesprochen wurde, wurde es nicht verwendet, um Geräteeinschränkungen anzuwenden oder Richtlinien auf Geräte anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="414fb-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="414fb-126">Die Geräteverwaltung kann sowohl dazu verwendet werden, um den Zugriff zu ermöglichen, indem Sie Zertifikate drücken, als auch den Zugriff mit einer Reihe von Geräteeinschränkungen einschränken.</span><span class="sxs-lookup"><span data-stu-id="414fb-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="414fb-127">In vielen Fällen können Geräte Verbindungseinschränkungen wie Bluetooth, VPN, USB oder sogar das Ausschalten des Zugriffs auf die Kamera oder das Mikrofon aufweisen.</span><span class="sxs-lookup"><span data-stu-id="414fb-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="414fb-128">Wenn Ihnen eine dieser Interessen zusteht, empfehlen wir Ihnen, unsere [Seite mit den allgemeinen Geräteeinschränkungen](hololens-common-device-restrictions.md)zu lesen.</span><span class="sxs-lookup"><span data-stu-id="414fb-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="414fb-129">Es gibt weitere komplexere Geräteeinschränkungen, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="414fb-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="414fb-130">Wie:</span><span class="sxs-lookup"><span data-stu-id="414fb-130">Such as:</span></span>

- <span data-ttu-id="414fb-131">Einschränken der Seiten, die mithilfe von [SettingsPageVisibility](settings-uri-list.md)in der Einstellungs-APP angezeigt werden können, sodass Benutzer nur auf die Einstellungen zugreifen können, die Sie anpassen müssen, beispielsweise das Ändern der Wi-Fi Verbindung.</span><span class="sxs-lookup"><span data-stu-id="414fb-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="414fb-132">Verwenden Sie den [Kiosk Modus](hololens-kiosk.md) , um die Benutzeroberfläche zu begrenzen, die Benutzern auf einem Gerät angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="414fb-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="414fb-133">Sie können Kioske so einstellen, dass eine einzelne APP oder mehrere apps mit einer benutzerdefinierten Startseite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="414fb-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="414fb-134">Kioske können auch verschiedenen Benutzern unterschiedliche Erfahrungen präsentieren.</span><span class="sxs-lookup"><span data-stu-id="414fb-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="414fb-135">[Windows-Anwendungssteuerung (WDAC)](windows-defender-application-control-wdac.md) , damit bestimmte Apps oder Prozesse nicht vollständig gestartet werden können.</span><span class="sxs-lookup"><span data-stu-id="414fb-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="414fb-136">Wenn Sie mehr über die unterschiedlichen Methoden der Geräteverwaltung oder Geräteeinschränkungen erfahren möchten, führen Sie den nächsten Schritt aus, und lesen Sie unsere Übersicht zur Geräteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="414fb-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <span data-ttu-id="414fb-137">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="414fb-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="414fb-138">Lesen der Übersicht über LSP und Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="414fb-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)