---
title: Windows Autopilot für HoloLens 2 (Private Vorschau)
description: Einrichtung von Autopilot auf HoloLens 2-Geräten.
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
ms.openlocfilehash: 5f887d7321c391ea9d67833373b39b3c9feeaf2c
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163089"
---
# Windows Autopilot für HoloLens 2

Wenn Sie HoloLens 2-Geräte für das Windows Autopilot-Programm einrichten, können Ihre Benutzer einem einfachen Vorgang folgen, um die Geräte aus der Cloud bereitzustellen.

Dieses Autopilot-Programm unterstützt den Self-Deployment-Modus von Autopilot zur Bereitstellung von HoloLens 2-Geräten als freigegebene Geräte unter Ihrem Mandanten. Der Self-Deployment-Modus nutzt die vorinstallierten OEM-Images und-Treiber des Geräts während des Bereitstellungsprozesses. Ein Benutzer kann das Gerät bereitstellen, ohne es einzuschalten und die vorkonfigurierte Benutzeroberfläche (Out-of-the-Box Experience, OOBE) zu durchlaufen. Um mehr über Windows Autopilot für Windows 10 zu erfahren, klicken Sie [hier](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).

Wenn ein Benutzer den Self-Deployment-Prozess von Autopilot startet, werden folgende Schritte ausgeführt:

1. Verknüpfen des Geräts mit Azure Active Directory (Azure AD).
   > [!NOTE]  
   > Autopilot für HoloLens unterstützt kein Verknüpfen mit Active Directory oder Azure AD Hybrid.
1. Verwenden von Azure AD, um das Gerät bei Microsoft Intune (oder einem anderen MDM-Dienst) zu registrieren.
1. Laden Sie die gerätebezogenen Richtlinien, benutzerbezogenen Anwendungen, Zertifikate und Netzwerkprofile herunter.
1. Bereitstellen des Geräts.
1. Präsentieren des Anmeldebildschirms für den Benutzer.

## Windows Autopilot für HoloLens 2 (Private Vorschau)

Befolgen Sie die nachstehenden Schritte, um Ihre Umgebung für die private Vorschau einzurichten:

1. Sicherstellen, dass die Voraussetzungen für Windows Autopilot für HoloLens 2 erfüllt sind
1. Registrieren für das private Vorschauprogramm für Windows Autopilot für HoloLens 2
1. Sicherstellen, dass für den Mandanten ein Test-Flight durchgeführt wurde (registriert für die Teilnahme am Programm)
1. Registrieren Ihrer Geräte bei Windows Autopilot
1. Erstellen einer Gerätegruppe
1. Erstellen eines Bereitstellungsprofils
1. Überprüfen der ESP-Konfiguration
1. Konfigurieren eines benutzerdefinierten Konfigurationsprofils für HoloLens-Geräte (bekanntes Problem)
1. Überprüfen des Profilstatus der HoloLens-Geräte


### 1. Sicherstellen, dass die Voraussetzungen für Windows Autopilot für HoloLens 2 erfüllt sind

**Lesen Sie die folgenden Abschnitte des Artikels zu den Anforderungen für Windows Autopilot:**

