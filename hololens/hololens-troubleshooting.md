---
title: HoloLens Problembehandlung für Geräte
description: Bleiben Sie auf dem laufenden über die gängigsten Lösungen, um HoloLens und Problembehandlungstechniken zu beheben.
author: evmill
ms.author: v-evmill
ms.date: 10/7/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: Probleme, Fehler, Problembehandlung, Fehlerbehebung, Hilfe, Support, HoloLens, Emulator
ms.openlocfilehash: ceb6f2670b15f46d17a0cb36f6602ae3d4e3ec1d
ms.sourcegitcommit: 8a3f925d2bda13c095b35f14d80afdd876aa859c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2021
ms.locfileid: "129800537"
---
# <a name="device-troubleshooting"></a>Problembehandlung für Geräte

In diesem Artikel wird beschrieben, wie Sie mehrere häufige Probleme HoloLens beheben.

>[!IMPORTANT]
> Bevor Sie mit der Problembehandlung beginnen, stellen Sie sicher, dass Ihr Gerät nach Möglichkeit auf **20-40 %** der Akkukapazität aufgeladen ist. Die [Akkukontrollleuchten](hololens2-setup.md#lights-that-indicate-the-battery-level) unter dem Netzschalter sind eine schnelle Möglichkeit, die Akkukapazität zu überprüfen, ohne sich beim Gerät anzumelden.

<a id="list"></a>

**Bekannte Probleme**
- [Jedes Mal, wenn die Stromversorgung auf 18 Prozent steigt, wird das Gerät plötzlich automatisch heruntergefahren.](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDrive UWP-App funktioniert nicht für Azure AD Benutzer](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [Remote Assist Video friert nach 20 Minuten ein](#remote-assist-video-freezes-after-20-minutes)
- [Bei der automatischen Anmeldung wird nach der Anmeldung gefragt.](#auto-login-asks-for-log-in)
- [Microsoft Edge kann nicht gestartet werden](#microsoft-edge-fails-to-launch)
- [Tastatur wechselt nicht zu Sonderzeichen](#keyboard-doesnt-switch-to-special-characters)
- [Beim Herunterladen gesperrter Dateien wird kein Fehler angezeigt.](#downloading-locked-files-doesnt-error)
- [Geräteportal dateiupload/download times out](#device-portal-file-uploaddownload-times-out)
- [Blauer Bildschirm nach dem Entrollen der Insider-Vorschau auf einem Gerät mit einem Insider-Build](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive werden bilder nicht automatisch hochgeladen.](#onedrive-doesnt-automatically-upload-pictures)

**Allgemein**
- [HoloLens reagiert nicht oder startet nicht](#hololens-is-unresponsive-or-wont-start)
- [Fehler "Wenig Speicherplatz"](#low-disk-space-error)
- [Kalibrierung schlägt fehl](#calibration-fails)
- [Kann sich nicht anmelden, da mein HoloLens zuvor für eine andere Person eingerichtet wurde](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity funktioniert nicht](#unity-isnt-working)
- [Windows Geräteportal funktioniert nicht ordnungsgemäß](#windows-device-portal-isnt-working-correctly)
- [Die HoloLens Emulator funktioniert nicht](#the-hololens-emulator-isnt-working)

**Eingabe**
- [Sprachbefehle funktionieren nicht](#voice-commands-arent-working)
- [Handeingabe funktioniert nicht](#hand-input-isnt-working)

**Konnektivität**
- [Verbindung mit WLAN kann nicht hergestellt werden](#cant-connect-to-wi-fi)

**Externe Geräte** 
- [Bluetooth Geräte werden nicht gekoppelt](#bluetooth-devices-arent-pairing)
- [USB-C-Mikrofon funktioniert nicht](#usb-c-microphone-isnt-working)
- [Geräte, die als verfügbar in aufgeführt Einstellungen funktionieren nicht](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>Jedes Mal, wenn die Stromversorgung auf 18 Prozent steigt, wird das Gerät plötzlich automatisch heruntergefahren.

Es gibt ein bekanntes Problem, bei dem das Gerät unerwartet heruntergefahren wird, wenn es eine Akkukapazität von 18 % erreicht. Dies ist ein Softwareproblem, kein Hardware- oder Akkuproblem. Tauschen Sie daher keine Geräte dafür aus. Wenn Sie nicht sicher sind, ob Ihr Problem diesem Fehler entspricht, gehen Sie wie hier vor:

1. Stellen Sie sicher, dass optionale Diagnosen auf Ihren Geräten aktiviert sind.
1. Reproduzieren des Problems
1. Übermitteln eines [Feedback-Hub](hololens-feedback.md) Problems
1. Geben Sie die URL für das Feedbackproblem an.
1. [An Support wenden](https://aka.ms/hololenssupport)

[Zurück zur Liste](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive UWP-App funktioniert nicht für Azure AD Benutzer

Wenn Sie OneDrive For Business mit Ihrem Azure AD-Konto verwenden, ist möglicherweise ein Fehler aufgetreten, wenn Sie sich bei Ihrer Posteingangs-app OneDrive haben. Die Möglichkeit, sich nicht bei der OneDrive-App anmelden, wirkt sich nicht auf automatische Uploads von Bildern und Videos aus, die von der Kamera-App erfasst werden. Ihre Dateien können weiterhin gespeichert und über den cloudbasierten OneDrive for Business zugegriffen werden. Die OneDrive und HoloLens arbeiten an dem Problem.

### <a name="workarounds"></a>Problemumgehungen

Voraussetzung: Kunden können die Microsoft Edge und das Betriebssystem des Geräts wird auf einen Windows Holographic,21H1-Build oder neuer aktualisiert.

Wenn dieses Problem vor liegt, versuchen Sie es mit einem der folgenden:

- Benutzer können direkt über OneDrive for Business Microsoft Edge zugreifen und über ihren Browser mit ihren Dateien auf der Website interagieren.
- Benutzer können die OneDrive PWA-App installieren HoloLens indem sie sie von Microsoft Edge. Dadurch können Benutzer Dateien auf dem Gerät erneut anzeigen und verwalten. Lesen Und befolgen Sie diese [Anweisungen zum Installieren der OneDrive PWA-App auf Ihrem HoloLens.](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[Zurück zur Liste](#list)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Remote Assist Video friert nach 20 Minuten ein

> [!NOTE]
> Es gibt eine neuere Version von Remote Assist, die eine Lösung für dieses Problem bietet. Aktualisieren [Sie Remote Assist](holographic-store-apps.md#update-apps) auf die neueste Version, um dieses Problem zu vermeiden.

> [!NOTE]
> Aufgrund des Schweregrads dieses bekannten Problems wurde die Verfügbarkeit von Holographic, Version 21H1, Windows vorübergehend angehalten. Der 21H1-Build ist jetzt wieder verfügbar, sodass Geräte möglicherweise erneut auf den neuesten 21H1-Build aktualisiert werden.

Bei der neuesten Version [von Windows Holographic, Version 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)haben einige Benutzer von Remote Assist video freezing during calls over 20 minutes (Video einfrieren während der Anrufe über 20 Minuten) erfahren. Dies ist ein **bekanntes Problem.**

### <a name="workarounds"></a>Problemumgehungen

Wenn Sie den Build nicht auf Remote Assist neueren Build aktualisieren können, führen Sie die folgenden Schritte aus.

#### <a name="restart-in-between-calls"></a>Neustart zwischen Aufrufen

Wenn Ihre Aufrufe länger als 20 Minuten dauern und dieses Problem vor sich geht, versuchen Sie, Ihr Gerät neu zu starten. Wenn Sie Ihr Gerät zwischen Remote Assist aufrufen, wird das Gerät aktualisiert und wieder in einen guten Zustand zurückverstanden.

Um ein Gerät auf Windows Holographic schnell neu zu starten, öffnen Sie Version [21H1](hololens-release-notes.md#windows-holographic-version-21h1) das Startmenü, wählen Sie das Benutzersymbol aus, und wählen Sie dann **Neu starten aus.**

[Zurück zur Liste](#list)

## <a name="auto-login-asks-for-log-in"></a>Bei der automatischen Anmeldung wird nach der Anmeldung gefragt.

Ein HoloLens 2-Gerät kann so konfiguriert werden, dass es sich automatisch über **Einstellungen**  ->  **Accounts**  ->  **Sign-in Options** ->  anmeldet und unter Erforderlich den Wert auf Never **(Nie) festlegen.** Einige Benutzer müssen sich möglicherweise erneut beim Gerät anmelden, wenn sie ein Gerät mit einem wesentlich großen Update aktualisieren, z. B. einem Featureupdate. Dies ist ein **bekanntes Problem.**

Beispiel für den Fall, dass dies auftreten kann:

- Aktualisieren eines Geräts von Windows Holographic, Version 2004 (Build 19041.xxxx) auf Windows Holographic, Version 21H1 (Build 20346.xxxx)
- Aktualisieren eines Geräts für ein umfangreiches Update auf demselben Hauptversions-Build, z. B. Windows Holographic, Version 2004, auf Windows Holographic, Version 20H2
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

Einige Kunden haben ein Problem gemeldet, bei dem Microsoft Edge nicht gestartet werden kann. Für diese Kunden bleibt das Problem bei einem Neustart bestehen und wird nicht mit Windows oder Anwendungsupdates behoben. Wenn dieses Problem besteht und Sie bestätigt haben, dass [Windows](hololens-updates.md#manually-check-for-updates)auf dem neuesten Stand ist, melden Sie einen Fehler aus der [Feedback-Hub-App](hololens-feedback.md) mit der folgenden Kategorie und Unterkategorie: Installieren und Aktualisieren von > Herunterladen, Installieren und Konfigurieren von Windows Update.

Es gibt keine bekannten Problemumgehungen, da wir das Problem bisher nicht beheben konnten. Das Melden eines Fehlers über Feedback-Hub hilft uns bei der Untersuchung! Dies ist ein **bekanntes Problem.**

[Zurück zur Liste](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Tastatur wechselt nicht zu Sonderzeichen

Während der OOBE liegt ein Problem vor, bei dem der Benutzer, nachdem er ein Arbeits-, Schul- oder Schulkonto ausgewählt und sein Kennwort eingegeben hat, zu den Sonderzeichen auf der Tastatur wechseln möchte, indem er auf die Schaltfläche &123 tippt, sich nicht in Sonderzeichen ändert. Dies ist ein **bekanntes Problem.**

Work-arounds:

- Schließen Sie die Tastatur, und öffnen Sie sie erneut, indem Sie auf das Textfeld tippen.
- Geben Sie ihr Kennwort falsch ein. Wenn die Tastatur beim nächsten Mal neu gestartet wird, funktioniert sie wie erwartet.
- Webauthentifizierung: Schließen Sie die Tastatur, und wählen **Sie Von einem anderen Gerät aus anmelden aus.**
- Wenn nur Zahlen eingegeben werden, kann ein Benutzer bestimmte Tasten drücken und gedrückt halten, um ein erweitertes Menü zu öffnen.
- Verwenden einer USB-Tastatur.

Dies wirkt sich nicht auf:

- Benutzer, die sich für die Verwendung eines persönlichen Kontos entscheiden.

[Zurück zur Liste](#list)

## <a name="downloading-locked-files-doesnt-error"></a>Beim Herunterladen gesperrter Dateien tritt kein Fehler auf.

> [!NOTE]
> Dies ist ein **bekanntes Problem,** das in [Windows Holographic, Version 21H1 – Juli 2021 Update](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)behoben wurde.

In vorherigen Builds von Windows Holographic war das Ergebnis beim Herunterladen einer gesperrten Datei eine HTTP-Fehlerseite. Im Windows Holographic-Update, Version 21H1, führt der Versuch, eine gesperrte Datei herunterzuladen, dazu, dass nichts sichtbar ist– die Datei wird nicht heruntergeladen, und es tritt kein Fehler auf.

[Zurück zur Liste](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Geräteportal Dateiupload-/Download-Times out
> [!NOTE]
> Dies ist ein **bekanntes Problem,** das in [Windows Holographic, Version 21H1 – Juli 2021 Update](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)behoben wurde. Wenn Sie die SSL-Verbindung zuvor als Teil der Problemumgehung deaktiviert haben, wird dringend empfohlen, sie erneut zu aktivieren.

Einige Kunden haben festgestellt, dass beim Versuch, Dateien hoch- oder herunterzuladen, der Vorgang möglicherweise hängt und dann ein Time out oder nie abgeschlossen wird. Dies ist vom[bekannten Problem "Datei gesperrt"](#downloading-locked-files-doesnt-error) getrennt. Dies betrifft Windows Holographic-Builds der Versionen 2004, 20H2 und 21H1. Das Problem wurde aufgrund eines Fehlers bei der Verarbeitung bestimmter Anforderungen durch Geräteportal verursacht und tritt am häufigsten auf, wenn https verwendet wird. Dies ist die Standardeinstellung.

### <a name="workaround"></a>Problemumgehung

Diese Problemumgehung, die gleichermaßen für Wi-Fi und UsbNcm gilt, besteht darin, die Option "erforderlich" unter "SSL-Verbindung" zu deaktivieren. Navigieren Sie hierzu zu **Geräteportal, System**, und wählen Sie die Seite **Einstellungen aus.** Suchen Sie im Abschnitt **Gerätesicherheit** nach **SSL-Verbindung,** und deaktivieren Sie die Option **Erforderlich.**

Der Benutzer sollte dann zu http:// wechseln, nicht https:// (IP-Adresse) und Funktionen wie Dateiupload und -download funktionieren.

[Zurück zur Liste](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Blue screen after unenrolling from Insider preview on a device flashed with an Insider build (Blauer Bildschirm nach dem Aufheben der Registrierung bei der Insider-Vorschau auf einem Gerät, das mit einem Insider-Build blinkt)

Dies ist ein Problem, das sich auf Benutzer auswirkt, die sich in einem Insider-Vorschaubuild befanden, ihre HoloLens 2 mit einem neuen Insider Preview-Build umgestrichen und dann die Registrierung für das Insider-Programm aufgehoben haben. Dies ist ein **bekanntes Problem.**

Dies wirkt sich nicht auf:

- Benutzer, die nicht bei Windows Insider registriert sind
- Insider:
    - Wenn ein Gerät registriert wurde, seit Insider-Builds Version 18362.x waren
    - Wenn sie einen von Insider signierten 19041.x-Build flashten, bleiben Sie für das Insider-Programm registriert.

Umgehen:

- Vermeiden Sie das Problem.
    - Flashen sie einen Nicht-Insider-Build. Eines der regelmäßigen monatlichen Updates.
    - Bleiben Sie auf Insider Preview
- Reflash the device (Reflash des Geräts)

    1. Versetzen Sie die HoloLens 2 manuell in den [Blinkmodus,](hololens-recovery.md) indem Sie vollständig herunterschalten, ohne eine Verbindung herzustellen. Tippen Sie dann bei gedrückter Lautstärke auf die Netzschaltfläche.

    1. Verbinden zum PC, und öffnen Sie Advanced Recovery Companion.

    1. Flashen Sie die HoloLens 2 auf den Standardbuild.

[Zurück zur Liste](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive lädt Bilder nicht automatisch hoch.

Die OneDrive-App für HoloLens unterstützt keinen automatischen Kameraupload für Arbeits- oder Schulkonten. Dies ist ein **bekanntes Problem.**

Problemumgehungen:

- Wenn dies für Ihr Unternehmen sinnvoll ist, wird der automatische Kameraupload für Microsoft-Kundenkonten unterstützt. Sie können sich zusätzlich zu Ihrem Arbeits- oder Schulkonto bei Ihrem Microsoft-Konto anmelden (die OneDrive-App unterstützt die duale Anmeldung). In Ihrem Microsoft-Konto-Profil in OneDrive können Sie den automatischen Kamerarollup im Hintergrund aktivieren.

- Wenn Sie einen Consumer Microsoft-Konto nicht sicher zum automatischen Hochladen Ihrer Fotos verwenden können, können Sie Fotos manuell über die OneDrive-App in Ihr Arbeits- oder Schulkonto hochladen. Stellen Sie hierzu sicher, dass Sie bei Ihrem Arbeits- oder Schulkonto in der OneDrive-App angemeldet sind. Wählen Sie die **+** Schaltfläche und dann **Hochladen** aus. Suchen Sie die Fotos oder Videos, die Sie hochladen möchten, indem Sie zu **Bilder > Kameraroll navigieren.** Wählen Sie die Fotos oder Videos aus, die Sie hochladen möchten, und klicken Sie dann auf die Schaltfläche **Öffnen.**

[Zurück zur Liste](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens reagiert nicht oder wird nicht gestartet

Wenn Ihre HoloLens nicht gestartet wird:

- Wenn die LEDs neben dem Netzschalter nicht aufleuchten oder nur eine LED kurz blinkt, müssen Sie möglicherweise [Ihre HoloLens aufladen.](hololens2-charging.md#charging-the-device)
- Wenn die LEDs beim Drücken des Netzschalters aufleuchten, aber auf den Bildschirmen nichts angezeigt wird, setzen Sie [das Gerät hart zurück.](hololens-recovery.md#hard-reset-procedure)

Wenn Ihre HoloLens eingefroren wird oder nicht mehr reagiert:

- Schalten Sie Ihre HoloLens aus, indem Sie auf den Netzschalter klicken, bis sich alle fünf LEDs selbst ausschalten, oder 15 Sekunden lang, wenn die LEDs nicht reagieren. Um Ihre HoloLens zu starten, drücken Sie erneut den Netzschalter.

Wenn diese Schritte nicht funktionieren, können Sie versuchen, Ihr HoloLens 2 Gerät oder [HoloLens Gerät (1. Generation)](hololens1-recovery.md) [wiederherzustellen.](hololens-recovery.md)

[Zurück zur Liste](#list)

## <a name="low-disk-space-error"></a>Fehler "Wenig Speicherplatz"

Sie müssen Speicherplatz freigeben, indem Sie eine oder mehrere der folgenden Schritte ausführen:

- Löschen Sie einige nicht verwendeten Leerzeichen. Wechseln Sie zu **Einstellungen**  >    >  **Systemräume,** wählen Sie einen Nicht mehr benötigten Bereich aus, und wählen Sie dann **Entfernen** aus.
- Entfernen Sie einige der Hologramme, die Sie platziert haben.
- Löschen Sie einige Bilder und Videos aus der Fotos-App.
- Deinstallieren Sie einige Apps aus Ihrer HoloLens. Tippen Sie in der **Liste Alle Apps** auf die App, die Sie deinstallieren möchten, und halten Sie sie fest, und wählen Sie dann **Deinstallieren aus.**

[Zurück zur Liste](#list)

## <a name="calibration-fails"></a>Kalibrierung schlägt fehl

Die Kalibrierung sollte für die meisten Personen funktionieren, aber es gibt Fälle, in denen die Kalibrierung fehlschlägt.
  
Mögliche Gründe für kalibrierungsfehler sind:

- Ablenkung und Nichtfolge der Kalibrierungsziele
- Fehlerhaftes oder zerlegtes Gerätevisor oder Gerätevisor nicht ordnungsgemäß positioniert
- Dirty oder Scratched Glasses
- Bestimmte Arten von Kontaktobjektiven und Brillen (farbige Kontaktobjektive, einige toristische Kontaktobjektive, IR-blockierende Brillen, einige hohe Brillen, Sonnenbrillen usw.)
- Stärker ausgesprochenes Makeup und einige Schrägstricherweiterungen
- Beren oder brillendicke Frames, wenn sie das Gerät daran hindern, Ihre Augen zu sehen
- Bestimmte Augengeschäderung, Augenzustände oder Augenverschiebungen wie schmale Augen, lange Schrägstriche, Amblyz, Nystagmus, einige Fälle von LASIK oder andere Augenoperationen

Wenn die Kalibrierung nicht erfolgreich ist, versuchen Sie:

- Bereinigen des Gerätevisors
- Bereinigen der Brille
- Verschieben des Gerätevisors so nah wie möglich an Ihre Augen
- Verschieben von Objekten aus dem Visier (z. B. Kopf)
- Einschalten eines Lichts in Ihrem Raum oder Wegbewegen von direktem Strahl

Wenn Sie alle Richtlinien befolgt haben und die Kalibrierung weiterhin fehlschlägt, können Sie die Kalibrierungsaufforderung in Einstellungen deaktivieren. Teilen Sie uns dies auch mit, indem Sie uns Feedback in [Feedback-Hub](hololens-feedback.md)senden.

Sehen Sie sich auch verwandte Informationen zur Problembehandlung bei [Bildfarbe oder Helligkeit an.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Das Festlegen von IPD gilt nicht für HoloLens 2, da die Augenpositionen vom System berechnet werden. 

[Zurück zur Liste](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Kann sich nicht anmelden, da mein HoloLens zuvor für eine andere Person eingerichtet wurde.

Sie können [das Gerät in den **Flashmodus** versetzen und Advanced Recovery Companion verwenden,](hololens-recovery.md#clean-reflash-the-device) um das Gerät wiederherzustellen.

[Zurück zur Liste](#list)


## <a name="unity-isnt-working"></a>Unity funktioniert nicht

- Unter [Installieren der Tools](/windows/mixed-reality/install-the-tools) finden Sie die neueste Version von Unity, die für die Entwicklung HoloLens wird.
- Bekannte Probleme mit unity HoloLens Technical Preview sind in den [Unity-Foren](https://forum.unity3d.com/threads/known-issues.394627/)HoloLens dokumentiert.

[Zurück zur Liste](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Geräteportal funktioniert nicht ordnungsgemäß

- Das LiveVorschaufeature in Mixed Reality erfassung kann einige Sekunden Wartezeit zeigen.

- Auf der Seite Virtuelle Eingabe sind die Steuerelemente Geste und Bildlauf im Abschnitt Virtuelle Gesten nicht funktionsfähig. Ihre Verwendung hat keine Auswirkungen. Die virtuelle Tastatur auf der virtuellen Eingabeseite funktioniert ordnungsgemäß.

- Nach dem Aktivieren des Entwicklermodus in Einstellungen kann es einige Sekunden dauern, bis der Schalter aktiviert Geräteportal ist.

[Zurück zur Liste](#list)

## <a name="the-hololens-emulator-isnt-working"></a>Die HoloLens Emulator funktioniert nicht

Informationen zum HoloLens Emulator finden Sie in unserer Entwicklerdokumentation.  Weitere Informationen zur [Problembehandlung für den HoloLens Emulator finden Sie hier.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)


- Nicht alle Apps in der Microsoft Store sind mit dem Emulator kompatibel. Beispielsweise können Young Conker und Fragmente nicht auf dem Emulator abspielbar sein.
- Sie können die PC-Webcam nicht in der Emulator.
- Das LiveVorschaufeature des Windows Geräteportal funktioniert nicht mit dem Emulator. Sie können weiterhin Mixed Reality Videos und Bilder erfassen.

[Zurück zur Liste](#list)

## <a name="voice-commands-arent-working"></a>Sprachbefehle funktionieren nicht

Wenn Cortana nicht auf Ihre Sprachbefehle reagiert, stellen Sie sicher, Cortana aktiviert ist. Wählen Sie in Alle Apps Liste die Option **Cortana**  >  **Menü**  >  **Notebook**  >  **Einstellungen,** um Änderungen vorzunehmen. Weitere Informationen dazu, was Sie sagen können, finden Sie unter [Verwenden Ihrer Stimme mit HoloLens](hololens-cortana.md).

Auf HoloLens (1. Generation) ist die integrierte Spracherkennung nicht konfigurierbar. Sie ist immer aktiviert. Auf HoloLens 2 können Sie auswählen, ob sie während der Geräteeinrichtung sowohl die Spracherkennung als auch Cortana aktivieren möchten.

Wenn Ihr HoloLens 2 nicht auf Ihre Stimme reagiert, stellen Sie sicher, dass die Spracherkennung aktiviert ist. Wechseln Sie zu **Start**  >  **Einstellungen**  >  **Privacy**  >  **Speech,** und aktivieren Sie **die Spracherkennung.**

[Zurück zur Liste](#list)

## <a name="hand-input-isnt-working"></a>Handeingabe funktioniert nicht

Um sicherzustellen, HoloLens ihre Hände sehen kann, müssen Sie sie im Gestenrahmen halten.  Das Mixed Reality Home bietet Feedback, das Sie darüber informiert, wann Ihre Hände nachverfolgt werden.  Das Feedback ist in verschiedenen Versionen von HoloLens:

- Bei HoloLens (1. Generation) ändert sich der Anvitsor von einem Punkt in einen Ring.
- Auf HoloLens 2 wird ein Fingerspitzencursor angezeigt, wenn sich Ihre Hand in der Nähe einer Tafel befindet, und ein Handstrahl wird angezeigt, wenn slates weiter entfernt sind.

Viele immersive Apps folgen Eingabemustern, die dem Home-Mixed Reality ähneln.  Erfahren Sie mehr über die Verwendung von [Handeingaben für HoloLens (1. Generation)](hololens1-basic-usage.md#use-hololens-with-your-hands) [und HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Wenn Sie Handarbeit tragen, beachten Sie, dass einige Handarbeitsarten nicht mit der Handverfolgung funktionieren.  Ein häufiges Beispiel sind schwarze Bänder, die tendenziell Lichtabbild absorbieren und nicht von der Tiefenkamera aufgenommen werden.  Wenn Ihre Arbeit Handarbeit umfasst, empfehlen wir Ihnen, eine hellere Farbe wie Blau oder Grau zu probieren.  Ein weiteres Beispiel sind große Baggy-Handarbeitshandle, die tendenziell die Form Ihrer Hand verdecken. Wir empfehlen die Verwendung von Handschninnen, die so formanpassung wie möglich sind, um optimale Ergebnisse zu erzielen.

Wenn Ihr Visor Fingerabdrücke oder Smudges auftrat, verwenden Sie die Mikrofiber-Bereinigungsbereinigung, die mit der HoloLens, um ihr Visor lappend zu bereinigen.

[Zurück zur Liste](#list)

## <a name="cant-connect-to-wi-fi"></a>Es kann keine Verbindung mit dem Wi-Fi

Hier sind einige Dinge, die Sie ausprobieren sollten, wenn Sie Ihre HoloLens nicht mit einem WLAN verbinden können:

- Stellen Sie sicher, dass das WLAN aktiviert ist. Um dies zu überprüfen, verwenden Sie die Geste Start, und wählen Einstellungen  >  **&amp; Netzwerk-Internet-WLAN**  >  **aus.** Wenn das WLAN eingeschaltet ist, schalten Sie es aus und dann wieder ein.
- Verringern Sie den Abstand zum Router oder Zugangspunkt.
- Starten Sie ihren Wi-Fi-Router neu, und starten [Sie dann HoloLens.](hololens-recovery.md) Try connecting again.
- Wenn keiner dieser Schritte funktioniert, prüfen Sie, ob Ihr Router die neueste Firmware verwendet. Diese Informationen finden Sie auf der Website des Herstellers.

[Zurück zur Liste](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth Geräte werden nicht gekoppelt

Wenn Sie Probleme beim Koppeln eines Bluetooth [haben,](hololens-connect-devices.md)versuchen Sie Folgendes:

- Wechseln Sie **Einstellungen**  >  **Geräte,** und stellen Sie sicher, Bluetooth aktiviert ist. Wenn dies der Reihe nach der Vorgang ist, deaktivieren Und wieder ein.
- Stellen Sie sicher, Bluetooth Gerät vollständig aufgeladen ist oder über neue Akkus verfügt.
- Wenn Sie immer noch keine Verbindung herstellen können, [starten Sie die HoloLens.](hololens-recovery.md)

[Zurück zur Liste](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C-Mikrofon funktioniert nicht

Beachten Sie, dass einige USB-C-Mikrofone sich fälschlicherweise sowohl als Mikrofon als auch als *Lautsprecher* melden. Dies ist ein Problem mit dem Mikrofon und nicht mit HoloLens. Wenn Sie eines dieser Mikrofone in HoloLens, kann der Sound verloren gehen. Glücklicherweise gibt es eine einfache Lösung.  

Legen **Einstellungen** Systemsound explizit die integrierten Lautsprecher  ->    ->   **(Analog Feature Audio Driver)** als **Standardgerät fest.** HoloLens sollten sich diese Einstellung auch dann merken, wenn das Mikrofon entfernt und später erneut verbunden wird.

![Problembehandlung bei USB-C-Mikrofonen.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Geräte, die als verfügbar in aufgeführt Einstellungen funktionieren nicht

HoloLens (1. Generation) unterstützt keine Bluetooth Audioprofile. Bluetooth Audiogeräte, z. B. Lautsprecher und Headsets, werden möglicherweise in den HoloLens als verfügbar angezeigt, werden aber nicht unterstützt.

HoloLens 2 unterstützt das Bluetooth A2DP-Audioprofil für die Stereowiedergabe. Das Bluetooth Hands Free-Profil, das die Mikrofonerfassung von einem Bluetooth-Peripheriegerät ermöglicht, wird auf der HoloLens 2.

Wenn Sie Probleme bei der Verwendung eines Bluetooth haben, stellen Sie sicher, dass es ein unterstütztes Gerät ist. Folgende Geräte werden unterstützt:

- QWERTY in englischer Sprache Bluetooth Tastaturen (Sie können diese überall dort verwenden, wo Sie die holografische Tastatur verwenden).
- Bluetooth Maus.
- Der [HoloLens klickt.](hololens1-clicker.md)

Sie können andere HID- Bluetooth UND GATT-Geräte mit Ihren geräten HoloLens. Möglicherweise müssen Sie jedoch entsprechende Begleit-Apps von Microsoft Store, um die Geräte tatsächlich zu verwenden.

[Zurück zur Liste](#list)
