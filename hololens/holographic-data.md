---
title: Suchen und Speichern von Dateien auf HoloLens
description: Verwenden des Datei-Explorers auf HoloLens zum Anzeigen und Verwalten von Dateien auf Ihrem Gerät
keywords: hololens
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
ms.openlocfilehash: 50a13e1634344bea66bb6b7ce90d9e3fc8c2a783
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828041"
---
# Suchen, öffnen und Speichern von Dateien auf HoloLens

Dateien, die Sie auf HoloLens erstellen, einschließlich Fotos und Videos, werden direkt auf Ihrem HoloLens-Gerät gespeichert. Sie können Sie auf die gleiche Weise anzeigen und verwalten, wie Sie Dateien unter Windows 10 verwalten würden:

- Verwenden der App "Datei-Explorer" für den Zugriff auf lokale Ordner
- Innerhalb des Speichers einer App.
- In einem speziellen Ordner (beispielsweise in der Video-oder Musikbibliothek).
- Verwenden eines Speicher Diensts, der eine APP und eine Dateiauswahl enthält (beispielsweise OneDrive).
- Verwenden eines Desktop-PCs, der über ein USB-Kabel mit dem HoloLens verbunden ist, Unterstützung für MTP (Media Transfer Protocol).

## Anzeigen von Dateien auf HoloLens mit dem Datei-Explorer

> Gilt für alle HoloLens 2-Geräte und HoloLens (1st Generation) ab [Windows 10 April 2018 Update (RS4) für HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).

Verwenden Sie den Datei-Explorer auf HoloLens, um Dateien auf Ihrem Gerät anzuzeigen und zu verwalten, darunter 3D-Objekte, Dokumente und Bilder. Wechseln Sie zu **Start**   >  **alle apps**   >  -**Datei-Explorer** , um zu beginnen.

> [!TIP]
> Wenn im Datei-Explorer keine Dateien aufgelistet sind, wählen Sie **dieses Gerät** im oberen linken Bereich aus.

Wenn im Datei-Explorer keine Dateien angezeigt werden, ist der Filter "zuletzt verwendet" möglicherweise aktiv (das Symbol "Uhr" ist im linken Bereich hervorgehoben). Um dieses Problem zu beheben, wählen Sie im linken Bereich (unter dem Symbol "Uhr") das Symbol " **dieses Gerät** Dokument" aus, oder öffnen Sie das Menü, und wählen Sie **dieses Gerät**aus.

## Suchen und Anzeigen Ihrer Fotos und Videos

Mit [Mixed-Reality-Aufnahmen](holographic-photos-and-videos.md) können Sie Fotos und Videos in Mixed Reality auf HoloLens.  Diese Fotos und Videos werden im Ordner "Kamerarolle" des Geräts gespeichert.

Sie können auf Fotos und Videos zugreifen, die mit HoloLens aufgenommen wurden, indem Sie:

- Zugriff auf die Kamera Rollen direkt über die [Foto-APP](holographic-photos-and-videos.md).
- Hochladen von Fotos und Videos in den Cloud-Speicher durch Synchronisieren Ihrer Fotos und Videos mit OneDrive.
- Verwenden der Seite "Mixed Reality Capture" des [Windows Device Portals](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)

### Fotos-App

Die Foto-APP ist eine der Standard-apps im **Startmenü** und wird mit HoloLens integriert. Weitere Informationen finden Sie unter [Verwenden der Foto-APP zum Anzeigen von Inhalten](holographic-photos-and-videos.md).

Sie können auch die [OneDrive-App](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) aus dem Microsoft Store installieren, um Fotos mit anderen Geräten zu synchronisieren.

### OneDrive-App

Mit [OneDrive](https://onedrive.live.com/) können Sie Ihre Fotos und Videos mit jedem beliebigen Gerät und jedem beliebigen Benutzer zugreifen, verwalten und freigeben. Wenn Sie auf die auf HoloLens aufgenommenen Fotos und Videos zugreifen möchten, laden Sie die [OneDrive-App](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) aus dem Microsoft Store auf Ihrem HoloLens. Nachdem Sie die App heruntergeladen haben, öffnen Sie die OneDrive-APP, und wählen Sie **Einstellungen**  >  **Kamera Upload**aus, und aktivieren Sie **Kamera Upload**.

### Herstellen einer Verbindung mit einem PC

Wenn auf Ihrem HoloLens das [Windows 10 April 2018-Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) oder höher ausgeführt wird, können Sie Ihr HoloLens mit einem Windows 10-PC verbinden, indem Sie mit einem USB-Kabel Fotos und Videos auf dem Gerät mithilfe von MTP (Media Transfer Protocol) durchsuchen. Sie müssen sicherstellen, dass das Gerät entsperrt ist, um Dateien zu durchsuchen, wenn Sie eine PIN oder ein Kennwort auf Ihrem Gerät eingerichtet haben.  

Wenn Sie das Windows- [Geräte Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)aktiviert haben, können Sie es verwenden, um die auf Ihrem Gerät gespeicherten Fotos und Videos zu durchsuchen, abzurufen und zu verwalten.

## Zugreifen auf Dateien in einer APP

Wenn eine Anwendung Dateien auf Ihrem Gerät speichert, können Sie diese Anwendung verwenden, um darauf zuzugreifen.

### Anfordern von Dateien aus einer anderen APP

Eine Anwendung kann anfordern, eine Datei zu speichern oder eine Datei aus einer anderen APP mit [Datei Wählern](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)zu öffnen.

### Bekannte Ordner

HoloLens unterstützt eine Reihe [bekannter Ordner](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) , für die apps die Berechtigung zum Zugriff anfordern können.

## Anzeigen von HoloLens-Dateien auf Ihrem PC

Ähnlich wie bei anderen mobilen Geräten können Sie mithilfe von MTP (Media Transfer Protocol) HoloLens mit Ihrem Desktop-PC verbinden und auf dem PC den Datei-Explorer öffnen, um auf Ihre HoloLens-Bibliotheken zugreifen zu können, um Sie einfach übertragen zu können.

So zeigen Sie Ihre HoloLens-Dateien im Datei-Explorer auf Ihrem PC an:

1. Registrieren Sie sich bei HoloLens, und schließen Sie es mit dem USB-Kabel im Lieferumfang des HoloLens an den PC an.

1. Wählen Sie **Gerät öffnen aus, um Dateien mit dem Datei-Explorer anzuzeigen**, oder öffnen Sie den Datei-Explorer auf dem PC, und navigieren Sie zu dem Gerät.

Wenn Sie Informationen zu Ihrem HoloLens anzeigen möchten, klicken Sie im Datei-Explorer auf Ihrem PC mit der rechten Maustaste auf den Gerätenamen, und wählen Sie dann **Eigenschaften**aus.

> [!NOTE]
> HoloLens (1st Gen) unterstützt keine Verbindung zu externen Festplatten oder SD-Karten.

## Mit der Cloud synchronisieren

Wenn Sie Fotos und andere Dateien von Ihrem HoloLens in die Cloud synchronisieren möchten, installieren Sie OneDrive auf HoloLens, und richten Sie Sie ein. Um OneDrive zu erhalten, suchen Sie im Microsoft Store auf Ihrem HoloLens danach.

HoloLens-APP-Dateien und-Daten werden nicht gesichert, daher empfiehlt es sich, Ihre wichtigen Inhalte auf OneDrive zu speichern. Auf diese Weise werden Ihre Informationen, wenn Sie Ihr Gerät zurücksetzen oder eine APP deinstallieren, gesichert.