- [Netzwerkanforderungen](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [Lizenzierungsanforderungen](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [Konfigurationsanforderungen](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)

**Lesen Sie den Abschnitt "[Voraussetzungen](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" im Artikel zum Self-Deployment-Modus von Autopilot.** Ihre Umgebung muss diese Anforderungen zusätzlich zu den Standardanforderungen für Windows Autopilot erfüllen. Sie brauchen die Abschnitte "Schritt-für-Schritt" und "Validierung" des Artikels nicht zu lesen. Die weiter unten in diesem Artikel aufgeführten Vorgehensweisen enthalten entsprechende Schritte speziell für HoloLens. Informationen zum Registrieren und Konfigurieren von Profilen finden Sie unter [4. Registrieren von Geräten bei Windows Autopilot](#4-register-devices-in-windows-autopilot) und [6. Erstellen eines Bereitstellungsprofils](#6-create-a-deployment-profile) in diesem Artikel. In diesen Abschnitten finden Sie die für HoloLens spezifischen Schritte.

> [!IMPORTANT]  
> Windows Autopilot für HoloLens 2 weist spezifische Betriebssystemanforderungen auf. Autopilot setzt voraus, dass Windows Holographic Version 2004 (Build 19041.1103 oder höher) auf den HoloLens-Geräten vorinstalliert ist. Bei Geräten, die bis Ende September 2020 ausgeliefert wurden, ist Windows Holographic Version 1903, vorinstalliert. Wenden Sie sich an Ihren Händler, um zu erfahren, wann Autopilot-fähige Geräte verfügbar sein werden. Wenn Sie an der privaten Vorschau teilnehmen möchten, lesen Sie die Anweisungen und Anforderungen weiter unten.

Autopilot-spezifische Informationen je nach Version des HoloLens-Betriebssystems.
- Um Autopilot zu verwenden, muss [Windows Holographic, Version 2004](hololens-release-notes.md#windows-holographic-version-2004) oder neuer auf dem Gerät installiert sein.
- Um Autopilot über WLAN zu verwenden, muss [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) oder neuer auf dem Gerät installiert sein. Allerdings können diese Builds weiterhin Ethernet-Adapter verwenden. 
- In den Builds [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) wurde die neue Geräteverwaltungsoption [Tenantlockdown CSP und Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot) aktiviert.  

Wenn Sie die Buildversion auf Ihrem Gerät bestätigen oder aktualisieren möchten, schließen Sie das Gerät an Ihren Windows 10-PC an und starten Sie [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8). 

**Wenn Sie die Autopilot-Vorschau testen möchten, vergewissern Sie sich vor dem Starten der vorkonfigurierten Benutzeroberfläche (Out-of-the-Box Experience, OOBE) und des Bereitstellungsprozesses, dass die HoloLens-Geräte die folgenden Voraussetzungen erfüllen:**

- Stellen Sie sicher, dass auf Ihrem Gerät Windows Holographic, Version 2004 (Build 19041.1103 oder höher) ausgeführt wird. Wenn das neueste Betriebssystem nicht vorinstalliert ist, müssen Sie die Aktualisierung manuell mit dem [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) durchführen. Anweisungen finden Sie [hier](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device). 
- Ihre Geräte müssen bei Windows Autopilot registriert werden. Informationen zum Registrieren von Geräten finden Sie unter [4. Registrieren von Geräten bei Windows Autopilot](#4-register-devices-in-windows-autopilot). Die empfohlene Vorgehensweise ist, dass Ihr Händler oder Verteiler die Geräte für Sie registriert.  
- Unter [Windows Holographic, Version 2004](hololens-release-notes.md#windows-holographic-version-2004) müssen Geräte mit dem Internet verbunden sein, bevor HoloLens eingeschaltet und der Autopilot-Bereitstellungsprozess eingeleitet wird. Schließen Sie Ihr Gerät mit einem "USB-C an Ethernet"-Adapter für eine kabelgebundene Internetverbindung über Ethernet an.
- Unter [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) können Geräte eine Verbindung zum WLAN in OOBE herstellen, um Autopilot zu erkennen. 
- Die Geräte sind noch nicht Mitglied von Azure AD und nicht bei Intune (oder einem anderen MDM-System) angemeldet. Der Self-Deployment-Prozess für Autopilot rundet führt diese Schritte aus. Um sicherzustellen, dass alle gerätebezogenen Informationen bereinigt werden, überprüfen Sie die **Geräte**-Seiten in Azure AD und den Intune-Portalen.
- Wenn Sie die Self-Deployment-Modus-Profile von Autopilot konfigurieren und verwalten möchten, stellen Sie sicher, dass Sie Zugriff auf [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com) haben.


### 2. Registrieren für das Windows Autopilot für HoloLens 2-Programm

**Für die Teilnahme am Programm muss Ihr Mandant beim privaten Vorschauprogramm angemeldet sein. Dadurch erhalten Sie die HoloLens-spezifischen Intune UI-Steuerelemente (auch als MEM bezeichnet) für Autopilot.** Wechseln Sie zu diesem Zweck zu [Windows Autopilot für HoloLens – Anforderung der privaten Vorschau](https://aka.ms/APHoloLensTAP), oder verwenden Sie den folgenden QR-Code zum Senden einer Anforderung.  

![Autopilot-QR-Code](./images/hololens-ap-qrcode.png)  

Microsoft führt einmal pro Woche ein Test-Flight für den Mandanten durch. Nach Abschluss des Test-Flights erhalten Sie eine E-Mail-Benachrichtigung. 

Halten Sie für diese Anforderung folgende Informationen bereit:

- Mandantendomäne
- Mandanten-ID
- Anzahl der HoloLens 2-Geräte, die an dieser Evaluierung teilnehmen
- Anzahl der HoloLens 2-Geräte, die Sie unter Verwendung des Self-Deployment-Modus von Autopilot bereitstellen möchten

### 3. Sicherstellen, dass für den Mandanten ein Test-Flight durchgeführt wurde

Führen Sie nach dem Einreichen Ihrer Anforderung die folgenden Schritte aus, um zu überprüfen, ob für den Mandanten ein Test-Flight durchgeführt wurde:

1. Melden Sie sich beim [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com) an.
1. Wählen Sie **Geräte** > **Windows** > **Windows-Registrierung** > **Windows Autopilot Deployment-Profile** > **Profil erstellen** aus.  
   
   ![Die Dropdownliste "Profil erstellen" enthält ein Element "HoloLens".](./images/hololens-ap-enrollment-profiles.png)
  Die angezeigte Liste sollte die Option **HoloLens** enthalten. Ist diese Option nicht enthalten, verwenden Sie eine der [Feedback](hololens2-autopilot.md#feedback-for-autopilot)-Optionen, um uns zu kontaktieren.

### 4. Registrieren von Geräten bei Windows Autopilot

In der Vorbereitungsphase gibt es zwei primäre Möglichkeiten, wie Sie Geräte bei Windows Autopilot registrieren können: 

1. **Wenden Sie sich an Ihren Händler, wenn Sie eine Bestellung aufgeben, um Ihre Geräte registrieren zu lassen** oder
2. **Rufen Sie den Hardwarehash ab (auch als Hardware-ID bezeichnet), und registrieren Sie das Gerät manuell.** 

Weitere Informationen zur Geräteregistrierung finden Sie in der Dokumentation zum [Hinzufügen von Geräten zu Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices).  

**Abrufen eines Gerätehardwarehashs**

Das Gerät kann seinen Hardwarehash während des OOBE-Vorgangs in einer CSV-Datei aufzeichnen oder später, wenn ein Gerätebesitzer den Diagnoseprotokoll-Sammlungsprozess startet (wie im folgenden Verfahren beschrieben). Normalerweise ist der Gerätebesitzer der erste Benutzer, der sich beim Gerät anmeldet.

1. Starten Sie das HoloLens 2-Gerät.
1. Drücken Sie auf dem Gerät gleichzeitig Einschalt- und Leiser-Taste, und lassen Sie sie dann wieder los. Das Gerät sammelt Diagnoseprotokolle und den Hardwarehash und speichert sie in einer Reihe von ZIP-Dateien. 
   1. Ausführliche Informationen und ein Schulungsvideo zur Durchführung finden Sie unter [Offline-Diagnostik](hololens-diagnostic-logs.md#offline-diagnostics). 
1. Schließen Sie das Gerät mit einem USB-C-Kabel an einen Computer an.
1. Öffnen Sie den Datei-Explorer auf dem Computer. Öffnen Sie **Dieser PC\\\<*HoloLens device name*>, und suchen Sie nach der Datei „AutopilotDiagnostics.zip“.**  

   > [!NOTE]  
   > Die ZIP-Datei ist möglicherweise nicht sofort verfügbar. Wenn die Datei noch nicht bereit ist, wird im Ordner "Dokumente" möglicherweise eine Datei "HoloLensDiagnostics.temp" angezeigt. Zum Aktualisieren der Liste der Dateien aktualisieren Sie das Fenster.

1. Extrahieren Sie den Inhalt der Datei "AutopilotDiagnostics.zip".
1. Suchen Sie in den extrahierten Dateien nach der CSV-Datei mit dem Dateinamenpräfix "DeviceHash". Kopieren Sie diese Datei auf ein Laufwerk auf dem Computer, um später darauf zuzugreifen.  
   > [!IMPORTANT]  
   > Die Daten in der CSV-Datei sollten folgende Header- und Zeilenformate aufweisen:
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

**4. Registrieren des Geräts bei Windows Autopilot**

1. Wählen Sie im Microsoft Endpoint Manager Admin Center **Geräte** > **Windows** > **Windows-Registrierung** und dann unter **Windows Autopilot- Deployment-Programm** die Optionen **Geräte** > **Import** aus.

1. Wählen Sie unter **Windows Autopilot-Geräte hinzufügen** die DeviceHash-CSV-Datei, dann **Öffnen** und anschließend **Import** aus.  
   
   ![Verwenden Sie den Befehl "Import" zum Importieren des Hardwarehashs aus.](./images/hololens-ap-hash-import.png)
1. Wählen Sie nach Abschluss des Importvorgangs **Geräte** > **Windows** > **Windows-Registrierung** > **Geräte** > **Synchronisieren** aus. Je nachdem, wie viele Geräte synchronisiert werden, kann der Vorgang einige Minuten in Anspruch nehmen. Wählen Sie **Aktualisieren** aus, um das registrierte Gerät anzuzeigen.  
   
   ![Verwenden Sie die Befehle "Synchronisieren" und "Aktualisieren", um die Liste der Geräte anzuzeigen.](./images/hololens-ap-devices-sync.png)  

### 5. Erstellen einer Gerätegruppe

1. Wählen Sie im Microsoft Endpoint Manager Admin Center **Gruppen** > **Neue Gruppe** aus.
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

### 6. Erstellen eines Bereitstellungsprofils

1. Wählen Sie im Microsoft Endpoint Manager Admin Center **Geräte** > **Windows** > **Windows-Registrierung** > **Windows Autopilot Deployment-Profile** > **Profil erstellen** > **HoloLens** aus.
1. Geben Sie einen Profilnamen und eine Beschreibung ein, und wählen Sie dann **Weiter** aus.  
   
   ![Hinzufügen eines Profilnamen und einer Beschreibung](./images/hololens-ap-profile-name.png)
1. Auf der Seite **Out-of-the-Box Experience (OOBE)** sind die meisten Einstellungen der OOBE optimal für diese Evaluierung vorkonfiguriert. Sie können optional folgende Einstellungen konfigurieren:  

   - **Sprache (Region)**: Wählen Sie die Sprache für OOBE aus. Wir empfehlen, dass Sie eine Sprache aus der Liste der [unterstützten Sprachen für HoloLens 2](hololens2-language-support.md) auswählen.
   - **Tastatur automatisch konfigurieren**: Um sicherzustellen, dass die Tastatur mit der ausgewählten Sprache übereinstimmt, wählen Sie **Ja** aus.
   - **Vorlage für Gerätenamen anwenden**: Um den Gerätenamen während des OOBE-Vorgangs automatisch festzulegen, wählen Sie **Ja** aus, und geben Sie dann den Vorlagenausdruck und die Platzhalter in **Namen eingeben** ein. Geben Sie z.B. ein Präfix und `%RAND:4%`&mdash; einen Platzhalter für eine vierstellige Zufallszahl ein.
     > [!NOTE]  
     > Wenn Sie eine Vorlage für Gerätenamen verwenden, startet der OOBE-Vorgang das Gerät ein weiteres Mal neu, nachdem der Gerätenamen angewendet und bevor das Gerät mit Azure AD verbunden wird. Mit diesem Neustart wird der neue Name wirksam.  

   ![Konfigurieren der OOBE-Einstellungen](./images/hololens-ap-profile-oobe.png)
1. Nachdem Sie die Einstellungen konfiguriert haben, wählen Sie **Weiter** aus.
1. Fügen Sie auf der Seite **Bereichstags** optional die Bereichstags hinzu, die Sie auf dieses Profil anwenden möchten. Weitere Informationen zu Bereichstags finden Sie unter [Verwenden von rollenbasierten Zugriffssteuerungen und Bereichstags für verteilte IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md). Wenn Sie fertig sind, wählen Sie **Weiter** aus.
1. Wählen Sie auf der Seite **Zuweisungen** für **Zuweisen an** die Option **Ausgewählte Gruppen** aus.
1. Wählen Sie unter **AUSGEWÄHLTE GRUPPEN** die Option **+ Wählen Sie die Gruppen aus, die eingeschlossen werden sollen** aus.
1. Wählen Sie in der Liste **Wählen Sie die Gruppen aus, die eingeschlossen werden sollen** die Gerätegruppe, die Sie für die Autopilot HoloLens-Geräte erstellt haben, und dann **Weiter**aus.  
  
   Wenn Sie Gruppen ausschließen möchten, wählen Sie **Wählen Sie die Gruppen aus, die ausgeschlossen werden sollen** und dann die Gruppen aus, die Sie ausschließen möchten.

   ![Weisen Sie dem Profil eine Gerätegruppe zu.](./images/hololens-ap-profile-assign-devicegroup.png)
1. Überprüfen Sie auf der Seite **Überprüfen und erstellen** die Einstellungen und dann **Erstellen** aus, um das Profil zu erstellen.  
   
   ![Überprüfen und erstellen](./images/hololens-ap-profile-summ.png)

### 7. Überprüfen der ESP-Konfiguration

Auf der Seite "Registrierungsstatus" (ESP) wird der Status des gesamten Gerätekonfigurationsprozesses angezeigt, der ausgeführt wird, wenn ein durch MDM verwalteter Benutzer sich das erste Mal bei einem Gerät anmeldet. Stellen Sie sicher, dass Ihre ESP-Konfiguration wie folgt aussieht, und überprüfen Sie, ob die Zuweisungen korrekt sind.  

![ESP-Konfiguration](./images/hololens-ap-profile-settings.png)

### 8. Überprüfen des Profilstatus der HoloLens-Geräte.

1. Wählen Sie im Microsoft Endpoint Manager Admin Center **Geräte** > **Windows** > **Windows-Registrierung** > **Geräte** aus.
1. Vergewissern Sie sich, dass die HoloLens-Geräte aufgelistet sind und Ihr Profilstatus **Zugewiesen** lautet.  
   > [!NOTE]  
   > Es kann einige Minuten dauern, bis das Profil dem Gerät zugewiesen wurde.  
   
   ![Geräte- und Profilzuweisungen.](./images/hololens-ap-devices-assignments.png)

## Windows Autopilot für HoloLens 2 – Benutzeroberfläche

Sobald die obigen Anweisungen abgeschlossen sind, werden Benutzer der HoloLens 2 folgende Erfahrungen bei der Bereitstellung ihrer HoloLens-Geräte machen:  

1. Für die Autopilot-Nutzung ist ein Internetzugriff erforderlich. Verwenden Sie eine der folgenden Optionen für den Internetzugriff:
    - Schließen Sie Ihr Gerät an ein WLAN-Netzwerk in OOBE an. Lassen Sie es dann automatisch Autopilot finden. Das ist das einzige Mal, dass Sie mit OOBE interagieren müssen, bis Autopilot von selbst abgeschlossen ist. Beachten Sie, dass HoloLens 2 nach der Internet-Erkennung standardmäßig 10 Sekunden wartet, bis es Autopilot findet. Wenn kein Autopilot-Profil innerhalb von 10 Sekunden erkannt wird, zeigt OOBE EULA an. Wenn dieses Szenario auftritt, starten Sie Ihr Gerät neu, um die Autopilot-Erkennung erneut zu versuchen. Beachten Sie auch, dass OOBE nur dann unbegrenzt auf Autopilot wartet, wenn die TenantLockdown-Richtlinie auf dem Gerät eingestellt ist.
    - Schließen Sie Ihr Gerät mit einem „USB-C an Ethernet“-Adapter für eine kabelgebundene Internetverbindung an das Ethernet an. Lassen Sie HoloLens 2 automatisch Autopilot vervollständigen.
    - Schließen Sie Ihr Gerät mit einem "USB-C an WLAN"-Adapter für eine kabellose Internetverbindung an. Lassen Sie HoloLens 2 automatisch Autopilot vervollständigen.

       > [!NOTE]
       > Die Verwendung von Autopilot wirkt sich auf den [Gerätebesitzer](security-adminless-os.md#device-owner) aus.
   
       > [!IMPORTANT]  
       > Um WLAN in OOBE für Autopilot zu verwenden, benötigen Geräte [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2).
       >
       > Bei Geräten, die Ethernet-Adapter verwenden, müssen Sie das Gerät an das Netzwerk anschließen, bevor die Out-of-the-Box-Erfahrung (OOBE) beginnt. Auf dem ersten OOBE-Bildschirm wird ermittelt, ob das Gerät als Autopilot-Gerät bereitgestellt wird. Wenn das Gerät keine Verbindung mit dem Netzwerk herstellen kann, oder wenn Sie sich entscheiden, das Gerät nicht als Autopilot-Gerät bereitzustellen, können Sie zu einem späteren Zeitpunkt nicht zur Autopilot-Bereitstellung wechseln. Stattdessen müssten Sie diesen Vorgang erneut ausführen, um das Gerät als Autopilot-Gerät bereitzustellen.

1. Das Gerät sollte die OOBE automatisch starten. Interagieren Sie nicht mit OOBE. Lehnen Sie sich stattdessen ganz entspannt zurück. Lassen Sie HoloLens 2 die Netzwerkverbindung ermitteln, und geben Sie der Anwendung die Zeit, den OOBE-Vorgang automatisch auszuführen. Das Gerät kann während des OOBE-Vorgangs neu gestartet werden. Die OOBE-Bildschirme sollten wie folgt aussehen.
   
   ![OOBE, Schritt 1](./images/hololens-ap-uex-1.png)
   ![OOBE, Schritt 2](./images/hololens-ap-uex-2.png)
   ![OOBE, Schritt 3](./images/hololens-ap-uex-3.png)
   ![OOBE, Schritt 4](./images/hololens-ap-uex-4.png)

1. Am Ende des OOBE-Vorgangs können Sie sich mit Ihrem Benutzernamen und Kennwort beim Gerät anmelden.

   ![OOBE, Schritt 5](./images/hololens-ap-uex-5.png)

## Bekannte Probleme

- Sie können keine Anwendungen installieren, die den Gerätesicherheitskontext verwenden.

## Tenantlockdown CSP und Autopilot
- Hält die Geräte am Mandanten der Organisation fest. Die Geräte werden an den Mandanten gebunden, selbst wenn sie zurückgesetzt werden oder erneut blinken. Mit zusätzlicher Sicherheit, indem die Einrichtung von Konten bei der Bereitstellung untersagt wird. 

HoloLens 2-Geräte unterstützen jetzt TenantLockdown CSP ab Windows Holographic Version 20H2. 

[TenantLockdown CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) ermöglicht es, HoloLens 2 nur über Autopilot an die MDM-Registrierung zu binden. Sobald der RequireNetworkInOOBE-Knoten des TenantLockdown CSP auf "true" oder "false" (anfänglich festgelegt) auf HoloLens 2 eingestellt ist, verbleibt dieser Wert auf dem Gerät, trotz erneutem Blinken, Betriebssystemupdates usw. 

Sobald der RequireNetworkInOOBE-Knoten des TenantLockdown CSP auf HoloLens 2 auf „true“ gesetzt ist, wartet OOBE nach der Netzwerkverbindung unbegrenzt auf das erfolgreiche Herunterladen und Anwenden des Autopilot-Profils. 

Sobald der RequireNetworkInOOBE-Knoten von TenantLockdown CSP auf HoloLens 2 auf „true“ gesetzt wird, sind folgende Vorgänge in OOBE unzulässig: 
- Erstellen lokaler Benutzer mit Laufzeit-Bereitstellung 
- Durchführen einer AAD-Join-Operation über Laufzeit-Bereitstellung 
- Auswählen, wem das Gerät in OOBE gehört 

### Einrichtung mit Intune 
1. Erstellen Sie ein benutzerdefiniertes OMA-URI-Gerätekonfigurationsprofil und geben Sie „true“ für den RequireNetworkInOOBE-Knoten an, wie unten dargestellt.
Der OMA-URI-Wert sollte ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE lauten

   > [!div class="mx-imgBorder"]
   > ![TenantLockdown über OMA-URI einrichten](images/hololens-tenant-lockdown.png)

1. Erstellen Sie eine Gruppe und weisen Sie das Gerätekonfigurationsprofil dieser Gerätegruppe zu. 

1. Machen Sie das HoloLens 2-Gerät zu einem Mitglied der im vorherigen Schritt erstellten Gruppe und lösen Sie die Synchronisierung aus.  

Überprüfen Sie im Intune-Portal, ob die Gerätekonfiguration erfolgreich angewendet wurde. Sobald diese Gerätekonfiguration erfolgreich auf das Hololens 2-Gerät angewendet wird, sind die Auswirkungen von TenantLockdown aktiv.

### Aufhebung des RequireNetworkInOOBE von TenantLockdown auf HoloLens 2 mit Intune 
1. Entfernen Sie die HoloLens 2 aus der Gerätegruppe, der die oben erstellte Gerätekonfiguration zuvor zugewiesen wurde. 

1. Erstellen Sie ein benutzerdefiniertes OMA URI-basiertes Gerätekonfigurationsprofil und geben Sie für RequireNetworkInOOBE den Wert „false“ an, wie unten dargestellt. Der OMA-URI-Wert sollte ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE lauten

   > [!div class="mx-imgBorder"]
   > ![Screenshot der Einstellung von RequireNetworkInOOBE auf „false“ über OMA-URI in Intune](images/hololens-tenant-lockdown-false.png)

1. Erstellen Sie eine Gruppe und weisen Sie das Gerätekonfigurationsprofil dieser Gerätegruppe zu. 

1. Machen Sie das HoloLens 2-Gerät zu einem Mitglied der im vorherigen Schritt erstellten Gruppe und lösen Sie die Synchronisierung aus.

Überprüfen Sie im Intune-Portal, ob die Gerätekonfiguration erfolgreich angewendet wurde. Sobald diese Gerätekonfiguration erfolgreich auf dem Hololens 2-Gerät angewendet wurde, sind die Effekte von TenantLockdown inaktiv. 

### Was passiert in OOBE, wenn das Autopilot-Profil auf HoloLens nicht zugewiesen wurde, nachdem TenantLockdown auf "true" festgelegt wurde? 
OOBE wartet unbestimmte Zeit auf den Autopilot-Profil-Download. Folgendes Dialogfeld wird angezeigt. Um die Auswirkungen von TenantLockdown zu entfernen, muss das Gerät zunächst bei seinem ursprünglichen Mandanten angemeldet werden, wobei nur Autopilot verwendet werden darf. RequireNetworkInOOBE muss wie im vorherigen Schritt beschrieben zurückgesetzt werden, bevor die von TenantLockdown CSP eingeführten Einschränkungen entfernt werden. 

![Geräteinterne Ansicht für den Zeitpunkt, zu dem die Richtlinie auf dem Gerät durchgesetzt wird.](images/hololens-autopilot-lockdown.png)

## Feedback zu Autopilot

Verwenden Sie eine der folgenden Methoden, um Feedback zu geben oder Probleme zu melden:

- Verwenden Sie die Feedback-App. Sie finden diese App auf mit HoloLens verbundenen Computern. Wählen Sie im Feedback-Hub die Kategorie **Unternehmensverwaltung** > **Gerät** aus.  

  Wenn Sie Feedback geben oder ein Problem melden möchten, geben Sie eine detaillierte Beschreibung an. Fügen Sie gegebenenfalls Screenshots und Protokolle hinzu.
- Senden Sie eine E-Mail-Nachricht an [hlappreview@Microsoft.com](mailto:hlappreview@microsoft.com). Geben Sie als Betreff der E-Mail**\<*Tenant*>\<*Tenant*> ein (wobei \<*Tenant*> der Name Ihres Intune-Mandanten ist).**

  Geben Sie in Ihrer Nachricht eine detaillierte Beschreibung an. Fügen Sie jedoch keine Daten wie Screenshots oder Protokolle hinzu, es sei denn, die Supportmitarbeiter fordern diese ausdrücklich an. Diese Daten können private oder personenbezogene Informationen (PII) enthalten.
