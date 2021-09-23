---
title: Insider Preview für Microsoft HoloLens
description: Erfahren Sie, wie Sie mit Insider-Builds beginnen, und geben Sie wertvolles Feedback zu unserem nächsten wichtigen Betriebssystemupdate für HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 09/14/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 22d635fd3fc32b8aedc36bcb19d900128cdcb718
ms.sourcegitcommit: ab86b31357004726d8a28ebae76123728adc8e59
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2021
ms.locfileid: "128306164"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview für Microsoft HoloLens

Willkommen bei den neuesten Insider Preview-Builds für HoloLens! Es ist einfach, mit den [ersten](hololens-insider.md#start-receiving-insider-builds) Schritten zu beginnen und wertvolles Feedback für unser nächstes größeres Betriebssystemupdate für HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Insider-Versionshinweise

Wir freuen uns, mit der Entwicklung neuer Features für Windows Insider beginnen zu können. Neue Builds werden an die Entwicklungs- und Betakanäle übertragen, um die neuesten Updates zu erhalten. Wir werden diese Seite weiterhin aktualisieren, wenn wir weitere Features und Updates zu unseren Windows Insider-Builds hinzufügen. Lassen Sie sich freuen und bereit sein, diese Updates in Ihre Realität zu mischen.

In diesem Thema geht es um die verbesserte Problembehandlung und Geräteberichte, einige behobene Fehler im Kioskmodus und den Zertifikat-Viewer, die erweiterte Verwaltbarkeitsoberfläche und die erhöhte Updatezuverlässigkeit. Ein neues Feature dieses Featureupdates, das in HoloLens ist unser Moving Platform Mode. Sehen Sie sich alle neuen großartigen Features für HoloLens 2!

| Funktion                 | BESCHREIBUNG                | Benutzer oder Szenario | Build eingeführt |
|-------------------------|----------------------------|--------------|------------------|
| [Verschieben des Plattformmodus](#moving-platform-mode) | Führt die Betaversion des Moving Platform Mode ein, die, wenn sie konfiguriert ist, die Verwendung von HoloLens 2 bei großen, dynamischen Bewegungsabläufen ermöglicht. | All | 20348.1411 |
| [PFX-Dateiunterstützung für den Zertifikat-Manager](#pfx-file-support-for-certificate-manager) | Hinzufügen von PFX-Zertifikaten über Einstellungen Benutzeroberfläche | Endbenutzer | 20348.1405 |
| [Anzeigen des erweiterten Diagnoseberichts in Einstellungen auf HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Anzeigen von MDM-Diagnoseprotokollen auf dem Gerät | Problembehandlung | 20348.1405 |
| [Offlinediagnosebenachrichtigungen](#offline-diagnostics-notifications) | Feedback zur Protokollsammlung | Problembehandlung | 20348.1405 |
| [Verbesserungen bei der Erfassung von Protokollen mit geringem Speicher](#low-storage-log-collection-improvements) | Verbesserungen an Protokollsammlungsszenarien in Situationen mit geringem Speicher. | Problembehandlung | 20348.1412 |
| [CSP-Änderungen für die HoloLens Details](#csp-changes-for-reporting-hololens-details) | Neue CSPs für zum Abfragen von Daten | IT-Administratoren    | 20348.1403                 |
| [Richtlinie für die automatische Anmeldung, die von CSP gesteuert wird](#auto-login-policy-controlled-by-csp) | Wird zum automatischen Anmelden eines Kontos verwendet. | IT-Administratoren | 20348.1405 |
| [Verbesserte Erkennung von Updateneustarts und Benachrichtigungen](#improved-update-restart-detection-and-notifications) | Neue aktivierte Richtlinien und Beux für Updates. | IT-Administratoren | 20348.1405 |
| [Smart Retry für App-Updates](#smart-retry-for-app-updates) | Ermöglicht IT-Administratoren geplante Erneutes Aktualisieren von Apps. | IT-Administratoren | 20348.1405 |
| [Verwenden Sie nur private Store-Apps nur für Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Konfigurieren der Store-App, um nur Apps aus der Organisation anzeigen zu können | IT-Administrator | 20348.1408 |
| [Verwenden von WDAC- und LOB-Apps](#use-wdac-and-lob-apps) | Ermöglicht IT-Administratoren, ihre eigenen Apps zu verwenden und weiterhin WDAC zu verwenden, um andere Apps zu blockieren. | IT-Administratoren | 20348.1405 |
| [Fehlerbehebungen und Verbesserungen](#fixes-and-improvements) | Korrekturen und Verbesserungen für HoloLens. | All | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>Checkliste für IT-Administrator-Insiderfeatures

✔️ Wenn Sie ein einzelnes Konto Azure AD automatisch anmelden möchten, konfigurieren [Sie diesen neuen CSP.](#auto-login-policy-controlled-by-csp) <br>
✔️ Wenn Sie Ihre Apps so konfigurieren möchten, dass sie nach einem Fehler beim Aktualisieren automatisch eine Aktualisierung versuchen, legen Sie diesen neuen CSP für intelligente [Wiederholungen fest.](#smart-retry-for-app-updates) <br>
✔️ Wenn Sie mehr Kontrolle über Betriebssystemupdates haben möchten, sehen Sie sich diese [neu aktivierten Updaterichtlinien an.](#improved-update-restart-detection-and-notifications) <br>
✔️ Wenn Sie die Apps Ihrer Organisation über den Microsoft Store im Unternehmensspeicher verfügbar machen müssen, aber nur den Zugriff auf die Apps Ihrer Organisation und nicht auf den vollständigen Store zulassen möchten, legen Sie diese Richtlinie [fest.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ Wenn Sie den freien Speicherplatz, die SSID oder BSSID Ihrer HoloLens-Geräte kennen möchten, sehen Sie sich diese csPs für die Berichterstellung [an.](#csp-changes-for-reporting-hololens-details) <br>
✔️ Wenn Sie WDAC verwenden möchten, um den Start von Apps oder Prozessen zu blockieren, aber auch Ihre eigene Linie von Schläfrigkeits-Apps verwenden müssen, können Sie jetzt lob in Ihrer [WDAC-Richtlinie zulassen.](#use-wdac-and-lob-apps)

### <a name="moving-platform-mode"></a>Verschieben des Plattformmodus

Ab **Insider-Build 20348.1411** haben wir Betaunterstützung für die Nachverfolgung auf Plattformen mit geringen dynamischen Bewegungen auf HoloLens 2. Nachdem Sie den Build installiert und den Moving Platform-Modus aktiviert haben, können Sie Ihre HoloLens 2 in umgebungen verwenden, auf die zuvor nicht zugegriffen werden konnte, z. B. in großen Booten und großen Bebauungsbooten. Derzeit ist das Feature nur auf die Unterstützung dieser spezifischen beweglichen Plattformen ausgerichtet. Zwar hindert Sie nichts daran, die Verwendung des Features in anderen Umgebungen zu versuchen, der Schwerpunkt bei diesem Feature liegt aber zuerst bei der hinzugefügten Unterstützung für diese Umgebungen.

Weitere Informationen dazu, was unterstützt wird und wie Sie dieses neue Feature aktivieren, finden Sie auf [der Seite zum Verschieben der Plattform.](hololens2-moving-platform.md)

#### <a name="overview-to-try-out-moving-platform-mode"></a>Übersicht zum Testen des Verschiebens des Plattformmodus

1. [Aktivieren Sie den Entwicklermodus und das Geräteportal.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. [Aktivieren Sie das Verschieben des Plattformmodus über das Geräteportal.](hololens2-moving-platform.md#enabling-moving-platform-mode)
1. Bringen Sie Ihr Gerät auf Ihre große sich bewegende Plattform, und beobachten Sie, wie stabil Hologramme sind.

### <a name="pfx-file-support-for-certificate-manager"></a>PFX-Dateiunterstützung für den Zertifikat-Manager

Eingeführt in Windows Insider-Build 20348.1405. Wir haben dem [Zertifikat-Manager](certificate-manager.md) Unterstützung für die Verwendung von PFX-Zertifikaten hinzugefügt. Wenn Benutzer zu **Einstellungen** Update &-Sicherheitszertifikate navigieren und Zertifikat installieren auswählen, unterstützt die Benutzeroberfläche jetzt  >    >  die PFX-Zertifikatdatei. 
Benutzer können das PFX-Zertifikat mit privatem Schlüssel in den Benutzer- oder Computerspeicher importieren.

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>Übersicht zum Testen von PFX-Dateien im Zertifikat-Manager

1. Bereiten Sie Ihre PFX-Datei vor.
1. Kopieren Sie die Datei über ein USB-C-Kabel auf Ihr Gerät.
1. Öffnen Sie die Einstellungen-App, navigieren Sie zum [Zertifikat-Manager,](certificate-manager.md) und wenden Sie das Zertifikat an.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Anzeigen des erweiterten Diagnoseberichts in Einstellungen auf HoloLens

Für verwaltete Geräte bei der Problembehandlung ist die Bestätigung, dass eine erwartete Richtlinienkonfiguration angewendet wird, ein wichtiger Schritt. Bisher mussten diese Informationen auf dem Gerät über MDM oder in der Nähe des Geräts angezeigt werden, nachdem mdm-Diagnoseprotokolle exportiert wurden, die über **Einstellungen-Konten** gesammelt wurden. Wählen Sie anschließend Die Verwaltungsprotokolle exportieren und auf einem pc in der Nähe anzeigen  ->    >  aus. 

Die MDM-Diagnose kann nun mithilfe des Edge-Browsers auf dem Gerät angezeigt werden. Um den MDM-Diagnosebericht einfacher anzuzeigen, navigieren Sie zur Seite Auf Arbeits- oder Schularbeit zugreifen, und wählen **Sie Erweiterten Diagnosebericht anzeigen aus.** Dadurch wird der Bericht in einem neuen Edgefenster generiert und geöffnet.

![Zeigen Sie den erweiterten Diagnosebericht in Einstellungen an.](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>Übersicht zum Testen des erweiterten Diagnoseberichts

1. Öffnen Sie die App „Einstellungen“.
1. Navigieren Sie zur Seite Konten, und klicken Sie auf den neuen Link **Exportieren Sie Ihre Verwaltungsprotokolle.**
1. Zeigen Sie erweiterte Informationen zu den Konfigurationen Ihres Geräts an.

### <a name="offline-diagnostics-notifications"></a>Offlinediagnosebenachrichtigungen

Dies ist ein Update für ein vorhandenes Feature namens [Offlinediagnose.](hololens-diagnostic-logs.md#offline-diagnostics) Bisher gab es keinen eindeutigen Hinweis für Benutzer, dass sie die Diagnosesammlung ausgelöst oder abgeschlossen hatten.
Jetzt in Windows Insider-Builds hinzugefügt, gibt es zwei Formen des feedback-Feedbacks für die Offlinediagnose. Das erste , das popupt, zeigt Benachrichtigungen an, die sowohl beim Start als auch beim Abschluss der Sammlung angezeigt werden. Diese werden angezeigt, wenn der Benutzer angemeldet ist und über Visuals verfügt.

![Popup zum Sammeln von Protokollen.](./images/logcollection1.jpg)

![Popup, wenn die Protokollsammlung abgeschlossen ist.](./images/logcollection2.jpg)

Da Benutzer die Offlinediagnose häufig als Fallbackmechanismus für die Protokollsammlung verwenden, wenn sie keinen Zugriff auf eine Anzeige haben, sich nicht anmelden können oder sich noch in OOBE befinden, wird beim Sammeln von Protokollen auch ein Audio cue wiedergegeben. Dieser Sound wird zusätzlich zur Popupbenachrichtigung wiedergegeben.

Dieses neue Feature wird aktiviert, wenn Ihr Gerät aktualisiert wird, und muss nicht aktiviert oder verwaltet werden. In jedem Fall, in dem dieses neue Feedback nicht angezeigt oder gehört werden kann, wird weiterhin die Offlinediagnose generiert.

Wir hoffen, dass es durch diese neuere Hinzufügung von Feedback zur Freundlichkeit einfacher ist, Diagnosedaten zu sammeln und Schneller in der Lage zu sein, Ihre Probleme zu beheben.

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>Übersicht zum Testen der Diagnosebenachrichtigungen

1. Entsperren Sie Ihr Gerät, und tragen Sie es ab.
1. Drücken Sie die Kombination aus **Einschaltfläche** und **Lautstärke nach unten,** um die [Offlinediagnose](hololens-diagnostic-logs.md#offline-diagnostics)zu erfassen.
1. Zeigen Sie die Popupbenachrichtigungen an, und hören Sie Audiohinweise dazu, wann Ihr Gerät gestartet wird und das Sammeln von Protokollen abgeschlossen ist.

### <a name="low-storage-log-collection-improvements"></a>Verbesserungen bei der Protokollsammlung mit geringem Speicher

In Szenarien, in denen ein Gerät bei der Erfassung von Diagnoseprotokollen wenig Speicherplatz auf dem Datenträger zu haben scheint, wird ein zusätzlicher Bericht mit dem Namen **StorageDiagnostics.zip** erstellt. Der Schwellenwert für niedrigen Speicher wird automatisch durch Windows [Speichers sense](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)bestimmt.

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>Übersicht zum Testen der Speicherverbesserungen mit geringem Speicher

1. Füllen Sie den Speicherplatz Ihres Geräts aus.
1. Drücken Sie die Kombination aus **Einschaltfläche** und **Lautstärke nach unten,** um die [Offlinediagnose](hololens-diagnostic-logs.md#offline-diagnostics)zu erfassen.
1. Beachten Sie, dass in der Sammlung der Protokolle, die im Ordner Dokumente Ihres HoloLens gespeichert sind, eine neue Datei vorhanden ist.

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP-Änderungen für die Berichterstellung HoloLens Details

- Eingeführt in Windows Insider-Build, 20348.1403

Die folgenden CSPs wurden mit neuen Möglichkeiten zum Melden von Informationen von Ihren HoloLens-Geräten aktualisiert.

#### <a name="devdetail-csp---free-storage"></a>DevDetail-CSP: Kostenlose Storage

DevDetail CSP meldet jetzt auch freien Speicherplatz auf HoloLens Gerät. Dies sollte ungefähr mit dem Wert übereinstimmen, der auf Einstellungen Seite Storage App angezeigt wird. Im Folgenden finden Sie den spezifischen Knoten, der diese Informationen enthält.

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

### <a name="auto-login-policy-controlled-by-csp"></a>Richtlinie für die automatische Anmeldung, die vom CSP gesteuert wird

Diese neue AutoLogonUser-Richtlinie steuert, ob ein Benutzer automatisch angemeldet wird. Einige Kunden möchten Geräte einrichten, die an eine Identität gebunden sind, aber keine Anmeldeerfahrung haben möchten. Imagine sofort ein Gerät abzuholen und die Remoteunterstützung zu verwenden. Sie haben auch den Vorteil, dass Sie HoloLens Geräte schnell verteilen und endbenutzern ermöglichen können, die Anmeldung zu beschleunigen.

Wenn die Richtlinie auf einen nicht leeren Wert festgelegt ist, wird die E-Mail-Adresse des Benutzers für die automatische Anmeldung angegeben. Der angegebene Benutzer muss sich mindestens einmal beim Gerät anmelden, um die automatische Anmeldung zu aktivieren.

Der OMA-URI der neuen Richtlinie `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` Zeichenfolgenwert

- Für Benutzer mit der gleichen E-Mail-Adresse ist die automatische Anmeldung aktiviert.

Auf einem Gerät, auf dem diese Richtlinie konfiguriert ist, muss sich der in der Richtlinie angegebene Benutzer mindestens einmal anmelden. Bei nachfolgenden Neustarts des Geräts nach der ersten Anmeldung wird der angegebene Benutzer automatisch angemeldet. Es wird nur ein einzelner Benutzer für die automatische Anmeldung unterstützt. Nach der Aktivierung kann sich der automatisch angemeldete Benutzer nicht mehr manuell abmelden. Um sich als anderer Benutzer anmelden zu können, muss die Richtlinie zuerst deaktiviert werden.

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

Zwischen aktiven Stunden und Installationszeitrichtlinien ist es möglich, einen Neustart HoloLens Geräten zu vermeiden, wenn sie verwendet werden. Es würde jedoch auch die Einführung von Updates verzögern, wenn keine Neustarts durchgeführt werden, um die Installation eines erforderlichen Updates abzuschließen. Wir haben nun Richtlinien hinzugefügt, damit die IT-It Stichtage und erforderliche Neustarts erzwingen und sicherstellen kann, dass die Installation eines Updates rechtzeitig abgeschlossen wird. Benutzer können benachrichtigt werden, bevor der Neustart initiiert wird, und sie können den Neustart entsprechend der IT-Richtlinie verzögern.

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

Jetzt für HoloLens aktiviert ist, ist eine neue Richtlinie, mit der IT-Administratoren ein wiederkehrendes oder einmaliges Datum festlegen können, um Apps neu zu starten, deren Update fehlgeschlagen ist, weil die App verwendet wird und das Update angewendet werden kann. Diese können basierend auf einigen verschiedenen Triggern festgelegt werden, z. B. einem geplanten Zeitpunkt oder einer Anmeldung. Weitere Informationen zur Verwendung dieser Richtlinie finden Sie unter [ApplicationManagement/ScheduleForceRestartForUpdateFailures.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>Übersicht zum Testen von Smart Retry für App-Updates

1. Konfigurieren Sie das neue Feature für intelligente Wiederholungen.
1. Melden Sie sich auf einem Gerät, das Ihre App noch nicht empfangen hat und für das sie ordnungsgemäß konfiguriert ist, in einer Onlineumgebung an.
1. Sorgen Sie dafür, dass das Gerät die App nicht herunterladen kann, indem Sie sie deaktivieren oder trennen.
1. Lassen Sie Ihr Gerät während der ausgelösten Zeit eingeschaltet und mit dem Internet verbunden, um den Download zu wiederholen.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Nur private Store-Apps für Microsoft Store

Die RequirePrivateStoreOnly-Richtlinie wurde für HoloLens aktiviert. Mit dieser Richtlinie kann die Microsoft Store-App so konfiguriert werden, dass nur der private Speicher angezeigt wird, der für Ihre Organisation über [Microsoft Store für Unternehmen](/microsoft-store/microsoft-store-for-business-overview)konfiguriert wurde. Beschränken des Zugriffs auf die Apps, die Sie zur Verfügung gestellt haben.

Erfahren Sie mehr über [ApplicationManagement/RequirePrivateStoreOnly](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly).

#### <a name="overview-to-try-only-private-store-apps"></a>Übersicht, um nur private Store-Apps zu testen

1. Konfigurieren Sie die neue Richtlinie für Ihre Geräte über [MDM.](hololens-mdm-configure.md)
1. Melden Sie sich bei einem Gerät mit der Richtlinie an.
1. Öffnen Sie die Microsoft Store-App, und beobachten Sie, dass Sie nur die Apps Ihrer Organisation sehen können.

### <a name="use-wdac-and-lob-apps"></a>Verwenden von WDAC- und LOB-Apps

Sie können jetzt WDAC verwenden, um den Start von Apps oder Prozessen zu blockieren und weiterhin Ihre eigene Reihe von Sperr-Apps zu verwenden. Sie können sie jetzt in Ihrer WDAC-Richtlinie zulassen. Die Verwendung dieser Richtlinie umfasst das Ausführen einer zusätzlichen Codezeile in PowerShell beim Erstellen der WDAC-Richtlinie. [Sehen Sie sich die Schritte hier](/mem/intune/configuration/custom-profile-hololens)an.

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>Übersicht zum Ausprobieren eigener Apps bei verwendung von WDAC zum Blockieren anderer Apps

1. Erfassen Sie die AUMIDs Ihrer BRANCHEN-App und die Apps, die Sie blockieren möchten.
1. Erstellen Sie mit den neuen Schritten [eine neue WDAC-Richtlinie.](/mem/intune/configuration/custom-profile-hololens)
1. [Stellen Sie die Richtlinie mithilfe von MDM](hololens-mdm-configure.md) auf Ihrem Gerät bereit.
1. Melden Sie sich beim Gerät an, und beobachten Sie, wie Sie Ihre App starten und andere blockieren können.

### <a name="fixes-and-improvements"></a>Fehlerbehebungen und Verbesserungen

- Es wurde ein [bekanntes Problem für Geräteportal behoben, bei dem keine Aufforderung zum Herunterladen gesperrter Dateien angezeigt wurde.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Ein [bekanntes Problem für Geräteportal mit Dateiupload- und Downloadtime outs](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)wurde behoben.
- Beheben von Problemen bei der Berichterstellung von Konformitätseigenschaften von HoloLens Geräten Möglicherweise ist ein Neustart erforderlich, damit die richtige Berichterstellung in Insider-Builds ausgelöst wird.  
- Aktivierte eine API für [zugewiesenen Zugriff,](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true) sodass Apps jetzt ermitteln können, ob ein HoloLens im Kioskmodus für den Benutzer ausgeführt wird, der beim HoloLens angemeldet ist.
- Die in der Box enthaltene Version von Remote Assist, die auf neuen Flashs installiert ist, wurde aktualisiert.
- Die Gamepadverarbeitung für 2D-Apps wurde in Insider-Builds deaktiviert. Durch das Entfernen können Apps die Gamepad-APIs jetzt direkt verwenden, haben Zugriff auf die gesamte Gruppe von Steuerelementen und können alles tun, was sie möchten. Entwickler sollten die Gamepad-APIs verwenden, um Gamepad-Eingaben zu nutzen. Hier ist ein Beispiel für [die Gamepad-Klasse (Windows. Gaming.Input): Windows UWP-Anwendungen.](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true)
- Ein Problem wurde behoben, bei dem oobe nach der ersten Benutzeranmeldung in Szenarien beendet wurde, in denen gruppenbasierte AAD-Kioskkonfigurationen verwendet wurden.
- Ein Problem im Zusammenhang mit dem Anzeigen von Updatebenachrichtigungen und Dialogfeldaufforderungen für den Geräteneustart wurde behoben.

## <a name="start-receiving-insider-builds"></a>Starten des Empfangs von Insider-Builds

> [!NOTE]
> Wenn Sie vor Kurzem noch nicht aktualisiert haben, starten Sie Ihr Gerät neu, um den Zustand zu aktualisieren und den neuesten Build zu erhalten.
>
> - Der Sprachbefehl "Gerät neu starten" funktioniert gut.
> - Sie können auch die Schaltfläche "Neu starten" in Einstellungen/Windows Insider Program auswählen.
>
> Es ist ein Fehler auf dem Back-End aufgetreten, der möglicherweise aufgetreten ist, sodass Sie wieder auf kursierten Stand kommen.

Wechseln Sie auf einem HoloLens 2 Gerät zu **Einstellungen**  >  **Update & Security** Windows Insider  >  **Program,** und wählen Sie Erste Schritte **aus.** Verknüpfen Sie das Konto, das Sie zum Registrieren als Windows Insider verwendet haben.

> [!NOTE]
> Um Ihr Gerät bei Insider-Builds zu registrieren, müssen Sie optionale Telemetriedaten aktivieren. Wenn Sie dies noch nicht getan haben, öffnen Sie die Einstellungen-App, wählen Sie  ->  **Datenschutzdiagnose & Feedback** und dann Optionale **Diagnosedaten** aus.

Windows Insider wechselt jetzt zu Kanäle. Der **Schnelle** Ring wird zum **Entwicklungskanal,** der **langsame** Ring zum **Betakanal** und der **Releasevorschauring** zum **Releasevorschaukanal.** Diese Zuordnung sieht wie folgt aus:

![Windows Erklärung von Insider-Kanälen.](images/WindowsInsiderChannels.png)

Weitere Informationen finden Sie unter [Introducing Windows Insider Channels (Einführung in Windows Insider Channels)](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) auf Windows Blogs.
Wählen Sie dann **Aktive Entwicklung von Windows** aus, wählen Sie aus, ob Sie Dev **Channel** oder **Betakanal** Builds erhalten möchten, und überprüfen Sie die Programmbedingungen.
Wählen Sie **Confirm > Restart Now (Jetzt neu starten)** aus, um den Vorgang abzuschließen. Wechseln Sie nach dem Neustart Ihres Geräts zu **Einstellungen > Update & Security > Suchen nach Updates,** um den neuesten Build zu erhalten.

### <a name="update-error-0x80070490-work-around"></a>Updatefehler 0x80070490 Problembearbeitung

Wenn beim Aktualisieren auf dem Entwicklungs- oder Betakanal ein Updatefehler 0x80070490 auftritt, versuchen Sie es mit der folgenden kurzfristigen Problemumgemeinung. Dies umfasst das Verschieben Ihres Insider-Kanals, das Aufnehmen des Updates und das anschließende Verschieben Ihres Insider-Kanals zurück.

#### <a name="stage-one---release-preview"></a>Phase 1: Releasevorschau

1. Einstellungen, Update & Security, Windows Insider Program, wählen Sie **Release Preview Channel (Releasevorschaukanal)** aus.

2. Einstellungen, Update & Security, Windows Update, **Suchen nach Updates.** Fahren Sie nach dem Update mit Phase 2 fort.

#### <a name="stage-two---dev-channel"></a>Phase 2: Entwicklungskanal

1. Einstellungen, Update & Security, Windows Insider Program, wählen Sie **Dev Channel** aus.

2. Einstellungen, Update & Security, Windows Update, **Suchen nach Updates.**

## <a name="ffu-download-and-flash-directions"></a>Download- und Flash-Anweisungen für FFU

Zum Testen mit einer Flugsignierungs-FFU müssen Sie ihr Gerät zunächst entsperren, bevor Sie die flugsigniert-FFU blinken lassen.

1. Auf dem PC:
    1. Laden Sie FFU von auf Ihren PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) herunter.

    1. Installieren Sie ARC (Advanced Recovery Companion) über die Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. Bei HoloLens – Flight Unlock: Öffnen **Sie Einstellungen** Update  >  **& Security** Windows Insider  >  **Program,** und starten Sie das Gerät neu.

1. Flash-FFU: Jetzt können Sie die mit Flugsignieren signierte FFU mit ARC flashen.

### <a name="provide-feedback-and-report-issues"></a>Bereitstellen von Feedback und Melden von Problemen

Verwenden Sie [die Feedback-Hub-App](hololens-feedback.md) auf Ihrem HoloLens, um Feedback zu geben und Probleme zu melden. Die Verwendung von Feedback-Hub stellt sicher, dass alle erforderlichen Diagnoseinformationen enthalten sind, damit unsere Techniker das Problem schnell debuggen und beheben können.  Probleme mit der chinesischen und japanischen Version von HoloLens sollten auf die gleiche Weise gemeldet werden.

> [!NOTE]
> Achten Sie darauf, dass Sie die Eingabeaufforderung akzeptieren, in der Sie gefragt werden, ob Feedback-Hub auf Ihren Ordner Dokumente zugreifen möchten (wählen Sie **Ja** aus, wenn Sie dazu aufgefordert werden).

## <a name="note-for-developers"></a>Hinweis für Entwickler

Sie sind willkommen und werden empfohlen, Ihre Anwendungen mit Insider-Builds von HoloLens zu entwickeln.  Informationen zu den ersten Schritte finden Sie in der [HoloLens Developer-Dokumentation.](https://developer.microsoft.com/windows/mixed-reality/development) Die gleichen Anweisungen funktionieren mit Insider-Builds von HoloLens.  Sie können die gleichen Builds von Unity und Visual Studio verwenden, die Sie bereits für HoloLens Entwicklung verwenden.

## <a name="stop-receiving-insider-builds"></a>Beenden des Empfangs von Insider-Builds

Wenn Sie keine Insider-Builds von Windows Holographic mehr erhalten möchten, können Sie sich abmelden, wenn Ihr HoloLens einen Produktionsbuild ausführt, oder Sie können Ihr Gerät mit dem Advanced Recovery Companion wiederherstellen, um Ihr Gerät in einer Nicht-Insider-Version von Windows Holographic [wiederherzustellen.](hololens-recovery.md)

> [!CAUTION]
> Es gibt ein bekanntes Problem, bei dem Benutzer, die die Registrierung bei Insider Preview-Builds nach der manuellen Neuinstallation eines neuen Vorschaubuilds aufheben, einen Bluescreen erhalten. Anschließend müssen sie ihr Gerät manuell wiederherstellen. Ausführliche Informationen dazu, ob Sie betroffen sind oder nicht, finden Sie in diesem [bekannten Problem.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

So überprüfen Sie, ob ihr HoloLens einen Produktionsbuild ausführt:

1. Wechseln Sie zu **Einstellungen > System > About**, und suchen Sie die Buildnummer.

1. [Informationen zu den Buildnummern für die Produktion finden Sie in den Versionshinweisen.](hololens-release-notes.md)

So deaktivieren Sie Insider-Builds:

1. Wechseln Sie auf einer HoloLens, die einen Produktionsbuild ausführt, zu **Einstellungen > Update & Security > Windows Insider Program,** und wählen Sie **Insider-Builds beenden** aus.

1. Befolgen Sie die Anweisungen, um Ihr Gerät zu deaktivieren.
