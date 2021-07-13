---
title: Übersicht über CSPs und Geräteverwaltung konfigurieren
description: Erfahren Sie, wie Sie CSPs, Richtlinien und Geräteverwaltung mithilfe von Mobilen Geräteverwaltung und Bereitstellungspaketen konfigurieren.
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
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640456"
---
# <a name="configure-csps-and-device-management-overview"></a><span data-ttu-id="af880-103">Übersicht über CSPs und Geräteverwaltung konfigurieren</span><span class="sxs-lookup"><span data-stu-id="af880-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="af880-104">IT-Administratoren können Richtlinieneinstellungen für HoloLens 2 definieren und implementieren.</span><span class="sxs-lookup"><span data-stu-id="af880-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="af880-105">Die verwendeten Konfigurationseinstellungen sind abhängig vom Bereitstellungsszenario. Dabei bieten unternehmenseigene Geräte die umfassendsten Kontrollmöglichkeiten für die IT.</span><span class="sxs-lookup"><span data-stu-id="af880-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="af880-106">In Windows 10 sind Konfigurationsdienstanbieter (Configuration Service Providers, CSP) eine Schnittstelle zum Lesen, Festlegen, Ändern oder Löschen von Konfigurationseinstellungen auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="af880-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="af880-107">Diese Einstellungen sind mit Registrierungsschlüsseln oder Dateien verknüpft.</span><span class="sxs-lookup"><span data-stu-id="af880-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="af880-108">Einige Konfigurationsdienstanbieter unterstützen das WAP-Format, einige unterstützen SyncML und andere beides.</span><span class="sxs-lookup"><span data-stu-id="af880-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="af880-109">Weitere Informationen zu Windows 10 Holographic-Geräteverwaltungs-CSPs finden Sie in der vollständigen Liste der [in HoloLens Geräten unterstützten CSPs.](/windows/client-management/mdm/configuration-service-provider-reference#hololens)</span><span class="sxs-lookup"><span data-stu-id="af880-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="af880-110">IT-Administratoren können richtlinien-CSP auch auf Geräten verwalten. Die vollständige Liste der [Richtlinien-CSPs,](/windows/client-management/mdm/policy-csps-supported-by-hololens2)die von HoloLens 2 unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="af880-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <a name="configuration-methods"></a><span data-ttu-id="af880-111">Konfigurationsmethoden</span><span class="sxs-lookup"><span data-stu-id="af880-111">Configuration methods</span></span>

### <a name="configure-with-mdm"></a><span data-ttu-id="af880-112">Konfigurieren mit MDM</span><span class="sxs-lookup"><span data-stu-id="af880-112">Configure with MDM</span></span>

