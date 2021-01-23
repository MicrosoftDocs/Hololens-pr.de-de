---
title: Lizenzanforderungen
description: Halten Sie sich auf dem Laufenden über alle Lizenzierungsanforderungen und Richtlinien, die Sie für die Geräteverwaltung für Mobilgeräte, HoloLens und Remote Assist benötigen.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283966"
---
# <span data-ttu-id="98042-103">Lizenzanforderungen</span><span class="sxs-lookup"><span data-stu-id="98042-103">License requirements</span></span>

## <span data-ttu-id="98042-104">Lizenzanleitung für das Mobile Device Management (MDM)</span><span class="sxs-lookup"><span data-stu-id="98042-104">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="98042-105">Wenn Sie Ihre HoloLens-Geräte verwalten möchten, benötigen Sie Azure AD und einen MDM.</span><span class="sxs-lookup"><span data-stu-id="98042-105">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="98042-106">Active Director (AD) kann nicht verwendet werden, um HoloLens-Geräte zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="98042-106">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="98042-107">Wenn Sie planen, einen anderen MDM als Intune zu verwenden, dann ist eine [Azure Active Directory-Lizenz](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="98042-107">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="98042-108">Wenn Sie Intune als MDM verwenden möchten, informieren Sie sich in der [Liste der Suites](https://docs.microsoft.com/intune/fundamentals/licenses), die Intune-Lizenzen beinhalten.</span><span class="sxs-lookup"><span data-stu-id="98042-108">If you plan on using Intune as your MDM, read up on the [list of suites](https://docs.microsoft.com/intune/fundamentals/licenses) that include Intune licenses.</span></span> **<span data-ttu-id="98042-109">Bitte beachten Sie, dass Azure AD in den meisten dieser Suites enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="98042-109">Please note that Azure AD is included in the majority of these suites.</span></span>**

## <span data-ttu-id="98042-110">Ermitteln der für Ihr Szenario und Ihre Produkte erforderlichen Lizenzen</span><span class="sxs-lookup"><span data-stu-id="98042-110">Identify the licenses needed for your scenario and products</span></span>

### <span data-ttu-id="98042-111">Lizenzanforderungen für HoloLens (1. Generation)</span><span class="sxs-lookup"><span data-stu-id="98042-111">HoloLens (1st gen) Licenses Requirements</span></span>

<span data-ttu-id="98042-112">Möglicherweise müssen Sie Ihr HoloLens-Gerät (1. Generation) auf Windows Holographic for Business aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="98042-112">You may need to upgrade your HoloLens (1st gen) device to Windows Holographic for Business.</span></span> <span data-ttu-id="98042-113">(Weitere Informationen finden Sie unter [Kommerzielle Funktionen von HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions), um festzustellen, ob ein Upgrade erforderlich ist).</span><span class="sxs-lookup"><span data-stu-id="98042-113">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="98042-114">Wenn dies der Fall ist, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="98042-114">If so, you will need to do the following:</span></span>

- <span data-ttu-id="98042-115">Erwerben Sie eine XML-Datei mit der HoloLens Enterprise-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="98042-115">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="98042-116">Wenden Sie die XML-Datei auf HoloLens an.</span><span class="sxs-lookup"><span data-stu-id="98042-116">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="98042-117">Hierfür können Sie ein [Bereitstellungspaket](hololens-provisioning.md) oder Ihren [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade) verwenden.</span><span class="sxs-lookup"><span data-stu-id="98042-117">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <span data-ttu-id="98042-118">Lizenzanforderungen für Remote Assist</span><span class="sxs-lookup"><span data-stu-id="98042-118">Remote Assist License Requirements</span></span>

<span data-ttu-id="98042-119">Vergewissern Sie sich, dass Sie über die erforderlichen Lizenzen und das erforderliche Gerät verfügen. Dies können Sie in der Dokumentation [Anforderungen](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) überprüfen.</span><span class="sxs-lookup"><span data-stu-id="98042-119">Make sure you have the required licensing and device, which you can check in the [requirements](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) documentation.</span></span>

1. [<span data-ttu-id="98042-120">Remote Assist-Lizenz</span><span class="sxs-lookup"><span data-stu-id="98042-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. <span data-ttu-id="98042-121">Oder probieren Sie eine [Remote Assist-Testversion](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist) aus.</span><span class="sxs-lookup"><span data-stu-id="98042-121">Or try a [Remote Assist trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span></span>
1. [<span data-ttu-id="98042-122">Teams Freemium/Teams</span><span class="sxs-lookup"><span data-stu-id="98042-122">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="98042-123">Azure Active Directory (Azure AD)-Lizenz</span><span class="sxs-lookup"><span data-stu-id="98042-123">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="98042-124">Wenn Sie beabsichtigen, **[dieses mandantenübergreifende Szenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** zu implementieren, benötigen Sie möglicherweise eine Lizenz für Informationsbarrieren.</span><span class="sxs-lookup"><span data-stu-id="98042-124">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="98042-125">Bitte lesen Sie [diesen Artikel](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary), um festzustellen, ob eine Lizenz für Informationsbarrieren erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="98042-125">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <span data-ttu-id="98042-126">Leitfäden zu Lizenzanforderungen</span><span class="sxs-lookup"><span data-stu-id="98042-126">Guides License Requirements</span></span>

<span data-ttu-id="98042-127">Sehen Sie sich die [aktualisierten Lizenzierungs- und Geräteanforderungen](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements) an.</span><span class="sxs-lookup"><span data-stu-id="98042-127">Check out the [updated licensing and device requirements](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="98042-128">Azure Active Directory (Azure AD)-Lizenz</span><span class="sxs-lookup"><span data-stu-id="98042-128">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="98042-129">Power BI</span><span class="sxs-lookup"><span data-stu-id="98042-129">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="98042-130">Handbücher</span><span class="sxs-lookup"><span data-stu-id="98042-130">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
