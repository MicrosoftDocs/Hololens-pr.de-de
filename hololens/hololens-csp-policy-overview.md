---
title: Übersicht über CSPs und Geräteverwaltung konfigurieren
description: Erfahren Sie, wie Sie CSPs, Richtlinien und Geräteverwaltung mithilfe von Mobile Device Management und Bereitstellungspaketen konfigurieren.
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
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283246"
---
# <span data-ttu-id="5d09f-103">Übersicht über CSPs und Geräteverwaltung konfigurieren</span><span class="sxs-lookup"><span data-stu-id="5d09f-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="5d09f-104">IT-Administratoren können Richtlinieneinstellungen auf HoloLens 2 definieren und implementieren.</span><span class="sxs-lookup"><span data-stu-id="5d09f-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="5d09f-105">Die verwendeten Konfigurationseinstellungen sind abhängig vom Bereitstellungsszenario. Dabei bieten unternehmenseigene Geräte die umfassendsten Kontrollmöglichkeiten für die IT.</span><span class="sxs-lookup"><span data-stu-id="5d09f-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="5d09f-106">In Windows 10 sind Konfigurationsdienstanbieter (Configuration Service Providers, CSP) eine Schnittstelle zum Lesen, Festlegen, Ändern oder Löschen von Konfigurationseinstellungen auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="5d09f-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="5d09f-107">Diese Einstellungen sind mit Registrierungsschlüsseln oder Dateien verknüpft.</span><span class="sxs-lookup"><span data-stu-id="5d09f-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="5d09f-108">Einige Konfigurationsdienstanbieter unterstützen das WAP-Format, andere syncML und einige unterstützen beide.</span><span class="sxs-lookup"><span data-stu-id="5d09f-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="5d09f-109">Weitere Informationen zu Windows 10 Holographic-Geräteverwaltungs-CSPs finden Sie in der vollständigen Liste der [CSPs, die auf HoloLens-Geräten unterstützt werden.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)</span><span class="sxs-lookup"><span data-stu-id="5d09f-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="5d09f-110">#A0 können den Richtlinien-CSP auch auf Geräten verwalten. Eine vollständige Liste der von [HoloLens 2 unterstützten Richtlinien-CSPs finden Sie in der liste.](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)</span><span class="sxs-lookup"><span data-stu-id="5d09f-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <span data-ttu-id="5d09f-111">Konfigurationsmethoden</span><span class="sxs-lookup"><span data-stu-id="5d09f-111">Configuration methods</span></span>

### <span data-ttu-id="5d09f-112">Konfigurieren mit MDM</span><span class="sxs-lookup"><span data-stu-id="5d09f-112">Configure with MDM</span></span>

<span data-ttu-id="5d09f-113">CSPs und Richtlinien können problemlos auf jedem persönlichen oder Unternehmensgerät verwaltet werden, das in einem MDM-System registriert ist.</span><span class="sxs-lookup"><span data-stu-id="5d09f-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="5d09f-114">Sobald ein Gerät in Ihrer MDM-Lösung registriert ist, können Sie dieses Gerät oder gerätesatz mithilfe von Gerätekonfigurationen verwalten.</span><span class="sxs-lookup"><span data-stu-id="5d09f-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="5d09f-115">Erfahren Sie mehr über die [Verwaltung Ihrer HoloLens-Geräte über MDM.](hololens-mdm-configure.md)</span><span class="sxs-lookup"><span data-stu-id="5d09f-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <span data-ttu-id="5d09f-116">Konfigurieren mit Bereitstellungspaketen</span><span class="sxs-lookup"><span data-stu-id="5d09f-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="5d09f-117">HoloLens 2 unterstützt auch das Festlegen einer begrenzten Gruppe von #A0 für HoloLens 2-Geräte über benutzerdefinierte Bereitstellungspakete.</span><span class="sxs-lookup"><span data-stu-id="5d09f-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="5d09f-118">Bereitstellungspakete werden in der Regel für nicht von MDM verwaltete Geräte genutzt und müssen manuell auf jedes Gerät angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="5d09f-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="5d09f-119">Lesen Sie Informationen zum Erstellen [benutzerdefinierter Bereitstellungspakete für HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning)</span><span class="sxs-lookup"><span data-stu-id="5d09f-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span>

## <span data-ttu-id="5d09f-120">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5d09f-120">Configurations</span></span>

### <span data-ttu-id="5d09f-121">Allgemeine Geräteeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="5d09f-121">Common device restrictions</span></span>

<span data-ttu-id="5d09f-122">Einige Geräteeinschränkungen sind so einfach und deaktivieren eine Funktionalität oder Verbindung mit dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="5d09f-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="5d09f-123">Weitere Informationen zu diesen Informationen finden Sie unter [allgemeinen Geräteeinschränkungen.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="5d09f-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <span data-ttu-id="5d09f-124">Kioskmodi</span><span class="sxs-lookup"><span data-stu-id="5d09f-124">Kiosk modes</span></span>

<span data-ttu-id="5d09f-125">Verwenden Sie den Kioskmodus, um zu steuern, welche Identitäten standardmäßig auf welche Apps zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="5d09f-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="5d09f-126">Kioske können für eine einzelne App oder eine Benutzeroberfläche mit mehreren Apps verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5d09f-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="5d09f-127">Kioskkonfigurationen reichen von einer einzelnen App für alle Benutzer des Geräts bis zu verschiedenen Auswahlen von Apps für unterschiedliche Gruppen.</span><span class="sxs-lookup"><span data-stu-id="5d09f-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="5d09f-128">Der Kioskmodus hält "zugelassene Apps" nicht am Starten anderer Apps ab und sollte niemals verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5d09f-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="5d09f-129">Weitere Informationen finden [Sie in den Kioskmodi und deren Verwendung.](hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="5d09f-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <span data-ttu-id="5d09f-130">Sichtbarkeit der Einstellungsseite</span><span class="sxs-lookup"><span data-stu-id="5d09f-130">Settings Page Visibility</span></span>

<span data-ttu-id="5d09f-131">Verwenden Sie die Einstellungs-App-Richtlinie, um zu steuern, welche Identitäten standardmäßig zugriff auf Einstellungen haben.</span><span class="sxs-lookup"><span data-stu-id="5d09f-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="5d09f-132">Mithilfe dieser Richtlinie kann die App "Einstellungen" so konfiguriert werden, dass entweder nur die ausgewählten Seiten angezeigt oder alle ausgewählten Seiten ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="5d09f-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="5d09f-133">[Erfahren Sie, wie Sie die verfügbaren Seiten konfigurieren.](settings-uri-list.md)</span><span class="sxs-lookup"><span data-stu-id="5d09f-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="5d09f-134">Dieses Feature ist derzeit nur in [Windows-Insider-Builds verfügbar.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="5d09f-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="5d09f-135">Stellen Sie sicher, dass Geräte, für die Sie dieses Feature verwenden möchten, ab Build 19041.1349 verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5d09f-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <span data-ttu-id="5d09f-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="5d09f-136">WDAC</span></span>

<span data-ttu-id="5d09f-137">Verwenden Sie die WDAC-Konfiguration, um zu steuern, welche Apps/Prozesse zulässig/nicht gestartet werden dürfen, unabhängig davon, ob sich das System im Kioskmodus befindet oder nicht.</span><span class="sxs-lookup"><span data-stu-id="5d09f-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="5d09f-138">Sehen Sie sich unsere Übersicht für WDAC an.</span><span class="sxs-lookup"><span data-stu-id="5d09f-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
