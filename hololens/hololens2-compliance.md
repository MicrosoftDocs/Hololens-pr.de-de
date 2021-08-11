---
title: HoloLens 2 Compliance und DSGVO
description: DSGVO-Dokumentation
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
ms.openlocfilehash: 3365e69c8408b75a5d4e1177df938f435dec05d9dc181c698d7991159645d15a
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660154"
---
# <a name="hololens-2-privacy-statement"></a>Datenschutzbestimmungen für HoloLens 2

Eines der Kernelemente der DSGVO ist "Datenschutz per Entwurf". Dieses Konzept gilt insbesondere für mobile Geräte wie die HoloLens 2 aufgrund ihrer Portabilität, unbegrenzten Internetverbindungen und offenen Kommunikationskanäle. Die Sicherheit des HoloLens 2 wurde [](/hololens/security-architecture) neu gestaltet, um einen erweiterten, innovativen Schutz der Sicherheit und des Datenschutzes zu bieten. Dies ist eine end-to-End-Lösung, die sowohl den Datenschutzansatz von Microsoft als auch die DSGVO-Vorschriften [enthält.](https://privacy.microsoft.com/)

 >[!NOTE]
> Dieses Dokument gilt nicht für HoloLens (1. Generation).

## <a name="privacy-overview"></a>Datenschutzübersicht

HoloLens 2 ist ein eigenständiger Windows-Computer, auf dem Windows Holographic ausgeführt wird und apps und Lösungen in einer immersiven Mixed Reality-Umgebung ausgeführt werden. Sie kann als sicheres Offlinegerät verwendet oder als verwaltetes Gerät in [Ihrer](/mem/intune/fundamentals/windows-holographic-for-business) Organisation bereitgestellt werden. Unter den folgenden Links erfahren Sie, wie die HoloLens 2 und Microsoft Ihre Daten verwenden und schützen:

1. [Microsoft-Datenschutzerklärung – HoloLens](https://privacy.microsoft.com/privacystatement) : Erweitern Sie den Abschnitt **Enterprise** und Entwickler im linken Navigationsmenü, und wählen Sie Enterprise- und Entwicklersoftware und **-appliances aus.** Wechseln Sie zum **HoloLens** Abschnitt .
2. [Windows 10 und Ihre Onlinedienste](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & Handbuch zur Datenschutzkonformität](/windows/privacy/windows-10-and-privacy-compliance)
4. [Datenschutz und personenbezogene Daten in Intune](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Netzwerksicherheit
Gemäß HoloLens 2 allgemeinen [Bereitstellungsszenarien](/hololens/common-scenarios)werden Ihre Daten durch die erstklassige Compliance von [Azure](/azure/compliance/) sowie durch die Integration gesetzlicher/gesetzlicher Standards geschützt. Wenn Sie noch nicht mit Azure AD und Dynamics 365 Remote Assist sind, finden Sie weitere Informationen in der Checkliste für die Bereitschaft zur Verantwortlichkeit von Azure und [Dynamics 365 für die DSGVO.](/compliance/regulatory/gdpr-arc-azure-dynamics)

Darüber hinaus bietet Windows Defender Firewall wichtige Funktionen zum Sichern der Gerätekonnektivität. Bei HoloLens 2 ist die Firewall immer aktiviert, und es gibt keine Möglichkeit, sie programmgesteuert oder über die Benutzeroberfläche zu deaktivieren. Wenn die HoloLens 2 mit [Intune](/mem/intune/protect/device-compliance-get-started)als verwaltetes Gerät bereitgestellt wird, stehen mit der Integration von [Endpoint with Microsoft Intune](/mem/intune/protect/advanced-threat-protection) als Mobile Threat Defense-Lösung mehr Konformitätsfunktionen zur Verfügung.

Erfahren Sie mehr über HoloLens 2 [Und-Architektur.](/hololens/security-architecture)

## <a name="os-security"></a>Betriebssystemsicherheit
Updates werden automatisch (standardmäßig) durchgeführt, sodass Ihre HoloLens 2 immer auf dem neuesten Stand der neuesten Version von Windows Holographic und allen installierten Apps ist. Weitere Informationen zur sicheren Entwicklung unseres Betriebssystems finden Sie im Folgenden:

1. [Statustrennung und -isolation](/hololens/security-state-separation-isolation)
1. [Betriebssystem ohne Administratorrechte](/hololens/security-adminless-os)
1. [Begrenzen der Verwendung von Kennwörtern](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Physische Sicherheit
HoloLens 2 verfügt über Flashspeicher, der durch [bitLocker-Verschlüsselung geschützt ist.](/hololens/security-encryption-data-protection) Ihr Gerät und die lokalen Daten können offline mit advanced [recovery companion (Advanced Recovery Companion)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) oder remote über MDM zurückgelöscht werden, wenn es als verwaltetes Gerät bereitgestellt wurde.

## <a name="data-protection"></a>Schutz von Daten
Windows Updates werden automatisch (standardmäßig) ausgeführt, und die [Azure-Integration](/hololens/security-encryption-data-protection#Azure-integration) schützt Daten, die zwischen sich selbst und der Cloud unterwegs sind.

Beim Bereitstellen von HoloLens 2 auf externen Clients stellt [Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide) sicher, dass Ihre vertraulichen Unternehmensdaten und -ressourcen getrennt und sicher sind.

Die Freigabe von Diagnosedaten für Microsoft kann manuell von MDM oder vom Benutzer während der OOBE konfiguriert werden. Es gibt zwei Optionen: Optionale Diagnosedaten und Erforderliche Diagnosedaten. Wenn Ihre ursprüngliche Diagnoseeinstellung zu einem späteren Zeitpunkt zu Problembehandlungszwecken geändert werden muss, kann sie vom Benutzer in **Einstellungen -> Privacy -> Diagnostics & Feedback** oder vom IT-Administrator (MDM) geändert werden, wenn ein verwaltetes Gerät ist. Weitere Informationen zu [Diagnose, Feedback und Datenschutz finden](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)Sie in Windows 10 .

> [!Important]
> Gerätediagnoseprotokolle enthalten personenbezogene Informationen (Personally Identifiable Information, PII), z. B. darüber, welche Prozesse oder Anwendungen der Benutzer bei typischen Vorgängen startet. Wenn mehrere Benutzer ein HoloLens-Gerät gemeinsam nutzen (z. B. melden sich Benutzer mit unterschiedlichen Microsoft Azure Active Directory-Konten (Azure AD) bei demselben Gerät an), enthalten die Diagnoseprotokolle möglicherweise PERSONENBEZOGENE-Informationen, die für mehrere Benutzer gelten.

Es gibt [mehrere Sammlungsmethoden und Datenaufbewahrungsrichtlinien](/hololens/hololens-diagnostic-logs) zum Sammeln von Diagnosedaten aus HoloLens 2.  Weitere Informationen dazu, wie Microsoft Diagnosedaten sammelt und verwendet,  finden Sie unter [Microsoft-Datenschutzbestimmungen](https://privacy.microsoft.com/privacystatement) – Diagnose – Erweitern Windows im linken Navigationsmenü, und wählen Sie **Diagnose aus.** Wechseln Sie zum **Abschnitt Diagnose.**
