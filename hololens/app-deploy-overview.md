---
title: 'Übersicht: App-Verwaltung'
description: Verschaffen Sie sich einen Überblick über die Mixed Reality-App-Verwaltung mit Verwaltung mobiler Geräte, Microsoft Store für Unternehmen und Bereitstellungspakete.
keywords: HoloLens, Benutzer, Konto, App, Anwendungsverwaltung,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635550"
---
# <a name="app-management-overview"></a><span data-ttu-id="a02d0-104">App-Verwaltung: Übersicht</span><span class="sxs-lookup"><span data-stu-id="a02d0-104">App Management: Overview</span></span>

<span data-ttu-id="a02d0-105">Sie können Apps auf vier verschiedenen Pfaden bereitstellen: **Mobile Geräteverwaltung (MDM),** **Microsoft Store für Unternehmen**, **Microsoft Store** oder durch Installation über **Bereitstellung**.</span><span class="sxs-lookup"><span data-stu-id="a02d0-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="a02d0-106">Mobile Geräteverwaltung (MDM)</span><span class="sxs-lookup"><span data-stu-id="a02d0-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="a02d0-107">Mit einer MDM-Lösung können IT-Entscheidungsträger und Administratoren ihre unternehmensspezifischen Apps privat automatisch installieren (pushen) oder Apps über den Store für eine Gruppe von Benutzern erwerben.</span><span class="sxs-lookup"><span data-stu-id="a02d0-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="a02d0-108">HoloLens-Geräte funktionieren am besten mit Microsoft Endpoint Manager (Intune) für [die Anwendungsverwaltung.](app-deploy-intune.md)</span><span class="sxs-lookup"><span data-stu-id="a02d0-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="a02d0-109">Intune bietet Benutzern auch eine feiner abgrenzende Kontrolle über IT-verwaltete Apps über die Unternehmensportal herunterladbare Benutzererfahrung.</span><span class="sxs-lookup"><span data-stu-id="a02d0-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="a02d0-110">Die folgenden Anweisungen gelten für Benutzer, die ihre Anwendungen mit Intune verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="a02d0-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="a02d0-111">Microsoft empfiehlt die Verwendung von Intune für die Anwendungs- und Geräteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="a02d0-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="a02d0-112">Mobile Geräteverwaltung (MDM) gilt für:</span><span class="sxs-lookup"><span data-stu-id="a02d0-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="a02d0-113">MDM bereitgestellt + Unternehmensportal</span><span class="sxs-lookup"><span data-stu-id="a02d0-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="a02d0-114">Line of Business-Apps (nicht öffentlich)</span><span class="sxs-lookup"><span data-stu-id="a02d0-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="a02d0-115">Manuelle Installation verfügbarer Anwendungen über Unternehmensportal</span><span class="sxs-lookup"><span data-stu-id="a02d0-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="a02d0-116">Pushen durch den Administrator durch die MDM-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="a02d0-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="a02d0-117">Automatisches Update über MDM</span><span class="sxs-lookup"><span data-stu-id="a02d0-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="a02d0-118">Microsoft Store für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="a02d0-118">Microsoft Store for Business</span></span>

