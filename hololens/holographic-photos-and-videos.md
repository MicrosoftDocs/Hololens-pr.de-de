---
title: Erfassen, Aufzeichnen und Freigeben von Mixed Reality-Fotos und -Videos
description: Erfahren Sie, wie Sie Mithilfe von Mixed Reality-Geräten Fotos und Videos erfassen HoloLens aufzeichnen und anzeigen. Erfahren Sie, wie Sie daten- Miracast gesammelte Dateien freigeben.
keywords: hololens, photo, video, capture, mrc, mixed reality capture, photos, camera, miracast, stream, livestream, demo, record
ms.assetid: 1b636ec3-6186-4fbb-81b2-71155aef0593
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 10/28/2019
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 54e9959c03b69db39ff2738e5d4f41f9740ae562b38e8d85998521a4733edad7
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664858"
---
# <a name="create-mixed-reality-photos-and-videos"></a>Mixed Reality-Fotos und -Videos aufnehmen

HoloLens bietet Benutzern die Erfahrung, die reale Welt mit der digitalen Welt zu mischen.  Mit mixed reality capture (MRC) können Sie diese Erfahrung als Foto oder Video erfassen oder das, was Sie sehen, in Echtzeit mit anderen teilen.

Bei der Mixed Reality-Erfassung wird ein Blick auf eine Person verwendet, damit andere Personen Hologramme sehen können, wie Sie sie sehen. Verwenden Sie für eine Dritte-Person-Ansicht [die Ansicht .](/windows/mixed-reality/spectator-view) Die Ansicht "Ungn" ist besonders nützlich für Demos.

Auch wenn es spaß macht, Videos für Freunde und Kollegen zu teilen, können Videos auch dazu beitragen, anderen Personen beizubringen, eine App zu verwenden oder Probleme mit Apps und Erfahrungen zu kommunizieren.

> [!NOTE]
> Wenn Sie Mixed Reality-Erfassungserfahrungen nicht starten können und ihr HoloLens ein Arbeitsgerät ist, wenden Sie sich an Ihren Systemadministrator. Der Zugriff auf die Kamera kann über die Unternehmensrichtlinie eingeschränkt werden.

## <a name="capture-a-mixed-reality-photo"></a>Aufnehmen eines Mixed Reality-Fotos

Es gibt mehrere Möglichkeiten, ein Foto von Mixed Reality auf einem HoloLens. Sie können Hardwaretasten, Sprache oder die Startmenü.

### <a name="hardware-buttons-to-take-photos"></a>Hardwareschaltflächen zum Erstellen von Fotos

Um ein schnelles Foto ihrer aktuellen Ansicht zu machen, drücken Sie gleichzeitig die Schaltflächen "Volume nach oben" und "Volume nach unten".  Dies ist ein wenig wie HoloLens Version eines Screenshots oder Druckbildschirms.

