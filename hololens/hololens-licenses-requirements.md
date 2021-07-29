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
- HoloLens 2
ms.openlocfilehash: bd7a7d03c81dced4fb66d8ebb176887811e823c9
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640276"
---
# <a name="license-requirements"></a>Lizenzanforderungen

## <a name="hololens-2-device-managed"></a>HoloLens 2-Gerät (verwaltet)

[Azure AD-Konto](/azure/active-directory/)

> [!IMPORTANT]
> Active Directory (AD) kann nicht zur Verwaltung von HoloLens-Geräten verwendet werden.

[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) oder eine andere MDM-Lösung.
- [Windows Autopilot für HoloLens 2](hololens2-autopilot.md): vereinfacht die Bereitstellung für IT-Administratoren und Endbenutzer. IT-Administratoren können HoloLens 2-Richtlinien vorkonfigurieren, und die Geräte werden beim ersten Systemstart ohne Benutzereingriff in betriebsbereitem Zustand bereitgestellt. 

  > [!NOTE]
  > Für Windows Autopilot müssen [Azure P1](/azure/active-directory/fundamentals/active-directory-whatis) und [Automatische Registrierung](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) vorab konfiguriert worden sein, damit der Autopilot-Ablauf und die Gerätebereitstellung mit geringem Arbeitsaufwand durchgeführt werden können. 

### <a name="business-use-case"></a>Geschäftlicher Anwendungsfall: 

- [Bereitstellungsszenario A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices): Proof-of-Concept- oder Pilotbereitstellung.

- [Bereitstellungsszenario B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network): Bereitstellung im großen Maßstab.

## <a name="hololens-2-device-only-non-managed"></a>Nur HoloLens 2-Gerät (nicht verwaltet)

Wenn Sie entweder ein Microsoft-Konto (MSA) oder ein lokales Konto verwenden, sind für diese Konten keine zusätzlichen Lizenzen erforderlich.

[Lokales Konto](/windows/security/identity-protection/access-control/local-accounts)

- Dieses Konto muss im Voraus mit dem Windows Configuration Designer (WCD) [bereitgestellt](hololens-provisioning.md#provisioning-package-hololens-wizard) werden.

[Microsoft-Konto (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> Mehrere Benutzer werden für ein Gerät, das eins dieser Konten verwendet, nicht unterstützt.

### <a name="business-use-case"></a>Geschäftlicher Anwendungsfall: 

- [Bereitstellungsszenario C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment): Offlinebereitstellung oder sichere Bereitstellung.
 
## <a name="dynamics-365-licensing-and-requirements"></a>Dynamics 365-Lizenzierung und -Anforderungen

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>Admin

- Azure AD-Konto (erforderlich für den Erwerb des Abonnements und die Zuweisung von Lizenzen)
- [Remote Assist-Abonnement](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (oder [Remote Assist-Testversion](/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist-Benutzer

- Azure AD-Konto

- Remote Assist-Lizenz 

  > [!NOTE]
  > Microsoft Teams bildet ein Bundle mit Remote Assist

- Netzwerkverbindung

#### <a name="microsoft-teams-user"></a>Microsoft Teams-Benutzer

- Azure AD-Konto

- Microsoft Teams oder [Teams Freemium](https://products.office.com/microsoft-teams/free).

- Netzwerkverbindungen

Wenn Sie dieses [mandantenübergreifende Szenario](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants) implementieren möchten, benötigen Sie möglicherweise eine Lizenz für Informationsbarrieren. Bitte lesen Sie [diesen Artikel](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary), um zu bestimmen, ob eine Lizenz für Informationsbarrieren erforderlich ist.

### <a name="dynamics-365-guides"></a>Dynamics 365-Leitfäden 

#### <a name="admin"></a>Admin

- Azure AD-Konto (erforderlich für den Erwerb des Abonnements und die Zuweisung von Lizenzen)
- Dynamics 365 [Guides-Abonnement oder kostenlose Testversion](/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>Guides-Autor

1. Azure AD-Konto
1. [Dynamics 365 Guides-Lizenz](/dynamics365/mixed-reality/guides/requirements)
1. Dynamics 365 Guides-Anwendung auf einem Computer oder HoloLens installiert
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (wird zum Anzeigen des Analytics-Dashboards verwendet)
1. Rolle „Autor“ (zum Erstellen von Leitfäden)
1. Netzwerkverbindung

#### <a name="guides-user"></a>Guides-Benutzer

1. Azure AD-Konto
1. [Dynamics 365 Guides-Lizenz](/dynamics365/mixed-reality/guides/requirements)
1. Dynamics 365 Guides-App auf einer HoloLens installiert
1. Operator-Rolle (zum Testen oder Verwenden von Leitfäden)
1. Netzwerkverbindung
