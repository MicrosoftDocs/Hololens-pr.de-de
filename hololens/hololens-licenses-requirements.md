---
title: Lizenzen für die Bereitstellung von Mixed Reality
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
ms.openlocfilehash: 0da2a2337b3b1f361ffbb698607f304efbf6d193
ms.sourcegitcommit: f3cda6c6b3bfb7ba4be5f4da66d8ed5b03ca807d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830139"
---
# Ermitteln, welche Lizenzen erforderlich sind

## Lizenzanleitung für das Mobile Device Management (MDM)

Wenn Sie Ihre HoloLens-Geräte verwalten möchten, benötigen Sie Azure AD und einen MDM. Active Director (AD) kann nicht verwendet werden, um HoloLens-Geräte zu verwalten.
Wenn Sie planen, einen anderen MDM als Intune zu verwenden, dann ist eine [Azure Active Directory-Lizenz](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) erforderlich.
Wenn Sie Intune als MDM verwenden möchten, finden Sie [hier](https://docs.microsoft.com/intune/fundamentals/licenses) eine Liste der Suites mit Intune-Lizenzen. **Bitte beachten Sie, dass Azure AD in den meisten dieser Suites enthalten ist.**

## Ermitteln der für Ihr Szenario und Ihre Produkte erforderlichen Lizenzen

### HoloLens-Lizenzanforderungen

Möglicherweise müssen Sie Ihr HoloLens-Gerät der 1. Generation auf Windows Holographic for Business aktualisieren. (Weitere Informationen finden Sie unter [Kommerzielle Funktionen von HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions), um festzustellen, ob ein Upgrade erforderlich ist).

 Wenn dies der Fall ist, müssen Sie die folgenden Schritte ausführen:

- Erwerben Sie eine XML-Datei mit der HoloLens Enterprise-Lizenz.
- Wenden Sie die XML-Datei auf HoloLens an. Hierfür können Sie ein [Bereitstellungspaket](hololens-provisioning.md) oder Ihren [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade) verwenden.

### Lizenzanforderungen für Remote Assist

Stellen Sie sicher, dass Sie über die erforderliche Lizenzierung und das erforderliche Gerät verfügen. Aktualisierte Lizenzierungs- und Produktanforderungen finden Sie [Hier](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).

1. [Remote Assist-Lizenz](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
1. [Teams Freemium/Teams](https://products.office.com/microsoft-teams/free)
1. [Azure Active Directory (Azure AD)-Lizenz](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

Wenn Sie beabsichtigen, **[dieses mandantenübergreifende Szenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** zu implementieren, benötigen Sie möglicherweise eine Lizenz für Informationsbarrieren. Bitte lesen Sie [diesen Artikel](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary), um festzustellen, ob eine Lizenz für Informationsbarrieren erforderlich ist.

### Leitfäden zu Lizenzanforderungen

Aktualisierte Lizenzierungs- und Geräteanforderungen finden Sie [Hier](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).

1. [Azure Active Directory (Azure AD)-Lizenz](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Power BI](https://powerbi.microsoft.com/desktop/)
1. [Handbücher](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
