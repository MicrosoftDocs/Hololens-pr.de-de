---
title: Suchen und Speichern von Dateien auf HoloLens
description: Erfahren Sie, wie Sie den Datei-Explorer auf HoloLens zum Öffnen, Anzeigen und Verwalten von Dateien auf Ihrem Mixed -Reality-Gerät verwenden.
keywords: How-to, Dateiauswahl, Dateien, Fotos, Videos, Bilder, OneDrive, Speicher, Datei-Explorer, HoloLens
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283526"
---
# Suchen, Öffnen und Speichern von Dateien mit HoloLens

Dateien, die Sie auf HoloLens erstellen, einschließlich Fotos und Videos, werden direkt auf Ihrem HoloLens-Gerät gespeichert. Zeigen Sie sie auf die gleiche Weise an, wie Sie Dateien unter Windows 10 verwalten würden:

- Verwenden der Datei-Explorer-App für den Zugriff auf lokale Ordner.
- Innerhalb des Speichers einer App.
- In einem speziellen Ordner (z. B. der Video- oder Musikbibliothek).
- Verwenden eines Speicherdiensts, der eine App und eine Dateiauswahl (z. B. OneDrive) enthält.
- Verwenden eines Desktop-PCs, der über ein USB-Kabel mit Ihrer HoloLens verbunden ist, mithilfe der MTP (Media Transfer Protocol)-Unterstützung.

## Anzeigen von Dateien auf HoloLens mit dem Datei-Explorer

> Gilt für alle HoloLens 2-Geräte und HoloLens (1. Generation) ab dem [Windows 10 April 2018 Update (RS4) für HoloLens.](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)

Verwenden Sie den Datei-Explorer auf HoloLens zum Anzeigen und Verwalten von Dateien auf Ihrem Gerät, einschließlich 3D-Objekten, Dokumenten und Bildern. Wechseln Sie **zum**   >  **Datei-Explorer**   >  **"Alle Apps starten",** um zu beginnen.

> [!TIP]
> Wenn im Datei-Explorer keine Dateien aufgelistet sind, wählen Sie dieses **Gerät** im oberen linken Bereich aus.

Wenn im Datei-Explorer keine Dateien angezeigt werden, ist der Filter "Zuletzt verwendet" möglicherweise aktiv (das Uhrsymbol wird im linken Bereich hervorgehoben). Um dieses Problem **** zu beheben, wählen Sie das Dokumentsymbol dieses Geräts im linken Bereich (unter dem Uhrsymbol) aus, oder öffnen Sie das Menü, und wählen Sie **"Dieses Gerät" aus.**

## Suchen und Anzeigen ihrer Fotos und Videos

[Mit Mixed -Reality-Aufnahmen](holographic-photos-and-videos.md) können Sie Mixed -Reality-Fotos und -Videos auf HoloLens aufnehmen.  Diese Fotos und Videos werden im Ordner "Camera Roll" des Geräts gespeichert.

Sie können auf Fotos und Videos zugreifen, die mit HoloLens aufgenommen wurden, indem Sie:

- Zugriff auf das Kamerarolling direkt über die [Fotos App.](holographic-photos-and-videos.md)
- Hochladen von Fotos und Videos in den Cloudspeicher, indem Sie Ihre Fotos und Videos mit OneDrive synchronisieren.
- verwenden Sie die Mixed Reality Capture-Seite des [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### Fotos-App

Die Fotos-App ist eine der Standard-Apps im **Startmenü** und ist in HoloLens integrierte. Erfahren Sie mehr [über die Verwendung Fotos App zum Anzeigen von Inhalten.](holographic-photos-and-videos.md)

Sie können auch die [#A0](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) aus dem Microsoft Store installieren, um Fotos mit anderen Geräten zu synchronisieren.

### OneDrive-App

[Mit OneDrive](https://onedrive.live.com/) können Sie auf Ihre Fotos und Videos zugreifen, diese verwalten und für jedes Gerät und jeden Benutzer freigeben. Um auf die auf HoloLens aufgenommenen Fotos und Videos zu zugreifen, laden Sie die #A0 aus [dem](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) Microsoft Store auf Ihre HoloLens herunter. Öffnen Sie nach dem Download die OneDrive-App, **wählen**Sie  >  **"Kameraeinstellungen hochladen"** aus, und aktivieren Sie den **Kameraupload.**

### Herstellen einer Verbindung mit einem PC

Wenn Ihre HoloLens das [Windows 10 April 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) Update oder höher ausgeführt wird, können Sie Ihre HoloLens mit einem Windows 10-PC verbinden, indem Sie ein USB-Kabel verwenden, um Fotos und Videos auf dem Gerät mithilfe von MTP (Media Transfer Protocol) zu durchsuchen. Sie müssen sicherstellen, dass das Gerät entsperrt ist, um Dateien zu durchsuchen, wenn Sie eine PIN oder ein Kennwort auf Ihrem Gerät eingerichtet haben.  

Wenn Sie das [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)aktiviert haben, können Sie es verwenden, um die auf Ihrem Gerät gespeicherten Fotos und Videos zu durchsuchen, abzurufen und zu verwalten.

## Zugreifen auf Dateien in einer App

Wenn eine Anwendung Dateien auf Ihrem Gerät speichert, können Sie diese Anwendung verwenden, um darauf zu zugreifen.

### Anfordern von Dateien von einer anderen App

Eine Anwendung kann anfordern, eine Datei zu speichern oder eine Datei in einer anderen App mithilfe der [Dateiauswahl zu öffnen.](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)

### Bekannte Ordner

HoloLens unterstützt eine Reihe von bekannten [Ordnern,](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) auf die Apps Zugriffsberechtigungen anfordern können.

## Anzeigen von HoloLens-Dateien auf Ihrem PC

Verbinden Sie HoloLens ähnlich wie andere mobile Geräte mit Ihrem Desktop-PC mithilfe von MTP (Media Transfer Protocol), und öffnen Sie den Datei-Explorer auf dem PC, um auf Ihre HoloLens-Bibliotheken zu zugreifen, um die Übertragung zu ermöglichen.

So sehen Sie Ihre HoloLens-Dateien im Datei-Explorer auf Ihrem PC:

1. Melden Sie sich bei HoloLens an, und schließen Sie es dann mit dem im HoloLens-Gerät mit dem USB-Kabel an den PC an.

1. Wählen **Sie "Gerät öffnen"** aus, um Dateien mit dem Datei-Explorer oder den Datei-Explorer auf dem PC zu öffnen und zum Gerät zu navigieren.

Wenn Sie Informationen zu Ihrer HoloLens anzeigen möchten, klicken Sie im Datei-Explorer auf Ihrem PC mit der rechten Maustaste auf den Gerätenamen, und wählen Sie dann **"Eigenschaften" aus.**

> [!NOTE]
> HoloLens (1. Generation) unterstützt keine Verbindung mit externen Festplatten oder SD-Karten.

## Synchronisieren mit der Cloud

Um Fotos und andere Dateien von Ihrer HoloLens in der Cloud zu synchronisieren, installieren und richten Sie OneDrive auf HoloLens ein. Um OneDrive zu erhalten, suchen Sie im Microsoft Store auf Ihrer HoloLens nach diesem.

HoloLens unterstützt keine #A0 und -Daten, daher ist es eine gute Idee, Ihre wichtigen Daten auf OneDrive zu speichern. Auf diese Weise werden Ihre Informationen gesichert, wenn Sie Ihr Gerät zurücksetzen oder eine App deinstallieren.
