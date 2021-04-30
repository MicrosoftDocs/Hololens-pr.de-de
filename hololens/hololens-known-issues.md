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
ms.openlocfilehash: 54bc090352983e814c64deea8f1f401c24e3261b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308845"
---
# <a name="known-issues-for-hololens"></a>Bekannte Probleme bei HoloLens

Dies ist die aktuelle Liste bekannter Probleme für HoloLens-Geräte. Überprüfen Sie hier zuerst, ob ein ungewöhnliches Verhalten auftritt. Diese Liste wird aktualisiert, wenn neue Probleme erkannt oder gemeldet werden oder wenn Probleme in zukünftigen HoloLens-Softwareupdates behoben werden.

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

- Auf der Seite Virtuelle Eingabe sind die Steuerelemente Gesten und Bildlauf im Abschnitt Virtuelle Gesten nicht funktionsfähig. Deren Verwendung hat keine Auswirkungen. Die virtuelle Tastatur auf derselben Seite funktioniert ordnungsgemäß.

- Nach dem Aktivieren des Entwicklermodus in den Einstellungen kann es einige Sekunden dauern, bis der Schalter aktiviert Geräteportal ist.

### <a name="onedrive-camera-upload"></a>Hochladen der OneDrive-Kamera

Die OneDrive-App für HoloLens unterstützt keinen automatischen Kameraupload für Arbeits- oder Schulkonten.

Problemumgehungen:

- Wenn dies für Ihr Unternehmen sinnvoll ist, wird der automatische Kameraupload für Microsoft-Kundenkonten unterstützt. Sie können sich bei Ihrem Microsoft-Konto zusätzlich zu Ihrem Arbeits-, Schul- oder Schulkonto anmelden (die OneDrive-App unterstützt die duale Anmeldung). In Ihrem Microsoft-Konto in OneDrive können Sie den automatischen Rollup der Hintergrundkamera aktivieren.

- Wenn Sie einen Consumer-Microsoft-Konto zum automatischen Hochladen Ihrer Fotos nicht sicher verwenden können, können Sie Fotos manuell aus der OneDrive-App in Ihr Arbeits-, Schul- oder Schulkonto hochladen. Stellen Sie dazu sicher, dass Sie bei Ihrem Arbeits- oder Schulkonto in der OneDrive-App angemeldet sind. Wählen Sie die **+** Schaltfläche und dann Hochladen **aus.** Suchen Sie die Fotos oder Videos, die Sie hochladen möchten, indem Sie zu Bilder > **Camera Roll navigieren.** Wählen Sie die Fotos oder Videos aus, die Sie hochladen möchten, und klicken Sie dann auf **die Schaltfläche** Öffnen.

## <a name="known-issues-for-hololens-2-devices"></a>Bekannte Probleme bei HoloLens 2 Geräten

### <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge kann nicht gestartet werden

