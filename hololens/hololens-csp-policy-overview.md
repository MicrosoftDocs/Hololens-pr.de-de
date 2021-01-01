---
title: Übersicht über CSPs und Geräteverwaltung konfigurieren
description: Konfigurieren von Kryptografiedienstanbieter, Richtlinien-und Geräteverwaltung
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c6da29506035525b1b1b5141a04603f63de1ef24
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252776"
---
# <span data-ttu-id="c92c3-103">Übersicht über CSPs und Geräteverwaltung konfigurieren</span><span class="sxs-lookup"><span data-stu-id="c92c3-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="c92c3-104">IT-Administratoren können Richtlinieneinstellungen auf HoloLens 2 definieren und implementieren.</span><span class="sxs-lookup"><span data-stu-id="c92c3-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="c92c3-105">Die verwendeten Konfigurationseinstellungen sind abhängig vom Bereitstellungsszenario. Dabei bieten unternehmenseigene Geräte die umfassendsten Kontrollmöglichkeiten für die IT.</span><span class="sxs-lookup"><span data-stu-id="c92c3-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="c92c3-106">In Windows 10 sind Configuration Service Providers (CSP) eine Schnittstelle zum Lesen, festlegen, ändern oder Löschen von Konfigurationseinstellungen auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="c92c3-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="c92c3-107">Diese Einstellungen sind mit Registrierungsschlüsseln oder Dateien verknüpft.</span><span class="sxs-lookup"><span data-stu-id="c92c3-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="c92c3-108">Einige Konfigurationsdienst Anbieter unterstützen das WAP-Format, einige unterstützen SyncML und einige unterstützen beide.</span><span class="sxs-lookup"><span data-stu-id="c92c3-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="c92c3-109">Weitere Informationen zu Windows 10 holographischen Device Management-Kryptografiedienstanbieter finden Sie in der vollständigen Liste der [in HoloLens-Geräten unterstützten Kryptografiedienstanbieter](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span><span class="sxs-lookup"><span data-stu-id="c92c3-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="c92c3-110">IT-Administratoren können auch Richtlinien-CSP auf Geräten verwalten, finden Sie in der vollständigen Liste der [Richtlinien Kryptografiedienstanbieter, die von HoloLens 2 unterstützt](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)werden.</span><span class="sxs-lookup"><span data-stu-id="c92c3-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <span data-ttu-id="c92c3-111">Konfigurationsmethoden</span><span class="sxs-lookup"><span data-stu-id="c92c3-111">Configuration methods</span></span>

### <span data-ttu-id="c92c3-112">Konfigurieren mit MDM</span><span class="sxs-lookup"><span data-stu-id="c92c3-112">Configure with MDM</span></span>

<span data-ttu-id="c92c3-113">Kryptografiedienstanbieter und Richtlinien können auf allen Personen-oder Unternehmensgeräten, die in einem MDM-System registriert sind, problemlos verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="c92c3-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="c92c3-114">Nachdem ein Gerät für Ihre MDM-Lösung registriert wurde, können Sie dieses Gerät oder eine Gruppe von Geräten mithilfe von Gerätekonfigurationen verwalten.</span><span class="sxs-lookup"><span data-stu-id="c92c3-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="c92c3-115">Erfahren Sie mehr darüber, wie [Sie Ihre HoloLens-Geräte über MDM verwalten](hololens-mdm-configure.md).</span><span class="sxs-lookup"><span data-stu-id="c92c3-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <span data-ttu-id="c92c3-116">Konfigurieren mit Bereitstellungspaketen</span><span class="sxs-lookup"><span data-stu-id="c92c3-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="c92c3-117">HoloLens 2 unterstützt auch das Festlegen eines eingeschränkten Satzes von CSP-Konfigurationen für HoloLens 2-Geräte über benutzerdefinierte Bereitstellungspakete.</span><span class="sxs-lookup"><span data-stu-id="c92c3-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="c92c3-118">Bereitstellungspakete werden in der Regel für nicht-MDM-verwaltete Geräte genutzt und müssen manuell auf jedes Gerät angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c92c3-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="c92c3-119">Lesen Sie Informationen zum Erstellen benutzerdefinierter [Bereitstellungspakete für HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="c92c3-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span>

