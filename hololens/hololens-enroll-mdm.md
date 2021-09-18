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
ms.openlocfilehash: b6206f7121d1ba78908d96f71c5c809ec97b06d5
ms.sourcegitcommit: 6c8406bbcc79c1f624736cc68e1aaeab70436902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2021
ms.locfileid: "127904343"
---
# <a name="enroll-hololens-in-mdm"></a>Registrieren von HoloLens in MDM

Sie können mehrere Microsoft HoloLens Geräte gleichzeitig mithilfe von Lösungen wie [Microsoft Intune](/intune/windows-holographic-for-business)verwalten. Sie können Einstellungen verwalten, zu installierende Apps auswählen und Sicherheitskonfigurationen festlegen, die auf die Anforderungen Ihrer Organisation zugeschnitten sind. Weitere Informationen finden Sie unter Verwalten von Geräten, die [Windows Holographic mit Microsoft Intune ausgeführt](/intune/windows-holographic-for-business)werden, den [Konfigurationsdienstanbietern (Configuration Service Providers, CSPs), die in Windows Holographic unterstützt werden,](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)und den [richtlinien,](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)die von Windows Holographic for Business unterstützt werden.

> [!NOTE]
> Die Verwaltung mobiler Geräte (Mobile Device Management, MDM), einschließlich der VPN-, BitLocker- und Kioskmodusfeatures, ist nur verfügbar, wenn Sie [ein Upgrade auf Windows Holographic for Business](hololens1-upgrade-enterprise.md)durchführen.

## <a name="requirements"></a>Anforderungen

 Ihre Organisation muss Mobile Geräteverwaltung (MDM) eingerichtet haben, um HoloLens Geräte verwalten zu können. Ihr MDM-Anbieter kann Microsoft Intune oder ein Drittanbieter sein, der die Microsoft-MDM-APIs verwendet.

## <a name="different-ways-to-enroll"></a>Verschiedene Möglichkeiten zum Registrieren

Je nach Art der [Identität,](hololens-identity.md) die entweder während der OOBE-Anmeldung oder nach der Anmeldung ausgewählt wurde, gibt es verschiedene Registrierungsmethoden.

- Wenn Identität Azure AD ist, klicken Sie entweder während der OOBE oder Einstellungen Schaltfläche Auf **Die**  ->  **App-Verbinden**  ->   zugreifen.
    - Für Azure AD erfolgt die [automatische MDM-Registrierung](hololens-enroll-mdm.md#auto-enrollment-in-mdm) nur, wenn Azure AD mit Registrierungs-URLs konfiguriert wurde.

- Wenn identity Azure AD ist und das Gerät beim Intune-MDM-Server mit einem bestimmten Konfigurationsprofil vorab registriert wurde, werden azure AD-Join und die [automatische MDM-Registrierung](hololens-enroll-mdm.md#auto-enrollment-in-mdm) während der OoBE durchgeführt.
    - Wird auch als [Autopilot-Flow](hololens2-autopilot.md) bezeichnet, der in Builds ab [19041.1103](hololens-release-notes.md#windows-holographic-version-2004)verfügbar ist.


- Wenn Identity MSA ist, verwenden **Sie Einstellungen** Schaltfläche  ->  **"App Access Work or School**  ->  **Verbinden".**
    - Wird auch als AWA-Flow (Add Work Account) bezeichnet.
- Wenn Identität lokaler Benutzer ist, verwenden **Sie Einstellungen** Link App Access Work  ->  **or School** Enroll only in device management  ->  **(Nur bei geräteverwaltung registrieren).**
    - Wird auch als reiner MDM-Registrierungsflow bezeichnet.

Sobald das Gerät bei Ihrem MDM-Server registriert ist, gibt die Einstellungen-App jetzt an, dass das Gerät bei der Geräteverwaltung registriert ist.

## <a name="auto-enrollment-in-mdm"></a>Automatische Registrierung in MDM

Wenn Ihre Organisation über ein [Azure Premium-Abonnement](https://azure.microsoft.com/overview/)verfügt und Azure Active Directory (Azure AD) und eine MDM-Lösung verwendet, die ein Azure AD Token für die Authentifizierung akzeptiert (derzeit nur in Microsoft Intune und AirWatch unterstützt), kann Ihr IT-Administrator Azure AD so konfigurieren, dass die MDM-Registrierung automatisch zugelassen wird, nachdem sich der Benutzer mit dem Azure AD Konto anmeldet. [Erfahren Sie, wie Sie die Azure AD-Registrierung konfigurieren.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Wenn die automatische Registrierung aktiviert ist, ist keine zusätzliche manuelle Registrierung erforderlich. Wenn der Benutzer sich mit einem Azure AD-Konto anmeldet, wird das Gerät nach der ersten Ausführung in MDM registriert.

Wenn ein Gerät Azure AD Eingebunden ist, kann sich dies darauf auswirken, wer den [Gerätebesitzer](security-adminless-os.md#device-owner)betrachtet hat.

## <a name="unenroll-hololens-from-intune"></a>Aufheben der Registrierung HoloLens bei Intune

Abhängig von der Registrierungsmethode ist die Registrierung Ihres Geräts möglicherweise nicht verfügbar.

Wenn Ihr Gerät mit einem Azure AD-Konto oder Autopilot registriert wurde, kann die Registrierung bei Intune nicht aufgehoben werden. Wenn Sie HoloLens aus Azure AD aufheben oder einem anderen Mandanten als Azure AD Mandanten wieder gliedern möchten, müssen Sie das Gerät [zurücksetzen/einen neuen Schrägstrich](hololens-recovery.md#reset-the-device) setzen.

Wenn Ihr Gerät über ein MSA-Konto registriert wurde, das ein Arbeitskonto hinzugefügt hat, oder über ein lokales Konto, das nur für die Geräteverwaltung registriert wurde, können Sie die Registrierung des Geräts aufheben. Öffnen Sie die Startmenü, und wählen Sie dann **Einstellungen** Schaltfläche App  ->  **Access Work or School**  ->  *YourAccount*  ->  **Disconnect** aus.

## <a name="enrollment-troubleshooting"></a>Problembehandlung bei der Registrierung

### <a name="ensure-valid-license-is-assigned-to-the-user"></a>Sicherstellen, dass dem Benutzer eine gültige Lizenz zugewiesen ist

Weitere Informationen finden Sie unter Troubleshoot Windows device enrollment problems in Microsoft Intune specifically following sections (Behandeln von Problemen bei der [Geräteregistrierung in Microsoft Intune](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors) folgenden Abschnitten), z. B. Überprüfen von [Gerätetypeinschränkungen](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#check-device-type-restrictions) und [Zuweisen einer gültigen Lizenz zum Benutzer.](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#assign-a-valid-license-to-the-user)

### <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Stellen Sie sicher, dass die MDM-Registrierung für Windows Geräte nicht blockiert wird.

Damit die Registrierung erfolgreich ist, müssen Sie sicherstellen, dass ihre HoloLens Geräte registriert werden können. Da HoloLens als Windows-Gerät gilt, dürfen keine Registrierungseinschränkungen gelten, die Ihre Bereitstellung blockieren könnten. [Überprüfen Sie diese Liste mit Einschränkungen](/mem/intune/enrollment/enrollment-restrictions-set), und stellen Sie sicher, dass Sie Ihre Geräte registrieren können.