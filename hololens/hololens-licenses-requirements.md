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
ms.openlocfilehash: 6224cd5e07794d9fca3c0a406e787d1a3fd88b43
ms.sourcegitcommit: bd55edcc855e20d6709c7e535573f43785155d41
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2021
ms.locfileid: "114661711"
---
# <a name="license-requirements"></a>Lizenzanforderungen

## <a name="overview"></a>Übersicht
Diese Seite bietet eine allgemeine Übersicht der Lizenzen und Konten, die zum Bereitstellen sowohl verwalteter als auch nicht verwalteter HoloLens 2-Geräte in Ihrer Organisation erforderlich sind. Sie enthält ferner Informationen zur Lizenzierung von Dynamics 365 [Remote Assist](#dynamics-365-remote-assist) und [Guides](#dynamics-365-guides).

## <a name="hololens-2-license-and-account-requirements"></a>HoloLens 2 Lizenz- und Kontoanforderungen

 
|       &nbsp;      | Verwaltete HoloLens | Nicht verwaltete HoloLens |
|-------------------|-----------------|---------------------|
| **Geschäftlicher Anwendungsfall** | | |
| [Bereitstellen auf mit der Cloud verbundenen Geräten: Proof-of-Concept/Pilotbereitstellung](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices)  | ✔️| |
| [Bereitstellen innerhalb des Netzwerks einer Organisation: Bereitstellung im großen Maßstab](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) | ✔️| |
| [Bereitstellen in einer sicheren Offlineumgebung](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) | | ✔️ |
| **Lizenzen** | | |
| Azure Active Directory | ✔️ | |
| MDM (Intune<sup>1</sup> oder <sup>2</sup>) | ✔️  | |
| **Konten** |  | |
| Azure AD-Administratorkonto | ✔️ |  |
| Azure AD-Benutzerkonto | ✔️ | |
| [Microsoft-Konto (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)| | ✔️ |
| [Lokales Konto](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | | ✔️ |
- <sup>1</sup> [Automatische Registrierung](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) während der Geräte-Ersteinrichtung, die die Registrierung bei und den Beitritt zu Azure Active Directory beinhaltet und die Verwaltung des Geräts durch Intune ermöglicht.
- <sup>2</sup> [Windows Autopilot für HoloLens 2](hololens2-autopilot.md) vereinfacht die Bereitstellungserfahrung sowohl für IT-Administratoren als auch für Endbenutzer. IT-Administratoren können HoloLens 2-Richtlinien vorkonfigurieren, und die Geräte werden beim ersten Systemstart ohne Benutzereingriff in betriebsbereitem Zustand bereitgestellt.
- <sup>3</sup> Dieses Konto muss im Voraus mit dem Windows Configuration Designer (WCD) [bereitgestellt](hololens-provisioning.md#provisioning-package-hololens-wizard) werden.

> [!IMPORTANT]
> Active Directory (AD) kann nicht zur Verwaltung von HoloLens-Geräten verwendet werden.
 
> [!WARNING]
> Mehrere Benutzer werden für ein Gerät, das entweder ein MSA- oder ein lokales Konto verwendet, nicht unterstützt.

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

- Microsoft Teams oder [Teams Freemium](https://products.office.com/microsoft-teams/free)

- Netzwerkverbindungen

Wenn Sie dieses [mandantenübergreifende Szenario](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants) implementieren möchten, benötigen Sie möglicherweise eine Lizenz für Informationsbarrieren. Bitte lesen Sie [diesen Artikel](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary), um zu bestimmen, ob eine Lizenz für Informationsbarrieren erforderlich ist.

### <a name="dynamics-365-guides"></a>Dynamics 365-Leitfäden 

#### <a name="admin"></a>Admin

1. Azure AD-Konto (erforderlich für den Erwerb des Abonnements und die Zuweisung von Lizenzen)
2. Dynamics 365 [Guides-Abonnement oder kostenlose Testversion](/dynamics365/mixed-reality/guides/setup-step-one)

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
