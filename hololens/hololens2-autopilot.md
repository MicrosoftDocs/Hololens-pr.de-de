---
title: Windows Autopilot für HoloLens 2
description: Informationen zum Einrichten und Konfigurieren von Autopilot auf HoloLens 2-Geräten sowie zur Problembehandlung.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/13/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilot
manager: jarrettr
ms.openlocfilehash: 23cb3612a633f6747c770d9fd52b137561492426
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284036"
---
# Windows Autopilot für HoloLens 2

Ab Windows Holographic Version 2004 unterstützt HoloLens 2 den Windows Autopilot [Self-Deployment-Modus](https://docs.microsoft.com/mem/autopilot/self-deploying). Administratoren können die out-of-box Benutzererfahrung (OOBE) in Microsoft Endpoint Manager konfigurieren. Geräte können dann vom Endnutzer mit wenig oder ohne Interaktion für die geschäftliche Nutzung aktiviert werden. Das reduziert den Verwaltungsaufwand für die Lagerhaltung, verringert die Vorbereitungskosten für die Geräte und Mitarbeiter benötigen weniger Support bei der Einrichtung. Weitere Informationen finden Sie in der [Windows Autopilot](https://docs.microsoft.com/mem/autopilot/windows-autopilot)-Dokumentation.

Wie bei den Surface-Geräten wird empfohlen, dass Kunden mit ihrem Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (Wiederverkäufer oder Distributor) zusammenarbeiten, um Geräte über das Partner Center für den Autopilot-Service registrieren zu lassen. Andere Methoden zur Geräteregistrierung finden Sie in der Dokumentation zum [Hinzufügen von Geräten](https://docs.microsoft.com/mem/autopilot/add-devices). Den effektivsten End-to-End-Pfad gewährleisten die Microsoft Vertriebspartner.

> [!NOTE]
> Ab dem 20.11.2020 geht die Autopilot-Konfiguration für HoloLens in Microsoft Endpoint Manager auf **Public Preview** über. Kunden müssen sich nicht mehr für die private Vorschau anmelden, und alle Mandanten können den Autopiloten im MEM Admin Center einrichten.

Wenn ein Benutzer den Prozess der selbsttätigen Bereitstellung von Autopilot startet, führt dieser folgende Schritte aus:

1. Verbinden des Geräts mit Azure Active Directory (Azure AD). Hinweis: Autopilot für HoloLens unterstützt weder den Active Directory-Beitritt noch den Azure AD Hybrid-Beitritt.

1. Verwenden von Azure AD, um das Gerät im Microsoft Endpoint Manager (oder einem anderen MDM-Dienst) anzumelden.

1. Herunterladen und Anwenden gerätespezifischer Richtlinien, Zertifikate, Netzwerkprofile und Anwendungen.

1. Bereitstellen des Geräts.

1. Präsentieren des Anmeldebildschirms für den Benutzer.

## Autopilot für HoloLens 2 konfigurieren

Zur Einrichtung Ihrer Umgebung befolgen Sie bitte die folgenden Schritte:

1. [Anforderungen für Windows Autopilot für HoloLens 2 überprüfen.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Automatische MDM-Registrierung aktivieren](#2-enable-automatic-mdm-enrollment)

1. [Geräte bei Windows Autopilot registrieren.](#3-register-devices-in-windows-autopilot)

1. [Erstellen einer Gerätegruppe.](#4-create-a-device-group)

1. [Erstellen Sie ein Bereitstellungsprofil.](#5-create-a-deployment-profile)

1. [Konfiguration der Registrierungsstatusseite (ESP) überprüfen.](#6-verify-the-esp-configuration)

1. [Überprüfen des Profilstatus der HoloLens-Geräte.](#7-verify-the-profile-status-of-the-hololens-devices)

### 1. Anforderungen für Windows Autopilot für HoloLens 2 überprüfen

#### Lesen Sie die folgenden Abschnitte des Artikels zu den Anforderungen für Windows Autopilot:

- [Netzwerkanforderungen](https://docs.microsoft.com/mem/autopilot/networking-requirements)  
- [Lizenzierungsanforderungen](https://docs.microsoft.com/mem/autopilot/licensing-requirements)  
- [Konfigurationsanforderungen](https://docs.microsoft.com/mem/autopilot/configuration-requirements)

**Lesen Sie den Abschnitt "[Voraussetzungen](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" im Artikel zum Self-Deployment-Modus von Autopilot.** Ihre Umgebung muss diese Anforderungen zusätzlich zu den Standardanforderungen für Windows Autopilot erfüllen. Sie brauchen die Abschnitte "Schritt-für-Schritt" und "Validierung" des Artikels nicht zu lesen. Die weiter unten in diesem Artikel aufgeführten Vorgehensweisen enthalten entsprechende Schritte speziell für HoloLens.

Informationen zur Registrierung von Geräten und Konfiguration von Profilen finden Sie in diesem Artikel unter [2. Geräte in Windows Autopilot registrieren](#3-register-devices-in-windows-autopilot) und [4. Bereitstellungsprofil erstellen](#5-create-a-deployment-profile). Zum Konfigurieren und Verwalten der Autopilot-Profile für den Self-Deployment-Modus stellen Sie sicher, dass Sie Zugriff auf [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com) haben.

#### HoloLens-Betriebssystemanforderungen überprüfen:

- Die Geräte müssen auf [Windows Holographic, Version 2004](hololens-release-notes.md#windows-holographic-version-2004) (Build 19041.1103) oder höher sein. Zur Bestätigung der Buildversion auf Ihrem Gerät oder um einen Flash auf das neueste Betriebssystem auszuführen, verwenden Sie [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) und unsere [Anweisungen zum erneuten Ausführen eines Flashs](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device). Hinweis: Bei Geräten, die bis Ende September 2020 ausgeliefert wurden, ist Windows Holographic Version 1903 vorinstalliert. Wenden Sie sich bitte an Ihren Händler, um sicherzustellen, dass Autopilot-fähige Geräte an Sie ausgeliefert werden.

- Windows Holographic, Version 2004 unterstützt nur Autopilot über Ethernet-Verbindung. Stellen Sie sicher, dass HoloLens mit einem "USB-C to Ethernet"-Adapter an das Ethernet angeschlossen ist, **bevor Sie einschalten**. Beim Hochfahren des Geräts ist keine Benutzerinteraktion erforderlich. Wenn Sie die Einführung von Autopilot für viele HoloLens-Geräte planen, empfehlen wir die Planung der Adapter-Infrastruktur. Wir raten von USB-Hubs ab, da sie oft die Installation zusätzlicher Treiber von Drittanbietern erfordern, die von HoloLens nicht unterstützt werden.

- [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (Build 19041.1128) oder höher unterstützen Autopilot über WLAN, obwohl Sie weiterhin Ethernet-Adapter verwenden können. Bei Geräten, die über WLAN angeschlossen sind, müssen Benutzer nur:

     - Die Kolibri-Szene durchlaufen
     - Die Sprache und das Gebietsschema auswählen
     - Die Augenkalibrierung durchführen
     - Eine Netzwerkverbindung herstellen

- Windows Holographic, Version 20H2 unterstützt [Tenantlockdown CSP und Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot). Dabei wird ein Gerät an einen Mandanten gebunden und sicherstellt, dass es im Falle eines versehentlichen oder absichtlichen Resets oder Löschvorgangs an diesen Mandant gebunden bleibt.  

- Stellen Sie sicher, dass die Geräte nicht bereits Mitglied von Azure AD sind und nicht bei Intune (oder einem anderen MDM-System) angemeldet sind. Autopilot-Self-Deployment schließt diese Schritte ab. Um sicherzustellen, dass alle gerätebezogenen Informationen bereinigt sind, überprüfen Sie die **Geräteseiten** sowohl in Azure AD als auch in den Intune-Portalen. Hinweis: Das Feature „Alle Zielgeräte auf Autopilot konvertieren“ wird derzeit von HoloLens nicht unterstützt.  

### 2. Automatische MDM-Registrierung aktivieren:

Damit Autopilot erfolgreich ist, müssen Sie die automatische MDM-Registrierung in Ihrem Azure-Portal aktivieren. Dadurch kann das Gerät ohne einen Benutzer registriert werden.

Wählen Sie im [Azure-Portal](https://portal.azure.com/#home) **Azure Active Directory**  ->  **Mobilität (MDM und MAM)**  ->  **Microsoft Intune**aus. Wenn Sie dann den **MDM-Benutzerbereich**konfigurieren, müssen Sie **Alle**auswählen.

Weitere Informationen zur Einrichtung finden Sie in der folgenden kurzen [Anleitung zur Aktivierung der automatischen MDM-Registrierung](https://docs.microsoft.com/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) oder der [Schnellstartanleitung zur automatischen Registrierung](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).

### 3. Geräte in Windows Autopilot registrieren

#### Hardware Hash abrufen

Ihre Geräte müssen vor der ersten Einrichtung in Windows Autopilot registriert werden. Für die MEM-Dokumentation zur Geräteregistrierung siehe [Geräte zu Autopilot hinzufügen](https://docs.microsoft.com/mem/autopilot/add-devices).  

Es gibt zwei Hauptmethoden, HoloLens-Geräte zu registrieren:

 - **Wiederverkäufer können Geräte im Partner Center registrieren, wenn Sie eine Bestellung aufgeben.**

   > [!NOTE]  
   > Das ist der empfohlene Pfad für das Hinzufügen von Geräten zum Autopilot-Dienst. [Mehr dazu](https://docs.microsoft.com/mem/autopilot/add-devices#reseller-distributor-or-partner-registration).  

 - **Rufen Sie den Hardware-Hash (auch Hardware-ID) ab und registrieren Sie das Gerät manuell im MEM Admin Center**.

- **Hardware-Hash abfragen**

Das Gerät zeichnet seinen Hardware-Hash während des OOBE-Prozesses in einer CSV-Datei auf. Oder später, wenn ein Gerätebesitzer den Prozess der Diagnoseprotokollsammlung startet (im folgenden Verfahren beschrieben). Normalerweise ist der Gerätebesitzer der erste Benutzer, der sich bei dem Gerät anmeldet.

1. Starten Sie das HoloLens 2-Gerät.

1. Drücken Sie am Gerät gleichzeitig die Tasten **Power** und **Volume Down** und lassen Sie die Tasten dann los. Das Gerät sammelt Diagnoseprotokolle und den Hardware-Hash und speichert sie in einer Gruppe von .zip-Dateien.

   1. Ausführliche Informationen und ein Schulungsvideo zur Durchführung finden Sie unter [Offline-Diagnostik](hololens-diagnostic-logs.md#offline-diagnostics).

1. Schließen Sie das Gerät mit einem USB-C-Kabel an einen Computer an.

1. Öffnen Sie den Datei-Explorer auf dem Computer. Öffnen Sie **Dieser PC\\\<*HoloLens device name*>, und suchen Sie nach der Datei „AutopilotDiagnostics.zip“.**  

   > [!NOTE]  
   > Die ZIP-Datei ist möglicherweise nicht sofort verfügbar. Wenn die Datei noch nicht bereit ist, wird im Ordner "Dokumente" möglicherweise eine Datei "HoloLensDiagnostics.temp" angezeigt. Zum Aktualisieren der Liste der Dateien aktualisieren Sie das Fenster.

1. Extrahieren Sie den Inhalt der Datei "AutopilotDiagnostics.zip".

1. Suchen Sie in den extrahierten Dateien nach der CSV-Datei mit dem Dateinamenpräfix "DeviceHash". Kopieren Sie diese Datei auf ein Laufwerk auf dem Computer, um später darauf zuzugreifen.  

   > [!IMPORTANT]  
   > Die Daten in der CSV-Datei sollten das folgende Kopf- und Zeilenformat verwenden:
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

#### Gerät über MEM registrieren

1. Wählen Sie im [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com) die Option **Geräte ** > **Windows** > **Windows-Registrierung**, und wählen Sie dann **Geräte** > **import** unter **Windows Autopilot Deployment-Programm** aus.

1. Wählen Sie unter **Windows Autopilot-Geräte hinzufügen** die DeviceHash-CSV-Datei, dann **Öffnen** und anschließend **Import** aus.  

   > [!div class="mx-imgBorder"]
   > ![Verwenden Sie den Befehl "Import" zum Importieren des Hardwarehashs aus.](./images/hololens-ap-hash-import.png)

1. Wählen Sie nach Abschluss des Importvorgangs **Geräte** > **Windows** > **Windows-Registrierung** > **Geräte** > **Synchronisieren** aus. Je nachdem, wie viele Geräte synchronisiert werden, kann der Vorgang einige Minuten in Anspruch nehmen. Wählen Sie **Aktualisieren** aus, um das registrierte Gerät anzuzeigen.  

   > [!div class="mx-imgBorder"]
   > ![Verwenden Sie die Befehle „Synchronisieren“ und „Aktualisieren“, um die Liste der Geräte anzuzeigen.](./images/hololens-ap-devices-sync.png)  

### 4. Gerätegruppe erstellen

1. Wählen Sie im [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com) die Option **Gruppen** >  **Neue Gruppe** aus.

1. Wählen Sie für **Gruppentyp** die Option **Sicherheit** aus, und geben Sie dann einen Gruppennamen und eine Beschreibung ein.

1. Wählen Sie für **Mitgliedschaftstyp** entweder **Zugewiesen** oder **Dynamisches Gerät** aus.

1. Führen Sie eine der folgenden Aktionen aus:  

   - Wenn Sie für **Mitgliedschaftstyp** im vorherigen Schritt die Option **Zugewiesen** ausgewählt haben, wählen Sie **Mitglieder** aus und fügen der Gruppe dann Autopilot-Geräte hinzu. Autopilot-Geräte, die noch nicht registriert sind, werden unter Verwendung der seriellen Gerätenummer als Gerätename aufgelistet.
   - Wenn Sie im vorherigen Schritt **Dynamische Geräte** als **Mitgliedschaftstyp** ausgewählt haben, wählen Sie **Dynamische Gerätemitglieder** aus, und geben Sie dann in **Erweiterte Regel** Code ein, der wie folgt aussieht:
     - Wenn Sie eine Gruppe erstellen möchten, die alle Ihre Autopilot-Geräte enthält, geben Sie Folgendes ein: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Das Gruppentagfeld von Intune ist dem **OrderID**-Attribut für Azure AD-Geräte zugeordnet. Wenn Sie eine Gruppe erstellen möchten, die alle Ihre Autopilot-Geräte enthält, die ein bestimmtes Gruppentag (OrderID der Azure AD-Geräte) aufweisen, geben Sie Folgendes ein: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Wenn Sie eine Gruppe erstellen möchten, die alle Ihre Autopilot-Geräte enthält, die eine bestimmte Bestellungskennung aufweisen, geben Sie Folgendes ein: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Diese Regeln zielen auf Attribute ab, die nur für Autopilot-Geräte gelten.
1. Wählen Sie **Speichern** und danach **Erstellen** aus.

### 5. Bereitstellungsprofil erstellen

1. Wählen Sie im [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com) die Option **Geräte** >  **Windows** und dann  >  **Windows-Registrierung**  >  **Windows Autopilot Deployment-Profile**  >  **Profil erstellen**  >  **HoloLens** aus.
   ![Die Dropdownliste "Profil erstellen" enthält ein Element "HoloLens".](./images/hololens-ap-enrollment-profiles.png)

1. Geben Sie einen Profilnamen und eine Beschreibung ein, und wählen Sie dann **Weiter** aus.  
   Die angezeigte Liste sollte die Option **HoloLens** enthalten. Ist diese Option nicht enthalten, verwenden Sie eine der [Feedback](hololens2-autopilot.md#feedback-and-support-for-autopilot)-Optionen, um uns zu kontaktieren.

   > [!div class="mx-imgBorder"]
   > ![Profilnamen und Beschreibung hinzufügen](./images/hololens-ap-profile-name.png)

1. Auf der Seite **Out-of-the-Box Experience (OOBE)** sind die meisten Einstellungen der OOBE optimal für diese Evaluierung vorkonfiguriert. Sie können optional folgende Einstellungen konfigurieren:  

   - **Sprache (Region)**: Wählen Sie die Sprache für OOBE aus. Wir empfehlen, dass Sie eine Sprache aus der Liste der [unterstützten Sprachen für HoloLens 2](hololens2-language-support.md) auswählen.
   - **Tastatur automatisch konfigurieren**: Um sicherzustellen, dass die Tastatur mit der ausgewählten Sprache übereinstimmt, wählen Sie **Ja** aus.
   - **Vorlage für Gerätenamen anwenden**: Um den Gerätenamen während des OOBE-Vorgangs automatisch festzulegen, wählen Sie **Ja** aus, und geben Sie dann den Vorlagenausdruck und die Platzhalter in **Namen eingeben** ein. Geben Sie z. B. ein Präfix und `%RAND:4%`&mdash; einen Platzhalter für eine vierstellige Zufallszahl ein.
     > [!NOTE]  
     > Wenn Sie eine Vorlage für Gerätenamen verwenden, startet der OOBE-Vorgang das Gerät ein weiteres Mal neu, nachdem der Gerätenamen angewendet und bevor das Gerät mit Azure AD verbunden wird. Mit diesem Neustart wird der neue Name wirksam.  

   > [!div class="mx-imgBorder"]
   > ![Konfigurieren der OOBE-Einstellungen](./images/hololens-ap-profile-oobe.png)

1. Nachdem Sie die Einstellungen konfiguriert haben, wählen Sie **Weiter** aus.
1. Fügen Sie auf der Seite **Bereichstags** optional die Bereichstags hinzu, die Sie auf dieses Profil anwenden möchten. Weitere Informationen zu Bereichstags finden Sie unter [Verwenden von rollenbasierten Zugriffssteuerungen und Bereichstags für verteilte IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md). Wenn Sie fertig sind, wählen Sie **Weiter** aus.
1. Wählen Sie auf der Seite **Zuweisungen** für **Zuweisen an** die Option **Ausgewählte Gruppen** aus.
1. Wählen Sie unter **AUSGEWÄHLTE GRUPPEN** die Option **+ Wählen Sie die Gruppen aus, die eingeschlossen werden sollen** aus.
1. Wählen Sie in der Liste **Wählen Sie die Gruppen aus, die eingeschlossen werden sollen** die Gerätegruppe, die Sie für die Autopilot HoloLens-Geräte erstellt haben, und dann **Weiter**aus.  
  
   Wenn Sie Gruppen ausschließen möchten, wählen Sie **Wählen Sie die Gruppen aus, die ausgeschlossen werden sollen** und dann die Gruppen aus, die Sie ausschließen möchten.

   > [!div class="mx-imgBorder"]
   > ![Weisen Sie dem Profil eine Gerätegruppe zu.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Überprüfen Sie auf der Seite **Überprüfen und erstellen** die Einstellungen und dann **Erstellen** aus, um das Profil zu erstellen.  

   > [!div class="mx-imgBorder"]
   > ![Überprüfen und erstellen](./images/hololens-ap-profile-summ.png)

### 6. ESP-Konfiguration überprüfen

Auf der Seite "Registrierungsstatus" (ESP) wird der Status des gesamten Gerätekonfigurationsprozesses angezeigt, der ausgeführt wird, wenn ein durch MDM verwalteter Benutzer sich das erste Mal bei einem Gerät anmeldet. Stellen Sie sicher, dass Ihre ESP-Konfiguration wie folgt aussieht, und überprüfen Sie, ob die Zuweisungen korrekt sind.  

> [!div class="mx-imgBorder"]
> ![ESP-Konfiguration](./images/hololens-ap-profile-settings.png)

### 7. Profilstatus der HoloLens-Geräte überprüfen

1. Wählen Sie im Microsoft Endpoint Manager Admin Center **Geräte** > **Windows** > **Windows-Registrierung** > **Geräte** aus.

1. Vergewissern Sie sich, dass die HoloLens-Geräte aufgelistet sind und Ihr Profilstatus **Zugewiesen** lautet.  

   > [!NOTE]  
   > Es kann einige Minuten dauern, bis das Profil dem Gerät zugewiesen wurde.  

   > [!div class="mx-imgBorder"]
   > ![Geräte- und Profilzuweisungen.](./images/hololens-ap-devices-assignments.png)

## Windows Autopilot für HoloLens 2 – Benutzeroberfläche

Sobald die obigen Anweisungen abgeschlossen sind, werden Benutzer der HoloLens 2 folgende Erfahrungen bei der Bereitstellung ihrer HoloLens-Geräte machen:  

1. Für die Autopilot-Nutzung ist ein Internetzugriff erforderlich. Verwenden Sie eine der folgenden Optionen für den Internetzugriff:

    - Schließen Sie Ihr Gerät an ein WLAN-Netzwerk in OOBE an. Lassen Sie es dann automatisch Autopilot finden. Das ist das einzige Mal, dass Sie mit OOBE interagieren müssen, bis Autopilot von selbst abgeschlossen ist. Beachten Sie, dass HoloLens 2 nach der Internet-Erkennung standardmäßig 10 Sekunden wartet, bis es Autopilot findet. Wenn kein Autopilot-Profil innerhalb von 10 Sekunden erkannt wird, zeigt OOBE EULA an. Wenn dieses Szenario auftritt, starten Sie Ihr Gerät neu, um die Autopilot-Erkennung erneut zu versuchen. Beachten Sie auch, dass OOBE nur dann unbegrenzt auf Autopilot wartet, wenn die TenantLockdown-Richtlinie auf dem Gerät eingestellt ist.

    - Schließen Sie Ihr Gerät mit einem „USB-C an Ethernet“-Adapter für eine kabelgebundene Internetverbindung an das Ethernet an. Lassen Sie HoloLens 2 automatisch Autopilot vervollständigen.

    - Schließen Sie Ihr Gerät mit einem „USB-C an WLAN“-Adapter für eine kabellose Internetverbindung an. Lassen Sie HoloLens 2 automatisch Autopilot vervollständigen.

        > [!IMPORTANT]  
       > Um WLAN in OOBE für Autopilot zu verwenden, benötigen Geräte [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2).
       >
       > Bei Geräten, die Ethernet-Adapter verwenden, müssen Sie das Gerät an das Netzwerk anschließen, bevor die Out-of-the-Box-Erfahrung (OOBE) beginnt. Auf dem ersten OOBE-Bildschirm wird ermittelt, ob das Gerät als Autopilot-Gerät bereitgestellt wird. Wenn das Gerät keine Verbindung mit dem Netzwerk herstellen kann, oder wenn Sie sich entscheiden, das Gerät nicht als Autopilot-Gerät bereitzustellen, können Sie zu einem späteren Zeitpunkt nicht zur Autopilot-Bereitstellung wechseln. Stattdessen müssten Sie diesen Vorgang erneut ausführen, um das Gerät als Autopilot-Gerät bereitzustellen.

1. Das Gerät sollte die OOBE automatisch starten. Interagieren Sie nicht mit OOBE. Lehnen Sie sich stattdessen ganz entspannt zurück. Lassen Sie HoloLens 2 die Netzwerkverbindung ermitteln, und geben Sie der Anwendung die Zeit, den OOBE-Vorgang automatisch auszuführen. Das Gerät kann während des OOBE-Vorgangs neu gestartet werden. Die OOBE-Bildschirme sollten wie folgt aussehen.

   ![OOBE Schritt 1 ](./images/autopilot-welcome.jpg)
   ![ OOBE Schritt 2 ](./images/autopilot-step-complete.jpg)
   ![ OOBE Schritt 3](./images/autopilot-device-setup.jpg)

1. Am Ende des OOBE-Vorgangs können Sie sich mit Ihrem Benutzernamen und Kennwort beim Gerät anmelden.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## TenantLockdown CSP und Autopilot

HoloLens 2-Geräte unterstützen TenantLockdown CSP ab Windows Holographic, Version 20H2. Dieser CSP hält die Geräte beim Mandanten der Organisation, indem sie an diesen Mandant gebunden werden, selbst im Falle eines Resets oder eine Flashs auf das neueste Betriebssystem.

[TenantLockdown CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) ermöglicht es, HoloLens 2 nur über Autopilot an die MDM-Registrierung zu binden. Sobald der RequireNetworkInOOBE-Knoten des TenantLockdown CSP auf "true" oder "false" (anfänglich festgelegt) auf HoloLens 2 eingestellt ist, verbleibt dieser Wert auf dem Gerät, trotz erneutem Blinken, Betriebssystemupdates usw.

Sobald der RequireNetworkInOOBE-Knoten des TenantLockdown CSP auf HoloLens 2 auf „true“ gesetzt ist, wartet OOBE nach der Netzwerkverbindung unbegrenzt auf das erfolgreiche Herunterladen und Anwenden des Autopilot-Profils.

Sobald der RequireNetworkInOOBE-Knoten von TenantLockdown CSP auf HoloLens 2 auf „true“ gesetzt wird, sind folgende Vorgänge in OOBE unzulässig:

- Erstellen lokaler Benutzer mit Laufzeit-Bereitstellung 
- Durchführen einer Azure AD-Verknüpfungsoperation über Laufzeitbereitstellung 
- Auswählen, wem das Gerät in OOBE gehört 

#### Einrichtung mit Intune 
1. Erstellen Sie ein benutzerdefiniertes OMA-URI-Gerätekonfigurationsprofil und geben Sie „true“ für den RequireNetworkInOOBE-Knoten an, wie unten dargestellt.
Der OMA-URI-Wert sollte ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE lauten

   > [!div class="mx-imgBorder"]
   > ![TenantLockdown über OMA-URI einrichten](images/hololens-tenant-lockdown.png)

1. Erstellen Sie eine Gruppe und weisen Sie das Gerätekonfigurationsprofil dieser Gerätegruppe zu.

1. Machen Sie das HoloLens 2-Gerät zu einem Mitglied der im vorherigen Schritt erstellten Gruppe und lösen Sie die Synchronisierung aus.  

Überprüfen Sie im Intune-Portal, ob die Gerätekonfiguration erfolgreich angewendet wurde. Sobald diese Gerätekonfiguration erfolgreich auf das HoloLens 2-Gerät angewendet wird, sind die Effekte von TenantLockdown aktiv.

#### Aufhebung des RequireNetworkInOOBE von TenantLockdown auf HoloLens 2 mit Intune

1. Entfernen Sie die HoloLens 2 aus der Gerätegruppe, der die oben erstellte Gerätekonfiguration zuvor zugewiesen wurde.

1. Erstellen Sie ein benutzerdefiniertes OMA URI-basiertes Gerätekonfigurationsprofil und geben Sie für RequireNetworkInOOBE den Wert „false“ an, wie unten dargestellt.
Der OMA-URI-Wert sollte ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE lauten

   > [!div class="mx-imgBorder"]
   > ![Screenshot der Einstellung von RequireNetworkInOOBE auf „false“ über OMA-URI in Intune](images/hololens-tenant-lockdown-false.png)

1. Erstellen Sie eine Gruppe und weisen Sie das Gerätekonfigurationsprofil dieser Gerätegruppe zu. 

1. Machen Sie das HoloLens 2-Gerät zu einem Mitglied der im vorherigen Schritt erstellten Gruppe und lösen Sie die Synchronisierung aus.

Überprüfen Sie im Intune-Portal, ob die Gerätekonfiguration erfolgreich angewendet wurde. Sobald diese Gerätekonfiguration erfolgreich auf das HoloLens 2-Gerät angewendet wird, sind die Effekte von TenantLockdown inaktiv.

#### Was würde in OOBE geschehen, wenn das Autopilot-Profil auf HoloLens deaktiviert wird, nachdem TenantLockdown auf „wahr“ festgelegt wurde? 
OOBE wartet unbestimmte Zeit auf den Autopilot-Profil-Download. Folgendes Dialogfeld wird angezeigt. Um die Auswirkungen von TenantLockdown zu entfernen, muss das Gerät zunächst bei seinem ursprünglichen Mandanten angemeldet werden, wobei nur Autopilot verwendet werden darf. RequireNetworkInOOBE muss wie im vorherigen Schritt beschrieben zurückgesetzt werden, bevor die von TenantLockdown CSP eingeführten Einschränkungen entfernt werden.

![Geräteinterne Ansicht für den Zeitpunkt, zu dem die Richtlinie auf dem Gerät durchgesetzt wird.](images/hololens-autopilot-lockdown.png)

## Bekannte Probleme und Einschränkungen

- Wir untersuchen ein Problem, bei dem die in MEM konfigurierte gerätekontextbasierte Anwendungsinstallation nicht für HoloLens gilt. [Mehr zu Gerätekontext- und Benutzerkontext-Installationen.](https://docs.microsoft.com/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Beim Einrichten des Autopiloten über WLAN kann es vorkommen, dass das Autopilot-Profil nicht heruntergeladen wird, wenn die Internetverbindung zum ersten Mal hergestellt wird. In diesem Fall werden die Lizenzbedingungen vorgelegt, und der Benutzer hat die Möglichkeit, das Setup ohne Autopilot durchzuführen. Wenn Sie das Einrichten mit Autopilot wiederholen möchten, setzen Sie das Gerät in den Ruhezustand und fahren Sie es dann hoch, oder starten Sie das Gerät neu, und versuchen Sie es erneut.
- Das Feature „Alle Zielgeräte auf Autopilot konvertieren“ wird von HoloLens derzeit nicht unterstützt.  

### Problembehandlung

Die folgenden Artikel können für Sie hilfreich sein, um weitere Informationen zu erhalten und Probleme mit Autopilot zu beheben. Beachten Sie jedoch, dass diese Artikel auf dem Windows 10-Desktop basieren und eventuell nicht alle Informationen auf HoloLens zutreffen:

- [Windows Autopilot – bekannte Probleme](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Problembehandlung der Windows-Geräteregistrierung in Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – Richtlinienkonflikte](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## Feedback und Support für Autopilot

Verwenden Sie eine der folgenden Methoden, um Feedback zu geben oder Probleme zu melden:

- Für Unterstützung bei der Geräteregistrierung wenden Sie sich bitte an Ihren Wiederverkäufer oder Distributor.
- Bei allgemeinen Support-Anfragen zu Windows Autopilot oder bei Problemen wie Profilzuweisungen, Gruppenerstellung oder MEM-Portalsteuerungen wenden Sie sich bitte an den [Microsoft Endpoint Manager-Support](https://docs.microsoft.com/mem/get-support)   
- Wenn Ihr Gerät für den Autopilot-Dienst registriert ist und das Profil auf dem MEM-Portal zugeordnet ist, wenden Sie sich an den [HoloLens-Support](https://docs.microsoft.com/hololens/) (siehe Karte 'Support'). Eröffnen Sie bitte ein Support-Ticket und fügen Sie gegebenenfalls Screenshots und Protokolle bei, indem Sie [Offline-Diagnoseprotokolle](hololens-diagnostic-logs.md#offline-diagnostics) während der Benutzererfahrung (OOBE) erfassen.
- Um ein Problem mit dem Gerät zu melden, verwenden Sie die Feedback Hub-App auf HoloLens. Wählen Sie im Feedback Hub die **Enterprise Management Device** > **-Kategorie**.
- Wenn Sie ein allgemeines Feedback zu Autopilot für HoloLens geben möchten, können Sie diese [Umfrage](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993) einsenden.
