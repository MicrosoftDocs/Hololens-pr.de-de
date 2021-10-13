---
title: HoloLens Problembehandlung für Geräte
description: Bleiben Sie auf dem laufenden über die gängigsten Lösungen, HoloLens Geräteprobleme und Problembehandlungstechniken zu beheben.
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
ms.openlocfilehash: afbbc1ab0e018f668381137849738ec7d274fe37
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924381"
---
# <a name="device-troubleshooting"></a>Problembehandlung für Geräte

In diesem Artikel wird beschrieben, wie Sie mehrere häufige Probleme HoloLens beheben.

>[!IMPORTANT]
> Bevor Sie mit der Problembehandlung beginnen, stellen Sie sicher, dass Ihr Gerät nach Möglichkeit auf **20-40 %** der Akkukapazität aufgeladen ist. Die [Akkukontrollleuchten](hololens2-setup.md#lights-that-indicate-the-battery-level) unter dem Netzschalter sind eine schnelle Möglichkeit, die Akkukapazität zu überprüfen, ohne sich beim Gerät anzumelden.

<a id="list"></a>

**Bekannte Probleme**
- [Jedes Mal, wenn die Stromversorgung auf 18 Prozent steigt, wird das Gerät plötzlich automatisch heruntergefahren.](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDrive UWP-App funktioniert nicht für Azure AD Benutzer](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [Warum wird die 0x80180014 Autopilot-100000000000000000000000000](#why-do-i-see-0x80180014-during-autopilot)
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

Wenn Sie OneDrive For Business mit Ihrem Azure AD-Konto verwenden, ist möglicherweise ein Fehler aufgetreten, wenn Sie sich bei Ihrer Posteingangs-App OneDrive haben. Wenn Sie sich nicht bei der OneDrive App anmelden, wirkt sich dies nicht auf automatische Uploads von Bildern und Videos aus, die von der Kamera-App erfasst wurden. Ihre Dateien können weiterhin gespeichert und über den cloudbasierten OneDrive for Business zugegriffen werden. Die OneDrive und HoloLens arbeiten an dem Problem.

### <a name="workarounds"></a>Problemumgehungen

Voraussetzung: Kunden können Microsoft Edge und das Betriebssystem des Geräts wird auf einen Windows Holographic,21H1-Build oder neuer aktualisiert.

Wenn dieses Problem vor liegt, versuchen Sie es mit einem der folgenden:

- Benutzer können direkt über OneDrive For Business Microsoft Edge zugreifen und über ihren Browser mit ihren Dateien auf der Website interagieren.
- Benutzer können die OneDrive PWA-App in HoloLens, indem sie sie von Microsoft Edge. Dadurch können Benutzer Dateien auf dem Gerät erneut anzeigen und verwalten. Lesen Und befolgen Sie diese [Anweisungen zum Installieren der OneDrive PWA-App auf Ihrem HoloLens.](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[Zurück zur Liste](#list)

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>Warum wird die 0x80180014 Autopilot-100000000000000000000000000

Dieser Fehler tritt in der Regel bei der Gerätezurücksetzung und -wiedervernutzung auf, bei der ein HoloLens Gerät Autopilot mindestens einmal durchgegangen ist. Um dieses Problem zu beheben, löschen Sie das Gerät aus [Microsoft Intune](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) und setzen Sie es erneut zurück, um den Autopilot-Flow abschließen zu können.

Weitere Informationen finden Sie auf der [Autopilot-Seite unter Problembehandlungsschritte.](hololens2-autopilot.md#why-do-i-see-0x80180014-during-autopilot)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Remote Assist Video friert nach 20 Minuten ein

> [!NOTE]
> Es gibt eine neuere Version von Remote Assist, die eine Lösung für dieses Problem bietet. Aktualisieren [Sie Remote Assist](holographic-store-apps.md#update-apps) auf die neueste Version, um dieses Problem zu vermeiden.

> [!NOTE]
> Aufgrund des Schweregrads dieses bekannten Problems wurde die Verfügbarkeit von Holographic, Version 21H1, Windows vorübergehend angehalten. Der 21H1-Build ist jetzt wieder verfügbar, sodass Geräte möglicherweise erneut auf den neuesten 21H1-Build aktualisiert werden.

Bei der neuesten Version [von Windows Holographic, Version 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)haben einige Benutzer von Remote Assist video freezing during calls over 20 minutes (Video einfrieren bei Aufrufen über 20 Minuten) erfahren. Dies ist ein **bekanntes Problem.**

### <a name="workarounds"></a>Problemumgehungen

Wenn Sie den Build nicht auf Remote Assist neueren Build aktualisieren können, führen Sie die folgenden Schritte aus.

#### <a name="restart-in-between-calls"></a>Neustart zwischen Aufrufen

Wenn Ihre Aufrufe länger als 20 Minuten dauern und dieses Problem vor sich geht, versuchen Sie, Ihr Gerät neu zu starten. Wenn Sie Ihr Gerät zwischen Remote Assist aufrufen, wird das Gerät aktualisiert und wieder in einen guten Zustand zurückverstanden.

Um ein Gerät in Windows Holographic schnell neu zu starten, öffnen Sie Version [21H1](hololens-release-notes.md#windows-holographic-version-21h1) das Startmenü, wählen Sie das Benutzersymbol aus, und wählen Sie dann **Neu starten aus.**

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
> Dieses Problem wurde ursprünglich mit der Versandversion von Microsoft Edge erstellt. Dieses Problem kann im [](hololens-new-edge.md)neuen -Microsoft Edge. Wenn dies nicht der Dere ist, senden Sie Uns Feedback.

Einige Kunden haben ein Problem gemeldet, bei dem Microsoft Edge nicht gestartet werden kann. Für diese Kunden bleibt das Problem bei einem Neustart bestehen und wird nicht mit Windows oder Anwendungsupdates behoben. Wenn dieses Problem besteht und Sie bestätigt haben, dass [Windows](hololens-updates.md#manually-check-for-updates)auf dem neuesten Stand ist, melden Sie einen Fehler aus der [Feedback-Hub-App](hololens-feedback.md) mit der folgenden Kategorie und Unterkategorie: Installieren und Aktualisieren von > Herunterladen, Installieren und Konfigurieren von Windows Update.

Es gibt keine bekannten Problemumgehungen, da wir das Problem bisher nicht beheben konnten. Das Melden eines Fehlers über Feedback-Hub hilft uns bei der Untersuchung! Dies ist ein **bekanntes Problem.**

[Zurück zur Liste](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Tastatur wechselt nicht zu Sonderzeichen

Während der OOBE liegt ein Problem vor, bei dem sich der Versuch, zu den Sonderzeichen auf der Tastatur zu wechseln, indem er auf die Schaltfläche &123 tippt, nicht in Sonderzeichen ändert, nachdem der Benutzer ein Arbeits-, Schul- oder Schulkonto ausgewählt und sein Kennwort eingegeben hat. Dies ist ein **bekanntes Problem.**

Arbeitsumgefungen:

- Schließen Sie die Tastatur, und öffnen Sie sie erneut, indem Sie auf das Textfeld tippen.
- Geben Sie Ihr Kennwort falsch ein. Wenn die Tastatur das nächste Mal neu gestartet wird, funktioniert sie wie erwartet.
- Webauthentifizierung, schließen Sie die Tastatur, und wählen **Sie Von einem anderen Gerät aus anmelden aus.**
- Wenn nur Zahlen eingeben, kann ein Benutzer bestimmte Tasten drücken und halten, um ein erweitertes Menü zu öffnen.
- Verwenden einer USB-Tastatur.

Dies hat keine Auswirkungen auf:

- Benutzer, die sich für die Verwendung eines persönlichen Kontos entscheiden.

[Zurück zur Liste](#list)

## <a name="downloading-locked-files-doesnt-error"></a>Fehler beim Herunterladen gesperrter Dateien

> [!NOTE]
> Dies ist **ein bekanntes Problem,** das in Windows [Holographic, Version 21H1 bis Juli 2021 Update, behoben wurde.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)

In früheren Builds von Windows Holographic war das Ergebnis beim Versuch, eine gesperrte Datei herunterzuladen, eine HTTP-Fehlerseite. Im Update Windows Holographic, Version 21H1, führt der Versuch, eine gesperrte Datei herunterzuladen, dazu, dass nichts sichtbar ist. Die Datei wird nicht heruntergeladen, und es ist kein Fehler aufgetreten.

[Zurück zur Liste](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Geräteportal dateiupload/download times out
> [!NOTE]
> Dies ist **ein bekanntes Problem,** das in Windows [Holographic, Version 21H1 bis Juli 2021 Update, behoben wurde.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update) Wenn Sie die SSL-Verbindung zuvor im Rahmen der Problemumgehung deaktiviert haben, wird dringend empfohlen, sie erneut zu aktivieren.

Einige Kunden haben festgestellt, dass beim Versuch, Dateien hochzuladen oder herunterzuladen, der Vorgang möglicherweise nicht mehr zu hängen scheint und dann ein Time out auftritt oder nie abgeschlossen wird. Dies ist von[](#downloading-locked-files-doesnt-error) dem bekannten Problem "dateigesperrt" getrennt. Dies wirkt sich auf Windows Holographic, Versionen 2004, 20H2 und 21H1 im Markt aus. Das Problem ist auf einen Fehler bei der Verarbeitung bestimmter Anforderungen durch Geräteportal von verursacht worden und wird am häufigsten bei Verwendung von https (Standardeinstellung) erreicht.

### <a name="workaround"></a>Problemumgehung

Diese Problemumgehung, die gleichermaßen für Wi-Fi und UsbNcm gilt, besteht im Deaktivieren der Option "erforderlich" unter "SSL-Verbindung". Navigieren Sie dazu zu Geräteportal **System,** und wählen Sie die **Seite Einstellungen** aus. Suchen Sie **im Abschnitt Gerätesicherheit** nach **SSL-Verbindung,** und deaktivieren Sie , um Erforderlich **zu deaktivieren.**

Der Benutzer sollte dann zu http:// wechseln, nicht https:// (IP-Adresse) und Features wie das Hochladen und Herunterladen von Dateien funktionieren.

[Zurück zur Liste](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Blauer Bildschirm nach dem Entrollen der Insider-Vorschau auf einem Gerät mit einem Insider-Build

Dieses Problem wirkt sich auf Benutzer aus, die sich in einem Insider Preview-Build befinden, ihre HoloLens 2 mit einem neuen Insider Preview-Build neu auftänden und dann die Registrierung beim Insider-Programm wieder auftänden. Dies ist ein **bekanntes Problem.**

Dies hat keine Auswirkungen auf:

- Benutzer, die nicht bei Windows Insider registriert sind
- Insider:
    - Wenn ein Gerät seit Insider-Builds registriert wurde, war Version 18362.x.
    - Wenn sie einen Insider-signierten 19041.x-Build flashten und beim Insider-Programm registriert bleiben

Umgeknung:

- Vermeiden Sie das Problem.
    - Flash für einen Nicht-Insider-Build. Eines der regelmäßigen monatlichen Updates.
    - Stay on Insider Preview
- Neustarten des Geräts

    1. Stellen Sie [die HoloLens 2 manuell in den Flashmodus,](hololens-recovery.md) indem Sie vollständig heruntergefahren werden, ohne eine Verbindung herzustellen. Tippen Sie dann beim Halten des Volumes auf den Netzschalter.

    1. Verbinden sie auf den PC, und öffnen Sie Advanced Recovery Companion.

    1. Flashen HoloLens 2 zum Standard-Build.

[Zurück zur Liste](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive werden bilder nicht automatisch hochgeladen.

Die OneDrive-App für HoloLens unterstützt keinen automatischen Kameraupload für Arbeits- oder Schulkonten. Dies ist ein **bekanntes Problem.**

Problemumgehungen:

- Wenn dies für Ihr Unternehmen sinnvoll ist, wird der automatische Kameraupload für Microsoft-Kundenkonten unterstützt. Sie können sich zusätzlich zu Ihrem Microsoft-Konto- oder Schulkonto bei Ihrem Konto anmelden (die OneDrive-App unterstützt die duale Anmeldung). In Ihrem Microsoft-Konto-Profil in OneDrive können Sie den automatischen Rollup der Hintergrundkamera aktivieren.

- Wenn Sie einen Consumer-Microsoft-Konto zum automatischen Hochladen Ihrer Fotos nicht sicher verwenden können, können Sie Fotos manuell aus der App in Ihr Arbeits-, Schul- oder OneDrive hochladen. Stellen Sie dazu sicher, dass Sie bei Ihrem Arbeits- oder Schulkonto in der OneDrive sind. Wählen Sie die **+** Schaltfläche und dann **Hochladen.** Suchen Sie die Fotos oder Videos, die Sie hochladen möchten, indem Sie zu Bilder > **Camera Roll navigieren.** Wählen Sie die Fotos oder Videos aus, die Sie hochladen möchten, und klicken Sie dann auf **die Schaltfläche** Öffnen.

[Zurück zur Liste](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens reagiert nicht oder startet nicht

Wenn Ihr HoloLens nicht gestartet wird:

- Wenn die LEDs neben dem Netzschalter nicht aufglühen oder nur eine LED kurz blinkt, müssen Sie möglicherweise Ihre [HoloLens.](hololens2-charging.md#charging-the-device)
- Wenn die LEDs beim Drücken des Netzschalters einglühen, aber auf den Anzeigen nichts angezeigt wird, setzen Sie das Gerät [fest zurück.](hololens-recovery.md#hard-reset-procedure)

Wenn Ihr HoloLens fixiert wird oder nicht mehr reagiert:

- Schalten Sie ihre HoloLens aus, indem Sie den Netzschalter drücken, bis sich alle fünf LEDs selbst ausschalten, oder 15 Sekunden lang, wenn die LEDs nicht reagieren. Drücken Sie zum HoloLens erneut das Netzschalter.

Wenn diese Schritte nicht funktionieren, [](hololens-recovery.md) können Sie versuchen, Ihr HoloLens 2-Gerät oder HoloLens [(1. Generation) wiederhergestellt zu werden.](hololens1-recovery.md)

[Zurück zur Liste](#list)

## <a name="low-disk-space-error"></a>Fehler "Wenig Speicherplatz"

Sie müssen speicherplatzaufbewahren, indem Sie eine oder mehrere der folgenden Schritte tun:

- Löschen Sie einige nicht verwendete Leerzeichen. Wechseln Sie **Einstellungen**  >    >  **Systemräume,** wählen Sie ein Leerzeichen aus, das Sie nicht mehr benötigen, und wählen Sie dann **Entfernen aus.**
- Entfernen Sie einige der Hologramme, die Sie platziert haben.
- Löschen Sie einige Bilder und Videos aus der Fotos App.
- Deinstallieren Sie einige Apps aus HoloLens. Tippen und **Alle Apps** in der Liste Der Benutzer tippen und halten Sie die App, die Sie deinstallieren möchten, und wählen Sie dann **Deinstallieren aus.**

[Zurück zur Liste](#list)

## <a name="calibration-fails"></a>Kalibrierung schlägt fehl

Die Kalibrierung sollte für die meisten Personen funktionieren, aber es gibt Fälle, in denen die Kalibrierung fehlschlägt.
  
Mögliche Gründe für Kalibrierungsfehler:

- Abgelenkung und Nichterkennen der Kalibrierungsziele
- Dirty or scratched device visor or device visor not positioned properly (Nicht ordnungsgemäß positioniertes oder verzerrtes Gerätevisor oder Gerätevisor)
- Dirty oder Scratched Brille
- Bestimmte Arten von Kontaktobjekten und Brillen (farbige Kontaktbrillen, einige Toric-Kontaktbrillen, IR blockierende Brillen, einige Brillen mit hoher Brille, Sonnenbrillen oder ähnliches)
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

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Geräteportal funktioniert nicht ordnungsgemäß

- Das LiveVorschaufeature in Mixed Reality erfassung kann einige Sekunden Wartezeit zeigen.

- Auf der Seite Virtuelle Eingabe sind die Steuerelemente Geste und Bildlauf im Abschnitt Virtuelle Gesten nicht funktionsfähig. Ihre Verwendung hat keine Auswirkungen. Die virtuelle Tastatur auf der virtuellen Eingabeseite funktioniert ordnungsgemäß.

- Nachdem Sie den Entwicklermodus in Einstellungen aktiviert haben, kann es einige Sekunden dauern, bis der Schalter aktiviert Geräteportal ist.

[Zurück zur Liste](#list)

## <a name="the-hololens-emulator-isnt-working"></a>Die HoloLens Emulator funktioniert nicht

Informationen zum HoloLens Emulator finden Sie in unserer Entwicklerdokumentation.  Weitere Informationen zur [Problembehandlung für den HoloLens Emulator finden Sie hier.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)


- Nicht alle Apps in der Microsoft Store sind mit dem Emulator kompatibel. Beispielsweise können Young Conker und Fragmente nicht auf dem Emulator abspielbar sein.
- Sie können die PC-Webcam nicht in der Emulator.
- Das LiveVorschaufeature des Windows Geräteportal funktioniert nicht mit dem Emulator. Sie können weiterhin Mixed Reality Videos und Bilder erfassen.

[Zurück zur Liste](#list)

## <a name="voice-commands-arent-working"></a>Sprachbefehle funktionieren nicht

Wenn Cortana nicht auf Ihre Sprachbefehle reagiert, stellen Sie sicher, Cortana aktiviert ist. Wählen Sie in Alle Apps Liste die Option **Cortana**  >  **Menü**  >  **notebook**  >  **Einstellungen** aus, um Änderungen vorzunehmen. Weitere Informationen dazu, was Sie sagen können, finden Sie unter [Verwenden Ihrer Stimme mit HoloLens](hololens-cortana.md).

Auf HoloLens (1. Generation) ist die integrierte Spracherkennung nicht konfigurierbar. Sie ist immer aktiviert. Auf HoloLens 2 können Sie auswählen, ob sie während der Geräteeinrichtung sowohl die Spracherkennung als auch Cortana aktivieren möchten.

Wenn Ihr HoloLens 2 nicht auf Ihre Stimme reagiert, stellen Sie sicher, dass die Spracherkennung aktiviert ist. Wechseln Sie **zu Start**  >  **Einstellungen**  >  **Privacy**  >  **Speech,** und aktivieren Sie **die Spracherkennung.**

[Zurück zur Liste](#list)

## <a name="hand-input-isnt-working"></a>Handeingabe funktioniert nicht

Um sicherzustellen, HoloLens ihre Hände sehen kann, müssen Sie sie im Gestenrahmen halten.  Das Mixed Reality Home bietet Feedback, das Sie darüber informiert, wann Ihre Hände nachverfolgt werden.  Das Feedback ist in verschiedenen Versionen von HoloLens:

- Bei HoloLens (1. Generation) ändert sich der Anvitsor von einem Punkt in einen Ring.
- Auf HoloLens 2 wird ein Fingerspitzencursor angezeigt, wenn sich Ihre Hand in der Nähe einer Tafel befindet, und ein Handstrahl wird angezeigt, wenn Tafeln weiter entfernt sind.

Viele immersive Apps folgen Eingabemustern, die ähnlich wie Mixed Reality Home sind.  Erfahren Sie mehr über die Verwendung von [Handeingaben für HoloLens (1. Generation)](hololens1-basic-usage.md#use-hololens-with-your-hands) [und HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Wenn Sie Handarbeit tragen, beachten Sie, dass einige Handarbeitsarten nicht mit der Handverfolgung funktionieren.  Ein häufiges Beispiel sind schwarze Bänder, die tendenziell Lichtabbild absorbieren und nicht von der Tiefenkamera aufgenommen werden.  Wenn Ihre Arbeit Handarbeit umfasst, empfehlen wir Ihnen, eine hellere Farbe wie Blau oder Grau zu probieren.  Ein weiteres Beispiel sind große Baggy-Handarbeitshandle, die tendenziell die Form Ihrer Hand verdecken. Wir empfehlen die Verwendung von Handschninnen, die so formanpassung wie möglich sind, um optimale Ergebnisse zu erzielen.

Wenn Ihr Visor Fingerabdrücke oder Smudges auftrat, verwenden Sie die Mikrofiber-Bereinigungsbereinigung, die mit der HoloLens, um ihr Visor lappend zu bereinigen.

[Zurück zur Liste](#list)

## <a name="cant-connect-to-wi-fi"></a>Es kann keine Verbindung mit dem Wi-Fi

Hier sind einige Dinge, die Sie ausprobieren sollten, wenn Sie Ihre HoloLens nicht mit einem WLAN verbinden können:

- Stellen Sie sicher, dass das WLAN aktiviert ist. Um dies zu überprüfen, verwenden Sie die Geste Start, und wählen Sie **dann Einstellungen**  >  **&amp; Netzwerk-Internet-WLAN**  >  **aus.** Wenn das WLAN eingeschaltet ist, schalten Sie es aus und dann wieder ein.
- Verringern Sie den Abstand zum Router oder Zugangspunkt.
- Starten Sie ihren Wi-Fi-Router neu, und starten [Sie dann HoloLens.](hololens-recovery.md) Try connecting again.
- Wenn keiner dieser Schritte funktioniert, prüfen Sie, ob Ihr Router die neueste Firmware verwendet. Diese Informationen finden Sie auf der Website des Herstellers.

[Zurück zur Liste](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth Geräte werden nicht gekoppelt

Wenn Sie Probleme beim Koppeln eines Bluetooth [haben,](hololens-connect-devices.md)versuchen Sie Folgendes:

- Wechseln Sie **Einstellungen**  >  **Geräte,** und stellen Sie sicher, Bluetooth aktiviert ist. Wenn dies der Reihe nach der Vorgang ist, deaktivieren Und wieder ein.
- Stellen Sie sicher, Bluetooth Gerät vollständig aufgeladen ist oder über neue Akkus verfügt.
- Wenn Sie immer noch keine Verbindung herstellen können, [starten Sie den HoloLens.](hololens-recovery.md)

[Zurück zur Liste](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C-Mikrofon funktioniert nicht

Beachten Sie, dass einige USB-C-Mikrofone sich fälschlicherweise sowohl als Mikrofon als auch als *Lautsprecher* melden. Dies ist ein Problem mit dem Mikrofon und nicht mit HoloLens. Wenn Sie eines dieser Mikrofone in HoloLens, kann der Sound verloren gehen. Glücklicherweise gibt es eine einfache Lösung.  

Legen **Einstellungen** Systemsound explizit die integrierten Lautsprecher  ->    ->   **(Analog Feature Audio Driver)** als **Standardgerät fest.** HoloLens sollten sich diese Einstellung auch dann merken, wenn das Mikrofon entfernt und später erneut verbunden wird.

![Problembehandlung bei USB-C-Mikrofonen.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Geräte, die als verfügbar in aufgeführt Einstellungen funktionieren nicht

HoloLens (1. Generation) unterstützt keine Bluetooth Audioprofile. Bluetooth Audiogeräte, z. B. Lautsprecher und Headsets, werden möglicherweise als verfügbar in HoloLens angezeigt, werden jedoch nicht unterstützt.

HoloLens 2 unterstützt das Bluetooth A2DP-Audioprofil für die Stereowiedergabe. Das Bluetooth Hands Free-Profil, das die Mikrofonerfassung von einem Bluetooth-Peripheriegerät ermöglicht, wird auf HoloLens 2.

Wenn Sie Probleme bei der Verwendung eines Bluetooth haben, stellen Sie sicher, dass es ein unterstütztes Gerät ist. Folgende Geräte werden unterstützt:

- QWERTY in englischer Sprache Bluetooth Tastaturen (Sie können diese überall dort verwenden, wo Sie die holografische Tastatur verwenden).
- Bluetooth Maus.
- Der [HoloLens klickt.](hololens1-clicker.md)

Sie können andere hid Bluetooth HID- und GATT-Geräte mit Ihren geräten HoloLens. Möglicherweise müssen Sie jedoch entsprechende Begleit-Apps von Microsoft Store installieren, um die Geräte tatsächlich zu verwenden.

[Zurück zur Liste](#list)
