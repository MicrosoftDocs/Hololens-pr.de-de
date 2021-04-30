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
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308644"
---
# <a name="app-management-overview"></a><span data-ttu-id="ccddf-104">App-Verwaltung: Übersicht</span><span class="sxs-lookup"><span data-stu-id="ccddf-104">App Management: Overview</span></span>

<span data-ttu-id="ccddf-105">Sie können Apps auf vier verschiedenen Pfaden bereitstellen: **Mobile Geräteverwaltung (MDM),** **Microsoft Store für Unternehmen**, **Microsoft Store** oder , indem Sie sie über Die **Bereitstellung installieren.**</span><span class="sxs-lookup"><span data-stu-id="ccddf-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="ccddf-106">Mobile Geräteverwaltung (MDM)</span><span class="sxs-lookup"><span data-stu-id="ccddf-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="ccddf-107">Mit einer MDM-Lösung können IT-Entscheidungsträger und Administratoren ihre unternehmensspezifischen Apps privat automatisch installieren (pushen) oder Apps über den Store für eine Gruppe von Benutzern erwerben.</span><span class="sxs-lookup"><span data-stu-id="ccddf-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="ccddf-108">HoloLens-Geräte funktionieren am besten mit Microsoft Endpoint Manager (Intune) für die [Anwendungsverwaltung.](app-deploy-intune.md)</span><span class="sxs-lookup"><span data-stu-id="ccddf-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="ccddf-109">Intune bietet Benutzern auch eine feiner abgrenzende Kontrolle über IT-verwaltete Apps über die Unternehmensportal herunterladbare Benutzererfahrung.</span><span class="sxs-lookup"><span data-stu-id="ccddf-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="ccddf-110">Die folgenden Anweisungen gelten für Benutzer, die ihre Anwendungen mit Intune verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="ccddf-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="ccddf-111">Microsoft empfiehlt die Verwendung von Intune für die Anwendungs- und Geräteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="ccddf-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="ccddf-112">Mobile Geräteverwaltung (MDM) gilt für:</span><span class="sxs-lookup"><span data-stu-id="ccddf-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="ccddf-113">MDM bereitgestellt + Unternehmensportal</span><span class="sxs-lookup"><span data-stu-id="ccddf-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="ccddf-114">Line of Business-Apps (nicht öffentlich)</span><span class="sxs-lookup"><span data-stu-id="ccddf-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="ccddf-115">Manuelle Installation verfügbarer Anwendungen über Unternehmensportal</span><span class="sxs-lookup"><span data-stu-id="ccddf-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="ccddf-116">Pushen durch den Administrator durch die MDM-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="ccddf-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="ccddf-117">Automatisches Update über MDM</span><span class="sxs-lookup"><span data-stu-id="ccddf-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="ccddf-118">Microsoft Store für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="ccddf-118">Microsoft Store for Business</span></span>

