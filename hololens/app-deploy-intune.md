---
title: Intune und Unternehmensportal
description: Erfahren Sie, wie Sie mit Intune, der Verwaltung mobiler Geräte und dem Unternehmensportal eine komfortable Benutzeroberfläche einrichten, zuweisen und erstellen.
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
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635499"
---
# <a name="intune--company-portal"></a><span data-ttu-id="7d9ac-104">Intune- und Unternehmensportal</span><span class="sxs-lookup"><span data-stu-id="7d9ac-104">Intune & Company Portal</span></span>

<span data-ttu-id="7d9ac-105">Mit Mobile Geräteverwaltung (MDM) können Sie Ihre eigenen benutzerdefinierten Apps über [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) verwenden, um sie direkt auf Ihren HoloLens Geräten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="7d9ac-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="7d9ac-106">Microsoft Intune ist ein cloudbasierter Dienst, der sich auf die Verwaltung mobiler Geräte (MDM, Mobile Device Management) und mobiler Anwendungen (MAM, Mobile Application Management) konzentriert.</span><span class="sxs-lookup"><span data-stu-id="7d9ac-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="7d9ac-107">Intune ist in der [EMS-Suite (Enterprise Mobility + Security)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) von Microsoft enthalten und ermöglicht Ihren Benutzern, produktiv zu sein, während die Daten ihrer Organisation geschützt bleiben.</span><span class="sxs-lookup"><span data-stu-id="7d9ac-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="7d9ac-108">Weitere Informationen zu Intune finden Sie unter [Was ist Intune?.](/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="7d9ac-108">To learn more about Intune, read [What is Intune](/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="7d9ac-109">Einrichten</span><span class="sxs-lookup"><span data-stu-id="7d9ac-109">Setup</span></span>

1. <span data-ttu-id="7d9ac-110">Hochladen eine App in eine Branchenanwendung, oder laden Sie eine benutzerdefinierte App in Ihren Intune-Mandanten hoch.</span><span class="sxs-lookup"><span data-stu-id="7d9ac-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="7d9ac-111">Siehe auch: [Enterprise App-Verwaltung.](/windows/client-management/mdm/enterprise-app-management)</span><span class="sxs-lookup"><span data-stu-id="7d9ac-111">See also: [Enterprise app management](/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="7d9ac-112">[Weisen Sie Ihre App einer Gruppe zu.](/mem/intune/apps/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="7d9ac-112">[Assign your app to a group](/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="7d9ac-113">Basierend auf dem von Ihnen ausgewählten Zuweisungstyp kann die App automatisch oder verfügbar bereitgestellt werden, damit sie sofort abgerufen werden kann, wenn Sie über eine Auswahl von Apps verfügen.</span><span class="sxs-lookup"><span data-stu-id="7d9ac-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="7d9ac-114">Achten Sie beim Erstellen Ihres AppX-Pakets darauf, dass Sie die Architektur für die Geräte berücksichtigen, auf denen Sie die Bereitstellung durchführen.</span><span class="sxs-lookup"><span data-stu-id="7d9ac-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="7d9ac-115">HoloLens 2 ist ARM64, und HoloLens (1. Generation) ist x86.</span><span class="sxs-lookup"><span data-stu-id="7d9ac-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="7d9ac-116">Sie können beides in ein einzelnes AppX-Paket einschließen, wenn Sie eine Umgebung mit gemischten Geräten planen.</span><span class="sxs-lookup"><span data-stu-id="7d9ac-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="7d9ac-117">Zuweisungstypen</span><span class="sxs-lookup"><span data-stu-id="7d9ac-117">Assignment types</span></span>

<span data-ttu-id="7d9ac-118">Damit Ihre App nach der Registrierung automatisch auf dem Gerät installiert wird, sollten Sie für diese Gruppe(en) **Erforderlich** auswählen.</span><span class="sxs-lookup"><span data-stu-id="7d9ac-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="7d9ac-119">Um Ihre App für Geräte, die über das Unternehmensportal registriert sind, zum Download zur Verfügung zu stellen, wählen Sie **Für registrierte Geräte verfügbar** aus.</span><span class="sxs-lookup"><span data-stu-id="7d9ac-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="7d9ac-120">Endbenutzererfahrung</span><span class="sxs-lookup"><span data-stu-id="7d9ac-120">End-User Experience</span></span>

<span data-ttu-id="7d9ac-121">Nachdem Sie die Konfiguration in Intune eingerichtet haben, können Endbenutzer Ihre ausgewählten Apps empfangen.</span><span class="sxs-lookup"><span data-stu-id="7d9ac-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="7d9ac-122">Führen Sie die folgenden Schritte aus, um Ihre Apps automatisch abzurufen:</span><span class="sxs-lookup"><span data-stu-id="7d9ac-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="7d9ac-123">Registrieren Sie Ihr Gerät bei Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="7d9ac-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="7d9ac-124">Nachdem Ihr Gerät die Registrierung abgeschlossen hat, sollten Sie die App auf Ihrem Gerät erhalten.</span><span class="sxs-lookup"><span data-stu-id="7d9ac-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="7d9ac-125">Wenn Ihre App nicht sofort angezeigt wird, wechseln Sie zu **Einstellungen**  >  **Konten**  >  **Arbeits- oder**  >  *Schulkontoinformationen,* und scrollen Sie nach unten, um Informationen zum Status der installierten App anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7d9ac-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="7d9ac-126">So gelangen Sie über die Unternehmensportal zu Apps:</span><span class="sxs-lookup"><span data-stu-id="7d9ac-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="7d9ac-127">Öffnen Sie das **Startmenü,** und wählen Sie **Microsoft Store** aus.</span><span class="sxs-lookup"><span data-stu-id="7d9ac-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="7d9ac-128">Suchen Sie **nach Unternehmensportal,** und laden Sie die App herunter.</span><span class="sxs-lookup"><span data-stu-id="7d9ac-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="7d9ac-129">Melden Sie sich bei Ihrem Konto an.</span><span class="sxs-lookup"><span data-stu-id="7d9ac-129">Sign into your account.</span></span>
4. <span data-ttu-id="7d9ac-130">Wählen Sie die App aus, die Sie erhalten möchten, und laden Sie sie herunter.</span><span class="sxs-lookup"><span data-stu-id="7d9ac-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="7d9ac-131">Erfahren Sie mehr über [die automatische Installation der Unternehmensportal](/mem/intune/apps/company-portal-app) und das Bereitstellen und Verwalten von Apps in [Intune.](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="7d9ac-131">Learn more about [auto-installing the Company Portal](/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
