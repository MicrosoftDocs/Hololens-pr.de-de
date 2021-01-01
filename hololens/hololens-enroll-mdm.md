---
title: Registrieren von HoloLens in MDM
description: Registrieren Sie HoloLens zur einfacheren Verwaltung mehrerer Geräte in der Verwaltung mobiler Geräte (Mobile Device Management, MDM).
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
ms.openlocfilehash: 7c17cbf88fc2e7a6dcd9aa600ad6e6910edb29a8
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253232"
---
# <span data-ttu-id="b6593-103">Registrieren von HoloLens in MDM</span><span class="sxs-lookup"><span data-stu-id="b6593-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="b6593-104">Sie können mehrere Microsoft HoloLens-Geräte gleichzeitig mit Lösungen wie [Microsoft InTune](https://docs.microsoft.com/intune/windows-holographic-for-business)verwalten.</span><span class="sxs-lookup"><span data-stu-id="b6593-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="b6593-105">Sie können Einstellungen verwalten, zu installierende Apps auswählen und Sicherheitskonfigurationen festlegen, die auf die Anforderungen Ihrer Organisation zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="b6593-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="b6593-106">Weitere Informationen finden Sie unter [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), und [Konfigurationsdienstanbieter (Configuration Service Providers, CSPs), die in Windows Holographic unterstützt werden](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) sowie [Richtlinien, die von Windows Holographic for Business unterstützt werden](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="b6593-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="b6593-107">Die mobile Geräteverwaltung (MDM), einschließlich VPN, BitLocker und Kiosk-Modus-Features ist nur verfügbar, wenn Sie [ein Upgrade auf Windows Holographic for Business durchführen](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="b6593-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="b6593-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b6593-108">Requirements</span></span>

 <span data-ttu-id="b6593-109">Für Ihre Organisation muss die Mobile Device Management (MDM) eingerichtet sein, um HoloLens-Geräte verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="b6593-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="b6593-110">Ihr MDM-Anbieter kann Microsoft Intune oder ein Drittanbieter sein, der die Microsoft-MDM-APIs verwendet.</span><span class="sxs-lookup"><span data-stu-id="b6593-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <span data-ttu-id="b6593-111">Verschiedene Methoden zum Registrieren</span><span class="sxs-lookup"><span data-stu-id="b6593-111">Different ways to enroll</span></span>

<span data-ttu-id="b6593-112">Je nach dem Typ der Identität, die während der OOBE oder der Post Anmeldung ausgewählt wurde, gibt es verschiedene Methoden für die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="b6593-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span></span> <span data-ttu-id="b6593-113">Wenn Sie mehr über die einzelnen Identitätstypen auf HoloLens erfahren möchten, besuchen Sie bitte [Diese Seite](hololens-identity.md).</span><span class="sxs-lookup"><span data-stu-id="b6593-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span></span>

- <span data-ttu-id="b6593-114">Wenn Identity Azure AD ist, klicken Sie entweder während der OOBE-oder **Einstellungen-App**  ->  **auf**die  ->  Schaltfläche "Arbeit" oder "Schule**verbinden** ".</span><span class="sxs-lookup"><span data-stu-id="b6593-114">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="b6593-115">Bei Azure AD erfolgt die automatische MDM-Registrierung nur, wenn Azure AD mit Registrierungs-URLs konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="b6593-115">For Azure AD, automatic MDM enrollment only occurs if Azure AD has been configured with enrollment URLs.</span></span>
- <span data-ttu-id="b6593-116">Wenn Identity Azure AD ist und Device bereits mit dem InTune-MDM-Server registriert wurde, dem ein bestimmtes Konfigurationsprofil zugewiesen ist, werden Azure AD-Join und die Registrierung automatisch während OOBE ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b6593-116">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and enrollment will automatically occur during OOBE.</span></span>
    - <span data-ttu-id="b6593-117">Auch als [Autopilot-Flow](hololens2-autopilot.md) verfügbar, der in [19041.1103 +-Builds](hololens-release-notes.md#windows-holographic-version-2004)verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b6593-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
- <span data-ttu-id="b6593-118">Wenn Identity MSA ist, verwenden Sie die **Einstellungen App**  ->  **Access work oder School**  ->  **Connect** .</span><span class="sxs-lookup"><span data-stu-id="b6593-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="b6593-119">Wird auch als Add work Account (AWA)-Flow bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b6593-119">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="b6593-120">Wenn Identität ein lokaler Benutzer ist, verwenden Sie die **Einstellungen App**  ->  **Access work oder School**  ->  **nur registrieren in Device Management** Link.</span><span class="sxs-lookup"><span data-stu-id="b6593-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="b6593-121">Wird auch als reiner MDM-Registrierungs Fluss bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b6593-121">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="b6593-122">Nachdem das Gerät für Ihren MDM-Server registriert wurde, wird in der Einstellungs-APP nun wiedergespiegelt, dass das Gerät für die Geräteverwaltung registriert ist.</span><span class="sxs-lookup"><span data-stu-id="b6593-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="b6593-123">Automatische Registrierung in MDM</span><span class="sxs-lookup"><span data-stu-id="b6593-123">Auto-enrollment in MDM</span></span>

<span data-ttu-id="b6593-124">Wenn Ihre Organisation Azure Active Directory (Azure AD) und eine MDM-Lösung verwendet, die ein Azure AD-Token für die Authentifizierung akzeptiert (derzeit nur in Microsoft InTune und "flugwatch" unterstützt), kann Ihr IT-Administrator Azure AD so konfigurieren, dass die MDM-Registrierung automatisch zugelassen wird, nachdem sich der Benutzer mit seinem Azure AD-Konto angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="b6593-124">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="b6593-125">Erfahren Sie, wie Sie die Azure AD-Registrierung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b6593-125">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="b6593-126">Wenn die automatische Registrierung aktiviert ist, ist keine zusätzliche manuelle Registrierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b6593-126">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="b6593-127">Wenn der Benutzer sich mit einem Azure AD-Konto anmeldet, wird das Gerät nach der ersten Ausführung in MDM registriert.</span><span class="sxs-lookup"><span data-stu-id="b6593-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="b6593-128">Wenn ein Gerät Azure AD beigetreten ist, kann dies Auswirkungen auf die Person haben, die den [Gerätebesitzer](security-adminless-os.md#device-owner)berücksichtigt hat.</span><span class="sxs-lookup"><span data-stu-id="b6593-128">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <span data-ttu-id="b6593-129">Abmelden von HoloLens aus InTune</span><span class="sxs-lookup"><span data-stu-id="b6593-129">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="b6593-130">Weitere Informationen zur Registrierung eines Geräts finden Sie auf [dieser Seite](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span><span class="sxs-lookup"><span data-stu-id="b6593-130">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span></span> 