<span data-ttu-id="a02d0-119">Das [Microsoft Store für Unternehmen](app-deploy-store-business.md) bietet IT-Entscheidungsträgern und Administratoren in Unternehmen das Suchen, Erwerben, Verwalten und Verteilen kostenloser und kostenpflichtiger Apps.</span><span class="sxs-lookup"><span data-stu-id="a02d0-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="a02d0-120">IT-Administratoren können Microsoft Store-Apps und private Line-of-Business-Apps in einem Bestand verwalten und lizenzen nach Bedarf zuweisen und wiederverwenden.</span><span class="sxs-lookup"><span data-stu-id="a02d0-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="a02d0-121">Weitere Informationen finden Sie unter [Voraussetzungen für die Verwendung der Microsoft Store für Unternehmen](/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="a02d0-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="a02d0-122">Die Microsoft Store für Unternehmen gilt für:</span><span class="sxs-lookup"><span data-stu-id="a02d0-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="a02d0-123">Öffentliche oder line of Business-Apps</span><span class="sxs-lookup"><span data-stu-id="a02d0-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="a02d0-124">Automatische Installation erforderlicher Anwendungen durch MDM-Zuordnung</span><span class="sxs-lookup"><span data-stu-id="a02d0-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="a02d0-125">Benutzer lädt Apps manuell herunter</span><span class="sxs-lookup"><span data-stu-id="a02d0-125">User manually downloads apps</span></span>
* <span data-ttu-id="a02d0-126">Automatische Aktualisierung</span><span class="sxs-lookup"><span data-stu-id="a02d0-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="a02d0-127">Microsoft Store-Apps</span><span class="sxs-lookup"><span data-stu-id="a02d0-127">Microsoft Store apps</span></span>

<span data-ttu-id="a02d0-128">Das Microsoft Store bietet IT-Entscheidungsträgern und Administratoren in Unternehmen das Suchen, Erwerben, Verwalten und Verteilen öffentlicher Apps.</span><span class="sxs-lookup"><span data-stu-id="a02d0-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="a02d0-129">Diese Microsoft Store gilt für:</span><span class="sxs-lookup"><span data-stu-id="a02d0-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="a02d0-130">Nur öffentliche Apps</span><span class="sxs-lookup"><span data-stu-id="a02d0-130">Public apps only</span></span>
* <span data-ttu-id="a02d0-131">Benutzer lädt Apps manuell herunter</span><span class="sxs-lookup"><span data-stu-id="a02d0-131">User manually downloads apps</span></span>
* <span data-ttu-id="a02d0-132">Automatisches Update, wenn eine Internetverbindung besteht</span><span class="sxs-lookup"><span data-stu-id="a02d0-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="a02d0-133">Weitere Informationen finden Sie unter [Holographic Store Apps](/hololens/holographic-store-apps).</span><span class="sxs-lookup"><span data-stu-id="a02d0-133">For more information, visit [Holographic Store Apps](/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="a02d0-134">Installieren über Bereitstellungspakete</span><span class="sxs-lookup"><span data-stu-id="a02d0-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="a02d0-135">[Mit](app-deploy-provisioning-package.md) Bereitstellungspaketen können Sie benutzerdefinierte oder line of Business-Apps installieren, sodass IT-Profis und Administratoren Apps schnell über USB auf einem lokalen Gerät installieren können.</span><span class="sxs-lookup"><span data-stu-id="a02d0-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="a02d0-136">Diese Installation kann ohne Internetverbindung und für jeden Identitätstyp erfolgen.</span><span class="sxs-lookup"><span data-stu-id="a02d0-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="a02d0-137">Die Installation über Bereitstellungspakete gilt für:</span><span class="sxs-lookup"><span data-stu-id="a02d0-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="a02d0-138">Line of Business/Selbst entwickelte (nicht öffentliche) Apps</span><span class="sxs-lookup"><span data-stu-id="a02d0-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="a02d0-139">Öffentliche Apps (wenn das Offlineinstallationsprogramm verfügbar ist)</span><span class="sxs-lookup"><span data-stu-id="a02d0-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="a02d0-140">Nur USB-Seitenladevorgang</span><span class="sxs-lookup"><span data-stu-id="a02d0-140">USB side-loading only</span></span>
* <span data-ttu-id="a02d0-141">Keine automatische Aktualisierung (manuelle Updates über Bereitstellungspaket erforderlich)</span><span class="sxs-lookup"><span data-stu-id="a02d0-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="a02d0-142">Installieren von Apps auf HoloLens 2 über App-Installer</span><span class="sxs-lookup"><span data-stu-id="a02d0-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="a02d0-143">Mithilfe [App-Installer](app-deploy-app-installer.md) können Benutzer einfach Apps auf lokalen Geräten installieren oder eine App für andere Benutzer freigeben, die mit anderen App-Installationsmethoden auf lokalen Geräten nicht vertraut HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a02d0-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="a02d0-144">Dies kann erfolgen, ohne den Entwicklermodus zu aktivieren oder Geräteportal.</span><span class="sxs-lookup"><span data-stu-id="a02d0-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="a02d0-145">Dies ist eine einfache Methode zum Verteilen einer vollständig erstellten App.</span><span class="sxs-lookup"><span data-stu-id="a02d0-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="a02d0-146">Unabhängig davon, ob Sie Ihre App einfach für einen anderen Benutzer mit einem HoloLens demo oder ihre App bereitstellen möchten, funktioniert diese Methode problemlos.</span><span class="sxs-lookup"><span data-stu-id="a02d0-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="a02d0-147">Die Installation über App-Installer gilt für:</span><span class="sxs-lookup"><span data-stu-id="a02d0-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="a02d0-148">Line of Business/Selbst entwickelte (nicht öffentliche) Apps</span><span class="sxs-lookup"><span data-stu-id="a02d0-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="a02d0-149">Nur side-load</span><span class="sxs-lookup"><span data-stu-id="a02d0-149">Side-load only</span></span>
* <span data-ttu-id="a02d0-150">Der Entwicklermodus oder das Geräteportal ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a02d0-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="a02d0-151">Einfache Installation durch Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="a02d0-151">Easy for end user to install</span></span>