## <span data-ttu-id="c92c3-120">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="c92c3-120">Configurations</span></span>

### <span data-ttu-id="c92c3-121">Allgemeine Geräteeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="c92c3-121">Common device restrictions</span></span>

<span data-ttu-id="c92c3-122">Einige Geräteeinschränkungen sind so einfach, dass eine Funktion oder Verbindung mit dem Gerät deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="c92c3-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="c92c3-123">Weitere Informationen zu diesen Informationen finden Sie unter [Allgemeine Geräteeinschränkungen.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="c92c3-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <span data-ttu-id="c92c3-124">Kiosk Modi</span><span class="sxs-lookup"><span data-stu-id="c92c3-124">Kiosk modes</span></span>

<span data-ttu-id="c92c3-125">Verwenden Sie den Kiosk Modus, um zu steuern, welche Identitäten standardmäßig auf welche apps zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="c92c3-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="c92c3-126">Kiosks können für eine einzelne APP oder für mehrere App-Benutzeroberflächen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c92c3-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="c92c3-127">Kiosk-Konfigurationen sind von einer einzelnen App für alle Benutzer, die das Gerät verwenden, bis hin zu unterschiedlichen Auswahlmöglichkeiten für Apps für verschiedene Gruppen.</span><span class="sxs-lookup"><span data-stu-id="c92c3-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="c92c3-128">Im Kiosk Modus werden die "erlaubten Apps" nicht dazu angehalten, andere apps zu starten.</span><span class="sxs-lookup"><span data-stu-id="c92c3-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="c92c3-129">Weitere Informationen finden Sie unter [Informationen zu Kiosk Modi und deren Verwendung](hololens-kiosk.md).</span><span class="sxs-lookup"><span data-stu-id="c92c3-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <span data-ttu-id="c92c3-130">Sichtbarkeit der Seite "Einstellungen"</span><span class="sxs-lookup"><span data-stu-id="c92c3-130">Settings Page Visibility</span></span>

<span data-ttu-id="c92c3-131">Verwenden Sie die Einstellungen-App-Richtlinie, um zu steuern, welche Identitäten standardmäßig Zugriff auf Einstellungen haben.</span><span class="sxs-lookup"><span data-stu-id="c92c3-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="c92c3-132">Mit dieser Richtlinie kann die Einstellungs-APP so konfiguriert werden, dass entweder nur die Option "Seiten auswählen" oder "alle ausgewählten Seiten ausblenden" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c92c3-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="c92c3-133">[Hier erfahren Sie, wie Sie die verfügbaren Seiten konfigurieren](settings-uri-list.md).</span><span class="sxs-lookup"><span data-stu-id="c92c3-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="c92c3-134">Dieses Feature ist derzeit nur in [Windows-Insider-Builds](hololens-insider.md)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c92c3-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="c92c3-135">Stellen Sie sicher, dass Geräte, für die Sie dieses Feature verwenden möchten, auf Build 19041.1349 + sind.</span><span class="sxs-lookup"><span data-stu-id="c92c3-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <span data-ttu-id="c92c3-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="c92c3-136">WDAC</span></span>

<span data-ttu-id="c92c3-137">Verwenden Sie die WDAC-Konfiguration, um zu steuern, welche apps/Prozesse zugelassen/nicht zulässig sind, unabhängig davon, ob sich das System im Kioskmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="c92c3-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="c92c3-138">Schauen Sie sich unsere Übersicht für WDAC.</span><span class="sxs-lookup"><span data-stu-id="c92c3-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
