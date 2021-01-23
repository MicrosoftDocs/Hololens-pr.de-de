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
# Lizenzanforderungen

## Lizenzanleitung für das Mobile Device Management (MDM)

Wenn Sie Ihre HoloLens-Geräte verwalten möchten, benötigen Sie Azure AD und einen MDM. Active Director (AD) kann nicht verwendet werden, um HoloLens-Geräte zu verwalten.
Wenn Sie planen, einen anderen MDM als Intune zu verwenden, dann ist eine [Azure Active Directory-Lizenz](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) erforderlich.
Wenn Sie Intune als MDM verwenden möchten, informieren Sie sich in der [Liste der Suites](https://docs.microsoft.com/intune/fundamentals/licenses), die Intune-Lizenzen beinhalten. **Bitte beachten Sie, dass Azure AD in den meisten dieser Suites enthalten ist.**

## Ermitteln der für Ihr Szenario und Ihre Produkte erforderlichen Lizenzen

### Lizenzanforderungen für HoloLens (1. Generation)

Möglicherweise müssen Sie Ihr HoloLens-Gerät (1. Generation) auf Windows Holographic for Business aktualisieren. (Weitere Informationen finden Sie unter [Kommerzielle Funktionen von HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions), um festzustellen, ob ein Upgrade erforderlich ist).

 Wenn dies der Fall ist, müssen Sie die folgenden Schritte ausführen:

- Erwerben Sie eine XML-Datei mit der HoloLens Enterprise-Lizenz.
- Wenden Sie die XML-Datei auf HoloLens an. Hierfür können Sie ein [Bereitstellungspaket](hololens-provisioning.md) oder Ihren [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade) verwenden.

### Lizenzanforderungen für Remote Assist

Vergewissern Sie sich, dass Sie über die erforderlichen Lizenzen und das erforderliche Gerät verfügen. Dies können Sie in der Dokumentation [Anforderungen](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) überprüfen.

1. [Remote Assist-Lizenz](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. Oder probieren Sie eine [Remote Assist-Testversion](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist) aus.
1. [Teams Freemium/Teams](https://products.office.com/microsoft-teams/free)
1. [Azure Active Directory (Azure AD)-Lizenz](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

Wenn Sie beabsichtigen, **[dieses mandantenübergreifende Szenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** zu implementieren, benötigen Sie möglicherweise eine Lizenz für Informationsbarrieren. Bitte lesen Sie [diesen Artikel](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary), um festzustellen, ob eine Lizenz für Informationsbarrieren erforderlich ist.

### Leitfäden zu Lizenzanforderungen

Sehen Sie sich die [aktualisierten Lizenzierungs- und Geräteanforderungen](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements) an.

1. [Azure Active Directory (Azure AD)-Lizenz](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Power BI](https://powerbi.microsoft.com/desktop/)
1. [Handbücher](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
