---
title: HoloLens 2 Compliance und DSGVO
description: DSGVO-Dokumentation
keywords: HoloLens, DSGVO, Datenschutz, PERSONENBEZOGENE Informationen
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: skerewala, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 684a97a4fcdc3aaf830f164c54fb3079e296c78c
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637114"
---
# <a name="hololens-2-privacy-statement"></a>Datenschutzbestimmungen für HoloLens 2

Eines der Kernelemente der DSGVO ist "Datenschutz durch Entwurf". Dieses Konzept gilt insbesondere für mobile Geräte wie die HoloLens 2 aufgrund ihrer Portabilität, unbegrenzter Internetverbindung und offener Kommunikationskanäle. Aus diesem Grund wurde die [Sicherheit](/hololens/security-architecture) der HoloLens 2 umgestaltet, um erweiterte, innovative Sicherheit und Datenschutz zu bieten, end-to-end, wobei sowohl der Microsoft-Ansatz für Datenschutz als auch [die DSGVO-Vorschriften](https://privacy.microsoft.com/)integriert wurden.

 >[!NOTE]
> Dieses Dokument gilt nicht für HoloLens (1. Generation).

## <a name="privacy-overview"></a>Übersicht über den Datenschutz

HoloLens 2 ist ein eigenständiger Windows Computer mit Windows Holographic, der Apps und Lösungen in einer immersiven Mixed Reality-Umgebung ausführt. Es kann als sicheres Offlinegerät verwendet oder als [verwaltetes Gerät](/mem/intune/fundamentals/windows-holographic-for-business) in Ihrer Organisation bereitgestellt werden. Unter den folgenden Links erfahren Sie, wie die HoloLens 2 und Microsoft Ihre Daten verwenden und schützen:

1. [Microsoft-Datenschutzerklärung – HoloLens](https://privacy.microsoft.com/privacystatement) – erweitern Sie den Abschnitt **Enterprise und Entwickler** im linken Navigationsmenü, und wählen Sie Enterprise und **Entwicklersoftware und -appliances aus.** Wechseln Sie zum Abschnitt **HoloLens.**
2. [Windows 10 und Ihre Onlinedienste](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & Handbuch zur Datenschutzkonformität](/windows/privacy/windows-10-and-privacy-compliance)
4. [Datenschutz und personenbezogene Daten in Intune](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Netzwerksicherheit
Gemäß den HoloLens 2 [Common Deployment Scenarios (Allgemeine Bereitstellungsszenarien)](/hololens/common-scenarios)werden Ihre Daten durch die erstklassige Compliance von [Azure](/azure/compliance/) sowie durch die Integration gesetzlicher/gesetzlicher Standards geschützt. Wenn Sie noch nicht mit Azure AD und Dynamics 365 Remote Assist sind, verweisen Sie auf die Checkliste zur Bereitschaft der [Azure- und Dynamics 365-Verantwortlichkeit für die DSGVO.](/compliance/regulatory/gdpr-arc-azure-dynamics)

Darüber hinaus bietet Windows Defender Firewall wichtige Funktionen zum Sichern der Gerätekonnektivität. Mit HoloLens 2 ist die Firewall immer aktiviert, und es gibt keine Möglichkeiten, sie programmgesteuert oder über die Benutzeroberfläche zu deaktivieren. Wenn die HoloLens 2 mit [Intune](/mem/intune/protect/device-compliance-get-started)als verwaltetes Gerät bereitgestellt wird, stehen mehr Kompatibilitätsfunktionen mit der Integration für [Endpoint mit Microsoft Intune](/mem/intune/protect/advanced-threat-protection) als Mobile Threat Defense-Lösung zur Verfügung.

Erfahren Sie mehr über die HoloLens 2 [Sicherheit und Architektur.](/hololens/security-architecture)

## <a name="os-security"></a>Betriebssystemsicherheit
Updates werden automatisch (standardmäßig) durchgeführt, sodass Ihre HoloLens 2 immer mit dem neuesten Release von Windows Holographic und allen installierten Apps auf dem neuesten Stand ist. Weitere Informationen zur sicheren Gestaltung unseres Betriebssystems finden Sie hier:

1. [Statustrennung und -isolation](/hololens/security-state-separation-isolation)
1. [Betriebssystem ohne Administratorrechte](/hololens/security-adminless-os)
1. [Begrenzen der Verwendung von Kennwörtern](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Physische Sicherheit
HoloLens 2 verfügt über Flashspeicher, der durch die [BitLocker-Verschlüsselung](/hololens/security-encryption-data-protection)geschützt ist. Ihr Gerät und seine lokalen Daten können mit [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) offline flasht oder remote über MDM zurückgesetzt werden, wenn es als verwaltetes Gerät bereitgestellt wurde.

## <a name="data-protection"></a>Schutz von Daten
Windows Updates werden automatisch (standardmäßig) ausgeführt, und die [Azure-Integration](/hololens/security-encryption-data-protection#Azure-integration) schützt Daten, die zwischen sich selbst und der Cloud reisen.

Bei der Bereitstellung von HoloLens 2 für externe Clients stellt [Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide) sicher, dass Ihre vertraulichen Unternehmensdaten und Ressourcen getrennt und sicher sind.

Die Freigabe von Diagnosedaten für Microsoft kann manuell von MDM oder vom Benutzer während der OoBE konfiguriert werden. Es gibt zwei Optionen: Optionale Diagnosedaten und Erforderliche Diagnosedaten. Wenn Ihre ursprüngliche Diagnoseeinstellung zu einem späteren Zeitpunkt zur Problembehandlung geändert werden muss, kann sie vom Benutzer in **Einstellungen -> Privacy -> Diagnostics & Feedback** oder vom IT-Administrator (MDM) geändert werden, wenn ein verwaltetes Gerät ist. Weitere Informationen zu [Diagnose, Feedback und Datenschutz finden Sie in Windows 10](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319).

> [!Important]
> Gerätediagnoseprotokolle enthalten personenbezogene Informationen (PiI), z. B. darüber, welche Prozesse oder Anwendungen der Benutzer bei typischen Vorgängen startet. Wenn mehrere Benutzer ein HoloLens Gerät freigeben (z. B. wenn sich Benutzer mit unterschiedlichen Microsoft Azure Active Directory (Azure AD)-Konten beim gleichen Gerät anmelden), enthalten die Diagnoseprotokolle möglicherweise PII-Informationen, die für mehrere Benutzer gelten.

Es gibt [mehrere Sammlungsmethoden und Datenaufbewahrungsrichtlinien](/hololens/hololens-diagnostic-logs) zum Sammeln von Diagnosedaten aus der HoloLens 2.  Weitere Informationen dazu, wie Microsoft Diagnosedaten sammelt und verwendet, finden Sie unter [Microsoft Privacy Statement – Diagnostics](https://privacy.microsoft.com/privacystatement) – expand **Windows** im linken Navigationsmenü, und wählen Sie **Diagnose** aus. Wechseln Sie zum Abschnitt **Diagnose.**
