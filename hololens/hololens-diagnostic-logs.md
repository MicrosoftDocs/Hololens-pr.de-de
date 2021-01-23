---
title: Sammeln und nutzen von Diagnoseinformationen von HoloLens-Geräten
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
ms.openlocfilehash: 206a31476820e8722b1b72fbd501345a089379b1
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283226"
---
# Sammeln und nutzen von Diagnoseinformationen von HoloLens-Geräten

Benutzer und Administratoren von HoloLens können zwischen vier verschiedenen Methoden zum Sammeln von Diagnoseinformationen von HoloLens wählen:

- Feedback-Hub-App
- DiagnosticLog-Konfigurationsdienstanbieter
- Einstellungs-App

> [!IMPORTANT]  
> Gerätediagnoseprotokolle enthalten personenbezogene Informationen (PiI), z. B. dazu, welche Prozesse oder Anwendungen der Benutzer während eines typischen Betriebs startet. Wenn mehrere Benutzer ein HoloLens-Gerät freigeben (z. B. benutzer melden sich mit unterschiedlichen Microsoft Azure Active Directory (Azure AD)-Konten am selben Gerät an), enthalten die Diagnoseprotokolle möglicherweise PII-Informationen, die für mehrere Benutzer gelten. Weitere Informationen finden Sie in den [Datenschutzbestimmungen von Microsoft.](https://privacy.microsoft.com/privacystatement)

In der folgenden Tabelle werden die drei Auflistungsmethoden verglichen. Die Methodennamen verknüpfen sich mit ausführlicheren Informationen in den Abschnitten, die auf die Tabelle folgen.

|Methode |Voraussetzungen |Datenspeicherorte |Datenzugriff und -verwendung |Datenaufbewahrung |
| --- | --- | --- | --- | --- |
|[Feedback-Hub](#feedback-hub) |Netzwerk- und Internetverbindung<br /><br />Feedback-Hub-App<br /><br />Berechtigung zum Hochladen von Dateien in die Microsoft Cloud |Microsoft Cloud<br /><br />HoloLens-Gerät (optional) |Der Benutzer fordert Unterstützung an, stimmt den Nutzungsbedingungen zu und lädt die Daten hoch.<br /><br />Mitarbeiter von Microsoft zeigen die Daten entsprechend den Nutzungsbedingungen an. |Daten in der Cloud werden für den Zeitraum aufbewahrt, der von Next Generation Privacy (NGP) definiert ist. Anschließend werden die Daten automatisch gelöscht.<br /><br />Daten auf dem Gerät können jederzeit von einem Benutzer gelöscht werden, der **über Gerätebesitzer-** oder **Administratorberechtigungen** verfügt. |
|[Problembehandlung für Einstellungen](#settings-troubleshooter) |Einstellungs-App |HoloLens-Gerät<br /><br />Verbundener Computer (optional) |Der Benutzer speichert die Daten, und nur der Benutzer zugrifft auf die Daten (es sei denn, der Benutzer gibt die Daten ausdrücklich für einen anderen Benutzer weiter). |Die Daten werden aufbewahrt, bis der Benutzer sie löscht.* |
|[DiagnosticLog-Konfigurationsdienstanbieter](#diagnosticlog-csp) |Netzwerkverbindung<br /><br />MDM-Umgebung, die den DiagnosticLog-CSP unterstützt |Administrator konfiguriert Speicherorte |In der verwalteten Umgebung erteilt der Benutzer dem Administratorzugriff auf die Daten implizit seine Zustimmung.<br /><br />Der Administrator konfiguriert Zugriffsrollen und -berechtigungen. | Der Administrator konfiguriert die Aufbewahrungsrichtlinie. |
|[Offlinediagnose](#offline-diagnostics) |Gerätekonfiguration:<ul><li>Eingeschaltet und mit Computer verbunden</li><li>Netz- und Lautstärketasten funktionieren</li></ul> |HoloLens-Gerät<br /><br />Verbundener Computer |Der Benutzer speichert die Daten, und nur der Benutzer zugrifft auf die Daten (es sei denn, der Benutzer gibt die Daten ausdrücklich für einen anderen Benutzer weiter). |Die Daten werden aufbewahrt, bis der Benutzer sie löscht. | 


-   Der Endbenutzer ist dafür verantwortlich, die Protokolle verantwortunglich mit einer anderen Person zu teilen. Diese Dateien sind in erster Linie hilfreich, wenn Sie sich an den Kundendienst und Support wenden.  

## Feedback-Hub

Ein Benutzer von HoloLens kann die Microsoft Feedback Hub-Desktop-App verwenden, um Diagnoseinformationen an den Microsoft Support zu senden. Weitere Informationen und vollständige Anweisungen finden Sie unter ["Feedback".](hololens-feedback.md)  

> [!NOTE]  
> **Kommerzielle Benutzer oder Unternehmensbenutzer:** Wenn Sie die Feedback-Hub-App verwenden, um ein Problem im Zusammenhang mit MDM, der Bereitstellung oder einem anderen Aspekt der Geräteverwaltung zu melden, ändern Sie die Kategorie der App in die Kategorie **"Enterprise Management**  >  **Device".**

### Voraussetzungen

- Das Gerät ist mit einem Netzwerk verbunden.
- Die Feedback-Hub-App ist auf dem Desktopcomputer des Benutzers verfügbar, und der Benutzer kann Dateien in die Microsoft Cloud hochladen.

### Datenspeicherorte, Zugriff und Aufbewahrung

Durch Die Zustimmung zu den Nutzungsbedingungen des Feedback-Hubs stimmt der Benutzer ausdrücklich der Speicherung und Verwendung der Daten (gemäß der Definition durch diesen Vertrag) zu.

Der Feedbackhub bietet dem Benutzer zwei Orte zum Speichern von Diagnoseinformationen:

- **Die Microsoft Cloud**. Daten, die der Benutzer mithilfe der Feedback-Hub-App hochlädt, werden für die Anzahl von Tagen gespeichert, die mit den Anforderungen für den Datenschutz der nächsten Generation (Next Generation Privacy, NGP) konsistent ist. Mitarbeiter von Microsoft können einen NGP-kompatiblen Viewer verwenden, um während dieses Zeitraums auf die Informationen zu zugreifen.
   > [!NOTE]  
   > Diese Anforderungen gelten für Daten in allen Feedback-Hub-Kategorien.

- **Das HoloLens-Gerät.** Beim Ablegen eines Berichts im Feedbackhub kann der Benutzer beim Senden von Feedback eine lokale Kopie der Diagnose und Anlagen speichern auswählen, die **erstellt wurden.** Wenn der Benutzer diese Option auswählt, speichert der Feedbackhub eine Kopie der Diagnoseinformationen auf dem HoloLens-Gerät. Diese Informationen bleiben für den Benutzer (oder alle Benutzer, die dieses Konto für die Anmeldung bei HoloLens verwenden) zugänglich. Um diese Informationen zu löschen, muss ein Benutzer über **Gerätebesitzer-** oder **Administratorberechtigungen** auf dem Gerät verfügen. Ein Benutzer mit den entsprechenden Berechtigungen kann sich **** beim Feedbackhub anmelden, Diagnoseprotokolle für die  >  **Einstellungsansicht**auswählen und die Informationen löschen.

## Problembehandlung für Einstellungen

Ein HoloLens-Benutzer kann die App "Einstellungen" auf dem Gerät verwenden, um Probleme zu beheben und Diagnoseinformationen zu sammeln. Gehen Sie hierzu folgendermaßen vor:

1. Öffnen Sie die App "Einstellungen", und wählen **Sie "Update &**  >  **Sicherheitsprobleme beheben"** aus.
1. Wählen Sie den entsprechenden Bereich aus, und wählen Sie **"Start" aus.**
1. Reproduzieren Sie das Problem.
1. Kehren Sie nach dem Reproduzieren des Problems zu "Einstellungen" zurück, und wählen Sie **"Beenden" aus.**

### Voraussetzungen

- Die App "Einstellungen" ist auf dem Gerät installiert und steht dem Benutzer zur Verfügung.

### Datenspeicherorte, Zugriff und Aufbewahrung

Da der Benutzer die Datensammlung startet, ist er implizit mit der Speicherung der Diagnoseinformationen einverstanden. Nur der Benutzer oder jeder Benutzer, mit dem der Benutzer die Daten teilt, kann auf die Daten zugreifen.

Die Diagnoseinformationen werden auf dem Gerät gespeichert. Wenn das Gerät mit dem Computer des Benutzers verbunden ist, befinden sich die Informationen in der folgenden Datei auch auf dem Computer:

> Dieser PC\\ \<*HoloLens device name*> \\Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> In diesem Dateipfad und -namen steht er für den Namen des HoloLens-Geräts und gibt das Datum und die Uhrzeit an, zu der die \<*HoloLens device name*> \<*ddmmyyhhmmss*> Datei erstellt wurde.

Die Diagnoseinformationen bleiben an diesen Speicherorten, bis der Benutzer sie löscht.

## DiagnosticLog-Konfigurationsdienstanbieter

In einer Umgebung für die mobile Geräteverwaltung (Mobile Device Management, MDM) kann der #A0 den [#A1 (DiagnosticLog Configuration Service Provider, CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) verwenden, um Diagnoseeinstellungen auf registrierten #A2 zu konfigurieren. Der IT-Administrator kann diese Einstellungen so konfigurieren, dass Protokolle von registrierten Geräten erfasst werden.

### Voraussetzungen

- Das Gerät ist mit einem Netzwerk verbunden.
- Das Gerät ist in einer #A0 registriert, die den DiagnosticLog-CSP unterstützt.

### Datenspeicherorte, Zugriff und Aufbewahrung

Da das Gerät Teil der verwalteten Umgebung ist, erteilt der Benutzer implizit dem Administratorzugriff auf Diagnoseinformationen.

Der #A0 verwendet den DiagnosticLog-CSP, um die Datenspeicherungs-, Aufbewahrungs- und Zugriffsrichtlinien zu konfigurieren, einschließlich der Richtlinien, die Folgendes regeln:

- Die Cloudinfrastruktur, in der die Diagnoseinformationen gespeichert werden.
- Der Aufbewahrungszeitraum für die Diagnoseinformationen.
- Berechtigungen, die den Zugriff auf die Diagnoseinformationen steuern.

## Offlinediagnose
In Situationen, in denen das Gerät keine Diagnosen über den Feedbackhub oder die Einstellungs-Problembehandlung sammeln kann, können Sie die Diagnose manuell erfassen. Ein Szenario, in dem dies erforderlich ist, ist, wenn das Gerät keine Verbindung mit dem WLAN herstellen kann. Die Diagnose sammelt Absturzabbilds und Protokolle vom Gerät, die einem Supporttechniker von Microsoft dabei helfen, Probleme zu isolieren.

Dies funktioniert, wenn das Gerät im Datei-Explorer angezeigt wird, nachdem es über ein USB-Kabel an einen PC angeschlossen wurde. 

> [!NOTE]
> Die Generierung und Verwaltung der Offlinediagnose wird je nach Betriebssystemversion unterschiedlich gesteuert. Bisher wurde sie durch die Telemetrieeinstellung gesteuert, wird jetzt jedoch direkt über eine Richtlinie gesteuert. 

Verhalten vor [Windows Holographic, Verison 20H2:](hololens-release-notes.md#windows-holographic-version-20h2)
 - Die Offlinediagnose ist nur aktiviert, wenn der Benutzer entweder die OOBE durch geht oder der Wert der [Richtlinie "System\AllowTelemetry"](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) auf "Full" festgelegt ist (Basic ist der Standardwert für HoloLens). 
- Um die Offlinediagnose zu deaktivieren, wechseln Sie zur Seite > **"Einstellungen-App"** und wählen Sie **"Standard"** in **"Diagnosedaten" aus.** Bei Builds, bei denen die Offlinediagnose von der Telemetrieeinstellung abhängt, wirkt sich dies nur darauf aus, ob Protokolle erfasst werden oder nicht. Es wirkt sich nicht auf die gesammelten Dateien aus.
- Wenn das Gerät gesperrt ist, werden keine Protokolle angezeigt.

On builds [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) and ands:
- Wenn die Fallbackdiagnose aktiviert ist, wird sie von einer bestimmten MDM-Richtlinie mit der entsprechenden Einstellung [MixedReality/FallbackDiagnostics gesteuert.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Wenn das Gerät gesperrt ist, werden keine Protokolle angezeigt.


Sehen Sie sich dieses Video an, um mehr zu erfahren. 

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Führen Sie die folgenden Schritte aus, um Diagnosen zu erfassen:
1.  Schließen Sie das Gerät mit einem USB-Kabel an Ihren PC an.
2.  Navigieren Sie im Datei-Explorer auf Ihrem PC zu **"Dieser PC \<hololens-device> \Interner Speicher".**
3.  Wenn der **Ordner "Interner Speicher"** nicht angezeigt wird, wartet das Gerät auf die Anmeldung eines Benutzers. Melden Sie sich an oder schalten Sie das Gerät ein, indem Sie die NETZTASTE 10 Sekunden lang gedrückt halten.
4.  Drücken Sie die POWER + VOLUME DOWN-Tasten, **und lassen Sie sie** sofort los.
5.  Warten Sie eine Minute, bis das Gerät die Zip-Archive vorbereitet. (Eine temporäre Datei mit dem Namen HololensDiagnostics.temp wird möglicherweise sichtbar, während das Gerät die Zip-Archive generiert. Greifen Sie nicht auf die Datei zu, und speichern Sie sie nicht. Nach Abschluss des Prozesses wird er durch die Zip-Archive ersetzt.)
6.  Aktualisieren Sie den Datei-Explorer, und navigieren Sie zum Ordner **"\Dokumente".**
7.  Kopieren Sie die Diagnose-ZIP-Dateien, und teilen Sie sie mit dem Microsoft-Supportteam.

> [!NOTE]
> Einige der Diagnose-ZIP-Dateien enthalten möglicherweise personenbezogene Informationen.



