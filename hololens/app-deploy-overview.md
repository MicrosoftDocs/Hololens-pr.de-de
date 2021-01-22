---
title: Übersicht – App-Verwaltung
description: Erste Schritte mit einer Übersicht über mixed Reality-App-Verwaltung mit Verwaltung mobiler Geräte, Microsoft Store für Unternehmen und Bereitstellungspaketen.
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283706"
---
# <span data-ttu-id="27240-104">App-Verwaltung: Übersicht</span><span class="sxs-lookup"><span data-stu-id="27240-104">App Management: Overview</span></span>

<span data-ttu-id="27240-105">Sie können Apps auf vier verschiedenen Pfaden bereitstellen: **Mobile Device Management (MDM),** **Microsoft Store für Unternehmen**, **Microsoft Store**oder durch Installation über **Bereitstellung.**</span><span class="sxs-lookup"><span data-stu-id="27240-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <span data-ttu-id="27240-106">Mobile Geräteverwaltung (MDM)</span><span class="sxs-lookup"><span data-stu-id="27240-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="27240-107">Eine MDM-Lösung ermöglicht es IT-Entscheidungsträgern und Administratoren, ihre eigenen ,Line-of-Business-Apps privat zu installieren (pushen) oder Apps über den Store für eine Gruppe von Benutzern zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="27240-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="27240-108">HoloLens-Geräte funktionieren am besten mit Microsoft Endpoint Manager (Intune) für [die Anwendungsverwaltung.](app-deploy-intune.md)</span><span class="sxs-lookup"><span data-stu-id="27240-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="27240-109">Intune bietet Benutzern auch eine feinkörnige Kontrolle über IT-verwaltete Apps über das Unternehmensportal, das heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="27240-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="27240-110">Die folgenden Anweisungen sind für Benutzer, die ihre Anwendungen mit Intune verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="27240-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="27240-111">Microsoft empfiehlt die Verwendung von Intune für die Anwendungs- und Geräteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="27240-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="27240-112">Die Verwaltung mobiler Geräte (Mobile Device Management, MDM) gilt für:</span><span class="sxs-lookup"><span data-stu-id="27240-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="27240-113">MDM bereitgestellt + Unternehmensportal</span><span class="sxs-lookup"><span data-stu-id="27240-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="27240-114">(nicht öffentliche) Line-of-Business-Apps</span><span class="sxs-lookup"><span data-stu-id="27240-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="27240-115">Manuelle Installation verfügbarer Anwendungen über das Unternehmensportal</span><span class="sxs-lookup"><span data-stu-id="27240-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="27240-116">Administrator-Push über die MDM-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="27240-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="27240-117">Automatisches Update über MDM</span><span class="sxs-lookup"><span data-stu-id="27240-117">Auto update through MDM</span></span>

## <span data-ttu-id="27240-118">Microsoft Store für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="27240-118">Microsoft Store for Business</span></span>

<span data-ttu-id="27240-119">Der [Microsoft Store für Unternehmen](app-deploy-store-business.md) bietet IT-Entscheidungsträgern und Administratoren in Unternehmen die Suche, den Erwerb, die Verwaltung und den Vertrieb kostenloser und kostenpflichtiger Apps.</span><span class="sxs-lookup"><span data-stu-id="27240-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="27240-120">It administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span><span class="sxs-lookup"><span data-stu-id="27240-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="27240-121">Weitere Informationen finden Sie unter ["Voraussetzungen für die Verwendung des Microsoft Store für Unternehmen".](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)</span><span class="sxs-lookup"><span data-stu-id="27240-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="27240-122">Der Microsoft Store für Unternehmen gilt für:</span><span class="sxs-lookup"><span data-stu-id="27240-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="27240-123">Öffentliche Apps oder Line-of-Business-Apps</span><span class="sxs-lookup"><span data-stu-id="27240-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="27240-124">Automatische Installation erforderlicher Anwendungen über die MDM-Zuordnung</span><span class="sxs-lookup"><span data-stu-id="27240-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="27240-125">Benutzer lädt Apps manuell herunter</span><span class="sxs-lookup"><span data-stu-id="27240-125">User manually downloads apps</span></span>
* <span data-ttu-id="27240-126">Automatisches Update</span><span class="sxs-lookup"><span data-stu-id="27240-126">Auto Update</span></span>

