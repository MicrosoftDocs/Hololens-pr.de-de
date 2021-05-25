---
title: Bekannte Probleme bei HoloLens
description: Halten Sie sich mit unserer Liste bekannter Probleme und Problemumgehungen auf dem Laufenden, die sich auf HoloLens-Kunden und -Entwickler auswirken können, die Unity und die Windows-Geräteportal verwenden.
keywords: Problembehandlung, bekanntes Problem, Hilfe
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: bc1d399a07a6a0622c953178cad7be1b8a018fdb
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397781"
---
# <a name="known-issues-for-hololens"></a>Bekannte Probleme bei HoloLens

Hier ist die aktuelle Liste der bekannten Probleme für HoloLens-Geräte. Überprüfen Sie hier zuerst, ob ein ungewöhnliches Verhalten angezeigt wird. Diese Liste wird aktualisiert, wenn neue Probleme erkannt oder gemeldet werden oder wenn Probleme in zukünftigen HoloLens-Softwareupdates behoben werden.

>[!NOTE]
> - Wenn Sie ein Problem feststellen, das Sie nicht blockiert, melden Sie es auf Ihrem HoloLens-Gerät über [Feedback-Hub](hololens-feedback.md).
> - Wenn das problemverdrückte Problem Sie zusätzlich zum Einreichen von Feedback blockiert, senden Sie [bitte eine Supportanfrage.](https://aka.ms/hlsupport)

- [Bekannte Probleme für alle HoloLens-Generationen](#known-issues-for-all-hololens-generations)
- [Bekannte Probleme bei HoloLens 2 Geräten](#known-issues-for-hololens-2-devices)
- [Bekannte Probleme bei HoloLens (1. Generation)](#known-issues-for-hololens-1st-gen)
- [Bekannte Probleme beim HoloLens-Emulator](#known-issues-for-hololens-emulator)

## <a name="known-issues-for-all-hololens-generations"></a>Bekannte Probleme für alle HoloLens-Generationen

### <a name="unity"></a>Unity

- Informationen zur neuesten Version von Unity, die für die HoloLens-Entwicklung empfohlen wird, finden Sie unter Installieren der [Tools.](https://docs.microsoft.com/windows/mixed-reality/install-the-tools)
- Bekannte Probleme mit der Unity HoloLens Technical Preview sind in den [HoloLens Unity-Foren](https://forum.unity3d.com/threads/known-issues.394627/)dokumentiert.

### <a name="windows-device-portal"></a>Windows-Geräteportal

- Die Livevorschaufunktion in Mixed Reality Aufzeichnung kann einige Sekunden Wartezeit aufweisen.

- Auf der Seite Virtuelle Eingabe sind die Steuerelemente Gesten und Scrollen im Abschnitt Virtuelle Gesten nicht funktionsfähig. Deren Verwendung hat keine Auswirkungen. Die virtuelle Tastatur auf der virtuellen Eingabeseite funktioniert ordnungsgemäß.

- Nach dem Aktivieren des Entwicklermodus in den Einstellungen kann es einige Sekunden dauern, bis der Schalter aktiviert Geräteportal ist.

### <a name="onedrive-camera-upload"></a>Hochladen der OneDrive-Kamera

Die OneDrive-App für HoloLens unterstützt keinen automatischen Kameraupload für Arbeits- oder Schulkonten.

Problemumgehungen:

- Wenn dies für Ihr Unternehmen sinnvoll ist, wird der automatische Kameraupload für Microsoft-Kundenkonten unterstützt. Sie können sich bei Ihrem Microsoft-Konto zusätzlich zu Ihrem Arbeits-, Schul- oder Schulkonto anmelden (die OneDrive-App unterstützt die duale Anmeldung). In Ihrem Microsoft-Konto in OneDrive können Sie den automatischen Rollup der Hintergrundkamera aktivieren.

- Wenn Sie einen Consumer-Microsoft-Konto zum automatischen Hochladen Ihrer Fotos nicht sicher verwenden können, können Sie Fotos manuell aus der OneDrive-App in Ihr Arbeits-, Schul- oder Schulkonto hochladen. Stellen Sie dazu sicher, dass Sie bei Ihrem Arbeits- oder Schulkonto in der OneDrive-App angemeldet sind. Wählen Sie die **+** Schaltfläche und dann Hochladen **aus.** Suchen Sie die Fotos oder Videos, die Sie hochladen möchten, indem Sie zu Bilder > **Camera Roll navigieren.** Wählen Sie die Fotos oder Videos aus, die Sie hochladen möchten, und klicken Sie dann auf **die Schaltfläche** Öffnen.

## <a name="known-issues-for-hololens-2-devices"></a>Bekannte Probleme bei HoloLens 2 Geräten

### <a name="device-using-auto-login-asks-for-log-in"></a>Gerät mit automatischer Anmeldung fordert zur Anmeldung auf

Ein HoloLens 2-Gerät kann so konfiguriert werden, dass es sich automatisch über Anmeldeoptionen für Einstellungskonten -> anmeldet und unter Erforderlich den Wert auf  ->    ->   **Never (Nie) festlegen.**  Einige Benutzer müssen sich möglicherweise erneut beim Gerät anmelden, wenn sie ein Gerät mit einem wesentlich großen Update aktualisieren, z. B. einem Featureupdate.

Beispiel für den Fall, dass dies auftreten kann:

- Aktualisieren eines Geräts von Windows Holographic, Version 2004 (Build 19041.xxxx) auf Windows Holographic, Version 21H1 (Build 20346.xxxx)
- Aktualisieren eines Geräts, um ein großes Update auf demselben Hauptversions-Build zu übernehmen, z. B. Windows Holographic, Version 2004 auf Windows Holographic, Version 20H2
- Aktualisieren eines Geräts von einem Factoryimage auf das neueste Image

Dies sollte in den:

- Geräte, die ein monatliches Wartungsupdate durchführen

Umgehen von Methoden:

- Anmeldemethoden wie PIN, Kennwort, Iris, Webauthentifizierung oder FIDO2-Schlüssel.
- Wenn die Geräte-PIN nicht gespeichert werden kann und andere Authentifizierungsmethoden nicht verfügbar sind, kann ein Benutzer den [manuellen Reflashingmodus](hololens-recovery.md#manual-procedure)verwenden.

### <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge kann nicht gestartet werden

> [!NOTE]
> Dieses Problem wurde ursprünglich mit der Versandversion von Microsoft Edge erstellt. Dieses Problem kann im [neuen Microsoft Edge](hololens-new-edge.md)behoben werden. Wenn dies nicht dere ist, senden Sie uns Feedback.

Einige Kunden haben ein Problem gemeldet, bei dem Microsoft Edge nicht gestartet werden kann. Für diese Kunden bleibt das Problem durch einen Neustart bestehen und wird nicht mit Windows- oder Anwendungsupdates gelöst. Wenn dieses Problem auftritt und Sie bestätigt haben, dass [Windows auf dem neuesten Stand ist,](hololens-updates.md#manually-check-for-updates)melden Sie einen Fehler aus der [Feedback-Hub-App](hololens-feedback.md) mit der folgenden Kategorie und Unterkategorie: Installieren und Aktualisieren > Herunterladen, Installieren und Konfigurieren Windows Update.

Es gibt keine bekannten Problemumgehungen, da wir das Problem bisher nicht lösen konnten. Das Melden eines Fehlers über Feedback-Hub hilft uns bei unserer Untersuchung!

### <a name="keyboard-does-not-switch-to-special-characters"></a>Tastatur wechselt nicht zu Sonderzeichen

Während der OOBE tritt ein Problem auf, bei dem der Benutzer, nachdem er ein Arbeits- oder Schulkonto ausgewählt hat und sein Kennwort eingibt, versucht, zu den Sonderzeichen auf der Tastatur zu wechseln, indem er auf die Schaltfläche &123 tippt, nicht in Sonderzeichen geändert wird.

Work-arounds:
-   Schließen Sie die Tastatur, und öffnen Sie sie erneut, indem Sie auf das Textfeld tippen.
-   Geben Sie ihr Kennwort falsch ein. Wenn die Tastatur beim nächsten Mal neu gestartet wird, funktioniert sie wie erwartet.
- Webauthentifizierung: Schließen Sie die Tastatur, und wählen **Sie Von einem anderen Gerät aus anmelden aus.**
-   Wenn nur Zahlen eingeben, kann ein Benutzer bestimmte Tasten drücken und halten, um ein erweitertes Menü zu öffnen.
-   Verwenden einer USB-Tastatur.

Dies hat keine Auswirkungen auf:
- Benutzer, die sich für die Verwendung eines persönlichen Kontos entscheiden.

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-an-insider-build"></a>Der blaue Bildschirm wird angezeigt, nachdem die Registrierung von Insider-Vorschauversionen auf einem Gerät mit einem Insider-Build neu erstellt wurde.

Dieses Problem wirkt sich auf Benutzer aus, die sich in einem Insider Preview-Build befinden, ihre HoloLens 2 mit einem neuen Insider Preview-Build neu auftippten und dann die Registrierung beim Insider-Programm wieder auftänden.

Dies hat keine Auswirkungen auf:
- Benutzer, die nicht in der Windows-Insider 
- Insider:
    - Wenn ein Gerät seit Insider-Builds registriert wurde, version 18362.x
    - Wenn sie einen Insider-signierten 19041.x-Build flashten und beim Insider-Programm registriert bleiben

Umgeknung: 
- Vermeiden Sie das Problem. 
    - Flash für einen Nicht-Insider-Build. Eines der regelmäßigen monatlichen Updates.
    - Stay on Insider Preview
- Neustarten des Geräts

    1. Stellen Sie [HoloLens 2 manuell in den Flashmodus,](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) indem Sie vollständig heruntergefahren werden, ohne eine Verbindung herzustellen. Tippen Sie dann beim Halten des Volumes auf den Netzschalter.
    
    1. Stellen Sie eine Verbindung mit dem PC herstellen, und öffnen Sie Advanced Recovery Companion.
    
    1. Flashen Sie die HoloLens 2 auf den Standardbuild.

## <a name="known-issues-for-hololens-1st-gen"></a>Bekannte Probleme bei HoloLens (1. Generation)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Herstellen einer Verbindung und Bereitstellung für HoloLens über Visual Studio

> [!NOTE]
> Letztes Update: 8/8 @ 17:11 Uhr – Visual Studio hat VS 2019 Version 16.2 veröffentlicht, das eine Behebung dieses Problems enthält. Es wird empfohlen, auf diese neueste Version zu aktualisieren, um zu vermeiden, dass dieser Fehler auftritt.

Visual Studio hat VS 2019 Version 16.2 veröffentlicht, die eine Behebung dieses Problems enthält. Es wird empfohlen, auf diese neueste Version zu aktualisieren, um zu vermeiden, dass dieser Fehler auftritt.

Problemursache: Benutzer, die Visual Studio 2015 oder frühe Releases von Visual Studio 2017 verwendet haben, um Anwendungen auf ihrer HoloLens bereitzustellen und zu debuggen und anschließend die neuesten Versionen von Visual Studio 2017 oder Visual Studio 2019 mit derselben HoloLens zu verwenden, sind betroffen. Die neueren Releases von Visual Studio eine neue Version einer Komponente bereitstellen, aber Dateien aus der älteren Version bleiben auf dem Gerät erhalten, sodass die neuere Version fehlschlägt.  Dies verursacht die folgende Fehlermeldung: DEP0100: Stellen Sie sicher, dass für das Zielgerät der Entwicklermodus aktiviert ist. Aufgrund des Fehlers 80004005 konnte keine Entwicklerlizenz für erhalten \<ip\> werden.

#### <a name="workaround"></a>Problemumgehung

Unser Team arbeitet derzeit an einer Lösung. In der Zwischenzeit können Sie die folgenden Schritte ausführen, um das Problem zu umgehen und die Blockierung von Bereitstellung und Debuggen aufzuheben:  

1. Öffnen Sie Visual Studio.

1. Klicken Sie auf **Datei** > **Neu** > **Projekt**.

1. Wählen Sie **Visual C#**  >  **Windows Desktop** Console App  >  **(.NET Framework)** aus.

1. Geben Sie dem Projekt einen Namen (z.B. "HoloLensDeploymentFix"), und stellen Sie sicher, dass das Framework auf mindestens .NET Framework 4.5 festgelegt ist, und klicken Sie dann auf **OK.**

1. Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf den Knoten **Verweise,** und fügen Sie die folgenden Verweise hinzu (wählen Sie zum Abschnitt **Durchsuchen** und **dann Durchsuchen aus):**

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Wenn Sie 10.0.18362.0 nicht installiert haben, verwenden Sie die neueste Version, die Sie haben. 

1. Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen **Sie**  >  **Vorhandenes Element hinzufügen** aus.

1. Navigieren Sie zu C:\Programme (x86)\Windows Kits\10\bin\10.0.18362.0\x86, und ändern Sie den Filter in **Alle Dateien ( . \* \* )**.

1. Wählen Sie sowohl SirepClient.dll als auch SshClient.dll und dann **Hinzufügen aus.**

1. Suchen Sie beide Dateien in Projektmappen-Explorer , und wählen Sie sie aus (sie sollten sich  am unteren Rand der Liste der Dateien befinden), und ändern Sie im Fenster Eigenschaften die Option In Ausgabeverzeichnis kopieren in **Immer kopieren.** 

1. Fügen Sie am Anfang der Datei der vorhandenen Liste von Anweisungen Folgendes `using` hinzu:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. Fügen Sie `static void Main(...)` in den folgenden Code hinzu:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Wählen Sie **Erstellen** > **Projektmappe erstellen** aus.

1. Öffnen Sie ein Eingabeaufforderungsfenster, und öffnen Sie cd in den Ordner, der die kompilierte EXE-Datei enthält (z.B. C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Führen Sie die ausführbare Datei aus, und geben Sie die IP-Adresse des Geräts als Befehlszeilenargument an. (Wenn eine Verbindung über USB besteht, können Sie 127.0.0.1 verwenden. Verwenden Sie andernfalls die Wi-Fi IP-Adresse des Geräts.)  Beispiel: "HoloLensDeploymentFix 127.0.0.1".

1. Nachdem das Tool ohne Nachrichten beendet wurde (dies sollte nur einige Sekunden dauern), können Sie ab Visual Studio 2017 oder neuer bereitstellen und debuggen.  Die weitere Verwendung des Tools ist nicht erforderlich.

Wir werden weitere Updates bereitstellen, sobald sie verfügbar sind.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Probleme beim Starten der Microsoft Store apps auf HoloLens

> [!NOTE]
> Letztes Update: 4/2 @ 10 AM – Problem behoben.

Beim Versuch, die Anwendung und die Apps auf HoloLens zu starten, können Probleme Microsoft Store werden. Wir haben festgestellt, dass das Problem auftritt, wenn Hintergrund-App-Updates eine neuere Version von Frameworkpaketen in bestimmten Sequenzen bereitstellen, während eine oder mehrere ihrer abhängigen Apps noch ausgeführt werden. In diesem Fall hat ein automatisches App-Update eine neue Version von .NET Native Framework bereitgestellt (Version 10.0.25531 bis 10.0.27413), die dazu führte, dass die ausgeführten Apps nicht ordnungsgemäß für alle ausgeführten Apps aktualisiert wurden, die die vorherige Version des Frameworks nutzen.  Der Ablauf für das Frameworkupdate lautet wie folgt:

1. Das neue Frameworkpaket wird aus dem Store heruntergeladen und installiert.

1. Alle Apps älteren Frameworks werden aktualisiert, um die neuere Version zu verwenden.

Wenn Schritt 2 vor dem Abschluss unterbrochen wird, können alle Apps, für die das neuere Framework nicht registriert wurde, nicht über das Startmenü gestartet werden.  Wir sind der Meinung, dass jede App auf HoloLens von diesem Problem betroffen sein könnte.

Einige Benutzer haben gemeldet, dass das Schließen von hängenden Apps und das Starten anderer Apps wie Feedback-Hub, 3D-Viewer oder Photos das Problem für sie löst. Dies funktioniert jedoch nicht zu 100 % der Zeit.

Wir haben grundverursachet, dass dieses Problem nicht das Update selbst verursacht hat, sondern ein Fehler im Betriebssystem, der dazu führte, dass das .NET Native Frameworkupdate falsch behandelt wurde. Wir freuen uns, bekanntgeben zu können, dass wir eine Korrektur identifiziert und ein Update (Betriebssystemversion 17763.380) veröffentlicht haben, das die Fehlerbehebung enthält.  

So prüfen Sie, ob Ihr Gerät das Update durchführen kann:

1. Wechseln Sie zur App Einstellungen, und öffnen **Sie Update & Security**.

1. Wählen Sie **Nach Updates suchen** aus.

1. Wenn ein Update auf 17763.380 verfügbar ist, aktualisieren Sie auf diesen Build, um die Korrektur für den App Hang-Fehler zu erhalten.

1. Nach dem Aktualisieren auf diese Version des Betriebssystems sollten die Apps wie erwartet funktionieren.

Darüber hinaus haben wir wie bei jeder HoloLens-Betriebssystemversion das FFU-Image im [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380)veröffentlicht.

Wenn Sie das Update nicht durchführen möchten, haben wir ab dem 29. Mai eine neue Version der Microsoft Store UWP-App veröffentlicht. Nachdem Sie über die aktualisierte Version des Speichers verfügen:

1. Öffnen Sie den Store, und vergewissern Sie sich, dass er geladen wird.
1. Verwenden Sie die Geste "Bloom", um das Menü zu öffnen.
1. Versuchen Sie, zuvor fehlerhafte Apps zu öffnen.
1. Wenn sie immer noch nicht gestartet werden kann, tippen Sie auf das Symbol der fehlerhaften App, halten Sie sie fest, und wählen Sie Deinstallieren aus.
1. Installieren Sie diese Apps aus dem Store neu.

Wenn Ihr Gerät weiterhin keine Apps laden kann, können Sie eine Version des .NET Native Frameworks und der Runtime über das Download Center querladen, indem Sie die folgenden Schritte ausführen:

1. Laden Sie [diese ZIP-Datei](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) aus dem Microsoft Download Center herunter. Beim Entpacken werden zwei Dateien erzeugt.  Microsoft .NET.Native.Runtime.1.7.appx und Microsoft .NET.Native.Framework.1.7.appx.

1. Vergewissern Sie sich, dass Ihr Gerät entsperrt ist.  Wenn Sie dies noch nicht getan haben, finden Sie unter [Verwenden](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) des Windows-Geräteportal Anweisungen.

1. Anschließend möchten Sie in die Windows-Geräteportal. Es wird empfohlen, dies über USB zu tun. Geben Sie dazu in Ihren http://127.0.0.1:10080 Browser ein.

1. Nachdem Sie die Windows-Geräteportal haben, müssen Sie die beiden heruntergeladenen Dateien "side load" laden. Dazu müssen Sie die linke Seitenleiste nach unten wechseln, bis Sie zum Abschnitt **Apps** wechseln und **Apps auswählen.**

1. Dann wird ein Bildschirm angezeigt, der dem folgenden ähnelt.  Sie möchten zum Abschnitt App  installieren wechseln und dort navigieren, wo Sie diese beiden APPX-Dateien entpackt haben. Sie können immer nur einen Schritt nach dem anderen tun. Klicken Sie daher nach dem Auswählen des ersten Schritts im Abschnitt Bereitstellen auf "Los". Gehen Sie dann für die zweite APPX-Datei vor.

   ![Windows-Geräteportal zum Installieren Side-Loaded App](images/20190322-DevicePortal.png)
   
1. An diesem Punkt sind wir der Meinung, dass Ihre Anwendungen wieder funktionieren sollten und dass Sie auch zum Store kommen können.

1. In einigen Fällen ist es erforderlich, den zusätzlichen Schritt zum Starten der App 3D-Viewer, bevor die betroffenen Apps gestartet werden. 

Wir freuen uns über Ihre Geduld, da wir den Prozess zur Lösung dieses Problems durchgegangen sind, und freuen uns auf die weitere Zusammenarbeit mit unserer Community, um erfolgreiche Mixed Reality zu schaffen.

### <a name="device-update"></a>Geräteupdate

- 30 Sekunden nach einem neuen Update verschwindet die Shell möglicherweise einmal. Führen Sie die **Blumengeste** aus, um Ihre Sitzung wieder aufzunehmen.

### <a name="visual-studio"></a>Visual Studio

- Unter [Installieren der Tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) finden Sie die aktuelle Version von Visual Studio, die für die HoloLens-Entwicklung empfohlen wird.

- Beim Bereitstellen einer App von Visual Studio auf Ihrer HoloLens wird möglicherweise der Folgende angezeigt: Der angeforderte Vorgang kann nicht für eine Datei ausgeführt werden, in der ein vom Benutzer zugeordneter **Abschnitt geöffnet ist. (Ausnahme von HRESULT: 0x800704C8)**. Versuchen Sie es in diesem Fall erneut, und Ihre Bereitstellung ist im Allgemeinen erfolgreich.

### <a name="api"></a>API

- Wenn die Anwendung den [Fokuspunkt](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) hinter dem Benutzer oder die normale auf camera.forward festlegt, werden Hologramme nicht in Mixed Reality-Aufnahme Fotos oder Videos angezeigt. Bis dieser Fehler in Windows behoben ist, sollten Anwendungen, die den [Fokuspunkt](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) aktiv festlegen, sicherstellen, dass die Normalität der Ebene in umgekehrter Richtung (z. B. normal = -camera.forward) festgelegt wird.

### <a name="xbox-wireless-controller"></a>Xbox Wireless Controller

- Xbox Wireless Controller S muss aktualisiert werden, bevor er mit HoloLens verwendet werden kann. Stellen Sie [sicher,](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) dass Sie auf dem neuesten Stand sind, bevor Sie versuchen, Ihren Controller mit einer HoloLens zu koppeln.

- Wenn Sie Ihre HoloLens neu starten, während der Xbox Wireless Controller verbunden ist, stellt der Controller nicht automatisch erneut eine Verbindung mit HoloLens her. Die Schaltfläche "Leitfaden" blinkt langsam, bis der Controller nach 3 Minuten ausgeschaltet wird. Um den Controller sofort wieder zu verbinden, schalten Sie den Controller aus, indem Sie die Schaltfläche Guide (Leitfaden) gedrückt halten, bis das Licht ausgeschaltet wird. Wenn Sie den Controller wieder einschalten, wird die Verbindung mit HoloLens wiederhergestellt.

- Wenn Ihre HoloLens in den Standbymodus wechselt, während der Xbox Wireless Controller verbunden ist, aktiviert jede Eingabe auf dem Controller die HoloLens. Sie können dies verhindern, indem Sie Ihren Controller ausschalten, wenn Sie ihn nicht mehr verwenden.

## <a name="known-issues-for-hololens-emulator"></a>Bekannte Probleme beim HoloLens-Emulator

- Nicht alle Apps im Microsoft Store sind mit dem Emulator kompatibel. Beispielsweise können Young Conker und Fragmente im Emulator nicht wiedergegeben werden.
- Sie können die PC-Webcam nicht im Emulator verwenden.
- Die Livevorschaufunktion des Windows-Geräteportal funktioniert nicht mit dem Emulator. Sie können weiterhin Mixed Reality Videos und Bilder erfassen.