<span data-ttu-id="af880-113">CSPs und Richtlinien können problemlos auf jedem persönlichen oder Unternehmensgerät verwaltet werden, das in einem MDM-System registriert ist.</span><span class="sxs-lookup"><span data-stu-id="af880-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="af880-114">Sobald ein Gerät in Ihrer MDM-Lösung registriert ist, können Sie dieses Gerät oder eine Gruppe von Geräten mithilfe von Gerätekonfigurationen verwalten.</span><span class="sxs-lookup"><span data-stu-id="af880-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="af880-115">Erfahren Sie mehr über das [Verwalten Ihrer HoloLens-Geräte über MDM.](hololens-mdm-configure.md)</span><span class="sxs-lookup"><span data-stu-id="af880-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <a name="configure-with-provisioning-packages"></a><span data-ttu-id="af880-116">Konfigurieren mit Bereitstellungspaketen</span><span class="sxs-lookup"><span data-stu-id="af880-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="af880-117">HoloLens 2 unterstützt auch das Festlegen eines begrenzten Satzes von CSP-Konfigurationen für HoloLens 2 Geräte über benutzerdefinierte Bereitstellungspakete.</span><span class="sxs-lookup"><span data-stu-id="af880-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="af880-118">Bereitstellungspakete werden in der Regel für Nicht-MDM-verwaltete Geräte genutzt und müssen manuell auf jedes Gerät angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="af880-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="af880-119">Lesen Sie Informationen zum Erstellen von [benutzerdefinierten Bereitstellungspaketen für HoloLens](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="af880-119">Read information on building custom [Provisioning Packages for HoloLens](hololens-provisioning.md).</span></span>

## <a name="configurations"></a><span data-ttu-id="af880-120">Configurations</span><span class="sxs-lookup"><span data-stu-id="af880-120">Configurations</span></span>

### <a name="common-device-restrictions"></a><span data-ttu-id="af880-121">Allgemeine Geräteeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="af880-121">Common device restrictions</span></span>

<span data-ttu-id="af880-122">Einige Geräteeinschränkungen sind so einfach und deaktivieren eine Funktionalität oder Verbindung mit dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="af880-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="af880-123">Weitere Informationen zu diesen Finden Sie unter [Allgemeine Geräteeinschränkungen.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="af880-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <a name="kiosk-modes"></a><span data-ttu-id="af880-124">Kioskmodi</span><span class="sxs-lookup"><span data-stu-id="af880-124">Kiosk modes</span></span>

<span data-ttu-id="af880-125">Verwenden Sie den Kioskmodus, um zu steuern, welche Identitäten standardmäßig Zugriff auf welche Apps haben.</span><span class="sxs-lookup"><span data-stu-id="af880-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="af880-126">Kiosks können für eine einzelne App oder mehrere App-Benutzeroberflächen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="af880-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="af880-127">Kioskkonfigurationen reichen von einer einzelnen App für alle Benutzer des Geräts bis hin zu unterschiedlichen Apps für verschiedene Gruppen.</span><span class="sxs-lookup"><span data-stu-id="af880-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="af880-128">Der Kioskmodus hindert "zulässige Apps" nicht daran, andere Apps zu starten, und war nie dafür vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="af880-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="af880-129">Weitere Informationen [finden Sie unter Kioskmodi und deren Verwendung.](hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="af880-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <a name="settings-page-visibility"></a><span data-ttu-id="af880-130">Einstellungen Seitensichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="af880-130">Settings Page Visibility</span></span>

<span data-ttu-id="af880-131">Verwenden Sie Einstellungen App-Richtlinie, um zu steuern, welche Identitäten standardmäßig Zugriff auf Einstellungen haben.</span><span class="sxs-lookup"><span data-stu-id="af880-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="af880-132">Mit dieser Richtlinie kann die Einstellungen-App so konfiguriert werden, dass entweder nur die ausgewählten Seiten angezeigt oder alle ausgewählten Seiten ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="af880-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="af880-133">[Erfahren Sie, wie Sie die verfügbaren Seiten konfigurieren.](settings-uri-list.md)</span><span class="sxs-lookup"><span data-stu-id="af880-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="af880-134">Dieses Feature ist derzeit nur in [Windows Insider-Builds](hololens-insider.md)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="af880-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="af880-135">Stellen Sie sicher, dass Geräte, für die Sie dieses Feature verwenden möchten, auf Build 19041.1349 oder mehr basieren.</span><span class="sxs-lookup"><span data-stu-id="af880-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <a name="wdac"></a><span data-ttu-id="af880-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="af880-136">WDAC</span></span>

<span data-ttu-id="af880-137">Verwenden Sie die WDAC-Konfiguration, um zu steuern, welche Apps/Prozesse gestartet werden dürfen bzw. nicht, unabhängig davon, ob sich das System im Kioskmodus befindet oder nicht.</span><span class="sxs-lookup"><span data-stu-id="af880-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="af880-138">Weitere Informationen finden Sie in unserer Übersicht für WDAC.</span><span class="sxs-lookup"><span data-stu-id="af880-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
