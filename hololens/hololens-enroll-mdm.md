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
# Registrieren von HoloLens in MDM

Sie können mehrere Microsoft HoloLens-Geräte gleichzeitig mit Lösungen wie [Microsoft Intune verwalten.](https://docs.microsoft.com/intune/windows-holographic-for-business) Sie können Einstellungen verwalten, zu installierende Apps auswählen und Sicherheitskonfigurationen festlegen, die auf die Anforderungen Ihrer Organisation zugeschnitten sind. Weitere Informationen finden Sie unter [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), und [Konfigurationsdienstanbieter (Configuration Service Providers, CSPs), die in Windows Holographic unterstützt werden](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) sowie [Richtlinien, die von Windows Holographic for Business unterstützt werden](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Die mobile Geräteverwaltung (MDM), einschließlich VPN, BitLocker und Kiosk-Modus-Features ist nur verfügbar, wenn Sie [ein Upgrade auf Windows Holographic for Business durchführen](hololens1-upgrade-enterprise.md).

## Anforderungen

 Ihre Organisation muss die mobile Geräteverwaltung (Mobile Device Management, MDM) einrichten, um die Geräte von HoloLens verwalten zu können. Ihr MDM-Anbieter kann Microsoft Intune oder ein Drittanbieter sein, der die Microsoft-MDM-APIs verwendet.
 
## Unterschiedliche Registrierungswege

Je nach Identitätstyp, der während der OOBE oder nach der Anmeldung ausgewählt wurde, gibt es unterschiedliche Registrierungsmethoden. Weitere Informationen zu den einzelnen Identitätstypen auf HoloLens finden Sie [auf dieser Seite.](hololens-identity.md)

- Wenn Identity Azure AD ist, dann entweder während der OOBE oder der **Schaltfläche "App-Zugriff**auf Arbeit" oder  ->  **"School**  ->  **Connect".**
    - Bei Azure AD erfolgt die automatische MDM-Registrierung nur, wenn Azure AD mit Registrierungs-URLs konfiguriert wurde.
- Wenn "Identity" Azure AD ist und das Gerät vor dem Intune-MDM-Server registriert wurde und ihm ein bestimmtes Konfigurationsprofil zugewiesen wurde, erfolgt Azure AD-Join und die Registrierung automatisch während der OOBE.
    - Wird auch [als "Autopilot Flow"](hololens2-autopilot.md) bezeichnet und ist in [19041.1103+ Builds verfügbar.](hololens-release-notes.md#windows-holographic-version-2004)
- Wenn "Identity" MSA ist, verwenden Sie die Schaltfläche **"Settings App**  ->  **Access Work" oder "School**  ->  **Connect".**
    - Wird auch als Add Work Account (AWA)-Fluss bezeichnet.
- Wenn "Identität" ein lokaler Benutzer ist, verwenden Sie **"Einstellungen**App  ->  **Access Work" oder "School**Enroll" nur  ->  **im Link "Geräteverwaltung".**
    - Wird auch als reiner MDM-Registrierungsablauf bezeichnet.

Nachdem das Gerät bei Ihrem MDM-Server registriert wurde, gibt die App "Einstellungen" jetzt wieder, dass das Gerät für die Geräteverwaltung registriert ist.

## Automatische Registrierung in MDM

Wenn Ihre Organisation Azure Active Directory (Azure AD) und eine MDM-Lösung verwendet, die ein Azure AD-Token für die Authentifizierung akzeptiert (derzeit nur in Microsoft Intune und AirWatch unterstützt), kann Ihr IT-Administrator Azure AD so konfigurieren, dass die Registrierung von MDM automatisch zulässig ist, nachdem sich der Benutzer mit seinem Azure AD-Konto angemeldet hat. [Erfahren Sie, wie Sie die Azure AD-Registrierung konfigurieren.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Wenn die automatische Registrierung aktiviert ist, ist keine zusätzliche manuelle Registrierung erforderlich. Wenn der Benutzer sich mit einem Azure AD-Konto anmeldet, wird das Gerät nach der ersten Ausführung in MDM registriert.

Wenn ein Gerät mit Azure AD verbunden ist, kann sich dies darauf auswirken, wer den [Gerätebesitzer betrachtet hat.](security-adminless-os.md#device-owner)

## Aufheben der Registrierung von HoloLens in Intune

Weitere Informationen zum Unenrolling eines Geräts finden Sie auf [dieser Seite.](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment) 
