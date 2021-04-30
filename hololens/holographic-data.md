---
title: Suchen und Speichern von Dateien auf HoloLens
description: Erfahren Sie, wie Sie den Datei-Explorer auf HoloLens verwenden, um Dateien auf Ihrem Mixed Reality-Gerät zu öffnen, anzuzeigen und zu verwalten.
keywords: Vorgehensweise, Dateiauswahl, Dateien, Fotos, Videos, Bilder, OneDrive, Speicher, Datei-Explorer, Hololens
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
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308596"
---
# <a name="find-open-and-save-files-on-hololens"></a>Suchen, Öffnen und Speichern von Dateien auf HoloLens

Dateien, die Sie auf HoloLens erstellen, einschließlich Fotos und Videos, werden direkt auf Ihrem HoloLens-Gerät gespeichert. Sie können sie auf die gleiche Weise anzeigen und verwalten, wie Sie Dateien auf Windows 10 verwalten würden:

- Verwenden der Datei-Explorer-App für den Zugriff auf lokale Ordner.
- Innerhalb des Speichers einer App.
- In einem speziellen Ordner (z. B. in der Video- oder Musikbibliothek).
- Verwenden eines Speicherdiensts, der eine App und eine Dateiauswahl enthält (z. B. OneDrive).
- Verwenden eines Mit HoloLens verbundenen Desktop-PCs über ein USB-Kabel mit MTP-Unterstützung (Media Transfer Protocol).

## <a name="view-files-on-hololens-using-file-explorer"></a>Anzeigen von Dateien auf HoloLens mithilfe des Datei-Explorers

> Gilt für alle HoloLens 2 Geräte und HoloLens (1. Generation) ab der [Windows 10 April 2018 Update (RS4) für HoloLens.](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)

Verwenden Sie den Datei-Explorer auf HoloLens, um Dateien auf Ihrem Gerät anzuzeigen und zu verwalten, einschließlich 3D-Objekten, Dokumenten und Bildern. Wechseln **Sie** zu Start   >  **Alle Apps**   >  **Datei-Explorer,** um zu beginnen.

> [!TIP]
> Wenn im Datei-Explorer keine Dateien aufgeführt sind, wählen Sie im linken oberen Bereich **Dieses Gerät** aus.

Wenn im Datei-Explorer keine Dateien angezeigt werden, ist der Filter "Zuletzt verwendet" möglicherweise aktiv (das Uhrsymbol ist im linken Bereich hervorgehoben). Um dies zu beheben, wählen Sie das Dokumentsymbol **Dieses Gerät** im linken Bereich (unterhalb des Uhrsymbols) aus, oder öffnen Sie das Menü, und wählen Sie **Dieses Gerät** aus.

## <a name="find-and-view-your-photos-and-videos"></a>Suchen und Anzeigen Ihrer Fotos und Videos

[Mit Mixed Reality](holographic-photos-and-videos.md) Capture können Sie Mixed Reality-Fotos und -Videos auf HoloLens aufnehmen.  Diese Fotos und Videos werden im Kamerarollordner des Geräts gespeichert.

Sie können auf Fotos und Videos zugreifen, die mit HoloLens aufgenommen wurden:

