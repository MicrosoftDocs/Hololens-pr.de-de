---
title: Bekannte Probleme bei HoloLens
description: Halten Sie sich mit unserer Liste bekannter Probleme und Problemumgehungen auf dem Laufenden, die sich auf Kunden und Entwickler von HoloLens auswirken können, die Unity und das Windows Device Portal verwenden.
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284076"
---
# Bekannte Probleme bei HoloLens

Dies ist die aktuelle Liste bekannter Probleme für HoloLens-Geräte. Überprüfen Sie hier zuerst, ob ein ungerades Verhalten vor sich geht. Diese Liste wird aktualisiert, wenn neue Probleme erkannt oder gemeldet werden oder wenn Probleme in zukünftigen HoloLens-Softwareupdates behoben werden.

>[!NOTE]
> - Wenn Sie ein Problem entdecken, das Sie nicht blockiert, melden Sie es bitte auf Ihrem HoloLens-Gerät über [den Feedback-Hub.](hololens-feedback.md)
> - Wenn das Problem, mit dem Sie konfrontiert sind, Sie blockiert, senden Sie zusätzlich zum Senden von Feedback eine [Supportanfrage.](https://aka.ms/hlsupport)

- [Bekannte Probleme für alle HoloLens-Generationen](#known-issues-for-all-hololens-generations)
- [Bekannte Probleme für HoloLens 2-Geräte](#known-issues-for-hololens-2-devices)
- [Bekannte Probleme für HoloLens (1. Generation)](#known-issues-for-hololens-1st-gen)
- [Bekannte Probleme für den HoloLens-Emulator](#known-issues-for-hololens-emulator)

## Bekannte Probleme für alle HoloLens-Generationen

### Unity

- Weitere [Informationen finden Sie unter Installieren der](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) Tools für die neueste Version von Unity, die für die Entwicklung von HoloLens empfohlen wird.
- Bekannte Probleme mit der Unity HoloLens Technical Preview sind in den [HoloLens Unity-Foren dokumentiert.](https://forum.unity3d.com/threads/known-issues.394627/)

### Windows Geräteportal

- Die Livevorschau in Mixed Reality-Aufnahme kann eine Wartezeit von mehreren Sekunden haben.

- Auf der Seite "Virtuelle Eingabe" sind die Gesten- und Bildlaufsteuerelemente im Abschnitt "Virtuelle Gesten" nicht funktionsfähig. Ihre Verwendung hat keine Auswirkung. Die virtuelle Tastatur auf derselben Seite funktioniert ordnungsgemäß.

- Nach dem Aktivieren des Entwicklermodus in den Einstellungen kann es einige Sekunden dauern, bis die Option zum Aktivieren des Geräteportals aktiviert ist.

### Hochladen der #A0

Die #A0 für HoloLens unterstützt keinen automatischen Kameraupload für Arbeits- oder Schulkonten.

Problemumgehungen:

- Wenn dies für Ihr Unternehmen sinnvoll ist, wird der automatische Kameraupload für Consumer-Microsoft-Konten unterstützt. Sie können sich bei Ihrem #A0 zusätzlich zu Ihrem Arbeits- oder Schulkonto anmelden (die #A1 unterstützt die duale Anmeldung). In Ihrem #A0 in OneDrive können Sie den automatischen Upload von Hintergrundkameras aktivieren.

- Wenn Sie nicht sicher ein #A0 verwenden können, um Ihre Fotos automatisch hochzuladen, können Sie Fotos aus der #A1 manuell in Ihr Arbeits- oder Schulkonto hochladen. Stellen Sie dazu sicher, dass Sie in der #A0 bei Ihrem Arbeits- oder Schulkonto angemeldet sind. Wählen Sie die **+** Schaltfläche aus, und wählen Sie **"Hochladen" aus.** Suchen Sie die Fotos oder Videos, die Sie hochladen möchten, indem Sie zu "Bilder" **> Camera Roll navigieren.** Wählen Sie die Fotos oder Videos aus, die Sie hochladen möchten, und wählen Sie dann die Schaltfläche **"Öffnen"** aus.

## Bekannte Probleme für HoloLens 2-Geräte

### Microsoft Edge kann nicht gestartet werden

Einige Kunden haben ein Problem gemeldet, bei dem Microsoft Edge nicht gestartet werden kann. Für diese Kunden bleibt das Problem durch einen Neustart bestehen und wird nicht mit Windows- oder Anwendungsupdates behoben. Wenn Dieses Problem auftritt und Sie bestätigt haben, dass [Windows](hololens-updates.md#manually-check-for-updates)auf dem neuesten Stand ist, melden Sie einen Fehler aus der [Feedback-Hub-App](hololens-feedback.md) mit der folgenden Kategorie und Unterkategorie an: Installieren und Aktualisieren > Herunterladen, Installieren und Konfigurieren von Windows Update.

Es gibt keine bekannten Problemumgehungen, da wir das Problem bisher nicht beheben konnten. Das Einreichen eines Fehlers über den #A0 hilft uns bei der Untersuchung!

### Tastatur wechselt nicht zu Sonderzeichen

Während der OOBE liegt ein Problem vor, bei dem, nachdem der Benutzer ein Arbeits-, Schul- oder Schulkonto ausgewählt und sein Kennwort eingegeben hat, versucht wird, zu den Sonderzeichen auf der Tastatur zu wechseln, indem er auf die Schaltfläche &123 klickt, nicht in Sonderzeichen geändert wird. 

Umarbeitungen:
-   Schließen Sie die Tastatur, und öffnen Sie sie erneut, indem Sie auf das Textfeld tippen.
-   Geben Sie Ihr Kennwort falsch ein. Wenn die Tastatur das nächste Mal neu gestartet wird, funktioniert sie wie erwartet.
- Webauthentifizierung, Tastatur schließen und **von einem anderen Gerät aus anmelden auswählen.** 
-   Wenn nur Zahlen eingeben, kann ein Benutzer bestimmte Tasten drücken und halten, um ein erweitertes Menü zu öffnen.
-   Verwenden einer USB-Tastatur.

Dies hat keine Auswirkungen auf:
- Benutzer, die sich für die Verwendung eines persönlichen Kontos entscheiden.

### Blue screen is shown after unenrolling from Insider preview builds on a device reflashed with a Insider build

This is an issue affecting that are on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program. 

Dies hat keine Auswirkungen auf:
- Benutzer, die nicht bei Windows Insider registriert sind 
- Insider:
    - Wenn ein Gerät registriert wurde, seit die Insiderbuilds Version 18362.x waren
    - Wenn sie einen insider signierten 19041.x-Build flashen und für das Insiderprogramm registriert bleiben 

Umarbeitung: 
- Vermeiden des Problems 
    - Flashen eines Nicht-Insider-Build. Eines der regelmäßigen monatlichen Updates. 
    - Bleiben Sie auf Insider Preview
- Schrägstrich für das Gerät

    1. Setzen Sie [HoloLens 2](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manuell in den Blinkmodus, indem Sie das Gerät vollständig herunter schalten, während keine Verbindung hergestellt wird. Tippen Sie dann beim Halten der Lautstärke auf die Ein/Aus-Taste.
    
    1. Stellen Sie eine Verbindung mit dem PC auf, und öffnen Sie Advanced Recovery Companion. 
    
    1. Flashen Sie HoloLens 2 auf den Standard-Build.   

## Bekannte Probleme für HoloLens (1. Generation)

### Es ist nicht möglich, eine Verbindung mit HoloLens herzustellen und über Visual Studio

> [!NOTE]
> Last Update: 8/8 @ 17:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue. Es wird empfohlen, auf diese neueste Version zu aktualisieren, um diesen Fehler zu vermeiden.

Visual Studio hat VS 2019 Version 16.2 veröffentlicht, die eine Behebung dieses Problems enthält. Es wird empfohlen, auf diese neueste Version zu aktualisieren, um diesen Fehler zu vermeiden.

Problemursache: Benutzer, die Visual Studio 2015 oder frühe Versionen von Visual Studio 2017 zum Bereitstellen und Debuggen von Anwendungen auf ihrer HoloLens verwendet haben und anschließend die neuesten Versionen von Visual Studio 2017 oder Visual Studio 2019 mit derselben HoloLens verwendet haben, sind davon betroffen. Die neueren Versionen von Visual Studio eine neue Version einer Komponente bereitstellen, aber Dateien aus der älteren Version werden auf dem Gerät übergehen, was zu einem Fehler bei der neueren Version führt.  Dies verursacht die folgende Fehlermeldung: DEP0100: Stellen Sie sicher, dass für das Zielgerät der Entwicklermodus aktiviert ist. Entwicklerlizenz konnte aufgrund des Fehlers \<ip\> 80004005 nicht erhalten werden.

#### Problemumgehung

Unser Team arbeitet derzeit an einem Fix. In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:  

1. Öffnen Sie Visual Studio.

1. Select **File**  >  **New**  >  **Project**.

1. Wählen **Sie Visual C#**  >  **Windows Desktop**Console App  >  **(.NET Framework) aus.**

1. Geben Sie dem Projekt einen Namen (z. B. "HoloLensDeploymentFix"), und stellen Sie sicher, dass das Framework auf mindestens .NET Framework 4.5 festgelegt ist, und wählen Sie dann **OK aus.**

1. Klicken Sie **** im Projektmappen-Explorer mit der rechten Maustaste auf den Knoten Verweise, und fügen Sie die folgenden Verweise hinzu (wählen Sie den Abschnitt "Durchsuchen" **aus,** und wählen Sie **"Durchsuchen"** aus):

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Wenn Sie 10.0.18362.0 nicht installiert haben, verwenden Sie die neueste Version. 

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen **Sie "Vorhandenes**  >  **Element hinzufügen" aus.**

1. Navigieren Sie zu "C:\Programme (x86)\Windows Kits\10\bin\10.0.18362.0\x86", und ändern Sie den Filter in **"Alle Dateien" (\*.\*).**

1. Wählen Sie sowohl SirepClient.dll als auch SshClient.dll aus, und wählen Sie **"Hinzufügen" aus.**

1. Suchen sie beide Dateien im Projektmappen-Explorer, und wählen Sie **** sie aus (sie **** sollten sich am Ende der Liste der Dateien befinden), und ändern Sie "In Ausgabeverzeichnis kopieren" im Eigenschaftenfenster in "Immer **kopieren".**

1. Fügen Sie am Anfang der Datei der vorhandenen Liste der Anweisungen Folgendes `using` hinzu:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. Fügen Sie `static void Main(...)` in diesem Abschnitt den folgenden Code hinzu:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Wählen Sie **Build Build**  >  **Solution aus.**

1. Öffnen Sie ein Eingabeaufforderungsfenster und eine CD in dem Ordner, der die kompilierte #A0 enthält (z. B. C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Führen Sie die ausführbare Datei aus, und geben Sie die Geräte-IP-Adresse als Befehlszeilenargument an. (Wenn eine Verbindung über USB besteht, können Sie 127.0.0.1 verwenden, andernfalls die Wi-Fi IP-Adresse des Geräts.)  Beispiel: "HoloLensDeploymentFix 127.0.0.1".

1. Nachdem das Tool ohne Meldungen beendet wurde (dies sollte nur einige Sekunden dauern), können Sie ab Visual Studio 2017 oder neuer bereitstellen und debuggen.  Eine weitere Verwendung des Tools ist nicht erforderlich.

Wir werden weitere Updates bereitstellen, sobald sie verfügbar sind.

### Probleme beim Starten des Microsoft Store und von Apps auf HoloLens

> [!NOTE]
> Letztes Update: 02.04. um 10:00 Uhr – Problem behoben. 

Beim Versuch, den Microsoft Store und Apps auf HoloLens zu starten, können Probleme auftreten. Wir haben festgestellt, dass das Problem auftritt, wenn Hintergrund-App-Updates eine neuere Version von Frameworkpaketen in bestimmten Sequenzen bereitstellen, während eine oder mehrere der abhängigen Apps noch ausgeführt werden. In diesem Fall führte ein automatisches App-Update, das eine neue Version von .NET Native Framework (Version 10.0.25531 bis 10.0.27413) lieferte, dazu, dass die ausgeführten Apps für alle ausgeführten Apps, die die vorherige Version des Frameworks verwenden, nicht ordnungsgemäß aktualisiert wurden.  Der Ablauf für das Frameworkupdate lautet wie folgt: 

1. Das neue Frameworkpaket wird aus dem Store heruntergeladen und installiert.

1. Alle Apps, die das ältere Framework verwenden, werden so aktualisiert, dass sie die neuere Version verwenden.

Wenn Schritt 2 vor Abschluss unterbrochen wird, können alle Apps, für die das neuere Framework nicht registriert wurde, nicht über das Startmenü gestartet werden.  Wir glauben, dass alle Apps auf HoloLens von diesem Problem betroffen sein könnten.

Einige Benutzer haben gemeldet, dass das Schließen von nicht mehr reagierten Apps und das Starten anderer Apps wie Feedback-Hub, 3D-Viewer oder Fotos das Problem für sie behebt. Dies funktioniert jedoch &mdash; nicht zu 100 % der Zeit.

Wir haben root caused that this issue was not caused the update itself, but a bug in the os that resulted in the .NET Native framework update being handled incorrectly. Wir freuen uns, Ihnen mitteilen zu können, dass wir einen Fix identifiziert und ein Update (Betriebssystemversion 17763.380) veröffentlicht haben, das den Fix enthält.  

Um zu sehen, ob Ihr Gerät das Update übernehmen kann, gehen Sie wie hier vor:

1. Wechseln Sie zur App "Einstellungen", und öffnen **Sie "Update & Security".**

1. Wählen **Sie "Nach Updates suchen" aus.**

1. Wenn ein Update auf 17763.380 verfügbar ist, aktualisieren Sie dieses Build, um den Fix für den #A0 zu erhalten.

1. Nach dem Aktualisieren auf diese Version des Betriebssystems sollten die Apps wie erwartet funktionieren.

Darüber hinaus haben wir wie bei jeder HoloLens -Betriebssystemversion das FFU-Image im [Microsoft Download Center veröffentlicht.](https://aka.ms/hololensdownload/10.0.17763.380)

Wenn Sie das Update nicht verwenden möchten, haben wir ab 29.03.2013 eine neue Version der Microsoft Store-UWP-App veröffentlicht. Nachdem Sie die aktualisierte Version des Store installiert haben:

1. Öffnen Sie den Store, und bestätigen Sie, dass er geladen wird.
1. Verwenden Sie die Öffnengeste, um das Menü zu öffnen.
1. Versuchen Sie, zuvor beschädigte Apps zu öffnen.
1. Wenn sie weiterhin nicht gestartet werden kann, tippen Sie auf das Symbol der beschädigten App, halten Sie es fest, und wählen Sie "Deinstallieren" aus.
1. Installieren Sie diese Apps erneut aus dem Store.

Wenn Ihr Gerät weiterhin keine Apps laden kann, können Sie eine Version von .NET Native Framework und Runtime über das Download Center querladen, indem Sie die folgenden Schritte ausführen:

1. Laden Sie [diese ZIP-Datei aus](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) dem Microsoft Download Center herunter. Durch das Entfernen des Wiederherstellens werden zwei Dateien erzeugt.  Microsoft.NET.Native.Runtime.1.7.appx und Microsoft.NET.Native.Framework.1.7.appx.

1. Stellen Sie sicher, dass Ihr Gerät entsperrt ist.  Wenn Sie dies noch nicht getan haben, finden Sie unter [Verwenden des Windows Device Portals](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) Anweisungen.

1. Sie möchten dann in das Windows Device Portal zugreifen. Wir empfehlen, dies über USB zu tun, und Sie würden dies tun, indem Sie in http://127.0.0.1:10080 Ihren Browser eingeben.

1. Nachdem Sie das Windows Device Portal eingerichtet haben, müssen Sie die beiden heruntergeladenen Dateien "laden". Dazu müssen Sie die linke Leiste nach unten gehen, bis Sie zum Abschnitt **"Apps"** wechseln und **"Apps" auswählen.**

1. Anschließend wird ein Bildschirm angezeigt, der der folgenden ähnelt.  Wechseln Sie zum Abschnitt "App installieren", und navigieren Sie zu dem Ort, an dem Sie diese beiden APPX-Dateien entzippt haben. **** Sie können immer nur einen Schritt nach dem anderen tun. Klicken Sie also nach dem Auswählen des ersten Schritts im Abschnitt "Bereitstellen" auf "Los". Tun Sie dies dann für die zweite APPX-Datei.

   ![Windows Device Portal zum Installieren Side-Loaded App](images/20190322-DevicePortal.png)
   
1. An diesem Punkt sind wir der Meinung, dass Ihre Anwendungen wieder funktionieren sollten und Sie auch den Store nutzen können.

1. In einigen Fällen muss der zusätzliche Schritt zum Starten der 3D-Viewer-App ausgeführt werden, bevor die betroffenen Apps gestartet werden. 

We appreciate your patience as we have through the process to get this issue resolved, and we look to continued working with our community to create successful Mixed Reality experiences.

### Geräteupdate

- 30 Sekunden nach einem neuen Update wird die Shell möglicherweise einmal ausgeblendet. Führen Sie die **Bloom-Geste** aus, um Ihre Sitzung fort zu setzen.

### Visual Studio

- Weitere [Informationen finden Sie unter "Installieren der](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) Tools für die neueste Version Visual Studio, die für die Entwicklung von HoloLens empfohlen wird.

- Wenn Sie eine App von Visual Studio auf Ihrer HoloLens bereitstellen, wird möglicherweise die Fehlermeldung angezeigt: Der angeforderte Vorgang kann nicht für eine Datei ausgeführt werden, in der ein vom Benutzer zugeordneter Abschnitt geöffnet **ist. (Ausnahme von HRESULT: 0x800704C8)**. Versuchen Sie es in diesem Fall erneut, und die Bereitstellung ist in der Regel erfolgreich.

### API

- Wenn die Anwendung [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) den Fokus hinter dem Benutzer oder den Normalen auf camera.forward legt, werden Hologramme in Mixed Reality Capture Fotos oder Videos nicht angezeigt. Bis dieser Fehler in Windows behoben ist, sollten Anwendungen, die den Fokus aktiv festlegen, sicherstellen, dass die Normale der Ebene gegenüber der Kamera vorwärts festgelegt ist (z. B. normal = -camera.forward). [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity)

### Xbox Wireless Controller

- Xbox Wireless Controller S muss aktualisiert werden, bevor er mit HoloLens verwendet werden kann. Stellen Sie [sicher, dass Sie auf dem neuesten](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) Stand sind, bevor Sie versuchen, Ihren Controller mit einer HoloLens zu koppeln.

- Wenn Sie Ihre HoloLens neu starten, während der Xbox Wireless Controller verbunden ist, wird der Controller nicht automatisch wieder mit HoloLens verbunden. Das Licht der Führungstaste blinkt langsam, bis der Controller nach 3 Minuten ausgeschaltet wird. Um den Controller sofort wieder zu verbinden, schalten Sie den Controller aus, indem Sie die Führungstaste gedrückt halten, bis das Licht ausgeschaltet wird. Wenn Sie den Controller wieder ein netzen, wird er wieder mit HoloLens verbunden.

- Wenn Ihre HoloLens in den Standbymodus versetzt wird, während der Xbox Wireless Controller verbunden ist, werden alle Eingaben auf dem Controller die HoloLens recken. Sie können dies verhindern, indem Sie den Controller ausschalten, wenn Sie damit fertig sind.

## Bekannte Probleme für den HoloLens-Emulator

- Nicht alle Apps im Microsoft Store sind mit dem Emulator kompatibel. Beispielsweise können "Young Conker" und "Fragmente" nicht im Emulator abspielbar sein.
- Sie können die Webcam des PCs nicht im Emulator verwenden.
- Das Live Preview-Feature des Windows Device Portal funktioniert nicht mit dem Emulator. Sie können mixed Reality-Videos und -Bilder weiterhin aufnehmen.
