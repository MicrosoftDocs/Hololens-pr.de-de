---
title: Problembehandlung für HoloLens-Geräte
description: Bleiben Sie über die gängigsten Lösungen für HoloLens-Geräteprobleme und Problembehandlungstechniken auf dem Laufenden.
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
keywords: Probleme, Fehler, Problembehandlung, Fehlerbehebung, Hilfe, Support, HoloLens, Emulator
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924620"
---
# <a name="device-troubleshooting"></a>Problembehandlung für Geräte

In diesem Artikel wird beschrieben, wie Sie mehrere häufige HoloLens-Probleme beheben.

>[!IMPORTANT]
> Bevor Sie mit der Problembehandlung beginnen, stellen Sie sicher, dass Ihr Gerät nach Möglichkeit **auf 20 bis 40** Prozent der Akkukapazität abgerechnet wird. Die [Akkuanzeigelichter](hololens2-setup.md#lights-that-indicate-the-battery-level) unter dem Netzschalter sind eine schnelle Möglichkeit, die Akkukapazität zu überprüfen, ohne sich beim Gerät anmelden zu müssen.

<a id="list"></a>

**Bekannte Probleme**
- [Remote Assist Video friert nach 20 Minuten ein](#remote-assist-video-freezes-after-20-minutes)
- [Bei der automatischen Anmeldung wird nach der Anmeldung gefragt.](#auto-login-asks-for-log-in)
- [Microsoft Edge kann nicht gestartet werden](#microsoft-edge-fails-to-launch)
- [Tastatur wechselt nicht zu Sonderzeichen](#keyboard-doesnt-switch-to-special-characters)
- [Beim Herunterladen gesperrter Dateien wird kein Fehler angezeigt.](#downloading-locked-files-doesnt-error)
- [Geräteportal beim Hochladen/Herunterladen von Dateien wird ein Zeitsupload durchgeführt.](#device-portal-file-uploaddownload-times-out)
- [Blauer Bildschirm nach dem Entrollen der Insider-Vorschau auf einem Gerät mit einem Insider-Build](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive lädt bilder nicht automatisch hoch.](#onedrive-doesnt-automatically-upload-pictures)

**Allgemein**
- [HoloLens reagiert nicht oder startet nicht](#hololens-is-unresponsive-or-wont-start)
- [Fehler "Wenig Speicherplatz"](#low-disk-space-error)
- [Kalibrierung schlägt fehl](#calibration-fails)
- [Kann sich nicht anmelden, da meine HoloLens zuvor für eine andere Person eingerichtet wurde](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity funktioniert nicht](#unity-isnt-working)
- [Windows-Geräteportal funktioniert nicht ordnungsgemäß.](#windows-device-portal-isnt-working-correctly)
- [Der HoloLens-Emulator funktioniert nicht](#the-hololens-emulator-isnt-working)

**Eingabe**
- [Sprachbefehle funktionieren nicht](#voice-commands-arent-working)
- [Handeingabe funktioniert nicht](#hand-input-isnt-working)

**Konnektivität**
- [Verbindung mit WLAN kann nicht hergestellt werden](#cant-connect-to-wi-fi)

**Externe Geräte** 
- [Bluetooth-Geräte werden nicht gekoppelt](#bluetooth-devices-arent-pairing)
- [USB-C-Mikrofon funktioniert nicht](#usb-c-microphone-isnt-working)
- [Geräte, die unter Einstellungen als verfügbar aufgeführt sind, funktionieren nicht](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Remote Assist Video friert nach 20 Minuten ein

> [!NOTE]
> Aufgrund des Schweregrads dieses bekannten Problems wurde die Verfügbarkeit von Windows Holographic, Version 21H1, angehalten. Wenn Sie Ihre Geräte weiterhin auf 21H1 aktualisieren möchten, lesen Sie die Anweisungen in unseren Versionshinweisen oben [auf der Seite.](hololens-release-notes.md)

Bei der neuesten Version von [Windows Holographic, Version 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)haben einige Benutzer von Remote Assist video freezing during calls over 20 minutes (Video einfrieren bei Aufrufen über 20 Minuten). Dies ist ein **bekanntes Problem.**

### <a name="workarounds"></a>Problemumgehungen

#### <a name="restart-in-between-calls"></a>Neustarten zwischen Aufrufen

Wenn Ihre Aufrufe länger als 20 Minuten dauern und dieses Problem vor sich geht, versuchen Sie, Ihr Gerät neu zu starten. Wenn Sie Ihr Gerät zwischen Remote Assist aufrufen, wird das Gerät aktualisiert und wieder in einen guten Zustand zurückverstanden.

Um ein Gerät unter Windows Holographic schnell neu zu starten, öffnen Sie Version [21H1](hololens-release-notes.md#windows-holographic-version-21h1) das Startmenü, wählen Sie das Benutzersymbol aus, und wählen Sie dann **Neu starten aus.**

#### <a name="revert-to-an-older-build"></a>Zurückverwenden zu einem älteren Build

Einige Kunden haben festgestellt, dass dieses Problem nicht mehr vor sich geht, wenn sie auf eine frühere Betriebssystemversion zurückverwenden. Wenn Sie festgestellt haben, dass bei Ihren Geräten dieses Problem vor liegt, führen Sie die folgenden Schritte aus:


Problemumgehungen:

- Wenn dies für Ihr Unternehmen sinnvoll ist, wird der automatische Kameraupload für Microsoft-Kundenkonten unterstützt. Sie können sich bei Ihrem Microsoft-Konto zusätzlich zu Ihrem Arbeits-, Schul- oder Schulkonto anmelden (die OneDrive-App unterstützt die duale Anmeldung). In Ihrem Microsoft-Konto in OneDrive können Sie den automatischen Rollup der Hintergrundkamera aktivieren.

- Wenn Sie einen Consumer-Microsoft-Konto zum automatischen Hochladen Ihrer Fotos nicht sicher verwenden können, können Sie Fotos manuell aus der OneDrive-App in Ihr Arbeits-, Schul- oder Schulkonto hochladen. Stellen Sie dazu sicher, dass Sie bei Ihrem Arbeits- oder Schulkonto in der OneDrive-App angemeldet sind. Wählen Sie die **+** Schaltfläche und dann Hochladen **aus.** Suchen Sie die Fotos oder Videos, die Sie hochladen möchten, indem Sie zu Bilder > **Camera Roll navigieren.** Wählen Sie die Fotos oder Videos aus, die Sie hochladen möchten, und klicken Sie dann auf **die Schaltfläche** Öffnen.


1. [Herunterladen des Build für Windows Holographic, Version 20H2 – Update mai 2021](https://aka.ms/hololens2download/10.0.19041.1146)
1. Befolgen Sie die [Anweisungen, um zu einer früheren Betriebssystemversion zurückzukehren.](hololens-update-hololens.md#go-back-to-a-previous-version)
1. Halten [Sie Betriebssystemupdates auf dem Gerät entweder manuell an,](hololens-updates.md#pause-updates-via-device) oder verwenden Sie für viele Geräte eine [Zurückschiefung über MDM.](hololens-updates.md#configure-an-update-deferral-policy)

[Zurück zur Liste](#list)

## <a name="auto-login-asks-for-log-in"></a>Bei der automatischen Anmeldung wird nach der Anmeldung gefragt.

Ein HoloLens 2-Gerät kann so konfiguriert werden, dass es sich automatisch über Anmeldeoptionen für Einstellungskonten -> anmeldet und unter Erforderlich den Wert auf  ->    ->   **Never (Nie) festlegen.**  Einige Benutzer müssen sich möglicherweise erneut beim Gerät anmelden, wenn sie ein Gerät mit einem wesentlich großen Update aktualisieren, z. B. einem Featureupdate. Dies ist ein **bekanntes Problem.**

Beispiel für den Fall, dass dies auftreten kann:

- Aktualisieren eines Geräts von Windows Holographic, Version 2004 (Build 19041.xxxx) auf Windows Holographic, Version 21H1 (Build 20346.xxxx)
- Aktualisieren eines Geräts, um ein großes Update auf demselben Hauptversions-Build zu übernehmen, z. B. Windows Holographic, Version 2004 auf Windows Holographic, Version 20H2
- Aktualisieren eines Geräts von einem Factoryimage auf das neueste Image

Dies sollte in den:

- Geräte, die ein monatliches Wartungsupdate verwenden

Methodenumkung:

- Anmeldemethoden wie PIN, Kennwort, Iris, Webauthentifizierung oder FIDO2-Schlüssel.
- Wenn die Geräte-PIN nicht gespeichert werden kann und keine anderen Authentifizierungsmethoden verfügbar sind, kann ein Benutzer den manuellen [Reflashmodus verwenden.](hololens-recovery.md#manual-procedure)

[Zurück zur Liste](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge kann nicht gestartet werden

> [!NOTE]
> Dieses Problem wurde ursprünglich mit der Versandversion von Microsoft Edge erstellt. Dieses Problem kann in der neuen Version [von Microsoft Edge.](hololens-new-edge.md) Wenn dies nicht der Dere ist, senden Sie Uns Feedback.

Einige Kunden haben ein Problem gemeldet, bei dem Microsoft Edge nicht gestartet werden kann. Für diese Kunden bleibt das Problem durch einen Neustart bestehen und wird nicht mit Windows- oder Anwendungsupdates gelöst. Wenn dieses Problem besteht und Sie bestätigt haben, dass [Windows](hololens-updates.md#manually-check-for-updates)auf dem neuesten Stand ist, melden Sie einen Fehler aus der [Feedback-Hub-App](hololens-feedback.md) mit der folgenden Kategorie und Unterkategorie: Installieren und Aktualisieren > Herunterladen, Installieren und Konfigurieren von Windows Update.

Es gibt keine bekannten Problemumgehungen, da wir das Problem bisher nicht beheben konnten. Das Einreichen eines Fehlers über Feedback-Hub hilft uns bei der Untersuchung! Dies ist ein **bekanntes Problem.**

[Zurück zur Liste](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Tastatur wechselt nicht zu Sonderzeichen

Während der OOBE liegt ein Problem vor, bei dem sich der Versuch, zu den Sonderzeichen auf der Tastatur zu wechseln, indem er auf die Schaltfläche &123 tippt, nicht in Sonderzeichen ändert, sobald der Benutzer ein Arbeits-, Schul- oder Schulkonto ausgewählt und sein Kennwort eingegeben hat. Dies ist ein **bekanntes Problem.**

Arbeitsumgefungen:
-   Schließen Sie die Tastatur, und öffnen Sie sie erneut, indem Sie auf das Textfeld tippen.
-   Geben Sie Ihr Kennwort falsch ein. Wenn die Tastatur das nächste Mal neu gestartet wird, funktioniert sie wie erwartet.
- Webauthentifizierung, schließen Sie die Tastatur, und wählen **Sie Von einem anderen Gerät aus anmelden aus.**
-   Wenn nur Zahlen eingeben, kann ein Benutzer bestimmte Tasten drücken und halten, um ein erweitertes Menü zu öffnen.
-   Verwenden einer USB-Tastatur.

Dies hat keine Auswirkungen auf:
- Benutzer, die sich für die Verwendung eines persönlichen Kontos entscheiden.

[Zurück zur Liste](#list)


## <a name="downloading-locked-files-doesnt-error"></a>Fehler beim Herunterladen gesperrter Dateien
> ! HINWEIS Dies ist **ein bekanntes** Problem, das in Windows-Insider Build, Version 20348.1403, behoben wurde.


In früheren Builds von Windows Holographic war das Ergebnis beim Versuch, eine gesperrte Datei herunterzuladen, eine HTTP-Fehlerseite. Im Windows Holographic-Update, Version 21H1, führt der Versuch, eine gesperrte Datei herunterzuladen, dazu, dass nichts sichtbar ist– die Datei wird nicht heruntergeladen, und es tritt kein Fehler auf. 

[Zurück zur Liste](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Geräteportal Dateiupload-/Download-Times out
> ! HINWEIS Dies ist ein **bekanntes Problem,** das in Windows-Insider Buildversion 20348.1403 behoben wurde. Wenn Sie die SSL-Verbindung zuvor als Teil der Problemumgehung deaktiviert haben, wird dringend empfohlen, sie erneut zu aktivieren.


Einige Kunden haben festgestellt, dass beim Versuch, Dateien hoch- oder herunterzuladen, der Vorgang möglicherweise hängt und dann ein Time out oder nie abgeschlossen wird. Dies ist vom[bekannten Problem "Datei gesperrt"](#downloading-locked-files-doesnt-error) getrennt. Dies betrifft windows Holographic, versionen 2004, 20H2 und 21H1 in-market builds. Das Problem wurde aufgrund eines Fehlers bei der Verarbeitung bestimmter Anforderungen durch Geräteportal verursacht und tritt am häufigsten auf, wenn https verwendet wird. Dies ist die Standardeinstellung. 

### <a name="workaround"></a>Problemumgehung

Diese Problemumgehung, die gleichermaßen für Wi-Fi und UsbNcm gilt, besteht darin, die Option "erforderlich" unter "SSL-Verbindung" zu deaktivieren. Navigieren Sie hierzu zu **Geräteportal, System,** und wählen Sie die Seite **Einstellungen aus.** Suchen Sie im Abschnitt **Gerätesicherheit** nach **SSL-Verbindung,** und deaktivieren Sie die Option **Erforderlich.**

Der Benutzer sollte dann zu http:// wechseln, nicht https:// (IP-Adresse) und Features wie Dateiupload und -download funktionieren.

[Zurück zur Liste](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Blue screen after unenrolling from Insider preview on a device flashed with an Insider build (Blauer Bildschirm nach dem Aufheben der Registrierung bei der Insider-Vorschau auf einem Gerät, das mit einem Insider-Build blinkt)

Dies ist ein Problem, das sich auf Benutzer auswirkt, die sich in einem Insider-Vorschaubuild befanden, ihre HoloLens 2 mit einem neuen Insider Preview-Build umgestrichen und dann die Registrierung für das Insider-Programm aufgehoben haben. Dies ist ein **bekanntes Problem.**

Dies wirkt sich nicht auf:
- Benutzer, die nicht für Windows-Insider registriert sind 
- Insider:
    - Wenn ein Gerät registriert wurde, seit Insider-Builds Version 18362.x waren
    - Wenn sie einen von Insider signierten 19041.x-Build flashten, bleiben Sie für das Insider-Programm registriert.

Umgehen: 
- Vermeiden Sie das Problem. 
    - Flashen sie einen Nicht-Insider-Build. Eines der regelmäßigen monatlichen Updates.
    - Bleiben Sie auf Insider Preview
- Reflash the device (Reflash des Geräts)

    1. Versetzen Sie die HoloLens 2 manuell in den [Blinkmodus,](hololens-recovery.md) indem Sie vollständig herunterschalten, ohne eine Verbindung herzustellen. Tippen Sie dann bei gedrückter Lautstärke auf die Netzschaltfläche.
    
    1. Stellen Sie eine Verbindung mit dem PC her, und öffnen Sie Advanced Recovery Companion.
    
    1. Flashen Sie die HoloLens 2 auf den Standardbuild.

[Zurück zur Liste](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive lädt Bilder nicht automatisch hoch

Die OneDrive-App für HoloLens unterstützt keinen automatischen Kameraupload für Arbeits- oder Schulkonten. Dies ist ein **bekanntes Problem.**

Problemumgehungen:

- Wenn dies für Ihr Unternehmen sinnvoll ist, wird der automatische Kameraupload für Microsoft-Kundenkonten unterstützt. Sie können sich zusätzlich zu Ihrem Arbeits- oder Schulkonto bei Ihrem Microsoft-Konto anmelden (die OneDrive-App unterstützt die duale Anmeldung). In Ihrem Microsoft-Konto-Profil in OneDrive können Sie den automatischen Kamerarollup im Hintergrund aktivieren.

- Wenn Sie einen Consumer Microsoft-Konto nicht sicher zum automatischen Hochladen Ihrer Fotos verwenden können, können Sie Fotos manuell über die OneDrive-App in Ihr Arbeits- oder Schulkonto hochladen. Stellen Sie hierzu sicher, dass Sie bei Ihrem Arbeits- oder Schulkonto in der OneDrive-App angemeldet sind. Wählen Sie die **+** Schaltfläche und dann **Hochladen** aus. Suchen Sie die Fotos oder Videos, die Sie hochladen möchten, indem Sie zu **Bilder > Kameraroll navigieren.** Wählen Sie die Fotos oder Videos aus, die Sie hochladen möchten, und klicken Sie dann auf die Schaltfläche **Öffnen.**

[Zurück zur Liste](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens reagiert nicht oder startet nicht

Wenn Ihre HoloLens nicht gestartet wird:

- Wenn die LEDs neben dem Netzschalter nicht aufleuchten oder nur eine LED kurz blinkt, müssen Sie Möglicherweise müssen Sie [Ihre HoloLens aufladen.](hololens2-charging.md#charging-the-device)
- Wenn die LEDs beim Drücken des Netzschalters aufleuchten, aber auf den Bildschirmen nichts angezeigt wird, setzen Sie [das Gerät hart zurück.](hololens-recovery.md#hard-reset-procedure)

Wenn Ihre HoloLens eingefroren wird oder nicht mehr reagiert:

- Schalten Sie Ihre HoloLens aus, indem Sie auf den Netzschalter klicken, bis sich alle fünf LEDs selbst ausschalten, oder 15 Sekunden lang, wenn die LEDs nicht reagieren. Um Ihre HoloLens zu starten, drücken Sie erneut den Netzschalter.

Wenn diese Schritte nicht funktionieren, können Sie versuchen, Ihr HoloLens 2 Gerät oder [HoloLens-Gerät (1. Generation)](hololens1-recovery.md) [wiederherzustellen.](hololens-recovery.md)

[Zurück zur Liste](#list)

## <a name="low-disk-space-error"></a>Fehler "Niedriger Speicherplatz"

Sie müssen Speicherplatz freigeben, indem Sie eine oder mehrere der folgenden Schritte ausführen:

- Löschen Sie einige nicht verwendeten Leerzeichen. Wechseln Sie zu **Einstellungen**  >  **Für**  >  **Systemplätze,** wählen Sie ein Leerzeichen aus, das Sie nicht mehr benötigen, und wählen Sie dann **Entfernen** aus.
- Entfernen Sie einige der Hologramme, die Sie platziert haben.
- Löschen Sie einige Bilder und Videos aus der Photos-App.
- Deinstallieren Sie einige Apps von HoloLens. Tippen **Sie in** der Liste Alle Apps auf die App, die Sie deinstallieren möchten, und halten Sie sie fest, und wählen Sie dann Deinstallieren **aus.**

[Zurück zur Liste](#list)

## <a name="calibration-fails"></a>Kalibrierung schlägt fehl

Die Kalibrierung sollte für die meisten Personen funktionieren, aber es gibt Fälle, in denen die Kalibrierung fehlschlägt.
  
Mögliche Gründe für kalibrierungsfehler sind:

- Ablenkung und Nichtfolge der Kalibrierungsziele
- Fehlerhaftes oder zerlegtes Gerätevisor oder Gerätevisor nicht ordnungsgemäß positioniert
- Dirty oder Scratched Glasses
- Bestimmte Arten von Kontaktobjektiven und Brillen (farbige Kontaktobjektive, einige torische Kontaktobjektive, IR-Blockierende Brillen, einige hohe Brillen, Sonnenbrillen usw.)
- Stärker ausgesprochenes Makeup und einige Schrägstricherweiterungen
- Beren oder brillendicke Frames, wenn sie das Gerät daran hindern, Ihre Augen zu sehen
- Bestimmte Augengeschäderung, Augenbedingungen oder Augenschübe wie schmale Augen, lange Schrägstriche, Amblytropie, Nystagmus, einige Fälle von LASIK oder andere Augenoperationen

Wenn die Kalibrierung nicht erfolgreich ist, versuchen Sie Es:

- Bereinigen des Gerätevisors
- Bereinigen der Brille
- Verschieben des Gerätevisors so nah wie möglich an Ihre Augen
- Verschieben von Objekten aus dem Visier (z. B. Kopf)
- Einschalten eines Lichts in Ihrem Raum oder Auslagern des direkten Strahls

Wenn Sie alle Richtlinien befolgt haben und die Kalibrierung weiterhin fehlschlägt, können Sie die Kalibrierungsaufforderung unter Einstellungen deaktivieren. Teilen Sie uns dies auch mit, indem Sie uns Feedback in [Feedback-Hub](hololens-feedback.md)senden.

Sehen Sie sich auch verwandte Informationen zur Problembehandlung für [Bildfarbe oder Helligkeit an.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Das Festlegen von IPD gilt nicht für HoloLens 2, da die Augenpositionen vom System berechnet werden. 

[Zurück zur Liste](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Kann sich nicht anmelden, weil meine HoloLens zuvor für eine andere Person eingerichtet wurde

Sie können [das Gerät in den **Flashmodus** versetzen und Advanced Recovery Companion verwenden,](hololens-recovery.md#clean-reflash-the-device) um das Gerät wiederherzustellen.

[Zurück zur Liste](#list)


## <a name="unity-isnt-working"></a>Unity funktioniert nicht

- Informationen zur neuesten Version von Unity, die für die HoloLens-Entwicklung empfohlen wird, finden Sie unter Installieren der [Tools.](/windows/mixed-reality/install-the-tools)
- Bekannte Probleme mit der Unity HoloLens Technical Preview sind in den [HoloLens Unity-Foren](https://forum.unity3d.com/threads/known-issues.394627/)dokumentiert.

[Zurück zur Liste](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows-Geräteportal funktioniert nicht ordnungsgemäß

- Die Livevorschaufunktion in Mixed Reality Aufzeichnung kann einige Sekunden Wartezeit aufweisen.

- Auf der Seite Virtuelle Eingabe sind die Steuerelemente Gesten und Bildlauf im Abschnitt Virtuelle Gesten nicht funktionsfähig. Deren Verwendung hat keine Auswirkungen. Die virtuelle Tastatur auf der virtuellen Eingabeseite funktioniert ordnungsgemäß.

- Nachdem Sie den Entwicklermodus in den Einstellungen aktiviert haben, kann es einige Sekunden dauern, bis der Schalter aktiviert ist, Geräteportal aktiviert ist.

[Zurück zur Liste](#list)

## <a name="emulator"></a>Emulator
### <a name="the-hololens-emulator-isnt-working"></a>Der HoloLens-Emulator funktioniert nicht

Informationen zum HoloLens-Emulator finden Sie in unserer Entwicklerdokumentation.  Erfahren Sie mehr über [die Problembehandlung für den HoloLens-Emulator.](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)


- Nicht alle Apps im Microsoft Store sind mit dem Emulator kompatibel. Beispielsweise können Young Conker und Fragmente im Emulator nicht wiedergegeben werden.
- Sie können die PC-Webcam nicht im Emulator verwenden.
- Die Livevorschaufunktion des Windows-Geräteportal funktioniert nicht mit dem Emulator. Sie können weiterhin Mixed Reality Videos und Bilder erfassen.

[Zurück zur Liste](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a>Ich kann die Tastatur nicht finden oder verwenden, um im HoloLens 2 Emulator einzugeben.

*Bald verfügbar*

[Zurück zur Liste](#list)

## <a name="voice-commands-arent-working"></a>Sprachbefehle funktionieren nicht

Wenn Cortana nicht auf Ihre Sprachbefehle reagiert, stellen Sie sicher, dass Cortana aktiviert ist. **Wählen** Sie in der Liste Alle Apps Cortana Menu Notebook Settings  >  **(Cortana-Menünotebookeinstellungen)**  >    >   aus, um Änderungen vorzunehmen. Weitere Informationen dazu, was Sie sagen können, finden Sie unter [Verwenden Ihrer Stimme mit HoloLens.](hololens-cortana.md)

Auf HoloLens (1. Generation) ist die integrierte Spracherkennung nicht konfigurierbar. Sie ist immer aktiviert. Auf HoloLens 2 können Sie auswählen, ob die Spracherkennung und Cortana während der Geräteeinrichtung eingeschaltet werden sollen.

Wenn Ihr HoloLens 2 nicht auf Ihre Stimme reagiert, stellen Sie sicher, dass die Spracherkennung aktiviert ist. Wechseln **Sie** zu  >    >  **Einstellungen datenschutz**  >  **speech** starten, und aktivieren Sie **die Spracherkennung.**

[Zurück zur Liste](#list)

## <a name="hand-input-isnt-working"></a>Handeingabe funktioniert nicht

Um sicherzustellen, dass HoloLens Ihre Hände sehen kann, müssen Sie sie im Gestenrahmen aufbewahren.  Die Mixed Reality Home bietet Feedback, das Sie darüber informiert, wann Ihre Hände nachverfolgt werden.  Das Feedback unterscheidet sich bei verschiedenen Versionen von HoloLens:
- Auf HoloLens (1. Generation) ändert sich der Anviertcursor von einem Punkt in einen Ring.
- Auf HoloLens 2 wird ein Fingerspitzencursor angezeigt, wenn sich die Hand in der Nähe eines Schiefers befindet, und ein Handstrahl wird angezeigt, wenn die Schieferzeichen weiter entfernt sind.

Viele immersive Apps folgen Eingabemustern, die Mixed Reality Home ähneln.  Erfahren Sie mehr über die Verwendung von Handeingaben in [HoloLens (1. Generation)](hololens1-basic-usage.md#use-hololens-with-your-hands) und [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Beachten Sie, dass einige Handlangentypen bei der Handnachverfolgung nicht funktionieren, wenn Sie Hand tragen.  Ein häufiges Beispiel sind schwarze Handbänder, die dazu tendieren, Licht zu absorbieren und nicht von der Tiefenkamera aufgenommen werden.  Wenn Es bei Ihrer Arbeit um Handbänder geht, empfiehlt es sich, eine hellere Farbe wie Blau oder Grau zu versuchen.  Ein weiteres Beispiel sind große baggy-Handstücke, die dazu tendieren, die Form Ihrer Hand zu verbergen. Wir empfehlen die Verwendung von Handlangen, die so formanpassend wie möglich sind, um optimale Ergebnisse zu erzielen.

Wenn Ihr Visier Fingerabdrücke oder Smudges hat, verwenden Sie die Microfiber-Bereinigungsanlage, die mit der HoloLens stammt, um Ihr Visier sauber zu bereinigen.

[Zurück zur Liste](#list)

## <a name="cant-connect-to-wi-fi"></a>Verbindung mit Wi-Fi kann nicht hergestellt werden

Hier sind einige Dinge, die Sie ausprobieren sollten, wenn Sie Ihre HoloLens nicht mit einem Wi-Fi Netzwerk verbinden können:

- Stellen Sie sicher, dass Wi-Fi aktiviert ist. Um dies zu überprüfen, verwenden Sie die Startgeste, und wählen Sie dann **Einstellungen**  >  **&amp; Netzwerkinternet-WLAN**  >  aus. Wenn Wi-Fi eingeschaltet ist, versuchen Sie, es zu deaktivieren und dann erneut zu aktivieren.
- Nähern Sie sich dem Router oder Zugriffspunkt an.
- Starten Sie Ihren Wi-Fi Router neu, und starten Sie dann [HoloLens neu.](hololens-recovery.md) Try connecting again.
- Wenn keines dieser Dinge funktioniert, überprüfen Sie, ob Ihr Router die neueste Firmware verwendet. Sie finden diese Informationen auf der Herstellerwebsite.

[Zurück zur Liste](#list)
## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth-Geräte werden nicht gekoppelt

Wenn Beim [Koppeln eines Bluetooth-Geräts](hololens-connect-devices.md)Probleme auftreten, versuchen Sie Folgendes:

- Wechseln **Sie** zu Einstellungen  >  **Geräte**, und stellen Sie sicher, dass Bluetooth aktiviert ist. Wenn dies der Grund ist, deaktivieren Sie sie, und aktivieren Sie sie erneut.
- Stellen Sie sicher, dass Ihr Bluetooth-Gerät vollständig in Rechnung gestellt wird oder über neue Akkus verfügt.
- Wenn Sie weiterhin keine Verbindung herstellen können, [starten Sie die HoloLens neu.](hololens-recovery.md)

[Zurück zur Liste](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C-Mikrofon funktioniert nicht
Beachten Sie, dass einige USB-C-Mikrofone sich fälschlicherweise sowohl als *Mikrofon* als auch als Lautsprecher melden. Dies ist ein Problem mit dem Mikrofon und nicht mit HoloLens. Wenn Sie eines dieser Mikrofone an HoloLens anschließen, geht möglicherweise der Sound verloren. Glücklicherweise gibt es eine einfache Lösung.  

Legen Sie unter **Systemsound** für Einstellungen  ->    ->  die integrierten Lautsprecher **(Analog Feature Audio Driver)** explizit als **Standardgerät** fest. HoloLens sollte sich diese Einstellung auch dann merken, wenn das Mikrofon entfernt und später erneut verbunden wird.

![Problembehandlung bei USB-C-Mikrofonen](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Geräte, die unter Einstellungen als verfügbar aufgeführt sind, funktionieren nicht

HoloLens (1. Generation) unterstützt keine Bluetooth-Audioprofile. Bluetooth-Audiogeräte wie Lautsprecher und Headsets werden möglicherweise in holoLens-Einstellungen als verfügbar angezeigt, werden jedoch nicht unterstützt.

HoloLens 2 unterstützt das Bluetooth A2DP-Audioprofil für die Stereowiedergabe. Das Bluetooth Hands Free-Profil, das die Mikrofonerfassung von einem Bluetooth-Peripheriegerät ermöglicht, wird auf HoloLens 2 nicht unterstützt.

Wenn Sie Probleme bei der Verwendung eines Bluetooth-Geräts haben, stellen Sie sicher, dass es sich um ein unterstütztes Gerät handelt. Folgende Geräte werden unterstützt:

- Englischsprachige QWERTY-Bluetooth-Tastaturen (Sie können diese überall dort verwenden, wo Sie die holografische Tastatur verwenden).
- Bluetooth-Maus.
- Der [HoloLens-Klicker](hololens1-clicker.md).

Sie können andere Bluetooth HID- und GATT-Geräte mit Ihrer HoloLens koppeln. Möglicherweise müssen Sie jedoch entsprechende Begleit-Apps von Microsoft Store installieren, um die Geräte tatsächlich zu verwenden.

[Zurück zur Liste](#list)
