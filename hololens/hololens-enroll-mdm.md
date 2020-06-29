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
ms.openlocfilehash: 054c4ded7496957671c055e3161a1297de7abc1a
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828096"
---
# Registrieren von HoloLens in MDM

Sie können mehrere Microsoft HoloLens-Geräte gleichzeitig mit Lösungen wie [Microsoft InTune](https://docs.microsoft.com/intune/windows-holographic-for-business)verwalten. Sie können Einstellungen verwalten, zu installierende Apps auswählen und Sicherheitskonfigurationen festlegen, die auf die Anforderungen Ihrer Organisation zugeschnitten sind. Weitere Informationen finden Sie unter [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), und [Konfigurationsdienstanbieter (Configuration Service Providers, CSPs), die in Windows Holographic unterstützt werden](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) sowie [Richtlinien, die von Windows Holographic for Business unterstützt werden](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Die mobile Geräteverwaltung (MDM), einschließlich VPN, BitLocker und Kiosk-Modus-Features ist nur verfügbar, wenn Sie [ein Upgrade auf Windows Holographic for Business durchführen](hololens1-upgrade-enterprise.md).

## Anforderungen

 Für Ihre Organisation muss die Mobile Device Management (MDM) eingerichtet sein, um HoloLens-Geräte verwalten zu können. Ihr MDM-Anbieter kann Microsoft Intune oder ein Drittanbieter sein, der die Microsoft-MDM-APIs verwendet.

## Automatische Registrierung in MDM

Wenn Ihre Organisation Azure Active Directory (Azure AD) und eine MDM-Lösung verwendet, die ein AAD-Token für die Authentifizierung akzeptiert (zurzeit nur in Microsoft Intune und AirWatch unterstützt), kann der IT-Administrator Azure AD so konfigurieren, dass die MDM-Registrierung automatisch zugelassen wird, wenn der Benutzer sich mit seinem Azure AD-Konto angemeldet hat. [Erfahren Sie, wie Sie die Azure AD-Registrierung konfigurieren.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Wenn die automatische Registrierung aktiviert ist, ist keine zusätzliche manuelle Registrierung erforderlich. Wenn der Benutzer sich mit einem Azure AD-Konto anmeldet, wird das Gerät nach der ersten Ausführung in MDM registriert.

## Registrieren über die Einstellungs-App

 Wenn das Gerät während der ersten Ausführung nicht in MDM registriert wird, kann der Benutzer das Gerät mithilfe der Einstellungs-App manuell bei dem MDM-Server der Organisation registrieren.

1. Wechseln Sie zu **Einstellungen** > **Konten** > **Arbeitsplatzzugriff**.
1. Wählen Sie **Für Verwaltungsdienst registrieren**, und geben Sie Ihr Organisationskonto ein. Sie werden zur Anmeldeseite Ihrer Organisation weitergeleitet.
1. Bei erfolgreicher Authentifizierung bei dem MDM-Server wird eine entsprechende Meldung angezeigt.

Ihr Gerät ist jetzt bei Ihrem MDM-Server registriert. Die Einstellungs-App wird jetzt anzeigen, dass das Gerät in der Geräteverwaltung registriert ist.

## Abmelden von HoloLens aus InTune

Sie können HoloLens dezentral von Intune [entfernen](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows). Wenn der Administrator das Gerät mithilfe der MDM-Registrierung entfernt, wird das Gerät aus dem Intune-Dashboard entfernt.