- [Schaltflächenpositionen auf HoloLens 2](hololens2-hardware.md)
- [Schaltflächenpositionen auf HoloLens (1. Generation)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> Wenn Sie **die Schaltflächen volume up** und volume **down** für drei Sekunden halten, beginnt die Aufzeichnung eines Videos, anstatt ein Foto zu machen. Um die Aufzeichnung zu beenden, tippen Sie gleichzeitig auf die Schaltflächen **"Volume nach** oben" **und "Lautstärke** nach unten".

### <a name="voice-commands-to-take-photos"></a>Sprachbefehle zum Erstellen von Fotos

Auf HoloLens 2 Version 2004 (und höher) sagen Sie: "Bild machen".

Auf HoloLens (1. Generation) oder HoloLens 2 Version 1903: "Hey Cortana, take a picture".

### <a name="start-menu-to-take-photos"></a>Startmenü, um Fotos zu machen

Verwenden Sie die Geste Start, um **zu Starten zu wechseln,** und wählen Sie dann das **Kamerasymbol** aus.

Zeigen Sie mit dem Kopf in die Richtung, was Sie aufnehmen möchten, und [tippen](hololens2-basic-usage.md#touch-holograms-near-you) Sie dann in die Luft, um ein Foto zu machen. Sie können weiterhin auf die Luft tippen und zusätzliche Fotos aufnehmen. Alle Fotos, die Sie aufnehmen, werden auf Ihrem Gerät gespeichert.

Verwenden Sie die Geste Start erneut, um die Fotoaufnahme zu beenden.  

## <a name="capture-a-mixed-reality-video"></a>Erfassen eines Mixed Reality-Videos

Es gibt mehrere Möglichkeiten, ein Video von Mixed Reality auf HoloLens; Sie können Hardwaretasten, Sprache oder die Startmenü.

### <a name="hardware-buttons-to-record-videos"></a>Hardwareschaltflächen zum Aufzeichnen von Videos

Die schnellste Möglichkeit zum Aufzeichnen eines Videos  besteht  im gleichzeitigen Drücken und Halten der Lautstärketasten und der Lautstärketasten, bis ein Countdown von drei Sekunden beginnt. Um die Aufzeichnung zu beenden, tippen Sie gleichzeitig auf beide Schaltflächen.

> [!NOTE]
> Wenn Sie das **Volume schnell nach oben** und die Lautstärke nach unten drücken, wird ein Foto angezeigt, anstatt ein Video aufzeichnen zu müssen. 

### <a name="voice-to-record-videos"></a>Sprache zum Aufzeichnen von Videos

Auf HoloLens 2 Version 2004 (und höher) sagen Sie: "Aufzeichnung starten". Um die Aufzeichnung zu beenden, sagen Sie "Aufzeichnung beenden".

Auf HoloLens (1. Generation) oder HoloLens 2 Version 1903: "Hey Cortana, start recording". Um die Aufzeichnung zu beenden, sagen Sie "Hey Cortana, aufzeichnung beenden".

### <a name="start-menu-to-record-videos"></a>Startmenü zum Aufzeichnen von Videos

Verwenden Sie die Geste Start, um **zu Starten zu wechseln,** und wählen Sie dann das **Symbol Video** aus. Zeigen Sie mit dem Kopf in die Richtung, was Sie erfassen möchten, und [tippen](hololens2-basic-usage.md#touch-holograms-near-you) Sie dann in die Luft, um mit der Aufzeichnung zu beginnen. Es gibt einen Countdown von drei Sekunden, und Ihre Aufzeichnung beginnt.

Um die Aufzeichnung zu beenden, verwenden Sie die Geste Start, und wählen Sie das **hervorgehobene Videosymbol** aus. Das Video wird auf Ihrem Gerät gespeichert.

> [!NOTE]
> **Gilt nur HoloLens (1. Generation)**  
> Die [Windows 10 October 2018 Update](/windows/mixed-reality/release-notes-october-2018) ändert das Verhalten der Startgeste und Windows auf HoloLens (1. Generation). Vor dem Update würde die Startgeste oder Windows eine Videoaufzeichnung beenden. Nach dem Update öffnet die Schaltfläche Startgeste oder Windows jedoch  das **Startmenü** (oder das Menü für schnelle Aktionen, wenn Sie sich in einer immersiven App befinden), über das Sie das hervorgehobene Videosymbol auswählen können, um die Aufzeichnung zu beenden. 

## <a name="share-what-you-see-in-real-time"></a>Teilen Sie das, was Sie sehen, in Echtzeit.

Sie können das, was Sie in HoloLens sehen, in Echtzeit mit Freunden und Kollegen teilen. Es stehen einige Methoden zur Verfügung:

1. Herstellen einer Verbindung mit einem Miracast bzw. adapterfähigen Geräts oder Adapters zum Ansehen auf einem Fernsehgerät.
1. Verwenden [Windows Geräteportal](/windows/mixed-reality/using-the-windows-device-portal) zum Ansehen auf einem PC
1. Verwenden der [Microsoft HoloLens-App zum](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) Ansehen auf einem PC.
1. Bereitstellen der [](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) Microsoft Dynamics 365 Remote Assist-App, mit der Front-Line-Mitarbeiter das Angezeigte an einen Remoteexperten streamen können. Der Remoteexperte kann den Front-Line-Worker dann wortlich oder durch Kommentieren in seiner Welt führen.

> [!NOTE]
> Für die Freigabe der Angezeigten über Windows Geräteportal oder Microsoft HoloLens-Begleit-App muss sich HoloLens im [Entwicklermodus befinden.](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)

### <a name="stream-video-with-miracast"></a>Streamen von Videos mit Miracast

Verwenden Sie die Geste Start, um **zu Starten zu** wechseln, und wählen Sie dann das symbol **Verbinden** aus. Wählen Sie in der angezeigten Auswahl das Miracast bzw. Adapter aus, mit dem bzw. dem Sie eine Verbindung herstellen möchten.

Um die Freigabe zu beenden, verwenden Sie die Startgeste, und wählen Sie das hervorgehobene **symbol Verbinden** aus. Da Sie gestreamt haben, wird nichts auf Ihrem Gerät gespeichert.

> [!NOTE]
> Miracast-Unterstützung wurde für HoloLens (1. Generation) ab dem [Windows 10 October 2018 Update.](/windows/mixed-reality/release-notes-october-2018)

### <a name="real-time-video-with-windows-device-portal"></a>Echtzeitvideo mit Windows Geräteportal

Da die Freigabe über Windows Geräteportal erfordert, dass der Entwicklermodus auf HoloLens aktiviert ist, befolgen Sie die Anweisungen in unserer Entwicklerdokumentation, um den Entwicklermodus einrichten und in [Windows Geräteportal.](/windows/mixed-reality/using-the-windows-device-portal)

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens Begleit-App

Da die Freigabe über die Microsoft HoloLens-Begleit-App erfordert, dass der Entwicklermodus auf HoloLens aktiviert ist, befolgen Sie die Anweisungen in unserer Entwicklerdokumentation, um den [Entwicklermodus einrichten.](/windows/mixed-reality/using-the-windows-device-portal) Laden Sie dann die [Microsoft HoloLens-App herunter,](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) und befolgen Sie die Anweisungen in der App, um eine Verbindung mit Ihrem HoloLens.

Nachdem die App mit Ihrem HoloLens eingerichtet wurde, wählen Sie im Hauptmenü der App die Option **Livestream** aus.

## <a name="view-your-mixed-reality-photos-and-videos"></a>Anzeigen ihrer Mixed Reality-Fotos und -Videos

Mixed Reality-Fotos und -Videos werden im "Kameraroll" des Geräts gespeichert. Sie können den Inhalt dieses Ordners in Ihrer HoloLens mit der Datei-Explorer-App durchsuchen (navigieren Sie zu **Bilder > Camera Roll**).

Sie können Ihre Mixed Reality-Fotos und -Videos auch in der Fotos-App anzeigen, die auf dem Gerät vorinstalliert HoloLens. Wenn Sie ein Foto in Ihrer Welt anheften möchten, wählen Sie es in der Fotos-App aus, und wählen **Sie Place in mixed world (In gemischter Welt platzieren) aus.** Sie können das Foto um Ihre Welt verschieben, nachdem es platziert wurde.

Zum Anzeigen und/oder Speichern Ihrer Mixed Reality-Fotos und -Videos auf [](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) einem PC, der mit HoloLens verbunden ist, können Sie Windows Geräteportal oder den Datei-Explorer Ihres PCs über [MTP verwenden.](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>Verwenden des Datei-Explorers zum Herunterladen ihrer Bilder, Videos und Dateien

Ähnlich wie bei anderen mobilen Geräten verbinden Sie Ihre HoloLens mit Ihrem PC, um den Datei-Explorer für den Zugriff auf Ihre HoloLens-Bibliotheken (Fotos, Videos, Dokumente) für die einfache Übertragung zu öffnen. Diese Methode ist einfach zu verwenden und erfordert nicht die Verwendung des Geräteportals oder WLAN.

1. Entsperren Sie das Gerät.
1. Verbinden gerät über USB an einen PC.
1. Der Datei-Explorer sollte auf Ihrem PC geöffnet werden.
1. Navigieren Sie zu: This PC \\ *yourhololensname*\Internal Storage\Pictures\Camera Roll
1. Kopieren Sie die dateien, die Sie benötigen, auf Ihren PC.

Tipps:
- Wenn keine Dateien angezeigt werden, stellen Sie sicher, dass Sie sich bei Ihrem HoloLens anmelden, um den Zugriff auf Ihre Daten zu ermöglichen.
- Sie können andere Dateien in anderen Ordnern, z. B. [Diagnosedateien,](hololens-diagnostic-logs.md#offline-diagnostics) aus dem Ordner Dokumente erhalten.
- Im Datei-Explorer auf Ihrem PC können Sie Geräteeigenschaften auswählen, um Windows Holographic OS-Versionsnummer (Firmwareversion), Geräteseriennummer und Akkuprozentsatz zu sehen.
- Wenn Ihre Organisation MDM zum Deaktivieren von [Konnektivität/AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) verwendet hat, können Sie keine Verbindung mit Ihrem Gerät herstellen.

## <a name="share-your-mixed-reality-photos-and-videos"></a>Teilen Ihrer Mixed Reality-Fotos und -Videos

Vor Windows [Holographic, Version 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)wird nach dem Erfassen eines Mixed Reality-Fotos oder -Videos eine Vorschau angezeigt. Klicken Sie über **der** Vorschau auf das Symbol Freigeben, um den Freigabe-Assistenten anzuzeigen. Von dort aus können Sie den Endpunkt auswählen, für den Sie das Foto oder Video freigeben möchten.

Mit Windows Holographic, Version 21H1, wird nach dem Erfassen eines Mixed Reality-Fotos oder -Videos eine Vorschau angezeigt. Klicken Sie über **der** Vorschau auf das Symbol Freigeben, um den Freigabe-Assistenten anzuzeigen. Von dort aus können Sie den Endpunkt (E-Mail, OneDrive usw.) auswählen, an den Sie dieses Foto oder Video freigeben möchten. Sie können ihren Benutzer auch HoloLens für Geräte in der Nähe freigeben, indem Sie Einstellungen **-> System -> Shared Experiences verwenden.** Weitere Informationen finden Sie unter [Freigeben von Geräten in der Nähe in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

> [!TIP] 
> Sie können auch Mixed Reality-Fotos und -Videos von OneDrive, indem Sie Ihre Mixed Reality-Fotos und -Videos automatisch hochladen. Öffnen Sie die OneDrive-App auf HoloLens, und melden Sie sich mit einem persönlichen Microsoft-Konto **an, [](https://account.microsoft.com)** sofern dies noch nicht der Reihe ist. Klicken Sie auf **Einstellungen** Symbol, und wählen Sie **Kamera hochladen aus.** Aktivieren Sie den Kameraupload. Ihre Mixed Reality-Fotos und -Videos werden nun jedes Mal OneDrive, wenn Sie die App auf dem HoloLens.

> [!NOTE]
> Sie können den Kameraupload nur in OneDrive, wenn Sie mit einem persönlichen OneDrive bei der Microsoft-Konto. Wenn Sie eine HoloLens mit einem Arbeits-, Schul- oder Schulkonto einrichten, können Sie der Microsoft-Konto-App eine persönliche OneDrive hinzufügen, um dieses Feature zu aktivieren.

## <a name="limitations-of-mixed-reality-capture"></a>Einschränkungen der Mixed Reality-Erfassung

- Bei Verwendung der Mixed Reality-Erfassung wird die Bildfrequenz der HoloLens auf 30 Hz halbiert.
- Die Auflösung von Fotos und Videos kann reduziert werden, wenn die Foto-/Videokamera bereits von einer anderen Anwendung verwendet wird, während live gestreamt wird oder wenn die Systemressourcen gering sind.

### <a name="maximum-recording-length"></a>Maximale Aufzeichnungslänge

Auf HoloLens 2 Geräten vor der Windows Holographic, Version 20H2, waren die auf dem Gerät aufgezeichneten Videos auf die maximale Länge von fünf Minuten beschränkt.

Aufgrund von Kundenfeedback haben wir die Aufzeichnungslänge von [Mixed Reality-Erfassungen erhöht.](holographic-photos-and-videos.md) Mixed Reality-Erfassungen sind standardmäßig nicht mehr auf 5 Minuten beschränkt, sondern berechnen stattdessen die maximale Aufzeichnungslänge basierend auf dem verfügbaren Speicherplatz. Das Gerät schätzt die maximale Dauer der Videoaufzeichnung basierend auf dem verfügbaren Speicherplatz auf bis zu 80 % des gesamten Speicherplatzes auf dem Datenträger.

> [!NOTE]
> Der HoloLens verwendet die Standardlänge der Videoaufzeichnung (5 Minuten), wenn eine der folgenden Bedingungen eintritt:
> - Die geschätzte maximale Aufzeichnungsdauer ist kleiner als die standardmäßigen 5 Minuten.
> - Der verfügbare Speicherplatz beträgt weniger als 20 % des gesamten Speicherplatzes auf dem Datenträger.

## <a name="default-file-format-and-resolution"></a>Standarddateiformat und -auflösung

### <a name="default-photo-format-and-resolution"></a>Standardbildformat und -auflösung

|  Sicherungsmedium  |  Format  |  Durchwahl  |  Lösung  |
|----------|----------|----------|----------|
| HoloLens 2 | [Jpeg](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (1. Generation) | [Jpeg](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408 x 792 px |

### <a name="recorded-video-format-and-resolution"></a>Aufgezeichnetes Videoformat und Auflösung

| Sicherungsmedium | Format | Durchwahl | Lösung | Geschwindigkeit | Audio |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30Fps | Stereo mit 48 kHz |
| HoloLens (1. Generation) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24Fps | Stereo mit 48 kHz |
