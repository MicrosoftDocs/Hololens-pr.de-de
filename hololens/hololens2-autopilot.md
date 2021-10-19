---
title: Windows Autopilot für HoloLens 2
description: Informationen zum Einrichten und Konfigurieren von Autopilot auf HoloLens 2-Geräten sowie zur Problembehandlung.
author: qianw211
ms.author: v-qianwen
ms.date: 10/11/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: sekerawa
ms.openlocfilehash: 05eb629e05395f04ddb8723d58d41db4161896fa
ms.sourcegitcommit: 39accbc8e35728969c500da052035af4fd317a65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2021
ms.locfileid: "129964580"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot für HoloLens 2

## <a name="overview"></a>Übersicht

Für die Bereitstellung im großen Stil empfehlen wir den Einstieg in Windows Autopilot. Diese Art der Bereitstellung wird als „geringer Benutzereingriff“ angesehen, da sie das Einrichten von HoloLens sowohl für IT- als auch für Endbenutzer drastisch vereinfacht. 

Auf allgemeiner Ebene erstellt ein IT-Administrator in der Regel die für den Geschäftsbetrieb bereiten Konfigurationen und registriert HoloLens 2 Geräte in MDM-Portalen. Wenn HoloLens 2 Geräte mit Out-Of-Box Experience (OOBE) gestartet werden und eine Verbindung mit dem Internet herstellen, werden geschäftsbereite Konfigurationen für registrierte HoloLens 2-Geräte automatisch heruntergeladen und angewendet, um die Geräte ohne Benutzereingriff betriebsbereit zu machen.

Weitere Informationen finden Sie im Artikel [Übersicht zu Windows Autopilot | Microsoft-Dokumentation](/mem/autopilot/windows-autopilot).

## <a name="supported-autopilot-scenario-on-hololens-2"></a>Unterstütztes Autopilot-Szenario in HoloLens 2

> [!NOTE]
> Die Autopilot-Konfiguration für HoloLens in Microsoft Endpunkt-Manager geht von **Öffentliche Vorschau** in **Allgemeine Verfügbarkeit** über. Alle Mandanten können dann Autopilot im MEM Admin Center einrichten.

Ab Windows Holographic Version 2004 unterstützt HoloLens 2 den Windows Autopilot [Self-Deployment-Modus](/mem/autopilot/self-deploying) mit Microsoft Intune (MDMs von Drittanbietern werden nicht unterstützt). Diese Konfiguration reduziert den Aufwand für die Bestandsverwaltung, verringert die Vorbereitungskosten für die Geräte und die Supportanrufe der Mitarbeiter während der Einrichtung. Weitere Informationen finden Sie in der [Windows Autopilot](/mem/autopilot/windows-autopilot)-Dokumentation.

