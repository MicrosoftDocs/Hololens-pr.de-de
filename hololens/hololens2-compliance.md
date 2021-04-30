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
ms.openlocfilehash: 8b795513d83c9d23f70b8dd8365e703d1fc43a51
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309917"
---
# <a name="hololens-2-privacy-statement"></a>HoloLens 2 Datenschutzbestimmungen

Eines der Kernelemente der DSGVO ist "Datenschutz durch Entwurf". Dieses Konzept gilt insbesondere für mobile Geräte wie die HoloLens 2 aufgrund ihrer Portabilität, unbegrenzter Internetverbindung und offener Kommunikationskanäle. Aus diesem Grund wurde die [Sicherheit](https://docs.microsoft.com/hololens/security-architecture) der HoloLens 2 umgestaltet, um erweiterte, innovative Sicherheit und Datenschutz zu bieten, end-to-end und den Microsoft-Ansatz für [Datenschutz und DSGVO-Vorschriften](https://privacy.microsoft.com/)zu integrieren.

 >[!NOTE]
> Dieses Dokument gilt nicht für HoloLens (1. Generation).

## <a name="privacy-overview"></a>Übersicht über den Datenschutz

HoloLens 2 ist ein eigenständiger Windows-Computer mit Windows Holographic, auf dem Apps und Lösungen in einer immersiven Mixed Reality-Umgebung ausgeführt werden. Es kann als sicheres Offlinegerät verwendet oder als [verwaltetes Gerät](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) in Ihrer Organisation bereitgestellt werden. Unter den folgenden Links erfahren Sie, wie die HoloLens 2 und Microsoft Ihre Daten verwenden und schützen:
1. [Microsoft-Datenschutzbestimmungen – HoloLens](https://privacy.microsoft.com/privacystatement) : Erweitern Sie im linken Navigationsmenü den Abschnitt **Enterprise und Developer,** und wählen Sie Software und Appliances für **Unternehmen und Entwickler aus.** Wechseln Sie zum Abschnitt **HoloLens.**
2.  [Windows 10 und Ihre Onlinedienste](https://privacy.microsoft.com/windows10privacy)
3.  [Windows 10 & Handbuch zur Datenschutzkonformität](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Datenschutz und personenbezogene Daten in Intune](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Netzwerksicherheit
Gemäß den HoloLens 2 [Common Deployment Scenarios (Allgemeine Bereitstellungsszenarien)](https://docs.microsoft.com/hololens/common-scenarios)werden Ihre Daten durch die erstklassige Compliance von [Azure](https://docs.microsoft.com/azure/compliance/) sowie durch die Integration gesetzlicher/gesetzlicher Standards geschützt. Wenn Sie noch nicht mit Azure AD und Dynamics 365 Remote Assist sind, verweisen Sie auf die Checkliste zur Bereitschaft der [Azure- und Dynamics 365-Verantwortlichkeit für die DSGVO.](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics)

Darüber hinaus bietet Windows Defender Firewall wichtige Funktionen zum Sichern der Gerätekonnektivität. Mit HoloLens 2 ist die Firewall immer aktiviert, und es gibt keine Möglichkeiten, sie programmgesteuert oder über die Benutzeroberfläche zu deaktivieren. Wenn die HoloLens 2 mit [Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)als verwaltetes Gerät bereitgestellt wird, stehen mit der Integration von [Endpoint with Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) als Mobile Threat Defense-Lösung weitere Konformitätsfunktionen zur Verfügung. 

Erfahren Sie mehr über die HoloLens 2 [Und-Architektur.](https://docs.microsoft.com/hololens/security-architecture)

## <a name="os-security"></a>Betriebssystemsicherheit
Updates werden automatisch (standardmäßig) ausgeführt, sodass HoloLens 2-Apps immer auf dem neuesten Stand der neuesten Version von Windows Holographic und aller installierten Apps sind. Weitere Informationen zur sicheren Entwicklung unseres Betriebssystems finden Sie im Folgenden:
1. [Zustandstrennung und -isolation](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [Betriebssystem ohne Administratorrechte](https://docs.microsoft.com/hololens/security-adminless-os)
1. [Einschränken der Kennwortnutzung](https://docs.microsoft.com/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Physische Sicherheit
HoloLens 2 verfügt über Flashspeicher, der durch [bitLocker-Verschlüsselung geschützt ist.](https://docs.microsoft.com/hololens/security-encryption-data-protection) Ihr Gerät und die lokalen Daten können offline mit advanced [recovery companion (Advanced Recovery Companion)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) oder remote über MDM zurückgelöscht werden, wenn es als verwaltetes Gerät bereitgestellt wurde.

## <a name="data-protection"></a>Schutz von Daten
Windows-Updates werden automatisch (standardmäßig) ausgeführt, und die [Azure-Integration](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) schützt Daten, die zwischen sich selbst und der Cloud unterwegs sind. 

Beim Bereitstellen von HoloLens 2 auf externen Clients stellt [Dynamics 365 Remote Assist](https://docs.microsoft.com/hololens/hololens2-deployment-guide) sicher, dass Ihre vertraulichen Unternehmensdaten und -ressourcen getrennt und sicher sind. 

Die Freigabe von Diagnosedaten für Microsoft kann manuell von MDM oder vom Benutzer während der OOBE konfiguriert werden. Es gibt zwei Optionen: Optionale Diagnosedaten und Erforderliche Diagnosedaten. Wenn Ihre ursprüngliche Diagnoseeinstellung zu einem späteren Zeitpunkt zu Problembehandlungszwecken geändert werden muss, kann sie vom Benutzer unter Einstellungen **-> Datenschutz -> Diagnostics & Feedback** oder vom IT-Administrator (MDM) geändert werden, wenn ein verwaltetes Gerät ist. Weitere Informationen zu [Diagnose, Feedback und Datenschutz finden](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)Sie in Windows 10 .

> [!Important]
> Gerätediagnoseprotokolle enthalten personenbezogene Informationen (Personally Identifiable Information, PII), z. B. darüber, welche Prozesse oder Anwendungen der Benutzer bei typischen Vorgängen startet. Wenn mehrere Benutzer ein HoloLens-Gerät freigeben (z. B. wenn sich Benutzer mit unterschiedlichen Microsoft Azure Active Directory (Azure AD)-Konten beim gleichen Gerät anmelden), enthalten die Diagnoseprotokolle möglicherweise PII-Informationen, die für mehrere Benutzer gelten.

 

Es gibt [mehrere Sammlungsmethoden und Datenaufbewahrungsrichtlinien](https://docs.microsoft.com/hololens/hololens-diagnostic-logs) zum Sammeln von Diagnosedaten aus der HoloLens 2.  Weitere Informationen dazu, wie Microsoft Diagnosedaten sammelt und verwendet, finden Sie unter [Microsoft-Datenschutzerklärung – Diagnose](https://privacy.microsoft.com/privacystatement) – Erweitern von **Windows** im linken Navigationsmenü, und wählen Sie **Diagnose** aus. Wechseln Sie zum Abschnitt **Diagnose.**
