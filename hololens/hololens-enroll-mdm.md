---
title: Registrieren von HoloLens in MDM
description: Erfahren Sie, wie Sie HoloLens für die Verwaltung mobiler Geräte (Mobile Device Management, MDM) registrieren, um die Verwaltung mehrerer Geräte zu vereinfachen.
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309717"
---
# <a name="enroll-hololens-in-mdm"></a>Registrieren von HoloLens in MDM

Sie können mehrere Microsoft HoloLens gleichzeitig mithilfe von Lösungen wie [Microsoft Intune.](https://docs.microsoft.com/intune/windows-holographic-for-business) Sie können Einstellungen verwalten, zu installierende Apps auswählen und Sicherheitskonfigurationen festlegen, die auf die Anforderungen Ihrer Organisation zugeschnitten sind. Weitere Informationen finden Sie unter Verwalten von Geräten, auf denen [Windows Holographic](https://docs.microsoft.com/intune/windows-holographic-for-business)mit Microsoft Intune ausgeführt wird, den [Konfigurationsdienstanbietern (Configuration Service Providers, CSPs),](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)die in Windows Holographic unterstützt werden, und den von [Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Die Verwaltung mobiler Geräte (Mobile Device Management, MDM), einschließlich der Vpn-, BitLocker- und Kioskmodusfunktionen, ist nur verfügbar, wenn Sie ein Upgrade auf [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

## <a name="requirements"></a>Anforderungen

 Ihre Organisation muss Mobile Geräteverwaltung (MDM) einrichten, um HoloLens-Geräte verwalten zu können. Ihr MDM-Anbieter kann Microsoft Intune oder ein Drittanbieter sein, der die Microsoft-MDM-APIs verwendet.
 
## <a name="different-ways-to-enroll"></a>Verschiedene Möglichkeiten zum Registrieren

Abhängig vom Typ der Identität, die [sie](hololens-identity.md) entweder während der OOBE oder nach der Anmeldung ausgewählt haben, gibt es verschiedene Registrierungsmethoden.

- Wenn Identität Azure AD ist, klicken Sie entweder während der OOBE- oder **Einstellungen-App-Zugriff** auf Die Arbeits-  ->  **oder**  ->  **Schul-/Schul-Connect-Schaltfläche.**
    - Für Azure AD erfolgt [die automatische MDM-Registrierung](hololens-enroll-mdm.md#auto-enrollment-in-mdm) nur, wenn Azure AD mit Registrierungs-URLs konfiguriert wurde.
     
- Wenn die Identität Azure AD und das Gerät beim Intune-MDM-Server vorab registriert wurde, dem ein bestimmtes Konfigurationsprofil zugewiesen ist, erfolgen Azure AD-Join und die automatische [MDM-Registrierung](hololens-enroll-mdm.md#auto-enrollment-in-mdm) während der OOBE.
    - Wird auch [als Autopilot-Flow](hololens2-autopilot.md) bezeichnet: Verfügbar in [Builds ab 19041.1103.](hololens-release-notes.md#windows-holographic-version-2004)
    

- Wenn Identität MSA ist, verwenden Sie die Schaltfläche **App-Zugriff** auf  ->  **Arbeits-** oder  ->  **Schul-/Schulzugriff.**
    - Wird auch als AWA-Flow (Add Work Account) bezeichnet.
- Wenn Identität lokaler Benutzer ist, verwenden Sie den Link App-Zugriff auf Arbeits- oder Schulkonto nur   ->    ->  **bei der Geräteverwaltung** registrieren.
    - Wird auch als reiner MDM-Registrierungsablauf bezeichnet.

Sobald das Gerät bei Ihrem MDM-Server registriert ist, gibt die App Einstellungen an, dass das Gerät für die Geräteverwaltung registriert ist.

## <a name="auto-enrollment-in-mdm"></a>Automatische Registrierung in MDM

Wenn Ihre Organisation über ein [Azure Premium-Abonnement](https://azure.microsoft.com/overview/)verfügt und Azure Active Directory (Azure AD) und eine MDM-Lösung verwendet, die ein Azure AD Token für die Authentifizierung akzeptiert (derzeit nur in Microsoft Intune und AirWatch unterstützt), kann Ihr IT-Administrator Azure AD so konfigurieren, dass die MDM-Registrierung automatisch zugelassen wird, nachdem sich der Benutzer mit dem Azure AD-Konto anmeldet. [Erfahren Sie, wie Sie die Azure AD-Registrierung konfigurieren.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Wenn die automatische Registrierung aktiviert ist, ist keine zusätzliche manuelle Registrierung erforderlich. Wenn der Benutzer sich mit einem Azure AD-Konto anmeldet, wird das Gerät nach der ersten Ausführung in MDM registriert.

Wenn ein Gerät Azure AD Eingebunden ist, kann sich dies darauf auswirken, wer den [Gerätebesitzer](security-adminless-os.md#device-owner)betrachtet hat.

## <a name="unenroll-hololens-from-intune"></a>Aufheben der Registrierung von HoloLens bei Intune

Abhängig von der Registrierungsmethode ist die Registrierung Ihres Geräts möglicherweise nicht verfügbar.

Wenn Ihr Gerät mit einem Azure AD-Konto oder Autopilot registriert wurde, kann die Registrierung bei Intune nicht aufgehoben werden. Wenn Sie HoloLens von Azure AD aufheben oder es einem anderen Mandanten als Azure AD Mandanten wieder gliedern möchten, müssen Sie das Gerät [zurücksetzen/einen neuen Schrägstrich setzen.](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device)

Wenn Ihr Gerät über ein MSA-Konto registriert wurde, das ein Arbeitskonto hinzugefügt hat, oder über ein lokales Konto, das nur für die Geräteverwaltung registriert wurde, können Sie die Registrierung des Geräts aufheben. Öffnen Sie die Startmenü, und wählen Sie dann die Schaltfläche **Einstellungen**  ->  **App-Zugriff auf Arbeits- oder SchulkontoKontoverbindung**  ->    ->  **aus.**