---
title: Lizenzanforderungen
description: ''
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
ms.openlocfilehash: 18a583f407b19c5b86870a49b8182d45f46a45f5
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857803"
---
# <span data-ttu-id="55177-102">Lizenzanforderungen</span><span class="sxs-lookup"><span data-stu-id="55177-102">License requirements</span></span>

## <span data-ttu-id="55177-103">Lizenzanleitung für das Mobile Device Management (MDM)</span><span class="sxs-lookup"><span data-stu-id="55177-103">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="55177-104">Wenn Sie Ihre HoloLens-Geräte verwalten möchten, benötigen Sie Azure AD und einen MDM.</span><span class="sxs-lookup"><span data-stu-id="55177-104">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="55177-105">Active Director (AD) kann nicht verwendet werden, um HoloLens-Geräte zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="55177-105">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="55177-106">Wenn Sie planen, einen anderen MDM als Intune zu verwenden, dann ist eine [Azure Active Directory-Lizenz](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="55177-106">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="55177-107">Wenn Sie Intune als MDM verwenden möchten, finden Sie [hier](https://docs.microsoft.com/intune/fundamentals/licenses) eine Liste der Suites mit Intune-Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="55177-107">If you plan on using Intune as your MDM,  [here](https://docs.microsoft.com/intune/fundamentals/licenses) are a list of suites that includes Intune licenses.</span></span> **<span data-ttu-id="55177-108">Bitte beachten Sie, dass Azure AD in den meisten dieser Suites enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="55177-108">Please note that Azure AD is included in the majority of these suites.</span></span>**

## <span data-ttu-id="55177-109">Ermitteln der für Ihr Szenario und Ihre Produkte erforderlichen Lizenzen</span><span class="sxs-lookup"><span data-stu-id="55177-109">Identify the licenses needed for your scenario and products</span></span>

### <span data-ttu-id="55177-110">HoloLens-Lizenzanforderungen</span><span class="sxs-lookup"><span data-stu-id="55177-110">HoloLens Licenses Requirements</span></span>

<span data-ttu-id="55177-111">Möglicherweise müssen Sie Ihr HoloLens-Gerät der 1. Generation auf Windows Holographic for Business aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="55177-111">You may need to upgrade your HoloLens 1st Gen Device to Windows Holographic for Business.</span></span> <span data-ttu-id="55177-112">(Weitere Informationen finden Sie unter [Kommerzielle Funktionen von HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions), um festzustellen, ob ein Upgrade erforderlich ist).</span><span class="sxs-lookup"><span data-stu-id="55177-112">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="55177-113">Wenn dies der Fall ist, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="55177-113">If so, you will need to do the following:</span></span>

- <span data-ttu-id="55177-114">Erwerben Sie eine XML-Datei mit der HoloLens Enterprise-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="55177-114">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="55177-115">Wenden Sie die XML-Datei auf HoloLens an.</span><span class="sxs-lookup"><span data-stu-id="55177-115">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="55177-116">Hierfür können Sie ein [Bereitstellungspaket](hololens-provisioning.md) oder Ihren [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade) verwenden.</span><span class="sxs-lookup"><span data-stu-id="55177-116">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <span data-ttu-id="55177-117">Lizenzanforderungen für Remote Assist</span><span class="sxs-lookup"><span data-stu-id="55177-117">Remote Assist License Requirements</span></span>

<span data-ttu-id="55177-118">Stellen Sie sicher, dass Sie über die erforderliche Lizenzierung und das erforderliche Gerät verfügen.</span><span class="sxs-lookup"><span data-stu-id="55177-118">Make sure you have the required licensing and device.</span></span> <span data-ttu-id="55177-119">Aktualisierte Lizenzierungs- und Produktanforderungen finden Sie [Hier](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).</span><span class="sxs-lookup"><span data-stu-id="55177-119">Updated licensing and product requirements can be found [here](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).</span></span>

1. [<span data-ttu-id="55177-120">Remote Assist-Lizenz</span><span class="sxs-lookup"><span data-stu-id="55177-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
1. [<span data-ttu-id="55177-121">Teams Freemium/Teams</span><span class="sxs-lookup"><span data-stu-id="55177-121">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="55177-122">Azure Active Directory (Azure AD)-Lizenz</span><span class="sxs-lookup"><span data-stu-id="55177-122">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="55177-123">Wenn Sie beabsichtigen, **[dieses mandantenübergreifende Szenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** zu implementieren, benötigen Sie möglicherweise eine Lizenz für Informationsbarrieren.</span><span class="sxs-lookup"><span data-stu-id="55177-123">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="55177-124">Bitte lesen Sie [diesen Artikel](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary), um festzustellen, ob eine Lizenz für Informationsbarrieren erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="55177-124">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <span data-ttu-id="55177-125">Leitfäden zu Lizenzanforderungen</span><span class="sxs-lookup"><span data-stu-id="55177-125">Guides License Requirements</span></span>

<span data-ttu-id="55177-126">Aktualisierte Lizenzierungs- und Geräteanforderungen finden Sie [Hier](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span><span class="sxs-lookup"><span data-stu-id="55177-126">Updated licensing and device requirements can be found [here](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="55177-127">Azure Active Directory (Azure AD)-Lizenz</span><span class="sxs-lookup"><span data-stu-id="55177-127">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="55177-128">Power BI</span><span class="sxs-lookup"><span data-stu-id="55177-128">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="55177-129">Handbücher</span><span class="sxs-lookup"><span data-stu-id="55177-129">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
