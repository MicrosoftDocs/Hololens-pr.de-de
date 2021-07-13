---
title: Bekannte Probleme bei HoloLens (1. Generation)
description: Halten Sie sich mit unserer Liste bekannter Probleme und Problemumgehungen auf dem laufenden, die sich auf HoloLens Kunden und Entwickler auswirken können, die Unity und die Windows Geräteportal.
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
ms.openlocfilehash: 36991d62da91011b807dfb9ff52ab16eadac8bc7
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640303"
---
# <a name="known-issues-for-hololens-1st-gen"></a>Bekannte Probleme bei HoloLens (1. Generation)

Hier ist die aktuelle Liste der bekannten Probleme für HoloLens Geräte. Überprüfen Sie hier zuerst, ob ein ungerades Verhalten vor sich geht. Diese Liste wird aktualisiert, wenn neue Probleme entdeckt oder gemeldet werden, oder wenn Probleme in zukünftigen HoloLens behoben werden.

>[!NOTE]
> - Wenn Sie ein Problem feststellen, das Sie nicht blockiert, melden Sie es auf Ihrem HoloLens-Gerät über [Feedback-Hub](hololens-feedback.md).
> - Wenn sie durch das Problem blockiert werden, stellen Sie zusätzlich zum Einreichen von Feedback [eine Supportanfrage.](https://aka.ms/hlsupport)


- [Bekannte Probleme für alle HoloLens Generation](#known-issues-for-all-hololens-generations)
- [Bekannte Probleme bei HoloLens (1. Generation)](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>Bekannte Probleme für alle HoloLens Generation

### <a name="unity"></a>Unity

- Unter [Installieren der Tools](/windows/mixed-reality/install-the-tools) finden Sie die neueste Version von Unity, die für die entwicklung HoloLens wird.
- Bekannte Probleme mit der Unity HoloLens Technical Preview sind in den [Unity-Foren](https://forum.unity3d.com/threads/known-issues.394627/)HoloLens dokumentiert.

### <a name="windows-device-portal"></a>Windows-Geräteportal

- Die Livevorschaufunktion in Mixed Reality Erfassung kann einige Sekunden Latenz zeigen.

- Auf der Seite Virtuelle Eingabe sind die Steuerelemente Geste und Bildlauf im Abschnitt Virtuelle Gesten nicht funktionsfähig. Ihre Verwendung hat keine Auswirkungen. Die virtuelle Tastatur auf der virtuellen Eingabeseite funktioniert ordnungsgemäß.

- Nach dem Aktivieren des Entwicklermodus in Einstellungen kann es einige Sekunden dauern, bis der Schalter aktiviert Geräteportal ist.

### <a name="onedrive-camera-upload"></a>OneDrive der Kamera

Die OneDrive-App für HoloLens unterstützt keinen automatischen Kameraupload für Arbeits- oder Schulkonten.

Problemumgehungen:

- Wenn dies für Ihr Unternehmen sinnvoll ist, wird der automatische Kameraupload für Microsoft-Kundenkonten unterstützt. Sie können sich bei Ihrem Microsoft-Konto zusätzlich zu Ihrem Arbeits-, Schul- oder Schulkonto anmelden (die OneDrive-App unterstützt die duale Anmeldung). In Ihrem Microsoft-Konto profil in OneDrive können Sie den automatischen Rollup der Hintergrundkamera aktivieren.

- Wenn Sie einen Consumer-Microsoft-Konto zum automatischen Hochladen Ihrer Fotos nicht sicher verwenden können, können Sie Fotos manuell aus der App in Ihr Arbeits- oder Schulkonto OneDrive hochladen. Stellen Sie dazu sicher, dass Sie bei Ihrem Arbeits- oder Schulkonto in der OneDrive sind. Wählen Sie die **+** Schaltfläche und dann **Hochladen.** Suchen Sie die Fotos oder Videos, die Sie hochladen möchten, indem Sie zu Bilder > **Camera Roll navigieren.** Wählen Sie die Fotos oder Videos aus, die Sie hochladen möchten, und klicken Sie dann auf **die Schaltfläche** Öffnen.

## <a name="known-issues-for-hololens-1st-gen"></a>Bekannte Probleme bei HoloLens (1. Generation)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Es kann keine Verbindung hergestellt und keine Bereitstellung für HoloLens über Visual Studio

> [!NOTE]
> Letztes Update: 8.08.um 17:11 Uhr– Visual Studio hat VS 2019 Version 16.2 veröffentlicht, was eine Lösung für dieses Problem enthält. Es wird empfohlen, auf diese neueste Version zu aktualisieren, um diesen Fehler zu vermeiden.

Visual Studio Version 16.2 von VS 2019 veröffentlicht, die eine Lösung für dieses Problem enthält. Es wird empfohlen, auf diese neueste Version zu aktualisieren, um diesen Fehler zu vermeiden.

Grundursache des Problems: Benutzer, die Visual Studio 2015 oder frühe Releases von Visual Studio 2017 zum Bereitstellen und Debuggen von Anwendungen in ihrer HoloLens verwendet haben und anschließend die neuesten Versionen von Visual Studio 2017 oder Visual Studio 2019 mit demselben HoloLens verwendet haben, sind betroffen. Die neueren Releases von Visual Studio stellen eine neue Version einer Komponente zur Bereitstellung, aber Dateien der älteren Version bleiben auf dem Gerät übrig, was dazu führt, dass die neuere Version fehlschlägt.  Dies verursacht die folgende Fehlermeldung: DEP0100: Stellen Sie sicher, dass für das Zielgerät der Entwicklermodus aktiviert ist. Eine Entwicklerlizenz für konnte aufgrund des \<ip\> Fehlers 80004005 nicht erworben werden.

#### <a name="workaround"></a>Problemumgehung

Unser Team arbeitet derzeit an einer Lösung. In der Zwischenzeit können Sie die folgenden Schritte ausführen, um das Problem zu beheben und die Blockierung von Bereitstellung und Debuggen zu beheben:  

1. Öffnen Sie Visual Studio.

1. Klicken Sie auf **Datei** > **Neu** > **Projekt**.

1. Wählen **Sie Visual C#**  >  **Windows Desktop** Console App  >  **(.NET Framework) aus.**

1. Geben Sie dem Projekt einen Namen (z. B. "HoloLensDeploymentFix"), und stellen Sie sicher, dass das Framework mindestens auf .NET Framework 4.5 festgelegt ist, und klicken Sie dann **auf OK.**

1. Klicken Sie mit der **rechten** Maustaste auf den Knoten Verweise in  Projektmappen-Explorer und fügen Sie die folgenden Verweise hinzu (wählen Sie den Abschnitt Durchsuchen aus, und wählen Sie **Durchsuchen aus):**

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Wenn 10.0.18362.0 nicht installiert ist, verwenden Sie die neueste Version, die Sie haben.

1. Klicken Sie mit der rechten Maustaste auf das Projekt in Projektmappen-Explorer und wählen **Sie**  >  **Vorhandenes Element hinzufügen aus.**

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

1. Öffnen Sie ein Eingabeaufforderungsfenster, und öffnen Sie cd in den Ordner, der die kompilierte .exe-Datei enthält (z.B. C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Führen Sie die ausführbare Datei aus, und geben Sie die IP-Adresse des Geräts als Befehlszeilenargument an. (Wenn eine Verbindung über USB besteht, können Sie 127.0.0.1 verwenden. Verwenden Sie andernfalls die Wi-Fi IP-Adresse des Geräts.)  Beispiel: "HoloLensDeploymentFix 127.0.0.1".

1. Nachdem das Tool ohne Nachrichten beendet wurde (dies sollte nur einige Sekunden dauern), können Sie ab Visual Studio 2017 oder neuer bereitstellen und debuggen.  Die weitere Verwendung des Tools ist nicht erforderlich.

Wir werden weitere Updates bereitstellen, sobald sie verfügbar sind.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Probleme beim Starten Microsoft Store Apps auf HoloLens

> [!NOTE]
> Letztes Update: 4/2 @ 10 AM – Problem behoben.

Beim Versuch, die App und die Apps auf dem Microsoft Store zu starten, können Probleme HoloLens. Wir haben festgestellt, dass das Problem auftritt, wenn Hintergrund-App-Updates eine neuere Version von Frameworkpaketen in bestimmten Sequenzen bereitstellen, während eine oder mehrere ihrer abhängigen Apps noch ausgeführt werden. In diesem Fall hat ein automatisches App-Update eine neue Version von .NET Native Framework bereitgestellt (Version 10.0.25531 bis 10.0.27413), was dazu führte, dass die ausgeführten Apps nicht ordnungsgemäß für alle ausgeführten Apps aktualisiert wurden, die die vorherige Version des Frameworks verwenden.  Der Ablauf für das Frameworkupdate lautet wie folgt:

1. Das neue Frameworkpaket wird aus dem Store heruntergeladen und installiert.

1. Alle Apps älteren Frameworks werden aktualisiert, um die neuere Version zu verwenden.

Wenn Schritt 2 vor dem Abschluss unterbrochen wird, können alle Apps, für die das neuere Framework nicht registriert wurde, nicht über das Startmenü gestartet werden.  Wir sind der Meinung, dass HoloLens app on HoloLens von diesem Problem betroffen sein könnte.

Einige Benutzer haben gemeldet, dass das Schließen von hängenden Apps und das Starten anderer Apps wie Feedback-Hub, 3D-Viewer oder Fotos das Problem für sie behebt. Dies funktioniert jedoch nicht in 100 % der Fälle.

Wir haben die Ursache dafür, dass dieses Problem nicht durch das Update selbst verursacht wurde, sondern durch einen Fehler im Betriebssystem, der dazu führte, dass das .NET Native Framework-Update falsch behandelt wurde. Wir freuen uns bekanntgeben zu können, dass wir eine Korrektur ermittelt und ein Update (Betriebssystemversion 17763.380) veröffentlicht haben, das den Fix enthält.  

So sehen Sie, ob Ihr Gerät das Update übernehmen kann:

1. Wechseln Sie zur Einstellungen-App, und öffnen Sie **Update & Security**.

1. Wählen Sie **Nach Updates suchen aus.**

1. Wenn ein Update auf 17763.380 verfügbar ist, aktualisieren Sie auf diesen Build, um die Behebung des Fehlers "App Hängt" zu erhalten.

1. Nach dem Aktualisieren auf diese Version des Betriebssystems sollten die Apps wie erwartet funktionieren.

Darüber hinaus haben wir wie bei jedem HoloLens Betriebssystemversion das FFU-Image im [Microsoft Download Center veröffentlicht.](https://aka.ms/hololensdownload/10.0.17763.380)

Wenn Sie das Update nicht verwenden möchten, haben wir eine neue Version der Microsoft Store UWP-App ab dem 29. Januar veröffentlicht. Nachdem Sie die aktualisierte Version des -Store:

1. Öffnen Sie die Store, und vergewissern Sie sich, dass sie geladen wird.
1. Verwenden Sie die Leiste , um das Menü zu öffnen.
1. Versuchen Sie, zuvor fehlerhafte Apps zu öffnen.
1. Wenn es immer noch nicht gestartet werden kann, tippen Sie auf das Symbol der fehlerhaften App, halten Sie es bei, und wählen Sie Deinstallieren aus.
1. Installieren Sie diese Apps erneut aus dem Store.

Wenn Ihr Gerät weiterhin keine Apps laden kann, können Sie eine Version von .NET Native Framework und Runtime über das Download Center per Sideload laden, indem Sie die folgenden Schritte ausführen:

1. Laden Sie [diese ZIP-Datei aus](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) dem Microsoft Download Center herunter. Beim Entpacken werden zwei Dateien erzeugt.  Microsoft .NET.Native.Runtime.1.7.appx und Microsoft .NET.Native.Framework.1.7.appx.

1. Vergewissern Sie sich, dass Ihr Gerät entsperrt ist.  Wenn Sie dies noch nicht getan haben, finden Sie unter [Verwenden der](/windows/mixed-reality/using-the-windows-device-portal) Windows Geräteportal Anweisungen.

1. Anschließend möchten Sie in die Windows Geräteportal. Es wird empfohlen, dies über USB zu tun. Geben Sie dazu in Ihren http://127.0.0.1:10080 Browser ein.

1. Nachdem Sie die Windows Geräteportal haben, müssen Sie die beiden heruntergeladenen Dateien "side load" laden. Dazu müssen Sie die linke Seitenleiste nach unten wechseln, bis Sie zum Abschnitt **Apps** wechseln und **Apps auswählen.**

1. Dann wird ein Bildschirm angezeigt, der dem folgenden ähnelt.  Sie möchten zum Abschnitt App  installieren wechseln und dort navigieren, wo Sie diese beiden APPX-Dateien entpackt haben. Sie können immer nur einen Schritt nach dem anderen tun. Klicken Sie daher nach dem Auswählen des ersten Schritts im Abschnitt Bereitstellen auf "Los". Gehen Sie dann für die zweite APPX-Datei vor.

   ![Windows Geräteportal zum Installieren der Side-Loaded-App](images/20190322-DevicePortal.png)

1. An diesem Punkt sind wir der Meinung, dass Ihre Anwendungen wieder funktionieren sollten, und dass Sie auch zum Store.

1. In einigen Fällen ist es erforderlich, den zusätzlichen Schritt zum Starten der App 3D-Viewer, bevor die betroffenen Apps gestartet werden.

Wir freuen uns über Ihre Geduld, da wir den Prozess zur Lösung dieses Problems durchgegangen sind, und freuen uns auf die weitere Zusammenarbeit mit unserer Community, um erfolgreiche Mixed Reality zu schaffen.

### <a name="device-update"></a>Geräteupdate

- 30 Sekunden nach einem neuen Update verschwindet die Shell möglicherweise einmal. Führen Sie die **Blumengeste** aus, um Ihre Sitzung wieder aufzunehmen.

### <a name="visual-studio"></a>Visual Studio

- Unter [Installieren der Tools](/windows/mixed-reality/install-the-tools) finden Sie die aktuelle Version von Visual Studio, die für die entwicklung HoloLens wird.

- Beim Bereitstellen einer App aus Visual Studio in Ihrer HoloLens wird möglicherweise der Folgende angezeigt: Der angeforderte Vorgang kann nicht für eine Datei ausgeführt werden, in der ein vom Benutzer zugeordneter **Abschnitt geöffnet ist. (Ausnahme von HRESULT: 0x800704C8)**. Versuchen Sie es in diesem Fall erneut, und Ihre Bereitstellung ist im Allgemeinen erfolgreich.

### <a name="api"></a>API

- Wenn die Anwendung den [Fokuspunkt](/windows/mixed-reality/focus-point-in-unity) hinter dem Benutzer oder die normale auf camera.forward legt, werden Hologramme nicht in Mixed Reality-Aufnahme Videos angezeigt. Bis dieser Fehler in Windows behoben wurde, sollten [](/windows/mixed-reality/focus-point-in-unity) Anwendungen, wenn sie aktiv den Fokuspunkt festlegen, sicherstellen, dass die Normale der Ebene gegenüber der Kamera (z. B. normal = -camera.forward) festgelegt ist.

### <a name="xbox-wireless-controller"></a>Xbox Wireless Controller

- Xbox Wireless Controller S muss aktualisiert werden, bevor es mit der HoloLens. Stellen Sie [sicher, dass Sie auf dem neuesten](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) Stand sind, bevor Sie versuchen, Ihren Controller mit einem HoloLens.

- Wenn Sie Ihren HoloLens starten, während der Xbox Wireless Controller verbunden ist, stellt der Controller nicht automatisch erneut eine Verbindung mit dem HoloLens. Das Guide-Schaltflächenlicht blinkt langsam, bis der Controller nach 3 Minuten ausgeschaltet wird. Um den Controller sofort wieder zu verbinden, schließen Sie den Controller aus, indem Sie die Taste Guide gedrückt halten, bis das Licht ausgeschaltet wird. Wenn Sie den Controller wieder ein-/aus-/wieder ein-/aus-HoloLens.

- Wenn Ihr HoloLens in den Standbymodus versetzt wird, während der Xbox Wireless Controller verbunden ist, werden alle Eingaben auf dem Controller die HoloLens. Sie können dies verhindern, indem Sie Ihren Controller ausschalten, wenn Sie ihn nicht mehr verwenden.

