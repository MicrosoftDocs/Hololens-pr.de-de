---
title: Versionshinweise für HoloLens 2
description: Bleiben Sie mit allen Updates in jedem neuen HoloLens 2-Release auf dem laufenden.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/12/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: c45a9a05cc7911bc9866df5e4313bc27a205d333
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924480"
---
# <a name="hololens-2-release-notes"></a>Versionshinweise für HoloLens 2

Um sicherzustellen, dass Sie mit Ihren HoloLens Geräten produktiv arbeiten können, werden weiterhin Feature-, Fehler- und Sicherheitsupdates veröffentlicht. Auf dieser Seite können Sie sehen, was für HoloLens jeden Monat neu ist. Um das neueste HoloLens 2 Update zu erhalten, können Sie entweder nach [Updates suchen und manuell aktualisieren](hololens-update-hololens.md#check-for-updates-and-manually-update) oder das Full Flash Update (FFU) zum [Flashen Ihres Geräts über Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device)abrufen. Der [Download](https://aka.ms/hololens2download) wird auf dem neuesten Stand gehalten und bietet den neuesten allgemein verfügbaren Build.

> [!NOTE]
> Die letzte Ankündigung von Windows 11 konzentrierte sich auf die PC-Version von Windows. Wir haben vor Kurzem ein [wichtiges Betriebssystemupdate für HoloLens 2 im Oktober 2021](#windows-holographic-version-21h2)veröffentlicht, und wir arbeiten basierend auf Kundenfeedback an weiteren zukünftigen Releases.

## <a name="windows-holographic-version-21h2"></a>Windows Holographic, Version 21H2

- Build 20348.1432

Windows Holographic, Version 21H2 ist jetzt verfügbar und bietet viele neue Features für HoloLens 2 Benutzer und IT-Experten. Hier geht es um die verbesserten Problembehandlungs- und Geräteberichte, einige behobene Fehler im Kioskmodus und der Zertifikatanzeige, die erweiterte Verwaltbarkeitsoberfläche und die erhöhte Updatezuverlässigkeit. Ein neues Feature dieses Featureupdates, das HoloLens wird, ist der Moving Platform-Modus. Sehen Sie sich alle neuen hervorragenden Features für HoloLens 2 an.

Dieses neueste Release ist ein monatliches Update auf Version 21H1, aber dieses Mal enthalten wir neue Features. Die Hauptbuildnummer bleibt unverändert, und Windows Update gibt ein monatliches Release auf Version 21H1 (Build 20348) an. Sie können sich Ihre Buildnummer auf dem Bildschirm Einstellungen > About ansehen, um zu bestätigen, dass Sie über den neuesten verfügbaren Build 20348.1432+ informiert sind. Öffnen Sie zum Aktualisieren auf das neueste Release die Einstellungen-App, wechseln Sie zu Update & Security (& Sicherheit aktualisieren), und tippen Sie auf Nach Updates suchen. Weitere Informationen zum Verwalten HoloLens Updates finden Sie unter [Verwalten von HoloLens Updates.](hololens-updates.md)

| Funktion                 | BESCHREIBUNG                | Benutzer oder Szenario |
|-------------------------|----------------------------|--------------|
| [Modus für bewegliche Plattformen](#moving-platform-mode) | Führt die Betaversion des Moving Platform Mode ein, die bei der Konfiguration die Verwendung von HoloLens 2 bei großen 1000-160-Euro ermöglicht, die eine geringe dynamische Bewegung aufweisen. | Alle |
| [PFX-Dateiunterstützung für den Zertifikat-Manager](#pfx-file-support-for-certificate-manager) | Hinzufügen von PFX-Zertifikaten über Einstellungen Benutzeroberfläche | Endbenutzer |
| [Anzeigen des erweiterten Diagnoseberichts in Einstellungen auf HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Anzeigen von MDM-Diagnoseprotokollen auf dem Gerät | Problembehandlung |
| [Offlinediagnosebenachrichtigungen](#offline-diagnostics-notifications) | Feedback zur Protokollsammlung | Problembehandlung |
| [Verbesserungen bei der Protokollsammlung mit geringem Speicher](#low-storage-log-collection-improvements) | Verbesserungen an Protokollsammlungsszenarien in Situationen mit geringem Speicherbedarf. | Problembehandlung |
| [CSP-Änderungen für die Berichterstellung HoloLens Details](#csp-changes-for-reporting-hololens-details) | Neue CSPs zum Abfragen von Daten | IT-Administratoren    |
| [Richtlinie für die automatische Anmeldung, die vom CSP gesteuert wird](#auto-login-policy-controlled-by-csp) | Wird verwendet, um sich automatisch bei einem Konto anzumelden. | IT-Administratoren |
| [Verbesserte Erkennung von Updateneustarts und Benachrichtigungen](#improved-update-restart-detection-and-notifications) | Neue aktivierte Richtlinien und Benutzererfahrung für Updates. | IT-Administratoren |
| [Smart Retry für App-Updates](#smart-retry-for-app-updates) | Ermöglicht IT-Administratoren geplante Wiederholungsversuche zum Aktualisieren von Apps. | IT-Administratoren |
| [Nur private Store-Apps für Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Konfigurieren der Store-App, um nur Apps aus der Organisation anzuzeigen | IT-Administrator |
| [Verwenden von WDAC- und LOB-Apps](#use-wdac-and-lob-apps) | Ermöglicht IT-Administratoren, ihre eigenen Apps zu verwenden und weiterhin WDAC zu verwenden, um andere Apps zu blockieren. | IT-Administratoren |
| [Fehlerbehebungen und Verbesserungen](#fixes-and-improvements) | Fehlerbehebungen und Verbesserungen für HoloLens. | Alle |

### <a name="it-admin-feature-checklist"></a>Prüfliste für IT-Administratorfeatures

✔️ Wenn Sie ein einzelnes Azure AD Konto für die automatische Anmeldung festlegen möchten, [konfigurieren Sie diesen neuen CSP.](#auto-login-policy-controlled-by-csp) <br>
✔️ Wenn Sie Ihre Apps so konfigurieren möchten, dass sie nach einem Updatefehler automatisch versucht werden, legen Sie [diesen neuen CSP für intelligente Wiederholungen fest.](#smart-retry-for-app-updates) <br>
✔️ Wenn Sie mehr Kontrolle über Betriebssystemupdates haben möchten, sehen Sie sich diese [neu aktivierten Updaterichtlinien an.](#improved-update-restart-detection-and-notifications) <br>
✔️ Wenn Sie die Apps Ihrer Organisation über die Microsoft Store im Unternehmensspeicher verfügbar machen müssen, aber nur den Zugriff auf die Apps Ihrer Organisation und nicht auf den vollständigen Store zulassen möchten, [legen Sie diese Richtlinie fest.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ Wenn Sie den freien Speicherplatz, die SSID oder die BSSID Ihrer HoloLens Geräte kennen möchten, sehen Sie sich diese [Berichts-CSPs an.](#csp-changes-for-reporting-hololens-details) <br>
✔️ Wenn Sie WDAC verwenden möchten, um den Start von Apps oder Prozessen zu blockieren, aber auch Ihre eigene Reihe von Sperr-Apps verwenden müssen, können Sie lob [jetzt in Ihrer WDAC-Richtlinie zulassen.](#use-wdac-and-lob-apps)

### <a name="moving-platform-mode"></a>Modus für bewegliche Plattformen

Ab [Windows Holographic, Version 21H2,](hololens-release-notes.md#windows-holographic-version-21h2) haben wir Betaunterstützung für die Nachverfolgung auf Plattformen mit geringer dynamischer Bewegung auf HoloLens 2 hinzugefügt. Nachdem Sie den Build installiert und den Moving Platform Mode aktiviert haben, können Sie Ihre HoloLens 2 in umgebungen verwenden, auf die zuvor nicht zugegriffen werden kann, z. B. in großen Booten und großen Mengen. Derzeit ist das Feature nur auf die Unterstützung dieser spezifischen beweglichen Plattformen ausgerichtet. Zwar hindert Sie nichts daran, die Verwendung des Features in anderen Umgebungen zu versuchen, der Schwerpunkt bei diesem Feature liegt aber zuerst bei der hinzugefügten Unterstützung für diese Umgebungen.

Weitere Informationen dazu, was unterstützt wird und wie Sie dieses neue Feature aktivieren, [finden Sie auf der Seite zum Verschieben der Plattform](hololens2-moving-platform.md).

#### <a name="overview-to-try-out-moving-platform-mode"></a>Übersicht zum Testen des Moving Platform-Modus

1. [Aktivieren Sie den Entwicklermodus und das Geräteportal.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. [Aktivieren Sie das Verschieben des Plattformmodus über das Geräteportal.](hololens2-moving-platform.md#enabling-moving-platform-mode)
1. Bringen Sie Ihr Gerät auf Ihre große bewegte Plattform, und beobachten Sie, wie stabil Hologramme sind.

### <a name="pfx-file-support-for-certificate-manager"></a>PFX-Dateiunterstützung für den Zertifikat-Manager

Eingeführt in Windows Insider-Build 20348.1405. Wir haben dem [Zertifikat-Manager](certificate-manager.md) Unterstützung für die Verwendung von PFX-Zertifikaten hinzugefügt. Wenn Benutzer zu **Einstellungen** Update &  >  **Sicherheitszertifikate** navigieren und Zertifikat  >   **installieren** auswählen, unterstützt die Benutzeroberfläche jetzt PFX-Zertifikatsdateien.
Benutzer können ein PFX-Zertifikat mit privatem Schlüssel in den Benutzer- oder Computerspeicher importieren.

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>Übersicht zum Testen von PFX-Dateien im Zertifikat-Manager

1. Bereiten Sie Ihre PFX-Datei vor.
1. Kopieren Sie die Datei über ein USB-C-Kabel auf Ihr Gerät.
1. Öffnen Sie die Einstellungen-App, navigieren Sie zum [Zertifikat-Manager,](certificate-manager.md) und wenden Sie das Zertifikat an.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Anzeigen des erweiterten Diagnoseberichts in Einstellungen auf HoloLens

Bei verwalteten Geräten bei der Problembehandlung ist die Bestätigung, dass eine erwartete Richtlinienkonfiguration angewendet wird, ein wichtiger Schritt. Vor diesem neuen Feature musste dies über MDM oder in der Nähe des Geräts erfolgen, nachdem mdm-Diagnoseprotokolle exportiert wurden, die über **Einstellungen**  ->  **Konten**  >  **auf Arbeits- oder Schulkonto zugreifen** gesammelt wurden. Wählen Sie dann **Verwaltungsprotokolle exportieren** und auf einem pc in der Nähe anzeigen aus.

Jetzt kann die MDM-Diagnose über den Edge-Browser auf dem Gerät angezeigt werden. Um den MDM-Diagnosebericht einfacher anzuzeigen, navigieren Sie zur Seite Auf Arbeits- oder Schuleinrichtung zugreifen, und wählen **Sie Erweiterten Diagnosebericht anzeigen** aus. Dadurch wird der Bericht in einem neuen Edgefenster generiert und geöffnet.

![Zeigen Sie den erweiterten Diagnosebericht in Einstellungen App an.](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>Übersicht zum Testen des erweiterten Diagnoseberichts

1. Öffnen Sie die App „Einstellungen“.
1. Navigieren Sie zur Seite Konten, und klicken Sie auf den neuen Link **Exportieren Sie Ihre Verwaltungsprotokolle.**
1. Zeigen Sie erweiterte Informationen zu den Konfigurationen Ihres Geräts an.

### <a name="offline-diagnostics-notifications"></a>Offlinediagnosebenachrichtigungen

Dies ist ein Update für ein vorhandenes Feature namens [Offlinediagnose.](hololens-diagnostic-logs.md#offline-diagnostics) Bisher gab es keinen eindeutigen Hinweis für Benutzer, dass sie die Diagnosesammlung ausgelöst oder abgeschlossen hatten.
In [Windows Holographic,Version 21H2 hinzugefügt,](hololens-release-notes.md#windows-holographic-version-21h2)gibt es zwei Formen von Feedback zur Offlinediagnose. Das erste , das popupt, zeigt Benachrichtigungen an, die sowohl beim Start als auch beim Abschluss der Sammlung angezeigt werden. Diese werden angezeigt, wenn der Benutzer angemeldet ist und über Visuals verfügt.

![Popup zum Sammeln von Protokollen.](./images/logcollection1.jpg)

![Popup, wenn die Protokollsammlung abgeschlossen ist.](./images/logcollection2.jpg)

Da Benutzer die Offlinediagnose häufig als Fallbackmechanismus für die Protokollsammlung verwenden, wenn sie keinen Zugriff auf eine Anzeige haben, sich nicht anmelden können oder sich noch in OOBE befinden, wird beim Sammeln von Protokollen auch ein Audio cue wiedergegeben. Dieser Sound wird zusätzlich zur Popupbenachrichtigung wiedergegeben.

Dieses neue Feature wird aktiviert, wenn Ihr Gerät aktualisiert wird, und muss nicht aktiviert oder verwaltet werden. In jedem Fall, in dem dieses neue Feedback nicht angezeigt oder gehört werden kann, wird weiterhin die Offlinediagnose generiert.

Wir hoffen, dass es durch diese neuere Hinzufügung von Feedback zur Freundlichkeit einfacher ist, Diagnosedaten zu sammeln und Schneller in der Lage zu sein, Ihre Probleme zu beheben.

Diese Informationen können später auf der Seite mit den [Diagnoseprotokollen](hololens-diagnostic-logs.md#offline-diagnostics)angezeigt werden.

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>Übersicht zum Testen der Diagnosebenachrichtigungen

1. Entsperren Sie Ihr Gerät, und tragen Sie es ab.
1. Drücken Sie die Kombination aus **Einschaltfläche** und **Lautstärke nach unten,** um die [Offlinediagnose](hololens-diagnostic-logs.md#offline-diagnostics)zu erfassen.
1. Zeigen Sie die Popupbenachrichtigungen an, und hören Sie Audiohinweise dazu, wann Ihr Gerät gestartet wird und das Sammeln von Protokollen abgeschlossen ist.

### <a name="low-storage-log-collection-improvements"></a>Verbesserungen bei der Protokollsammlung mit geringem Speicher

In Szenarien, in denen ein Gerät bei der Erfassung von Diagnoseprotokollen wenig Speicherplatz auf dem Datenträger zu haben scheint, wird ein zusätzlicher Bericht mit dem Namen **StorageDiagnostics.zip** erstellt. Der Schwellenwert für niedrigen Speicher wird automatisch durch Windows [Speichers sense](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)bestimmt.

Diese Informationen können später auf der Seite mit den [Diagnoseprotokollen](hololens-diagnostic-logs.md#offline-diagnostics)angezeigt werden.

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>Übersicht, um die Verbesserungen bei geringem Speicher zu testen

1. Füllen Sie den Speicherplatz Ihres Geräts aus.
1. Drücken Sie die Kombination aus **Einschaltfläche** und **Lautstärke nach unten,** um die [Offlinediagnose](hololens-diagnostic-logs.md#offline-diagnostics)zu erfassen.
1. Beachten Sie, dass in der Sammlung der Protokolle, die im Ordner Dokumente Ihrer HoloLens gespeichert sind, eine neue Datei vorhanden ist.

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP-Änderungen für die Berichterstellung HoloLens Details

Die folgenden CSPs wurden mit neuen Möglichkeiten zum Melden von Informationen von Ihren HoloLens-Geräten aktualisiert.

#### <a name="devdetail-csp---free-storage"></a>DevDetail-CSP: Kostenlose Storage

DevDetail CSP meldet jetzt auch freien Speicherplatz auf HoloLens Gerät. Dies sollte ungefähr mit dem Wert übereinstimmen, der auf der seite Storage Einstellungen App angezeigt wird. Im Folgenden finden Sie den spezifischen Knoten, der diese Informationen enthält.

- ./DevDetail/Ext/Microsoft/FreeStorage (nur GET-Vorgang)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus-CSP: SSID und BSSID

DeviceStatus CSP meldet jetzt auch SSID und BSSID Wi-Fi Netzwerks, mit dem HoloLens aktiv verbunden ist. Im Folgenden werden die spezifischen Knoten mit diesen Informationen angezeigt.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID

Syncml-Beispielblob (für MDM-Anbieter) zum Abfragen von NetworkIdentifiers

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a>Richtlinie für die automatische Anmeldung, die von CSP gesteuert wird

Diese neue AutoLogonUser-Richtlinie steuert, ob ein Benutzer automatisch angemeldet wird. Einige Kunden möchten Geräte einrichten, die an eine Identität gebunden sind, aber keine Anmeldeerfahrung haben möchten. Imagine, ein Gerät zu nutzen und sofort Remoteunterstützung zu verwenden. Sie haben auch den Vorteil, dass Sie HoloLens Geräte schnell verteilen und endbenutzern ermöglichen können, die Anmeldung zu beschleunigen.

Wenn die Richtlinie auf einen nicht leeren Wert festgelegt ist, wird die E-Mail-Adresse des Benutzers für die automatische Anmeldung angegeben. Der angegebene Benutzer muss sich mindestens einmal beim Gerät anmelden, um die automatische Anmeldung zu aktivieren.

Der OMA-URI der neuen Richtlinie `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` Zeichenfolgenwert

- Für Benutzer mit derselben E-Mail-Adresse ist die automatische Anmeldung aktiviert.

Auf einem Gerät, auf dem diese Richtlinie konfiguriert ist, muss sich der in der Richtlinie angegebene Benutzer mindestens einmal anmelden. Bei nachfolgenden Neustarts des Geräts nach der ersten Anmeldung wird der angegebene Benutzer automatisch angemeldet. Es wird nur ein einzelner Benutzer für die automatische Anmeldung unterstützt. Nach der Aktivierung kann sich der automatisch angemeldete Benutzer nicht mehr manuell abmelden. Um sich als anderer Benutzer anzumelden, muss die Richtlinie zuerst deaktiviert werden.

> [!NOTE]
>
> - Einige Ereignisse, z. B. wichtige Betriebssystemupdates, erfordern möglicherweise, dass sich der angegebene Benutzer erneut beim Gerät anmeldet, um das Verhalten der automatischen Anmeldung fortzusetzen.
> - Die automatische Anmeldung wird nur für MSA- und AAD-Benutzer unterstützt.

#### <a name="overview-to-try-auto-logon-csp"></a>Übersicht zum Testen des automatischen Anmelde-CSP

1. Konfigurieren Sie den neuen CSP [mithilfe einer benutzerdefinierten Richtlinie](/mem/intune/configuration/custom-settings-windows-10) für einen gewünschten Benutzer: `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`
1. Wenden Sie den CSP über das [Bereitstellungspaket](hololens-provisioning.md) oder [MDM](hololens-mdm-configure.md)auf das Gerät an.
1. Melden Sie sich beim angegebenen Konto an.
1. Starten Sie das Gerät neu, und beobachten Sie, dass der Benutzer automatisch angemeldet ist.

### <a name="improved-update-restart-detection-and-notifications"></a>Verbesserte Erkennung von Updateneustarts und Benachrichtigungen

Zwischen aktiven Stunden und Installationszeitrichtlinien ist es möglich, einen Neustart HoloLens Geräten zu vermeiden, wenn sie verwendet werden. Es würde jedoch auch die Einführung von Updates verzögern, wenn keine Neustarts durchgeführt werden, um die Installation eines erforderlichen Updates abzuschließen. Wir haben nun Richtlinien hinzugefügt, mit denen die IT-It Stichtage und erforderliche Neustarts erzwingen und sicherstellen kann, dass die Installation eines Updates rechtzeitig abgeschlossen wird. Benutzer können benachrichtigt werden, bevor der Neustart initiiert wird, und sie können den Neustart entsprechend der IT-Richtlinie verzögern.

Die folgenden Updaterichtlinien wurden hinzugefügt:

- [Update/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Update/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Update/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Update/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Update/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

#### <a name="overview-to-try-new-update-notifications"></a>Übersicht zum Testen neuer Updatebenachrichtigungen

1. Konfigurieren Sie einen der neuen Update-CSPs über [das Bereitstellungspaket](hololens-provisioning.md) oder [mdm](hololens-mdm-configure.md) (siehe Linkliste oben, und wählen Sie einen aus).
1. Verwenden Sie das Gerät während der geplanten Zeit.
1. Beachten Sie, dass der Benutzer über das Update benachrichtigt wird und das Gerät neu starten \* muss.

\* Ihre Ergebnisse können je nach verwendeten Updaterichtlinien variieren.

### <a name="smart-retry-for-app-updates"></a>Smart Retry für App-Updates

Jetzt für HoloLens aktiviert ist, ist eine neue Richtlinie, mit der IT-Administratoren ein wiederkehrendes oder einmaliges Datum festlegen können, um Apps neu zu starten, deren Update fehlgeschlagen ist, weil die App verwendet wird und das Update angewendet werden kann. Diese können basierend auf einigen verschiedenen Triggern festgelegt werden, z. B. einer geplanten Zeit oder einer Anmeldung. Weitere Informationen zur Verwendung dieser Richtlinie finden Sie unter [ApplicationManagement/ScheduleForceRestartForUpdateFailures.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

Diese Informationen finden Sie später auf der [Seite app deployment store for business (App-Bereitstellungsspeicher für Unternehmen).](app-deploy-store-business.md)

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>Übersicht zum Testen von Smart Retry für App-Updates

1. Konfigurieren Sie das neue Feature für intelligente Wiederholungen.
1. Melden Sie sich auf einem Gerät, auf dem Ihre App noch nicht empfangen wurde und für das sie ordnungsgemäß konfiguriert ist, in einer Onlineumgebung an.
1. Sorgen Sie dafür, dass das Gerät die App nicht herunterladen kann, indem Sie sie deaktivieren oder trennen.
1. Lassen Sie Ihr Gerät während der ausgelösten Zeit eingeschaltet und mit dem Internet verbunden, um den Download zu wiederholen.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Nur private Store-Apps für Microsoft Store

Die RequirePrivateStoreOnly-Richtlinie wurde für HoloLens aktiviert. Mit dieser Richtlinie kann die Microsoft Store-App so konfiguriert werden, dass nur der private Speicher angezeigt wird, der für Ihre Organisation über [Microsoft Store für Unternehmen](/microsoft-store/microsoft-store-for-business-overview)konfiguriert wurde. Beschränken des Zugriffs auf die Apps, die Sie zur Verfügung gestellt haben.

Weitere Informationen zu [ApplicationManagement/RequirePrivateStoreOnly](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

Diese Informationen finden Sie später auf der [Seite app deployment store for business (App-Bereitstellungsspeicher für Unternehmen).](app-deploy-store-business.md)

#### <a name="overview-to-try-only-private-store-apps"></a>Übersicht, um nur private Store-Apps auszuprobieren

1. Konfigurieren Sie die neue Richtlinie für Ihre Geräte über [MDM.](hololens-mdm-configure.md)
1. Melden Sie sich bei einem Gerät mit der Richtlinie an.
1. Öffnen Sie die Microsoft Store-App, und beobachten Sie, dass Sie nur die Apps Ihrer Organisation sehen können.

### <a name="use-wdac-and-lob-apps"></a>Verwenden von WDAC- und LOB-Apps

Sie können jetzt WDAC verwenden, um den Start von Apps oder Prozessen zu blockieren und weiterhin Ihre eigene Reihe von Sperr-Apps zu verwenden. Sie können sie jetzt in Ihrer WDAC-Richtlinie zulassen. Die Verwendung dieser Richtlinie umfasst das Ausführen einer zusätzlichen Codezeile in PowerShell, wenn Sie Ihre WDAC-Richtlinie erstellen. [Sehen Sie sich die Hier beschriebenen Schritte an.](/mem/intune/configuration/custom-profile-hololens)

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>Übersicht über das Testen eigener Apps bei der Verwendung von WDAC zum Blockieren anderer Apps

1. Sammeln Sie die AUMIDs Ihrer LOB-App und die Apps, die Sie blockieren möchten.
1. [Erstellen Sie eine neue WDAC-Richtlinie,](/mem/intune/configuration/custom-profile-hololens) und folgen Sie den neuen Schritten.
1. [Stellen Sie die Richtlinie mithilfe von MDM](hololens-mdm-configure.md) auf Ihrem Gerät zur Anwendung.
1. Melden Sie sich beim Gerät an, und beobachten Sie, wie Sie Ihre App starten und andere blockieren können.

### <a name="fixes-and-improvements"></a>Fehlerbehebungen und Verbesserungen

#### <a name="for-developers"></a>Für Entwickler

- Es wurde ein [bekanntes Problem für Geräteportal, bei](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)dem keine Aufforderung zum Herunterladen gesperrter Dateien angezeigt wurde.
- Es wurde ein [bekanntes Problem bei Geräteportal dateiupload- und download-Time outs behoben.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Die Gamepadverarbeitung für 2D-Apps wurde in Insider-Builds deaktiviert. Durch das Entfernen können Apps die Gamepad-APIs jetzt direkt verwenden und haben Zugriff auf den gesamten Satz von Steuerelementen und können für weitere Arbeiten entwickelt werden. Entwickler sollten die Gamepad-APIs verwenden, um Gamepad-Eingaben zu nutzen. Hier ist ein Beispiel für [gamepad Class (Windows. Gaming.Input) – Windows UWP-Anwendungen .](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true)
- Es wurde [eine API für zugewiesenen Zugriff](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true) aktiviert, damit Apps jetzt ermitteln können, ob ein HoloLens im Kioskmodus für den benutzer angemeldeten Benutzer ausgeführt HoloLens.

#### <a name="for-enterprise"></a>Informationen Enterprise

- Behandelt Probleme im Zusammenhang mit der Berichterstellung von Konformitätseigenschaften HoloLens Geräten. Möglicherweise ist ein Neustart erforderlich, damit die richtige Berichterstellung für Insider-Builds ausgelöst wird.  
- Die In-Box-Version von Remote Assist aktualisiert, die auf neuen Flashs installiert ist.
- Es wurde ein Problem behoben, bei dem oobe nach der ersten Benutzer-Anmeldung in Szenarien beendet wurde, in denen AAD gruppenbasierte Kioskkonfigurationen verwendet wurden.
- Es wurde ein Problem mit der Anzeige von Updatebenachrichtigungen und Dialogaufforderungen für den Geräteneustart behoben.
- Es wurde ein Problem behoben, bei dem Xbox Controller und andere Bluetooth LE-Peripheriegeräte nach dem Neustart des Geräts erneut gekoppelt werden mussten, um eine Verbindung herzustellen.
- Ein Videoencoder-Problem wurde behoben, das zu einem kurzen Einfrieren des ausgehenden Videos während eines Remote Assist konnte. Wi-Fi treiber- und firmware-Änderungen, um "Fragment and Forge"-Sicherheitsrisiken Wi-Fi beheben.
- Wi-Fi treiber- und firmware-Änderungen, um "Fragment and Forge"-Sicherheitsrisiken Wi-Fi beheben.
- Bei Verwendung des MpM (Moving Platform Mode) wird "Down" durch die durchschnittliche Schwerkraft in kurzer Zeit geschätzt. Dieser Wert ersetzt echte Schwerkraft beim Verschieben des Plattformmodus.
- Regelmäßiges Wabbeln in Hologrammen im 3DoF-Modus oder während des Verlusts der Nachverfolgung wurde behoben.
- Behebt ein Problem, das sich auf Updates des Release 21H1/21H2 aus älteren Versionen auswirken kann.

## <a name="windows-holographic-version-20h2---october-2021-update"></a>Windows Holographic, Version 20H2 – Update vom Oktober 2021

- Build 19041.1168

Verbesserungen und Fehlerbehebungen im Update:

- Dieses monatliche Qualitätsupdate enthält keine wichtigsten Änderungen. Wir empfehlen Ihnen, unseren neuesten Build, Windows Holographic, Version 21H2, auszuprobieren.

## <a name="windows-holographic-version-21h1---september-2021-update"></a>Windows Holographic, Version 21H1 – Update vom September 2021

- Build 20348.1018

Verbesserungen und Fehlerbehebungen im Update:

- Korrekturen zur Behebung von Problemen, bei denen die Systemzeit unerwartet springen kann.

## <a name="windows-holographic-version-20h2---september-2021-update"></a>Windows Holographic, Version 20H2 – Update vom September 2021

- Build 19041.1165

Verbesserungen und Fehlerbehebungen im Update:

- Korrekturen zur Behebung von Problemen, bei denen die Systemzeit unerwartet springen kann.

## <a name="windows-holographic-version-21h1---august-2021-update"></a>Windows Holographic, Version 21H1 – Update vom August 2021

- Build 20348.1014

Verbesserungen und Fehlerbehebungen im Update:

- Es wurde ein Problem behoben, durch das Xbox-Controller daran gehindert wurden, in immersiven Anwendungen mit Controllerunterstützung zu arbeiten.
- Verbesserte Diagnose für Geräteupdatefehler.

## <a name="windows-holographic-version-20h2---august-2021-update"></a>Windows Holographic, Version 20H2 – Update vom August 2021

- Build 19041.1161

Verbesserungen und Fehlerbehebungen im Update:

- Dieses monatliche Qualitätsupdate enthält keine wichtigsten Änderungen. Wir empfehlen Ihnen, unseren neuesten Build, Windows Holographic, Version 21H1, auszuprobieren.

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows Holographic, Version 21H1 – Update vom Juli 2021

- Build 20348.1010

Verbesserungen und Fehlerbehebungen im Update:

- Geräteportal verfügt über erweiterte Methoden, um den Kunden zu benachrichtigen, wenn beim Öffnen gesperrter Dateien Probleme mit dem Datei-Explorer auftreten.
- Das Hochladen, Herunterladen, Umbenennen und Löschen von Dateien ist jetzt behoben, wenn https in allen unterstützten Browsern verwendet wird.
- Ein Problem wurde behobenWi-Fi bei dem der Wi-Fi-Proxy nicht gespeichert werden kann, wenn die Wi-Fi-Eigenschaften-Benutzeroberfläche von Einstellungen > Network & Internet > Status > **Properties gestartet wurde.**
- Es wurde ein Problem mit dem Entfernen von eSIM-Zertifikaten über Betriebssystemupdates hinweg behoben. Durch diese Korrektur wird sichergestellt, dass die eSIM-Zertifikate und die zugehörigen Komponenten beim Aktualisieren auf das Release 21H1 entfernt werden.
- Es wurde ein Problem behoben, das sich auf vorinstallierte Apps bei Betriebssystemzurücksetzungen ausdrückte.
- Akkuladeleistung optimiert, um die Laufzeit beim Laden mit erhöhter CPU-Auslastung zu erhöhen. Wenn beim HoloLens 2 Geräte erkannt wird, dass das Gerät heiß ist, wird der interne Akku langsamer geladen, um die Wärme zu reduzieren. Der positive Kompromiss besteht in der geringeren Wahrscheinlichkeit, dass ein Gerät aufgrund von wärmeren Problemen heruntergefahren wird, mit der Auswirkung, dass das Gerät länger ausgeführt wird. Wenn das Gerät kalt ausgeführt wird, ist die Gebührenrate nicht betroffen.

> [!IMPORTANT]
> Aufgrund eines nun behobenen bekannten Problems in unserem [21H1-Build,](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)das sich auf Remote Assist-Benutzer ausdrängte, haben wir das Angebot von updates von Windows Holographic, Version 21H1, temporal angehalten. Wir haben auch den Standardmäßigen Arc-Build (Advanced Recovery Companion) in den Windows [Holographic, Version 20H2 – Update juni 2021 geändert.](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update) Der ARC-Build wird nun für den 21H1-Build fortgesetzt.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows Holographic, Version 20H2 – Update vom Juli 2021

- Build 19041.1157

Verbesserungen und Fehlerbehebungen im Update:

- Geräteportal verfügt über erweiterte Methoden, um den Kunden zu benachrichtigen, wenn beim Öffnen gesperrter Dateien Probleme mit dem Datei-Explorer auftreten.
- Das Hochladen, Herunterladen, Umbenennen und Löschen von Dateien ist jetzt behoben, wenn https in allen unterstützten Browsern verwendet wird.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, Version 21H1 – Update juni 2021

- Build 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive für den Upload der Kamerarolle für Arbeit oder Schule

Wir haben der HoloLens 2 Einstellungen-App ein neues Feature hinzugefügt, mit dem Kunden automatisch Mixed Reality-Fotos und -Videos aus dem Ordner Pictures > Camera Roll des Geräts in den entsprechenden OneDrive for Work- oder School-Ordner hochladen können. Dieses Feature behebt eine Featurelücke innerhalb der [OneDrive-App](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) auf HoloLens 2, die nur den automatischen Upload der Kamerarolle in die persönliche Microsoft-Konto eines Kunden (und nicht in dessen Arbeits-, Schul- oder Schulkonto) unterstützt.

**So funktioniert's**

- Besuchen **Einstellungen > System > Mixed Reality-Kamera, um** "Kameraupload" zu aktivieren.
- Wenn Sie dieses  Feature auf Die Position Ein festlegen, werden alle Mixed Reality-Fotos oder Videos, die auf Ihrem Gerät erfasst werden, automatisch in die Warteschlange eingereiht, um sie in den Ordner Pictures > Camera Roll Ihres OneDrive for Work- oder School-Kontos hochzuladen.
    >[!NOTE]
    >Fotos und Videos, die vor der Aktivierung  dieses Features erfasst wurden, werden nicht für den Upload in die Warteschlange eingereiht und müssen weiterhin manuell hochgeladen werden.
- In einer Statusmeldung auf der Einstellungen-Seite wird die Anzahl der Dateien angezeigt, deren Upload aussteht (oder "OneDrive ist auf dem neuesten Stand", wenn alle ausstehenden Dateien hochgeladen wurden).
- Wenn Sie Sich um Bandbreite sorgen oder den Upload aus irgendeinem Grund "anhalten" möchten, können Sie das Feature auf die **Position Aus** umschalten. Durch das vorübergehende Deaktivieren des Features wird sichergestellt, dass die Uploadwarteschlange weiter erhöht wird, wenn Sie dem Ordner Camera Roll neue Dateien hinzufügen. Dateien werden jedoch erst hochgeladen, wenn Sie das Feature erneut aktivieren.
- Die neuesten Dateien werden zuerst hochgeladen (last in, first out).
- Wenn Ihr OneDrive-Konto Probleme hat (z. B.  nach änderungen ihres Kennworts), wird auf der Seite "Jetzt korrigieren" Einstellungen angezeigt.
- Es gibt keine maximale Dateigröße, aber beachten Sie, dass das Hochladen großer Dateien länger dauert (insbesondere, wenn die Uploadbandbreite eingeschränkt ist). Wenn Sie den Upload "anhalten" oder deaktivieren, während eine große Datei hochgeladen wird, wird der Teilupload beibehalten. Wenn der Upload innerhalb weniger Stunden nach dem "Anhalten" oder Deaktivieren erneut aktiviert wird, wird der Upload an der Stelle fortgesetzt, an der er unterbrochen wurde. Wenn der Upload jedoch nach mehreren Stunden erneut aktiviert wird, wird der Upload der großen Datei von Anfang an neu gestartet.

**Bekannte Probleme und Einschränkungen**

- Diese Einstellung verfügt nicht über eine integrierte Drosselung basierend auf der aktuellen Bandbreitennutzung. Wenn Sie die Bandbreite für ein anderes Szenario maximieren müssen, deaktivieren Sie die Einstellung manuell. Hochladen wird angehalten, aber das Feature überwacht weiterhin neu hinzugefügte Dateien für Camera Roll. Aktivieren Sie den Upload erneut, wenn Sie bereit sind, ihn fortzufahren.
- Dieses Feature muss für jedes Benutzerkonto auf dem Gerät aktiviert sein und kann nur aktiv Dateien für den Benutzer hochladen, der derzeit auf dem Gerät angemeldet ist.
- Wenn Sie Fotos oder Videos aufnehmen, während Sie die Uploadanzahl auf der Einstellungen-Seite in Echtzeit ansehen, beachten Sie, dass sich die Anzahl der ausstehenden Dateien möglicherweise nicht ändert, bis der Upload der aktuellen Datei abgeschlossen ist.
- Hochladen wird angehalten, wenn Ihr Gerät in den Ein- oder Ausgeschaltet ist. Um sicherzustellen, dass ihre ausstehenden Uploads abgeschlossen sind, verwenden Sie das Gerät aktiv, bis auf der Einstellungen-Seite "OneDrive ist auf dem neuesten Stand" angezeigt wird, oder passen Sie Ihre Power &-Einstellungen für den **Ruhezustand** an.

### <a name="added-support-for-some-telemetry-policies"></a>Unterstützung für einige Telemetrierichtlinien hinzugefügt

Die folgenden Telemetrierichtlinien werden jetzt auf dem HoloLens 2:

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry und System\ConfigureTelemetryOptInSettingsUx sollten zusammen verwendet werden, um die vollständige Kontrolle über die Telemetrie und das Verhalten in der Einstellungen zu haben.

Verbesserungen und Fehlerbehebungen im Update:

- Korrektur größerer Videobeschädigungen mit Farb kalibrierung.
- Es wird ein Problem behoben, bei dem Text im Menü Energie abgeschnitten werden kann.
- Aktiviert die Unterstützung für die RequirePrivateStoreOnly-Richtlinie.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holographic, Version 20H2 – Update juni 2021

- Build 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>Unterstützung für einige Telemetrierichtlinien hinzugefügt

Die folgenden Telemetrierichtlinien werden jetzt auf dem HoloLens 2:

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry und System\ConfigureTelemetryOptInSettingsUx sollten zusammen verwendet werden, um die vollständige Kontrolle über die Telemetrie und das Verhalten in der Einstellungen zu haben.

Wir empfehlen Ihnen, unseren neuesten Build, Windows Holographic, Version 21H1, auszuprobieren.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic, Version 1903 – Update juni 2021

- Build 18362.1116

Verbesserungen und Fehlerbehebungen im Update:

- Dieses monatliche Qualitätsupdate enthält keine wichtigsten Änderungen. Wir empfehlen Ihnen, unseren neuesten Build, Windows Holographic, Version 21H1, auszuprobieren.

>[!IMPORTANT]
> Dieser Build wird nicht mehr verwendet.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, Version 21H1

- Build 20346.1002

Dieses Update enthält Features für zwei Zielgruppen: -Funktionen, die von jedem Benutzer auf einem Gerät verwendet werden können, sowie neue Geräteverwaltungsoptionen, die von IT-Administratoren konfiguriert werden können. In der folgenden Tabelle sind die Features angegeben, die für die einzelnen Zielgruppen relevant sind. Wenn Sie IT-Administrator sind, sehen Sie sich unsere [Checkliste für IT-Administratoren – Update an.](#it-admin---update-checklist)
>[!IMPORTANT]
>Um auf diesen Build zu aktualisieren, müssen HoloLens 2-Geräte derzeit das Update vom Februar 2021 (Build 19041.1136) oder neuer ausführen. Wenn dieses Featureupdate nicht verfügbar ist, aktualisieren Sie zuerst Ihr Gerät, und versuchen Sie es erneut.

>[!NOTE]
>Derzeit unterstützt Microsoft HoloLens 2 monatliche Wartungsupdates (Fehler- und Sicherheitskorrekturen) für die folgenden Releases:
>
>- Windows Holographic, Version 20H2 (Build 19041.1128+)
>- Windows Holographic, Version 2004 (Build 19041.1103+)
>- Windows Holographic, Version 1903 (Build 18362+)
>
> Mit der Einführung Windows Holographic Version 21H1 werden monatliche Wartungsupdates für Windows Holographic Version **1903 eingestellt.** Dies ermöglicht es uns, uns auf neuere Releases zu konzentrieren und weiterhin wertvolle Verbesserungen zu erzielen.

| Funktionsname                                              | Kurze Beschreibung                                                                      | Zielgruppe |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Der neue Microsoft Edge](#introducing-the-new-microsoft-edge)  | Die neue, Chromium-basierte Microsoft Edge ist jetzt für HoloLens 2. | Endbenutzer |
[WebXR und 360 Viewer](#webxr-and-360-viewer) | Probieren Sie immersive Weberfahrungen und die Wiedergabe von 360 Videos aus. | Endbenutzer |
[Neue Einstellungen-App](#new-settings-app) | Die Legacy-Einstellungen-App wird durch eine aktualisierte Version mit neuen Features und Einstellungen ersetzt. | Endbenutzer |
[Anzeigen der Farb kalibrierung](#display-color-calibration) | Wählen Sie ein alternatives Farbprofil für Ihre HoloLens 2 Anzeigen aus. | Endbenutzer |
[Standard-App-Auswahl](#default-app-picker) | Wählen Sie aus, welche App für jede Datei oder jeden Linktyp gestartet werden soll. | Endbenutzer |
[App-bezogene Lautstärkeregelung](#per-app-volume-control) | Steuern Sie das Volume auf App-Ebene unabhängig vom Systemvolumen. | Endbenutzer |
[Installieren von Web-Apps](#install-web-apps) | Installieren Sie Web-Apps auf HoloLens 2- wie Microsoft Office mit dem neuen Microsoft Edge Browser. | Endbenutzer |
[Wischen zum Tippen](#swipe-to-type) | Verwenden Sie die Fingerspitze, um Wörter auf der holografischen Tastatur zu "wischen". | Endbenutzer |
[Menü „Stromversorgung“ im Startmenü](#power-menu-from-start) | Starten Sie das Gerät im Startmenü neu, und fahren HoloLens herunter. | Endbenutzer |
[Mehrere Benutzer, die auf dem Anmeldebildschirm aufgeführt sind](#multiple-users-listed-on-sign-in-screen) | Zeigen Sie mehrere Benutzerkonten auf dem Anmeldebildschirm an. | Endbenutzer |
[Unterstützung externer USB-C-Mikrofone](#usb-c-external-microphone-support) | Verwenden Sie USB-C-Mikrofone für Apps und/oder Remote Assist. | Endbenutzer |
[Automatische Anmeldung von Besucher für Kioske](#visitor-auto-logon-for-kiosks) | Aktiviert die automatische Anmeldung bei Besucherkonten, die für Kioskmodi verwendet werden sollen. | IT-Administrator |
[Neue AUMIDs für neue Apps im Kioskmodus](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMIDs für neue Einstellungen und Edge-Apps. | IT-Administrator |
[Verbesserte Übergabe von Fehlern im Kioskmodus](#kiosk-mode-behavior-changes-for-handling-of-failures) | Im Kioskmodus wird vor dem leeren Startmenü nach Global Assigned Access (Globaler zugewiesener Zugriff) sucht. | IT-Administrator |
[New SettingsURIs for Page Einstellungen Visibility (Neue EinstellungenURIs für Einstellungen Sichtbarkeit)](#new-settings-uris-for-page-settings-visibility) | Über 20 neue SettingsURIs für Einstellungen/PageVisibilityList-Richtlinie. | IT-Administrator |
[Konfigurieren der Fallbackdiagnose](#configuring-fallback-diagnostics-via-settings-app) | Festlegen des Fallbackdiagnoseverhaltens in Einstellungen App. | IT-Administrator |
[Freigeben von Geräten in der Nähe](#share-things-with-nearby-devices) | Freigeben von Dateien oder URLs von einem HoloLens auf einem PC. | Alle |
[Neue Diagnoseverfolgungen für das Betriebssystem](#new-os-diagnostic-traces) | Neue Problembehandlung in Einstellungen Betriebssystemupdates. | IT-Administrator |
[Übermittlungsoptimierung (Vorschau)](#delivery-optimization-preview) | Reduzieren Sie den Bandbreitenverbrauch für Downloads von HoloLens Geräten. | IT-Administrator |

Sehen Sie sich die zugehörigen Versionshinweise an:

- [Besuchen Sie das HoloLens Emulator-Archiv.](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365-Leitfäden](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Vorstellung des neuen Microsoft Edge

![Animation des Logos der Vorgängerversion von Microsoft Edge zum neuen Microsoft Edge-Logo.](images/new-edge.gif)

Der neue Microsoft Edge [greift auf das Open-Source-Projekt Chromium zurück](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/), um für Kunden mehr Kompatibilität und für Webentwickler weniger Fragmentierung des Webs zu ermöglichen.

> [!IMPORTANT]
> Diese neue Microsoft Edge-Version ersetzt automatisch die Vorgängerversion von Microsoft Edge, die in neuen Releases [nicht mehr unterstützt](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) wird.

![Screenshot des neuen Microsoft Edge.](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Einführung des neuen Microsoft Edge

Der neue Microsoft Edge ![Symbol des neuen Microsoft Edge.](images/new_edge_logo.png) (dargestellt durch ein blaugrünes Wirbelsymbol) wird an das Startmenü angeheftet und automatisch gestartet, wenn Sie einen Weblink aktivieren.

> [!NOTE]
> Wenn Sie den neuen Microsoft Edge erstmals auf der HoloLens 2 starten, werden Ihre Einstellungen und Daten aus der Vorgängerversion von Microsoft Edge importiert. Wenn Sie legacy-Microsoft Edge nach dem Start des neuen Microsoft Edge weiterhin verwenden, werden diese neuen Daten nicht von legacy Microsoft Edge mit dem neuen Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Konfigurieren von Richtlinieneinstellungen für den neuen Microsoft Edge

Der neue Microsoft Edge bietet IT-Administratoren auf der HoloLens 2 eine wesentlich breitere Palette an Richtlinien für den Browser als in der Vorgängerversion möglich war.

Hier finden Sie einige hilfreiche Ressourcen, um mehr über die Verwaltung von Richtlinieneinstellungen für den neuen Microsoft Edge zu erfahren:

- [Konfigurieren von Microsoft Edge-Richtlinieneinstellungen mit Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Richtlinienzuordnung zwischen Vorgänger- und neuer Version von Microsoft Edge](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Richtlinienzuordnung zwischen Google Chrome und Microsoft Edge](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Vollständige [Microsoft Edge Enterprise-Dokumentation](/deployedge/)

> [!IMPORTANT]
> Aufgrund des Umfangs der Browserrichtlinien, die vom neuen Microsoft Edge unterstützt werden, kann unser Team nicht garantieren, dass jede neue Richtlinie auf der HoloLens 2 funktioniert. Wir haben jedoch getestet und bestätigt, dass die neue Microsoft Edge-Entsprechung jeder Richtlinie in der Vorgängerversion von Microsoft Edge, die zuvor auf HoloLens 2 unterstützt wurde, wie erwartet funktioniert. Unter [Richtlinienzuordnung zwischen Vorgänger- und neuer Version von Microsoft Edge](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) finden Sie die neue Microsoft Edge-Entsprechung jeder Browserrichtlinie in der Vorgängerversion, die Sie mit HoloLens 2 verwendet haben.
>
> Es gibt mindestens zwei neue Microsoft Edge-Richtlinien, von denen wir wissen, dass sie *nicht* mit HoloLens 2 funktionieren:
>
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Was Sie vom neuen Microsoft Edge auf der HoloLens 2 erwarten können

Da es sich beim neuen Microsoft Edge um eine native Win32-App mit neuer UWP-Adapterschicht handelt, die es ermöglicht, auf reinen UWP-Geräten wie der HoloLens 2 ausgeführt zu werden, sind einige Features möglicherweise nicht sofort verfügbar. In den kommenden Monaten werden wir neue Szenarien und Features unterstützen, weshalb Sie an dieser Stelle stets aktuelle Informationen finden.

**Szenarien und Features, die voraussichtlich nicht funktionieren:**

- Erfahrung bei der ersten Inbetriebnahme, Anmeldung am Profil und Synchronisierung
- Das Rendering und Verhalten von Websites sollte wie erwartet sein
- Die meisten Browserfunktionen (Favoriten, Verlauf usw.) sollten wie erwartet funktionieren
- Dunkler Modus
- Installieren von Web-Apps auf dem Gerät
- Installieren von Erweiterungen (teilen Sie uns mit, wenn Sie Erweiterungen verwenden, die auf der HoloLens 2 nicht ordnungsgemäß funktionieren)
- Anzeige und Markup einer PDF-Datei
- Raumklang aus einem einzelnen Browserfenster
- Automatische und manuelle Aktualisierung des Browsers
- Speichern einer PDF-Datei im Menü „Drucken“ (mit der Option „In PDF-Datei speichern“)
- WebXR- und 360 Viewer-Erweiterung
- Inhaltswiederherstellung in richtigem Fenster beim Durchsuchen mehrerer in Ihrer Umgebung platzierter Fenster

**Szenarien und Features, die voraussichtlich nicht funktionieren:**

- Raumklang aus mehreren Fenstern mit gleichzeitigen Audiostreams
- „Sehen, sagen“
- Drucken

**Bekannte Probleme im Browser:**

- Die Bildschirmlupenvorschau auf der holografischen Tastatur wurde für den neuen Microsoft Edge deaktiviert. Wir hoffen, dieses Feature in einem künftigen Update wieder aktivieren zu können, sobald die Vergrößerung ordnungsgemäß funktioniert.
- Audio wird möglicherweise im falschen Browserfenster wiedergegeben, wenn ein anderes Browserfenster geöffnet und aktiv ist. Sie können dieses Problem umgehen, indem Sie das andere aktive Fenster schließen, das kein Audio wiedergeben soll.
- Wenn Sie Audiodaten aus einem Browserfenster im [Modus "Follow me"](hololens2-basic-usage.md#follow-me-stop-following)wieder geben, wird die Audiowiedergabe fortgesetzt, wenn Sie den Modus "Follow me" deaktivieren. Sie können dieses Problem beheben, indem Sie die Audiowiedergabe beenden, bevor Sie den Modus "Follow me" deaktivieren, oder indem Sie das Fenster mit der **Schaltfläche X** schließen.
- Die Interaktion mit aktiven Microsoft Edge-Fenstern kann dazu führen, dass andere 2D-App-Fenster unerwartet inaktiv werden. Sie können diese Fenster reaktivieren, indem Sie erneut mit ihnen interagieren.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider-Kanäle

Das Microsoft Edge-Team stellt der Edge Insider-Community drei Vorschaukanäle zur Verfügung: Beta, Dev und Canary. Wenn Sie einen Vorschaukanal installieren, wird die veröffentlichte Version von Microsoft Edge nicht von Ihrer HoloLens 2 deinstalliert. Zudem können Sie mehrere gleichzeitig installieren.

Besuchen Sie die [Homepage von Microsoft Edge Insider](https://www.microsoftedgeinsider.com), um mehr über die Edge Insider-Community zu erfahren. Weitere Informationen zu den verschiedenen Edge Insider-Kanälen und den ersten Schritte finden Sie auf der [Downloadseite für Edge Insider](https://www.microsoftedgeinsider.com/download).

Es gibt mehrere Methoden zum Installieren von Microsoft Edge Insider-Kanälen für HoloLens 2:

**Direkte Installation auf dem Gerät (derzeit nur für nicht verwaltete Geräte möglich)**

  1. Besuchen Sie auf Ihrer HoloLens 2 die [Downloadseite von Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Wählen Sie die Schaltfläche **Download for HoloLens 2** für den Edge Insider-Kanal aus, den Sie installieren möchten.
  1. Rufen Sie die heruntergeladene MSIX-Datei in der Edge-Downloadwarteschlange oder im Ordner „Downloads“ Ihres Geräts (mithilfe von Datei-Explorer) auf.
  1. Das [App-Installationsprogramm](app-deploy-app-installer.md) wird gestartet.
  1. Wählen Sie die Schaltfläche **Installieren** aus.
  1. Nach erfolgreicher Installation finden Sie im Startmenü in der Liste **Alle Apps** Microsoft Edge Beta, Dev oder Canary als separaten Eintrag.

**Installation über PC mit Windows-Geräteportal (erfordert, dass der [Entwicklermodus](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) auf der HoloLens 2 aktiviert ist)**

  1. Besuchen Sie auf Ihrem PC die [Downloadseite von Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Wählen Sie die **Dropdownpfeilschaltfläche** neben der Schaltfläche „Download for Windows 10“ für den Edge Insider-Kanal aus, den Sie installieren möchten.
  1. Wählen Sie im Dropdownmenü **HoloLens 2** aus.
  1. Speichern Sie die MSIX-Datei im Ordner „Downloads“ Ihres PCs (oder in einem anderen einfach zugänglichen Ordner).
  1. Verwenden Sie das [Windows-Geräteportal](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) auf Ihrem PC, um die heruntergeladene MSIX-Datei auf HoloLens 2 zu installieren.
  1. Nach erfolgreicher Installation finden Sie im Startmenü in der Liste **Alle Apps** Microsoft Edge Beta, Dev oder Canary als separaten Eintrag.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Blockieren des neuen Microsoft Edge mit WDAC

IT-Administratoren, die ihre [WDAC-Richtlinie](windows-defender-application-control-wdac.md) so aktualisieren möchten, dass die neue Microsoft Edge-App blockiert wird, müssen ihrer Richtlinie Folgendes hinzufügen.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Verwalten von Endpunkten für den neuen Microsoft Edge

In einigen Umgebungen gelten möglicherweise Netzwerkeinschränkungen, die berücksichtigt werden müssen. Um eine reibungslose Erfahrung mit dem neuen Edge zu gewährleisten, [aktivieren Sie diese Microsoft-Endpunkte](/deployedge/microsoft-edge-security-endpoints).

Erfahren Sie mehr über die derzeit [verfügbaren Endpunkte für HoloLens](hololens-offline.md).

### <a name="install-web-apps"></a>Installieren von Web-Apps

 > [!Note]
>Ab der [Windows Holographic-Version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ist die Web-App „Microsoft Office“ nicht mehr vorinstalliert.

Sie können den neuen Edge verwenden, um Web-Apps neben Microsoft Store-Apps zu installieren. Beispielsweise können Sie die Microsoft Office-Web-App installieren, um Dateien anzuzeigen und zu bearbeiten, die in SharePoint oder auf OneDrive gehostet werden. Um die Office-Web-App zu installieren, besuchen Sie https://www.office.com. Wählen Sie auf der Adressleiste die Schaltfläche **App verfügbar** oder **Office installieren** aus. Wählen Sie zum Bestätigen **Installieren** aus.

> [!IMPORTANT]
> Office-Web-App-Funktionalität ist nur verfügbar, wenn Ihre HoloLens 2 über eine aktive Internetverbindung verfügt.

### <a name="webxr-and-360-viewer"></a>WebXR und 360 Viewer

Der neue Microsoft Edge unterstützt WebXR, den neuen Standard zum Schaffen immersiver Weberfahrungen (der WebVR ersetzt). Viele immersive Weberfahrungen wurden unter Berücksichtigung von VR entworfen (sie ersetzen Ihr Sichtfeld durch eine virtuelle Umgebung), aber diese Erfahrungen werden auch von der HoloLens 2 unterstützt. Der WebXR-Standard ermöglicht auch immersive Weberfahrungen mittels Augmented und Mixed Reality, die Ihre physische Umgebung nutzen. Je mehr Zeit Entwickler für WebXR aufwenden, desto mehr erwarten wir neue Augmented und Mixed-Reality-Erfahrungen, die HoloLens 2-Kunden ausprobieren können!

Die 360 Viewer-Erweiterung basiert auf WebXR und wird automatisch zusammen mit dem neuen Microsoft Edge auf der HoloLens 2 installiert. Diese Weberweiterung gibt Ihnen die Möglichkeit, in 360-Grad-Videos einzutauchen. YouTube bietet die größte Auswahl an 360-Grad-Videos, weshalb wir Ihnen empfehlen, dort zu beginnen.

#### <a name="how-to-use-webxr"></a>Verwendung von WebXR

1. Navigieren Sie zu einer Website mit WebXR-Unterstützung.
1. Wählen Sie auf der Website die Schaltfläche **In VR ansehen** aus. Die Position und visuelle Darstellung dieser Schaltfläche kann je nach Website variieren, sieht aber in etwa so aus:

    ![Beispiel der Schaltfläche „In VR ansehen“.](images/75px-enter-vr.png)

1. Wenn Sie zum ersten Mal versuchen, eine WebXR-Umgebung in einer bestimmten Domäne zu starten, bittet der Browser um Zustimmung zum Aufrufen einer immersiven Ansicht. Wählen Sie **Zulassen** aus.
1. Verwenden Sie [HoloLens 2-Gesten](hololens2-basic-usage.md#the-hand-tracking-frame), um sich in der Umgebung zu bewegen.
1. Wenn die Umgebung nicht über die Schaltfläche **Beenden** verfügt, kehren Sie mit der [Startgeste](hololens2-basic-usage.md#start-gesture) zur Startseite zurück.

**Empfohlene WebXR-Beispiele**

- 360 Viewer (siehe den nächsten Abschnitt)
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Verwenden von 360 Viewer

1. Navigieren Sie auf YouTube zu einem 360-Grad-Video.
1. Wählen Sie im Videoframe die Schaltfläche mit dem Mixed Reality-Headset aus:

    ![Schaltfläche zum Aktivieren von 360 Viewer.](images/enter-360-viewer.jpg)

1. Wenn Sie zum ersten Mal versuchen, 360 Viewer in einer bestimmten Domäne zu starten, bittet der Browser um Zustimmung zum Aufrufen einer immersiven Ansicht. Wählen Sie **Zulassen** aus.
1. [Tippen Sie in die Luft](hololens2-basic-usage.md#select-using-air-tap), um die Wiedergabesteuerelemente zu aktivieren. Per [Handstrahl und Tippen in die Luft](hololens2-basic-usage.md#select-using-air-tap) können Sie die Wiedergabe starten/anhalten, vor- und zurückspringen, Untertitel ein-/ausschalten oder die Umgebung beenden (wodurch die immersive Ansicht beendet wird). Die Wiedergabesteuerelemente werden nach einigen Sekunden Inaktivität nicht mehr angezeigt.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Bekannte Probleme mit WebXR und 360 Viewer

- Je nach Komplexität des WebXR-Erlebnisses kann die Framerate abfallen oder ruckeln.
- Die Unterstützung beweglicher Handgelenke in WebXR ist standardmäßig nicht aktiviert. Entwickler können die Unterstützung über `edge://flags` aktivieren, indem sie "WebXR Hand Input" aktivieren.
- 360-Grad-Videos von anderen Websites als YouTube funktionieren möglicherweise nicht wie erwartet.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Senden von Feedback zu WebXR und 360 Viewer

Teilen Sie Feedback und Fehler über das Feature **Feedback senden** im neuen Microsoft Edge mit unserem Team.

### <a name="new-settings-app"></a>Neue Einstellungen-App

Mit diesem Release führen wir eine neue Version der App Einstellungen ein. Die neue Einstellungen-App enthält neue Funktionen und erweiterte Einstellungen für HoloLens 2 in den folgenden Bereichen: Sound, Energie & Ruhezustand, Netzwerk & Internet, Apps, Konten, Erleichterte Bedienung und mehr.

> [!NOTE]
> Da sich die neue Einstellungen-App von der Legacy-Einstellungen-App unterscheidet, werden alle Fenster mit Einstellungen, die Sie zuvor in Ihrer Umgebung platziert haben, nach dem Update entfernt.

![Startseite mit der „Neue Einstellungen“-App.](images/new-settings-app.png)

**Neue Funktionen und Einstellungen**

- Suchen von Einstellungen: Suchen Sie auf der Startseite der Einstellungen nach Einstellungen, indem Sie Schlüsselwörter oder den Namen der Einstellung verwenden.
- System > Sound:
  - Eingabe- und Ausgabeaudiogeräte: Wählen Sie unabhängig Ihre Eingabe- und Ausgabeaudiogeräte aus (z B. hören Sie Audios über Bluetooth Kopfhörer an oder verwenden Sie ein USB-C-Mikrofon für die Audioeingabe).
    > [!NOTE]
    > Bluetooth-Mikrofone werden von HoloLens 2 nicht unterstützt.
  - App-Lautstärke: Passen Sie die Lautstärke der einzelnen Apps unabhängig an. Weitere Informationen finden Sie unter[ Lautstärkesteuerung per App](#per-app-volume-control).
- System > Energie & Ruhezustand: Legen Sie fest, wann das Gerät nach einer gewissen Zeit der Inaktivität in den Ruhezustand übergehen soll.
- System > Akku: Aktivieren Sie manuell den Stromsparmodus Modus, oder legen Sie einen Akkuschwellenwert fest, an dem Stromsparmodus Modus automatisch eingeschaltet wird.
- Geräte > USB: Sie können USB-Verbindungen standardmäßig deaktivieren.
- Netzwerk & Internet:
  - USB-C-Ethernet-Adapter werden jetzt in Netzwerk & Internet angezeigt.
  - USB-C Ethernet-Adaptereinstellungen sind jetzt verfügbar, einschließlich der IP-Adresse.
  - Sie können jetzt den Flugzeugmodus auf HoloLens 2 aktivieren.
- Apps: Sie können die Standard-Apps, die für Datei- und Linktypen verwendet werden, zurücksetzen. Weitere Informationen finden Sie unter [Standardapp-Auswahl](#default-app-picker).
- Konten > Andere Benutzer: Gerätebesitzer können Benutzer hinzufügen, Standardbenutzer auf Gerätebesitzer höherstufen, Gerätebesitzer auf Standardbenutzer herabstufen und Benutzer entfernen.
- Erleichterte Bedienung: Ändern der Textgröße und einiger visueller Effekte.

**Bekannte Probleme**

- Fenster mit zuvor platzierten Einstellungen werden entfernt (siehe Hinweis oben).
- Sie können Ihr Gerät nicht mehr mit der Einstellungen-App umbenennen. IT-Administratoren können Geräte umbenennen, indem sie die [Windows Autopilot für HoloLens 2](hololens2-autopilot.md)-Vorlage für Gerätenamen oder den MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName Knoten verwenden.
- Auf der Seite „Ethernet“ wird jederzeit ein virtuelles Ethernet-Gerät („UsbNcm“) angezeigt.
- Der Akkuverbrauch für den neuen Microsoft Edge ist aufgrund seiner Art als Win32-Desktopanwendung, die von einer UWP-Adapterebene unterstützt wird, möglicherweise nicht korrekt (es wird in Kürze keine Korrektur erwartet).

#### <a name="display-color-calibration"></a>Anzeigen der Farb kalibrierung

Mit dieser neuen Einstellung können Sie ein alternatives Farbprofil für Ihre HoloLens 2 auswählen. Dies kann dazu beitragen, dass Farben genauer angezeigt werden, insbesondere bei niedrigeren Helligkeitsstufen im Display. Die Kalibrierung der Anzeigefarbe finden Sie in Einstellungen App auf der Seite System > Kalibrierung.

> [!NOTE]
> Da durch diese Einstellung ein neues Farbprofil in der Firmware Ihres Displays gespeichert wird, handelt es sich um eine gerätespezifische Einstellung (und nicht um eine eindeutige für jedes Benutzerkonto).

##### <a name="how-to-use-display-color-calibration"></a>Kalibrierung der Displayfarben

1. Starten Sie die App **Einstellungen**, und wechseln Sie zu **System > Kalibrierung**.
1. Wählen Sie unter **Display color calibration** (Farbkalibrierung des Displays) die Schaltfläche **Run display color calibration** (Farbkalibrierung des Displays ausführen) aus.
1. Die Oberfläche zur Farbkalibrierung des Displays wird eingeblendet und bittet Sie zu prüfen, um sich Ihr Visier in der richtigen Position befindet.
1. Nachdem Sie die Anweisungsdialogfelder durchlaufen haben, wird das Display automatisch auf eine Helligkeit von 30 % abgeblendet.
    > [!TIP]
    > Wenn Sie Probleme haben, die abgeblendete Szenerie in Ihrer Umgebung zu sehen, können Sie den Helligkeitspegel der HoloLens 2 manuell justieren, indem Sie links am Gerät auf die Tasten für Helligkeit drücken.
1. Wählen Sie die Tasten 1-6 aus, um die einzelnen Farbprofile sofort auszuprobieren und dasjenige zu finden, das in Ihren Augen am besten aussieht (dies bedeutet in der Regel das Profil, das die Szene am neutralsten erscheinen lässt, wobei die Graustufenmuster und Hautfarbtöne wie erwartet aussehen).

    ![Szenerie zur Farbkalibrierung des Displays.](images/color-cal-ui.png)

1. Wenn Sie mit dem ausgewählten Profil zufrieden sind, wählen Sie die Schaltfläche **Speichern und beenden** aus.
1. Wenn Sie keine Änderungen vornehmen möchten, wählen Sie die Schaltfläche **Abbrechen und beenden** aus, woraufhin Ihre Änderungen zurückgesetzt werden.

> [!TIP]
> Es folgen einige hilfreiche Tipps, die Sie bei der Verwendung der Einstellung zur Farbkalibrierung des Displays beachten sollten:
>
> - Sie können in „Einstellungen“ die Farbkalibrierung des Displays nach Bedarf erneut ausführen.
> - Wenn jemand auf dem Gerät zuvor die Einstellung zum Ändern von Farbprofilen verwendet hat, werden Datum und Zeit dieser letzten Änderung auf der Seite „Einstellungen“ angezeigt.
> - Wenn Sie die Farbkalibrierung des Displays erneut ausführen, wird das zuvor gespeicherte Farbprofil hervorgehoben und Profil 0 nicht angezeigt (da Profil 0 das ursprüngliche Farbprofil des Displays darstellt).
> - Wenn Sie zum ursprünglichen Farbprofil des Displays zurückkehren möchten, wechseln Sie dazu zur Seite „Einstellungen“ (weitere Informationen zum [Zurücksetzen des Farbprofils](#how-to-reset-color-profile)).

##### <a name="how-to-reset-color-profile"></a>Zurücksetzen des Farbprofils

Wenn Sie nicht mit dem benutzerdefinierten Farbprofil zufrieden sind, das in Ihrer HoloLens 2 gespeichert ist, können Sie das ursprüngliche Farbprofil des Geräts wiederherstellen:

1. Starten Sie die App **Einstellungen**, und wechseln Sie zu **System > Kalibrierung**.
1. Wählen Sie unter **Display color calibration** (Farbkalibrierung anzeigen) die Schaltfläche **Reset to default color profile** (Auf Standardfarbprofil zurücksetzen) aus.
1. Wenn das Dialogfeld geöffnet wird, wählen Sie **Neu starten** aus, wenn Sie die HoloLens 2 neu starten und Ihre Änderungen übernehmen möchten.

#### <a name="top-display-color-calibration-known-issues"></a>Bekannte Probleme bei der Farbkalibrierung des Displays

- Auf der Einstellungen Seite ist die Statuszeichenfolge, die Sie darüber informiert, wann das Farbprofil zuletzt geändert wurde, veraltet, bis Sie diese Seite der Einstellungen.
    - Problemumgehung: Wählen Sie eine andere Seite „Einstellungen“ und dann die Seite „Kalibrierung“ erneut aus.

#### <a name="default-app-picker"></a>Standard-App-Auswahl

Wenn Sie einen Link aktivieren oder einen Dateityp mit mehr als einer installierten App öffnen, die diesen unterstützt, wird ein neues Fenster geöffnet, in dem Sie aufgefordert werden, auszuwählen, welche installierte App den Datei- oder Linktyp verarbeiten soll. In diesem Fenster können Sie auch festlegen, dass die ausgewählte App die Datei oder den Linktyp „Einmal" oder „Immer“ handhabt.

Wenn Sie „Immer“ wählen, aber später ändern möchten, mit welcher App eine bestimmte Datei oder ein bestimmter Linktyp gehandhabt wird, können Sie Ihre gespeicherten Standardeinstellungen unter **Einstellungen > Apps** zurücksetzen. Scrollen Sie auf der Seite nach unten, und wählen Sie unter „Standard-Apps für Dateitypen“ und/oder „Standard-Apps für Linktypen“ die Schaltfläche **Löschen** aus. Im Gegensatz zur ähnlichen Einstellung auf Desktop-PCs können Sie die Standardeinstellungen einzelner Dateitypen nicht zurücksetzen.

#### <a name="per-app-volume-control"></a>App-bezogene Lautstärkeregelung

In diesem Windows können Benutzer nun die Volumeebene jeder App manuell anpassen. So können sich Benutzer besser auf die Apps konzentrieren, die sie benötigen, bzw. besser hören, wenn sie mehrere Apps einsetzen. Beispielsweise müssen Sie die Lautstärke einer App reduzieren, während Sie in einer anderen App eine andere Person zwecks Fernbetreuung anrufen.

Um die Lautstärke einer einzelnen App festzulegen, navigieren Sie zu **Einstellungen** > **System** > **Klang**, und wählen Sie unter „Erweiterte Klangoptionen“ **App-Lautstärke und Geräteeinstellungen** aus.<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Wischen zum Tippen

Einige Kunden finden es schneller, auf virtuellen Tastaturen zu "tippen", indem sie die Form des Worts wischen, das sie eingeben möchten, und wir zeigen diese Funktion für die holografische Tastatur in der Vorschau an. Sie können ein Wort nach dem anderen wischen, indem Sie die Fingerspitze durch die Ebene der holografischen Tastatur übergeben, die Form des Worts wischen und dann die Fingerspitze von der Tastaturebene abziehen. Sie können folgende Wörter wischen, ohne die Leertaste drücken zu müssen, indem Sie den Finger zwischen den Worten von der Tastatur nehmen. Sie wissen, dass das Feature funktioniert, wenn Sie eine Wischspur sehen, die der Bewegung Ihres Fingers auf der Tastatur folgt.

Beachten Sie, dass dieses Feature aufgrund der Natur einer holografischen Tastatur, bei der der Finger keinen Widerstand spürt (im Gegensatz zu einem Smartphone-Display), schwierig zu bedienen und zu beherrschen sein kann. 

### <a name="power-menu-from-start"></a>Menü „Stromversorgung“ im Startmenü

Ein neues Menü, über das der Benutzer sich abmelden, das Gerät herunterfahren und neu starten kann. Eine Anzeige auf dem HoloLens-Startbildschirm, die angibt, wann ein Systemupdate verfügbar ist.

#### <a name="how-to-use"></a>Verwendung

1. Öffnen Sie den HoloLens-Startbildschirm mithilfe der [Startgeste,](hololens2-basic-usage.md#start-gesture) oder sagen Sie „Zum Startmenü“.

2. Beachten Sie das Auslassungszeichen (...) neben dem Benutzerprofilbild:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Wählen Sie das Benutzerprofilbild mit Ihren Händen oder dem Sprachbefehl „Stromversorgung“ aus.

4. Ein Menü mit den Optionen „Abmelden“, „Neustarten“ oder „Gerät herunterfahren“ wird angezeigt:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Wählen Sie die Menüoptionen zum Abmelden, Neustarten oder Herunterfahren Ihrer HoloLens aus. Die Option „Abmelden“ ist möglicherweise nicht verfügbar, wenn das Gerät für ein [einzelnes Microsoft-Konto (MSA) oder ein lokales Konto](hololens-identity.md) eingerichtet ist.

6. Verlassen Sie das Menü, indem Sie eine andere Stelle berühren oder das Startmenü mit der Startgeste schließen.

#### <a name="update-indicator"></a>Aktualisierungsindikator

Wenn ein Update verfügbar ist, wird das Symbol mit den Auslassungszeichen angezeigt, um anzugeben, dass bei einem Neustart das Update installiert wird. Die Menüoptionen ändern sich ebenfalls, um das Vorhandensein des Updates widerzubilden.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Mehrere Benutzer, die auf dem Anmeldebildschirm aufgeführt sind

Zuvor wurde auf dem Bildschirm Anmelden nur der zuletzt angemeldete Benutzer sowie ein Einstiegspunkt "Anderer Benutzer" angezeigt. Wir haben Kundenfeedback erhalten, dass dies nicht ausreicht, wenn sich mehrere Benutzer beim Gerät angemeldet haben. Sie mussten weiterhin ihren Benutzernamen usw. erneut eingeben.

In diesem Windows-Build eingeführt: Wenn  Sie Auf der rechten Seite des PIN-Eingabefelds Anderer Benutzer auswählen, werden auf dem Bildschirm Anmelden mehrere Benutzer angezeigt, die sich zuvor beim Gerät angemeldet haben. Dadurch können Benutzer ihr Benutzerprofil auswählen und sich dann mit ihren Anmeldeinformationen Windows Hello anmelden. Über die Schaltfläche Konto hinzufügen kann dem Gerät auch ein neuer Benutzer über die Seite Andere **Benutzer hinzugefügt** werden.

Im Menü Andere Benutzer zeigt die Schaltfläche Andere Benutzer den letzten Benutzer an, der sich am Gerät angemeldet hat. Wählen Sie diese Schaltfläche aus, um zum Anmeldebildschirm für diesen Benutzer zurückzukehren.

![Standardeinstellung des Anmeldebildschirms.](./images/multiusers1.jpg)

<br>

![Anmeldebildschirm für andere Benutzer.](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Unterstützung externer USB-C-Mikrofone

> [!IMPORTANT]
> Wenn Sie ein **USB-Mikrofon anschließen, wird es nicht automatisch als Eingabegerät festgelegt**. Beim Einstecken einer Reihe von USB-C-Anschlüssen werden Benutzer feststellen, dass die Audiodaten des Geräts automatisch an die Anschlüsse umgeleitet werden, aber das HoloLens-Betriebssystem priorisiert das interne Mikrofonarray vor jedem anderen Eingabegerät. **Führen Sie die folgenden Schritte aus, um ein USB-C-Mikrofon zu verwenden.**

Benutzer können externe Mikrofone mit USB-C-Verbindung über das Einstellungsfeld **Sound** auswählen. USB-C-Mikrofone können zum Aufrufen, Aufzeichnen usw. verwendet werden.

Öffnen Sie die App **Einstellungen**, und wählen Sie **System** > **Sound** aus.

![Sound-Einstellungen.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Um externe Mikrofone mit **Remote Assist** verwenden zu können, müssen Benutzer auf den Link „Soundgeräte verwalten“ klicken.
>
> Verwenden Sie dann die Dropdownliste, um das externe Mikrofon entweder auf **Standard** oder **Kommunikationsstandard** zu setzen. Die Auswahl **Standard** bedeutet, dass das externe Mikrofon überall verwendet wird.
>
> Die Auswahl von **Kommunikationsstandard** bedeutet, dass das externe Mikrofon in Remote Assist und anderen Kommunikations-Apps verwendet wird, aber das HoloLens-Mikrofon-Array kann weiterhin für andere Aufgaben verwendet werden.

![Verwalten von Soundgeräten.](images/usbc-mic-2.png)

<br>

![Festlegen der Mikrofon-Standardeinstellung.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Wie sieht es mit der Unterstützung von Bluetooth Mikrofonen aus?

Leider werden Bluetooth Mikrofone auf dem HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Problembehandlung bei USB-C-Mikrofonen

Beachten Sie, dass einige USB-C-Mikrofone sich fälschlicherweise sowohl als Mikrofon als auch als *Lautsprecher* melden. Dies ist ein Problem mit dem Mikrofon und nicht mit HoloLens. Wenn Sie eines dieser Mikrofone in HoloLens, kann der Sound verloren gehen. Glücklicherweise gibt es eine einfache Lösung.  

Legen **Einstellungen** Systemsound explizit die integrierten Lautsprecher  >    >   **(Analog Feature Audio Driver)** als **Standardgerät fest.** HoloLens sollten sich diese Einstellung auch dann merken, wenn das Mikrofon entfernt und später erneut verbunden wird.

![Problembehandlung bei USB-C-Mikrofonen.](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Automatische Anmeldung von Besucher für Kioske

Mit diesem neuen Feature kann die automatische Anmeldung bei Besucherkonten für Kioskmodi verwendet werden.

Für eine konfiguration ohne AAD, um ein Gerät für die automatische Anmeldung von Besucher zu konfigurieren:

1. Erstellen Sie ein Bereitstellungspaket, das:
    1. Konfiguriert **Laufzeiteinstellungen/AssignedAccess,** um Besucherkonten zu ermöglichen.
    1. Registriert das Gerät optional bei MDM **(Laufzeiteinstellungen/Arbeitsplatz/Registrierungen),** damit es später verwaltet werden kann.
    1. Erstellen Sie kein lokales Konto.
1. [Wenden Sie das Bereitstellungspaket an.](hololens-provisioning.md)

Bei einer AAD können Benutzer ohne diese Änderung etwas ähnliches erreichen wie heute. AAD geräten, die für den Kioskmodus konfiguriert sind, können sich mit einer einzelnen Schaltfläche vom Anmeldebildschirm aus bei einem Besucherkonto anmelden. Nach der Anmeldung beim Besucherkonto fordert das Gerät erst dann erneut zur Anmeldung auf, wenn der Besucher explizit über das Startmenü abmelden oder das Gerät neu gestartet wird.

Die automatische Anmeldung von Besucher kann über eine benutzerdefinierte [OMA-URI-Richtlinie verwaltet](/mem/intune/configuration/custom-settings-windows-10) werden:

- URI-Wert: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Richtlinie  | BESCHREIBUNG   | Configurations  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Ermöglicht einem Besucher die automatische Anmeldung bei einem Kiosk   | 1 (Ja), 0 (Nein, Standard)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Verwenden der neuen Einstellungen- und Edge-Apps im Kioskmodus

Beim Hinzufügen von Apps in [Kiosks](hololens-kiosk.md)fügt ein IT-Administrator die App häufig dem Kiosk hinzu, verwendet aber die App-Benutzermodell-ID (AUMID). Da sowohl die Einstellungen-App als auch die Microsoft Edge-App als neue Apps betrachtet werden und sich von den älteren Apps unterscheiden, müssen Kiosks, die AUMIDs für diese Apps verwenden, aktualisiert werden, um die neue AUMID zu verwenden.

Wenn Sie einen Kiosk so ändern, dass er die neuen Apps enthält, empfiehlt es sich, die neue AUMID-Datei zu verwenden und die alte zu verlassen. Dies ermöglicht einen einfachen Übergang, wenn Benutzer das Betriebssystem aktualisieren und keine neuen Richtlinien erhalten müssen, um den Kiosk weiterhin wie vorgesehen zu verwenden.

| App                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Alte Einstellungen-App       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Neue Einstellungen-App       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Alte Microsoft Edge-App | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Neue Microsoft Edge-App | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Verhaltensänderungen im Kioskmodus für die Behandlung von Fehlern

Wenn ein Gerät in älteren Builds über eine Kioskkonfiguration (eine Kombination aus global zugewiesenem Zugriff und zugewiesenem Zugriff eines AAD-Gruppenmitglieds)[](hololens-kiosk.md#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode)verfehlt, wird dem Benutzer bei der Ermittlung der AAD-Gruppenmitgliedschaft im Startmenü "nichts angezeigt" angezeigt.

Ab diesem Windows Fallback auf die globale Kioskkonfiguration (falls vorhanden) bei Ausfällen während AAD Gruppenkioskmodus.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Neue Einstellungen-URIs für seitenseitige Einstellungen Sichtbarkeit

In [Windows Holographic Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) haben wir die [Richtlinie Einstellungen/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) hinzugefügt, um die Seiten einzuschränken, die in der App Einstellungen werden. Die PageVisibilityList ist eine Richtlinie, die es IT-Administratoren ermöglicht, entweder zu verhindern, dass bestimmte Seiten in der Systemeinstellungen-App sichtbar oder zugänglich sind oder Sie können das für alle Seiten tun, mit Ausnahme der angegebenen Seiten.

Wenn Sie [seite Einstellungen Sichtbarkeit](settings-uri-list.md)besuchen, finden Sie Anweisungen zur Verwendung dieses CSP und die Liste der URIs, die in früheren Versionen verfügbar waren.

Wir erweitern die Liste der verfügbaren Einstellungen URIs, die IT-Administratoren verwalten können. Einige dieser URIs gelten für neu verfügbare Bereiche innerhalb der neuen Einstellungen App. Wenn Sie die Richtlinie Einstellungen/PageVisibilityList verwenden, überprüfen Sie die folgende Liste, und passen Sie ihre zulässigen oder blockierten Seiten nach Bedarf an.

> [!NOTE]
> **Veraltet: ms-settings:network-proxy**
>
> Eine Einstellungsseite ist in diesen neueren Builds veraltet. Die alte **Seite &**  >  **Internetproxy** ist nicht mehr als globale Einstellung verfügbar. Die neuen Proxyeinstellungen pro Verbindung finden Sie unter **Netzwerk-&**  >  **Internet-WLAN-Eigenschaften** oder Netzwerk-&  >     >  **Internet-Ethernet-Eigenschaften.**  >  

<br>

| Seite "Einstellungen"                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Apps > Apps & Features                               | `ms-settings:appsfeatures`                         |
| Apps > Apps & Features > Erweiterte Optionen          | `ms-settings:appsfeatures-app`                     |
| Apps > Offlinezuordnungen                                  | `ms-settings:maps`                                 |
| Apps > Offlinezuordnungen > Herunterladen von Karten                  | `ms-settings:maps-downloadmaps`                    |
| Geräte > Maus                                      | `ms-settings:mouse`                                |
| Geräte > USB                                        | `ms-settings:usb`                                  |
| Netzwerk & Internet > Flugzeugmodus                   | `ms-settings:network-airplanemode`                 |
| Datenschutz > Allgemein                                    | `ms-settings:privacy-general`                      |
| Datenschutz > Ink-& Eingeben der Personalisierung             | `ms-settings:privacy-speechtyping`                 |
| Datenschutz > Motion                                     | `ms-settings:privacy-motion`                       |
| Rahmen für Datenschutz > Screenshot                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Datenschutz > Screenshots und Apps                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| System > Battery                                     | `ms-settings:batterysaver`                         |
| System > Battery                                     | `ms-settings:batterysaver-settings`                |
| System > Sound                                       | `ms-settings:sound`                                |
| System > Sound > App-Lautstärke und Geräteeinstellungen | `ms-settings:apps-volume`                          |
| System > Sound > Verwalten von Soundgeräten              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Time & Language > Date & time                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| Update & Security > Reset & Recovery               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Aktualisierte URIs

Zuvor haben die folgenden beiden URIs einen Benutzer nicht direkt auf die angegebenen Seiten verwiesen, sondern nur die Hauptseite für Updates blockiert. Die folgenden Elemente wurden aktualisiert, um zu ihren Seiten zu leiten:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Konfigurieren der Fallbackdiagnose über Einstellungen App

In Einstellungen App kann ein Benutzer nun das Verhalten der [Fallbackdiagnose](hololens-diagnostic-logs.md)konfigurieren. Navigieren Sie auf der Einstellungen-App zur Seite   >  **Datenschutzproblembehandlung,** um diese Einstellung zu konfigurieren.

> [!NOTE]
> Wenn eine MDM-Richtlinie für das Gerät konfiguriert ist, kann der Benutzer dieses Verhalten nicht außer Kraft setzen.  

### <a name="share-things-with-nearby-devices"></a>Freigeben von Dingen für Geräte in der Nähe

Teilen Sie Dinge mit nahezu Windows 10 Geräten, einschließlich PCs und anderen HoloLens 2 Geräten. Sie können es in **Einstellungen**  >  **freigegebenen**  >  **Systemerfahrungen** ausprobieren, um Dateien oder URLs von einer HoloLens an einen PC freizugeben. Weitere Informationen zum Freigeben von [Geräten in der Nähe finden Sie in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Dieses Feature kann über [Connectivity/AllowConnectedDevices](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)verwaltet werden.

### <a name="new-os-diagnostic-traces"></a>Neue Diagnoseablaufverfolgungen für das Betriebssystem

Zusätzlich zu den vorherigen Problembehandlungen in der Einstellungen-App wurde eine neue Problembehandlung hinzugefügt, und die neue Einstellungen-App für Betriebssystemupdates wurde hinzugefügt. Navigieren Sie zu **Einstellungen**  >  **&amp; Updatesicherheitsproblembehandlung**  >    >  **Windows Update,** und wählen **Sie Starten** aus. Dadurch können Sie Ablaufverfolgungen erfassen, während Sie Ihr Problem mit Betriebssystemupdates reproduzieren, um die Problembehandlung für Ihre IT oder Ihren Support zu verbessern.

### <a name="delivery-optimization-preview"></a>Übermittlungsoptimierung (Vorschau)

Mit diesem HoloLens Update ermöglicht Windows Holographic for Business Übermittlungsoptimierungseinstellungen, um den Bandbreitenverbrauch für Downloads von mehreren HoloLens Geräten zu reduzieren. Eine ausführlichere Beschreibung dieser Funktionalität zusammen mit der empfohlenen Netzwerkkonfiguration finden Sie hier: [Übermittlungsoptimierung für Windows 10-Updates](/windows/deployment/update/waas-delivery-optimization).

Die folgenden Einstellungen werden als Teil der Verwaltungsoberfläche aktiviert und [können über Intune konfiguriert werden](/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Dieses Vorschauangebot hat einige Nachteile:

- HoloLens-Unterstützung ist in dieser Vorschau ausschließlich auf Betriebssystemupdates beschränkt.
- Windows Holographic for Business unterstützt nur HTTP-Downloadmodi und Downloads von einem [Microsoft Connected Cache-Endpunkt](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache). Peer-to-Peer-Downloadmodi und Gruppenzuweisungen werden für HoloLens-Geräte derzeit nicht unterstützt.
- HoloLens unterstützt keine Bereitstellungs- oder Übermittlungsoptimierung für Windows Server Update Services-Endpunkte.
- Für die Problembehandlung ist entweder eine Diagnose auf dem Connected Cache-Server oder das Erfassen einer Ablaufverfolgung für HoloLens über **Einstellungen** > **Update und Sicherheit** >  **Problembehandlung** >  **Windows Update** erforderlich.

### <a name="it-admin---update-checklist"></a>IT-Administrator – Checkliste aktualisieren

Diese Prüfliste hilft Ihnen, die neuen Elemente zu kennen, die in diesem Featureupdate hinzugefügt werden und sich möglicherweise auf Ihre aktuellen Geräteverwaltungskonfigurationen auswirken können, oder neue Features, die Sie möglicherweise verwenden möchten.

#### <a name="updates-to-kiosk-mode"></a>Updates für den Kioskmodus

✔️ [**Neue AUMIDs für neue Apps im Kioskmodus:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Wenn Sie zuvor entweder die Einstellungen-App oder Microsoft Edge App in einem Kiosk verwendet haben, haben wir diese Apps durch neue Apps ersetzt, die eine andere App-ID verwenden. Wir empfehlen Ihnen dringend, unten [New AUMIDs for new apps in Kiosk mode (Neue AUMIDs für neue Apps im Kioskmodus)](#use-the-new-settings-and-edge-apps-in-kiosk-modes) zu lesen. Dadurch wird sichergestellt, dass Sie entweder weiterhin über die Einstellungen-App in Ihrem Kiosk verfügen oder die neue Microsoft Edge-App einschließen. Diese Änderungen können jetzt vorgenommen und auf allen Geräten bereitgestellt werden und ermöglichen einen reibungslosen Übergang beim Update.

✔️ Automatische [**Anmeldung des Besuchers für Kiosks:**](#visitor-auto-logon-for-kiosks)

Besucher können jetzt automatisch bei einem Kiosk angemeldet werden. Dieses Verhalten ist standardmäßig aktiviert, kann aber verwaltet und deaktiviert werden.

✔️ Fehler beim Übergeben des [**Kioskmodus verbessert:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Wenn AAD Gruppenmitgliedschaft des angemeldeten AAD Benutzers nicht erfolgreich bestimmt wurde, wird die globale Kioskkonfiguration für das Startmenü verwendet (sofern vorhanden), andernfalls wird dem Benutzer ein leeres Startmenü angezeigt. Obwohl das leere Startmenü keine Konfiguration ist, die Sie direkt festlegen können, kann diese neue Behandlung ihre Supportabteilung darüber informieren, wenn Sie Kiosks verwenden, da dies möglicherweise für Ihre Konfigurationen gilt oder Sie neue Anpassungen an den zugewiesenen Zugriffskonfigurationen vornehmen möchten.

#### <a name="updates-to-page-settings-visibility"></a>Updates der Sichtbarkeit von Seiten Einstellungen

✔️ Neue [**Einstellungen-URIs für Seiten-Einstellungen-Sichtbarkeit**](#new-settings-uris-for-page-settings-visibility)

Wenn Sie derzeit [Page Einstellungen Visibility](settings-uri-list.md) verwenden, können Sie Anpassungen an Ihren vorhandenen URIs vornehmen, die Sie entweder zugelassen oder blockiert haben.

#### <a name="updates-for-your-wdac-policy"></a>Updates für Ihre WDAC-Richtlinie

✔️ Wenn Sie zuvor Microsoft Edge über WDAC blockiert haben, sollten Sie Ihre WDAC-Richtlinie aktualisieren. Überprüfen Sie Folgendes, und verwenden Sie den bereitgestellten Beispielcode.

#### <a name="enable-new-endpoints-for-edge"></a>Aktivieren neuer Endpunkte für Edge

✔️ Wenn Sie über eine Infrastruktur verfügen, die die Konfiguration von Netzwerkendpunkten wie Proxy oder Firewall umfasst, aktivieren Sie diese neuen Endpunkte für die neue Microsoft Edge-App.

#### <a name="newly-configurable-items"></a>Neu konfigurierbare Elemente

✔️ Konfigurieren [der Fallbackdiagnose:](#configuring-fallback-diagnostics-via-settings-app)Sie können konfigurieren, ob und wer die Fallbackdiagnose erfassen darf.

✔️ Freigeben von[Geräten in der Nähe:](#share-things-with-nearby-devices)Sie können das neue Feature für die Freigabe in der Nähe deaktivieren.

✔️ Konfigurieren [von Richtlinieneinstellungen für die neue Microsoft Edge:](#configuring-policy-settings-for-the-new-microsoft-edge)Überprüfen Sie die neu für Microsoft Edge verfügbaren Konfigurationen.

#### <a name="new-diagnostic-tool"></a>Neues Diagnosetool

✔️ Neue[Diagnoseablaufverfolgungen](#new-os-diagnostic-traces)für das Betriebssystem: Erfassen Sie Protokolle im Zusammenhang mit Betriebssystemupdates.

### <a name="improvements-and-fixes-in-the-update"></a>Verbesserungen und Fehlerbehebungen im Update:

- [Die Offlinediagnose](hololens-diagnostic-logs.md#offline-diagnostics) enthält auch zusätzliche Geräteinformationen für Seriennummer und Betriebssystemversion.
- Behebt ein Problem im Zusammenhang mit der Bereitstellung von Branchenanwendungen über Laufzeitbereitstellungspakete.
- Behebt ein Problem im Zusammenhang mit der Berichterstellung zum Installationsstatus von Branchenanwendungen.
- Behebt ein Problem im Zusammenhang mit der Persistenz neuer App-Pakete über Geräterücksetzungen hinweg.
- Behebt ein Problem, das dazu führen kann, dass falsche Symbole in Edge für japanische Kunden eingegeben werden.
- Verbessert die Resilienz von Betriebssystemupdates für vorinstallierte Apps wie Edge.
- Behandelt eine Updatesicherheit, die sich auf die Installation von Microsoft Edge auswirkt.

## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, Version 20H2 – Update vom Mai 2021

- Build 19041.1146

Verbesserungen und Fehlerbehebungen im Update:

- Dieses monatliche Qualitätsupdate enthält keine wichtigen Änderungen. Wir empfehlen Ihnen, unseren neuesten Build Windows Holographic, Version 21H1, auszuprobieren.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, Version 1903 – Update vom Mai 2021

- Build 18362.1110

Verbesserungen und Fehlerbehebungen im Update:

- Dieses monatliche Qualitätsupdate enthält keine wichtigen Änderungen. **Dieser Build empfängt keine monatlichen Dienstupdates mehr.** Wir empfehlen Ihnen, unseren neuesten Build, Windows Holographic, Version 21H1, auszuprobieren.

## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, Version 20H2 – Update vom April 2021

- Build 19041.1144

Verbesserungen und Fehlerbehebungen im Update:

- Behebt ein Problem bei der Berichterstellung zum Installationsstatus von Line-of-Business-Anwendungen.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, Version 1903 – Update april 2021

- Build 18362.1108

Verbesserungen und Fehlerbehebungen im Update:

- Behebt ein Problem, bei dem Einstellungen App abstürzt, wenn versucht wird, ein Kennwort für ein lokales Konto zu ändern.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, Version 20H2 – Update vom März 2021

- Build 19041.1140

Verbesserungen und Fehlerbehebungen im Update:

- Kunden, die AdvancedPhotoCapture oder LowLagPhotoCapture zum Erfassen von Fotos mit HoloLens 2 verwenden, können die Kamerapose jetzt bis zu 3 Sekunden nach der Aufnahme des Fotos abrufen.
- Behebung eines Arbeitsspeicherverlusts in Geräteportal Service, das zu einer erhöhten Speicherauslastung durch den Dienst führte, die dazu führte, dass andere Anwendungen nicht genügend Arbeitsspeicher zuordnen.
- Es wurde ein Problem behoben, bei dem sich Benutzer, die für den gestufigen Rollout registriert sind, nicht beim Gerät anmelden konnten.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, Version 1903 – Update vom März 2021

- Build 18362.1102

Verbesserungen und Fehlerbehebungen im Update:

- Behebung eines Arbeitsspeicherverlusts in Geräteportal Service, das zu einer erhöhten Speicherauslastung durch den Dienst führte, die dazu führte, dass andere Anwendungen nicht genügend Arbeitsspeicher zuordnen.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, Version 20H2 – Update vom Februar 2021

- Build 19041.1136

Verbesserungen und Fehlerbehebungen im Update:

- Behebt ein Problem bei der anfänglichen Geräteeinrichtung und beim Speichern von App-Updates.
- Behebt ein Problem mit Upgrades und Flügen für HoloLens Versionen.
- Nicht verwendete vorinstallierte Zertifikate wurden aus dem eSIM-Stammspeicher von HoloLens entfernt.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, Version 1903 – Update vom Februar 2021

- Build 18362.1098

Dieses monatliche Qualitätsupdate enthält keine wichtigsten Änderungen. Wir empfehlen Ihnen, unsere neuesten Builds für Windows Holographic, Version 2004, auszuprobieren.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, Version 20H2 – Update vom Januar 2021

- Build 19041.1134

Verbesserungen und Fehlerbehebungen im Update:

- Verbesserte Leistung beim Starten, Fortsetzen und Wechseln von Benutzern, wenn viele Benutzer auf dem Gerät sind.
- Arm32-Unterstützung für den [Research-Modus wurde hinzugefügt.](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, Version 1903 – Update vom Januar 2021

- Build 18362.1091

Dieses monatliche Qualitätsupdate enthält keine wichtigsten Änderungen. Wir empfehlen Ihnen, unsere neuesten Builds für Windows Holographic, Version 2004, auszuprobieren.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, Version 20H2 – Update vom Dezember 2020

- Build 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Installieren von Apps auf HoloLens 2 über App-Installer

Wir fügen **eine neue Funktion (App-Installer)** hinzu, mit der Sie Anwendungen nahtloser auf Ihren HoloLens 2 installieren können. Das Feature ist standardmäßig **für nicht verwaltete Geräte aktiviert.** Um Unterbrechungen für Unternehmen zu verhindern, ist das App-Installationsprogramm derzeit nicht für **verwaltete** Geräte verfügbar.  

Ein Gerät gilt als "verwaltet", **wenn** eine der folgenden Bedingungen zutrifft:

- MDM [registriert](hololens-enroll-mdm.md)
- Mit [Bereitstellungspaket konfiguriert](hololens-provisioning.md)
- Die [Benutzeridentität](hololens-identity.md) ist Azure AD

Sie können Apps jetzt installieren, ohne den Entwicklermodus zu aktivieren oder Geräteportal.  Laden Sie einfach (über USB oder über Edge) das Appx Bundle auf Ihr Gerät herunter, und navigieren Sie im Datei-Explorer zum Appx-Bundle, um zum Starten der Installation aufgefordert zu werden.  Alternativ können Sie [eine Installation über eine Webseite initiieren.](/windows/msix/app-installer/installing-windows10-apps-web)  Genau wie Apps, die Sie über die Microsoft Store installieren oder mithilfe der BEREITSTELLUNGsfunktion für BRANCHEN-Apps von [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) MDM sideload verwenden, müssen Apps digital mit dem Signierungstool signiert werden, und das Zertifikat, das zum Signieren verwendet wird, muss vom HoloLens-Gerät als vertrauenswürdig eingestuft werden, bevor die App bereitgestellt werden kann. [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Installationsanweisungen für die Anwendung.**

1. Stellen Sie sicher, dass Ihr Gerät nicht als verwaltet gilt.
1. Stellen Sie sicher, HoloLens 2 gerät eingeschaltet und mit Ihrem PC verbunden ist.
1. Stellen Sie sicher, dass Sie beim HoloLens 2 angemeldet sind.
1. Navigieren Sie auf Ihrem PC zu Ihrer benutzerdefinierten App, und kopieren Sie Yourapp.appxbundle in IhrGerätename\Internes Storage\Downloads.   Nachdem Sie das Kopieren Ihrer Datei abgeschlossen haben, können Sie ihr Gerät trennen.
1. Öffnen Sie HoloLens 2-Gerät das Startmenü, wählen Sie Alle Apps aus, und starten Sie die Datei-Explorer-App.
1. Navigieren Sie zum Ordner Downloads. Möglicherweise müssen Sie im linken Bereich der App zuerst Dieses Gerät auswählen und dann zu Downloads navigieren.
1. Wählen Sie die Datei yourapp.appxbundle aus.
1. Die App-Installer wird gestartet. Wählen Sie die Schaltfläche Installieren aus, um Ihre App zu installieren.
Die installierte App wird nach Abschluss der Installation automatisch gestartet.

Beispiel-Apps finden Sie auf Windows [universellen Beispielen GitHub,](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) um diesen Flow zu testen.

Erfahren Sie mehr über den [vollständigen Prozess der Installation von Apps auf HoloLens 2 mit dem App-Installer.](app-deploy-app-installer.md)  

![Installieren von MRTK-Beispielen über App-Installer.](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Verbesserungen und Fehlerbehebungen im Update:

- Die Handverfolgung verwaltet jetzt die Nachverfolgung in vielen neuen Fällen, in denen die Hand zuvor verloren gegangen wäre.  In einigen dieser neuen Fälle wird nur die Handflächenposition des Benutzers basierend auf der tatsächlichen Hand des Benutzers aktualisiert, während die anderen Fugen basierend auf einer vorherigen Pose abgeleitet werden.  Diese Änderung trägt zur Verbesserung der Nachverfolgungskonsistenz bei Bewegungen wie Slapping, Throwing, Scooping und Clapping bei.  Dies hilft auch in Fällen, in denen sich die Hand in der Nähe einer Oberfläche befindet oder ein Objekt hält.  Wenn Handgelenke abgeleitet werden, wird [](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) der Genauigkeitswert pro Joint auf "Approximate" (Ungefähr) anstatt auf "High" festgelegt.
- Es wurde ein Problem behoben, bei dem die PIN-Azure AD konten den Fehler "Es ist ein Fehler aufgetreten.
- Benutzer sollten beim Starten von ET, Iris über die Einstellungs-App, neuer Benutzer oder Popupbenachrichtigung deutlich weniger OoBE-Abstürze nach dem Start sehen.
- Benutzer sollten über die richtige Zeitzone verfügen, die aus der OOBE kommt.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, Version 1903 – Update vom Dezember 2020

- Build 18362.1088

Dieses monatliche Qualitätsupdate enthält keine wichtigsten Änderungen. Wir empfehlen Ihnen, unsere neueste Windows Holographic-Version 20H2 – Update vom Dezember 2020 und das neue App-Installer-Feature auszuprobieren, das im Build hinzugefügt wurde.

## <a name="windows-holographic-version-20h2"></a>Windows Holographic, Version 20H2

- Build 19041.1128

Windows Holographic, Version 20H2, ist jetzt verfügbar und bietet eine große Menge neuer Features für HoloLens 2 und IT-Experten. Von der automatischen Blickpositionierung über den Zertifikat-Manager in Einstellungen über verbesserte Kioskmodusfunktionen bis hin zu neuen Autopilot-Setupfunktionen. Mit diesem neuen Update können IT-Teams eine präzisere Kontrolle über die Konfiguration und Verwaltung HoloLens Geräte übernehmen und den Benutzern noch nahtlosere holografische Erfahrungen bieten.

Dieses neueste Release ist ein monatliches Update auf Version 2004, aber dieses Mal werden neue Features veröffentlicht. Die Hauptversionsnummer bleibt unverändert, und Windows Update gibt ein monatliches Release für Version 2004 (Build 19041) an. Sie können ihre Buildnummer auf dem Bildschirm Einstellungen > About (Informationen) anzeigen, um zu bestätigen, dass Sie sich auf dem neuesten verfügbaren Build 19041.1128 und mehr befinden. Um auf das neueste Release zu aktualisieren, öffnen Sie die Einstellungen-App, wechseln Sie zu Update & Sicherheit, und tippen Sie auf Nach Updates suchen. Weitere Informationen zum Verwalten von Updates für HoloLens finden Sie unter [Verwalten HoloLens Updates.](hololens-updates.md)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Neues in Windows Holographic, Version 20H2  

| Funktion                                              | BESCHREIBUNG                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Unterstützung der automatischen Augenstellung](hololens-release-notes.md#auto-eye-position-support) | Berechnet aktiv Augenpositionen, ohne dass Benutzer die EyeTracking-Kalibrierung verwenden.   |
| [Zertifikat-Manager](hololens-release-notes.md#certificate-manager)   | Ermöglicht neuen einfacheren Methoden das Installieren und Entfernen von Zertifikaten aus der Einstellungen App.     |
| [Automatisches Starten der Bereitstellung über USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Bei der Bereitstellung von Paketen auf USB-Laufwerken wird die Bereitstellungsseite in OOBE automatisch aufgefordert.                                                         |
| [Automatisches Bestätigen von Bereitstellungspaketen in OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Bereitstellungspakete werden automatisch während der OOBE auf der Bereitstellungsseite angewendet.                                                         |
| [Automatische Bereitstellung ohne Benutzeroberfläche](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Kombinieren des automatischen Starts und der automatischen Bestätigung der Bereitstellung |
| [Verwenden von Autopilot mit Wi-Fi Verbindung](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Verwenden Sie Autopilot vom Gerät Wi-Fi ohne Ethernet-Adapter. |
| [TenantLockdown CSP und Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Nachdem die Mandantenregistrierung und die Richtlinie angewendet wurden, kann das Gerät nur bei jedem Zurücksetzen oder erneuten Flashen des Geräts bei diesem Mandanten registriert werden. |
| [Global zugewiesener Zugriff](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Neue Konfigurationsmethode für den Kioskmodus für mehrere Apps, die den Kiosk auf Systemebene anwendet, sodass er für alle gilt.                  |
| [Automatisches Starten einer App im Kiosk mit mehreren Apps](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Legt fest, dass eine Anwendung automatisch gestartet wird, wenn sie sich bei einem Kioskmodus mit mehreren Apps anmeldet.                                                        |
| [Änderungen des Kioskmodusverhaltens bei der Behandlung von Fehlern](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Der Kioskmodusfehler weist jetzt einen restriktiven Fallback auf.                                                                                                |
| [HoloLens Politik](hololens-release-notes.md#hololens-policies)                                    | Neue Richtlinien für HoloLens.     |
| [Cache Azure AD Gruppenmitgliedschaft für Offlinekiosk](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Mit der neuen Richtlinie können Benutzer den Gruppenmitgliedschaftscache verwenden, um den Kioskmodus für die festgelegte Anzahl von Tagen offline zu verwenden.                                        |
| [Neue Geräteeinschränkungsrichtlinien für HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Neu aktivierte Geräteverwaltungsrichtlinien für HoloLens 2.                                                                                |
| [Neue Energierichtlinien für HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Neu unterstützte Richtlinien für Energietimeouteinstellungen.  |
| [Aktualisieren von Richtlinien](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Neu aktivierte Richtlinien, die die Steuerung von Updates ermöglichen.           |
| [Einstellungen Seitensichtbarkeit für HoloLens 2 aktiviert](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Richtlinie zum Auswählen der Seiten, die in Einstellungen App angezeigt werden.             |
| [Forschungsmodus](hololens-release-notes.md#research-mode) | Verwenden des Forschungsmodus auf HoloLens 2. |
| [Aufzeichnungslänge erhöht](hololens-release-notes.md#recording-length-increased) | MRC-Aufzeichnungen sind nicht mehr auf 5 Minuten begrenzt. |
| [Verbesserungen und Fehlerbehebungen im Update](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Zusätzliche Fehlerbehebungen im Update.   |

### <a name="auto-eye-position-support"></a>Unterstützung der automatischen Augenstellung

In HoloLens 2 ermöglichen Augenpositionen eine genaue Hologrammpositionierung, eine komfortable Anzeige und eine verbesserte Anzeigequalität. Die Augenstellungen werden intern im Rahmen der Eye-Tracking-Berechnung bestimmt. Dies erfordert jedoch, dass jeder Benutzer eine Eye-Tracking-Kalibrierung durchläuft, auch wenn das Erlebnis möglicherweise keine Blickeingabe erfordert.

**Auto Eye Position (AEP)** ermöglicht diese Szenarien durch eine interaktionsfreie Methode zur Berechnung der Augenstellung des Benutzers. Die automatische Blickposition funktioniert im Hintergrund automatisch ab dem Moment, an dem der Benutzer das Gerät einschaltet. Wenn der Benutzer nicht über eine vorherige Kalibrierung der Blickverfolgung verfügt, beginnt auto eye position mit der Bereitstellung der Augenpositionen des Benutzers für das Anzeigesystem nach einer Verarbeitungszeit von 20 bis 30 Sekunden. Die Benutzerdaten werden nicht dauerhaft auf dem Gerät gespeichert. Daher wird dieser Vorgang wiederholt, wenn der Benutzer das Gerät startet und wieder einschaltet oder wenn das Gerät neu gestartet oder aus dem Standbymodus reaktiviert wird.

Es gibt ein paar Änderungen hinsichtlich des Systemverhaltens bei der Funktion Auto Eye Position, wenn ein nicht kalibrierter Benutzer das Gerät aufsetzt. In diesem Kontext bezieht sich ein uncalibrierter Benutzer auf eine Person, die den Kalibrierungsprozess für die Augenüberwachung auf dem Gerät noch nicht durchlaufen hat.

| Aktive Anwendung | Früheres Verhalten | Verhalten ab Windows Holographic, Version 20H2-Update |
|:-------------------|:-----------------|:-----------------------------------|
| Nicht-Anvisieren ist in der App oder Holographic Shell aktiviert |Eingabeaufforderung zur Eye-Tracking-Kalibrierung wird angezeigt. | Es wird kein Eingabeaufforderung angezeigt. |
| Anvisieren ist in der App aktiviert | Eingabeaufforderung zur Eye-Tracking-Kalibrierung wird angezeigt. | Das Dialogfeld zur Eye-Tracking-Kalibrierung wird nur angezeigt, wenn die Anwendung auf den Blickfluss zugreift. |

Wenn Benutzer von einer Anwendung mit aktiviertem Nicht-Anvisieren zu einer Anwendung wechseln, die auf Blickdaten zugreift, wird die Kalibrierungsaufforderung angezeigt.

Alle anderen Systemverhalten ähneln, wenn der aktuelle Benutzer nicht über eine aktive Eyetracking-Kalibrierung verfügt. Beispielsweise wird die Einhändige Startgeste nicht aktiviert. Die Out-Of-Box-Experience für die Ersteinrichtung wird nicht verändert.

Für Benutzer, die Daten zum Anvisieren mit den Augen oder eine sehr genaue Hologrammpositionierung erfordern, empfehlen wir uncalibrierten Benutzern die Kalibrierung der Blickverfolgung. Sie ist über die Kalibrierungseingabeaufforderung für die Blickverfolgung oder durch Starten der Einstellungen-App über das Startmenü zugänglich, und wählen Sie dann **System > Calibration > Eye Calibration > Run eye calibration (Kalibrierung** der Augen ausführen) aus.

Diese Informationen finden Sie später mit [anderen Kalibrierungsinformationen.](hololens-calibration.md#auto-eye-position-support)

### <a name="certificate-manager"></a>Zertifikat-Manager

- Verbesserte Überwachungs-, Diagnose- und Validierungstools für Gerätesicherheit und -konformität über den neuen Zertifikat-Manager. Mit dieser Funktion können Sie Ihre Zertifikate in kommerziellen Umgebungen im großen Stil bereitstellen, behandeln und überprüfen.

In Windows Holographic-Version 20H2 fügen wir einen Zertifikat-Manager in der HoloLens 2 Einstellungen-App hinzu. Wechseln Sie zu **Einstellungen > Update & Security > Certificates**. Dieses Feature bietet eine einfache und benutzerfreundliche Möglichkeit zum Anzeigen, Installieren und Entfernen von Zertifikaten auf Ihrem Gerät. Mit dem neuen Zertifikat-Manager verfügen Administratoren und Benutzer jetzt über verbesserte Überwachungs-, Diagnose- und Validierungstools, um sicherzustellen, dass Geräte sicher und konform bleiben.

- **Überwachung:** Möglichkeit, zu überprüfen, ob ein Zertifikat ordnungsgemäß bereitgestellt wurde, oder um zu bestätigen, dass es ordnungsgemäß entfernt wurde.
- **Diagnose:** Wenn Probleme auftreten, spart die Überprüfung, ob die entsprechenden Zertifikate auf dem Gerät vorhanden sind, Zeit und hilft bei der Problembehandlung.
- **Überprüfung:** Die Überprüfung, ob ein Zertifikat den beabsichtigten Zweck erfüllt und funktionsfähig ist, kann insbesondere in kommerziellen Umgebungen erhebliche Zeit sparen, bevor Zertifikate in größerem Umfang bereitgestellt werden.

Um schnell ein bestimmtes Zertifikat in der Liste zu finden, gibt es Optionen zum Sortieren nach Name, Speicher oder Ablaufdatum. Benutzer können auch direkt nach einem Zertifikat suchen. Um einzelne Zertifikateigenschaften anzuzeigen, wählen Sie das Zertifikat aus, und klicken Sie auf **Info**.

Die Zertifikatinstallation unterstützt derzeit CER- und CRT-Dateien. Gerätebesitzer können Zertifikate auf dem lokalen Computer und dem aktuellen Benutzer installieren.  alle anderen Benutzer können nur in Current User installieren. Benutzer können nur Zertifikate entfernen, die direkt von der Einstellungen-Benutzeroberfläche installiert wurden. Wenn ein Zertifikat auf andere Weise installiert wurde, muss es auch mit demselben Mechanismus entfernt werden.

#### <a name="steps-to-install-a-certificate"></a>Schritte zum Installieren eines Zertifikats

1. Verbinden Ihre HoloLens 2 zu einem PC.
1. Platzieren Sie die Zertifikatdatei, die Sie installieren möchten, an einem Speicherort auf Ihrem HoloLens 2.
1. Navigieren Sie zu **Einstellungen App > Update & Security > Certificates**, und wählen Sie Zertifikat installieren aus.
1. Klicken Sie auf **Datei importieren,** und navigieren Sie zu dem Speicherort, an dem Sie das Zertifikat gespeichert haben.
1. Wählen Sie **Store Standort aus.**
1. Wählen Sie **Zertifikat Store** aus.
1. Klicken Sie auf **Installieren**.

Das Zertifikat sollte nun auf dem Gerät installiert sein.

#### <a name="steps-to-remove-a-certificate"></a>Schritte zum Entfernen eines Zertifikats

1. Navigieren Sie zu **Einstellungen App > Update and Security > Certificates**.
1. Suchen Sie im Suchfeld nach dem Zertifikat anhand des Namens.
1. Wählen Sie das Zertifikat aus.
1. Klicken Sie auf **Entfernen.**
1. Wählen Sie **Ja** aus, wenn Sie zur Bestätigung aufgefordert werden.

![Zertifikatanzeige in der Einstellungen-App.](images/certificate-viewer-device.jpg)

![Abbildung: Verwenden der Zertifikat-Benutzeroberfläche zum Installieren eines Zertifikats](images/certificate-device-install.jpg)

Diese Informationen finden Sie später [auf einer neuen Seite des Zertifikat-Managers.](certificate-manager.md)

### <a name="auto-launch-provisioning-from-usb"></a>Automatisches Starten der Bereitstellung über USB

- Automatisierte Prozesse, die eine geringere Benutzerinteraktion ermöglichen, wenn USB-Laufwerke mit Bereitstellungspaketen während der OoBE verwendet werden.

Vor diesem Release mussten Benutzer den Bereitstellungsbildschirm während der OoBE manuell starten, um die Bereitstellung mithilfe einer Schaltflächenkombination zu ermöglichen. Jetzt können Benutzer die Schaltflächenkombination überspringen, indem sie ein Bereitstellungspaket auf einem USB-Speicherlaufwerk verwenden.

1. Anschließen des USB-Laufwerks mit dem Bereitstellungspaket während des ersten interaktionsfähigen OoBE-Moments
1. Wenn das Gerät bereit für die Bereitstellung ist, öffnet es automatisch die Eingabeaufforderung mit der Bereitstellungsseite.

Hinweis: Wenn ein USB-Laufwerk beim Starten des Geräts angeschlossen bleibt, zählt OOBE ein vorhandenes USB-Speichergerät auf und überwacht, ob weitere angeschlossen sind.

Weitere Informationen zum Anwenden von Bereitstellungspaketen während der Oobe finden Sie in der [Dokumentation zur HoloLens Bereitstellung.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Weitere Informationen zum [automatischen Starten](hololens-provisioning.md#auto-launch-provisioning-from-usb) der Bereitstellung über usb finden Sie in der Dokumentation zur HoloLens-Bereitstellung.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Automatische Bestätigung von Bereitstellungspaketen in OOBE

- Automatisierter Prozess, der eine geringere Benutzerinteraktion ermöglicht. Wenn die Seite Bereitstellungspaket angezeigt wird, werden automatisch alle aufgelisteten Pakete angewendet.

Wenn der Hauptbildschirm für die Bereitstellung angezeigt wird, zählt OOBE 10 Sekunden nach unten, bevor automatisch mit dem Anwenden aller Bereitstellungspakete begonnen wird. Benutzer können die Pakete, die sie erwartet haben, innerhalb dieser 10 Sekunden bestätigen [oder abbrechen.](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)

### <a name="automatic-provisioning-without-using-ui"></a>Automatische Bereitstellung ohne Benutzeroberfläche

- Kombinierte automatische Prozesse für reduzierte Geräteinteraktionen für die Bereitstellung.

Durch die Kombination des automatischen Starts der Bereitstellung von USB-Geräten und der automatischen Bestätigung von Bereitstellungspaketen kann ein Benutzer HoloLens 2 Geräte automatisch bereitstellen, ohne die Benutzeroberfläche des Geräts oder sogar das Gerät zu verwenden. Sie können weiterhin das gleiche USB-Laufwerk und bereitstellungspaket für mehrere Geräte verwenden. Dies ist nützlich für die gleichzeitige Bereitstellung mehrerer Geräte im selben Bereich.

1. Erstellen Sie mit [Windows Konfigurations-Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) [ein Bereitstellungspaket.](hololens-provisioning.md)
1. Kopieren Sie das Paket auf ein USB-Speicherlaufwerk.
1. [Flashen Sie Ihre HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) auf [19041.1361 oder neueren Build.](https://aka.ms/hololens2previewdownload)
1. Wenn [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) das Blinken des Geräts abgeschlossen hat, ziehen Sie das USB-C-Kabel aus.
1. Schließen Sie Ihr USB-Laufwerk an das Gerät an.
1. Wenn das HoloLens 2 Gerät in OOBE gestartet wird, wird das Bereitstellungspaket automatisch auf dem USB-Laufwerk erkannt und die Bereitstellungsseite gestartet.
1. Nach 10 Sekunden wendet das Gerät automatisch das Bereitstellungspaket an.

Ihr Gerät ist jetzt konfiguriert und [zeigt den Bildschirm Bereitstellung erfolgreich](hololens-provisioning.md#automatic-provisioning-without-using-ui)an.

### <a name="using-autopilot-with-wi-fi-connection"></a>Verwenden von Autopilot mit Wi-Fi Verbindung

- Usb-C-Adapter für Ethernet wurden nicht mehr benötigt, um den Hardwarebedarf zu reduzieren, da Autopilot auf Wi-Fi verbundenen Geräten funktionieren kann.

Sobald Sie während der OOBE eine Verbindung mit HoloLens 2 mit WLAN herstellen, sucht OOBE nach einem Autopilot-Profil für das Gerät. Wenn eine gefunden wird, wird sie verwendet, um den Rest des AAD Join- und Registrierungsflows abzuschließen. Anders ausgedrückt: Die Verwendung von Ethernet zu USB-C oder Wi-Fi zu USB-C-Adaptern ist keine Anforderung mehr, sie funktionieren jedoch weiterhin, wenn sie zu Beginn der OOBE bereitgestellt werden. Erfahren Sie mehr über [Autopilot für HoloLens 2 Geräte.](hololens2-autopilot.md)

### <a name="tenantlockdown-csp-and-autopilot"></a>TenantLockdown CSP und Autopilot

- Behält Geräte auf dem Mandanten der Organisation bei, indem sie für den Mandanten gesperrt werden, auch wenn der Gerätezurücksetzungs- oder Reflash-Ansatz verwendet wird. Mit zusätzlicher Sicherheit, indem sie die Kontoerstellung in über die Bereitstellung nicht zulasst.

HoloLens 2 Geräte unterstützen ab [Windows Holographic-Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2)den TenantLockdown-CSP.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP ermöglicht es, HoloLens 2 nur über Autopilot an die MDM-Registrierung zu binden. Sobald der RequireNetworkInOOBE-Knoten des TenantLockdown CSP auf „wahr“ oder „falsch“ (anfänglich festgelegt) auf HoloLens 2 eingestellt ist, verbleibt dieser Wert auf dem Gerät, trotz erneutem Blinken, Betriebssystemupdates usw.

Sobald der RequireNetworkInOOBE-Knoten des TenantLockdown CSP auf HoloLens 2 auf „wahr“ gesetzt ist, wartet OOBE nach der Netzwerkverbindung unbegrenzt auf das erfolgreiche Herunterladen und Anwenden des Autopilot-Profils.

Sobald der RequireNetworkInOOBE-Knoten von TenantLockdown CSP auf HoloLens 2 auf „wahr“ gesetzt wird, sind folgende Vorgänge in OOBE unzulässig:

- Erstellen lokaler Benutzer mit Laufzeit-Bereitstellung
- Durchführen einer Azure AD-Verknüpfungsoperation über Laufzeitbereitstellung
- Auswählen, wem das Gerät in OOBE gehört

#### <a name="how-to-set-this-using-intune"></a>Wie richtet man das mit Intune ein?

1. Erstellen Sie ein benutzerdefiniertes OMA-URI-Gerätekonfigurationsprofil und geben Sie „wahr“ für den RequireNetworkInOOBE-Knoten an, wie unten dargestellt.
Der OMA-URI-Wert sollte ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE lauten

   > [!div class="mx-imgBorder"]
   > ![TenantLockdown über OMA-URI einrichten.](images/hololens-tenant-lockdown.png)

1. Erstellen Sie eine Gruppe und weisen Sie dieser Gerätegruppe das Gerätekonfigurationsprofil zu.

1. Machen Sie das HoloLens 2-Gerät zu einem Mitglied der im vorherigen Schritt erstellten Gruppe und lösen Sie die Synchronisierung aus.  

Überprüfen Sie im Intune-Portal, ob die Gerätekonfiguration erfolgreich angewendet wurde. Sobald diese Gerätekonfiguration erfolgreich auf das HoloLens 2-Gerät angewendet wird, sind die Effekte von TenantLockdown aktiv.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Wie funktioniert die Aufhebung des RequireNetworkInOOBE von TenantLockdown auf HoloLens 2 mit Intune?

1. Entfernen Sie die HoloLens 2 aus der Gerätegruppe, der die oben erstellte Gerätekonfiguration zuvor zugewiesen wurde.

1. Erstellen Sie ein benutzerdefiniertes OMA URI-basiertes Gerätekonfigurationsprofil, und geben Sie für RequireNetworkInOOBE den Wert „falsch“ an, wie unten dargestellt.
Der OMA-URI-Wert sollte ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE lauten

   > [!div class="mx-imgBorder"]
   > ![Screenshot der Einstellung von RequireNetworkInOOBE auf „false“ über OMA-URI in Intune.](images/hololens-tenant-lockdown-false.png)

1. Erstellen Sie eine Gruppe und weisen Sie dieser Gerätegruppe das Gerätekonfigurationsprofil zu.

1. Machen Sie das HoloLens 2-Gerät zu einem Mitglied der im vorherigen Schritt erstellten Gruppe und lösen Sie die Synchronisierung aus.

Überprüfen Sie im Intune-Portal, ob die Gerätekonfiguration erfolgreich angewendet wurde. Sobald diese Gerätekonfiguration erfolgreich auf das HoloLens 2-Gerät angewendet wird, sind die Effekte von TenantLockdown inaktiv.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Was würde während der OOBE geschehen, wenn das Autopilot-Profil auf HoloLens deaktiviert wird, nachdem TenantLockdown auf „wahr“ festgelegt wurde?

OOBE wartet auf unbestimmte Zeit auf den Autopilot-Profil-Download. Folgendes Dialogfeld wird angezeigt. Um die Auswirkungen von TenantLockdown zu entfernen, muss das Gerät zunächst bei seinem ursprünglichen Mandanten angemeldet werden, wobei nur Autopilot verwendet werden darf. RequireNetworkInOOBE muss wie im vorherigen Schritt beschrieben zurückgesetzt werden, bevor die von TenantLockdown CSP eingeführten Einschränkungen entfernt werden.

![Geräteinterne Ansicht für den Zeitpunkt, zu dem die Richtlinie auf dem Gerät durchgesetzt wird.](images/hololens-autopilot-lockdown.png)

Diese Informationen finden Sie jetzt zusammen mit dem restliche Autopilot unter [Tenantlockdown CSP und Autopilot](hololens2-autopilot.md#tenant-lockdown-csp-and-autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Global zugewiesener Zugriff – Kioskmodus

- Reduzierte Identitätsverwaltung für Kiosk, indem die neue Kioskmethode aktiviert wird, die den Kioskmodus auf Systemebene anwendet.

Mit diesem neuen Feature kann ein IT-Administrator ein HoloLens 2 Gerät für den Kioskmodus für mehrere Apps konfigurieren, der auf Systemebene anwendbar ist, keine Affinität mit einer Identität im System aufwies und für alle Benutzer gilt, die sich beim Gerät anmelden. Weitere Informationen zu dieser neuen Funktion finden Sie im [HoloLens Kioskmodus.](hololens-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Automatisches Starten einer Anwendung im Kioskmodus mit mehreren Apps

- Fokussierte Erfahrung mit dem automatischen App-Start, wodurch die Benutzeroberflächen- und App-Auswahl weiter erhöht wird, die für Kioskmodus-Benutzeroberflächen ausgewählt wurde.

Gilt nur für den Kioskmodus mit mehreren Apps, und nur eine App kann mithilfe des hervorgehobenen Attributs unten in der Konfiguration des zugewiesenen Zugriffs für den automatischen Start festgelegt werden.

Die Anwendung wird automatisch gestartet, wenn sich der Benutzer anmeldet.

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Änderungen des Kioskmodusverhaltens bei der Behandlung von Fehlern

- Sichererer Kioskmodus, indem verfügbare Apps bei Kioskmodusfehlern beseitigt werden.

Zuvor wurden Fehler beim Anwenden des Kioskmodus HoloLens verwendet, um alle Anwendungen im Startmenü anzuzeigen. In Windows Holographic-Version 20H2 werden im Fall von Ausfällen keine Apps wie folgt im Startmenü angezeigt:

![Abbildung, wie der Kioskmodus jetzt aussieht, wenn ein Fehler auftritt.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens Politik

- Geräteverwaltungsoptionen speziell für HoloLens, die für die Verwaltung des Geräts erstellt wurden.

Neue Mixed Reality-Richtlinien wurden für HoloLens 2 Geräte auf Windows Holographic Version 20H2 erstellt. Neue steuerbare Einstellungen: Festlegen der Helligkeit, Festlegen der Lautstärke, Deaktivieren der Audioaufzeichnung in Mixed Reality-Erfassungen, Festlegen, wann Diagnosedaten erfasst werden können, und AAD Gruppenmitgliedschaftscache.  

| Neue HoloLens-Richtlinie                                | BESCHREIBUNG                                                                               | Notizen                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Ermöglicht das Deaktivieren von Helligkeitsschaltflächen, sodass sich die Helligkeit nicht ändert, wenn Sie sie drücken.       | 1 Ja, 0 Nein (Standard)                                                |
| MixedReality\VolumeButtonDisabled                  | Ermöglicht das Deaktivieren von Lautstärkereglern, sodass sich das Volumen durch drücken nicht ändert.               | 1 Ja, 0 Nein (Standard)                                                |
| MixedReality\MicrophoneDisabled                    | Deaktiviert das Mikrofon, sodass keine Audioaufzeichnung auf HoloLens 2 möglich ist.                      | 1 Ja, 0 Nein (Standard)                                                |
| MixedReality\FallbackDiagnostics                   | Steuert das Verhalten, wann Diagnoseprotokolle gesammelt werden können.                               | 0 Deaktiviert, 1 für Gerätebesitzer aktiviert, 2 für alle aktiviert (Standard) |
| MixedReality\HeadTrackingMode                      | Für die zukünftige Verwendung reserviert.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheCacheInDays | Steuert, wie viele Tage Azure AD Gruppenmitgliedschaftscache für Kiosks für Azure AD Gruppen verwendet wird. | Siehe unten.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Cache Azure AD Gruppenmitgliedschaft für Offlinekiosk

- Aktivierte Offlinekiosk, die bis zu 60 Tage lang mit AAD Gruppen verwendet werden können.

Diese Richtlinie steuert, wie viele Tage Azure AD Gruppenmitgliedschaftscache für Konfigurationen des zugewiesenen Zugriffs verwendet werden darf, die auf Azure AD Gruppen für angemeldete Benutzer ausgerichtet sind. Sobald dieser Richtlinienwert nur auf einen Wert größer als 0 festgelegt ist, wird der Cache verwendet, andernfalls nicht.  

Name: AADGroupMembershipCacheCacheInDays-URI-Wert: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCache UsernameInDays

Min. – 0 Tage  
Max. – 60 Tage

Schritte zur ordnungsgemäßen Verwendung dieser Richtlinie:

1. Erstellen Sie ein Gerätekonfigurationsprofil für Kioskzielgruppen Azure AD, und weisen Sie es HoloLens Geräten zu.
1. Erstellen Sie eine benutzerdefinierte OMA-URI-basierte Gerätekonfiguration, die diesen Richtlinienwert auf die gewünschte Anzahl von Tagen (> 0) festlegt, und weisen Sie sie HoloLens Geräten zu.
    1. Der URI-Wert sollte in das Textfeld OMA-URI als ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheOrporaInDays eingegeben werden.
    1. Der Wert kann zwischen min/max zulässig sein.
1. Registrieren Sie HoloLens Geräte, und überprüfen Sie, ob beide Konfigurationen auf das Gerät angewendet werden.
1. Lassen Sie Azure AD Benutzer 1 anmelden, wenn das Internet verfügbar ist. Sobald sich der Benutzer anmeldet und Azure AD Gruppenmitgliedschaft erfolgreich bestätigt wurde, wird der Cache erstellt.
1. Jetzt kann Azure AD Benutzer 1 HoloLens offline schalten und für den Kioskmodus verwenden, solange der Richtlinienwert X Tage zulässt.
1. Die Schritte 4 und 5 können für jeden anderen Azure AD Benutzer N wiederholt werden. Der Wichtigste Punkt hierbei ist, dass sich jeder Azure AD Benutzer über das Internet beim Gerät anmelden muss, damit wir mindestens einmal feststellen können, dass er Mitglied Azure AD Gruppe ist, für die die Kioskkonfiguration vorgesehen ist.

> [!NOTE]
> Bis Schritt 4 für eine Azure AD Benutzer das in "getrennten" Umgebungen beschriebene Fehlerverhalten auftritt.

### <a name="new-device-restriction-policies-for-hololens-2"></a>Neue Geräteeinschränkungsrichtlinien für HoloLens 2

- Ermöglicht Es Benutzern, bestimmte Geräteverwaltungsrichtlinien zu verwalten, z. B. das Blockieren des Hinzufügens oder Entfernens von Bereitstellungspaketen.

Neu aktivierte Richtlinien, die mehr Verwaltungsoptionen für HoloLens 2 Geräte ermöglichen.

- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage)
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

Diese beiden neuen Richtlinien für AllowAddProvisioningPackage und AllowRemoveProvisioningPackage werden unseren [allgemeinen Geräteeinschränkungen](hololens-common-device-restrictions.md)hinzugefügt.

> [!NOTE]
> In Bezug auf [RemoteLock](/windows/client-management/mdm/remotelock-csp)unterstützt HoloLens nur die Konfiguration ./Vendor/MSFT/RemoteLock/Lock. Die Konfigurationen, die pins wie Zurücksetzen und Wiederherstellen behandeln, werden nicht unterstützt.

### <a name="new-power-policies-for-hololens-2"></a>Neue Energierichtlinien für HoloLens 2

- Weitere Optionen, wenn HoloLens über Energierichtlinien in den Energiesparmodus versetzt oder gesperrt wird.

Mit diesen neu hinzugefügten Richtlinien können Administratoren Energiezustände steuern, z. B. Leerlauftimeout. Klicken Sie auf den Link für diese Richtlinie, um mehr über die einzelnen Richtlinien zu erfahren.

|     Link zur Richtliniendokumentation                |     Notizen                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Beispielwert, der in Windows Konfigurations-Designer verwendet werden soll, d. h.`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Beispielwert, der in Windows Konfigurations-Designer verwendet werden soll, d. h.`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Beispielwert für die Verwendung in Windows-Konfigurations-Designer, d.h. 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Beispielwert für die Verwendung in Windows-Konfigurations-Designer, d.h. 100                                                                          |
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Beispielwert, der in Windows Konfigurations-Designer verwendet werden soll, d. h.`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Beispielwert, der in Windows Konfigurations-Designer verwendet werden soll, d. h.`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Diese beiden neuen Richtlinien für DisplayOffTimeoutOnBattery und DisplayOffTimeoutPluggedIn werden unseren [allgemeinen Geräteeinschränkungen](hololens-common-device-restrictions.md)hinzugefügt.

> [!NOTE]
> Stellen Sie für konsistente HoloLens 2 sicher, dass die Werte für DisplayOffTimeoutOnBattery und StandbyTimeoutOnBattery auf den gleichen Wert festgelegt sind. Dasselbe gilt für DisplayOffTimeoutPluggedIn und StandbyTimeoutPluggedIn. Weitere Informationen zum modernen Standbymodus finden Sie [unter Anzeigen, Standbymodus und Ruhezustand von Leerlauftimern.](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers)

### <a name="newly-enabled-update-policies-for-hololens"></a>Neu aktivierte Updaterichtlinien für HoloLens

- Weitere Optionen für die Installation von Updates oder das Deaktivieren der Schaltfläche Updates anhalten, um Updates sicherzustellen.

Diese Updaterichtlinien sind jetzt auf HoloLens 2 Geräten aktiviert:

- [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
- [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
- [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Ausführliche Informationen zu diesen Updaterichtlinien und deren Verwendung für HoloLens Geräte finden Sie hier unter [Verwalten HoloLens Updates.](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Einstellungen Seitensichtbarkeit für HoloLens 2 aktiviert

- Erhöhte Benutzeroberflächensteuerung in der Einstellungen-App, die möglicherweise verwechselt wird, um eine begrenzte Auswahl von Seiten anzuzeigen.

Wir haben nun eine Richtlinie aktiviert, mit der IT-Administratoren entweder verhindern können, dass bestimmte Seiten in der System-Einstellungen-App sichtbar oder zugänglich sind, oder dies für alle Seiten mit Ausnahme der angegebenen Seiten. Klicken Sie auf den folgenden Link, um zu erfahren, wie Sie dieses Feature vollständig anpassen.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Informationen zu den Seiteneinstellungen, die Sie auf HoloLens 2 anpassen können, finden Sie auf der [Seite Einstellungen URIs](settings-uri-list.md).

![Screenshot der Nutzungszeit, die in der Einstellungen-App geändert werden.](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Forschungsmodus

Im Forschungsmodus wird die HoloLens 2 zu einem Tool für die Bildverarbeitung. Im Vergleich zu früheren Editionen hat der Forschungsmodus für HoloLens 2 die folgenden Vorteile:

- Zusätzlich zu Sensoren, die im Forschungsmodus HoloLens (1. Generation) verfügbar gemacht werden, bieten wir jetzt IMU-Sensorzugriff, einschließlich Beschleunigungsmesser, Gyroskop und Magnetometer.
- HoloLens 2 bietet neue Funktionen, die zusammen mit dem Forschungsmodus verwendet werden können. Insbesondere der Zugriff auf artikulierte APIs für Handtracking und Eyetracking, die eine umfangreichere Reihe von Experimenten bereitstellen können.

Forscher haben jetzt die Möglichkeit, den Forschungsmodus auf ihren HoloLens Geräten zu aktivieren, um auf alle diese externen Datenströme von Rohbildsensoren zuzugreifen. Der Forschungsmodus für HoloLens 2 bietet auch Zugriff auf die Messwerte für Beschleunigungsmesser, Gyroskop und Magnetometer. Um die Privatsphäre der Benutzer zu schützen, sind unformatierte Eyetrackingkamerabilder nicht über den Forschungsmodus verfügbar, aber die Blickrichtung ist über vorhandene APIs verfügbar.

Weitere technische Details finden Sie in der Dokumentation zum [Forschungsmodus.](/windows/mixed-reality/research-mode)

### <a name="recording-length-increased"></a>Aufzeichnungslänge erhöht

Aufgrund von Kundenfeedback haben wir die Aufzeichnungslänge von [Mixed Reality-Erfassungen](holographic-photos-and-videos.md)erhöht. Mixed Reality-Erfassungen sind standardmäßig nicht mehr auf 5 Minuten beschränkt, sondern berechnen die maximale Aufzeichnungslänge basierend auf dem verfügbaren Speicherplatz. Das Gerät schätzt die maximale Videoaufzeichnungsdauer basierend auf dem verfügbaren Speicherplatz auf bis zu 80 % des gesamten Speicherplatzes.

> [!NOTE]
> Der HoloLens verwendet die Standardlänge der Videoaufzeichnung (5 Minuten), wenn einer der folgenden Vorgänge auftritt:
>
> - Die geschätzte maximale Aufzeichnungsdauer ist kleiner als die Standarddauer von 5 Minuten.
> - Der verfügbare Speicherplatz beträgt weniger als 20 % des gesamten Speicherplatzes.

Die vollständigen Anforderungen finden Sie in unserer Dokumentation [zu holografischen Fotos und Videos.](holographic-photos-and-videos.md#maximum-recording-length)

### <a name="improvements-and-fixes-in-the-windows-holographic-version-20h2-update"></a>Verbesserungen und Fehlerbehebungen im Windows Holographic-Update, Version 20H2:

- Weitere Bildschirme in OOBE befinden sich jetzt im dunklen Modus.
- Weitere Informationen finden Sie in den aktuellen Onlinedatenschutzerklärungen.
- Es wurde ein Problem behoben, bei dem Benutzer VPN-Profile nicht über Bereitstellungspakete bereitstellen konnten.
- Proxykonfigurationsproblem für VPN-Verbindung behoben.
- Aktualisierte Richtlinie zum Deaktivieren der Enumeration von USB-Funktionen über MDM für NCM für AllowUsbConnection.
- Es wurde ein Problem behoben, das verhinderte, dass ein HoloLens Gerät im [Datei-Explorer](hololens-kiosk.md)über das Media Transfer Protocol (MTP) angezeigt wurde, wenn das Gerät als Kiosk mit einer einzelnen App eingerichtet wurde. Beachten Sie, dass MTP (und usb-Verbindung im Allgemeinen) weiterhin mithilfe der [AllowUSBConnection-Richtlinie](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) deaktiviert werden können.
- Ein Problem wurde behoben, bei dem Symbole im Startmenü im Kioskmodus ordnungsgemäß skaliert wurden.
- Ein Problem wurde behoben, das darauf zurückzuführen ist, dass die HTTP-Zwischenspeicherung den Kioskmodus beeinträchtigt, der auf Azure AD Gruppen ausgerichtet ist.
- Ein Problem wurde behoben, bei dem Benutzer die Schaltfläche Koppeln nicht verwenden konnten, nachdem sie den Entwicklermodus mit Bereitstellungspaketen aktiviert haben, es sei denn, sie haben den Entwicklermodus deaktiviert und wieder aktiviert.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, Version 1903 – Update vom November 2020

- Build 18362.1085

Dieses monatliche Qualitätsupdate enthält keine wichtigen Änderungen. Wir empfehlen Ihnen, unseren neuesten Build für feature release Windows Holographic, Version 20H2, auszuprobieren.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, Version 2004 – Oktober 2020 Update

- Build 19041.1124

Verbesserungen und Fehlerbehebungen im Update:

- Eine unnötige Überprüfung, die einen Laufzeitsystemfehler verursacht hat, wurde entfernt.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, Version 1903 – Oktober 2020 Update

- Build 18362.1081

Dieses monatliche Qualitätsupdate enthält keine wichtigen Änderungen. Wir empfehlen Ihnen, unsere neuesten Builds für Windows Holographic, Version 2004, auszuprobieren.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, Version 2004 – September 2020 Update

- Build 19041.1117

Verbesserungen und Fehlerbehebungen im Update:

- Behebt ein Problem, das verhindert hat, dass Visual Studio eine Anwendung debuggt, wenn SupportsMultipleInstances="true" im appxmanifest vorhanden ist.
- Dieses Release enthält eine Korrektur der NCSI-Proxyerkennung, um die fehlerhafte Interneterkennung über den Netzwerkproxy zu beheben. NCSI kann einen Computerproxy und profilbasierten Proxy für die Erkennung von Internetkonnektivität verwenden. Der Pro-Benutzer-Proxy wird in der zukünftigen Version von NCSI unterstützt.
- Auf den meisten Windows Mixed Reality Geräten ist der Vorwärtsrichtungsvektor parallel zum Boden, wenn sich der Kopf des Benutzers in einer neutralen Position befindet, die nach vorne blickt. Frühere Versionen von HoloLens 2 den Vektor jedoch so ausgerichtet, dass er stattdessen den Anzeigepanels entspricht, die relativ zur idealen Ausrichtung einige Grad nach unten geneigt sind. Neuere Versionen von HoloLens 2 haben dies korrigiert, um semantische Konsistenz über Formularfaktoren hinweg sicherzustellen.
- Verbesserte Handtrackingstabilität, die in bestimmten Szenarien zu weniger Nachverfolgungsverlusten führt.
- Dieses Release enthält eine Korrektur zur Verbesserung der Qualität des Audiozeitstempels, die möglicherweise zu Problemen bei der Videoaufzeichnung beigetragen hat.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, Version 1903 – Update vom September 2020

- Build 18362.1079

Verbesserungen und Fehlerbehebungen im Update:

- Auf den meisten Windows Mixed Reality Geräten ist der Vorwärtsrichtungsvektor parallel zum Boden, wenn sich der Kopf des Benutzers in einer neutralen Position befindet, die nach vorne blickt. Frühere Versionen von HoloLens 2 den Vektor jedoch so ausgerichtet, dass er stattdessen den Anzeigepanels entspricht, die relativ zur idealen Ausrichtung einige Grad nach unten geneigt sind. Neuere Versionen von HoloLens 2 haben dies korrigiert, um semantische Konsistenz über Formularfaktoren hinweg sicherzustellen.
- Verbesserte Handtrackingstabilität, die in bestimmten Szenarien zu weniger Nachverfolgungsverlusten führt.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, Version 2004 – Update vom August 2020

- Build 19041.1113

Verbesserungen und Fehlerbehebungen im Update:

- Einstellungen App folgt dem Benutzer nicht mehr in iris-Registrierungs- oder Eye Tracking-Kalibrierungserfahrungen.
- Ein Fehler wurde behoben, bei dem das Anwenden eines Bereitstellungspakets während der Oobe, das das Gerät umbenennt und andere Aktionen ausführt (z. B. das Herstellen einer Verbindung mit einem Netzwerk), nach dem Neustart des Geräts aufgrund einer Umbenennung die anderen Aktionen nicht ausführen kann.
- Das Farbschema der anfänglichen Geräteeinrichtungsflows wurde geändert, um die visuelle Qualität zu verbessern.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, Version 1903 – Update vom August 2020

- Build 18362.1074

Dieses monatliche Qualitätsupdate enthält keine wichtigen Änderungen. Wir empfehlen Ihnen, unsere neuesten Builds für Windows Holographic, Version 2004, auszuprobieren.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, Version 2004 – Update vom Juli 2020

- Build 19041.1109

Verbesserungen und Fehlerbehebungen im Update:

- Entwickler können jetzt zwischen dem Aktivieren oder Deaktivieren von Geräteportal benötigen eine sichere Verbindung wählen.
- Die Zuverlässigkeit für Anwendungsstarts nach Betriebssystemupdates wurde verbessert.
- Standard-Eingangsbox-Helligkeit wurde in 100 Prozent geändert.
- Es wurde ein Problem mit der HTTPS-Weiterleitung für die Windows Geräteportal auf HoloLens 2 behoben.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, Version 1903 – Update vom Juli 2020

- Build 18362.1071

Verbesserungen und Fehlerbehebungen im Update:

- Ein Problem wurde behoben, das dazu führen konnte, dass Hologramme in Unity-Anwendungen nicht mehr angezeigt werden, wenn die Nachverfolgung verloren geht oder wiedererlangt wird.
- Ein Problem wurde behoben, das dazu führte, dass exklusive HoloLens-Apps bei Verwendung des HoloLens Emulator mit Hardwarebeschleunigung auf bestimmten Geräten wieder auf die Shell abstürzten.
- Es wurde ein Problem in Bezug auf die HTTPS-Weiterleitung für die Windows Geräteportal auf HoloLens 2 behoben.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, Version 2004 – Juni 2020 Update

- Build 19041.1106

Verbesserungen und Fehlerbehebungen im Update:

- Benutzerdefinierte MRC-Aufzeichnungen verfügen jetzt über neue Standardwerte für bestimmte Eigenschaften, wenn sie nicht angegeben werden.
  - Auf dem *MRC-Videoeffekt:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (immersives Headset))
  - Auf dem *MRC-Audioeffekt:*
    - LoopbackGain (der aktuelle Wert "App-Audiogewinn" auf der Mixed Reality-Aufnahme Seite in Windows Geräteportal)
    - MicrophoneGain (der aktuelle Wert "Mikrofonaudiogewinn" auf der Mixed Reality-Aufnahme Seite in Windows Geräteportal)
- Ein Fehler zur Verbesserung der Audioqualität in Mixed Reality-Erfassungsszenarien wurde behoben. Durch diese Korrektur sollte insbesondere die Audiowiedergabe in der Aufzeichnung vermieden werden, wenn das **Startmenü** angezeigt wird.
- Verbesserte Hologrammstabilität in aufgezeichneten Videos.
- Ein Problem wurde behoben, bei dem die Mixed Reality-Erfassung das Video nicht aufzeichnen konnte, nachdem das Gerät mehrere Tage lang im Standbyzustand war.
- Die HolographicSpace.UserPresence-API ist in der Regel für Unity-Anwendungen deaktiviert. Dieses Verhalten vermeidet ein Problem, das dazu geführt hat, dass einige Apps angehalten wurden, wenn das Visier nach oben gekippt wurde, auch wenn die Einstellung "Im Hintergrund ausführen" aktiviert war. Die API ist jetzt für unity-Versionen 2018.4.18 und höher und 2019.3.4 und höher aktiviert.
- Wenn Sie über eine Wi-Fi Verbindung auf Geräteportal zugreifen, kann ein Webbrowser den Zugriff auf aufgrund eines ungültigen Zertifikats verhindern. Der Browser meldet möglicherweise einen Fehler wie "ERR_SSL_PROTOCOL_ERROR", auch wenn das Gerätezertifikat zuvor als vertrauenswürdig eingestuft wurde. In diesem Fall können Sie nicht zu Geräteportal, da es keine Option zum Ignorieren von Sicherheitswarnungen gibt. Dieses Update hat das Problem behoben. Wenn das Gerätezertifikat zuvor heruntergeladen und auf einem PC als vertrauenswürdig eingestuft wurde, um Browsersicherheitswarnungen zu entfernen, und der SSL-Fehler auftritt, muss das neue Zertifikat heruntergeladen und als vertrauenswürdig eingestuft werden, um Sicherheitswarnungen des Browsers zu beheben.
- Ermöglicht das Erstellen eines Laufzeitbereitstellungspakets, das eine App mithilfe von MSIX-Paketen installieren kann.
- In **Einstellungen** System Hologramme wurde eine Einstellung hinzugefügt, mit der  >    >   Benutzer beim Herunterfahren des Geräts automatisch alle Hologramme aus Mixed Reality Startseite entfernen können.
- Es wurde ein Problem behoben, das dazu führte, dass HoloLens Apps ihr Pixelformat so geändert haben, dass sie im HoloLens Emulator schwarz gerendert werden.
- Ein Fehler wurde behoben, der während der Iris-Anmeldung einen Absturz verursacht hat.
- Ein Problem mit wiederholten Storedownloads für bereits aktuelle Apps wurde behoben.
- Ein Fehler wurde behoben, der verhinderte, dass immersive Apps Microsoft Edge wiederholt öffnen.
- Es wurde ein Problem mit dem Starten der Fotos-App beim ersten Start nach dem Update vom Release 1903 behoben.
- Verbesserte Leistung und Zuverlässigkeit.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, Version 1903 – Juni 2020 Update

- Build 18362.1064

Verbesserungen und Fehlerbehebungen im Update:

- Benutzerdefinierte MRC-Aufzeichnungen verfügen über neue Standardwerte für bestimmte Eigenschaften, wenn sie nicht angegeben werden.
  - Auf dem *MRC-Videoeffekt:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (immersives Headset))
  - Auf dem *MRC-Audioeffekt:*
    - LoopbackGain (der aktuelle Wert "App-Audiogewinn" auf der Mixed Reality-Aufnahme Seite in Windows Geräteportal)
    - MicrophoneGain (der aktuelle Wert "Mikrofonaudiogewinn" auf der Mixed Reality-Aufnahme Seite in Windows Geräteportal)
- Die HolographicSpace.UserPresence-API ist in der Regel für Unity-Anwendungen deaktiviert. Dieses Verhalten vermeidet ein Problem, das dazu führt, dass einige Apps angehalten werden, wenn das Visier nach oben gedreht wird, auch wenn die Einstellung für die Ausführung im Hintergrund aktiviert ist. Die API ist jetzt für unity-Versionen 2018.4.18 und höher und 2019.3.4 und höher aktiviert.
- Es wurde ein Problem behoben, das dazu führte, dass HoloLens Apps ihr Pixelformat so geändert haben, dass sie im HoloLens Emulator schwarz gerendert werden.
- Es wurde ein Problem mit dem Starten der Fotos-App beim ersten Start nach dem Update von Version 1903 behoben.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, Version 2004

- Build: 19041.1103

Das wichtige Softwareupdate von Mai 2020 für HoloLens 2, *Windows Holographic, Version 2004* enthält eine Vielzahl von interessanten neuen Funktionen, z. B. Unterstützung für Windows Autopilot, den dunklen App-Modus, USB Ethernet-Unterstützung für 5G/GIGABIT-Hotspots und vieles mehr. Um auf das neueste Release zu aktualisieren, öffnen Sie die   Einstellungen-App, wechseln Sie zu **Update & Security**, und wählen Sie die Schaltfläche Nach Updates **suchen**   aus. 

|             Funktion                              |          BESCHREIBUNG                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Vorkonfigurieren und nahtloses Einrichten neuer Geräte für die Produktion mithilfe von Windows AutoPilot                 |
|       FIDO 2-Unterstützung                             |          Unterstützung für FIDO2-Sicherheitsschlüssel, um eine schnelle und sichere Authentifizierung für freigegebene Geräte zu ermöglichen            |
|       Verbesserte Bereitstellung                      |          Nahtloses Anwenden eines Bereitstellungspakets von einem USB-Laufwerk auf Ihre HoloLens                              |
|       Anwendungsinstallationsstatus                 |          Überprüfen des Installationsstatus in der Einstellungen-App für Apps, die per Push über MDM an HoloLens 2 übertragen wurden               |
|       Konfigurationsdienstanbieter (Configuration Service Providers, CSPs)   |          Neue Konfigurationsdienstanbieter hinzugefügt, um die Verwaltungsfunktionen zu verbessern                 |
|       USB 5G/LTE-Unterstützung                       |          Erweiterte USB-Ethernet-Funktion ermöglicht Unterstützung für 5G/HEADSET                                    |
|       Dunkler App-Modus                              |          Dunkler App-Modus für Apps verfügbar, die sowohl dunkle als auch helle Modi unterstützen, um die Anzeige zu verbessern        |
|       Sprachbefehle                             |          Unterstützung für zusätzliche Systemstimmenbefehle zum Steuern HoloLens Freihandsteuerung                           |
|       Verbesserungen bei der Handnachverfolgung                 |          Verbesserungen der Handnachverfolgung verbessern die Genauigkeit von Schaltflächen und 2D-Slateinteraktionen                        |
|       Qualitätsverbesserungen und Fehlerbehebungen                 |          Verschiedene Verbesserungen der Systemleistung und -zuverlässigkeit auf der gesamten Plattform                            |

### <a name="support-for-windows-autopilot"></a>Unterstützung für Windows Autopilot

Windows Autopilot für HoloLens 2 ermöglicht dem Geräteverkaufskanal die Vorab-Registrierung HoloLens Intune-Mandanten. Wenn Geräte eintreffen, können sie selbst als freigegebene Geräte unter Ihrem Mandanten bereitgestellt werden. Um die Selbstbereitstellung nutzen zu können, muss das Gerät während des ersten Bildschirms im Setup mithilfe eines USB-C-to-Ethernet-Geräts eine Verbindung mit einem Netzwerk herstellen.

Nachdem ein Benutzer den Autopilot-Self-Deploying-Prozess gestartet hat, werden die folgenden Schritte abgeschlossen:

1. Verbinden des Geräts mit Azure Active Directory (Azure AD).
1. Verwenden Azure AD, um das Gerät bei Microsoft Intune (oder einem anderen MDM-Dienst) zu registrieren.
1. Laden Sie die gerätespezifischen Richtlinien, Zertifikate und Netzwerkprofile herunter.
1. Bereitstellen des Geräts.
1. Stellen Sie dem Benutzer den Anmeldebildschirm vor.

Weitere Informationen finden Sie im Windows Autopilot for HoloLens 2 Evaluation Guide (Leitfaden zur [Evaluierung von Autopilot für HoloLens 2).](hololens2-autopilot.md)

*Wenden Sie sich an Ihren Konto-Manager, um jetzt an der AutoPilot-Vorschau teilzu nehmen. Für Autopilot bereite Geräte werden bald mit dem Versand beginnen.*

### <a name="fido2-security-key-support"></a>FIDO2-Sicherheitsschlüsselunterstützung

Einige Benutzer geben ein HoloLens-Gerät für andere Benutzer in einer Arbeits- oder Schulumgebung weiter. Daher ist es wichtig, dass Benutzer problemlos lange Benutzernamen und Kennwörter eingeben müssen. Mit Fast Identity Online (FIDO) können sich alle Benutzer in Ihrer Organisation (Azure AD-Mandant) nahtlos bei HoloLens anmelden, ohne einen Benutzernamen oder ein Kennwort eingeben zu müssen.

FIDO2-Sicherheitsschlüssel sind eine "unphishable" standardbasierte kennwortlose Authentifizierungsmethode, die in jedem Formfaktor verwendet werden kann. FIDO ist ein offener Standard für die kennwortlose Authentifizierung. Dadurch können sich Benutzer und Organisationen ohne Benutzernamen oder Kennwort bei ihren Ressourcen anmelden. Stattdessen verwenden sie einen externen Sicherheitsschlüssel oder einen in ein Gerät integrierten Plattformschlüssel.

Informationen zu den ersten Schritte finden Sie unter [Aktivieren der Anmeldung mit kennwortlosem Sicherheitsschlüssel.](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Verbesserte MDM-Registrierung per Bereitstellungspaket

Mithilfe von Bereitstellungspaketen HoloLens Konfiguration über eine Konfigurationsdatei und nicht über die HoloLens standardbasierte Begehung festlegen. Zuvor mussten Bereitstellungspakete in den internen HoloLens kopiert werden. Jetzt können sie sich auf einem USB-Laufwerk speichern, sodass sie einfacher auf mehreren HoloLens-Geräten wiederverwendet werden können, und Sie können Geräte parallel bereitstellen. Bereitstellungspakete unterstützen jetzt auch ein Feld für die Registrierung bei der Geräteverwaltung, sodass nach der Bereitstellung keine manuelle Einrichtung mehr erforderlich ist.

So können Sie es ausprobieren:

1. Laden Sie die neueste Version des Windows-Konfigurations-Designers aus dem Windows auf Ihren PC herunter.
1. Wählen **Sie Provision HoloLens Devices** Provision HoloLens 2 devices  >  **(Geräte HoloLens 2 bereitstellen) aus.**
1. Erstellen Sie Ihr Konfigurationsprofil. Kopieren Sie dann alle Dateien, die auf ein USB-C-Speichergerät erstellt wurden.
1. Schließen Sie das USB-C-Gerät an alle neu aufb blinkenden HoloLens. Drücken Sie dann die **Netztasten**  +  **des** Volumes, um Ihr Bereitstellungspaket anzuwenden.

### <a name="line-of-business-application-install-status"></a>Installationsstatus der line-of-business-Anwendung

Die Bereitstellung und Verwaltung von MDM-Apps für line-of-business-Apps ist wichtig für HoloLens. Administratoren und Benutzer müssen den App-Installationsstatus für die Überwachung und Diagnose anzeigen. In dieser Version haben wir weitere Details hinzugefügt, Einstellungen Kontozugriff auf Arbeits- oder Schulkonto  >    >    >  **Klicken Sie auf Ihre**  >  **Kontoinformationen.**

### <a name="additional-csps-and-policies"></a>Zusätzliche CSPs und Richtlinien

Ein [Konfigurationsdienstanbieter (Configuration Service Provider, CSP)](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) ist eine Schnittstelle zum Lesen, Festlegen, Ändern oder Löschen von Konfigurationseinstellungen auf einem Gerät. In dieser Version fügen wir Unterstützung für weitere Richtlinien hinzu, um die Kontrolle zu erhöhen, die Administratoren über HoloLens bereitgestellt haben. Eine Liste der csps, die von HoloLens unterstützt werden, finden Sie unter [NetworkQoSPolicy CSP](/windows/client-management/mdm/networkqospolicy-csp).

Neu in dieser Version:

**Policy CSP** 

Der Richtlinienkonfigurations-Dienstanbieter ermöglicht dem Unternehmen das Konfigurieren von Richtlinien auf Windows Geräten. In dieser Version haben wir neue Richtlinien für HoloLens hinzugefügt, die hier aufgeführt sind. Weitere Informationen finden Sie unter [Richtlinien-CSPs, die von HoloLens 2.](/windows/client-management/mdm/policies-supported-by-hololens2)  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps
- LetAppsAccessAccessAccesseInput
- LetAppsAccessGazeInput_ForceAllowTheseApps
- LetAppsAccessGazeInput_ForceDenyTheseApps
- LetAppsAccessGazeInput_UserInControlOfTheseApps
- LetAppsAccessMicrophone_ForceAllowTheseApps
- LetAppsAccessMicrophone_ForceDenyTheseApps
- LetAppsAccessMicrophone_UserInControlOfTheseApps
- AllowWiFi

**NetworkQoSPolicy-CSP**

Der NetworkQoSPolicy-Konfigurationsdienstanbieter erstellt QoS-Richtlinien (Network Quality of Service). Eine QoS-Richtlinie führt eine Reihe von Aktionen für den Netzwerkdatenverkehr basierend auf einer Reihe von Abgleichsbedingungen aus. Weitere Informationen finden Sie unter [NetworkQoSPolicy CSP](/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Erweiterte USB-Ethernet-Unterstützung für 5G/ETHERNET-Tethergeräte

Es wurde Unterstützung hinzugefügt, um bestimmte mobile Breitbandgeräte zu aktivieren, z. B. 5G/SPEED-Telefone und Wi-Fi-Hotspots, wenn sie über USB an die HoloLens 2 werden. Diese Geräte werden jetzt in den **Netzwerkeinstellungen als** eine andere Ethernet-Verbindung angezeigt. (Mobile Breitbandgeräte, die einen externen Treiber erfordern, werden nicht unterstützt.) Diese Funktion ermöglicht Verbindungen mit hoher Bandbreite, Wi-Fi nicht verfügbar ist und Wi-Fi tethering nicht ausreichend leistungsfähigkeit ist. Weitere Informationen zu unterstützten USB-Geräten finden Sie unter [Verbinden zum Bluetooth und USB-C-Geräten.](hololens-connect-devices.md)  

### <a name="hand-tracking-improvements"></a>Verbesserungen bei der Handnachverfolgung

Dieses Release umfasst mehrere Verbesserungen der Handverfolgung:

- **Pointing-Pose-Stabilität:** Das System spricht sich jetzt dagegen aus, den Zeigefinger zu beugen, wenn er von der Handfläche verblendet wird. Diese Änderung verbessert die Genauigkeit beim Drücken von Schaltflächen, Eingeben, Scrollen von Inhalten und mehr! 
- **Reduziertes versehentliches Tippen in die Luft:** Wir haben die Erkennung der Tippbewegung in die Luft verbessert. Es gibt jetzt weniger versehentliche Aktivierungen in mehreren gängigen Szenarien, z. B. wenn Sie ihre Hände auf Ihre Seiten legen.
- **Zuverlässigkeit des Benutzerwechsels:** Das System ist jetzt schneller und zuverlässiger bei der Aktualisierung der Handgröße, wenn Sie ein Gerät freigeben.
- **Reduziertes Handdiebstahl:** Wir haben die Behandlung von Fällen verbessert, in denen die Sensoren mehr als zwei Hände im Blick haben. Wenn mehrere Personen nah beieinander arbeiten, ist die Wahrscheinlichkeit deutlich geringer, dass die nachverfolgte Hand vom Benutzer zur Hand einer anderen Person in der Szene "springt".
- **Systemzuverlässigkeit:** Es wurde ein Problem behoben, das dazu führte, dass die Handverfolgung nicht mehr funktionierte, wenn das Gerät unter hoher Auslastung war.

### <a name="dark-mode"></a>Dunkler Modus

Viele Windows-Apps unterstützen jetzt sowohl den dunklen als auch den hellen Modus. HoloLens 2 Können Benutzer den Standardmodus für Apps auswählen, die beide unterstützen. Nach dem Update ist der Standard-App-Modus "dunkel", aber Sie können diese Einstellung problemlos ändern: Navigieren Sie zu Einstellungen Systemfarben Wählen Sie Ihren Standard-App-Modus  >    >    >  **aus.**

Diese "in-Box"-Apps unterstützen den dunklen Modus:

- Einstellungen
- Microsoft Store
- E-Mail
- Kalender
- Datei-Explorer
- Feedback-Hub
- OneDrive
- Fotos
- 3D-Betrachter
- Filme & TV

![Fenster im dunklen Modus sind gekachelt.](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Systemstimmenbefehle

Sie können nun Sprachbefehle mit jeder App auf dem Gerät verwenden. Weitere Informationen finden Sie unter [Verwenden Ihrer Stimme zum Betreiben HoloLens](hololens-cortana.md). Siehe auch [Unterstützte Sprachen für HoloLens 2](hololens2-language-support.md).  

### <a name="cortana-updates"></a>Cortana Updates

Die aktualisierte App kann in Microsoft 365 integriert werden, damit Sie ihre Geräte besser nutzen können (derzeit nur in US-English verfügbar). Auf HoloLens 2 unterstützt Cortana gerätespezifische Befehle nicht mehr, z. B. das Anpassen des Volumes oder neustarten. Diese Optionen werden jetzt von den neuen Systemstimmenbefehlen unterstützt. Weitere Informationen zur neuen Cortana-App finden Sie in unserem [Blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Qualitätsverbesserungen und Fehlerbehebungen

Verbesserungen und Fehlerbehebungen auch im Update:  

- Ein aktives Kalibrierungssystem für die Anzeige wurde eingeführt. Dieses Feature verbessert die Stabilität und Ausrichtung von Hologrammen. Sie bleiben nun an Ort und Stelle, wenn Sie den Kopf von Seite zu Seite bewegen.
- Ein Fehler wurde behoben, Wi-Fi streaming to HoloLens in regelmäßigen Abständen unterbrochen wurde. Wenn eine Anwendung angibt, dass streaming mit geringer Latenz benötigt wird, implementieren Sie die Korrektur, indem Sie die [SetSocketMediaStreamingMode-Funktion aufrufen.](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)
- Ein Gerät, das während des Streamings im Forschungsmodus nicht mehr verfügbar war, wurde behoben.
- Es wurde ein Fehler behoben, bei dem in einigen Fällen der richtige Benutzer beim Fortsetzen einer Sitzung nicht auf dem Anmeldebildschirm angezeigt wurde.
- Es wurde ein Problem behoben, bei dem Benutzer MDM-Protokolle nicht über **Einstellungen.**
- Es wurde ein Problem behoben, bei dem die Genauigkeit der Blickverfolgung unmittelbar nach der vorgeschachtelten Einrichtung niedriger als erwartet sein konnte.
- Es wurde ein Problem behoben, bei dem das Eyetrackingsubsystem unter bestimmten Bedingungen nicht initialisiert oder kalibriert werden konnte.
- Es wurde ein Problem behoben, bei dem die Kalibrierung der Augen für einen bereits kalibrierten Benutzer angezeigt wurde.
- Es wurde ein Problem behoben, bei dem ein Treiber während der Kalibrierung der Augen abstürzte.
- Es wurde ein Problem behoben, bei dem wiederholtes Drücken des Netzschalters zu einem Systemzeitüberschreitungs- und Shellabsturz von 60 Sekunden führen konnte.
- Verbesserte Stabilität für Tiefenpuffer.
- Im Bereich **wurde eine Schaltfläche** Freigeben hinzugefügt Feedback-Hub damit Benutzer leichter Feedback senden können.
- Es wurde ein Fehler behoben, bei dem RoboRaid wan nicht ordnungsgemäß installiert wurde.

### <a name="known-issues"></a>Bekannte Probleme

- Ein Problem mit der Zh-CN-Systemsprache verhindert, dass Sprachbefehle eine Mixed Reality-Erfassung ausführen oder die IP-Adresse des Geräts anzeigen.
- Ein Problem erfordert, dass Sie die Cortana-App starten, nachdem Sie das Gerät gestartet haben, um die Sprachaktivierung "Hey Cortana" zu verwenden. Wenn Sie von einem Build 18362 aktualisiert haben, wird möglicherweise auch eine zweite App-Kachel für die vorherige Version der Cortana-App angezeigt, die in Start nicht mehr **funktioniert.**

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, Version 1903 – Update vom Mai 2020

- Build 18362.1061

Dieses monatliche Qualitätsupdate enthält keine wichtigsten Änderungen, da das Team an der Windows Holographic Version 2004 May Update arbeitet, wie zuvor beschrieben.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, Version 1903 – Update april 2020

- Build 18362.1059

**Dunkler Modus für unterstützte Apps**

Viele Windows-Apps unterstützen sowohl den dunklen als auch den hellen Modus. HoloLens 2 Können Kunden jetzt den Standardmodus für Apps auswählen, die beide Farbschemas unterstützen. Basierend auf Kundenfeedback legen wir den Standard-App-Modus auf "dunkel" fest, aber Sie können diese Einstellung jederzeit problemlos ändern: Navigieren Sie zu **Einstellungen > System > Colors,** um nach **"Choose your default app mode"** (Standard-App-Modus auswählen) zu suchen.

Diese "in-Box"-Apps unterstützen den dunklen Modus:

- Einstellungen
- Microsoft Store
- E-Mail
- Kalender
- Datei-Explorer
- Feedback-Hub
- OneDrive
- Fotos
- 3D-Betrachter
- Filme & TV

**Verbesserungen und Fehlerbehebungen auch im Update:**

- Es wurde sichergestellt, dass Shellüberlagerungen in Mixed Reality-Erfassungen enthalten sind.
- Unreal-Entwickler können jetzt die 3D-Ansichtsseite in Geräteportal um ihre Anwendungen zu testen und zu debuggen.
- Verbesserte Hologrammstabilität bei der Mixed Reality-Erfassung, wenn der *HolographicDepthReprojectionMethod DepthReprojection-Algorithmus* verwendet wird.
- Der Fehler "WinRT IStreamSocketListener API Class not registered" (WinRT-IStreamSocketListener-API-Klasse nicht registriert) für 32-Bit-ARM-Apps wurde behoben.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, Version 1903 – Update vom März 2020

- Build 18362.1056

Verbesserungen und Fehlerbehebungen im Update:

- Verbesserte Hologrammstabilität bei der Mixed Reality-Erfassung, wenn der *AutoPlanar-Algorithmus HolographicDepthReprojectionMethod* verwendet wird.
- Es wurde sichergestellt, dass das Koordinatensystem, das an ein MF-Tiefenbeispiel angefügt ist, mit der öffentlichen Dokumentation konsistent ist.
- Die Produktivität von Entwicklern wurde verbessert, da Kunden große Mengen von Text über das Geräteportal einfügen können.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, Version 1903 – Update vom Februar 2020

- Build 18362.1053

Verbesserungen und Fehlerbehebungen im Update:

- Die HolographicSpace.UserPresence-API für Unity-Anwendungen wurde vorübergehend deaktiviert. Durch diese Änderung wird ein Problem vermieden, das dazu führte, dass einige Apps angehalten wurden, wenn das Visor gekippt wurde, auch wenn die Einstellung "Im Hintergrund ausführen" aktiviert wurde.
- Es wurde ein zufälliger HUP-Absturz behoben, der durch die Handverfolgung verursacht wurde, bei dem der Benutzer bemerkte, dass die Benutzeroberfläche erst nach einigen Sekunden einfriert und dann wieder in die Shell übergestürzt ist.
- Die Handnachverfolgung wurde verbessert, sodass der obere Teil dieses Fingers beim Pokeen mit dem Zeigefinger weniger wahrscheinlich unerwartet gelockt wird.
- Verbesserte Zuverlässigkeit von Head Tracking, räumlicher Zuordnung und anderen Laufzeiten.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, Version 1903 – Update vom Januar 2020

- Build 18362.1043

Verbesserungen und Fehlerbehebungen im Update:

- Verbesserte Stabilität für exklusive Apps bei der Arbeit mit dem HoloLens 2 Emulator.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, Version 1903 – Update vom Dezember 2019

- Build 18362.1042

Verbesserungen und Fehlerbehebungen im Update:

- LSR-Korrekturen (Last Stage Veröffentlichung) wurden eingeführt. Verbessertes visuelles Rendering von Hologrammen, um stabiler und präziser zu erscheinen, indem die Tiefe genauer abbucht. Dieses Symptom ist nach diesem Update deutlicher, wenn Apps die Tiefe der Hologramme nicht richtig festlegen.
- Die Stabilität exklusiver Apps und die Navigation zwischen exklusiven Apps wurden korrigiert.
- Es wurde ein Problem behoben, bei dem die Mixed Reality-Erfassung kein Video aufzeichnen konnte, nachdem sich das Gerät mehrere Tage lang im Standbyzustand befindet.
- Verbesserte Hologrammstabilität.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, Version 1903 – Update vom November 2019

- Build 18362.1039

Verbesserungen und Fehlerbehebungen im Update:

- Die Funktionalität von **Select** voice commands during initial setup for en-CA and en-AU wurde behoben.
- Verbesserte visuelle Qualität von Objekten, die weit entfernt in den neuesten Versionen von Unity und Mixed Reality Toolkit (MRTK) platziert sind.
- Behoben: Probleme mit holografischen Anwendungen, die beim Start in einem angehaltenen Zustand hängen bleiben, bis die Startmenü geöffnet und dann geschlossen wurde.
- Korrekturen und Verbesserungen der Konformität mit OpenXR-Runtime für HoloLens 2 und den Emulator.
