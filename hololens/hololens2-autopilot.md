---
title: Windows Autopilot für HoloLens 2 – Evaluierungshandbuch
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 4/10/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilot
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: 3d98e67e79ae10b606c529adbda95dbb61b8fd15
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829440"
---
# Windows Autopilot für HoloLens 2 – Evaluierungshandbuch

Wenn Sie HoloLens 2-Geräte für das Windows Autopilot-Programm einrichten, können Ihre Benutzer einem einfachen Vorgang folgen, um die Geräte aus der Cloud bereitzustellen.

Dieses Autopilot-Programm unterstützt den Self-Deployment-Modus von Autopilot zur Bereitstellung von HoloLens 2-Geräten als freigegebene Geräte unter Ihrem Mandanten. Der Self-Deployment-Modus nutzt die vorinstallierten OEM-Images und-Treiber des Geräts während des Bereitstellungsprozesses. Ein Benutzer kann das Gerät bereitstellen, ohne es einzuschalten und die vorkonfigurierte Benutzeroberfläche (Out-of-the-Box Experience, OOBE) zu durchlaufen.  

![Der Self-Deployment-Prozess von Autopilot konfiguriert freigegebene Geräte über eine Netzwerkverbindung im monitorlosen Modus.](./images/hololens-ap-intro.png)

Wenn ein Benutzer den Self-Deployment-Prozess von Autopilot startet, werden folgende Schritte ausgeführt:

1. Verknüpfen des Geräts mit Azure Active Directory (Azure AD).
   > [!NOTE]  
   > Autopilot für HoloLens unterstützt kein Verknüpfen mit Active Directory oder Azure AD Hybrid.
1. Verwenden von Azure AD, um das Gerät bei Microsoft Intune (oder einem anderen MDM-Dienst) zu registrieren.
1. Laden Sie die gerätebezogenen Richtlinien, benutzerbezogenen Anwendungen, Zertifikate und Netzwerkprofile herunter.
1. Bereitstellen des Geräts.
1. Präsentieren des Anmeldebildschirms für den Benutzer.

## Windows Autopilot für HoloLens 2 – Erste Schritte

Die folgenden Schritten fassen den Vorgang zum Einrichten Ihrer Umgebung für Windows Autopilot für HoloLens 2 zusammen. In restlichen Abschnitt werden die Details zu diesen Schritten beschrieben.

1. Sicherstellen, dass die Voraussetzungen für Windows Autopilot für HoloLens erfüllt sind.
1. Registrieren für das Windows Autopilot für HoloLens 2-Programm.
1. Sicherstellen, dass für den Mandanten ein Test-Flight durchgeführt wurde (registriert für die Teilnahme am Programm).
1. Registrieren von Geräten bei Windows Autopilot.
1. Erstellen einer Gerätegruppe.
1. Erstellen eines Bereitstellungsprofils.
1. Überprüfen der ESP-Konfiguration.
1. Konfigurieren eines benutzerdefinierten Konfigurationsprofils für HoloLens-Geräte (bekanntes Problem).
1. Überprüfen des Profilstatus der HoloLens-Geräte.