## <span data-ttu-id="27240-127">Microsoft Store-Apps</span><span class="sxs-lookup"><span data-stu-id="27240-127">Microsoft Store apps</span></span>

<span data-ttu-id="27240-128">Der Microsoft Store bietet IT-Entscheidungsträgern und Administratoren in Unternehmen die Suche, den Erwerb, die Verwaltung und den Vertrieb öffentlicher Apps.</span><span class="sxs-lookup"><span data-stu-id="27240-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="27240-129">Dieser Microsoft Store gilt für:</span><span class="sxs-lookup"><span data-stu-id="27240-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="27240-130">Nur öffentliche Apps</span><span class="sxs-lookup"><span data-stu-id="27240-130">Public apps only</span></span>
* <span data-ttu-id="27240-131">Benutzer lädt Apps manuell herunter</span><span class="sxs-lookup"><span data-stu-id="27240-131">User manually downloads apps</span></span>
* <span data-ttu-id="27240-132">Automatisches Update, wenn eine Verbindung mit dem Internet besteht</span><span class="sxs-lookup"><span data-stu-id="27240-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="27240-133">Weitere Informationen finden Sie unter [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span><span class="sxs-lookup"><span data-stu-id="27240-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="27240-134">Installieren über Bereitstellungspakete</span><span class="sxs-lookup"><span data-stu-id="27240-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="27240-135">[Mit Bereitstellungspaketen](app-deploy-provisioning-package.md) können Sie benutzerdefinierte Apps oder Line-of-Business-Apps installieren, sodass IT-Profis und Administratoren Apps schnell über USB auf einem oder mehreren lokalen Geräten installieren können.</span><span class="sxs-lookup"><span data-stu-id="27240-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="27240-136">Diese Installation kann ohne Internetverbindung und für jeden Identitätstyp durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="27240-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="27240-137">Die Installation über Bereitstellungspakete gilt für:</span><span class="sxs-lookup"><span data-stu-id="27240-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="27240-138">Geschäftsbereich/selbst entwickelte (nicht öffentliche) Apps</span><span class="sxs-lookup"><span data-stu-id="27240-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="27240-139">Öffentliche Apps (wenn ein Offlineinstallationsprogramm verfügbar ist)</span><span class="sxs-lookup"><span data-stu-id="27240-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="27240-140">Nur side-loading von USB</span><span class="sxs-lookup"><span data-stu-id="27240-140">USB side-loading only</span></span>
* <span data-ttu-id="27240-141">Kein automatisches Update (erfordert manuelle Updates über das Bereitstellungspaket)</span><span class="sxs-lookup"><span data-stu-id="27240-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <span data-ttu-id="27240-142">Installieren von Apps auf HoloLens 2 über den App-Installer</span><span class="sxs-lookup"><span data-stu-id="27240-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="27240-143">Die Verwendung des [App-Installers](app-deploy-app-installer.md) kann für Benutzer einfach sein, um Apps auf lokalen Geräten zu installieren oder eine App für eine andere Person zu teilen, die mit anderen Methoden zur Installation von Apps auf HoloLens nicht vertraut ist.</span><span class="sxs-lookup"><span data-stu-id="27240-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="27240-144">Dies ist möglich, ohne den Entwicklermodus aktivieren oder das Geräteportal verwenden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="27240-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="27240-145">Dies ist eine einfache Methode zum Verteilen einer vollständig erstellten App.</span><span class="sxs-lookup"><span data-stu-id="27240-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="27240-146">Unabhängig davon, ob Sie Ihre App einfach für einen anderen Benutzer mit einer HoloLens demon möchten oder Wenn Sie Ihre App bereitstellen möchten, funktioniert diese Methode problemlos.</span><span class="sxs-lookup"><span data-stu-id="27240-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="27240-147">Die Installation über den App Installer gilt für:</span><span class="sxs-lookup"><span data-stu-id="27240-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="27240-148">Geschäftsbereich/selbst entwickelte (nicht öffentliche) Apps</span><span class="sxs-lookup"><span data-stu-id="27240-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="27240-149">Nur Sideloading</span><span class="sxs-lookup"><span data-stu-id="27240-149">Side-load only</span></span>
* <span data-ttu-id="27240-150">Erfordert weder den Entwicklermodus noch das Geräteportal</span><span class="sxs-lookup"><span data-stu-id="27240-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="27240-151">Einfache Installation für Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="27240-151">Easy for end user to install</span></span>
