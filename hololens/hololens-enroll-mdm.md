---
title: Registrieren von HoloLens in MDM
description: Erfahren Sie, wie Sie HoloLens in der Mobile Device Management (MDM) registrieren, um die Verwaltung mehrerer Geräte zu vereinfachen.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b9473f4e80f6438ef4c438711ac0de342c5327e1
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283186"
---
# <span data-ttu-id="800cd-103">Registrieren von HoloLens in MDM</span><span class="sxs-lookup"><span data-stu-id="800cd-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="800cd-104">Sie können mehrere Microsoft HoloLens-Geräte gleichzeitig mit Lösungen wie [Microsoft Intune verwalten.](https://docs.microsoft.com/intune/windows-holographic-for-business)</span><span class="sxs-lookup"><span data-stu-id="800cd-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="800cd-105">Sie können Einstellungen verwalten, zu installierende Apps auswählen und Sicherheitskonfigurationen festlegen, die auf die Anforderungen Ihrer Organisation zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="800cd-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="800cd-106">Weitere Informationen finden Sie unter [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), und [Konfigurationsdienstanbieter (Configuration Service Providers, CSPs), die in Windows Holographic unterstützt werden](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) sowie [Richtlinien, die von Windows Holographic for Business unterstützt werden](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="800cd-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="800cd-107">Die mobile Geräteverwaltung (MDM), einschließlich VPN, BitLocker und Kiosk-Modus-Features ist nur verfügbar, wenn Sie [ein Upgrade auf Windows Holographic for Business durchführen](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="800cd-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="800cd-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="800cd-108">Requirements</span></span>

 <span data-ttu-id="800cd-109">Ihre Organisation muss die mobile Geräteverwaltung (Mobile Device Management, MDM) einrichten, um die Geräte von HoloLens verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="800cd-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="800cd-110">Ihr MDM-Anbieter kann Microsoft Intune oder ein Drittanbieter sein, der die Microsoft-MDM-APIs verwendet.</span><span class="sxs-lookup"><span data-stu-id="800cd-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <span data-ttu-id="800cd-111">Unterschiedliche Registrierungswege</span><span class="sxs-lookup"><span data-stu-id="800cd-111">Different ways to enroll</span></span>

<span data-ttu-id="800cd-112">Je nach Identitätstyp, der während der OOBE oder nach der Anmeldung ausgewählt wurde, gibt es unterschiedliche Registrierungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="800cd-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span></span> <span data-ttu-id="800cd-113">Weitere Informationen zu den einzelnen Identitätstypen auf HoloLens finden Sie [auf dieser Seite.](hololens-identity.md)</span><span class="sxs-lookup"><span data-stu-id="800cd-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span></span>

- <span data-ttu-id="800cd-114">Wenn Identity Azure AD ist, dann entweder während der OOBE oder der **Schaltfläche "App-Zugriff**auf Arbeit" oder  ->  **"School**  ->  **Connect".**</span><span class="sxs-lookup"><span data-stu-id="800cd-114">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="800cd-115">Bei Azure AD erfolgt die automatische MDM-Registrierung nur, wenn Azure AD mit Registrierungs-URLs konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="800cd-115">For Azure AD, automatic MDM enrollment only occurs if Azure AD has been configured with enrollment URLs.</span></span>
- <span data-ttu-id="800cd-116">Wenn "Identity" Azure AD ist und das Gerät vor dem Intune-MDM-Server registriert wurde und ihm ein bestimmtes Konfigurationsprofil zugewiesen wurde, erfolgt Azure AD-Join und die Registrierung automatisch während der OOBE.</span><span class="sxs-lookup"><span data-stu-id="800cd-116">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and enrollment will automatically occur during OOBE.</span></span>
    - <span data-ttu-id="800cd-117">Wird auch [als "Autopilot Flow"](hololens2-autopilot.md) bezeichnet und ist in [19041.1103+ Builds verfügbar.](hololens-release-notes.md#windows-holographic-version-2004)</span><span class="sxs-lookup"><span data-stu-id="800cd-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
- <span data-ttu-id="800cd-118">Wenn "Identity" MSA ist, verwenden Sie die Schaltfläche **"Settings App**  ->  **Access Work" oder "School**  ->  **Connect".**</span><span class="sxs-lookup"><span data-stu-id="800cd-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="800cd-119">Wird auch als Add Work Account (AWA)-Fluss bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="800cd-119">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="800cd-120">Wenn "Identität" ein lokaler Benutzer ist, verwenden Sie **"Einstellungen**App  ->  **Access Work" oder "School**Enroll" nur  ->  **im Link "Geräteverwaltung".**</span><span class="sxs-lookup"><span data-stu-id="800cd-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="800cd-121">Wird auch als reiner MDM-Registrierungsablauf bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="800cd-121">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="800cd-122">Nachdem das Gerät bei Ihrem MDM-Server registriert wurde, gibt die App "Einstellungen" jetzt wieder, dass das Gerät für die Geräteverwaltung registriert ist.</span><span class="sxs-lookup"><span data-stu-id="800cd-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="800cd-123">Automatische Registrierung in MDM</span><span class="sxs-lookup"><span data-stu-id="800cd-123">Auto-enrollment in MDM</span></span>

<span data-ttu-id="800cd-124">Wenn Ihre Organisation Azure Active Directory (Azure AD) und eine MDM-Lösung verwendet, die ein Azure AD-Token für die Authentifizierung akzeptiert (derzeit nur in Microsoft Intune und AirWatch unterstützt), kann Ihr IT-Administrator Azure AD so konfigurieren, dass die Registrierung von MDM automatisch zulässig ist, nachdem sich der Benutzer mit seinem Azure AD-Konto angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="800cd-124">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="800cd-125">Erfahren Sie, wie Sie die Azure AD-Registrierung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="800cd-125">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="800cd-126">Wenn die automatische Registrierung aktiviert ist, ist keine zusätzliche manuelle Registrierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="800cd-126">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="800cd-127">Wenn der Benutzer sich mit einem Azure AD-Konto anmeldet, wird das Gerät nach der ersten Ausführung in MDM registriert.</span><span class="sxs-lookup"><span data-stu-id="800cd-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="800cd-128">Wenn ein Gerät mit Azure AD verbunden ist, kann sich dies darauf auswirken, wer den [Gerätebesitzer betrachtet hat.](security-adminless-os.md#device-owner)</span><span class="sxs-lookup"><span data-stu-id="800cd-128">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <span data-ttu-id="800cd-129">Aufheben der Registrierung von HoloLens in Intune</span><span class="sxs-lookup"><span data-stu-id="800cd-129">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="800cd-130">Weitere Informationen zum Unenrolling eines Geräts finden Sie auf [dieser Seite.](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment)</span><span class="sxs-lookup"><span data-stu-id="800cd-130">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span></span> 
