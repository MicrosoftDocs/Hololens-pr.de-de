---
title: Sammeln und Verwenden von Diagnoseinformationen von HoloLens-Geräten
description: Erfahren Sie, wie Sie Diagnoseinformationen von HoloLens Geräten sammeln, verwenden und beibehalten.
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
ms.openlocfilehash: 2cbf3005293f4fde91b22f3ff87edc6041e53336
ms.sourcegitcommit: 16897df83c309acecf04e2bcfea310891cb6681b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2021
ms.locfileid: "127817275"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Sammeln und Verwenden von Diagnoseinformationen von HoloLens-Geräten

HoloLens Benutzer und Administratoren können aus vier verschiedenen Methoden auswählen, um Diagnoseinformationen von HoloLens zu sammeln:

- Feedback-Hub-App
- DiagnosticLog CSP
- Einstellungs-App
- Offlinediagnose

> [!IMPORTANT]  
> Gerätediagnoseprotokolle enthalten personenbezogene Informationen (PiI), z. B. darüber, welche Prozesse oder Anwendungen der Benutzer bei typischen Vorgängen startet. Wenn mehrere Benutzer ein HoloLens Gerät freigeben (z. B. wenn sich Benutzer mit unterschiedlichen Microsoft Azure Active Directory -Konten (Azure AD) beim gleichen Gerät anmelden), können die Diagnoseprotokolle PERSONENBEZOGENE Informationen enthalten, die für mehrere Benutzer gelten. Weitere Informationen finden Sie in den [Datenschutzbestimmungen von Microsoft.](https://privacy.microsoft.com/privacystatement)

In der folgenden Tabelle werden verschiedene Auflistungsmethoden verglichen. Die Methodennamen sind mit ausführlicheren Informationen in den Abschnitten verknüpft, die der Tabelle folgen.

|Methode |Voraussetzungen |Datenspeicherorte |Datenzugriff und -verwendung |Beibehaltung von Daten |
| --- | --- | --- | --- | --- |
|[Feedback-Hub](#feedback-hub) |Netzwerk- und Internetverbindung<br /><br />Feedback-Hub-App<br /><br />Berechtigung zum Hochladen von Dateien in die Microsoft-Cloud |Microsoft-Cloud<br /><br />HoloLens Gerät (optional) |Der Benutzer fordert Unterstützung an, stimmt den Nutzungsbedingungen zu und lädt die Daten hoch.<br /><br />Microsoft-Mitarbeiter zeigen die Daten in Übereinstimmung mit den Nutzungsbedingungen an. |Daten in der Cloud werden für den Zeitraum beibehalten, der durch den Datenschutz der nächsten Generation (Next Generation Privacy, NGP) definiert ist. Anschließend werden die Daten automatisch gelöscht.<br /><br />Daten auf dem Gerät können jederzeit von einem Benutzer gelöscht werden, der über **Gerätebesitzer-** oder **Administratorberechtigungen** verfügt. |
|[Einstellungen Problembehandlung](#settings-troubleshooter) |Einstellungs-App |HoloLens-Gerät<br /><br />Verbundener Computer (optional) |Der Benutzer speichert die Daten, und nur der Benutzer greift auf die Daten zu (es sei denn, der Benutzer gibt die Daten explizit für einen anderen Benutzer weiter). |Die Daten werden auf dem Gerät beibehalten, bis der Benutzer sie löscht.* |
|[DiagnosticLog CSP](#diagnosticlog-csp) |Netzwerkverbindung<br /><br />MDM-Umgebung, die den DiagnosticLog-CSP unterstützt |Administrator konfiguriert Speicherorte |In der verwalteten Umgebung stimmt der Benutzer implizit dem Administratorzugriff auf die Daten zu.<br /><br />Der Administrator konfiguriert Zugriffsrollen und Berechtigungen. | Daten werden im Cloudspeicher beibehalten, und der Administrator konfiguriert die Aufbewahrungsrichtlinie. |
|[Offlinediagnose](#offline-diagnostics) |Gerätekonfiguration:<ul><li>Eingeschaltet und mit Computer verbunden</li><li>Funktionstüchtigen von Netzschaltern und Lautstärkereglern</li></ul> |HoloLens-Gerät<br /><br />Verbundener Computer |Der Benutzer speichert die Daten, und nur der Benutzer greift auf die Daten zu (es sei denn, der Benutzer gibt die Daten explizit für einen anderen Benutzer weiter). |Die Daten werden auf dem Gerät beibehalten, bis der Benutzer sie löscht. |

* Der Endbenutzer ist verantwortlich für die verantwortungsbewusste Freigabe der Protokolle für eine andere Person. Diese Dateien sind in erster Linie nützlich, wenn Sie sich an den Kundendienst und den Support wenden.  

## <a name="feedback-hub"></a>Feedback-Hub

Ein HoloLens Benutzer kann die Microsoft Feedback-Hub-Desktop-App verwenden, um Diagnoseinformationen an Microsoft-Support zu senden. Ausführliche Informationen und vollständige Anweisungen finden Sie unter [Feedback.](hololens-feedback.md)  

> [!NOTE]  
> **Kommerzielle Benutzer oder Unternehmensbenutzer:** Wenn Sie die Feedback-Hub-App verwenden, um ein Problem im Zusammenhang mit MDM, Bereitstellung oder einem anderen Aspekt der Geräteverwaltung zu melden, ändern Sie die App-Kategorie in **Enterprise**  >  **Verwaltungsgerätekategorie**.

>[!IMPORTANT]
> Um die bestmöglichen Daten zum Beheben von Problemen bereitzustellen, wird dringend empfohlen, die Gerätetelemetrie auf **Optional** festzulegen. Sie können diesen Wert während der Out-of-Box-Experience (OOBE) oder mithilfe der **Einstellungen-App** festlegen. Wählen Sie hierzu mithilfe von Einstellungen **> Einstellungen > Datenschutz > App-Diagnose starten > Ein** aus.

### <a name="prerequisites"></a>Voraussetzungen

- Das Gerät ist mit einem Netzwerk verbunden.
- Die Feedback-Hub-App ist auf dem Desktopcomputer des Benutzers verfügbar, und der Benutzer kann Dateien in die Microsoft-Cloud hochladen.

### <a name="data-locations-access-and-retention"></a>Datenspeicherorte, Zugriff und Aufbewahrung

Durch die Zustimmung zu den Nutzungsbedingungen der Feedback-Hub stimmt der Benutzer explizit der Speicherung und Nutzung der Daten zu (gemäß definition in dieser Vereinbarung).

Der Feedback-Hub bietet dem Benutzer zwei Orte zum Speichern von Diagnoseinformationen:

- **Die Microsoft-Cloud.** Daten, die der Benutzer mithilfe der Feedback-Hub App hochlädt, werden für die Anzahl von Tagen gespeichert, die den Anforderungen des Datenschutzes der nächsten Generation (Next Generation Privacy, NGP) entsprechen. Microsoft-Mitarbeiter können während dieses Zeitraums einen NGP-kompatiblen Viewer verwenden, um auf die Informationen zuzugreifen.

   > [!NOTE]  
   > Diese Anforderungen gelten für Daten in allen Feedback-Hub Kategorien.

- **Die HoloLens Geräts**. Beim Erstellen eines Berichts in Feedback-Hub kann der Benutzer lokale Kopie der Diagnose und Anlagen speichern auswählen, die **beim Senden von Feedback erstellt wurden.** Wenn der Benutzer diese Option auswählt, speichert der Feedback-Hub eine Kopie der Diagnoseinformationen auf dem HoloLens Gerät. Auf diese Informationen kann der Benutzer (oder jeder Benutzer, der dieses Konto für die Anmeldung bei HoloLens verwendet) zugreifen. Um diese Informationen zu löschen, muss ein Benutzer über **Gerätebesitzer-** oder **Administratorberechtigungen** auf dem Gerät verfügen. Ein Benutzer mit den entsprechenden Berechtigungen kann sich beim Feedback-Hub anmelden, **Einstellungen**  >  **Diagnoseprotokolle anzeigen** auswählen und die Informationen löschen.

## <a name="settings-troubleshooter"></a>Einstellungen Problembehandlung

Ein HoloLens Benutzer kann die **Einstellungen-App** auf dem Gerät verwenden, um Probleme zu beheben und Diagnoseinformationen zu sammeln. Gehen Sie hierzu folgendermaßen vor:

1. Öffnen Sie die Einstellungen-App, und wählen Sie die Seite Update & Security Troubleshoot **(Problembehandlung** für die Sicherheit aktualisieren)  >   aus.
1. Wählen Sie den entsprechenden Bereich und dann **Starten** aus.
1. Reproduzieren Sie das Problem.
1. Nachdem Sie das Problem reproduziert haben, kehren Sie zu Einstellungen zurück, und wählen Sie dann **Beenden** aus.

Ein Benutzer kann auch das Verhalten der Fallbackdiagnose über die **Einstellungen-App** konfigurieren. Navigieren Sie zur Seite **Datenschutz -> Problembehandlung,** um diese Einstellung zu konfigurieren.
> [!NOTE]
> Wenn für das Gerät eine MDM-Richtlinie konfiguriert ist, kann der Benutzer dieses Verhalten nicht außer Kraft setzen.

### <a name="os-update-troubleshooter"></a>Problembehandlung für Betriebssystemupdates
Auf Builds [Windows Holographic, Version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) und höher:
- Zusätzlich zu den vorherigen Problembehandlungen in der Einstellungen-App wurde eine neue Problembehandlung hinzugefügt, und die neue Einstellungen-App für Betriebssystemupdates wurde hinzugefügt. Navigieren Sie zu **Einstellungen -> Update & Security -> Problembehandlung -> Windows Update,** und wählen **Sie Starten** aus. Dadurch können Sie Ablaufverfolgungen erfassen, während Sie Ihr Problem mit Betriebssystemupdates reproduzieren, um die Problembehandlung für Ihre IT oder Ihren Support zu verbessern.

### <a name="prerequisites"></a>Voraussetzungen

- Die **Einstellungen-App** ist auf dem Gerät installiert und für den Benutzer verfügbar.

### <a name="data-locations-access-and-retention"></a>Datenspeicherorte, Zugriff und Aufbewahrung

Da der Benutzer die Datensammlung startet, stimmt der Benutzer implizit dem Speichern der Diagnoseinformationen zu. Nur der Benutzer oder jeder Benutzer, für den der Benutzer die Daten gemeinsam nutzt, kann auf die Daten zugreifen.

Die Diagnoseinformationen werden auf dem Gerät gespeichert. Wenn das Gerät mit dem Computer des Benutzers verbunden ist, befinden sich die Informationen auch auf dem Computer in der folgenden Datei:

> Dieser \\ \<*HoloLens device name*> \\ pcinterne Storage \\ Dokumente \\ Trace \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> In diesem Dateipfad und -namen \<*HoloLens device name*> stellt den Namen des HoloLens Geräts und das Datum und die Uhrzeit der \<*ddmmyyhhmmss*> Dateierstellung dar.

Die Diagnoseinformationen verbleiben an diesen Speicherorten, bis sie vom Benutzer gelöscht werden.

### <a name="view-diagnostic-report"></a>Anzeigen des Diagnoseberichts

Um die MDM-Diagnose auf HoloLens 2 anzuzeigen, wählen Sie Ihr WLAN-Symbol aus, navigieren Sie dann zu Einstellungen Accounts Access work or school (Kontozugriff auf Arbeits-, Schul- oder Schulkonto), und wählen Sie Export your management logs (Verwaltungsprotokolle  ->    >   **exportieren) aus.** HoloLens sendet die Protokolldateien an Ihr Konto und zeigt deren Speicherort auf Ihrem Desktop-PC an.

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

In einer Mobile Geräteverwaltung-Umgebung (MDM) kann der IT-Administrator den [Configuration Service Provider (CSP) DiagnosticLog](/windows/client-management/mdm/diagnosticlog-csp) verwenden, um Diagnoseeinstellungen auf registrierten HoloLens konfigurieren. Der IT-Administrator kann diese Einstellungen konfigurieren, um Protokolle von registrierten Geräten zu erfassen.

Weitere Informationen:
- [Sammeln von Diagnoseinformationen von einem Windows-Gerät](/mem/intune/remote-actions/collect-diagnostics)
- [Intune Public Preview – Windows 10 Gerätediagnose](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Voraussetzungen

- Das Gerät ist mit einem Netzwerk verbunden.
- Das Gerät wird in einer MDM-Umgebung registriert, die den DiagnosticLog-CSP unterstützt.

### <a name="data-locations-access-and-retention"></a>Datenspeicherorte, Zugriff und Aufbewahrung

Da das Gerät Teil der verwalteten Umgebung ist, erteilt der Benutzer implizit seine Zustimmung zum Administratorzugriff auf Diagnoseinformationen.

Der IT-Administrator verwendet den DiagnosticLog-CSP, um die Datenspeicher-, Aufbewahrungs- und Zugriffsrichtlinien zu konfigurieren, einschließlich der Richtlinien, die Folgendes regeln:

- Die Cloudinfrastruktur, in der die Diagnoseinformationen gespeichert werden.
- Die Beibehaltungsdauer für die Diagnoseinformationen.
- Berechtigungen, die den Zugriff auf die Diagnoseinformationen steuern.

## <a name="offline-diagnostics"></a>Offlinediagnose
In Situationen, in denen das Gerät nicht in der Lage ist, Diagnosedaten über Feedback-Hub oder die Einstellungen Problembehandlung zu erfassen, können Sie die Diagnose manuell erfassen. Ein Szenario, in dem dies erforderlich ist, ist, wenn das Gerät keine Verbindung mit einem gerät herstellen Wi-Fi oder Sie nicht auf andere oben genannte Methoden zugreifen können. Die Diagnose erfasst Absturzabbilddaten und Protokolle vom Gerät, die einem Microsoft-Supporttechniker helfen, Probleme zu isolieren.

Dies funktioniert, wenn das Gerät im Datei-Explorer angezeigt wird, nachdem es über ein USB-Kabel mit einem PC verbunden wurde.

> [!NOTE]
> Die Generierung und Verwaltung der Offlinediagnose wird je nach Betriebssystemversion unterschiedlich gesteuert. Zuvor wurde sie durch die Telemetrieeinstellung gesteuert, wird aber jetzt direkt über die MDM-Richtlinie gesteuert. Wenn diese Einstellung oder MDM-Richtlinie deaktiviert wird, können mit diesem Mechanismus keine Diagnoseprotokolle gesammelt werden.

Verhalten vor [Windows Holographic, Version 20H2:](hololens-release-notes.md#windows-holographic-version-20h2)
 - Die Offlinediagnose ist nur aktiviert, wenn der Benutzer entweder oobe durchfädt oder der Richtlinienwert [System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) auf Vollständig festgelegt ist (Basic ist der Standardwert HoloLens). 
- Um die Offlinediagnose zu deaktivieren, wechseln Sie zur **Seite Einstellungen App > Datenschutz,** und wählen Sie unter  **Diagnosedaten die Option Standard aus.** Bei Builds, bei denen die Offlinediagnose von der Telemetrieeinstellung abhängt, wirkt sich dies nur darauf aus, ob Protokolle erfasst werden. Dies wirkt sich nicht auf die erfassten Dateien aus.
- Wenn das Gerät gesperrt ist, werden keine Protokolle angezeigt.

Auf Builds [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) und ab:
- Wenn Fallbackdiagnose aktiviert ist, wird von einer bestimmten MDM-Richtlinie mit der entsprechenden Einstellung [MixedReality/FallbackDiagnostics gesteuert.](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Wenn das Gerät gesperrt ist, werden keine Protokolle angezeigt.

Sehen Sie sich dieses Video an, um mehr zu erfahren.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Führen Sie die folgenden Schritte aus, um Diagnosedaten zu erfassen:

1.  Verbinden Sie das Gerät mit einem USB-Kabel an Ihren PC an.

2.  Navigieren Sie im Datei-Explorer auf Ihrem PC zu **"This PC \<hololens-device> \Internal Storage".**

3.  Wenn der **ordner internal Storage** nicht angezeigt wird, wartet das Gerät darauf, dass sich ein Benutzer anmeldet. Melden Sie sich an, oder fahren Sie das Gerät mit strom, indem Sie die NETZSCHALTTASTE 10 Sekunden lang gedrückt halten.

4.  Drücken Sie die Tasten Power **+ Volume Down** , und lassen Sie sie sofort wieder frei.

5.  Warten Sie eine Minute, bis das Gerät die ZIP-Archive vorbereitet hat. (Eine temporäre Datei mit dem Namen HololensDiagnostics.temp wird möglicherweise sichtbar, während das Gerät die ZIP-Archive generiert. Greifen Sie nicht auf diese Datei zu, oder speichern Sie sie nicht. Wenn der Prozess abgeschlossen ist, wird er durch die ZIP-Archive ersetzt.)

6.  Aktualisieren Sie den Datei-Explorer, und navigieren Sie zum **Ordner "\Documents".**

7.  Kopieren Sie die DIAGNOSE-ZIP-Dateien, und geben Sie sie für das Microsoft-Supportteam weiter.

    > [!NOTE]
    > Einige der DIAGNOSE-ZIP-Dateien können PII enthalten.
