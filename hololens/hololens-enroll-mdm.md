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
ms.openlocfilehash: a368c622c137374ea9cc544490d3492fa9d3f8c1
ms.sourcegitcommit: 749d617f3f0ce3e6363ff6cd1a03f87b9280f418
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "122979354"
---
# <a name="enroll-hololens-in-mdm"></a>Registrieren von HoloLens in MDM

Sie können mehrere Microsoft HoloLens gleichzeitig mit lösungen wie [Microsoft Intune.](/intune/windows-holographic-for-business) Sie können Einstellungen verwalten, zu installierende Apps auswählen und Sicherheitskonfigurationen festlegen, die auf die Anforderungen Ihrer Organisation zugeschnitten sind. Weitere Informationen finden Sie unter Verwalten von [Windows Holographic mit Microsoft Intune](/intune/windows-holographic-for-business), den [konfigurationsdienstanbietern (Configuration Service Providers, CSPs),](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)die in Windows Holographic unterstützt werden, und den von [Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Die Verwaltung mobiler Geräte (Mobile Device Management, MDM), einschließlich der VPN-, BitLocker- und Kioskmodusfeatures, ist nur verfügbar, wenn Sie ein Upgrade auf [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

## <a name="requirements"></a>Anforderungen

 In Ihrer Organisation muss Mobile Geräteverwaltung (MDM) eingerichtet sein, um ihre HoloLens verwalten zu können. Ihr MDM-Anbieter kann Microsoft Intune oder ein Drittanbieter sein, der die Microsoft-MDM-APIs verwendet.

## <a name="different-ways-to-enroll"></a>Verschiedene Möglichkeiten zum Registrieren

Abhängig vom Typ der Identität, die [sie](hololens-identity.md) entweder während der OOBE oder nach der Anmeldung ausgewählt haben, gibt es verschiedene Registrierungsmethoden.

- Wenn Die Identität Azure AD ist, klicken Sie entweder während der OOBE oder Einstellungen **App**  ->  **Access Work oder School**  ->  **Verbinden** Schaltfläche.
    - Für Azure AD erfolgt [die automatische MDM-Registrierung](hololens-enroll-mdm.md#auto-enrollment-in-mdm) nur, wenn Azure AD mit Registrierungs-URLs konfiguriert wurde.

- Wenn die Identität Azure AD und das Gerät beim Intune-MDM-Server vorab registriert wurde, dem ein bestimmtes Konfigurationsprofil zugewiesen ist, erfolgen Azure AD-Join und die automatische [MDM-Registrierung](hololens-enroll-mdm.md#auto-enrollment-in-mdm) während der OOBE.
    - Wird auch [als Autopilot-Flow](hololens2-autopilot.md) bezeichnet: Verfügbar in [Builds ab 19041.1103.](hololens-release-notes.md#windows-holographic-version-2004)


- Wenn Identität MSA ist, verwenden Sie Einstellungen **App** Access Work- oder  ->  **School Verbinden Schaltfläche.**  ->  
    - Wird auch als AWA-Flow (Add Work Account) bezeichnet.
- Wenn Identität lokaler Benutzer ist, verwenden Sie Einstellungen **Link App** Access Work or  ->  **School** Enroll only in device  ->  management (Nur bei **Geräteverwaltung registrieren).**
    - Wird auch als reiner MDM-Registrierungsablauf bezeichnet.

Sobald das Gerät bei Ihrem MDM-Server registriert ist, gibt die Einstellungen-App an, dass das Gerät für die Geräteverwaltung registriert ist.

## <a name="auto-enrollment-in-mdm"></a>Automatische Registrierung in MDM

Wenn Ihre Organisation über ein [Azure Premium-Abonnement](https://azure.microsoft.com/overview/)verfügt und Azure Active Directory (Azure AD) und eine MDM-Lösung verwendet, die ein Azure AD-Token für die Authentifizierung akzeptiert (derzeit nur in Microsoft Intune und AirWatch unterstützt), kann Ihr IT-Administrator Azure AD so konfigurieren, dass die MDM-Registrierung nach der Anmeldung des Benutzers mit seinem Azure AD-Konto automatisch zulässig ist. [Erfahren Sie, wie Sie die Azure AD-Registrierung konfigurieren.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Wenn die automatische Registrierung aktiviert ist, ist keine zusätzliche manuelle Registrierung erforderlich. Wenn der Benutzer sich mit einem Azure AD-Konto anmeldet, wird das Gerät nach der ersten Ausführung in MDM registriert.

Wenn ein Gerät in Azure AD ist, kann sich dies darauf auswirken, wer als [Gerätebesitzer angesehen wird.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Registrierung von HoloLens intune

Je nach Registrierungsmethode ist die Registrierung Ihres Geräts möglicherweise nicht verfügbar.

Wenn Ihr Gerät mit einem Konto Azure AD Autopilot registriert wurde, kann die Registrierung bei Intune nicht entfernt werden. Wenn Sie die HoloLens von Azure AD oder einem anderen Mandanten als dem Azure AD-Mandanten wieder verwenden möchten, müssen Sie das Gerät [zurücksetzen/neu](hololens-recovery.md#reset-the-device) zurücksetzen.

Wenn Ihr Gerät über ein MSA-Konto registriert wurde, das ein Arbeitskonto hinzugefügt hat, oder über ein lokales Konto, das nur für die Geräteverwaltung registriert wurde, können Sie die Registrierung des Geräts wieder aufknen. Öffnen Sie die Startmenü, und wählen Sie dann **Einstellungen App** Access Work  ->  **or School**  ->  *YourAccount*  ->  **Disconnect (IhrKonto trennen)** aus.

## <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Stellen Sie sicher, dass die MDM-Registrierung nicht für Windows blockiert wird.

Damit die Registrierung erfolgreich ist, müssen Sie sicherstellen, dass Ihre HoloLens registrieren können. Da HoloLens gerät als Windows gilt, müssen keine Registrierungseinschränkungen gelten, die Ihre Bereitstellung blockieren könnten. [Überprüfen Sie diese Liste der Einschränkungen,](/mem/intune/enrollment/enrollment-restrictions-set) und stellen Sie sicher, dass Sie Ihre Geräte registrieren können.