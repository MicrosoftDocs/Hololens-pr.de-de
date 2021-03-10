---
title: Registrieren von HoloLens in MDM
description: Erfahren Sie, wie Sie HoloLens in der Verwaltung mobiler Geräte (Mobile Device Management, MDM) registrieren, um die Verwaltung mehrerer Geräte zu vereinfachen.
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
ms.openlocfilehash: 4042cce40bea2c3d52d6ffc5d2908f6fde7cf222
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400675"
---
# <a name="enroll-hololens-in-mdm"></a>Registrieren von HoloLens in MDM

Sie können mehrere Microsoft HoloLens-Geräte gleichzeitig mit Lösungen wie [Microsoft Intune verwalten.](https://docs.microsoft.com/intune/windows-holographic-for-business) Sie können Einstellungen verwalten, zu installierende Apps auswählen und Sicherheitskonfigurationen festlegen, die auf die Anforderungen Ihrer Organisation zugeschnitten sind. Weitere Informationen finden Sie unter [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), und [Konfigurationsdienstanbieter (Configuration Service Providers, CSPs), die in Windows Holographic unterstützt werden](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) sowie [Richtlinien, die von Windows Holographic for Business unterstützt werden](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Die mobile Geräteverwaltung (MDM), einschließlich VPN, BitLocker und Kiosk-Modus-Features ist nur verfügbar, wenn Sie [ein Upgrade auf Windows Holographic for Business durchführen](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Anforderungen

 Ihre Organisation muss mobile Geräteverwaltung (Mobile Device Management, MDM) einrichten, um HoloLens-Geräte verwalten zu können. Ihr MDM-Anbieter kann Microsoft Intune oder ein Drittanbieter sein, der die Microsoft-MDM-APIs verwendet.
 
## <a name="different-ways-to-enroll"></a>Unterschiedliche Möglichkeiten zur Registrierung

Je nach [Identitätstyp, der](hololens-identity.md) entweder während der OOBE oder nach der Anmeldung ausgewählt wurde, gibt es unterschiedliche Registrierungsmethoden.

- Wenn Identity Azure AD ist, dann entweder während der Schaltfläche OOBE oder **Einstellungen App**Access Work  ->  **oder School**  ->  **Connect.**
    - Für Azure AD erfolgt [die automatische MDM-Registrierung](hololens-enroll-mdm.md#auto-enrollment-in-mdm) nur, wenn Azure AD mit Registrierungs-URLs konfiguriert wurde. 
     
- Wenn Identity Azure AD ist und das Gerät beim Intune-MDM-Server mit einem bestimmten Konfigurationsprofil vorab registriert wurde, tritt azure AD-Join und die automatische [MDM-Registrierung](hololens-enroll-mdm.md#auto-enrollment-in-mdm) während der OOBE auf.
    - Auch als [Autopilot-Fluss](hololens2-autopilot.md) bezeichnet Verfügbar in [19041.1103+ Builds](hololens-release-notes.md#windows-holographic-version-2004).
    

- Wenn Identity MSA ist, verwenden Sie die Schaltfläche **Einstellungen App**Access Work  ->  **oder School**  ->  **Connect.**
    - Wird auch als Add Work Account (AWA)-Fluss bezeichnet.
- Wenn Identity der lokale Benutzer ist, verwenden Sie **Einstellungen App**Access Work  ->  **oder School**Registrieren nur im Link zur  ->  **Geräteverwaltung.**
    - Wird auch als reiner MDM-Registrierungsfluss bezeichnet.

Sobald das Gerät bei Ihrem MDM-Server registriert wurde, gibt die Einstellungs-App nun an, dass das Gerät in der Geräteverwaltung registriert ist.

## <a name="auto-enrollment-in-mdm"></a>Automatische Registrierung in MDM

Wenn Ihre Organisation über ein [Azure Premium-Abonnement](https://azure.microsoft.com/overview/)verfügt und Azure Active Directory (Azure AD) und eine MDM-Lösung verwendet, die ein Azure AD-Token für die Authentifizierung akzeptiert (derzeit nur in Microsoft Intune und AirWatch unterstützt), kann Ihr IT-Administrator Azure AD so konfigurieren, dass die MDM-Registrierung automatisch zulässig ist, nachdem sich der Benutzer mit seinem Azure AD-Konto angemeldet hat. [Erfahren Sie, wie Sie die Azure AD-Registrierung konfigurieren.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Wenn die automatische Registrierung aktiviert ist, ist keine zusätzliche manuelle Registrierung erforderlich. Wenn der Benutzer sich mit einem Azure AD-Konto anmeldet, wird das Gerät nach der ersten Ausführung in MDM registriert.

Wenn ein Gerät Azure AD Beigetreten ist, kann sich dies auf die Personen auswirken, die als [Gerätebesitzer angesehen werden.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Aufheben der Registrierung von HoloLens aus Intune

HoloLens 2 ist zwar Windows 10-Gerät, kann aber nicht einfach von Intune entrollt werden. Wenn Sie holoLens aus Azure AD nicht mehr mit HoloLens in einen anderen Azure AD-Mandanten bzw. einen anderen Azure AD-Mandanten bzw. einen anderen Azure AD-Mandanten verwenden möchten, müssen Sie das Gerät [zurücksetzen/erneut](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) schräg schräg setzen.