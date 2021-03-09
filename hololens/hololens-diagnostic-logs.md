---
title: Sammeln und Nutzen von Diagnoseinformationen von HoloLens-Geräten
description: Erfahren Sie, wie Sie Diagnoseinformationen von HoloLens-Geräten sammeln, verwenden und beibehalten.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/15/2020
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4a360e99a45b855957e36dd6ba31ede3da9631ba
ms.sourcegitcommit: b5f1b7c197cb58b746efc3809c61cf7a2e8c08ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "11399807"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Sammeln und Nutzen von Diagnoseinformationen von HoloLens-Geräten

HoloLens-Benutzer und -Administratoren können zwischen vier verschiedenen Methoden zum Sammeln von Diagnoseinformationen von HoloLens auswählen:

- Feedback-Hub-App
- DiagnosticLog-Konfigurationsdienstanbieter
- Einstellungs-App
- Offlinediagnose

> [!IMPORTANT]  
> Gerätediagnoseprotokolle enthalten personenbezogene Informationen (PII), z. B. darüber, welche Prozesse oder Anwendungen der Benutzer während typischer Vorgänge startet. Wenn mehrere Benutzer ein HoloLens-Gerät gemeinsam verwenden (z. B. benutzer melden sich mit unterschiedlichen Microsoft Azure Active Directory (Azure AD)-Konten am gleichen Gerät an), können die Diagnoseprotokolle PII-Informationen enthalten, die für mehrere Benutzer gelten. Weitere Informationen finden Sie unter [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).

In der folgenden Tabelle werden verschiedene Auflistungsmethoden verglichen. Die Methodennamen verknüpfen sich mit ausführlicheren Informationen in den Abschnitten, die der Tabelle folgen.