- Direktes Zugreifen auf die Kamerarolle über die [Fotos-App](holographic-photos-and-videos.md).
- Hochladen von Fotos und Videos in den Cloudspeicher durch Synchronisieren Ihrer Fotos und Videos mit OneDrive.
- mithilfe Mixed Reality-Aufnahme -Seite des [Windows-Geräteportal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### <a name="photos-app"></a>Fotos-App

Die Fotos-App ist eine der Standard-Apps im **Startmenü** und in HoloLens integriert. Erfahren Sie mehr über [die Verwendung der Fotos-App zum Anzeigen von Inhalten.](holographic-photos-and-videos.md)

Sie können die [OneDrive-App](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) auch über den Microsoft Store, um Fotos mit anderen Geräten zu synchronisieren.

### <a name="onedrive-app"></a>OneDrive-App

[Mit OneDrive](https://onedrive.live.com/) können Sie auf Ihre Fotos und Videos zugreifen, diese verwalten und für beliebige Geräte und Benutzer freigeben. Um auf die Fotos und Videos zu zugreifen, die auf HoloLens erfasst wurden, laden Sie die [OneDrive-App](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) aus Microsoft Store HoloLens herunter. Öffnen Sie nach dem Herunterladen die OneDrive-App, wählen Sie Einstellungskameraupload  >  aus, und aktivieren Sie **Kameraupload.**

### <a name="connect-to-a-pc"></a>Herstellen einer Verbindung mit einem PC

Wenn auf Ihrer HoloLens das Update vom [Windows 10 April 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) oder höher ausgeführt wird, können Sie Ihre HoloLens mit einem Windows 10-PC verbinden, indem Sie ein USB-Kabel verwenden, um Fotos und Videos auf dem Gerät mithilfe von MTP (Media Transfer Protocol) zu durchsuchen. Sie müssen sicherstellen, dass das Gerät entsperrt ist, um Dateien zu durchsuchen, wenn Sie eine PIN oder ein Kennwort auf Ihrem Gerät eingerichtet haben.  

Wenn Sie die [](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)Windows-Geräteportal aktiviert haben, können Sie sie verwenden, um die auf Ihrem Gerät gespeicherten Fotos und Videos zu durchsuchen, abzurufen und zu verwalten.

## <a name="access-files-within-an-app"></a>Zugreifen auf Dateien in einer App

Wenn eine Anwendung Dateien auf Ihrem Gerät speichert, können Sie diese Anwendung verwenden, um darauf zu zugreifen.

### <a name="requesting-files-from-another-app"></a>Anfordern von Dateien von einer anderen App

Eine Anwendung kann mithilfe der Dateiauswahl anfordern, eine Datei zu speichern oder eine Datei aus einer anderen [App zu öffnen.](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)

### <a name="known-folders"></a>Bekannte Ordner

HoloLens unterstützt eine Reihe [bekannter Ordner,](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) für die Apps Zugriffsberechtigungen anfordern können.

## <a name="view-hololens-files-on-your-pc"></a>Anzeigen von HoloLens-Dateien auf Ihrem PC

Verbinden Sie HoloLens ähnlich wie andere mobile Geräte mithilfe von MTP (Media Transfer Protocol) mit Ihrem Desktop-PC, und öffnen Sie den Datei-Explorer auf dem PC, um zur einfachen Übertragung auf Ihre HoloLens-Bibliotheken zuzugreifen.

So sehen Sie Ihre HoloLens-Dateien im Datei-Explorer auf Ihrem PC:

1. Melden Sie sich bei HoloLens an, und schließen Sie es dann über das USB-Kabel, das mit holoLens stammt, an den PC an.

1. Wählen Sie **Gerät öffnen aus, um Dateien mit dem Datei-Explorer anzuzeigen,** oder öffnen Sie den Datei-Explorer auf dem PC, und navigieren Sie zum Gerät.

Um Informationen zu HoloLens anzuzeigen, klicken Sie im Datei-Explorer auf Ihrem PC mit der rechten Maustaste auf den Gerätenamen, und wählen Sie dann **Eigenschaften** aus.

> [!NOTE]
> HoloLens (1. Generation) unterstützt keine Verbindung mit externen Festplatten oder SD-Karten.

## <a name="sync-to-the-cloud"></a>Synchronisieren mit der Cloud

Installieren und einrichten Sie OneDrive auf HoloLens, um Fotos und andere Dateien von HoloLens mit der Cloud zu synchronisieren. Um OneDrive zu erhalten, suchen Sie im Microsoft Store auf Ihrer HoloLens danach.

HoloLens gesichert keine App-Dateien und -Daten. Daher ist es eine gute Idee, Ihre wichtigen Dinge in OneDrive zu speichern. Auf diese Weise werden Ihre Informationen gesichert, wenn Sie Ihr Gerät zurücksetzen oder eine App deinstallieren.
