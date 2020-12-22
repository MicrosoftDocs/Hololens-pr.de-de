---
title: InTune und Unternehmens Portal
description: InTune, App-Verwaltung, APP, Unternehmensportal, Portal
keywords: InTune, App-Verwaltung, APP, Unternehmensportal, Portal, hololens
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
ms.openlocfilehash: 7fcd65d5e49fa9cdd771828401749a0a41e50238
ms.sourcegitcommit: d319ac257b9ace484acf5dcfb16c9d4e19ea50a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2020
ms.locfileid: "11247217"
---
# <span data-ttu-id="0b664-104">Intune und Unternehmensportal</span><span class="sxs-lookup"><span data-stu-id="0b664-104">Intune & Company Portal</span></span>

<span data-ttu-id="0b664-105">Mit der Verwaltung mobiler Geräte (Mobile Device Management, MDM) können Sie Ihre eigenen benutzerdefinierten Apps über [Microsoft Endpoint Manager (InTune)](https://docs.microsoft.com/intune/windows-holographic-for-business) verwenden, um Sie direkt auf Ihren HoloLens-Geräten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="0b664-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="0b664-106">Microsoft InTune ist ein Cloud-basierter Dienst, der sich auf die Verwaltung mobiler Geräte (Mobile Device Management, MDM) und die Verwaltung mobiler Anwendungen (MAM) konzentriert.</span><span class="sxs-lookup"><span data-stu-id="0b664-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="0b664-107">InTune ist in der Microsoft [Enterprise Mobility + Security (EMS)-Suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)enthalten und ermöglicht Benutzern, produktiv zu sein und gleichzeitig ihre Organisationsdaten zu schützen.</span><span class="sxs-lookup"><span data-stu-id="0b664-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="0b664-108">Wenn Sie mehr über InTune erfahren möchten, lesen Sie [Was ist InTune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span><span class="sxs-lookup"><span data-stu-id="0b664-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <span data-ttu-id="0b664-109">Setup</span><span class="sxs-lookup"><span data-stu-id="0b664-109">Setup</span></span>

1. <span data-ttu-id="0b664-110">Laden Sie eine app in eine geschäftszeile hoch, oder laden Sie eine benutzerdefinierte app in ihren InTune-Mandanten hoch.</span><span class="sxs-lookup"><span data-stu-id="0b664-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="0b664-111">Siehe auch: [Enterprise-App-Verwaltung](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span><span class="sxs-lookup"><span data-stu-id="0b664-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="0b664-112">[Weisen Sie Ihre APP einer Gruppe zu](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="0b664-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="0b664-113">Basierend auf dem von Ihnen ausgewählten Zuordnungstyp können Sie die APP automatisch oder verfügbar bereitstellen lassen, wenn Sie eine Auswahl von apps haben.</span><span class="sxs-lookup"><span data-stu-id="0b664-113">Based on the assignment type you choose you can have the app delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span> 

> [!NOTE] 
> <span data-ttu-id="0b664-114">Achten Sie beim Erstellen Ihres AppX-Pakets darauf, dass Sie die Architektur für die Geräte berücksichtigen, auf die Sie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0b664-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="0b664-115">HoloLens 2 ist ARM64, und HoloLens (1st Generation) ist x86.</span><span class="sxs-lookup"><span data-stu-id="0b664-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="0b664-116">Sie können beide in ein einzelnes AppX-Bundle einbeziehen, wenn Sie eine Umgebung mit gemischten Geräten planen.</span><span class="sxs-lookup"><span data-stu-id="0b664-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <span data-ttu-id="0b664-117">Zuordnungstypen</span><span class="sxs-lookup"><span data-stu-id="0b664-117">Assignment types</span></span>

<span data-ttu-id="0b664-118">Wenn Sie möchten, dass Ihre APP nach der Registrierung automatisch auf dem Gerät installiert wird, sollten Sie für diese Gruppe (n) **erforderlich** auswählen.</span><span class="sxs-lookup"><span data-stu-id="0b664-118">If you prefer your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="0b664-119">Wenn Sie Ihre APP für die über das Unternehmensportal registrierten Personen herunterladen möchten, wählen Sie **für eingeschriebene Geräte verfügbar**aus.</span><span class="sxs-lookup"><span data-stu-id="0b664-119">If you prefer to make your app available for download to those enrolled through the company portal, select **Available for enrolled devices**.</span></span>


## <span data-ttu-id="0b664-120">Endbenutzererfahrung</span><span class="sxs-lookup"><span data-stu-id="0b664-120">End User Experience</span></span>

<span data-ttu-id="0b664-121">Nachdem Sie die Konfiguration auf InTune eingerichtet haben, sind Sie bereit, damit Endbenutzer Ihre ausgewählten apps empfangen können.</span><span class="sxs-lookup"><span data-stu-id="0b664-121">After you have set up configuration on Intune you are ready for end users to recieve your selected apps.</span></span>

<span data-ttu-id="0b664-122">Führen Sie die folgenden Schritte aus, um Ihre APP (s) automatisch abzurufen:</span><span class="sxs-lookup"><span data-stu-id="0b664-122">Follow these steps to automatically get your app(s):</span></span>
1. <span data-ttu-id="0b664-123">Registrieren Sie Ihr Gerät für Ihren Mandanten.</span><span class="sxs-lookup"><span data-stu-id="0b664-123">Enroll your device with your tenant.</span></span> 
2. <span data-ttu-id="0b664-124">Sobald Ihr Gerät die Registrierung abgeschlossen hat, sollten Sie die APP auf Ihrem Gerät empfangen.</span><span class="sxs-lookup"><span data-stu-id="0b664-124">Once your device has completed enrollment, you should receive the app on your device.</span></span> 
3. <span data-ttu-id="0b664-125">Wenn Sie die APP nicht sofort sehen, wechseln Sie zu **Einstellungen**  >  **Firmen**  >  **Arbeit oder Schule**  >  **YourAccount** Informationen, und Scrollen Sie nach unten, um Informationen zum installierten App-Status anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0b664-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > **youraccount** Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="0b664-126">So gelangen Sie zu Apps über das Unternehmens Portal:</span><span class="sxs-lookup"><span data-stu-id="0b664-126">How to get to apps through the Company Portal:</span></span>
1. <span data-ttu-id="0b664-127">Öffnen Sie das **Startmenü** , und wählen Sie **Microsoft Store**aus.</span><span class="sxs-lookup"><span data-stu-id="0b664-127">Open the **Start Menu** and select **Microsoft Store**.</span></span> 
2. <span data-ttu-id="0b664-128">Suchen Sie nach **Unternehmens Portal** , und laden Sie die APP herunter.</span><span class="sxs-lookup"><span data-stu-id="0b664-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="0b664-129">Bei Ihrem Konto anmelden.</span><span class="sxs-lookup"><span data-stu-id="0b664-129">Sign into your account.</span></span>
4. <span data-ttu-id="0b664-130">Wählen Sie die APP aus, die Sie erhalten möchten, und laden Sie Sie herunter.</span><span class="sxs-lookup"><span data-stu-id="0b664-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="0b664-131">Weitere Informationen finden Sie [unter Automatisches Installieren des Unternehmensportals](https://docs.microsoft.com/mem/intune/apps/company-portal-app) und [bereitstellen und Verwalten von apps in InTune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span><span class="sxs-lookup"><span data-stu-id="0b664-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
