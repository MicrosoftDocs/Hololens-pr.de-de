---
title: Bekannte Probleme bei HoloLens (1. Generation)
description: Halten Sie sich mit unserer Liste bekannter Probleme und Problemumgehungen auf dem Laufenden, die sich auf HoloLens Kunden und Entwickler auswirken können, die Unity und die Windows Geräteportal verwenden.
keywords: Problembehandlung, bekanntes Problem, Hilfe
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: d2a8ae420a0c1d646625fe81b166e2daae07e44652b70f2e4a1b19ccba240cfb
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663937"
---
# <a name="known-issues-for-hololens-1st-gen"></a>Bekannte Probleme bei HoloLens (1. Generation)

Hier ist die aktuelle Liste der bekannten Probleme für HoloLens Geräte. Überprüfen Sie hier zuerst, ob ein ungewöhnliches Verhalten auftritt. Diese Liste wird aktualisiert, wenn neue Probleme erkannt oder gemeldet werden oder wenn Probleme in zukunft HoloLens Softwareupdates behoben werden.

>[!NOTE]
> - Wenn Sie ein Problem feststellen, das Sie nicht blockiert, melden Sie es auf Ihrem HoloLens Gerät über [Feedback-Hub](hololens-feedback.md).
> - Wenn das problemverdrückte Problem sie zusätzlich zum Einreichen von Feedback blockiert, senden Sie [bitte eine Supportanfrage.](https://aka.ms/hlsupport)


- [Bekannte Probleme für alle HoloLens Generationen](#known-issues-for-all-hololens-generations)
- [Bekannte Probleme bei HoloLens (1. Generation)](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>Bekannte Probleme für alle HoloLens Generationen

### <a name="unity"></a>Unity

- Informationen zur neuesten Version von Unity, die für die entwicklung HoloLens empfohlen wird, finden Sie unter Installieren der [Tools.](/windows/mixed-reality/install-the-tools)
- Bekannte Probleme mit der Unity HoloLens Technical Preview sind in den [HoloLens Unity-Foren](https://forum.unity3d.com/threads/known-issues.394627/)dokumentiert.

### <a name="windows-device-portal"></a>Windows-Geräteportal

- Die Livevorschaufunktion in Mixed Reality Aufzeichnung kann einige Sekunden Wartezeit aufweisen.

- Auf der Seite Virtuelle Eingabe sind die Steuerelemente Gesten und Scrollen im Abschnitt Virtuelle Gesten nicht funktionsfähig. Deren Verwendung hat keine Auswirkungen. Die virtuelle Tastatur auf der virtuellen Eingabeseite funktioniert ordnungsgemäß.

- Nachdem Sie den Entwicklermodus in Einstellungen aktiviert haben, kann es einige Sekunden dauern, bis der Schalter die Geräteportal aktiviert hat.

### <a name="onedrive-camera-upload"></a>OneDrive Kameraupload

Die OneDrive-App für HoloLens unterstützt keinen automatischen Kameraupload für Arbeits- oder Schulkonten.

Problemumgehungen:

- Wenn dies für Ihr Unternehmen geeignet ist, wird der automatische Kameraupload für Microsoft-Kundenkonten unterstützt. Sie können sich zusätzlich zu Ihrem Arbeits- oder Schulkonto bei Ihrem Microsoft-Konto anmelden (die OneDrive-App unterstützt die duale Anmeldung). In Ihrem Microsoft-Konto-Profil in OneDrive können Sie den automatischen Kamerarollup im Hintergrund aktivieren.

- Wenn Sie einen Consumer Microsoft-Konto nicht sicher zum automatischen Hochladen Ihrer Fotos verwenden können, können Sie Fotos manuell über die OneDrive-App in Ihr Arbeits- oder Schulkonto hochladen. Stellen Sie hierzu sicher, dass Sie bei Ihrem Arbeits- oder Schulkonto in der OneDrive-App angemeldet sind. Wählen Sie die **+** Schaltfläche und dann **Hochladen** aus. Suchen Sie die Fotos oder Videos, die Sie hochladen möchten, indem Sie zu **Bilder > Kameraroll navigieren.** Wählen Sie die Fotos oder Videos aus, die Sie hochladen möchten, und klicken Sie dann auf die Schaltfläche **Öffnen.**

## <a name="known-issues-for-hololens-1st-gen"></a>Bekannte Probleme bei HoloLens (1. Generation)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Über Visual Studio kann keine Verbindung hergestellt und für HoloLens bereitgestellt werden.

> [!NOTE]
> Letztes Update: 8/8 @ 17:11 Uhr – Visual Studio hat VS 2019 Version 16.2 veröffentlicht, die eine Behebung dieses Problems enthält. Es wird empfohlen, auf diese neueste Version zu aktualisieren, um zu vermeiden, dass dieser Fehler auftritt.

Visual Studio hat VS 2019 Version 16.2 veröffentlicht, die eine Behebung dieses Problems enthält. Es wird empfohlen, auf diese neueste Version zu aktualisieren, um zu vermeiden, dass dieser Fehler auftritt.

Problemursache: Benutzer, die Visual Studio 2015 oder frühe Releases von Visual Studio 2017 verwendet haben, um Anwendungen auf ihrem HoloLens bereitzustellen und zu debuggen, und anschließend die neuesten Versionen von Visual Studio 2017 oder Visual Studio 2019 mit demselben HoloLens verwendet haben, sind betroffen. Die neueren Releases von Visual Studio eine neue Version einer Komponente bereitstellen, aber Dateien aus der älteren Version bleiben auf dem Gerät erhalten, was dazu führt, dass die neuere Version fehlschlägt.  Dies verursacht die folgende Fehlermeldung: DEP0100: Stellen Sie sicher, dass für das Zielgerät der Entwicklermodus aktiviert ist. Aufgrund eines Fehlers 80004005 konnte keine Entwicklerlizenz für erhalten \<ip\> werden.

#### <a name="workaround"></a>Problemumgehung

Unser Team arbeitet derzeit an einer Lösung. In der Zwischenzeit können Sie die folgenden Schritte ausführen, um das Problem zu umgehen und die Blockierung von Bereitstellung und Debuggen aufzuheben:  

1. Öffnen Sie Visual Studio.

1. Klicken Sie auf **Datei** > **Neu** > **Projekt**.

1. Wählen Sie **Visual C#**  >  **Windows Desktop** Console App  >  **(.NET Framework)** aus.

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

1. Suchen Sie beide Dateien in Projektmappen-Explorer (sie sollten sich unten in der Liste der Dateien befinden), und wählen Sie sie aus, und ändern Sie im Fenster **Eigenschaften** die Option **In Ausgabeverzeichnis** kopieren in **Immer kopieren.**

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

1. Öffnen Sie ein Eingabeaufforderungsfenster, und öffnen Sie cd in dem Ordner, der die kompilierte .exe Datei enthält (z.B. C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Führen Sie die ausführbare Datei aus, und geben Sie die IP-Adresse des Geräts als Befehlszeilenargument an. (Wenn sie über USB verbunden ist, können Sie 127.0.0.1 verwenden, andernfalls die Wi-Fi IP-Adresse des Geräts.)  Beispiel: "HoloLensDeploymentFix 127.0.0.1".

1. Nachdem das Tool ohne Nachrichten beendet wurde (dies sollte nur wenige Sekunden dauern), können Sie ab Visual Studio 2017 oder neuer bereitstellen und debuggen.  Die fortgesetzte Verwendung des Tools ist nicht erforderlich.

Wir werden weitere Updates bereitstellen, sobald sie verfügbar werden.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Probleme beim Starten der Microsoft Store und Apps auf HoloLens

> [!NOTE]
> Letztes Update: 4/2 @ 10:00 Uhr – Problem behoben.

Beim Versuch, die Microsoft Store und Apps auf HoloLens zu starten, treten möglicherweise Probleme auf. Wir haben festgestellt, dass das Problem auftritt, wenn Hintergrund-App-Updates eine neuere Version von Frameworkpaketen in bestimmten Sequenzen bereitstellen, während eine oder mehrere abhängige Apps noch ausgeführt werden. In diesem Fall hat ein automatisches App-Update eine neue Version des .NET Native Frameworks (Version 10.0.25531 bis 10.0.27413) bereitgestellt, sodass die ausgeführten Apps für alle ausgeführten Apps, die die vorherige Version des Frameworks nutzen, nicht ordnungsgemäß aktualisiert wurden.  Der Ablauf für das Frameworkupdate sieht wie folgt aus:

1. Das neue Frameworkpaket wird aus dem Store heruntergeladen und installiert.

1. Alle Apps, die das ältere Framework verwenden, werden aktualisiert, um die neuere Version zu verwenden.

Wenn Schritt 2 vor Abschluss unterbrochen wird, können alle Apps, für die das neuere Framework nicht registriert wurde, nicht über das Startmenü gestartet werden.  Wir sind der Meinung, dass jede App auf HoloLens von diesem Problem betroffen sein könnte.

Einige Benutzer haben gemeldet, dass das Schließen von hängenden Apps und das Starten anderer Apps, z. B. Feedback-Hub, 3D-Viewer oder Fotos das Problem für sie löst. Dies funktioniert jedoch nicht zu 100 % der Zeit.

Wir haben grundverursachet, dass dieses Problem nicht das Update selbst verursacht hat, sondern ein Fehler im Betriebssystem, der dazu führte, dass das .NET Native Frameworkupdate falsch behandelt wurde. Wir freuen uns, bekanntgeben zu können, dass wir eine Korrektur identifiziert und ein Update (Betriebssystemversion 17763.380) veröffentlicht haben, das die Fehlerbehebung enthält.  

So prüfen Sie, ob Ihr Gerät das Update durchführen kann:

1. Wechseln Sie zur Einstellungen-App, und öffnen **Sie Update & Security**.

1. Wählen Sie **Nach Updates suchen** aus.

1. Wenn ein Update auf 17763.380 verfügbar ist, aktualisieren Sie auf diesen Build, um die Korrektur für den App Hang-Fehler zu erhalten.

1. Nach dem Aktualisieren auf diese Version des Betriebssystems sollten die Apps wie erwartet funktionieren.

Darüber hinaus haben wir wie bei jeder HoloLens Betriebssystemversion das FFU-Image im [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380)veröffentlicht.

Wenn Sie das Update nicht durchführen möchten, haben wir ab dem 29. Mai eine neue Version der Microsoft Store UWP-App veröffentlicht. Nachdem Sie die aktualisierte Version des Store:

1. Öffnen Sie die Store, und vergewissern Sie sich, dass sie geladen wird.
1. Verwenden Sie die Geste "Bloom", um das Menü zu öffnen.
1. Versuchen Sie, zuvor fehlerhafte Apps zu öffnen.
1. Wenn sie immer noch nicht gestartet werden kann, tippen Sie auf das Symbol der fehlerhaften App, halten Sie sie fest, und wählen Sie Deinstallieren aus.
1. Installieren Sie diese Apps aus dem Store neu.

Wenn Ihr Gerät weiterhin keine Apps laden kann, können Sie eine Version des .NET Native Frameworks und der Runtime über das Download Center querladen, indem Sie die folgenden Schritte ausführen:

1. Laden Sie [diese ZIP-Datei](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) aus dem Microsoft Download Center herunter. Beim Entpacken werden zwei Dateien erzeugt.  Microsoft .NET.Native.Runtime.1.7.appx und Microsoft .NET.Native.Framework.1.7.appx.

1. Vergewissern Sie sich, dass Ihr Gerät vom Entwickler entsperrt ist.  Wenn Sie dies noch nicht getan haben, finden Sie anweisungen unter [Verwenden des Windows Geräteportal.](/windows/mixed-reality/using-the-windows-device-portal)

1. Sie möchten dann in den Windows Geräteportal gelangen. Es wird empfohlen, dies über USB zu tun, und Sie würden dies tun, indem Sie http://127.0.0.1:10080 in Ihren Browser eingeben.

1. Nachdem Sie die Windows Geräteportal haben, müssen Sie die beiden heruntergeladenen Dateien "querladen". Dazu müssen Sie die linke Seitenleiste nach unten wechseln, bis Sie zum Abschnitt **Apps** gelangen und **Apps** auswählen.

1. Daraufhin wird ein Bildschirm angezeigt, der dem folgenden ähnelt.  Sie möchten zum Abschnitt **App installieren** navigieren und zu dem Punkt navigieren, an dem Sie diese beiden APPX-Dateien entpackt haben. Sie können jeweils nur einen auswählen. Klicken Sie also nach dem Auswählen des ersten Eintrags im Abschnitt Bereitstellen auf "Los". Gehen Sie dann für die zweite APPX-Datei vor.

   ![Windows Geräteportal zum Installieren der Side-Loaded-App](images/20190322-DevicePortal.png)

1. An diesem Punkt sind wir der Meinung, dass Ihre Anwendungen wieder funktionieren sollten und sie auch zum Store gelangen können.

1. In einigen Fällen ist es erforderlich, den zusätzlichen Schritt zum Starten der 3D-Viewer-App auszuführen, bevor die betroffenen Apps gestartet werden.

Wir freuen uns über Ihre Geduld, da wir den Prozess durchlaufen haben, um dieses Problem zu lösen, und wir freuen uns darauf, weiterhin mit unserer Community zusammenzuarbeiten, um erfolgreiche Mixed Reality zu schaffen.

### <a name="device-update"></a>Geräteupdate

- 30 Sekunden nach einem neuen Update wird die Shell möglicherweise einmal ausgeblendet. Führen Sie die **Geste "Bloom"** aus, um Ihre Sitzung fortzusetzen.

### <a name="visual-studio"></a>Visual Studio

- Informationen zur aktuellen Version von Visual Studio, die für die entwicklung HoloLens empfohlen wird, finden Sie unter Installieren der [Tools.](/windows/mixed-reality/install-the-tools)

- Beim Bereitstellen einer App aus Visual Studio in Ihrem HoloLens wird möglicherweise der Folgende angezeigt: **Der angeforderte Vorgang kann nicht für eine Datei ausgeführt werden, in der ein benutzerzuordnungsbasierter Abschnitt geöffnet ist. (Ausnahme von HRESULT: 0x800704C8)**. Versuchen Sie es in diesem Fall erneut, und Ihre Bereitstellung ist in der Regel erfolgreich.

### <a name="api"></a>API

- Wenn die Anwendung den [Fokuspunkt](/windows/mixed-reality/focus-point-in-unity) hinter dem Benutzer oder die normale auf camera.forward festlegt, werden Hologramme nicht in Mixed Reality-Aufnahme Fotos oder Videos angezeigt. Bis dieser Fehler in Windows behoben ist, sollten Anwendungen, die den [Fokuspunkt](/windows/mixed-reality/focus-point-in-unity) aktiv festlegen, sicherstellen, dass die Normalität der Ebene gegenüber der Kamera nach vorn festgelegt wird (z. B. normal = -camera.forward).

### <a name="xbox-wireless-controller"></a>Xbox Wireless Controller

- Xbox Wireless Controller S muss aktualisiert werden, bevor er mit HoloLens verwendet werden kann. Stellen Sie [sicher,](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) dass Sie auf dem neuesten Stand sind, bevor Sie versuchen, Ihren Controller mit einem HoloLens zu koppeln.

- Wenn Sie Ihre HoloLens neu starten, während der Xbox Wireless Controller verbunden ist, stellt der Controller nicht automatisch erneut eine Verbindung mit HoloLens her. Die Schaltfläche "Leitfaden" blinkt langsam, bis der Controller nach 3 Minuten ausgeschaltet wird. Um den Controller sofort wieder zu verbinden, schalten Sie den Controller aus, indem Sie die Schaltfläche Leitfaden gedrückt halten, bis das Licht ausgeschaltet wird. Wenn Sie den Controller wieder einschalten, wird die Verbindung mit HoloLens wiederhergestellt.

- Wenn Ihre HoloLens in den Standbymodus wechselt, während der Xbox Wireless Controller verbunden ist, aktiviert jede Eingabe auf dem Controller die HoloLens. Sie können dies verhindern, indem Sie Ihren Controller ausschalten, wenn Sie ihn nicht mehr verwenden.

