---
title: Registrieren von HoloLens in MDM
description: Erfahren Sie, wie Sie HoloLens für die Verwaltung mobiler Geräte (Mobile Device Management, MDM) registrieren, um die Verwaltung mehrerer Geräte zu vereinfachen.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/15/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f466abe45a1a9ad676f8dd6a94244473c084be7
ms.sourcegitcommit: 38b5e4d92da6fc5d6a6a2ef875644d6db2cce822
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2021
ms.locfileid: "130202878"
---
# <a name="enroll-hololens-in-mdm"></a>Registrieren von HoloLens in MDM

Sie können mehrere Microsoft HoloLens gleichzeitig mit lösungen wie [Microsoft Intune.](/intune/windows-holographic-for-business) Sie können Einstellungen verwalten, zu installierende Apps auswählen und Sicherheitskonfigurationen festlegen, die auf die Anforderungen Ihrer Organisation zugeschnitten sind. Weitere Informationen finden Sie unter Verwalten von [Windows Holographic mit Microsoft Intune](/intune/windows-holographic-for-business), den [konfigurationsdienstanbietern (CONFIGURATION Service Providers, CSPs),](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)die in Windows Holographic unterstützt werden, und den von [Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Die Verwaltung mobiler Geräte (Mobile Device Management, MDM), einschließlich der Vpn-, BitLocker- und Kioskmodusfunktionen, ist nur verfügbar, wenn Sie ein Upgrade auf [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

## <a name="requirements"></a>Anforderungen

 Ihre Organisation muss Mobile Geräteverwaltung (MDM) eingerichtet haben, um ihre HoloLens verwalten zu können. Ihr MDM-Anbieter kann Microsoft Intune oder ein Drittanbieter sein, der die Microsoft-MDM-APIs verwendet.

## <a name="different-ways-to-enroll"></a>Verschiedene Möglichkeiten zum Registrieren

Abhängig vom Typ der Identität, die [sie](hololens-identity.md) entweder während der OOBE oder nach der Anmeldung ausgewählt haben, gibt es verschiedene Registrierungsmethoden.

- Wenn Die Identität Azure AD ist, klicken Sie entweder während der OOBE oder Einstellungen **app** access work or school Verbinden button (App Access-Arbeits-,  ->    ->  **Schul- oder Verbinden** klicken.
    - Für Azure AD erfolgt [die automatische MDM-Registrierung](hololens-enroll-mdm.md#auto-enrollment-in-mdm) nur, wenn Azure AD mit Registrierungs-URLs konfiguriert wurde.

- Wenn die Identität Azure AD und das Gerät beim Intune-MDM-Server vorab registriert wurde, dem ein bestimmtes Konfigurationsprofil zugewiesen ist, erfolgen Azure AD-Join und die automatische [MDM-Registrierung](hololens-enroll-mdm.md#auto-enrollment-in-mdm) während der OOBE.
    - Wird auch [als Autopilot-Flow](hololens2-autopilot.md) bezeichnet: Verfügbar in [Builds ab 19041.1103.](hololens-release-notes.md#windows-holographic-version-2004)


- Wenn Identität MSA ist, verwenden Sie Einstellungen **App** Access Work- oder  ->  **School Verbinden Schaltfläche.**  ->  
    - Wird auch als AWA-Flow (Add Work Account) bezeichnet.
- Wenn Identität lokaler Benutzer ist, verwenden Sie Einstellungen **Link App** Access Work or School Enroll only in device management (Nur bei  ->    ->  **Geräteverwaltung registrieren).**
    - Wird auch als reiner MDM-Registrierungsablauf bezeichnet.

Nachdem das Gerät bei Ihrem MDM-Server registriert wurde, gibt die Einstellungen-App an, dass das Gerät für die Geräteverwaltung registriert ist.

## <a name="auto-enrollment-in-mdm"></a>Automatische Registrierung in MDM

Wenn Ihre Organisation über ein [Azure Premium-Abonnement](https://azure.microsoft.com/overview/)verfügt, verwendet Azure Active Directory (Azure AD) und eine MDM-Lösung, die ein Azure AD-Token für die Authentifizierung akzeptiert (derzeit nur in Microsoft Intune und AirWatch unterstützt), kann Ihr IT-Administrator konfigurieren. Azure AD, die MDM-Registrierung automatisch zu ermöglichen, nachdem sich der Benutzer mit seinem Azure AD anmeldet. [Ausführliche Hintergrundinformationen finden Sie unter Konfigurieren Azure AD Registrierung](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) und Azure Active [Directory-Integration mit MDM.](/windows/client-management/mdm/azure-active-directory-integration-with-mdm)

Wenn die automatische Registrierung aktiviert ist, ist keine zusätzliche manuelle Registrierung erforderlich. Wenn der Benutzer sich mit einem Azure AD-Konto anmeldet, wird das Gerät nach der ersten Ausführung in MDM registriert.

Wenn ein Gerät in Azure AD ist, kann sich dies darauf auswirken, wer als [Gerätebesitzer angesehen wird.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Registrierung von HoloLens intune

Je nach Registrierungsmethode ist die Registrierung Ihres Geräts möglicherweise nicht verfügbar.

Wenn Ihr Gerät mit einem Konto Azure AD Autopilot registriert wurde, kann die Registrierung bei Intune nicht entfernt werden. Wenn Sie die HoloLens von Azure AD oder zu einem anderen als dem Azure AD-Mandanten erneut verwenden möchten, müssen Sie das Gerät [zurücksetzen/neu](hololens-recovery.md#restart-the-device) zurücksetzen.

Wenn Ihr Gerät über ein MSA-Konto registriert wurde, das ein Arbeitskonto hinzugefügt hat, oder über ein lokales Konto, das nur für die Geräteverwaltung registriert wurde, können Sie die Registrierung des Geräts wieder auf den Weg geben. Öffnen Sie die Startmenü, und wählen Sie dann **Einstellungen App** Access Work  ->  **or School**  ->  *YourAccount*  ->  **Disconnect (IhrKonto trennen)** aus.

## <a name="enrollment-troubleshooting"></a>Problembehandlung bei der Registrierung

### <a name="ensure-device-is-successfully-connected-to-internet-before-attempting-enrollment-post-oobe"></a>Stellen Sie sicher, dass das Gerät erfolgreich mit dem Internet verbunden ist, bevor Sie versuchen, sich nach oobe zu registrieren.

Sobald sich der Benutzer angemeldet hat, stellen Sie sicher, dass eine Internetverbindung besteht, indem Sie zu einer beliebigen Website mit Internetanbindung auf dem Gerät navigieren.

### <a name="ensure-that-azure-active-directory-aad-join-is-not-disabled-in-your-aad-tenant"></a>Stellen Sie sicher, Azure Active Directory (AAD) join nicht in Ihrem AAD ist.

Informationen zu [den verfügbaren](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) Optionen finden Sie unter Konfigurieren Ihrer Geräteeinstellungen in Azure-Portal.

### <a name="ensure-valid-license-is-assigned-to-the-user"></a>Stellen Sie sicher, dass dem Benutzer eine gültige Lizenz zugewiesen ist.

Weitere Informationen finden Windows Behandeln von Problemen bei der Geräteregistrierung [in](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors) Microsoft Intune den folgenden Abschnitten, z. [B.](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#check-device-type-restrictions) Überprüfen von Gerätetypeinschränkungen und Zuweisen einer gültigen Lizenz [zum Benutzer.](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#assign-a-valid-license-to-the-user)

### <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Stellen Sie sicher, dass die MDM-Registrierung nicht für Windows blockiert wird.

Damit die Registrierung erfolgreich ist, müssen Sie sicherstellen, dass Ihre HoloLens registrieren können. Da HoloLens als Windows-Gerät gilt, dürfen keine Registrierungseinschränkungen gelten, die Ihre Bereitstellung blockieren könnten. [Überprüfen Sie diese Liste mit Einschränkungen](/mem/intune/enrollment/enrollment-restrictions-set), und stellen Sie sicher, dass Sie Ihre Geräte registrieren können.
