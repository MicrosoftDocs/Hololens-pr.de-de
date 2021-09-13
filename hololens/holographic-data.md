---
title: Suchen und Speichern von Dateien auf HoloLens
description: Erfahren Sie, wie Sie den Datei-Explorer auf HoloLens zum Öffnen, Anzeigen und Verwalten von Dateien auf Ihrem Mixed Reality-Gerät verwenden.
keywords: How-to, file picker, files, photos, videos, pictures, OneDrive, storage, file explorer, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032551"
---
# <a name="find-open-and-save-files-on-hololens"></a>Suchen, Öffnen und Speichern von Dateien mit HoloLens

Dateien, die Sie auf einem HoloLens, einschließlich Fotos und Videos, werden direkt auf Ihrem HoloLens gespeichert. Sie können sie auf die gleiche Weise anzeigen und verwalten wie Dateien auf Windows 10:

- Verwenden der Datei-Explorer-App für den Zugriff auf lokale Ordner.
- Im Speicher einer App.
- In einem speziellen Ordner (z. B. in der Video- oder Musikbibliothek).
- Verwenden eines Speicherdiensts, der eine App und eine Dateiauswahl enthält (z. B. OneDrive).
- Verwenden eines Desktop-PCs, HoloLens mithilfe eines USB-Kabels mit MTP-Unterstützung (Media Transfer Protocol) verbunden ist.

## <a name="view-files-on-hololens-using-file-explorer"></a>Anzeigen von Dateien auf HoloLens mithilfe des Datei-Explorers

> Gilt für alle HoloLens 2-Geräte und HoloLens (1. Generation) ab dem Update vom [Windows 10 April 2018 (RS4) für HoloLens](/windows/mixed-reality/release-notes-april-2018).

Verwenden Sie den Datei-Explorer auf HoloLens, um Dateien auf Ihrem Gerät, einschließlich 3D-Objekten, Dokumenten und Bildern, anzeigen und verwalten zu können. Wechseln Sie **zu Alle Apps**   >     >  **Datei-Explorer starten,** um zu beginnen.

> [!TIP]
> Wenn im Datei-Explorer keine Dateien aufgeführt sind, wählen Sie **im** linken oberen Bereich dieses Geräts aus.

Wenn im Datei-Explorer keine Dateien angezeigt werden, ist der Filter "Zuletzt verwendet" möglicherweise aktiv (das Uhrsymbol ist im linken Bereich hervorgehoben). Um dieses Problem  zu beheben, wählen Sie im linken Bereich (unterhalb des Uhrsymbols) das Dokumentsymbol Dieses Gerät aus, oder öffnen Sie das Menü, und wählen Sie **Dieses Gerät aus.**

## <a name="find-and-view-your-photos-and-videos"></a>Suchen und Anzeigen Ihrer Fotos und Videos

[Mit der Mixed Reality-Aufnahme](holographic-photos-and-videos.md) können Sie Mixed Reality-Fotos und -Videos auf HoloLens.  Diese Fotos und Videos werden im Kamerarollordner des Geräts gespeichert.

Sie können auf Fotos und Videos zugreifen, die mit HoloLens wurden:

- Zugriff auf die Kamerarolle direkt über die [Fotos-App.](holographic-photos-and-videos.md)
- Hochladen von Fotos und Videos in den Cloudspeicher durch Synchronisieren Ihrer Fotos und Videos mit OneDrive.
- mithilfe Mixed Reality-Aufnahme -Seite des [Windows Geräteportal](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### <a name="photos-app"></a>Fotos-App

Die Fotos-App ist eine der Standard-Apps im **Startmenü** und ist mit HoloLens. Erfahren Sie mehr [über die Verwendung der Fotos-App zum Anzeigen von Inhalten.](holographic-photos-and-videos.md)

Sie können die App auch [OneDrive-App aus](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) dem Microsoft Store, um Fotos mit anderen Geräten zu synchronisieren.

### <a name="onedrive-app"></a>OneDrive-App

[OneDrive](https://onedrive.live.com/) können Sie auf Ihre Fotos und Videos zugreifen, diese verwalten und für jedes Gerät und für jeden Benutzer freigeben. Um auf die Fotos und Videos zu HoloLens, [](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) laden Sie die OneDrive-App aus dem Microsoft Store auf Ihre HoloLens. Öffnen Sie nach dem Herunterladen die OneDrive-App, wählen Sie Einstellungen   >  **Camera upload (Kameraupload)** aus, und aktivieren Sie **Camera upload (Kameraupload).**

### <a name="connect-to-a-pc"></a>Verbinden auf einen PC

Wenn auf Ihrem HoloLens das [Update vom Windows 10 April 2018](/windows/mixed-reality/release-notes-april-2018) oder höher ausgeführt wird, können Sie Ihre HoloLens mit einem Windows 10-PC verbinden, indem Sie mithilfe eines USB-Kabels Fotos und Videos auf dem Gerät mithilfe von MTP (Medienübertragungsprotokoll) durchsuchen. Sie müssen sicherstellen, dass das Gerät entsperrt ist, um Dateien zu durchsuchen, wenn Sie eine PIN oder ein Kennwort auf Ihrem Gerät eingerichtet haben.  

Wenn Sie die Windows Geräteportal aktiviert [haben,](/windows/mixed-reality/using-the-windows-device-portal)können Sie sie verwenden, um die auf Ihrem Gerät gespeicherten Fotos und Videos zu durchsuchen, abzurufen und zu verwalten.

## <a name="access-files-within-an-app"></a>Zugreifen auf Dateien in einer App

Wenn eine Anwendung Dateien auf Ihrem Gerät speichert, können Sie diese Anwendung für den Zugriff darauf verwenden.

### <a name="requesting-files-from-another-app"></a>Anfordern von Dateien von einer anderen App

Eine Anwendung kann mithilfe der Dateiauswahl anfordern, eine Datei zu speichern oder eine Datei aus einer anderen [App zu öffnen.](/windows/mixed-reality/app-model#file-pickers)

### <a name="known-folders"></a>Bekannte Ordner

HoloLens unterstützt eine Reihe bekannter [Ordner,](/windows/mixed-reality/app-model#known-folders) für die Apps Zugriffsberechtigungen anfordern können.

## <a name="view-hololens-files-on-your-pc"></a>Anzeigen HoloLens Dateien auf Ihrem PC

Stellen Sie ähnlich wie bei anderen mobilen Geräten über MTP (Media Transfer Protocol) eine Verbindung mit Ihrem Desktop-PC HoloLens, und öffnen Sie den Datei-Explorer auf dem PC, um zur einfachen Übertragung auf Ihre HoloLens-Bibliotheken zu zugreifen.

So sehen Sie HoloLens Dateien im Datei-Explorer auf Ihrem PC:

1. Melden Sie sich bei HoloLens an, und schließen Sie es dann mithilfe des USB-Kabels an den PC an, das im HoloLens.

1. Wählen **Sie Gerät öffnen aus, um Dateien mit dem Datei-Explorer anzeigen,** oder öffnen Sie den Datei-Explorer auf dem PC, und navigieren Sie zum Gerät.

Klicken Sie zum Anzeigen HoloLens Gerätenamens im Datei-Explorer auf Ihrem PC mit der rechten Maustaste auf den **Gerätenamen,** und wählen Sie dann Eigenschaften aus.

> [!NOTE]
> HoloLens (1. Generation) unterstützt keine Verbindung mit externen Festplatten oder SD-Karten.

## <a name="sync-to-the-cloud"></a>Synchronisieren mit der Cloud

Um Fotos und andere Dateien aus Ihrem HoloLens mit der Cloud zu synchronisieren, installieren und richten Sie OneDrive auf HoloLens. Um die OneDrive, suchen Sie in der Microsoft Store in Ihrer HoloLens.

HoloLens keine App-Dateien und -Daten sichern, ist es daher eine gute Idee, Ihre wichtigen Daten zu speichern, um OneDrive. Auf diese Weise werden Ihre Informationen gespeichert, wenn Sie Ihr Gerät zurücksetzen oder eine App deinstallieren.