Wie bei den Surface-Geräten wird empfohlen, dass Kunden mit ihrem Microsoft [Cloudlösungsanbieter](https://partner.microsoft.com/cloud-solution-provider) (Wiederverkäufer oder Händler) zusammenarbeiten, um Geräte über das Partner Center für den Autopilot-Service registrieren zu lassen.

Wenn ein Benutzer den Prozess der selbsttätigen Bereitstellung von Autopilot startet, führt dieser folgende Schritte aus:

1. Verbinden des Geräts mit Azure Active Directory (Azure AD). Autopilot für HoloLens unterstützt weder Active Directory-Join noch Azure AD Hybrid-Join.

1. Verwenden Sie Azure AD, um das Gerät im Microsoft Endpunkt Manager (oder einem anderen MDM-Dienst) anzumelden.

1. Herunterladen und Anwenden gerätespezifischer Richtlinien, Zertifikate, Netzwerkprofile und Anwendungen.

1. Zeigen Sie dem Benutzer den Anmeldebildschirm an.

## <a name="configuring-autopilot-for-hololens-2"></a>Konfigurieren von Autopilot für HoloLens 2

Zur Einrichtung Ihrer Umgebung befolgen Sie die folgenden Schritte:

1. [Überprüfen Sie die Anforderungen für Windows Autopilot für HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Aktivieren Sie die Automatischen MDM-Registrierung](#2-enable-automatic-mdm-enrollment)

1. (Nur für Intune) [Achten Sie darauf, dass die MDM-Registrierung für Windows-Geräte nicht blockiert ist.](/mem/intune/enrollment/enrollment-restrictions-set)

1. [Registrieren Sie die Geräte in Windows Autopilot.](#4-register-devices-in-windows-autopilot)

1. [Erstellen einer Gerätegruppe.](#5-create-a-device-group)

1. [Erstellen Sie ein Autopilot-Profil, und weisen Sie es der Gerätegruppe zu.](#6-create-autopilot-profile-and-assign-it-to-the-device-group)

1. [Erstellen Sie die Konfiguration der Seite zum Registrierungsstatus (ESP), und weisen Sie sie der Gerätegruppe zu.](#7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group)

1. [Überprüfen Sie den Profilstatus der HoloLens-Geräte.](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Überprüfen Sie die Anforderungen für Windows Autopilot für HoloLens 2

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Lesen Sie die folgenden Abschnitte des Artikels zu den Anforderungen für Windows Autopilot:

- [Netzwerkanforderungen](/mem/autopilot/networking-requirements)  
- [Lizenzanforderungen](/mem/autopilot/licensing-requirements)  
- [Konfigurationsanforderungen](/mem/autopilot/configuration-requirements)

**Lesen Sie den Abschnitt „[Anforderungen](/windows/deployment/windows-autopilot/self-deploying#requirements)“ im Artikel zum Self-Deployment-Modus von Autopilot.** Ihre Umgebung muss diese Anforderungen zusätzlich zu den Standardanforderungen für Windows Autopilot erfüllen. Sie brauchen die Abschnitte "Schritt-für-Schritt" und "Überprüfung" des Artikels nicht zu lesen. Die später in diesem Artikel aufgeführten Vorgehensweisen enthalten entsprechende Schritte speziell für HoloLens.

Stellen Sie sicher, dass die Geräte nicht bereits Mitglied von Azure AD sind und nicht bei Intune (oder einem anderen MDM-System) angemeldet sind. Autopilot-Self-Deployment schließt diese Schritte ab. Um sicherzustellen, dass alle gerätebezogenen Informationen bereinigt sind, überprüfen Sie sowohl in Azure AD als auch in den Intune-Portalen die Seiten **Geräte**. Die Funktion „Alle Zielgeräte auf Autopilot konvertieren“ wird von HoloLens derzeit nicht unterstützt.

#### <a name="review-hololens-os-requirements"></a>Überprüfen von HoloLens-Betriebssystemanforderungen:

Verwenden Sie den [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=2&activetab=pivot:overviewtab) und unsere [Anweisungen zur erneuten Durchführung des Geräte-Flashs](hololens-recovery.md), um die Build-Version auf Ihrem Gerät zu bestätigen oder erneut auf das neueste Betriebssystem zu „flashen“. Bei Geräten, die bis Ende September 2020 ausgeliefert wurden, ist Windows Holographic Version 1903 vorinstalliert. Wenden Sie sich an Ihren Händler, um sicherzustellen, dass Autopilot-fähige Geräte an Sie ausgeliefert werden.

 Minimale Betriebssystemversion | Feature unterstützt | Hinweise
 ------ | ------ | ------  
 [Windows Holographic, Version 2004](hololens-release-notes.md#windows-holographic-version-2004) (Build 19041.1103) oder höher | 1. Selbstbereitstellungsszenario von Autopilot in HoloLens 2. | Autopilot-Profildownloads werden nur über Ethernet unterstützt. Stellen Sie sicher, dass die HoloLens mit einem „USB-C auf Ethernet“-Adapter an das Ethernet angeschlossen ist **bevor Sie sie einschalten**.  Wenn Sie die Einführung von Autopilot für viele HoloLens-Geräte planen, empfehlen wir die Planung der Adapter-Infrastruktur. Wir raten von USB-Hubs ab, da sie oft die Installation von Treibern von Drittanbietern erfordern, die von HoloLens nicht unterstützt werden.
 [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (Build 19041.1128) oder höher | 1. Herunterladen des Autopilot-Profils über WLAN. <br> 2. [Mandantensperrung: CSP und Autopilot](#tenant-lockdown-csp-and-autopilot) zum Sperren von Geräten mit einem von Autopilot angegebenen Mandanten. | Sie können bei Bedarf weiterhin Ethernet-Adapter verwenden. Bei Geräten, die über WLAN angeschlossen sind, müssen Benutzer nur: <ul> <li> Die Kolibri-Szene durchlaufen </li> <li> Die Sprache und das Gebietsschema auswählen </li> <li> Die Augenkalibrierung ausführen </li> <li> Erfolgreich eine Verbindung mit dem gewünschten WLAN-Netzwerk herstellen </li> </ul>

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Aktivieren Sie die Automatischen MDM-Registrierung:

Damit Autopilot erfolgreich ist, müssen Sie die automatische MDM-Registrierung in Ihrem Azure-Portal aktivieren. Dadurch kann das Gerät ohne einen Benutzer registriert werden.

Weitere Informationen zur Einrichtung finden Sie im folgenden kurzen [Leitfaden zum Aktivieren der automatischen MDM-Registrierung](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) oder im [Schnellstarthandbuch für die automatische Registrierung](/mem/intune/enrollment/quickstart-setup-auto-enrollment).

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. Stellen Sie sicher, dass die MDM-Registrierung für Windows-Geräte nicht blockiert ist.

Damit Autopilot erfolgreich ist, müssen Sie sicherstellen, dass sich Ihre HoloLens-Geräte registrieren können. Da HoloLens als Windows-Gerät gilt, dürfen keine Registrierungseinschränkungen gelten, die Ihre Bereitstellung blockieren könnten. [Überprüfen Sie diese Liste mit Einschränkungen](/mem/intune/enrollment/enrollment-restrictions-set), und stellen Sie sicher, dass Sie Ihre Geräte registrieren können.

### <a name="4-register-devices-in-windows-autopilot"></a>4. Registrieren Sie die Geräte in Windows Autopilot

Ihre Geräte müssen vor der ersten Einrichtung in Windows Autopilot registriert werden.

Es gibt drei Hauptmethoden, HoloLens-Geräte zu registrieren:

 - **Wiederverkäufer können Geräte im Partner Center registrieren, wenn Sie eine Bestellung aufgeben.**

   > [!NOTE]  
   > Dies ist der empfohlene Pfad für das Hinzufügen von Geräten zum Autopilot-Dienst. [Weitere Informationen](/mem/autopilot/partner-registration)  

 - **Sie können [eine Supportanforderung](hololens2-autopilot-registration-support.md) direkt an Microsoft senden.**
 - **Rufen Sie den Hardwarehash (auch als eine Hardware-ID bezeichnet) ab, und registrieren Sie das Gerät manuell im MEM Admin Center.**

#### <a name="obtain-hardware-hash"></a>Abrufen des Hardwarehashs

Sie können den Hardwarehash vom Gerät abrufen. Das Gerät zeichnet seinen Hardware-Hash während des OOBE-Prozesses in einer CSV-Datei auf. Oder später, wenn ein Gerätebesitzer den Prozess der Diagnoseprotokollerfassung startet (im folgenden Verfahren beschrieben). Normalerweise ist der Gerätebesitzer der erste Benutzer, der sich auf dem Gerät anmeldet.

> [!WARNING]
> Wenn Sie OOBE in Builds vor 20H2 durchlaufen haben und die Telemetrie auf „Erforderlich“ festgelegt wurde, können Sie den Hardwarehash für Autopilot nicht mit dieser Methode erfassen. Um Ihren Hardwarehash über diese Methode zu erfassen, legen Sie ihre Telemetrie-Option über die Einstellungen-App auf „Vollständig“ fest, und wählen Sie **Datenschutz** > **Diagnose** aus.

1. Starten Sie das HoloLens 2-Gerät.

1. Drücken Sie auf dem Gerät gleichzeitig die Schaltflächen **Ein** und **Lautstärke senken** und lassen sie dann los. Das Gerät erfasst die Diagnoseprotokolle und den Hardware-Hash und speichert sie in einer Gruppe von .zip-Dateien.

1. Ausführliche Informationen und ein Schulungsvideo zur Durchführung finden Sie unter [Offline-Diagnostik](hololens-diagnostic-logs.md#offline-diagnostics).

1. Schließen Sie das Gerät mit einem USB-C-Kabel an einen Computer an.

1. Öffnen Sie den Datei-Explorer auf dem Computer. Öffnen Sie <b>Dieser PC\\</b><*HoloLens-Gerätename*><b>\\Interner Speicher\\Dokumente</b>, und suchen Sie die Datei „AutopilotDiagnostics.zip“.  

   > [!NOTE]  
   > Die ZIP-Datei ist möglicherweise nicht sofort verfügbar. Wenn die Datei noch nicht bereit ist, wird im Ordner „Dokumente“ möglicherweise eine Datei „HoloLensDiagnostics.temp“ angezeigt. Aktualisieren Sie das Fenster zum updaten der Liste der Dateien.

1. Extrahieren Sie den Inhalt der Datei „AutopilotDiagnostics.zip“.

1. Suchen Sie in den extrahierten Dateien nach der CSV-Datei mit dem Dateinamenpräfix „DeviceHash.“ Kopieren Sie diese Datei auf ein Laufwerk auf dem Computer, um später darauf zugreifen zu können.  

   > [!IMPORTANT]  
   > Die Daten in der CSV-Datei sollten das folgende Kopf- und Zeilenformat verwenden:
   >
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

#### <a name="register-device-through-mem"></a>Registrieren des Geräts über MEM

1. Wählen Sie im [Microsoft Endpunkt Manager Admin Center](https://endpoint.microsoft.com) die Option **Geräte** > **Windows** > **Windows Registrierung** und dann unter **Windows Autopilot Bereitstellung-Programm** die Option **Geräte** > **Import** aus.

1. Wählen Sie unter **Hinzufügen von Windows Autopilot Geräten** die CSV-Datei DeviceHash aus, wählen Sie **Öffnen** und dann **Importieren** aus.  

   > [!div class="mx-imgBorder"]
   > ![Verwenden Sie den Befehl "Import" zum Importieren des Hardwarehashs](./images/hololens-ap-hash-import.png).

1. Wählen Sie nach Abschluss des Imports **Geräte** > **Windows** > **Windows-Registrierung** > **Geräte** > **Synchronisierung** aus. Der Vorgang kann einige Minuten dauern, je nachdem, wie viele Geräte synchronisiert werden. Wählen Sie **Aktualisieren** aus, um das registrierte Gerät anzuzeigen.  

   > [!div class="mx-imgBorder"]
   > ![Verwenden Sie die Befehle „Synchronisieren“ und „Aktualisieren“, um die Liste der Geräte anzuzeigen.](./images/hololens-ap-devices-sync.png)  

### <a name="5-create-a-device-group"></a>5. Erstellen einer Gerätegruppe

1. Wählen Sie im [Microsoft Endpunkt Manager Admin Center](https://endpoint.microsoft.com) **Gruppen** > **Neue Gruppe**.

1. Wählen Sie für den **Gruppentyp** **Sicherheit** aus, und geben Sie dann einen Gruppennamen und eine Beschreibung ein.

1. Wählen Sie für den **Mitgliedschaftstyp** entweder **Zugewiesen** oder **Dynamisches Gerät**.

1. Führen Sie eines der folgenden Verfahren aus:  

   - Wenn Sie im vorherigen Schritt als **Mitgliedschaftstyp** **zugewiesen** ausgewählt haben, dann wählen Sie **Mitglieder** und fügen Sie Autopilot-Geräte zu der Gruppe hinzu. Autopilot-Geräte, die noch nicht registriert sind, werden unter Verwendung der seriellen Gerätenummer als Gerätename aufgelistet.
   - Wenn Sie im vorherigen Schritt **Dynamische Geräte** als **Mitgliedschaftstyp** ausgewählt haben, wählen Sie **Dynamische Gerätemitglieder** aus, und geben Sie dann einen Code in **Erweiterte Regel** ein, der dem folgenden ähnelt:
     - Wenn Sie eine Gruppe mit all Ihren Autopilot-Geräten erstellen möchten, geben Sie ein: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Das Intune-Feld „Gruppentag“ wird dem Attribut **OrderID** auf Azure AD-Geräten zugeordnet. Wenn Sie eine Gruppe erstellen möchten, die alle Ihre Autopilot-Geräte enthält, die ein bestimmtes Gruppentag (OrderID der Azure AD-Geräte) aufweisen, geben Sie Folgendes ein: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Wenn Sie eine Gruppe erstellen möchten, die alle Ihre Autopilot-Geräte enthält, die eine bestimmte Bestellnummer aufweisen, geben Sie Folgendes ein: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Diese Regeln zielen auf Attribute ab, die nur für Autopilot-Geräte gelten.
1. Wählen Sie **Speichern** und dann **Erstellen** aus.

### <a name="6-create-autopilot-profile-and-assign-it-to-the-device-group"></a>6. Erstellen Sie ein Autopilot-Profil, und weisen Sie es der Gerätegruppe zu.

1. Wählen Sie im [Microsoft Endpunkt Manager Admin Center](https://endpoint.microsoft.com) die Option **Geräte** > **Windows** > **Windows Registrierung** > **Windows Autopilot-Bereitstellungsprofile** > **Profil Erstellen** > **HoloLens**.
   ![Die Dropdownliste „Profil erstellen“ enthält ein Element „HoloLens“.](./images/hololens-ap-enrollment-profiles.png)

1. Geben Sie einen Profilnamen und eine Beschreibung ein, und wählen Sie dann **Weiter** aus.  
   Die angezeigte Liste sollte die Option **HoloLens** enthalten. Ist diese Option nicht enthalten, verwenden Sie eine der [Feedback](hololens2-autopilot.md#feedback-and-support-for-autopilot)-Optionen, um uns zu kontaktieren.

   > [!div class="mx-imgBorder"]
   > ![Hinzufügen von Profilname und Beschreibung.](./images/hololens-ap-profile-name.png)

1. Auf der Seite **Out-of-Box-Benutzererfahrungen (OOBE)** sind die meisten Einstellungen vorkonfiguriert, um OOBE für diese Auswertung zu optimieren. Sie können optional die folgenden Einstellungen konfigurieren:  

   - **Sprache (Region)** :Wählen Sie die Sprache für OOBE aus. Es wird empfohlen, eine Sprache aus der Liste der [unterstützten Sprachen für HoloLens 2](hololens2-language-support.md) auszuwählen.
   - **Tastatur automatisch konfigurieren:** Wählen Sie **Ja** aus, um sicherzustellen, dass die Tastatur der ausgewählten Sprache entspricht.
   - **Anwenden der Gerätenamen-Vorlage**: Um den Gerätenamen während des OOBE-Vorgangs automatisch festzulegen, wählen Sie **Ja** aus und geben Sie dann den Vorlagenausdruck und die Platzhalter in **Eingeben eines Namens** ein. Geben Sie z. B. ein Präfix und `%RAND:4%`&mdash;einen Platzhalter für eine vierstellige Zufallszahl ein.
     > [!NOTE]  
     > Wenn Sie eine Vorlage für Gerätenamen verwenden, startet der OOBE-Vorgang das Gerät ein Mal neu, nachdem der Gerätename angewendet und bevor das Gerät in Azure AD eingebunden wird. Mit diesem Neustart wird der neue Name wirksam.  

   > [!div class="mx-imgBorder"]
   > ![Konfigurieren der OOBE-Einstellungen.](./images/hololens-ap-profile-oobe.png)

1. Nachdem Sie die Einstellungen konfiguriert haben, wählen Sie **Weiter** aus.
1. Fügen Sie auf der Seite **Bereichsmarkierungen** optional die Bereichsmarkierungen hinzu, die Sie auf dieses Profil anwenden möchten. Weitere Informationen zu Bereichsmarkierungen finden Sie unter [Use role-based access control and scope tags for distributed IT (Verwenden der rollenbasierten Zugriffssteuerung und von Bereichsmarkierungen für verteilte IT)](/mem/intune/fundamentals/scope-tags.md). Wählen Sie anschließend **Weiter** aus.
1. Wählen Sie auf der Seite **Zuweisungen** für **Zuweisen an** die Option **Ausgewählte Gruppen** aus.
1. Wählen Sie unter **AUSGEWÄHLTE GRUPPEN** die Option **+ Gruppen auswählen, die eingeschlossen werden sollen**.
1. Wählen Sie in der Liste **Gruppen auswählen, die eingeschlossen werden sollen** die Gerätegruppe, die Sie für die Autopilot HoloLens-Geräte erstellt haben, und wählen Sie dann **Weiter** aus.  
  
   Wenn Sie Gruppen ausschließen möchten, wählen Sie **Auswahl auszuschließender Gruppen** und dann die Gruppen aus, die Sie ausschließen möchten.

   > [!div class="mx-imgBorder"]
   > ![Weisen Sie dem Profil eine Gerätegruppe zu.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Überprüfen Sie auf der Seite **Überprüfen und Erstellen** die Einstellungen und wählen Sie dann **Erstellen** aus, um das Profil zu erstellen.  

   > [!div class="mx-imgBorder"]
   > ![Überprüfen und erstellen.](./images/hololens-ap-profile-summ.png)

### <a name="7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group"></a>7. Erstellen Sie die Konfiguration der Seite zum Registrierungsstatus (ESP), und weisen Sie sie der Gerätegruppe zu.

Auf der Seite „Registrierungsstatus“ (ESP) wird der Status des gesamten Gerätekonfigurationsprozesses angezeigt, der ausgeführt wird, wenn ein durch MDM verwalteter Benutzer sich das erste Mal bei einem Gerät anmeldet. Stellen Sie sicher, dass Ihre ESP-Konfiguration wie folgt aussieht, und überprüfen Sie, ob die Zuweisungen korrekt sind.  

> [!div class="mx-imgBorder"]
> ![ESP-Konfiguration.](./images/hololens-ap-profile-settings.png)

Weitere Informationen zum ESP finden Sie unter [Einrichten der Seite „Registrierungsstatus“ – Microsoft Intune | Microsoft-Dokumentation](/mem/intune/enrollment/windows-enrollment-status)

### <a name="8-verify-the-profile-status-of-the-hololens-devices"></a>8. Überprüfen Sie den Profilstatus der HoloLens-Geräte

1. Wählen Sie **Geräte** > **Windows**  > **Windows-Registrierung** > **Geräte** im Microsoft Endpunkt Manager Admin Center aus.

1. Vergewissern Sie sich, dass die HoloLens-Geräte aufgelistet sind und Ihr Profilstatus **Zugewiesen** lautet.  

   > [!NOTE]  
   > Es kann einige Minuten dauern, bis das Profil dem Gerät zugewiesen wurde.  

   > [!div class="mx-imgBorder"]
   > ![Geräte- und Profilzuweisungen.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows Autopilot für die HoloLens 2 – Benutzeroberfläche

Sobald die obigen Anweisungen abgeschlossen sind, werden Ihre Benutzer der HoloLens 2 folgende Erfahrungen bei der Bereitstellung ihrer HoloLens-Geräte machen:  

1. Für die Nutzung Autopilot-Erfahrungen ist ein Internetzugriff erforderlich. Verwenden Sie eine der folgenden Optionen um einen Internetzugang bereitzustellen:

    - Schließen Sie Ihr Gerät an ein WLAN-Netzwerk in OOBE an. Lassen Sie es dann automatisch Autopilot-Erfahrung finden. Das ist das einzige Mal, dass Sie mit OOBE interagieren müssen, bis Autopilot-Erfahrung von selbst abgeschlossen ist.

    - Schließen Sie Ihr Gerät mit einem „USB-C auf Ethernet“-Adapter für eine kabelgebundene Internetverbindung an das Ethernet an. Lassen Sie HoloLens 2 automatisch Autopilot-Erfahrung vervollständigen.

    - Schließen Sie Ihr Gerät mit einem „USB-C auf WLAN“-Adapter für eine kabellose Internetverbindung an. Lassen Sie HoloLens 2 automatisch Autopilot-Erfahrung vervollständigen.

        > [!IMPORTANT]  
       > Geräte, die versuchen, Wi-Fi Netzwerke in OOBE für Autopilot zu verwenden müssen über [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) verfügen.
       >
       > Bei Geräten, die Ethernet-Adapter verwenden, müssen Sie das Gerät an das Netzwerk anschließen, bevor die Out-of-the-Box-Erfahrung (OOBE) beginnt. Auf dem ersten OOBE-Bildschirm wird ermittelt, ob das Gerät als Autopilot-Gerät bereitgestellt wird. Wenn das Gerät keine Verbindung mit dem Netzwerk herstellen kann, oder wenn Sie sich entscheiden, das Gerät nicht als Autopilot-Gerät bereitzustellen, können Sie zu einem späteren Zeitpunkt nicht zur Autopilot-Bereitstellung wechseln. Stattdessen müssten Sie diesen Vorgang erneut ausführen, um das Gerät als Autopilot-Gerät bereitzustellen.

1. Das Gerät sollte die OOBE automatisch starten. Interagieren Sie nicht mit OOBE.

    > [!IMPORTANT]
    > Interagieren Sie während einer Autopilot-Bereitstellung nicht mit OOBE, und drücken Sie nicht den Netzschalter, um das System in den Standbymodus zu bringen oder herunterzufahren. Dies kann dazu führen, dass der Autopilot-Ablauf nicht abgeschlossen wird.

   Lassen Sie HoloLens 2 die Netzwerkverbindung ermitteln, und erlauben Sie ihr den OOBE-Vorgang automatisch auszuführen. Das Gerät könnte während des OOBE-Vorgangs neu starten. Die OOBE-Bildschirme sollten wie folgt aussehen.

   ![OOBE Schritt 1.](./images/autopilot-welcome.jpg)
   ![OOBE Schritt 2.](./images/autopilot-step-complete.jpg)
   ![OOBE Schritt 3.](./images/autopilot-device-setup.jpg)

1. Am Ende des OOBE-Vorgangs können Sie sich mit Ihrem Benutzernamen und Kennwort beim Gerät anmelden.

   <img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenant-lockdown-csp-and-autopilot"></a>TenantLockdown CSP und Autopilot

HoloLens 2-Geräte unterstützen TenantLockdown CSP ab Windows Holographic, Version 20H2. Dieser CSP hält die Geräte beim Mandanten des Unternehmens, indem sie an diesen Mandant gebunden werden, selbst im Falle eines Resets oder eine erneuten Flashs.

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

#### <a name="why-did-i-not-see-autopilot-experience-even-though-the-autopilot-profile-is-assigned-in-intune"></a>Warum wurde die Autopilot-Benutzeroberfläche nicht angezeigt, obwohl das Autopilot-Profil in Intune zugewiesen ist?

Standardmäßig wartet HoloLens 2 nach der Internet-Erkennung 15 Sekunden mit der Autopilot-Ermittlung. Wenn innerhalb von 15 Sekunden kein Autopilot-Profil erkannt wird, bedeutet dies, dass Autopilot nicht ordnungsgemäß erkannt wurde, dann wird die Seite mit der EULA angezeigt.

Starten Sie Ihr Gerät neu, und versuchen Sie es erneut. Weitere Informationen finden Sie unter [Bekannte Probleme und Einschränkungen](hololens2-autopilot.md#known-issues-and-limitations) oder [Problembehandlung](hololens2-autopilot.md#troubleshooting).

## <a name="known-issues-and-limitations"></a>Einschränkungen und bekannte Probleme

### <a name="why-do-i-see-0x80180014-during-autopilot"></a>Warum wird während des Autopilot-Prozesses „0x80180014“ angezeigt?

Dies ist ein Fehler, der während des Autopilot-Prozesses auf dem Gerät angezeigt wird. Dieses hier beschriebene Problem tritt nur auf, wenn für ein HoloLens-Gerät Folgendes gilt:

1. Autopilot wurde bereits mindestens einmal durchlaufen.
1. Das Gerät wird jetzt zurückgesetzt und erneut für Autopilot verwendet.

Auf der Autopilot-Benutzeroberfläche tritt ein bestimmter Fehler auf.

![HoloLens-Fehlercode für Autopilot-Fehler](images/autopilot-0x80180014-failure.jpg)

Welche Schritte müssen ausgeführt werden, um diesen Fehler zu beheben?

1. Führen Sie die Schritte unter [Problembehandlung beim Import und der Registrierung von Autopilot-Geräten](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) aus, um das Gerät aus Intune zu entfernen. (Diese Aufgabe muss von Ihrem Intune-Administrator ausgeführt werden.)
1. Starten Sie nach Abschluss von Schritt 1 das Gerät neu, und melden Sie sich an.
1. Navigieren Sie zu **Einstellungen** -> **Update & Sicherheit** -> **Zurücksetzen & Wiederherstellen**, und wählen Sie **Erste Schritte** aus.
    1. Wenn in den Schritten 2 und 3 Probleme auftreten, finden Sie Alternativen zum Zurücksetzen des Geräts unter [HoloLens zurücksetzen/Reflash ausführen](hololens-recovery.md).

Anschließend sollte AutoPilot erfolgreich registriert werden.

### <a name="troubleshooting"></a>Problembehandlung

Die folgenden Artikel können eine nützliche Ressource für Sie sein, um mehr Informationen zu erhalten und Autopilot-Probleme zu beheben. Allerdings basieren diese Artikel auf dem Windows 10 Desktop, und möglicherweise gelten nicht alle Informationen für die HoloLens:

- [Windows Autopilot: bekannte Probleme](/mem/autopilot/known-issues)
- [Behandeln von Problemen bei der Windows-Geräteregistrierung in Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot: Richtlinienkonflikte](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Feedback und Support für Autopilot

Verwenden Sie eine der folgenden Methoden, um Feedback zu geben oder Probleme zu melden:

- Für Unterstützung bei der Geräteregistrierung wenden Sie sich an Ihren Wiederverkäufer oder Händler.
- Wenden Sie sich bei allgemeinen Supportanfragen zu Windows Autopilot oder bei Problemen wie Profilzuweisungen, Gruppenerstellung oder MEM-Portalsteuerungen an den [Microsoft Endpunkt Manager Support](/mem/get-support)  
- Wenn Ihr Gerät für den Autopilot-Dienst registriert ist und das Profil auf dem MEM-Portal zugeordnet ist, wenden Sie sich an den [Support](/hololens/) (siehe Karte „Support“). Eröffnen Sie ein Support-Ticket, und fügen Sie gegebenenfalls Screenshots und Protokolle bei, indem Sie [Offline Diagnostik Protokolle](hololens-diagnostic-logs.md#offline-diagnostics) während der Out-of-Box Benutzererfahrung (OOBE) erfassen.
- Um ein Problem mit dem Gerät zu melden, verwenden Sie die App „Feedback Hub“ auf Ihrer HoloLens. Wählen Sie im Feedback-Hub die Kategorie **Enterprise Management** > **Gerät** aus.
- Wenn Sie ein allgemeines Feedback zu Autopilot für HoloLens geben möchten, können Sie diese [Umfrage](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993) absenden

## <a name="delete-autopilot-devices"></a>Löschen von Autopilot-Geräten

Möglicherweise möchten Sie kein Gerät mehr für Autopilot verwenden oder Ihre Geräte bei einem anderen Mandanten registrieren. Lesen Sie in diesem Fall [Löschen von Autopilot-Geräten](/mem/autopilot/add-devices#delete-autopilot-devices).