Einige Kunden haben ein Problem gemeldet, bei dem Microsoft Edge nicht gestartet werden kann. Für diese Kunden bleibt das Problem durch einen Neustart bestehen und wird nicht mit Windows- oder Anwendungsupdates gelöst. Wenn dieses Problem besteht und Sie bestätigt haben, dass [Windows](hololens-updates.md#manually-check-for-updates)auf dem neuesten Stand ist, melden Sie einen Fehler aus der [Feedback-Hub-App](hololens-feedback.md) mit der folgenden Kategorie und Unterkategorie: Installieren und Aktualisieren > Herunterladen, Installieren und Konfigurieren von Windows Update.

Es gibt keine bekannten Problemumgehungen, da wir das Problem bisher nicht beheben konnten. Das Einreichen eines Fehlers über Feedback-Hub hilft uns bei der Untersuchung!

### <a name="keyboard-does-not-switch-to-special-characters"></a>Tastatur wechselt nicht zu Sonderzeichen

Während der OOBE tritt ein Problem auf. Sobald der Benutzer ein Arbeits- oder Schulkonto ausgewählt hat und sein Kennwort eingibt, wird der Versuch, zu den Sonderzeichen auf der Tastatur zu wechseln, indem auf die Schaltfläche &123 tippt, nicht in Sonderzeichen geändert. 

Work-arounds:
-   Schließen Sie die Tastatur, und öffnen Sie sie erneut, indem Sie auf das Textfeld tippen.
-   Geben Sie ihr Kennwort falsch ein. Wenn die Tastatur beim nächsten Mal neu gestartet wird, funktioniert sie wie erwartet.
- Webauthentifizierung: Schließen Sie die Tastatur, und wählen **Sie Von einem anderen Gerät aus anmelden aus.** 
-   Wenn nur Zahlen eingegeben werden, kann ein Benutzer bestimmte Tasten drücken und gedrückt halten, um ein erweitertes Menü zu öffnen.
-   Verwenden einer USB-Tastatur.

Dies wirkt sich nicht auf:
- Benutzer, die sich für die Verwendung eines persönlichen Kontos entscheiden.

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build"></a>Blauer Bildschirm wird angezeigt, nachdem die Registrierung von Insider-Vorschaubuilds auf einem Gerät aufgehoben wurde, das mit einem Insider-Build umgestrichen wurde.

Dies ist ein Problem, das sich auf Benutzer auswirkt, die sich in einem Insider-Vorschaubuild befanden, ihre HoloLens 2 mit einem neuen Insider Preview-Build umgestrichen und dann die Registrierung für das Insider-Programm aufgehoben haben. 

Dies wirkt sich nicht auf:
- Benutzer, die nicht für Windows-Insider registriert sind 
- Insider:
    - Wenn ein Gerät registriert wurde, da Insider-Builds Version 18362.x waren
    - Wenn sie einen Von Insider signierten 19041.x-Build flashten, bleiben Sie für das Insider-Programm registriert. 

Umgehen: 
- Vermeiden Sie das Problem. 
    - Flashen sie einen Nicht-Insider-Build. Eines der regelmäßigen monatlichen Updates. 
    - Stay on Insider Preview
- Neustarten des Geräts

    1. Stellen Sie [HoloLens 2 manuell in den Flashmodus,](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) indem Sie vollständig heruntergefahren werden, ohne eine Verbindung herzustellen. Tippen Sie dann beim Halten des Volumes auf den Netzschalter.
    
    1. Stellen Sie eine Verbindung mit dem PC herstellen, und öffnen Sie Advanced Recovery Companion. 
    
    1. Flashen HoloLens 2 auf den Standard-Build.   

## <a name="known-issues-for-hololens-1st-gen"></a>Bekannte Probleme bei HoloLens (1. Generation)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Verbindung und Bereitstellung in HoloLens über Visual Studio

> [!NOTE]
> Letztes Update: 8.08.um 17:11 Uhr– Visual Studio hat VS 2019 Version 16.2 veröffentlicht, die eine Lösung für dieses Problem enthält. Es wird empfohlen, auf diese neueste Version zu aktualisieren, um diesen Fehler zu vermeiden.

Visual Studio version 16.2 von VS 2019 veröffentlicht, das eine Lösung für dieses Problem enthält. Es wird empfohlen, auf diese neueste Version zu aktualisieren, um diesen Fehler zu vermeiden.

Grundursache des Problems: Benutzer, die Visual Studio 2015 oder frühe Releases von Visual Studio 2017 zum Bereitstellen und Debuggen von Anwendungen auf ihrer HoloLens verwendet haben und anschließend die neuesten Versionen von Visual Studio 2017 oder Visual Studio 2019 mit derselben HoloLens verwendet haben, sind betroffen. Die neueren Releases von Visual Studio eine neue Version einer Komponente bereitstellen, aber Dateien der älteren Version bleiben auf dem Gerät übrig, was dazu führt, dass die neuere Version fehlschlägt.  Dies verursacht die folgende Fehlermeldung: DEP0100: Stellen Sie sicher, dass für das Zielgerät der Entwicklermodus aktiviert ist. Eine Entwicklerlizenz für konnte aufgrund des \<ip\> Fehlers 80004005 nicht erworben werden.

#### <a name="workaround"></a>Problemumgehung

Unser Team arbeitet derzeit an einer Lösung. In der Zwischenzeit können Sie die folgenden Schritte ausführen, um das Problem zu beheben und die Blockierung von Bereitstellung und Debuggen zu beheben:  

1. Öffnen Sie Visual Studio.

1. Klicken Sie auf **Datei** > **Neu** > **Projekt**.

1. Wählen **Sie Visual C#**  >  **Windows Desktop** Console App  >  **(.NET Framework) aus.**

1. Geben Sie dem Projekt einen Namen (z.B. "HoloLensDeploymentFix"), und stellen Sie sicher, dass das Framework auf mindestens .NET Framework 4.5 festgelegt ist, und klicken Sie dann auf **OK.**

1. Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf den Knoten **Verweise,** und fügen Sie die folgenden Verweise hinzu (wählen **Sie** zum Abschnitt Durchsuchen und **dann Durchsuchen aus):**

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Wenn Sie 10.0.18362.0 nicht installiert haben, verwenden Sie die neueste Version, die Sie haben. 

1. Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen **Sie**  >  **Vorhandenes Element hinzufügen** aus.

1. Navigieren Sie zu C:\Programme (x86)\Windows Kits\10\bin\10.0.18362.0\x86, und ändern Sie den Filter in **Alle Dateien ( . \* \* )**.

1. Wählen Sie sowohl SirepClient.dll als auch SshClient.dll und dann **Hinzufügen** aus.

1. Suchen Sie beide Dateien in Projektmappen-Explorer (sie sollten sich unten in der Liste der Dateien befinden), und wählen Sie sie aus, und ändern Sie kopieren in **Ausgabeverzeichnis** im **Eigenschaftenfenster** in **Immer kopieren.**

1. Fügen Sie am Anfang der Datei der vorhandenen Liste der -Anweisungen Folgendes `using` hinzu:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. Fügen `static void Main(...)` Sie in den folgenden Code hinzu:

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

1. Öffnen Sie ein Eingabeaufforderungsfenster und cd in dem Ordner, der die kompilierte EXE-Datei enthält (z.B. C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Führen Sie die ausführbare Datei aus, und geben Sie die IP-Adresse des Geräts als Befehlszeilenargument an. (Wenn sie über USB verbunden ist, können Sie 127.0.0.1 verwenden, andernfalls die Wi-Fi IP-Adresse des Geräts.)  Beispiel: "HoloLensDeploymentFix 127.0.0.1".

1. Nachdem das Tool ohne Nachrichten beendet wurde (dies sollte nur wenige Sekunden dauern), können Sie ab Visual Studio 2017 oder neuer bereitstellen und debuggen.  Die fortgesetzte Verwendung des Tools ist nicht erforderlich.

Wir werden weitere Updates bereitstellen, sobald sie verfügbar werden.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Probleme beim Starten der Microsoft Store und Apps auf HoloLens

> [!NOTE]
> Letztes Update: 4/2 @ 10:00 Uhr – Problem behoben. 

Beim Versuch, die Microsoft Store und Apps auf HoloLens zu starten, treten möglicherweise Probleme auf. Wir haben festgestellt, dass das Problem auftritt, wenn Hintergrund-App-Updates eine neuere Version von Frameworkpaketen in bestimmten Sequenzen bereitstellen, während eine oder mehrere ihrer abhängigen Apps noch ausgeführt werden. In diesem Fall hat ein automatisches App-Update eine neue Version von .NET Native Framework bereitgestellt (Version 10.0.25531 bis 10.0.27413), die dazu führte, dass die ausgeführten Apps nicht ordnungsgemäß für alle ausgeführten Apps aktualisiert wurden, die die vorherige Version des Frameworks nutzen.  Der Ablauf für das Frameworkupdate lautet wie folgt: 

1. Das neue Frameworkpaket wird aus dem Store heruntergeladen und installiert.

1. Alle Apps älteren Frameworks werden aktualisiert, um die neuere Version zu verwenden.

Wenn Schritt 2 vor dem Abschluss unterbrochen wird, können alle Apps, für die das neuere Framework nicht registriert wurde, nicht über das Startmenü gestartet werden.  Wir glauben, dass jede App auf HoloLens von diesem Problem betroffen sein könnte.

Einige Benutzer haben gemeldet, dass das Schließen von hängenden Apps und das Starten anderer Apps wie Feedback-Hub, 3D-Viewer oder Photos das Problem für sie behebt. Dies funktioniert jedoch nicht &mdash; in 100 % der Fälle.

Wir haben die Ursache dafür, dass dieses Problem nicht durch das Update selbst verursacht wurde, sondern durch einen Fehler im Betriebssystem, der dazu führte, dass das .NET Native Framework-Update falsch behandelt wurde. Wir freuen uns bekanntgeben zu können, dass wir eine Korrektur ermittelt und ein Update (Betriebssystemversion 17763.380) veröffentlicht haben, das den Fix enthält.  

Um zu überprüfen, ob Ihr Gerät das Update übernehmen kann, gehen Sie wie hier beschrieben vor:

1. Wechseln Sie zur App Einstellungen, und öffnen Sie **Update & Security**.

1. Wählen Sie **Nach Updates suchen aus.**

1. Wenn ein Update auf 17763.380 verfügbar ist, aktualisieren Sie auf diesen Build, um die Behebung des Fehlers "App Hängt" zu erhalten.

1. Nach dem Aktualisieren auf diese Version des Betriebssystems sollten die Apps wie erwartet funktionieren.

Darüber hinaus haben wir wie bei jedem HoloLens-Betriebssystem-Release das FFU-Image im [Microsoft Download Center veröffentlicht.](https://aka.ms/hololensdownload/10.0.17763.380)

Wenn Sie das Update nicht verwenden möchten, haben wir eine neue Version der Microsoft Store UWP-App ab dem 29. Januar veröffentlicht. Nachdem Sie über die aktualisierte Version des Speichers verfügen:

1. Öffnen Sie den Store, und vergewissern Sie sich, dass er geladen wird.
1. Verwenden Sie die Geste "Bloom", um das Menü zu öffnen.
1. Versuchen Sie, zuvor fehlerhafte Apps zu öffnen.
1. Wenn sie immer noch nicht gestartet werden kann, tippen Sie auf das Symbol der fehlerhaften App, halten Sie sie fest, und wählen Sie Deinstallieren aus.
1. Installieren Sie diese Apps erneut aus dem Store.

Wenn Ihr Gerät weiterhin keine Apps laden kann, können Sie eine Version des .NET Native Frameworks und der Runtime über das Download Center querladen, indem Sie die folgenden Schritte ausführen:

1. Laden Sie [diese ZIP-Datei](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) aus dem Microsoft Download Center herunter. Beim Entpacken werden zwei Dateien erzeugt.  Microsoft .NET.Native.Runtime.1.7.appx und Microsoft .NET.Native.Framework.1.7.appx.

1. Vergewissern Sie sich, dass Ihr Gerät vom Entwickler entsperrt ist.  Wenn Sie dies noch nicht getan haben, finden Sie anweisungen unter [Verwenden der Windows-Geräteportal.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)

1. Sie möchten dann in den Windows-Geräteportal gelangen. Es wird empfohlen, dies über USB zu tun, und Sie würden dies tun, indem Sie http://127.0.0.1:10080 in Ihren Browser eingeben.

1. Nachdem Sie die Windows-Geräteportal haben, müssen Sie die beiden heruntergeladenen Dateien "querladen". Dazu müssen Sie die linke Seitenleiste nach unten wechseln, bis Sie zum Abschnitt **Apps** gelangen und **Apps** auswählen.

1. Daraufhin wird ein Bildschirm angezeigt, der dem folgenden ähnelt.  Navigieren Sie zum Abschnitt **App installieren,** und navigieren Sie zu dem Punkt, an dem Sie diese beiden APPX-Dateien entpackt haben. Sie können jeweils nur einen auswählen. Klicken Sie also nach dem Auswählen des ersten Eintrags im Abschnitt Bereitstellen auf "Los". Gehen Sie dann für die zweite APPX-Datei vor.

   ![Windows-Geräteportal zum Installieren Side-Loaded App](images/20190322-DevicePortal.png)
   
1. An diesem Punkt sind wir der Meinung, dass Ihre Anwendungen wieder funktionieren sollten und Dass Sie auch zum Store gelangen können.

1. In einigen Fällen ist es erforderlich, den zusätzlichen Schritt zum Starten der App 3D-Viewer, bevor die betroffenen Apps gestartet werden. 

Wir freuen uns über Ihre Geduld, da wir den Prozess zur Lösung dieses Problems durchgegangen sind, und freuen uns auf die weitere Zusammenarbeit mit unserer Community, um erfolgreiche Mixed Reality zu schaffen.

### <a name="device-update"></a>Geräteupdate

- 30 Sekunden nach einem neuen Update verschwindet die Shell möglicherweise einmal. Führen Sie die **Blumengeste** aus, um Ihre Sitzung wieder aufzunehmen.

### <a name="visual-studio"></a>Visual Studio

- Unter [Installieren der Tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) finden Sie die aktuelle Version von Visual Studio, die für die HoloLens-Entwicklung empfohlen wird.

- Beim Bereitstellen einer App von Visual Studio auf Ihrer HoloLens wird möglicherweise der Folgende angezeigt: Der angeforderte Vorgang kann nicht für eine Datei ausgeführt werden, in der ein vom Benutzer zugeordneter **Abschnitt geöffnet ist. (Ausnahme von HRESULT: 0x800704C8)**. Versuchen Sie es in diesem Fall erneut, und Ihre Bereitstellung ist im Allgemeinen erfolgreich.

### <a name="api"></a>API

- Wenn die Anwendung den [Fokuspunkt](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) hinter dem Benutzer oder die normale auf camera.forward legt, werden Hologramme nicht in Mixed Reality-Aufnahme Videos angezeigt. Bis dieser Fehler in Windows behoben ist, sollten Anwendungen, wenn sie aktiv den Fokuspunkt festlegen, sicherstellen, dass die Normale ebene gegenüber der Kamera (z. B. normal = -camera.forward) festgelegt ist. [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity)

### <a name="xbox-wireless-controller"></a>Xbox Wireless Controller

- Xbox Wireless Controller S muss aktualisiert werden, bevor es mit HoloLens verwendet werden kann. Stellen Sie [sicher, dass Sie auf dem neuesten Stand](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) sind, bevor Sie versuchen, Ihren Controller mit einer HoloLens zu koppeln.

- Wenn Sie Ihre HoloLens neu starten, während der Xbox Wireless Controller verbunden ist, stellt der Controller die Verbindung mit HoloLens nicht automatisch wieder her. Das Guide-Schaltflächenlicht blinkt langsam, bis der Controller nach 3 Minuten ausgeschaltet wird. Um den Controller sofort wieder zu verbinden, schließen Sie den Controller aus, indem Sie die Taste Guide gedrückt halten, bis das Licht ausgeschaltet wird. Wenn Sie den Controller wieder ein-/aus-netzen, wird die Verbindung mit HoloLens wiederhergestellt.

- Wenn Ihre HoloLens in den Standbymodus versetzt wird, während der Xbox Wireless Controller verbunden ist, wird die HoloLens durch jede Eingabe auf dem Controller reaktiviert. Sie können dies verhindern, indem Sie Ihren Controller ausschalten, wenn Sie ihn nicht mehr verwenden.

## <a name="known-issues-for-hololens-emulator"></a>Bekannte Probleme beim HoloLens-Emulator

- Nicht alle Apps im Microsoft Store sind mit dem Emulator kompatibel. Beispielsweise können Young Conker und Fragmente im Emulator nicht wiedergegeben werden.
- Sie können die PC-Webcam nicht im Emulator verwenden.
- Die Livevorschaufunktion des Windows-Geräteportal funktioniert nicht mit dem Emulator. Sie können weiterhin Mixed Reality Videos und Bilder erfassen.
