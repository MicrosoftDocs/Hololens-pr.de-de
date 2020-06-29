---
title: Bekannte Probleme bei HoloLens
description: Dies ist die Liste bekannter Probleme, die sich auf HoloLens-Entwickler auswirken können.
keywords: Problembehandlung, bekannte Probleme, Hilfe
author: mattzmsft
ms.author: mazeller
ms.date: 4/20/2020
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
ms.openlocfilehash: 330a7fd549a2b847f77715ca90d69f1d4df1fb1d
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828427"
---
# Bekannte Probleme bei HoloLens

Dies ist die aktuelle Liste bekannter Probleme für HoloLens-Geräte. Überprüfen Sie hier zuerst, ob ein unregelmäßiges Verhalten angezeigt wird. Diese Liste wird aktualisiert, wenn neue Probleme erkannt oder gemeldet werden oder Probleme in zukünftigen HoloLens-Softwareupdates behoben werden.

>[!NOTE]
> - Wenn Sie ein Problem entdecken, das Sie nicht blockiert, melden Sie es bitte über das [Feedback-Hub](hololens-feedback.md)auf Ihrem HoloLens-Gerät.
> - Wenn Ihnen das Problem, mit dem Sie konfrontiert sind, blockiert, senden Sie bitte [eine Support-Anfrage](https://aka.ms/hlsupport).

- [Bekannte Probleme für alle HoloLens-Generationen](#known-issues-for-all-hololens-generations)
- [Bekannte Probleme bei HoloLens 2-Geräten](#known-issues-for-hololens-2-devices)
- [Bekannte Probleme bei HoloLens (1st Generation)](#known-issues-for-hololens-1st-gen)
- [Bekannte Probleme beim HoloLens-Emulator](#known-issues-for-hololens-emulator)

## Bekannte Probleme für alle HoloLens-Generationen

### Unity

- Weitere Informationen finden Sie unter [Installieren der Tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) für die neueste Version von Unity, die für die HoloLens-Entwicklung empfohlen wird.
- Bekannte Probleme mit der technischen Vorschau von Unity HoloLens sind in den [HoloLens Unity-Foren](https://forum.unity3d.com/threads/known-issues.394627/)dokumentiert.

### Windows Geräteportal

- Das Feature für die Live Vorschau in Mixed-Reality-Aufnahmen kann mehrere Sekunden Wartezeit aufweisen.
- Auf der virtuellen Eingabeseite sind die Steuerelemente für Gesten und Scrollen unter dem Abschnitt virtuelle Gesten nicht funktionsfähig. Die Verwendung hat keine Auswirkungen. Die virtuelle Tastatur auf derselben Seite funktioniert ordnungsgemäß.
- Nach dem Aktivieren des Entwicklermodus in Einstellungen kann es einige Sekunden dauern, bis der Wechsel zum Aktivieren des Geräte Portals aktiviert ist.

## Bekannte Probleme bei HoloLens 2-Geräten

### Der blaue Bildschirm wird angezeigt, nachdem die Registrierung von Insider Preview-Builds auf einem Gerät mit einem Insider-Build nicht mehr registriert wurde.

Hierbei handelt es sich um ein Problem, das Auswirkungen auf Benutzer hat, die sich auf einem Insider Preview-Build befanden, ihre HoloLens 2 mit einem neuen Insider Preview-Build erneut aufblitzten und dann aus dem Insider-Programm entfernt wurden. 

Dies hat keine Auswirkungen auf:
- Benutzer, die nicht für Windows Insider registriert sind 
- Insider
    - Wenn ein Gerät registriert wurde, da Insider-Builds Version 18362. x waren
    - Wenn Sie einen Insider-signierten 19041. x-Build aufblitzten und im Insider-Programm registriert bleiben 

Umgehen: 
- Vermeiden des Problems 
    - Flashen Sie einen nicht Insider-Build. Eine der regelmäßigen monatlichen Updates. 
    - Bleiben Sie auf Insider Preview
- Erneutes Blinken des Geräts
    1. Setzen Sie das [HoloLens 2 manuell in den Blinkmodus](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) , indem Sie das Gerät vollständig Herunterfahren, während Sie keine Verbindung herstellen. Tippen Sie dann bei gedrückter Lautstärke auf die Power-Taste.
    1. Stellen Sie eine Verbindung mit dem PC her, und öffnen Sie Advanced Recovery Companion. 
    1. Blinken Sie das HoloLens 2 auf den Standard-Build.   

## Bekannte Probleme bei HoloLens (1st Generation)

### Über Visual Studio kann keine Verbindung zu HoloLens hergestellt und bereitgestellt werden

> [!NOTE]
> Letzte Aktualisierung: 8/8 @ 5:11Pm – Visual Studio hat vs 2019 Version 16,2 veröffentlicht, die eine Lösung für dieses Problem enthält. Wir empfehlen, diese neueste Version zu aktualisieren, um zu vermeiden, dass dieser Fehler auftritt.

Visual Studio hat vs 2019 Version 16,2 veröffentlicht, die eine Lösung für dieses Problem enthält. Wir empfehlen, diese neueste Version zu aktualisieren, um zu vermeiden, dass dieser Fehler auftritt.

Ursache: Benutzer, die Visual Studio 2015 oder frühe Versionen von Visual Studio 2017 zum Bereitstellen und Debuggen von Anwendungen auf Ihren HoloLens verwendet und anschließend die neuesten Versionen von Visual Studio 2017 oder Visual Studio 2019 mit demselben HoloLens verwendet haben, sind davon betroffen. Die neueren Versionen von Visual Studio stellen eine neue Version einer Komponente bereit, aber Dateien aus der älteren Version sind auf dem Gerät übrig, wodurch die neuere Version fehlschlägt.  Dies führt zu der folgenden Fehlermeldung: DEP0100: Stellen Sie sicher, dass das Zielgerät den Entwicklermodus aktiviert hat. Auf Grund des Fehlers 80004005 konnte keine Entwicklerlizenz abgerufen \<ip\> werden.

#### Problemumgehung

Unser Team arbeitet derzeit an einer Lösung. In der Zwischenzeit können Sie die folgenden Schritte ausführen, um das Problem zu umgehen und die Blockierung der Bereitstellung und des Debuggens zu unterstützen:  

1. Öffnen von Visual Studio
1. Wählen Sie **Datei**  >  **Neues**  >  **Projekt**aus.
1. Wählen Sie **Visual C#**  >  **Windows Desktop**  >  **Console-app (.NET Framework)** aus.
1. Geben Sie dem Projekt einen Namen (beispielsweise "HoloLensDeploymentFix"), und stellen Sie sicher, dass das Framework auf mindestens .NET Framework 4,5 eingestellt ist, und wählen Sie dann **OK**aus.
1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Knoten **Verweise** , und fügen Sie die folgenden Verweise hinzu (Wählen Sie den Abschnitt **Durchsuchen** und dann **Durchsuchen**aus):

    ```CMD
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Wenn Sie 10.0.18362.0 nicht installiert haben, verwenden Sie die neueste Version. 

1. Klicken Sie im Projektmappen-Explorer mit der rechten **Add**Maustaste auf das Projekt, und wählen Sie  >  **Vorhandenes Element**hinzufügen aus.
1. Navigieren Sie zu "C:\Program Files (x86)"-Kits\10\bin\10.0.18362.0\x86, und ändern Sie den Filter in **alle Dateien (\ *. \ *)**.
1. Wählen Sie SirepClient.dll und SshClient.dll aus, und wählen Sie dann **Hinzufügen**aus.
1. Suchen Sie im Projektmappen-Explorer nach beiden Dateien, und wählen Sie Sie aus (Sie sollten sich unten in der Liste der Dateien befinden), und wechseln Sie im **Eigenschaften** Fenster in **Ausgabeverzeichnis kopieren** , um **immer zu kopieren**.
1. Fügen Sie oben in der Datei die folgende Liste der vorhandenen `using` Anweisungen hinzu:

    ```CMD
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. `static void Main(...)`Fügen Sie innerhalb von den folgenden Code hinzu:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Wählen **Build**Sie  >  **Projektmappe**erstellen aus.
1. Öffnen Sie ein Eingabeaufforderungsfenster und eine CD in dem Ordner, in dem sich die kompilierte EXE-Datei befindet (beispielsweise C:\MyProjects\HoloLensDeploymentFix\bin\Debug).
1. Führen Sie die ausführbare Datei aus, und geben Sie die IP-Adresse des Geräts als Befehlszeilenargument an. (Wenn Sie über USB verbunden sind, können Sie 127.0.0.1 verwenden, andernfalls verwenden Sie die WLAN-IP-Adresse des Geräts.)  Beispiel: "HoloLensDeploymentFix 127.0.0.1"

1. Nachdem das Tool ohne Nachrichten beendet wurde (Dies sollte nur ein paar Sekunden dauern), können Sie jetzt in Visual Studio 2017 oder höher bereitstellen und Debuggen.  Eine fortgesetzte Nutzung des Tools ist nicht erforderlich.

Wir werden weitere Updates zur Verfügung stellen, sobald diese verfügbar sind.

### Probleme beim Starten von Microsoft Store und Apps auf HoloLens

> [!NOTE]
> Letzte Aktualisierung: 4/2 @ 10.00-Problem behoben. 

Bei dem Versuch, den Microsoft Store und die apps auf HoloLens zu starten, können Probleme auftreten. Wir haben festgestellt, dass das Problem auftritt, wenn Hintergrund-APP-Updates eine neuere Version der Framework-Pakete in bestimmten Sequenzen bereitstellen, während eine oder mehrere der abhängigen apps noch ausgeführt werden. In diesem Fall hat ein automatisches App-Update eine neue Version von .net Native Framework (Version 10.0.25531 to 10.0.27413) geliefert, die dazu führte, dass die ausgeführten Apps für alle ausgeführten apps, die die vorherige Version des Frameworks verwenden, nicht ordnungsgemäß aktualisiert wurden.  Der Fluss für das Framework-Update lautet wie folgt: 

1. Das neue Framework-Paket wird aus dem Store heruntergeladen und installiert.
1. Alle apps, die das ältere Framework verwenden, werden "aktualisiert", um die neuere Version zu verwenden.

Wenn Schritt 2 vor Abschluss unterbrochen wird, können alle apps, für die das neuere Framework nicht registriert wurde, nicht über das Startmenü gestartet werden.  Wir sind der Meinung, dass jede APP auf HoloLens von diesem Problem betroffen sein könnte.

Einige Benutzer haben gemeldet, dass das Schließen von hängenden apps und das Starten anderer apps wie Feedback-Hub, 3D-Viewer oder Fotos das Problem für Sie behebt &mdash; , dies funktioniert jedoch nicht 100% der Zeit.

Wir haben root verursacht, dass dieses Problem nicht das Update selbst verursacht hat, sondern ein Fehler im Betriebssystem, der dazu führte, dass das .net Native Framework-Update falsch gehandhabt wurde. Wir freuen uns, Ihnen mitzuteilen, dass wir eine Lösung gefunden haben und ein Update (OS Version 17763,380) mit dem Fix veröffentlicht haben.  

Wenn Sie feststellen möchten, ob Ihr Gerät das Update durchführen kann, wenden Sie sich bitte an:

1. Wechseln Sie zur Einstellungs-APP, und öffnen Sie **Update & Security**.
1. Wählen Sie **nach Updates**suchen aus.
1. Wenn Update auf 17763,380 verfügbar ist, aktualisieren Sie auf diesen Build, um den Fix für den App-Hang Fehler zu erhalten.
1. Nach dem Aktualisieren auf diese Version des Betriebssystems sollten die apps wie erwartet funktionieren.

Darüber hinaus haben wir, wie bei jeder HoloLens-Betriebssystemversion, das FFU-Bild im [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380)gepostet.

Wenn Sie das Update nicht durchführen möchten, haben wir eine neue Version der Microsoft Store-UWP-App ab 3/29 veröffentlicht. Nachdem Sie die aktualisierte Version des Stores installiert haben:

1. Öffnen Sie den Store, und bestätigen Sie, dass er geladen wird.
1. Verwenden Sie die Bloom-Geste, um das Menü zu öffnen.
1. Versuchen Sie, zuvor fehlerhafte apps zu öffnen.
1. Wenn Sie immer noch nicht gestartet werden kann, tippen Sie auf das Symbol der fehlerhaften APP, und wählen Sie deinstallieren aus.
1. Resinstall Sie diese apps aus dem Store.

Wenn Ihr Gerät weiterhin keine apps laden kann, können Sie mit den folgenden Schritten eine Version von .net Native Framework und Runtime über das Download Center querladen:

1. Bitte laden Sie [diese ZIP-Datei](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) aus dem Microsoft Download Center herunter. Beim Entzippen werden zwei Dateien erstellt.  Microsoft. net. Native. Runtime. 1.7. AppX und Microsoft. net. Native. Framework. 1.7. AppX
1. Bitte überprüfen Sie, ob Ihr Gerät dev entriegelt ist.  Wenn Sie dies noch nicht getan haben, finden Sie [hier](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)eine Anleitung.
1. Sie möchten dann auf das Windows Device Portal zugreifen. Wir empfehlen Ihnen, dies über USB zu tun, und zwar durch Eingabe http://127.0.0.1:10080 in den Browser.
1. Nachdem Sie das Windows Device Portal eingerichtet haben, müssen Sie die beiden heruntergeladenen Dateien "seitlich laden". Dazu müssen Sie in der linken Leiste nach unten gehen, bis Sie zum Abschnitt " **apps** " gelangen, und wählen Sie **apps**aus.
1. Sie sehen dann einen ähnlichen Bildschirm wie den folgenden.  Sie möchten zu dem Abschnitt mit der Installations- **App** wechseln, und navigieren Sie zu dem Speicherort, an dem Sie die beiden APPX-Dateien entpackt haben. Sie können nur eine zu einem Zeitpunkt ausführen, nachdem Sie das erste ausgewählt haben, und klicken Sie dann im Abschnitt Bereitstellen auf "Gehe zu". Führen Sie dann die folgenden Schritte für die zweite APPX-Datei aus.

   ![Windows-Geräte Portal zum Installieren der Seite-geladenen App](images/20190322-DevicePortal.png)
1. An diesem Punkt sind wir der Meinung, dass Ihre Anwendungen wieder funktionieren sollten und dass Sie auch zum Store gelangen können.
1. In einigen Fällen ist es notwendig, den zusätzlichen Schritt zum Starten der 3D-Viewer-App auszuführen, bevor betroffene apps gestartet werden. 

Wir danken Ihnen für Ihre Geduld, da wir diesen Prozess durchlaufen haben, um dieses Problem zu lösen, und wir freuen uns darauf, weiterhin mit unserer Community zusammenzuarbeiten, um erfolgreiche gemischte Realitäts Erlebnisse zu schaffen.

### Geräteaktualisierung

- 30 Sekunden nach einem neuen Update kann die Shell einmal ausgeblendet werden. Führen Sie die **Bloom** -Geste aus, um die Sitzung fortzusetzen.

### Visual Studio

- Weitere Informationen finden Sie unter [Installieren der Tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) für die neueste Version von Visual Studio, die für die HoloLens-Entwicklung empfohlen wird.
- Wenn Sie eine APP aus Visual Studio auf Ihrem HoloLens bereitstellen, wird möglicherweise die folgende Fehlermeldung angezeigt: **der angeforderte Vorgang kann nicht für eine Datei durchgeführt werden, in der ein Benutzer zugeordneter Abschnitt geöffnet ist. (Ausnahme von HRESULT: 0x800704C8)**. Wenn dies der Fall ist, versuchen Sie es erneut, und die Bereitstellung ist in der Regel erfolgreich.

### API

- Wenn die Anwendung den [Fokuspunkt](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) hinter dem Benutzer oder dem normalen auf Camera festlegt, werden Hologramme nicht in Fotos oder Videos in Mixed-Reality-Aufnahmen angezeigt. Bis dieser Fehler in Windows behoben ist, sollten Anwendungen, die den [Fokuspunkt](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) aktiv festgelegt haben, sicherstellen, dass die Ebene normal auf der gegenüberliegenden Kamera festgelegt wird (beispielsweise normal =-Camera. Forward).

### Xbox-Wireless-Controller

- Xbox Wireless Controller S muss aktualisiert werden, bevor Sie mit HoloLens verwendet werden kann. Stellen Sie sicher, dass Sie auf dem [neuesten Stand](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) sind, bevor Sie versuchen, Ihren Controller mit einem HoloLens zu koppeln.
- Wenn Sie Ihr HoloLens während der Verbindung mit dem Xbox Wireless Controller neu starten, wird der Controller nicht automatisch wieder mit HoloLens verbunden. Die schaltflächenanzeige blinkt langsam, bis der Controller nach 3 Minuten ausgeschaltet wird. Wenn Sie den Controller sofort wieder anschließen möchten, schalten Sie den Controller aus, indem Sie die Führungs Taste gedrückt halten, bis die Leuchte ausgeschaltet wird. Wenn Sie Ihren Controller wieder eingeschaltet haben, wird die Verbindung mit HoloLens wiederhergestellt.
- Wenn Ihr HoloLens in den Standbymodus wechselt, während der Xbox Wireless-Controller verbunden ist, werden alle Eingaben auf dem Controller den HoloLens wieder aktivieren. Sie können dies verhindern, indem Sie den Controller ausschalten, wenn Sie ihn nicht mehr verwenden.

## Bekannte Probleme beim HoloLens-Emulator

- Nicht alle apps im Microsoft Store sind mit dem Emulator kompatibel. Beispielsweise sind junge Conker und Fragmente auf dem Emulator nicht spielbar.
- Sie können die PC-Webcam im Emulator nicht verwenden.
- Das Feature "Live Vorschau" des Windows-Geräte Portals funktioniert nicht mit dem Emulator. Sie können weiterhin Videos und Bilder aus der Mixed-Reality-Realität aufnehmen.
