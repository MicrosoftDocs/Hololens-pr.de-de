---
title: HoloLens 2-Datenschutz
description: Dokumentation zum Datenschutz
keywords: HoloLens, DSGVO, Datenschutz, PERSONENBEZOGENE Informationen, Datenschutz
author: golish
ms.author: marcingo
ms.reviewer: sekerawa, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 74f74645a3fc1282f48cb7ce0f6f722979c91b04
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032621"
---
# <a name="hololens-2-privacy-and-data-protection"></a>HoloLens 2-Datenschutz

Eines der Kernelemente der DSGVO ist "Datenschutz durch Entwurf". Dieses Konzept gilt insbesondere für mobile Geräte wie die HoloLens 2 aufgrund ihrer Portabilität, unbegrenzter Internetverbindung und offener Kommunikationskanäle. Aus diesem Grund wurde die [Sicherheit](/hololens/security-architecture) der HoloLens 2 neu gestaltet, um erweiterte, innovative Sicherheit und Datenschutz zu bieten, end-to-end und den Microsoft-Ansatz für [Datenschutz und DSGVO-Vorschriften](https://privacy.microsoft.com/)zu integrieren.

 >[!NOTE]
> Dieses Dokument gilt nicht für HoloLens (1. Generation).

## <a name="privacy-overview"></a>Übersicht über den Datenschutz

HoloLens 2 ist ein eigenständiger Windows Computer mit Windows Holographic, auf dem Apps und Lösungen in einer immersiven Mixed Reality-Umgebung ausgeführt werden. Es kann als sicheres Offlinegerät verwendet oder als [verwaltetes Gerät](/mem/intune/fundamentals/windows-holographic-for-business) in Ihrer Organisation bereitgestellt werden. Unter den folgenden Links erfahren Sie, wie die HoloLens 2 und Microsoft Ihre Daten verwenden und schützen:

1. [Microsoft-Datenschutzerklärung – HoloLens](https://privacy.microsoft.com/privacystatement) – erweitern Sie den Abschnitt **Enterprise und Entwickler** im linken Navigationsmenü, und wählen Sie Enterprise und **Entwicklersoftware und -appliances** aus. Wechseln Sie zum Abschnitt **HoloLens.**
2. [Windows 10 und Ihre Onlinedienste](https://privacy.microsoft.com/windows10privacy)
3. [Leitfaden zur Datenschutzkonformität Windows 10 &](/windows/privacy/windows-10-and-privacy-compliance)
4. [Datenschutz und personenbezogene Daten in Intune](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Netzwerksicherheit
Gemäß den HoloLens 2 [Common Deployment Scenarios (Allgemeine Bereitstellungsszenarien)](/hololens/common-scenarios)werden Ihre Daten durch die erstklassige Compliance von [Azure](/azure/compliance/) sowie durch die Integration gesetzlicher/gesetzlicher Standards geschützt. Wenn Sie noch nicht mit Azure AD und Dynamics 365 Remote Assist sind, verweisen Sie auf die Checkliste zur Bereitschaft der [Azure- und Dynamics 365-Verantwortlichkeit für die DSGVO.](/compliance/regulatory/gdpr-arc-azure-dynamics)

Darüber hinaus bietet Windows Defender Firewall wichtige Funktionen zum Sichern der Gerätekonnektivität. Bei HoloLens 2 ist die Firewall immer aktiviert, und es gibt keine Möglichkeit, sie programmgesteuert oder über die Benutzeroberfläche zu deaktivieren. Wenn die HoloLens 2 als verwaltetes Gerät mit [Intune](/mem/intune/protect/device-compliance-get-started)bereitgestellt wird, stehen mit der Integration für [Endpoint mit Microsoft Intune](/mem/intune/protect/advanced-threat-protection) als Mobile Threat Defense-Lösung mehr Kompatibilitätsfunktionen zur Verfügung.

Erfahren Sie mehr über die HoloLens 2 [Sicherheit und Architektur.](/hololens/security-architecture)

## <a name="os-security"></a>Betriebssystemsicherheit
Updates werden automatisch (standardmäßig) durchgeführt, sodass Ihre HoloLens 2 immer mit der neuesten Version von Windows Holographic und allen installierten Apps auf dem neuesten Stand ist. Weitere Informationen zur sicheren Gestaltung unseres Betriebssystems finden Sie hier:

1. [Statustrennung und -isolation](/hololens/security-state-separation-isolation)
1. [Betriebssystem ohne Administratorrechte](/hololens/security-adminless-os)
1. [Begrenzen der Verwendung von Kennwörtern](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Physische Sicherheit
HoloLens 2 verfügt über Flashspeicher, der durch die [BitLocker-Verschlüsselung](/hololens/security-encryption-data-protection)geschützt ist. Ihr Gerät und seine lokalen Daten können mit [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) offline flasht oder remote über MDM zurückgesetzt werden, wenn es als verwaltetes Gerät bereitgestellt wurde.

## <a name="data-protection"></a>Datenschutz
Windows Updates werden automatisch (standardmäßig) ausgeführt, und die [Azure-Integration](/hololens/security-encryption-data-protection#Azure-integration) schützt Daten, die zwischen sich selbst und der Cloud reisen.

Bei der Bereitstellung von HoloLens 2 für externe Clients stellt [Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide) sicher, dass Ihre vertraulichen Unternehmensdaten und Ressourcen getrennt und sicher sind.

Die Freigabe von Diagnosedaten für Microsoft kann manuell von MDM oder vom Benutzer während der OoBE konfiguriert werden. Es gibt zwei Optionen: Optionale Diagnosedaten und Erforderliche Diagnosedaten. Wenn Ihre ursprüngliche Diagnoseeinstellung zu einem späteren Zeitpunkt zu Problembehandlungszwecken geändert werden muss, kann sie vom Benutzer in **Einstellungen -> Privacy -> Diagnostics & Feedback** oder vom IT-Administrator (MDM) geändert werden, wenn ein verwaltetes Gerät ist. Weitere Informationen zu [Diagnose, Feedback und Datenschutz](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)finden Sie in Windows 10 .

> [!Important]
> Gerätediagnoseprotokolle enthalten personenbezogene Informationen (PiI), z. B. darüber, welche Prozesse oder Anwendungen der Benutzer bei typischen Vorgängen startet. Wenn mehrere Benutzer ein HoloLens Gerät freigeben (z. B. wenn sich Benutzer mit unterschiedlichen Microsoft Azure Active Directory -Konten (Azure AD) beim gleichen Gerät anmelden), enthalten die Diagnoseprotokolle möglicherweise PII-Informationen, die für mehrere Benutzer gelten.

Es gibt [mehrere Sammlungsmethoden und Datenaufbewahrungsrichtlinien](/hololens/hololens-diagnostic-logs) zum Sammeln von Diagnosedaten aus der HoloLens 2.  Weitere Informationen dazu, wie Microsoft Diagnosedaten sammelt und verwendet, finden Sie unter [Microsoft Privacy Statement – Diagnostics](https://privacy.microsoft.com/privacystatement) – expand **Windows** im linken Navigationsmenü, und wählen Sie **Diagnose** aus. Wechseln Sie zum Abschnitt **Diagnose.**
