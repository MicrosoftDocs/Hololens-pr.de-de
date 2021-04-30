---
title: Intune und Unternehmensportal
description: Erfahren Sie, wie Sie eine komfortable Benutzeroberfläche mit Intune, der Verwaltung mobiler Geräte und dem Unternehmensportal einrichten, zuweisen und erstellen.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309728"
---
# <a name="intune--company-portal"></a><span data-ttu-id="4f587-104">Intune & Unternehmensportal</span><span class="sxs-lookup"><span data-stu-id="4f587-104">Intune & Company Portal</span></span>

<span data-ttu-id="4f587-105">Mit Mobile Geräteverwaltung (MDM) können Sie Ihre eigenen benutzerdefinierten Apps über [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) verwenden, um sie direkt auf Ihren HoloLens-Geräten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4f587-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="4f587-106">Microsoft Intune ist ein cloudbasierter Dienst, der sich auf die Verwaltung mobiler Geräte (MDM, Mobile Device Management) und mobiler Anwendungen (MAM, Mobile Application Management) konzentriert.</span><span class="sxs-lookup"><span data-stu-id="4f587-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="4f587-107">Intune ist in der [EMS-Suite (Enterprise Mobility + Security)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) von Microsoft enthalten und ermöglicht Ihren Benutzern, produktiv zu sein, während die Daten ihrer Organisation geschützt bleiben.</span><span class="sxs-lookup"><span data-stu-id="4f587-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="4f587-108">Weitere Informationen zu Intune finden Sie unter [Was ist Intune?.](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="4f587-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="4f587-109">Setup</span><span class="sxs-lookup"><span data-stu-id="4f587-109">Setup</span></span>

1. <span data-ttu-id="4f587-110">Laden Sie eine App in einen Line of Business-Dienst hoch, oder laden Sie eine benutzerdefinierte App in Ihren Intune-Mandanten hoch.</span><span class="sxs-lookup"><span data-stu-id="4f587-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="4f587-111">Siehe auch: [Unternehmens-App-Verwaltung](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span><span class="sxs-lookup"><span data-stu-id="4f587-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="4f587-112">[Weisen Sie Ihre App einer Gruppe zu.](https://docs.microsoft.com/mem/intune/apps/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="4f587-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="4f587-113">Basierend auf dem von Ihnen ausgewählten Zuweisungstyp kann die App automatisch übermittelt werden oder verfügbar sein, damit sie sofort heruntergefahren werden kann, wenn Sie über eine Auswahl von Apps verfügen.</span><span class="sxs-lookup"><span data-stu-id="4f587-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="4f587-114">Achten Sie beim Erstellen Ihres AppX-Pakets darauf, dass Sie die Architektur für die Geräte, auf denen Sie bereitstellen, berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="4f587-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="4f587-115">HoloLens 2 arm64 und HoloLens (1. Generation) ist x86.</span><span class="sxs-lookup"><span data-stu-id="4f587-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="4f587-116">Sie können beides in ein einzelnes AppX-Paket einbetten, wenn Sie eine Umgebung für gemischte Geräte planen.</span><span class="sxs-lookup"><span data-stu-id="4f587-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="4f587-117">Zuweisungstypen</span><span class="sxs-lookup"><span data-stu-id="4f587-117">Assignment types</span></span>

<span data-ttu-id="4f587-118">Damit Ihre App nach der Registrierung automatisch auf dem Gerät installiert wird, sollten Sie **Für** diese Gruppe(n) erforderlich auswählen.</span><span class="sxs-lookup"><span data-stu-id="4f587-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="4f587-119">Wählen Sie Verfügbar für registrierte Geräte aus, um Ihre App für Geräte verfügbar zu machen, die über das Unternehmensportal **registriert sind.**</span><span class="sxs-lookup"><span data-stu-id="4f587-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="4f587-120">Endbenutzererfahrung</span><span class="sxs-lookup"><span data-stu-id="4f587-120">End-User Experience</span></span>

<span data-ttu-id="4f587-121">Nachdem Sie die Konfiguration in Intune eingerichtet haben, können Endbenutzer Ihre ausgewählten Apps erhalten.</span><span class="sxs-lookup"><span data-stu-id="4f587-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="4f587-122">Führen Sie die folgenden Schritte aus, um Ihre Apps automatisch zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="4f587-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="4f587-123">Registrieren Sie Ihr Gerät bei Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="4f587-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="4f587-124">Nachdem die Registrierung Ihres Geräts abgeschlossen ist, sollten Sie die App auf Ihrem Gerät erhalten.</span><span class="sxs-lookup"><span data-stu-id="4f587-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="4f587-125">Wenn Sie Ihre App nicht sofort sehen, wechseln Sie zu Einstellungen Konten Arbeits- oder SchulkontoInformationen, und scrollen Sie nach unten, um Informationen zum Status der  >    >    >   installierten App anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4f587-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="4f587-126">So gelangen Sie über die Unternehmensportal zu Apps:</span><span class="sxs-lookup"><span data-stu-id="4f587-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="4f587-127">Öffnen Sie das **Startmenü,** und wählen Sie **Microsoft Store** aus.</span><span class="sxs-lookup"><span data-stu-id="4f587-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="4f587-128">Suchen Sie **nach Unternehmensportal,** und laden Sie die App herunter.</span><span class="sxs-lookup"><span data-stu-id="4f587-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="4f587-129">Melden Sie sich bei Ihrem Konto an.</span><span class="sxs-lookup"><span data-stu-id="4f587-129">Sign into your account.</span></span>
4. <span data-ttu-id="4f587-130">Wählen Sie die App aus, die Sie erhalten möchten, und laden Sie sie herunter.</span><span class="sxs-lookup"><span data-stu-id="4f587-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="4f587-131">Erfahren Sie mehr über [die automatische Installation der Unternehmensportal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) und das Bereitstellen und Verwalten von Apps in [Intune.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="4f587-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
