---
title: Intune und Unternehmensportal
description: Informationen zum Einrichten, Zuweisen und Erstellen einer komfortablen Benutzeroberfläche mit Intune, der Verwaltung mobiler Geräte und dem Unternehmensportal.
keywords: Intune, App-Verwaltung, App, Unternehmensportal, Portal, HoloLens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283716"
---
# <span data-ttu-id="66460-104">Intune und Unternehmensportal</span><span class="sxs-lookup"><span data-stu-id="66460-104">Intune & Company Portal</span></span>

<span data-ttu-id="66460-105">Mit der Mobile Device Management (MDM) können Sie Ihre eigenen benutzerdefinierten Apps über [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) verwenden, um sie direkt auf Ihren HoloLens-Geräten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="66460-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="66460-106">Microsoft Intune ist ein cloudbasierter Dienst, der sich auf mobile Geräteverwaltung (Mobile Device Management, MDM) und mobile Anwendungsverwaltung (Mobile Application Management, MAM) konzentriert.</span><span class="sxs-lookup"><span data-stu-id="66460-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="66460-107">Intune ist in der [Enterprise Mobility + Security (EMS)-Suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)von Microsoft enthalten und ermöglicht Benutzern, produktiv zu sein und gleichzeitig ihre Unternehmensdaten zu schützen.</span><span class="sxs-lookup"><span data-stu-id="66460-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="66460-108">Weitere Informationen zu Intune finden Sie unter ["Was ist Intune".](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="66460-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <span data-ttu-id="66460-109">Setup</span><span class="sxs-lookup"><span data-stu-id="66460-109">Setup</span></span>

1. <span data-ttu-id="66460-110">Laden Sie eine App in eine Geschäftsbereich hoch, oder laden Sie eine benutzerdefinierte App in Ihren Intune-Mandanten hoch.</span><span class="sxs-lookup"><span data-stu-id="66460-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="66460-111">Siehe auch: [Enterprise-App-Verwaltung](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span><span class="sxs-lookup"><span data-stu-id="66460-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="66460-112">[Weisen Sie Ihre App einer Gruppe zu.](https://docs.microsoft.com/mem/intune/apps/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="66460-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="66460-113">Basierend auf dem von Ihnen verwendeten Zuweisungstyp kann die App automatisch zugestellt oder verfügbar sein, um problemlos nach unten gezogen zu werden, wenn Sie über eine Auswahl von Apps verfügen.</span><span class="sxs-lookup"><span data-stu-id="66460-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="66460-114">Achten Sie beim Erstellen Ihres Appx-Bundles darauf, die Architektur für die Geräte, auf denen Sie bereitstellen, zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="66460-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="66460-115">HoloLens 2 ist ARM64 und HoloLens (1. Generation) x86.</span><span class="sxs-lookup"><span data-stu-id="66460-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="66460-116">Sie können beides in ein einzelnes Appx-Bundle mit einplanen, wenn Sie eine Umgebung mit gemischten Geräten planen.</span><span class="sxs-lookup"><span data-stu-id="66460-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <span data-ttu-id="66460-117">Zuweisungstypen</span><span class="sxs-lookup"><span data-stu-id="66460-117">Assignment types</span></span>

<span data-ttu-id="66460-118">Damit Ihre App nach der Registrierung automatisch auf dem \*\*\*\* Gerät installiert wird, sollten Sie "Erforderlich" für diese Gruppe(en) auswählen.</span><span class="sxs-lookup"><span data-stu-id="66460-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="66460-119">Um Ihre App für den Download auf Geräten verfügbar zu machen, die über das Unternehmensportal registriert sind, wählen Sie **"Verfügbar"** für registrierte Geräte aus.</span><span class="sxs-lookup"><span data-stu-id="66460-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <span data-ttu-id="66460-120">End-User A0</span><span class="sxs-lookup"><span data-stu-id="66460-120">End-User Experience</span></span>

<span data-ttu-id="66460-121">Nachdem Sie die Konfiguration in Intune eingerichtet haben, können Endbenutzer Ihre ausgewählten Apps empfangen.</span><span class="sxs-lookup"><span data-stu-id="66460-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="66460-122">Führen Sie die folgenden Schritte aus, um Ihre App(en) automatisch zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="66460-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="66460-123">Registrieren Sie Ihr Gerät bei Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="66460-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="66460-124">Sobald Ihr Gerät die Registrierung abgeschlossen hat, sollten Sie die App auf Ihrem Gerät erhalten.</span><span class="sxs-lookup"><span data-stu-id="66460-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="66460-125">Wenn Die App nicht sofort angezeigt \*\*\*\* wird, wechseln Sie zu Kontoinformationen zu "Einstellungskonten " Arbeit" oder "Schule", und scrollen Sie nach unten, um Informationen zum Status der  >  \*\*\*\*  >  \*\*\*\*  >  \*\* installierten App zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="66460-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="66460-126">So wechseln Sie über das Unternehmensportal zu Apps:</span><span class="sxs-lookup"><span data-stu-id="66460-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="66460-127">Öffnen Sie **das Startmenü,** und wählen **Sie Microsoft Store aus.**</span><span class="sxs-lookup"><span data-stu-id="66460-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="66460-128">Suchen Sie nach **dem Unternehmensportal,** und laden Sie die App herunter.</span><span class="sxs-lookup"><span data-stu-id="66460-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="66460-129">Melden Sie sich bei Ihrem Konto an.</span><span class="sxs-lookup"><span data-stu-id="66460-129">Sign into your account.</span></span>
4. <span data-ttu-id="66460-130">Wählen Sie die App aus, die Sie empfangen möchten, und laden Sie sie herunter.</span><span class="sxs-lookup"><span data-stu-id="66460-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="66460-131">Erfahren Sie mehr [über die automatische Installation des Unternehmensportals](https://docs.microsoft.com/mem/intune/apps/company-portal-app) und das Bereitstellen und Verwalten von Apps in [Intune.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="66460-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
