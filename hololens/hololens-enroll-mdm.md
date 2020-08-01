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
ms.openlocfilehash: 1dd6c2e6cde980b86ac810f82d27b3b88f20f336
ms.sourcegitcommit: 7edbb99e0972d3d857e5e87c062c3c64cacc1f41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2020
ms.locfileid: "10903221"
---
# Registrieren von HoloLens in MDM

Sie können mehrere Microsoft HoloLens-Geräte gleichzeitig mit Lösungen wie [Microsoft InTune](https://docs.microsoft.com/intune/windows-holographic-for-business)verwalten. Sie können Einstellungen verwalten, zu installierende Apps auswählen und Sicherheitskonfigurationen festlegen, die auf die Anforderungen Ihrer Organisation zugeschnitten sind. Weitere Informationen finden Sie unter [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), und [Konfigurationsdienstanbieter (Configuration Service Providers, CSPs), die in Windows Holographic unterstützt werden](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) sowie [Richtlinien, die von Windows Holographic for Business unterstützt werden](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Die mobile Geräteverwaltung (MDM), einschließlich VPN, BitLocker und Kiosk-Modus-Features ist nur verfügbar, wenn Sie [ein Upgrade auf Windows Holographic for Business durchführen](hololens1-upgrade-enterprise.md).

## Anforderungen

 Für Ihre Organisation muss die Mobile Device Management (MDM) eingerichtet sein, um HoloLens-Geräte verwalten zu können. Ihr MDM-Anbieter kann Microsoft Intune oder ein Drittanbieter sein, der die Microsoft-MDM-APIs verwendet.
 
## Verschiedene Methoden zum Registrieren

Je nach dem Typ der Identität, die während der OOBE oder der Post Anmeldung ausgewählt wurde, gibt es verschiedene Methoden für die Registrierung. Wenn Sie mehr über die einzelnen Identitätstypen auf HoloLens erfahren möchten, besuchen Sie bitte [Diese Seite](hololens-identity.md).

- Wenn Identity Aad ist, wählen Sie entweder während der OOBE-oder **Einstellungen-App**  ->  **Access work oder School**  ->  **Connect** .
    - Bei Aad erfolgt die automatische MDM-Registrierung nur, wenn Aad mit Registrierungs-URLs konfiguriert wurde.
- Wenn Identity Aad ist und Device für den InTune-MDM-Server mit einem bestimmten Konfigurationsprofil bereits registriert wurde, werden Aad-Join und die Registrierung automatisch während OOBE ausgeführt.
    - Auch als [Autopilot-Flow](hololens2-autopilot.md) verfügbar, der in [19041.1103 +-Builds](hololens-release-notes.md#windows-holographic-version-2004)verfügbar ist.
- Wenn Identity MSA ist, verwenden Sie die **Einstellungen App**  ->  **Access work oder School**  ->  **Connect** .
    - Wird auch als Add work Account (AWA)-Flow bezeichnet.
- Wenn Identität ein lokaler Benutzer ist, verwenden Sie die **Einstellungen App**  ->  **Access work oder School**  ->  **nur registrieren in Device Management** Link.
    - Wird auch als reiner MDM-Registrierungs Fluss bezeichnet.

Nachdem das Gerät für Ihren MDM-Server registriert wurde, wird in der Einstellungs-APP nun wiedergespiegelt, dass das Gerät für die Geräteverwaltung registriert ist.

## Automatische Registrierung in MDM

Wenn Ihre Organisation Azure Active Directory (Azure AD) und eine MDM-Lösung verwendet, die ein AAD-Token für die Authentifizierung akzeptiert (zurzeit nur in Microsoft Intune und AirWatch unterstützt), kann der IT-Administrator Azure AD so konfigurieren, dass die MDM-Registrierung automatisch zugelassen wird, wenn der Benutzer sich mit seinem Azure AD-Konto angemeldet hat. [Erfahren Sie, wie Sie die Azure AD-Registrierung konfigurieren.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Wenn die automatische Registrierung aktiviert ist, ist keine zusätzliche manuelle Registrierung erforderlich. Wenn der Benutzer sich mit einem Azure AD-Konto anmeldet, wird das Gerät nach der ersten Ausführung in MDM registriert.

## Abmelden von HoloLens aus InTune

Weitere Informationen zur Registrierung eines Geräts finden Sie auf [dieser Seite](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment). 
