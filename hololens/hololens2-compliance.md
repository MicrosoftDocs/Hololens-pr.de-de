---
title: HoloLens 2 Compliance und DSGVO
description: Dokumentation zur DSGVO
keywords: HoloLens, DSGVO, Datenschutz, PII
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
ms.openlocfilehash: 8b795513d83c9d23f70b8dd8365e703d1fc43a51
ms.sourcegitcommit: 76a99370ab841c06e533cc2f4a0c78c1fb7eac70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "11324872"
---
# Datenschutzbestimmungen für HoloLens 2

Eines der Kernelemente der DSGVO ist "Datenschutz nach Entwurf". Dieses Konzept gilt insbesondere für mobile Geräte wie holoLens 2 aufgrund ihrer Portabilität, unbegrenzten Internetverbindungen und offenen Kommunikationskanälen. Aus diesem Grund wurde die Sicherheit [](https://docs.microsoft.com/hololens/security-architecture) von HoloLens 2 umgestaltet, um einen erweiterten, innovative Sicherheit und Datenschutz von Ende zu Ende zu bieten, der sowohl den Ansatz von Microsoft für datenschutz- als auch die DSGVO-Bestimmungen [einbehört.](https://privacy.microsoft.com/)

 >[!NOTE]
> Dieses Dokument gilt nicht für HoloLens (1. Generation).

## Übersicht über den Datenschutz

HoloLens 2 ist ein eigenständiger Windows-Computer mit Windows Holographic, auf dem Apps und Lösungen in einer immersiven Mixed -Reality-Umgebung ausgeführt werden. Es kann als sicheres Offlinegerät verwendet oder als verwaltetes [Gerät in](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) Ihrer Organisation bereitgestellt werden. Unter den folgenden Links erfahren Sie, wie HoloLens 2 und Microsoft Ihre Daten verwendet und schützt:
1. [Microsoft Privacy Statement – HoloLens](https://privacy.microsoft.com/privacystatement) – erweitern Sie den Abschnitt **"Unternehmen"** und "Entwickler" im linken Navigationsmenü, und wählen Sie Enterprise- und **Entwicklersoftware und -appliances aus.** Wechseln Sie zum **Abschnitt "HoloLens".**
2.  [Windows 10 und Ihre Onlinedienste](https://privacy.microsoft.com/windows10privacy)
3.  [Leitfaden zu Windows 10 und Datenschutzrichtlinien](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Datenschutz und personenbezogene Daten in Intune](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## Netzwerksicherheit
Im Anschluss an die allgemeinen Bereitstellungsszenarien von HoloLens [2](https://docs.microsoft.com/hololens/common-scenarios)werden Ihre Daten durch die erstklassige Compliance von [Azure](https://docs.microsoft.com/azure/compliance/) sowie durch die Integration rechtlicher/behördlicher Standards geschützt. If you are new to Azure AD and Dynamics 365 Remote Assist, reference the [Azure and Dynamics 365 accountability readiness checklist for the GDPR](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics).

Darüber hinaus bietet Windows Defender Firewall wichtige Funktionen zum Sichern der Gerätekonnektivität. Bei HoloLens2 ist die Firewall immer aktiviert, und es gibt keine Möglichkeit, Sie programmgesteuert oder über die Benutzeroberfläche zu deaktivieren. Wenn HoloLens 2 als verwaltetes Gerät mit [Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)bereitgestellt wird, steht mit der Integration von Endpoint in [Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) als Mobile Threat Defense-Lösung mehr Compliancefunktionen zur Verfügung. 

Erfahren Sie mehr über die Sicherheit und Architektur [von](https://docs.microsoft.com/hololens/security-architecture)HoloLens 2.

## Betriebssystemsicherheit
Updates werden automatisch (standardmäßig) durchgeführt, damit HoloLens 2 immer mit der neuesten Version von Windows Holographic und allen installierten Apps auf dem neuesten Stand ist. Weitere Informationen zum sicheren Design unseres Betriebssystems finden Sie unter den folgenden Themen:
1. [Statustrennung und -isolation](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [Betriebssystem ohne Administrator](https://docs.microsoft.com/hololens/security-adminless-os)
1. [Begrenzen der Verwendung von Kennwörtern](https://docs.microsoft.com/hololens/security-limiting-password-use)

## Physische Sicherheit
HoloLens 2 verfügt über Flashspeicher, der durch die [BitLocker-Verschlüsselung geschützt ist.](https://docs.microsoft.com/hololens/security-encryption-data-protection) Ihr Gerät und seine lokalen Daten können offline mit [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) geblitzt oder remote über MDM gelöscht werden, wenn es als verwaltetes Gerät bereitgestellt wurde.

## Datenschutz
Windows Updates werden automatisch (standardmäßig) ausgeführt, und die [Azure-Integration](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) schützt Daten, die zwischen sich selbst und der Cloud liegen. 

Bei der Bereitstellung von HoloLens 2 für externe Clients stellt [Dynamics 365 Remote Assist](https://docs.microsoft.com/hololens/hololens2-deployment-guide) sicher, dass Ihre vertraulichen Unternehmensdaten und -ressourcen getrennt und sicher sind. 

Die Freigabe von Diagnosedaten an Microsoft kann manuell von MDM oder vom Benutzer während der OOBE konfiguriert werden. Es gibt zwei Optionen: optionale Diagnosedaten und erforderliche Diagnosedaten. Wenn Ihre ursprüngliche Diagnoseeinstellung zu einem späteren Zeitpunkt zur Problembehandlung geändert werden muss, kann sie vom Benutzer unter "Einstellungen -> Datenschutz **-> Diagnose & Feedback"** oder vom IT-Administrator (MDM) geändert werden, wenn es sich um ein verwaltetes Gerät handelt. Weitere Informationen zu Diagnose, Feedback und Datenschutz finden Sie [unter Windows 10.](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)

> [!Important]
> Gerätediagnoseprotokolle enthalten personenbezogene Informationen (PII), z. B. dazu, welche Prozesse oder Anwendungen der Benutzer während eines typischen Betriebs startet. Wenn mehrere Benutzer ein HoloLens-Gerät freigeben (z. B. benutzer melden sich mit unterschiedlichen Microsoft Azure Active Directory (Azure AD)-Konten am selben Gerät an), enthalten die Diagnoseprotokolle möglicherweise PII-Informationen, die für mehrere Benutzer gelten.

 

Es gibt [mehrere Sammlungsmethoden und Datenaufbewahrungsrichtlinien](https://docs.microsoft.com/hololens/hololens-diagnostic-logs) zum Sammeln von Diagnosedaten aus HoloLens 2.  Weitere Informationen dazu, wie Microsoft Diagnosedaten sammelt und verwendet, finden Sie unter [Microsoft Privacy Statement - Diagnostics](https://privacy.microsoft.com/privacystatement) - expand **Windows** in the left navigation menu and select **Diagnostics**. Wechseln Sie zum Abschnitt **"Diagnose".**