### 1. Sicherstellen, dass die Voraussetzungen für Windows Autopilot für HoloLens erfüllt sind
Die neuesten Informationen zur Teilnahme am Programm finden Sie unter [Windows-Insider-Versionshinweise](hololens-insider.md#windows-insider-release-notes).

Lesen Sie die folgenden Abschnitte des Artikels zu den Anforderungen für Windows Autopilot:

- [Netzwerkanforderungen](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [Lizenzierungsanforderungen](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [Konfigurationsanforderungen](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)
> [!IMPORTANT]  
> Im Gegensatz zu anderen Windows Autopilot-Programmen weist Windows Autopilot für HoloLens 2 spezifische Betriebssystemanforderungen auf.

Lesen Sie den Abschnitt "[Voraussetzungen](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" im Artikel zum Self-Deployment-Modus von Autopilot. Ihre Umgebung muss diese Anforderungen zusätzlich zu den Standardanforderungen für Windows Autopilot erfüllen.

> [!NOTE]  
> Sie brauchen die Abschnitte "Schritt-für-Schritt" und "Validierung" des Artikels nicht zu lesen. Die weiter unten in diesem Artikel aufgeführten Vorgehensweisen enthalten entsprechende Schritte speziell für HoloLens.

> [!IMPORTANT]  
> Informationen zum Registrieren und Konfigurieren von Profilen finden Sie unter [4. Registrieren von Geräten bei Windows Autopilot](#4-register-devices-in-windows-autopilot) und [6. Erstellen eines Bereitstellungsprofils](#6-create-a-deployment-profile) in diesem Artikel. In diesen Abschnitten finden Sie die für HoloLens spezifischen Schritte.

Vergewissern Sie sich vor dem Starten der vorkonfigurierten Benutzeroberfläche (Out-of-the-Box Experience, OOBE) und des Bereitstellungsprozesses, dass die HoloLens-Geräte die folgenden Voraussetzungen erfüllen:

- Die Geräte sind noch keine Mitglieder von Azure AD und noch nicht bei Intune (oder einem anderen MDM-System) registriert. Der Self-Deployment-Prozess für Autopilot rundet führt diese Schritte aus. Um sicherzustellen, dass alle gerätebezogenen Informationen bereinigt werden, überprüfen Sie die **Geräte**-Seiten in Azure AD und Intune.
- Jedes Gerät kann eine Verbindung mit dem Internet herstellen. Sie können „USB-C auf Ethernet“-Adapter für eine kabelgebundene Internetverbindung oder „USB C auf WLAN“-Adapter für eine drahtlose Internetverbindung verwenden. 
- Jedes Gerät kann mithilfe eines USB-C-Kabels an einen Computer angeschlossen werden, und auf diesem Computer ist [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) installiert.
- Jedes Gerät hat das neueste Windows-Update installiert: Windows 10, Version 19041.1002.200107-0909 oder eine neuere Version.

Wenn Sie die Self-Deployment-Modus-Profile von Autopilot konfigurieren und verwalten möchten, stellen Sie sicher, dass Sie Zugriff auf [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com) haben.

### 2. Registrieren für das Windows Autopilot für HoloLens 2-Programm

Wenn Sie am Programm teilnehmen möchten, müssen Sie einen Mandanten verwenden, für den ein Test-Flight für HoloLens durchgeführt wurde. Wechseln Sie zu diesem Zweck zu [Windows Autopilot für HoloLens – Anforderung der privaten Vorschau](https://aka.ms/APHoloLensTAP), oder verwenden Sie den folgenden QR-Code zum Senden einer Anforderung.  

![Autopilot-QR-Code](./images/hololens-ap-qrcode.png)  

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
  Die angezeigte Liste sollte die Option **HoloLens** enthalten. Ist diese Option nicht enthalten, verwenden Sie eine der [Feedback](#feedback)-Optionen, um uns zu kontaktieren.

### 4. Registrieren von Geräten bei Windows Autopilot

Um ein HoloLens-Gerät im Windows Autopilot-Programm zu registrieren, müssen Sie den Hardwarehash des Geräts abrufen (auch als Hardware-ID bezeichnet). Das Gerät kann seinen Hardwarehash während des OOBE-Vorgangs in einer CSV-Datei aufzeichnen oder später, wenn ein Gerätebesitzer den Diagnoseprotokoll-Sammlungsprozess startet (wie im folgenden Verfahren beschrieben). Normalerweise ist der Gerätebesitzer der erste Benutzer, der sich beim Gerät anmeldet.

**Abrufen eines Gerätehardwarehashs**

1. Starten Sie das HoloLens 2-Gerät.
1. Drücken Sie auf dem Gerät gleichzeitig Einschalt- und Leiser-Taste, und lassen Sie sie dann wieder los. Das Gerät sammelt Diagnoseprotokolle und den Hardwarehash und speichert sie in einer Reihe von ZIP-Dateien.
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

Ihre HoloLens-Benutzer können diese Schritte zum Bereitstellen von HoloLens-Geräten ausführen.  

1. Verwenden Sie das USB-C-Kabel, um das HoloLens-Gerät an einen Computer anzuschließen, auf dem Advanced Recovery Companion (ARC) installiert und das entsprechende Windows-Update heruntergeladen wurde.
1. Verwenden Sie ARC, um die geeignete Version von Windows auf das Gerät zu flashen.
1. Schließen Sie das Gerät an das Netzwerk an, und starten Sie das Gerät dann neu.  
   > [!IMPORTANT]  
   > Sie müssen das Gerät an das Netzwerk anschließen, bevor die vorkonfigurierte Benutzeroberfläche (Out-of-the-Box Experience, OOBE) gestartet wird. Auf dem ersten OOBE-Bildschirm wird ermittelt, ob das Gerät als Autopilot-Gerät bereitgestellt wird. Wenn das Gerät keine Verbindung mit dem Netzwerk herstellen kann, oder wenn Sie sich entscheiden, das Gerät nicht als Autopilot-Gerät bereitzustellen, können Sie zu einem späteren Zeitpunkt nicht zur Autopilot-Bereitstellung wechseln. Stattdessen müssten Sie diesen Vorgang erneut ausführen, um das Gerät als Autopilot-Gerät bereitzustellen.

   Das Gerät sollte die OOBE automatisch starten. Interagieren Sie nicht mit OOBE. Lehnen Sie sich stattdessen ganz entspannt zurück. Lassen Sie HoloLens 2 die Netzwerkverbindung ermitteln, und geben Sie der Anwendung die Zeit, den OOBE-Vorgang automatisch auszuführen. Das Gerät kann während des OOBE-Vorgangs neu gestartet werden. Die OOBE-Bildschirme sollten wie folgt aussehen.
   
   ![OOBE, Schritt 1](./images/hololens-ap-uex-1.png)
   ![OOBE, Schritt 2](./images/hololens-ap-uex-2.png)
   ![OOBE, Schritt 3](./images/hololens-ap-uex-3.png)
   ![OOBE, Schritt 4](./images/hololens-ap-uex-4.png)

Am Ende des OOBE-Vorgangs können Sie sich mit Ihrem Benutzernamen und Kennwort beim Gerät anmelden.

  ![OOBE, Schritt 5](./images/hololens-ap-uex-5.png)

## Bekannte Probleme

- Sie können keine Anwendungen installieren, die den Gerätesicherheitskontext verwenden.

## Feedback senden

Verwenden Sie eine der folgenden Methoden, um Feedback zu geben oder Probleme zu melden:

- Verwenden Sie die Feedback-App. Sie finden diese App auf mit HoloLens verbundenen Computern. Wählen Sie im Feedback-Hub die Kategorie **Unternehmensverwaltung** > **Gerät** aus.  

  Wenn Sie Feedback geben oder ein Problem melden möchten, geben Sie eine detaillierte Beschreibung an. Fügen Sie gegebenenfalls Screenshots und Protokolle hinzu.
- Senden Sie eine E-Mail-Nachricht an [hlappreview@Microsoft.com](mailto:hlappreview@microsoft.com). Geben Sie als Betreff der E-Mail**\<*Tenant*>\<*Tenant*> ein (wobei \<*Tenant*> der Name Ihres Intune-Mandanten ist).**

  Geben Sie in Ihrer Nachricht eine detaillierte Beschreibung an. Fügen Sie jedoch keine Daten wie Screenshots oder Protokolle hinzu, es sei denn, die Supportmitarbeiter fordern diese ausdrücklich an. Diese Daten können private oder personenbezogene Informationen (PII) enthalten.