|Methode |Voraussetzungen |Datenspeicherorte |Datenzugriff und -verwendung |Datenaufbewahrung |
| --- | --- | --- | --- | --- |
|[Feedback-Hub](#feedback-hub) |Netzwerk- und Internetverbindung<br /><br />Feedback-Hub-App<br /><br />Berechtigung zum Hochladen von Dateien in die Microsoft Cloud |Microsoft Cloud<br /><br />HoloLens-Gerät (optional) |Der Benutzer bittet um Unterstützung, stimmt den Nutzungsbedingungen zu und lädt die Daten hoch.<br /><br />Microsoft-Mitarbeiter zeigen die Daten entsprechend den Nutzungsbedingungen an |Daten in der Cloud werden für den Zeitraum aufbewahrt, der von Next Generation Privacy (NGP) definiert wird. Anschließend werden die Daten automatisch gelöscht.<br /><br />Daten auf dem Gerät können jederzeit von einem Benutzer gelöscht werden, der über **Gerätebesitzer-** oder **Administratorberechtigungen** verfügt. |
|[Problembehandlung für Einstellungen](#settings-troubleshooter) |Einstellungs-App |HoloLens-Gerät<br /><br />Verbundener Computer (optional) |Der Benutzer speichert die Daten, und nur der Benutzer zugrifft auf die Daten (es sei denn, der Benutzer teilt die Daten ausdrücklich mit einem anderen Benutzer). |Die Daten werden auf dem Gerät aufbewahrt, bis der Benutzer sie löscht.* |
|[DiagnosticLog-Konfigurationsdienstanbieter](#diagnosticlog-csp) |Netzwerkverbindung<br /><br />MDM-Umgebung, die den DiagnosticLog-CSP unterstützt |Administrator konfiguriert Speicherorte |In der verwalteten Umgebung erteilt der Benutzer dem Administratorzugriff auf die Daten implizit seine Zustimmung.<br /><br />Administrator konfiguriert Zugriffsrollen und -berechtigungen. | Daten werden im Cloudspeicher aufbewahrt, und der Administrator konfiguriert die Aufbewahrungsrichtlinie. |
|[Offlinediagnose](#offline-diagnostics) |Gerätekonfiguration:<ul><li>Eingeschaltet und mit dem Computer verbunden</li><li>Power- und Volume-Tasten funktionieren</li></ul> |HoloLens-Gerät<br /><br />Verbundener Computer |Der Benutzer speichert die Daten, und nur der Benutzer zugrifft auf die Daten (es sei denn, der Benutzer teilt die Daten ausdrücklich mit einem anderen Benutzer). |Die Daten werden auf dem Gerät aufbewahrt, bis der Benutzer sie löscht. |

- Der Endbenutzer ist für die verantwortungsverantwortliche Freigabe der Protokolle für eine andere Person verantwortlich. Diese Dateien sind in erster Linie hilfreich, wenn Sie sich an den Kundendienst und support wenden.  

## <a name="feedback-hub"></a>Feedback-Hub

Ein HoloLens-Benutzer kann die Microsoft Feedback Hub-Desktop-App verwenden, um Diagnoseinformationen an den Microsoft Support zu senden. Weitere Informationen und vollständige Anweisungen finden Sie unter [Feedback geben.](hololens-feedback.md)  

> [!NOTE]  
> **Kommerzielle Oder Unternehmensbenutzer:** Wenn Sie die FeedbackHub-App verwenden, um ein Problem zu melden, das sich auf MDM, bereitstellung oder einen anderen Aspekt der Geräteverwaltung bezieht, ändern Sie die Kategorie der App in Kategorie Enterprise **Management**  >  **Device**.

### <a name="prerequisites"></a>Voraussetzungen

- Das Gerät ist mit einem Netzwerk verbunden.
- Die FeedbackHub-App ist auf dem Desktopcomputer des Benutzers verfügbar, und der Benutzer kann Dateien in die Microsoft Cloud hochladen.

### <a name="data-locations-access-and-retention"></a>Datenspeicherorte, Zugriff und Aufbewahrung

Durch die Zustimmung zu den Nutzungsbedingungen des FeedbackHubs stimmt der Benutzer explizit der Speicherung und Verwendung der Daten zu (wie in dieser Vereinbarung definiert).

Der Feedbackhub bietet dem Benutzer zwei Orte zum Speichern von Diagnoseinformationen:

- **Die Microsoft Cloud**. Daten, die der Benutzer mithilfe der FeedbackHub-App hochlädt, werden für die Anzahl von Tagen gespeichert, die mit den Anforderungen des Datenschutzes der nächsten Generation (Next Generation Privacy, NGP) konsistent sind. Microsoft-Mitarbeiter können einen NGP-kompatiblen Viewer verwenden, um während dieses Zeitraums auf die Informationen zu zugreifen.
   > [!NOTE]  
   > Diese Anforderungen gelten für Daten in allen Feedback Hub-Kategorien.

- **Das HoloLens-Gerät**. Während der Einreichung eines Berichts im Feedbackhub kann der Benutzer eine lokale Kopie von Diagnosen und Anlagen speichern auswählen, die beim Senden von **Feedback erstellt wurden.** Wenn der Benutzer diese Option auswählt, speichert der FeedbackHub eine Kopie der Diagnoseinformationen auf dem HoloLens-Gerät. Diese Informationen bleiben für den Benutzer (oder alle Benutzer, die dieses Konto zum Anmelden bei HoloLens verwenden) zugänglich. Um diese Informationen zu löschen, muss ein Benutzer über **Gerätebesitzer-** oder **Administratorberechtigungen** auf dem Gerät verfügen. Ein Benutzer mit den entsprechenden Berechtigungen kann sich **** beim FeedbackHub anmelden, Diagnoseprotokolle anzeigen und  >  **** die Informationen löschen.

## <a name="settings-troubleshooter"></a>Problembehandlung für Einstellungen

Ein HoloLens-Benutzer kann die Einstellungs-App auf dem Gerät verwenden, um Probleme zu beheben und Diagnoseinformationen zu sammeln. Gehen Sie hierzu folgendermaßen vor:

1. Öffnen Sie die Einstellungs-App, und wählen **& Seite "Sicherheitsprobleme**  >  **aktualisieren"** aus.
1. Wählen Sie den entsprechenden Bereich aus, und wählen Sie **Start aus.**
1. Reproduzieren Sie das Problem.
1. Kehren Sie nach dem Reproduzieren des Problems zu Einstellungen zurück, und wählen Sie **dann Beenden aus.**

### <a name="prerequisites"></a>Voraussetzungen

- Die Einstellungs-App ist auf dem Gerät installiert und steht dem Benutzer zur Verfügung.

### <a name="data-locations-access-and-retention"></a>Datenspeicherorte, Zugriff und Aufbewahrung

Da der Benutzer die Datensammlung startet, wird der Benutzer implizit der Speicherung der Diagnoseinformationen zustimmen. Nur der Benutzer oder jeder Benutzer, mit dem der Benutzer die Daten teilt, kann auf die Daten zugreifen.

Die Diagnoseinformationen werden auf dem Gerät gespeichert. Wenn das Gerät mit dem Computer des Benutzers verbunden ist, befinden sich die Informationen auch auf dem Computer in der folgenden Datei:

> Dieser PC\\ \<*HoloLens device name*> \\Interner Speicher\\Dokumente\\Ablaufverfolgung \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> Stellt in diesem Dateipfad und -name den Namen des HoloLens-Geräts dar und stellt das Datum und die Uhrzeit dar, zu der \<*HoloLens device name*> \<*ddmmyyhhmmss*> die Datei erstellt wurde.

Die Diagnoseinformationen bleiben an diesen Speicherorten, bis der Benutzer sie löscht.

## <a name="diagnosticlog-csp"></a>DiagnosticLog-Konfigurationsdienstanbieter

In einer Mobile Device Management (MDM)-Umgebung kann der #A0 den [DiagnosticLog-Konfigurationsdienstanbieter (DiagnosticLog Configuration Service Provider, CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) verwenden, um Diagnoseeinstellungen auf registrierten HoloLens-Geräten zu konfigurieren. Der IT-Administrator kann diese Einstellungen so konfigurieren, dass Protokolle von registrierten Geräten gesammelt werden.

Weitere Informationen:
- [Sammeln von Diagnosen von einem Windows-Gerät](https://docs.microsoft.com/mem/intune/remote-actions/collect-diagnostics)
- [Intune Public Preview – Windows 10-Gerätediagnose](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Voraussetzungen

- Das Gerät ist mit einem Netzwerk verbunden.
- Das Gerät ist in einer #A0 registriert, die den DiagnosticLog-CSP unterstützt.

### <a name="data-locations-access-and-retention"></a>Datenspeicherorte, Zugriff und Aufbewahrung

Da das Gerät Teil der verwalteten Umgebung ist, wird der Benutzer implizit dem Administratorzugriff auf Diagnoseinformationen zugestimmt.

Der #A0 verwendet den DiagnosticLog-CSP zum Konfigurieren der Datenspeicher-, Aufbewahrungs- und Zugriffsrichtlinien, einschließlich der Richtlinien, die Folgendes regeln:

- Die Cloudinfrastruktur, in der die Diagnoseinformationen gespeichert werden.
- Der Aufbewahrungszeitraum für die Diagnoseinformationen.
- Berechtigungen, die den Zugriff auf die Diagnoseinformationen steuern.

## <a name="offline-diagnostics"></a>Offlinediagnose
In Situationen, in denen das Gerät keine Diagnose über den Feedbackhub oder die Problembehandlung für Einstellungen erfassen kann, können Sie die Diagnose manuell erfassen. Ein Szenario, in dem dies erforderlich ist, ist, wenn das Gerät keine Verbindung mit Wi-Fi oder Sie nicht auf andere oben genannte Methoden zugreifen können. Die Diagnose sammelt Absturzabbilds und Protokolle vom Gerät, die einen Microsoft-Supporttechniker dabei unterstützen, Probleme zu isolieren.

Dies funktioniert, wenn das Gerät im Datei-Explorer angezeigt wird, nachdem es über ein USB-Kabel mit einem PC verbunden wurde.

> [!NOTE]
> Die Generierung und Verwaltung der Offlinediagnose wird abhängig von Ihrer Betriebssystemversion unterschiedlich gesteuert. Zuvor wurde sie durch die Telemetrieeinstellung gesteuert, wird jetzt jedoch direkt über die MDM-Richtlinie gesteuert. Wenn dies über eine Einstellung oder eine MDM-Richtlinie deaktiviert ist, können Diagnoseprotokolle nicht mithilfe dieses Mechanismus erfasst werden.

Verhalten vor [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2):
 - Die Offlinediagnose ist nur aktiviert, wenn der Benutzer entweder OOBE durch geht oder der Wert der [System\AllowTelemetry-Richtlinie](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) auf Full festgelegt ist (Basic ist der Standardwert für HoloLens). 
- Um die Offlinediagnose zu deaktivieren, wechseln Sie zu Einstellungen **App > Seite** Datenschutz, und wählen Sie unter Diagnosedaten die Option **Standard** **aus.** Bei Builds, bei denen die Offlinediagnose von der Telemetrieeinstellung abhängt, wirkt sich dies nur darauf aus, ob Protokolle erfasst werden oder nicht. Es wirkt sich nicht auf die erfassten Dateien aus.
- Wenn das Gerät gesperrt ist, werden keine Protokolle angezeigt.

Auf Builds [von Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) und mehr:
- Wenn die Fallbackdiagnose aktiviert ist, wird dies durch eine bestimmte MDM-Richtlinie mit der entsprechenden Einstellung [MixedReality/FallbackDiagnostics gesteuert.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Wenn das Gerät gesperrt ist, werden keine Protokolle angezeigt.

Sehen Sie sich dieses Video an, um mehr zu erfahren.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Führen Sie die folgenden Schritte aus, um Diagnosen zu sammeln:
1.  Verbinden Sie das Gerät mit einem USB-Kabel mit Ihrem PC.
2.  Navigieren Sie im Datei-Explorer auf Ihrem PC zu **"Dieser PC \<hololens-device> \Interner Speicher".**
3.  Wenn der **Ordner "Interner Speicher"** nicht angezeigt wird, wartet das Gerät darauf, dass sich ein Benutzer anmeldet. Melden Sie sich an oder schalten Sie das Gerät ein, indem Sie die POWER-Taste für 10 Sekunden gedrückt halten.
4.  Drücken Sie die POWER + VOLUME DOWN-Schaltflächen, und lassen Sie **sie** sofort los.
5.  Warten Sie eine Minute, bis das Gerät die ZIP-Archive vorbereitet. (Eine temporäre Datei mit dem Namen HololensDiagnostics.temp wird möglicherweise sichtbar, während das Gerät die ZIP-Archive generiert. Greifen Sie nicht auf diese Datei zu, oder speichern Sie sie nicht. Wenn der Prozess abgeschlossen ist, wird er durch die ZIP-Archive ersetzt.)
6.  Aktualisieren Sie den Datei-Explorer, und navigieren Sie zum **Ordner "\Dokumente".**
7.  Kopieren Sie die Diagnose-ZIP-Dateien, und teilen Sie sie mit dem Microsoft-Supportteam.

> [!NOTE]
> Einige der Diagnose-ZIP-Dateien enthalten möglicherweise personenbezogene Informationen.