<span data-ttu-id="ccddf-119">Das [Microsoft Store für Unternehmen](app-deploy-store-business.md) bietet IT-Entscheidungsträgern und Administratoren in Unternehmen das Suchen, Erwerben, Verwalten und Verteilen kostenloser und kostenpflichtiger Apps.</span><span class="sxs-lookup"><span data-stu-id="ccddf-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="ccddf-120">IT-Administratoren können Microsoft Store-Apps und private Line-of-Business-Apps in einem Bestand verwalten und lizenzen nach Bedarf zuweisen und wiederverwenden.</span><span class="sxs-lookup"><span data-stu-id="ccddf-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="ccddf-121">Weitere Informationen finden Sie unter [Voraussetzungen für die Verwendung der Microsoft Store für Unternehmen](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="ccddf-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="ccddf-122">Die Microsoft Store für Unternehmen gilt für:</span><span class="sxs-lookup"><span data-stu-id="ccddf-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="ccddf-123">Öffentliche apps oder Line of Business-Apps</span><span class="sxs-lookup"><span data-stu-id="ccddf-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="ccddf-124">Automatische Installation erforderlicher Anwendungen über MDM-Zuordnung</span><span class="sxs-lookup"><span data-stu-id="ccddf-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="ccddf-125">Benutzer lädt Apps manuell herunter</span><span class="sxs-lookup"><span data-stu-id="ccddf-125">User manually downloads apps</span></span>
* <span data-ttu-id="ccddf-126">Automatische Aktualisierung</span><span class="sxs-lookup"><span data-stu-id="ccddf-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="ccddf-127">Microsoft Store-Apps</span><span class="sxs-lookup"><span data-stu-id="ccddf-127">Microsoft Store apps</span></span>

<span data-ttu-id="ccddf-128">Die Microsoft Store bietet IT-Entscheidungsträgern und Administratoren in Unternehmen die Möglichkeit, öffentliche Apps zu finden, zu erwerben, zu verwalten und zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="ccddf-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="ccddf-129">Diese Microsoft Store gilt für:</span><span class="sxs-lookup"><span data-stu-id="ccddf-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="ccddf-130">Nur öffentliche Apps</span><span class="sxs-lookup"><span data-stu-id="ccddf-130">Public apps only</span></span>
* <span data-ttu-id="ccddf-131">Benutzer lädt Apps manuell herunter</span><span class="sxs-lookup"><span data-stu-id="ccddf-131">User manually downloads apps</span></span>
* <span data-ttu-id="ccddf-132">Automatisches Update, wenn eine Verbindung mit dem Internet besteht</span><span class="sxs-lookup"><span data-stu-id="ccddf-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="ccddf-133">Weitere Informationen finden Sie unter [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span><span class="sxs-lookup"><span data-stu-id="ccddf-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="ccddf-134">Installieren über Bereitstellungspakete</span><span class="sxs-lookup"><span data-stu-id="ccddf-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="ccddf-135">[Mit Bereitstellungspaketen](app-deploy-provisioning-package.md) können Sie benutzerdefinierte oder branchenspezifische Apps installieren, sodass IT-Spezialisten und Administratoren Apps schnell über USB auf einem lokalen Gerät installieren können.</span><span class="sxs-lookup"><span data-stu-id="ccddf-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="ccddf-136">Diese Installation kann ohne Internetverbindung und für jeden Identitätstyp erfolgen.</span><span class="sxs-lookup"><span data-stu-id="ccddf-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="ccddf-137">Die Installation über Bereitstellungspakete gilt für:</span><span class="sxs-lookup"><span data-stu-id="ccddf-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="ccddf-138">Branchenspezifische/selbst entwickelte (nicht öffentliche) Apps</span><span class="sxs-lookup"><span data-stu-id="ccddf-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="ccddf-139">Öffentliche Apps (wenn ein Offlineinstaller verfügbar ist)</span><span class="sxs-lookup"><span data-stu-id="ccddf-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="ccddf-140">Nur USB-Querladen</span><span class="sxs-lookup"><span data-stu-id="ccddf-140">USB side-loading only</span></span>
* <span data-ttu-id="ccddf-141">Kein automatisches Update (erfordert manuelle Updates über das Bereitstellungspaket)</span><span class="sxs-lookup"><span data-stu-id="ccddf-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="ccddf-142">Installieren von Apps auf HoloLens 2 über App-Installer</span><span class="sxs-lookup"><span data-stu-id="ccddf-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="ccddf-143">Mithilfe der [App-Installer](app-deploy-app-installer.md) können Benutzer über eine einfache Benutzeroberfläche verfügen, um Apps auf lokalen Geräten zu installieren oder eine App für eine andere Person zu teilen, die mit anderen App-Installationsmethoden auf HoloLens nicht vertraut ist.</span><span class="sxs-lookup"><span data-stu-id="ccddf-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="ccddf-144">Dies kann erfolgen, ohne den Entwicklermodus zu aktivieren oder Geräteportal zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ccddf-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="ccddf-145">Dies ist eine einfache Methode zum Verteilen einer vollständig erstellten App.</span><span class="sxs-lookup"><span data-stu-id="ccddf-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="ccddf-146">Unabhängig davon, ob Sie Ihre App einfach für einen anderen Benutzer mit einer HoloLens demo oder ihre App bereitstellen möchten, funktioniert diese Methode problemlos.</span><span class="sxs-lookup"><span data-stu-id="ccddf-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="ccddf-147">Die Installation über App-Installer gilt für:</span><span class="sxs-lookup"><span data-stu-id="ccddf-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="ccddf-148">Line of Business/Selbst entwickelte (nicht öffentliche) Apps</span><span class="sxs-lookup"><span data-stu-id="ccddf-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="ccddf-149">Nur side-load</span><span class="sxs-lookup"><span data-stu-id="ccddf-149">Side-load only</span></span>
* <span data-ttu-id="ccddf-150">Der Entwicklermodus oder das Geräteportal ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ccddf-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="ccddf-151">Einfache Installation durch Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="ccddf-151">Easy for end user to install</span></span>
