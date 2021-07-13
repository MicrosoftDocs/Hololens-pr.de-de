---
title: HoloLens Problembehandlung für Geräte
description: Bleiben Sie auf dem laufenden über die gängigsten Lösungen zum HoloLens von Geräteproblemen und Zur Problembehandlung.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: Issues, Bug, Troubleshoot, Fix, Help, Support, HoloLens, Emulator
ms.openlocfilehash: b07514e73e43d267aa856c0fb9a256448e565000
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635448"
---
# <a name="device-troubleshooting"></a>Problembehandlung für Geräte

In diesem Artikel wird beschrieben, wie Sie mehrere allgemeine HoloLens Beheben von Problemen beheben.

>[!IMPORTANT]
> Bevor Sie mit der Problembehandlung beginnen, stellen Sie sicher, dass Ihrem Gerät nach Möglichkeit **20 bis 40 Prozent** der Akkukapazität in Rechnung gestellt werden. Die [Akkuanzeigelichter](hololens2-setup.md#lights-that-indicate-the-battery-level) unter dem Netzschalter sind eine schnelle Möglichkeit, die Akkukapazität zu überprüfen, ohne sich beim Gerät anzumelden.

<a id="list"></a>

**Bekannte Probleme**
- [Remote Assist Video friert nach 20 Minuten ein](#remote-assist-video-freezes-after-20-minutes)
- [Bei der automatischen Anmeldung wird zur Anmeldung aufgefordert.](#auto-login-asks-for-log-in)
- [Microsoft Edge kann nicht gestartet werden](#microsoft-edge-fails-to-launch)
- [Tastatur wechselt nicht zu Sonderzeichen](#keyboard-doesnt-switch-to-special-characters)
- [Beim Herunterladen gesperrter Dateien wird kein Fehler angezeigt.](#downloading-locked-files-doesnt-error)
- [Geräteportal Dateiupload-/Download-Times out](#device-portal-file-uploaddownload-times-out)
- [Blue screen after unenrolling from Insider preview on a device flashed with an Insider build (Blauer Bildschirm nach dem Aufheben der Registrierung bei der Insider-Vorschau auf einem Gerät, das mit einem Insider-Build blinkt)](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive lädt Bilder nicht automatisch hoch.](#onedrive-doesnt-automatically-upload-pictures)

**Allgemein**
- [HoloLens reagiert nicht oder wird nicht gestartet](#hololens-is-unresponsive-or-wont-start)
- [Fehler "Wenig Speicherplatz"](#low-disk-space-error)
- [Kalibrierung schlägt fehl](#calibration-fails)
- [Kann sich nicht anmelden, da mein HoloLens zuvor für eine andere Person eingerichtet wurde.](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity funktioniert nicht](#unity-isnt-working)
- [Windows Geräteportal funktioniert nicht ordnungsgemäß](#windows-device-portal-isnt-working-correctly)
- [Die HoloLens Emulator funktioniert nicht](#the-hololens-emulator-isnt-working)

**Input** (Eingabe)
- [Sprachbefehle funktionieren nicht](#voice-commands-arent-working)
- [Handeingabe funktioniert nicht](#hand-input-isnt-working)

**Konnektivität**
- [Verbindung mit WLAN kann nicht hergestellt werden](#cant-connect-to-wi-fi)

**Externe Geräte** 
- [Bluetooth Geräte werden nicht gekoppelt](#bluetooth-devices-arent-pairing)
- [USB-C-Mikrofon funktioniert nicht](#usb-c-microphone-isnt-working)
- [Geräte, die in Einstellungen als verfügbar aufgeführt sind, funktionieren nicht](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Remote Assist Video friert nach 20 Minuten ein

> [!NOTE]
> Es gibt eine neuere Version von Remote Assist, die eine Lösung für dieses Problem enthält. Aktualisieren Sie [Remote Assist](holographic-store-apps.md#update-apps) auf die neueste Version, um dieses Problem zu vermeiden.

> [!NOTE]
> Aufgrund des Schweregrads dieses bekannten Problems haben wir die Verfügbarkeit von Windows Holographic, Version 21H1, vorübergehend angehalten. Der 21H1-Build ist jetzt wieder verfügbar, sodass Geräte erneut auf den neuesten 21H1-Build aktualisiert werden können.

In der neuesten Version von [Windows Holographic, Version 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)haben einige Benutzer von Remote Assist während Anrufen über 20 Minuten videogesperrt. Dies ist ein **bekanntes Problem.**

### <a name="workarounds"></a>Problemumgehungen

Wenn Sie Remote Assist nicht auf einen neueren Build aktualisieren können, versuchen Sie Folgendes.

#### <a name="restart-in-between-calls"></a>Neustart zwischen Aufrufen

Wenn Ihre Anrufe länger als 20 Minuten dauern und dieses Problem auftritt, versuchen Sie, Ihr Gerät neu zu starten. Wenn Sie Ihr Gerät zwischen Remote Assist Aufrufen neu starten, wird das Gerät aktualisiert und wieder in einen guten Zustand versetzt.

Um ein Gerät auf Windows Holographic schnell neu zu starten, öffnen Sie [Version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) das Startmenü, und wählen Sie das Benutzersymbol und dann **Neu starten** aus.

[Zurück zur Liste](#list)

## <a name="auto-login-asks-for-log-in"></a>Bei der automatischen Anmeldung wird zur Anmeldung aufgefordert.

Ein HoloLens 2 Gerät kann so konfiguriert werden, dass es sich automatisch über **Einstellungen** Anmeldeoptionen für Konten >  ->    ->   anmeldet und unter **Erforderlich** den Wert **auf Nie** festlegt. Einige Benutzer müssen sich möglicherweise erneut beim Gerät anmelden, wenn sie ein Gerät mit einem erheblich großen Update aktualisieren, z. B. ein Featureupdate. Dies ist ein **bekanntes Problem.**

Beispiel für den Fall, dass dies der Fall sein kann:

- Aktualisieren eines Geräts von Windows Holographic, Version 2004 (Build 19041.xxxx) auf Windows Holographic, Version 21H1 (Build 20346.xxxx)
- Aktualisieren eines Geräts, um ein umfangreiches Update für den gleichen Hauptbuild zu übernehmen, z. B. Windows Holographic, Version 2004 auf Windows Holographic, Version 20H2
- Aktualisieren eines Geräts von einem Factoryimage auf das neueste Image

Dies sollte nicht während der:

- Geräte, die ein monatliches Wartungsupdate durchführen

Umgehen von Methoden:

- Anmeldemethoden wie PIN, Kennwort, Iris, Webauthentifizierung oder FIDO2-Schlüssel.
- Wenn die Geräte-PIN nicht gespeichert werden kann und andere Authentifizierungsmethoden nicht verfügbar sind, kann ein Benutzer den [manuellen Reflashingmodus](hololens-recovery.md#manual-procedure)verwenden.

[Zurück zur Liste](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge kann nicht gestartet werden

> [!NOTE]
> Dieses Problem wurde ursprünglich mit der Versandversion von Microsoft Edge erstellt. Dieses Problem kann im [neuen Microsoft Edge](hololens-new-edge.md)behoben werden. Wenn dies nicht dere ist, senden Sie uns Feedback.

Einige Kunden haben ein Problem gemeldet, bei dem Microsoft Edge nicht gestartet werden kann. Für diese Kunden bleibt das Problem durch einen Neustart bestehen und wird nicht mit Windows oder Anwendungsupdates gelöst. Wenn dieses Problem auftritt und Sie bestätigt [haben, dass Windows auf dem neuesten Stand ist,](hololens-updates.md#manually-check-for-updates)melden Sie einen Fehler aus der [Feedback-Hub-App](hololens-feedback.md) mit der folgenden Kategorie und Unterkategorie: Installieren und Aktualisieren > Herunterladen, Installieren und Konfigurieren von Windows Update.

Es gibt keine bekannten Problemumgehungen, da wir das Problem bisher nicht lösen konnten. Das Melden eines Fehlers über Feedback-Hub hilft uns bei unserer Untersuchung! Dies ist ein **bekanntes Problem.**

[Zurück zur Liste](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Tastatur wechselt nicht zu Sonderzeichen

Während der OOBE tritt ein Problem auf, bei dem der Benutzer, nachdem er ein Arbeits- oder Schulkonto ausgewählt hat und sein Kennwort eingibt, versucht, zu den Sonderzeichen auf der Tastatur zu wechseln, indem er auf die Schaltfläche &123 tippt, nicht in Sonderzeichen geändert wird. Dies ist ein **bekanntes Problem.**

Work-arounds:
-   Schließen Sie die Tastatur, und öffnen Sie sie erneut, indem Sie auf das Textfeld tippen.
-   Geben Sie ihr Kennwort falsch ein. Wenn die Tastatur beim nächsten Mal neu gestartet wird, funktioniert sie wie erwartet.
- Webauthentifizierung: Schließen Sie die Tastatur, und wählen **Sie Von einem anderen Gerät aus anmelden aus.**
-   Wenn nur Zahlen eingegeben werden, kann ein Benutzer bestimmte Tasten drücken und gedrückt halten, um ein erweitertes Menü zu öffnen.
-   Verwenden einer USB-Tastatur.

Dies wirkt sich nicht auf:
- Benutzer, die sich für die Verwendung eines persönlichen Kontos entscheiden.

[Zurück zur Liste](#list)

## <a name="downloading-locked-files-doesnt-error"></a>Fehler beim Herunterladen gesperrter Dateien

> [!NOTE]
> Dies ist ein **bekanntes Problem,** das in Windows Insider-Buildversion 20348.1403 behoben wurde.

In vorherigen Builds von Windows Holographic war das Ergebnis beim Herunterladen einer gesperrten Datei eine HTTP-Fehlerseite. Im Windows Holographic-Update, Version 21H1, führt der Versuch, eine gesperrte Datei herunterzuladen, dazu, dass nichts sichtbar ist– die Datei wird nicht heruntergeladen, und es tritt kein Fehler auf.

[Zurück zur Liste](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Geräteportal Dateiupload-/Download-Times out
> [!NOTE]
> Dies ist ein **bekanntes Problem,** das in Windows Insider-Buildversion 20348.1403 behoben wurde. Wenn Sie die SSL-Verbindung zuvor als Teil der Problemumgehung deaktiviert haben, wird dringend empfohlen, sie erneut zu aktivieren.


Einige Kunden haben festgestellt, dass beim Versuch, Dateien hoch- oder herunterzuladen, der Vorgang möglicherweise hängt und dann ein Time out oder nie abgeschlossen wird. Dies ist vom[bekannten Problem "Datei gesperrt"](#downloading-locked-files-doesnt-error) getrennt. Dies betrifft Windows Holographic-Builds der Versionen 2004, 20H2 und 21H1. Das Problem wurde aufgrund eines Fehlers bei der Verarbeitung bestimmter Anforderungen durch Geräteportal verursacht und tritt am häufigsten auf, wenn https verwendet wird. Dies ist die Standardeinstellung. 

### <a name="workaround"></a>Problemumgehung

Diese Problemumgehung, die gleichermaßen für Wi-Fi und UsbNcm gilt, besteht darin, die Option "erforderlich" unter "SSL-Verbindung" zu deaktivieren. Navigieren Sie hierzu zu Geräteportal, **System**, und wählen Sie die Seite **Einstellungen aus.** Suchen Sie im Abschnitt **Gerätesicherheit** nach **SSL-Verbindung,** und deaktivieren Sie die Option **Erforderlich.**

Der Benutzer sollte dann zu http:// wechseln, nicht https:// (IP-Adresse) und Features wie das Hochladen und Herunterladen von Dateien funktionieren.

[Zurück zur Liste](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Blauer Bildschirm nach dem Entrollen der Insider-Vorschau auf einem Gerät mit einem Insider-Build

Dieses Problem wirkt sich auf Benutzer aus, die sich in einem Insider Preview-Build befinden, ihre HoloLens 2 mit einem neuen Insider Preview-Build neu auftänden und dann die Registrierung beim Insider-Programm wieder auftänden. Dies ist ein **bekanntes Problem.**

Dies hat keine Auswirkungen auf:
- Benutzer, die nicht bei Windows Insider registriert sind 
- Insider:
    - Wenn ein Gerät seit Insider-Builds registriert wurde, version 18362.x
    - Wenn sie einen Insider-signierten 19041.x-Build flashten und beim Insider-Programm registriert bleiben

Umgeknung: 
- Vermeiden Sie das Problem. 
    - Flash für einen Nicht-Insider-Build. Eines der regelmäßigen monatlichen Updates.
    - Stay on Insider Preview
- Neustarten des Geräts

    1. Stellen Sie [die HoloLens 2 manuell in den Flashmodus,](hololens-recovery.md) indem Sie vollständig heruntergefahren werden, ohne eine Verbindung herzustellen. Tippen Sie dann beim Halten des Volumes auf den Netzschalter.
    
    1. Verbinden sie auf den PC, und öffnen Sie Advanced Recovery Companion.
    
    1. Flashen HoloLens 2 an den Standard-Build.

[Zurück zur Liste](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive werden bilder nicht automatisch hochgeladen.

Die OneDrive-App für HoloLens unterstützt keinen automatischen Kameraupload für Arbeits- oder Schulkonten. Dies ist ein **bekanntes Problem.**

Problemumgehungen:

- Wenn dies für Ihr Unternehmen sinnvoll ist, wird der automatische Kameraupload für Microsoft-Kundenkonten unterstützt. Sie können sich bei Ihrem Microsoft-Konto zusätzlich zu Ihrem Arbeits-, Schul- oder Schulkonto anmelden (die OneDrive-App unterstützt die duale Anmeldung). In Ihrem Microsoft-Konto profil in OneDrive können Sie den automatischen Rollup der Hintergrundkamera aktivieren.

- Wenn Sie einen Consumer-Microsoft-Konto zum automatischen Hochladen Ihrer Fotos nicht sicher verwenden können, können Sie Fotos manuell aus der App in Ihr Arbeits- oder Schulkonto OneDrive hochladen. Stellen Sie dazu sicher, dass Sie bei Ihrem Arbeits- oder Schulkonto in der OneDrive sind. Wählen Sie die **+** Schaltfläche und dann **Hochladen.** Suchen Sie die Fotos oder Videos, die Sie hochladen möchten, indem Sie zu Bilder > **Camera Roll navigieren.** Wählen Sie die Fotos oder Videos aus, die Sie hochladen möchten, und klicken Sie dann auf **die Schaltfläche** Öffnen.

[Zurück zur Liste](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens reagiert nicht oder startet nicht

Wenn Ihr HoloLens nicht gestartet wird:

- Wenn die LEDs neben dem Netzschalter nicht aufglühen oder nur eine LED kurz blinkt, müssen Sie möglicherweise Ihre [HoloLens.](hololens2-charging.md#charging-the-device)
- Wenn die LEDs beim Drücken des Netzschalters einglühen, aber auf den Anzeigen nichts angezeigt wird, setzen Sie das Gerät [fest zurück.](hololens-recovery.md#hard-reset-procedure)

Wenn Ihr HoloLens fixiert wird oder nicht mehr reagiert:

- Schalten Sie ihre HoloLens aus, indem Sie den Netzschalter drücken, bis sich alle fünf LEDs selbst ausschalten, oder 15 Sekunden lang, wenn die LEDs nicht reagieren. Drücken Sie erneut HoloLens, um den Computer zu starten.

Wenn diese Schritte nicht funktionieren, [](hololens-recovery.md) können Sie versuchen, Ihr HoloLens 2 oder HoloLens [(1. Generation) wiederhergestellt zu werden.](hololens1-recovery.md)

[Zurück zur Liste](#list)

## <a name="low-disk-space-error"></a>Fehler "Wenig Speicherplatz"

Sie müssen speicherplatzaufbewahren, indem Sie eine oder mehrere der folgenden Schritte tun:

- Löschen Sie einige nicht verwendete Leerzeichen. Wechseln Sie **Einstellungen**  >    >  **Systemräume,** wählen Sie ein Leerzeichen aus, das Sie nicht mehr benötigen, und wählen Sie dann **Entfernen aus.**
- Entfernen Sie einige der Hologramme, die Sie platziert haben.
- Löschen Sie einige Bilder und Videos aus der Fotos App.
- Deinstallieren Sie einige Apps aus HoloLens. Tippen **und Alle Apps** in der Liste Der Benutzer tippen und halten Sie die App, die Sie deinstallieren möchten, und wählen Sie dann Deinstallieren **aus.**

[Zurück zur Liste](#list)

## <a name="calibration-fails"></a>Kalibrierung schlägt fehl

Die Kalibrierung sollte für die meisten Personen funktionieren, aber es gibt Fälle, in denen die Kalibrierung fehlschlägt.
  
Mögliche Gründe für Kalibrierungsfehler:

- Abgelenkung und Nichterkennen der Kalibrierungsziele
- Dirty or scratched device visor or device visor not positioned properly (Nicht ordnungsgemäß positioniertes oder verzerrtes Gerätevisor oder Gerätevisor)
- Dirty oder Scratched Brille
- Bestimmte Arten von Kontaktobjekten und Brillen (farbige Kontaktbrillen, einige Toric-Kontaktkontakte, IR blockierende Brillen, einige Brillen mit hoher Brille, Sonnenbrillen oder ähnliches)
- Stärker ausgesprochenes Makeup und einige Wimpernerweiterungen
- Brillenrahmen mit Kopf oder Brille, wenn sie das Gerät am Sehen Ihrer Augen blockieren
- Bestimmte Augenplage, Augenbedingungen oder Augenbrillen wie schmale Augen, lange Augenstriche, Amblylen, Nystagmus, einige Fälle von LASIK oder andere Augenspitzen

Wenn die Kalibrierung nicht erfolgreich ist, versuchen Sie:

- Bereinigen des Gerätevisors
- Bereinigen ihrer Brille
- Pushen Ihres Gerätevisors so nah wie möglich an Ihren Augen
- Entfernen von Objekten in Ihrem Visor (z. B. Beschnitt)
- Einschalten eines Lichts in Ihrem Raum oder Verlassen des direkten Lichts

Wenn Sie alle Richtlinien befolgt haben und die Kalibrierung weiterhin fehlschlägt, können Sie die Kalibrierungsaufforderung in der Einstellungen. Teilen Sie uns dies auch mit, indem Sie feedback in [Feedback-Hub.](hololens-feedback.md)

Weitere Informationen finden Sie auch in den [zugehörigen Informationen zur Problembehandlung bei Bildfarben oder Helligkeit.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Das Festlegen der IPD gilt nicht für HoloLens 2, da Augenpositionen vom System berechnet werden. 

[Zurück zur Liste](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Kann sich nicht anmelden, da mein HoloLens zuvor für eine andere Person eingerichtet wurde

Sie können [das Gerät in den **Flashmodus setzen** und Advanced Recovery Companion zum](hololens-recovery.md#clean-reflash-the-device) Wiederherstellen des Geräts verwenden.

[Zurück zur Liste](#list)


## <a name="unity-isnt-working"></a>Unity funktioniert nicht

- Unter [Installieren der Tools](/windows/mixed-reality/install-the-tools) finden Sie die neueste Version von Unity, die für die entwicklung HoloLens wird.
- Bekannte Probleme mit der Unity HoloLens Technical Preview sind in den [Unity-Foren](https://forum.unity3d.com/threads/known-issues.394627/)HoloLens dokumentiert.

[Zurück zur Liste](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Geräteportal funktioniert nicht ordnungsgemäß.

- Die Livevorschaufunktion in Mixed Reality Erfassung kann einige Sekunden Latenz zeigen.

- Auf der Seite Virtuelle Eingabe sind die Steuerelemente Geste und Bildlauf im Abschnitt Virtuelle Gesten nicht funktionsfähig. Ihre Verwendung hat keine Auswirkungen. Die virtuelle Tastatur auf der virtuellen Eingabeseite funktioniert ordnungsgemäß.

- Nach dem Aktivieren des Entwicklermodus in Einstellungen kann es einige Sekunden dauern, bis der Schalter aktiviert Geräteportal ist.

[Zurück zur Liste](#list)

## <a name="the-hololens-emulator-isnt-working"></a>Die HoloLens Emulator funktioniert nicht

Informationen zum HoloLens Emulator finden Sie in unserer Entwicklerdokumentation.  Erfahren Sie mehr über [die Problembehandlung des HoloLens Emulators.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)


- Nicht alle Apps in der Microsoft Store sind mit dem Emulator kompatibel. Beispielsweise können Young Conker und Fragmente nicht auf dem Emulator abspielbar sein.
- Sie können die PC-Webcam nicht in der Emulator.
- Das LiveVorschaufeature des Windows Geräteportal funktioniert nicht mit dem Emulator. Sie können weiterhin Mixed Reality Videos und Bilder erfassen.

[Zurück zur Liste](#list)

## <a name="voice-commands-arent-working"></a>Sprachbefehle funktionieren nicht

Wenn Cortana nicht auf Ihre Sprachbefehle reagiert, stellen Sie sicher, Cortana aktiviert ist. Wählen Sie Alle Apps Liste die Option **Cortana**  >  **Menü**  >  **Notebook**  >  **Einstellungen,** um Änderungen vorzunehmen. Weitere Informationen dazu, was Sie sagen können, finden Sie unter [Verwenden Ihrer Stimme mit HoloLens](hololens-cortana.md).

Bei HoloLens (1. Generation) ist die integrierte Spracherkennung nicht konfigurierbar. Sie ist immer aktiviert. Auf HoloLens 2 können Sie auswählen, ob die Spracherkennung und Cortana während der Geräteeinrichtung eingeschaltet werden sollen.

Wenn Ihr HoloLens 2 nicht auf Ihre Stimme reagiert, stellen Sie sicher, dass die Spracherkennung aktiviert ist. Wechseln **Sie** zu Start  >  **Einstellungen**  >  **Privacy**  >  **Speech ,und** aktivieren Sie **die Spracherkennung.**

[Zurück zur Liste](#list)

## <a name="hand-input-isnt-working"></a>Handeingabe funktioniert nicht

Um sicherzustellen, dass HoloLens Ihre Hände sehen können, müssen Sie sie im Gestenrahmen aufbewahren.  Die Mixed Reality Home bietet Feedback, das Sie darüber informiert, wann Ihre Hände nachverfolgt werden.  Das Feedback unterscheidet sich in verschiedenen Versionen von HoloLens:
- Bei HoloLens (1. Generation) ändert sich der Cursor für das Anvischen von einem Punkt in einen Ring.
- Auf HoloLens 2 wird ein Fingerspitzencursor angezeigt, wenn sich die Hand in der Nähe eines Schiefers befindet, und ein Handstrahl wird angezeigt, wenn sich die Schieferzeichen weiter entfernt befinden.

Viele immersive Apps folgen Eingabemustern, die Mixed Reality Home ähneln.  Erfahren Sie mehr über die Verwendung von Handeingaben in [HoloLens (1. Generation)](hololens1-basic-usage.md#use-hololens-with-your-hands) und [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Beachten Sie, dass einige Arten von Handlangen nicht mit Handtracking funktionieren, wenn Sie Handschutz tragen.  Ein häufiges Beispiel sind schwarze Handbänder, die dazu tendieren, Licht zu absorbieren und nicht von der Tiefenkamera aufgenommen werden.  Wenn Es bei Ihrer Arbeit um Handbänder geht, empfiehlt es sich, eine hellere Farbe wie Blau oder Grau zu versuchen.  Ein weiteres Beispiel sind große baggy-Handstücke, die dazu tendieren, die Form Ihrer Hand zu verbergen. Wir empfehlen die Verwendung von Handlangen, die so formanpassend wie möglich sind, um optimale Ergebnisse zu erzielen.

Wenn Ihr Visier Fingerabdrücke oder Smudges hat, verwenden Sie die Mikrofiber-Bereinigungsanlage, die im HoloLens zur Bereinigung Ihres Visors verwendet wurde.

[Zurück zur Liste](#list)

## <a name="cant-connect-to-wi-fi"></a>Verbindung mit Wi-Fi kann nicht hergestellt werden

Hier sind einige Dinge, die Sie ausprobieren sollten, wenn Sie Ihre HoloLens nicht mit einem Wi-Fi Netzwerk verbinden können:

- Stellen Sie sicher, dass Wi-Fi aktiviert ist. Um dies zu überprüfen, verwenden Sie die Startgeste, und wählen Sie dann **Einstellungen**  >  **&amp; Netzwerkinternet-WLAN**  >  aus. Wenn Wi-Fi eingeschaltet ist, versuchen Sie, es zu deaktivieren und dann erneut zu aktivieren.
- Nähern Sie sich dem Router oder Zugriffspunkt.
- Starten Sie Ihren Wi-Fi Router neu, und starten Sie dann [HoloLens neu.](hololens-recovery.md) Try connecting again.
- Wenn keines dieser Dinge funktioniert, überprüfen Sie, ob Ihr Router die neueste Firmware verwendet. Sie finden diese Informationen auf der Herstellerwebsite.

[Zurück zur Liste](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth Geräte werden nicht gekoppelt

Wenn Beim [Koppeln eines Bluetooth Geräts](hololens-connect-devices.md)Probleme auftreten, versuchen Sie Folgendes:

- Wechseln Sie zu **Einstellungen**  >  **Geräte**, und stellen Sie sicher, dass Bluetooth aktiviert ist. Wenn dies der Grund ist, deaktivieren Sie sie, und aktivieren Sie sie erneut.
- Stellen Sie sicher, dass Ihr Bluetooth Gerät vollständig in Rechnung gestellt wird oder über neue Akkus verfügt.
- Wenn Sie weiterhin keine Verbindung herstellen können, [starten Sie den HoloLens neu.](hololens-recovery.md)

[Zurück zur Liste](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C-Mikrofon funktioniert nicht
Beachten Sie, dass einige USB-C-Mikrofone sich fälschlicherweise sowohl als *Mikrofon* als auch als Lautsprecher melden. Dies ist ein Problem mit dem Mikrofon und nicht mit HoloLens. Wenn Sie eines dieser Mikrofone in HoloLens anschließen, geht möglicherweise der Sound verloren. Glücklicherweise gibt es eine einfache Lösung.  

Legen **Sie in Einstellungen**  ->  **System**  ->  **Sound** die integrierten Lautsprecher **(Analog Feature Audio Driver)** explizit als **Standardgerät** fest. HoloLens sollten sich diese Einstellung auch dann merken, wenn das Mikrofon entfernt und später erneut verbunden wird.

![Problembehandlung bei USB-C-Mikrofonen](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Geräte, die in Einstellungen als verfügbar aufgeführt sind, funktionieren nicht

HoloLens (1. Generation) unterstützt keine Bluetooth Audioprofile. Bluetooth Audiogeräte, z. B. Lautsprecher und Headsets, werden möglicherweise in HoloLens Einstellungen als verfügbar angezeigt, werden jedoch nicht unterstützt.

HoloLens 2 unterstützt das Bluetooth A2DP-Audioprofil für die Stereowiedergabe. Das Profil Bluetooth Hands Free, das die Mikrofonerfassung von einem Bluetooth Peripheriegerät ermöglicht, wird auf HoloLens 2 nicht unterstützt.

Wenn Sie Probleme bei der Verwendung eines Bluetooth Geräts haben, stellen Sie sicher, dass es sich um ein unterstütztes Gerät handelt. Folgende Geräte werden unterstützt:

- QWERTY in englischer Sprache Bluetooth Tastaturen (Sie können diese überall dort verwenden, wo Sie die holografische Tastatur verwenden).
- Bluetooth-Maus.
- Der [HoloLens Clicker](hololens1-clicker.md).

Sie können andere Bluetooth HID- und GATT-Geräte mit Ihrem HoloLens koppeln. Möglicherweise müssen Sie jedoch entsprechende Begleit-Apps von Microsoft Store installieren, um die Geräte tatsächlich zu verwenden.

[Zurück zur Liste](#list)
