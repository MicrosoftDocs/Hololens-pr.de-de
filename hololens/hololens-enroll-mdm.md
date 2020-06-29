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
ms.date: 07/15/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 054c4ded7496957671c055e3161a1297de7abc1a
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828096"
---
# <span data-ttu-id="512c5-103">Registrieren von HoloLens in MDM</span><span class="sxs-lookup"><span data-stu-id="512c5-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="512c5-104">Sie können mehrere Microsoft HoloLens-Geräte gleichzeitig mit Lösungen wie [Microsoft InTune](https://docs.microsoft.com/intune/windows-holographic-for-business)verwalten.</span><span class="sxs-lookup"><span data-stu-id="512c5-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="512c5-105">Sie können Einstellungen verwalten, zu installierende Apps auswählen und Sicherheitskonfigurationen festlegen, die auf die Anforderungen Ihrer Organisation zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="512c5-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="512c5-106">Weitere Informationen finden Sie unter [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), und [Konfigurationsdienstanbieter (Configuration Service Providers, CSPs), die in Windows Holographic unterstützt werden](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) sowie [Richtlinien, die von Windows Holographic for Business unterstützt werden](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="512c5-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="512c5-107">Die mobile Geräteverwaltung (MDM), einschließlich VPN, BitLocker und Kiosk-Modus-Features ist nur verfügbar, wenn Sie [ein Upgrade auf Windows Holographic for Business durchführen](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="512c5-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="512c5-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="512c5-108">Requirements</span></span>

 <span data-ttu-id="512c5-109">Für Ihre Organisation muss die Mobile Device Management (MDM) eingerichtet sein, um HoloLens-Geräte verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="512c5-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="512c5-110">Ihr MDM-Anbieter kann Microsoft Intune oder ein Drittanbieter sein, der die Microsoft-MDM-APIs verwendet.</span><span class="sxs-lookup"><span data-stu-id="512c5-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>

## <span data-ttu-id="512c5-111">Automatische Registrierung in MDM</span><span class="sxs-lookup"><span data-stu-id="512c5-111">Auto-enrollment in MDM</span></span>

<span data-ttu-id="512c5-112">Wenn Ihre Organisation Azure Active Directory (Azure AD) und eine MDM-Lösung verwendet, die ein AAD-Token für die Authentifizierung akzeptiert (zurzeit nur in Microsoft Intune und AirWatch unterstützt), kann der IT-Administrator Azure AD so konfigurieren, dass die MDM-Registrierung automatisch zugelassen wird, wenn der Benutzer sich mit seinem Azure AD-Konto angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="512c5-112">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an AAD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="512c5-113">Erfahren Sie, wie Sie die Azure AD-Registrierung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="512c5-113">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="512c5-114">Wenn die automatische Registrierung aktiviert ist, ist keine zusätzliche manuelle Registrierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="512c5-114">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="512c5-115">Wenn der Benutzer sich mit einem Azure AD-Konto anmeldet, wird das Gerät nach der ersten Ausführung in MDM registriert.</span><span class="sxs-lookup"><span data-stu-id="512c5-115">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

## <span data-ttu-id="512c5-116">Registrieren über die Einstellungs-App</span><span class="sxs-lookup"><span data-stu-id="512c5-116">Enroll through Settings app</span></span>

 <span data-ttu-id="512c5-117">Wenn das Gerät während der ersten Ausführung nicht in MDM registriert wird, kann der Benutzer das Gerät mithilfe der Einstellungs-App manuell bei dem MDM-Server der Organisation registrieren.</span><span class="sxs-lookup"><span data-stu-id="512c5-117">When the device is not enrolled in MDM during the first-run experience, the user can manually enroll the device with the organization's MDM server using the Settings app.</span></span>

1. <span data-ttu-id="512c5-118">Wechseln Sie zu **Einstellungen** > **Konten** > **Arbeitsplatzzugriff**.</span><span class="sxs-lookup"><span data-stu-id="512c5-118">Go to **Settings** > **Accounts** > **Work access**.</span></span>
1. <span data-ttu-id="512c5-119">Wählen Sie **Für Verwaltungsdienst registrieren**, und geben Sie Ihr Organisationskonto ein.</span><span class="sxs-lookup"><span data-stu-id="512c5-119">Select **Enroll into device management** and enter your organizational account.</span></span> <span data-ttu-id="512c5-120">Sie werden zur Anmeldeseite Ihrer Organisation weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="512c5-120">You will be redirected to your organization's sign in page.</span></span>
1. <span data-ttu-id="512c5-121">Bei erfolgreicher Authentifizierung bei dem MDM-Server wird eine entsprechende Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="512c5-121">Upon successful authentication to the MDM server, a success message is shown.</span></span>

<span data-ttu-id="512c5-122">Ihr Gerät ist jetzt bei Ihrem MDM-Server registriert.</span><span class="sxs-lookup"><span data-stu-id="512c5-122">Your device is now enrolled with your MDM server.</span></span> <span data-ttu-id="512c5-123">Die Einstellungs-App wird jetzt anzeigen, dass das Gerät in der Geräteverwaltung registriert ist.</span><span class="sxs-lookup"><span data-stu-id="512c5-123">The Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="512c5-124">Abmelden von HoloLens aus InTune</span><span class="sxs-lookup"><span data-stu-id="512c5-124">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="512c5-125">Sie können HoloLens dezentral von Intune [entfernen](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows).</span><span class="sxs-lookup"><span data-stu-id="512c5-125">You cannot [unenroll](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) HoloLens from Intune remotely.</span></span> <span data-ttu-id="512c5-126">Wenn der Administrator das Gerät mithilfe der MDM-Registrierung entfernt, wird das Gerät aus dem Intune-Dashboard entfernt.</span><span class="sxs-lookup"><span data-stu-id="512c5-126">If the administrator unenrolls the device using MDM, the device will age out of the Intune dashboard.</span></span>
