---
title: Sammeln und nutzen von Diagnoseinformationen von HoloLens-Geräten
description: Sammeln und nutzen von Diagnoseinformationen von HoloLens-Geräten
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
ms.openlocfilehash: b0a068bb50d033544b4bf44100d005dfedc1d94d
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162938"
---
# Sammeln und nutzen von Diagnoseinformationen von HoloLens-Geräten

HoloLens-Benutzer und-Administratoren können unter vier verschiedenen Methoden auswählen, um Diagnoseinformationen von HoloLens zu sammeln:

- Feedback-Hub-App
- DiagnosticLog-Konfigurationsdienstanbieter
- Einstellungs-App

> [!IMPORTANT]  
> Gerätediagnose Protokolle enthalten personenbezogene Informationen (PII), beispielsweise Informationen darüber, welche Prozesse oder Anwendungen der Benutzer während typischer Vorgänge startet. Wenn mehrere Benutzer ein HoloLens-Gerät verwenden (beispielsweise melden sich Benutzer mit verschiedenen Microsoft Azure Active Directory (AAD)-Konten bei demselben Gerät an), enthalten die Diagnoseprotokolle möglicherweise PII-Informationen, die für mehrere Benutzer gelten. Weitere Informationen finden Sie unter [Microsoft-Datenschutzbestimmungen](https://privacy.microsoft.com/privacystatement).

In der folgenden Tabelle werden die drei sammlungsmethoden verglichen. Die Methodennamen verweisen auf ausführlichere Informationen in den Abschnitten, die der Tabelle folgen.

|Methode |Voraussetzungen |Datenspeicherorte |Datenzugriff und-Verwendung |Datenaufbewahrung |
| --- | --- | --- | --- | --- |
|[Feedback-Hub](#feedback-hub) |Netzwerk-und Internetverbindung<br /><br />Feedback-Hub-App<br /><br />Berechtigung zum Hochladen von Dateien in die Microsoft-Cloud |Microsoft-Cloud<br /><br />HoloLens-Gerät (optional) |Der Benutzer bittet um Unterstützung, akzeptiert die Nutzungsbedingungen und lädt die Daten hoch<br /><br />Die Daten werden von Microsoft-Mitarbeitern im Einklang mit den Nutzungsbestimmungen angezeigt. |Daten in der Cloud werden für den Zeitraum beibehalten, der durch den Datenschutz der nächsten Generation (NGP) definiert ist. Dann werden die Daten automatisch gelöscht.<br /><br />Daten auf dem Gerät können jederzeit von einem Benutzer gelöscht werden, der über **Gerätebesitzer** oder **Administrator** Berechtigungen verfügt. |
|[Einstellungen-Problembehandlung](#settings-troubleshooter) |Einstellungs-App |HoloLens-Gerät<br /><br />Verbundener Computer (optional) |Der Benutzer speichert die Daten, und nur der Benutzer greift auf die Daten zu (es sei denn, der Benutzer hat die Daten ausdrücklich mit einem anderen Benutzer geteilt). |Die Daten werden beibehalten, bis der Benutzer Sie löscht. * |
|[DiagnosticLog-Konfigurationsdienstanbieter](#diagnosticlog-csp) |Netzwerkverbindung<br /><br />MDM-Umgebung, die den DiagnosticLog-CSP unterstützt |Der Administrator konfiguriert Speicherorte |In der verwalteten Umgebung stimmt der Benutzer implizit dem Administratorzugriff auf die Daten zu.<br /><br />Der Administrator konfiguriert Zugriffsrollen und Berechtigungen. | Der Administrator konfiguriert die Aufbewahrungsrichtlinie. |
|[Offline Diagnose](#offline-diagnostics) |Gerätekonfiguration:<ul><li>Eingeschaltet und mit Computer verbunden</li><li>Power-und Lautstärketasten funktionieren</li></ul> |HoloLens-Gerät<br /><br />Verbundener Computer |Der Benutzer speichert die Daten, und nur der Benutzer greift auf die Daten zu (es sei denn, der Benutzer hat die Daten ausdrücklich mit einem anderen Benutzer geteilt). |Die Daten werden beibehalten, bis der Benutzer Sie löscht. | 


-   Der Endbenutzer ist dafür verantwortlich, die Protokolle verantwortungsbewusst mit einer anderen Person zu teilen. Diese Dateien sind in erster Linie hilfreich, wenn Sie sich mit dem Kundendienst und-Support in Verbindung setzen.  

## Feedback-Hub

Ein HoloLens-Benutzer kann die Microsoft Feedback-Hub-Desktop-App verwenden, um Diagnoseinformationen an den Microsoft-Support zu senden. Details und vollständige Anweisungen finden Sie unter [Feedback zu uns](hololens-feedback.md).  

> [!NOTE]  
> **Kommerzielle oder Unternehmensbenutzer:** Wenn Sie die Feedback-Hub-App verwenden, um ein Problem zu melden, das sich auf MDM, Bereitstellung oder einen anderen Aspekt der Geräteverwaltung bezieht, ändern Sie die APP-Kategorie in die Kategorie **Enterprise Management**  >  **Device**.

### Voraussetzungen

- Das Gerät ist mit einem Netzwerk verbunden.
- Die Feedback-Hub-APP ist auf dem Desktopcomputer des Benutzers verfügbar, und der Benutzer kann Dateien in die Microsoft-Cloud hochladen.

### Datenspeicherorte, Zugriff und Aufbewahrung

Durch die Zustimmung zu den Nutzungsbedingungen des Feedback-Hubs willigt der Nutzer ausdrücklich in die Speicherung und Nutzung der Daten ein (wie in diesem Vertrag definiert).

Der Feedback-Hub bietet zwei Stellen, an denen der Benutzer Diagnoseinformationen speichern muss:

- **Die Microsoft-Cloud**. Daten, die der Benutzer mithilfe der Feedback-Hub-App hochlädt, werden für die Anzahl der Tage gespeichert, die mit den Datenschutzanforderungen der nächsten Generation (NGP) konsistent sind. Microsoft-Mitarbeiter können einen NGP-kompatiblen Viewer verwenden, um während dieses Zeitraums auf die Informationen zuzugreifen.
   > [!NOTE]  
   > Diese Anforderungen gelten für Daten in allen Feedback-Hub-Kategorien.

- **Das HoloLens-Gerät**. Beim Einreichen eines Berichts im Feedback-Hub kann der Benutzer **eine lokale Kopie der Diagnose und Anlagen, die beim geben von Feedback erstellt wurden, speichern**auswählen. Wenn der Benutzer diese Option auswählt, speichert der Feedback-Hub eine Kopie der Diagnoseinformationen auf dem HoloLens-Gerät. Diese Informationen bleiben dem Benutzer (oder jeder Person, die dieses Konto verwendet, um sich bei HoloLens zu anmelden) weiterhin zugänglich. Zum Löschen dieser Informationen muss ein Benutzer über **Gerätebesitzer** oder **Administrator** Berechtigungen auf dem Gerät verfügen. Ein Benutzer, der über die entsprechenden Berechtigungen verfügt, kann sich beim Feedback-Hub anmelden, **Einstellungen**  >  **Anzeigendiagnose Protokolle**auswählen und die Informationen löschen.

## Einstellungen-Problembehandlung

Ein HoloLens-Benutzer kann die Einstellungs-APP auf dem Gerät verwenden, um Probleme zu beheben und Diagnoseinformationen zu sammeln. Gehen Sie hierzu folgendermaßen vor:

1. Öffnen Sie die Einstellungs-APP, und wählen Sie **Update & Security**  >  **Troubleshooting** Page aus.
1. Wählen Sie den entsprechenden Bereich aus, und wählen Sie **Start**aus.
1. Reproduzieren Sie das Problem.
1. Nachdem Sie das Problem reproduziert haben, kehren Sie zu Einstellungen zurück, und wählen Sie **Beenden**aus.

### Voraussetzungen

- Die Einstellungs-APP ist auf dem Gerät installiert und steht dem Benutzer zur Verfügung.

### Datenspeicherorte, Zugriff und Aufbewahrung

Da der Benutzer die Datensammlung startet, stimmt der Benutzer implizit der Speicherung der Diagnoseinformationen zu. Nur der Benutzer oder alle Personen, mit denen der Benutzer die Daten freigibt, können auf die Daten zugreifen.

Die Diagnoseinformationen werden auf dem Gerät gespeichert. Wenn das Gerät mit dem Computer des Benutzers verbunden ist, befinden sich die Informationen auch auf dem Computer in der folgenden Datei:

> Diese PC\\ \<*HoloLens device name*> \\Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*> . ETL

> [!NOTE]  
> In diesem Dateipfad und-Name \<*HoloLens device name*> stellt den Namen des HoloLens-Geräts dar und \<*ddmmyyhhmmss*> stellt das Datum und die Uhrzeit der Erstellung der Datei dar.

Die Diagnoseinformationen verbleibt an diesen Speicherorten, bis der Benutzer Sie löscht.

## DiagnosticLog-Konfigurationsdienstanbieter

In einer MDM-Umgebung (Mobile Device Management) kann der IT-Administrator den [DiagnosticLog-Konfigurationsdienstanbieter (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) verwenden, um Diagnoseeinstellungen auf registrierten HoloLens-Geräten zu konfigurieren. Der IT-Administrator kann diese Einstellungen so konfigurieren, dass Protokolle von registrierten Geräten erfasst werden.

### Voraussetzungen

- Das Gerät ist mit einem Netzwerk verbunden.
- Das Gerät ist in einer MDM-Umgebung registriert, die den DiagnosticLog-CSP unterstützt.

### Datenspeicherorte, Zugriff und Aufbewahrung

Da das Gerät Teil der verwalteten Umgebung ist, stimmt der Benutzer implizit dem Administratorzugriff auf Diagnoseinformationen zu.

Der IT-Administrator verwendet den DiagnosticLog-CSP zum Konfigurieren der Daten Speicherungs-, Aufbewahrungs-und Zugriffsrichtlinien, einschließlich der folgenden Richtlinien:

- Die Cloud-Infrastruktur, in der die Diagnoseinformationen gespeichert sind.
- Der Aufbewahrungszeitraum für die Diagnoseinformationen.
- Berechtigungen, die den Zugriff auf die Diagnoseinformationen steuern.

## Offline Diagnose
In Situationen, in denen das Gerät keine Diagnose über den Feedback-Hub oder die Einstellungsproblem Behandlung sammeln kann, können Sie die Diagnose manuell sammeln. Ein Szenario, in dem dies erforderlich ist, ist, wenn das Gerät keine WLAN-Verbindung herstellen kann. Die Diagnose sammelt Absturzabbilder und-Protokolle vom Gerät, die einem Microsoft-Supporttechniker helfen, Probleme zu isolieren.

Dies funktioniert, wenn das Gerät im Datei-Explorer angezeigt wird, nachdem es über ein USB-Kabel mit einem PC verbunden wurde. 

> [!NOTE]
> Die Offline Diagnose Generierung und-Verwaltung wird je nach Betriebssystemversion unterschiedlich gesteuert. Zuvor wurde sie von der Telemetrie-Einstellung gesteuert, wird nun aber direkt über die Richtlinie gesteuert. 

Verhalten vor [Windows holographisch, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2):
 - Die Offline Diagnose ist nur aktiviert, wenn der Benutzer entweder OOBE durchläuft oder der [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) -Richtlinienwert auf vollständig gesetzt ist (Standard ist Standardwert auf HoloLens). 
- Wenn Sie die Offline Diagnose deaktivieren möchten, wechseln Sie zu **Einstellungen-app > Seite Privatsphäre** , und wählen Sie **Standard** in **Diagnosedaten**aus. Bei Builds, bei denen die Offline Diagnose von der Telemetrie-Einstellung abhängt, wirkt sich dies nur darauf aus, ob Protokolle erfasst werden. Es hat keinen Einfluss darauf, welche Dateien erfasst werden.
- Wenn Gerät gesperrt ist, werden die Protokolle nicht angezeigt.

Auf erstellt [Windows holographisch, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) und weiter:
- Wenn die Fall Back Diagnose aktiviert ist, wird Sie von einer bestimmten MDM-Richtlinie mit der entsprechenden Einstellung [MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics) gesteuert.
- Wenn Gerät gesperrt ist, werden die Protokolle nicht angezeigt.


Schauen Sie sich dieses Video an, um weitere Informationen zu erhalten. 

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Führen Sie die folgenden Schritte aus, um Diagnosen zu sammeln:
1.  Schließen Sie das Gerät mit einem USB-Kabel an Ihren PC an.
2.  Navigieren Sie im Datei-Explorer auf Ihrem PC zu **"dieser PC- \<hololens-device> \Internal-Speicher"**.
3.  Wenn der **interne Speicher** Ordner nicht angezeigt wird, wartet das Gerät darauf, dass sich ein Benutzer anmeldet. Wenn Sie die Einschalttaste 10 Sekunden lang gedrückt halten, sollten Sie sich entweder anmelden oder das Gerät in den Stromkreis schalten.
4.  Drücken Sie die **Einschalt** Taste, und lassen Sie Sie gleichzeitig wieder los.
5.  Warten Sie eine Minute, bis das Gerät die ZIP-Archive vorbereitet hat. (Eine temporäre Datei mit dem Namen "HololensDiagnostics. Temp" wird möglicherweise angezeigt, während das Gerät die ZIP-Archive generiert. Greifen Sie nicht auf die Datei zu oder speichern Sie Sie. Wenn der Prozess abgeschlossen ist, wird er durch die ZIP-Archive ersetzt.)
6.  Aktualisieren Sie den Datei-Explorer, und navigieren Sie zum Ordner **"\Dokumente"** .
7.  Kopieren Sie die ZIP-Diagnosedateien, und geben Sie Sie für das Microsoft-Support Team frei.

> [!NOTE]
> Einige der Diagnose-ZIP-Dateien enthalten möglicherweise personenbezogene Informationen.



