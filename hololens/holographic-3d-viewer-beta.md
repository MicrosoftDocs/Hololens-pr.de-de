---
title: Verwenden des 3D-Viewers (Beta) mit HoloLens (1. Generation)
description: Beschreibt die Dateitypen und Features, die vom 3D-Viewer (Beta) auf HoloLens (1. Generation) unterstützt werden, sowie Informationen zur Verwendung und Problembehandlung für die App.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f5481d6466459667deb99232fdd67c4491798cbe
ms.sourcegitcommit: 1b19b0eb552189d7c50617bbdf3a102d3c85ee0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016286"
---
# Verwenden des 3D-Viewers (Beta) mit HoloLens (1. Generation)

3D-Viewer (Beta) ermöglicht das Anzeigen von 3D-Modellen auf HoloLens (1. Generation). Sie können *unterstütze* FBX-Dateien von Microsoft Edge, OneDrive und anderen Apps öffnen und anzeigen.

>[!NOTE]
>Dieser Artikel bezieht sich auf die immersive Einheit **3D-Viewer (Beta)**-App, die FBX-Dateien unterstützt und nur auf HoloLens (1. Generation) verfügbar ist. Die vorinstallierte **3D-Viewer**-App auf HoloLens 2 unterstützt das Öffnen von benutzerdefinierten GLB 3D-Modellen in der Mixed-Reality-Startseite (Weitere Informationen finden Sie unter [Übersicht über die Asset-Voraussetzungen](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview)).

>[!IMPORTANT]
>Der 3D Viewer (Beta) ist zwar im Microsoft Store für HoloLens (1. Generation) weiterhin verfügbar, wird aber nicht mehr aktiv weiterentwickelt und auch nicht mehr unterstützt.

Wenn es beim Öffnen eines 3D-Modells im 3D-Viewer (Beta) Probleme gibt oder bestimmte Features Ihres 3D-Modells nicht unterstützt werden, lesen Sie die[Spezifikationen für unterstützte Inhalte](#supported-content-specifications) weiter unten.

Informationen zum Erstellen oder Optimieren von 3D-Modellen zur Verwendung mit 3D-Viewer (Beta) finden Sie unter [Optimieren von 3D-Modellen für 3D-Viewer (Beta)](#optimizing-3d-models-for-3d-viewer-beta).

Es gibt zwei Möglichkeiten, um ein 3D-Modell auf HoloLens zu öffnen. Weitere Informationen hierzu finden Sie in [Anzeigen von FBX-Dateien auf HoloLens](#viewing-fbx-files-on-hololens) weiter unten.

Wenn Sie nach dem Lesen dieser Themen auf Probleme stoßen, lesen Sie [Problembehandlung](#troubleshooting) weiter unten.

## Spezifikationen für unterstützte Inhalte

### Dateiformat

- FBX-Format
- Maximale FBX-Version 2015.1.0

### Dateigröße

- Mindestens 5 KB
- Maximal 500 MB

### Geometrie

- Nur Polygonmodelle. Keine Unterteilungsflächen oder NURBs
- Rechtshändiges Koordinatensystem
- Scheren in Transformationsmatrizen werden nicht unterstützt.

### Texturen

- Texturkarten müssen in die FBX-Datei eingebettet sein
- Unterstützte Bildformate
  - JPEG- und PNG-Bilder
  - BMP-Bilder (24-Bit RGB-True-Color)
  - TGA-Bilder (24-Bit RGB und 32-Bit RGBQ True-Color)
- Maximale Texturauflösung von 2.048 x 2.048
- Maximale Anzahl einer diffusen Karte, einer normalen Karte und eine Reflexionswürfelkarte pro Gittermodell
- Alpha-Kanal in diffusen Texturen bewirkt, dass Pixel unter 50 % verworfen werden

### Animation

- Skalieren/Drehung/Translation von Animationen auf einzelne Objekte
- Skelettartige (manipulierte) Animation unter Anwendung von Skins
  - Maximal 4 Einflüsse pro Scheitelpunkt

### Materialien

- Lambert- und Phong-Materialien werden unterstützt, mit einstellbaren Parametern
- Unterstützte Materialeigenschaften für Lambert
  - Haupttextur (RGB + Alpha-Test)
  - Diffuse Farbe (RGB)
  - Umgebungsfarbe (RGB)
- Unterstützte Materialeigenschaften für Phong
  - Haupttextur (RGB + Alpha-Test)
  - Diffuse Farbe (RGB)
  - Umgebungsfarbe (RGB)
  - Glanzfarbe (RGB)
  - Glanz
  - Reflektivität
- Benutzerdefinierte Materialien werden nicht unterstützt
- Höchstens ein Material pro Gittermodell
- Höchstens eine Materialschicht
- Höchstens 8 Materialien pro Datei

### Datei- und Modellbeschränkungen

Es gibt feste Beschränkungen hinsichtlich der Dateigröße sowie der Anzahl der Modelle, Scheitelpunkte und Gittermodelle, die im 3D-Viewer (Beta) gleichzeitig geöffnet sein können:

- 500 MB maximale Dateigröße pro Modell
- Scheitelpunkte: 600.000 insgesamt in allen geöffneten Modellen
- Gittermodelle: 1.600 insgesamt in allen geöffneten Modellen
- Höchstens 40 Modelle gleichzeitig geöffnet

## Optimieren von 3D-Modellen für 3D-Viewer (Beta)

### Praktische Überlegungen

- Vermeiden Sie schwarze Materialien oder schwarze Bereiche in Textkurkarten. Hologramme bestehen aus Licht. Deshalb rendert HoloLens schwarz (die Abwesenheit von Licht) als transparent.
- Vergewissern Sie sich vor dem Exportieren nach FBX aus dem Erstellungstool, dass alle Geometrien sichtbar und entriegelt sind und keine Ebenen, die Geometrie enthalten, deaktiviert oder mit einer Vorlage versehen sind. Sichtbarkeit wird nicht beachtet.
- Vermeiden Sie sehr große Translation-Offsets zwischen den Knoten (beispielsweise 100.000 Einheiten). Das kann dazu führen, dass das Modell während des Verschiebens/Skalierens/Drehens wackelt.

### Leistungsoptimierung

Berücksichtigen Sie beim Erstellen von Inhalten die Leistung und validieren Sie in der 3D-Viewer-App (Beta) auf HoloLens während des Erstellungsprozesses, um optimale Ergebnisse zu erzielen. 3D-Viewer (Beta) rendert Inhalte in Echtzeit. Die Leistung unterliegt den HoloLens-Hardwarefunktionen.  

Ein 3D-Modell enthält zahlreiche Variablen, die sich auf die Leistung auswirken können. Im 3D-Viewer (Beta) wird beim Laden eine Warnung angezeigt, wenn mehr als 150.000 Scheitelpunkte oder mehr als 400 Gittermodelle vorhanden sind. Animationen können sich auf die Leistung anderer offener Modelle auswirken. Es gibt feste Beschränkungen hinsichtlich der Dateigröße sowie der Anzahl der Modelle, Scheitelpunkte und Gittermodelle, die im 3D-Viewer (Beta) gleichzeitig geöffnet sein können (siehe [Datei- und Modellbeschränkungen](#file-and-model-limitations)).  

Wenn das 3D-Modell aufgrund der Komplexität des Modells nicht ordnungsgemäß ausgeführt wird, ziehen Sie Folgendes in Betracht:

- Reduzieren der Polygonanzahl
- Verringern der Anzahl von Bones in manipulierten Animationen
- Vermeiden von Selbstokklusion

Das beidseitige Rendering wird im 3D-Viewer (Beta) unterstützt, aus Leistungsgründen ist es jedoch standardmäßig deaktiviert. Das kann über die Schaltfläche **Beidseitig** auf der Seite **Details** aktiviert werden. Vermeiden Sie beidseitiges Rendern Ihrer Inhalte, um eine optimale Leistung zu erzielen.

### Überprüfen Ihres 3D-Modells

Überprüfen Sie das Modell, indem Sie es im 3D-Viewer (Beta) auf HoloLens öffnen. Wählen Sie die Schaltfläche **Details** aus, um die Eigenschaften des Modells und Warnungen für nicht unterstützte Inhalte anzuzeigen (sofern vorhanden).

### Rendern von 3D-Modellen mit realer Bemaßung

Standardmäßig zeigt 3D-Viewer (Beta) 3D-Modelle in komfortabler Größe und Position in Relation zur benutzenden Person an. Wenn es jedoch wichtig ist, ein 3D-Modell mit realen Maßen darzustellen (wenn Sie beispielsweise Möbelmodelle in einem Raum evaluieren), kann die/der Ersteller/in der Inhalte eine Kennzeichnung in den Metadaten der Datei festlegen, um zu verhindern, dass das Modell sowohl von der Anwendung als auch von den Benutzenden geändert wird.

Wenn Sie das Skalieren des Modells verhindern möchten, fügen Sie ein boolesches benutzerdefiniertes Attribut zu jedem Objekt in der Szene mit dem Namen Microsoft_DisableScale hinzu und legen es auf „true“ fest. 3D-Viewer (Beta) berücksichtigt dann die FbxSystemUnit-Informationen, die in der FBX-Datei gespeichert sind. Der Maßstab im 3D-Viewer (Beta) entspricht 1 m pro FBX-Einheit.

## FBX-Dateien auf HoloLens ansehen

### FBX-Datei über Microsoft Edge öffnen

FBX-Dateien können direkt über eine Website mit Microsoft Edge auf HoloLens geöffnet werden.

1. Navigieren Sie in Microsoft Edge zu der FBX-Datei auf der Webseite, die Sie anzeigen möchten.
1. Wählen Sie die Datei zum Download aus.
1. Wählen Sie nach Abschluss des Downloads die Schaltfläche **Öffnen** in Microsoft Edge aus, um die Datei im 3D-Viewer (Beta) zu öffnen.

Die heruntergeladene Datei kann später mithilfe von Downloads in Microsoft Edge aufgerufen und erneut geöffnet werden. Wenn Sie ein 3D-Modell speichern und den fortgesetzten Zugriff sicherstellen möchten, laden Sie die Datei auf Ihren Computer herunter, und speichern sie in Ihrem OneDrive-Konto. Die Datei kann dann über die OneDrive-App auf HoloLens geöffnet werden.

> [!NOTE]
> Einige Websites mit herunterladbaren FBX-Modellen stellen sie im ZIP-Format bereit. 3D-Viewer (Beta) kann ZIP-Dateien nicht direkt öffnen. Verwenden Sie stattdessen Ihren Computer, um die FBX-Datei zu extrahieren und in Ihrem OneDrive-Konto zu speichern. Die Datei kann dann über die OneDrive-App auf HoloLens geöffnet werden.

### Eine FBX-Datei über Microsoft Edge öffnen

FBX-Dateien können über OneDrive geöffnet werden, indem Sie die OneDrive-App auf HoloLens verwenden. Dazu müssen Sie OneDrive mithilfe der Microsoft Store-App auf HoloLens installiert haben und die FBX-Datei muss sich bereits auf OneDrive auf Ihrem PC befinden.

Sobald sich FBX-Dateien in OneDrive befinden, können sie auf zwei Arten auf HoloLens mit dem 3D-Viewer (Beta) geöffnet werden:

- Starten Sie OneDrive auf HoloLens und wählen Sie die FBX-Datei aus, die Sie im 3D-Viewer (Beta) öffnen möchten.
- Starten Sie den 3D-Viewer (Beta). Tippen Sie in die Luft, um die Symbolleiste anzuzeigen, und wählen Sie **Datei öffnen** aus. OneDrive wird geöffnet und Sie können eine FBX-Datei auswählen.

## Problembehandlung

### Beim Öffnen eines 3D-Modells wird eine Warnung angezeigt

Sie sehen beim Öffnen eine Warnung, wenn ein 3D-Modell von 3D-Viewer (Beta) nicht unterstützte Features enthält, oder wenn das Modell zu komplex ist und die Leistung beeinträchtigt werden kann. Der 3D-Viewer (Beta) lädt zwar weiterhin das 3D-Modell, die Leistung oder die visuelle Wiedergabetreue ist jedoch möglicherweise beeinträchtigt.

Weitere Informationen hierzu finden Sie unter [Spezifikationen für unterstützte Inhalte](#supported-content-specifications) und [Optimieren von 3D-Modellen für 3D-Viewer (Beta)](#optimizing-3d-models-for-3d-viewer-beta).

### Eine Warnung wird angezeigt und das 3D-Modell wird nicht geladen

Eine Fehlermeldung wird angezeigt, wenn der 3D-Viewer (Beta) aufgrund der Komplexität oder Dateigröße ein 3D-Modell nicht laden kann, oder wenn die FBX-Datei beschädigt oder ungültig ist. Eine Fehlermeldung wird angezeigt, wenn die maximale Anzahl von Modellen, Scheitelpunkten oder Gittermodellen erreicht ist, die gleichzeitig geöffnet sein können.  

Weitere Informationen hierzu finden Sie unter [Spezifikationen für unterstützte Inhalte](#supported-content-specifications) und [Datei- und Modellbeschränkungen](#file-and-model-limitations).

### Mein 3D-Modell wird geladen, wird jedoch nicht wie erwartet angezeigt

Wenn Ihr 3D-Modell im 3D-Viewer (Beta) nicht erwartungsgemäß aussieht, tippen Sie in die Luft, um die Symbolleiste anzuzeigen, und wählen Sie dann **Details** aus. Aspekte der Datei, die vom 3D-Viewer (Beta) nicht unterstützt werden, werden als Warnungen hervorgehoben.

Das häufigste Problem sind fehlende Texturen, weil sie wahrscheinlich nicht in die FBX-Datei eingebettet sind. In diesem Fall wird das Modell weiß angezeigt. Dieses Problem kann bei der Erstellung behoben werden. Wählen Sie dazu beim Export aus Ihrem Erstellungstool nach FBX die Option zum Einbetten der Texturen aus.

Weitere Informationen hierzu finden Sie unter [Spezifikationen für unterstützte Inhalte](#supported-content-specifications) und [Optimieren von 3D-Modellen für 3D-Viewer (Beta)](#optimizing-3d-models-for-3d-viewer-beta).

### Beim Anzeigen meines 3D-Modells sinkt die Leistung

Die Leistung beim Laden und Anzeigen eines 3D-Modells kann durch die Komplexität des Modells, die Anzahl der gleichzeitig geöffneten Modelle oder die Anzahl der Modelle mit aktiven Animationen beeinflusst werden.

Weitere Informationen hierzu finden Sie unter [Optimieren von 3D-Modellen für 3D-Viewer (Beta)](#optimizing-3d-models-for-3d-viewer-beta) und [Datei- und Modellbeschränkungen](#file-and-model-limitations).

### Wenn ich eine FBX-Datei auf HoloLens öffne, wird sie nicht im 3D-Viewer (Beta) geöffnet.

3D-Viewer (Beta) wird bei der Installation automatisch mit der Dateierweiterung FBX verknüpft.

Wenn beim Versuch eine FBX-Datei zu öffnen ein Dialogfeld angezeigt wird, das Sie zum Microsoft Store weiterleitet, dann ist derzeit keine App mit der Dateierweiterung .fbx in HoloLens verknüpft.

Stellen Sie sicher, dass 3D Viewer (Beta) installiert ist. Wenn er nicht installiert ist, laden Sie ihn aus dem Microsoft Store auf HoloLens herunter.

Wenn der 3D-Viewer (Beta) bereits installiert ist, starten Sie ihn, und versuchen Sie erneut, die Datei zu öffnen. Wenn das Problem weiterhin besteht, deinstallieren Sie 3D-Viewer (Beta), und installieren ihn neu. Dadurch wird die FBX-Dateierweiterung mit 3D-Viewer (Beta) verknüpft.

Wenn beim Versuch, eine FBX-Datei zu öffnen, eine andere App als 3D-Viewer (Beta) geöffnet wird, wurde diese App wahrscheinlich nach dem 3D-Viewer (Beta) installiert und hat die Zuordnung zur Dateierweiterung FBX übernommen. Wenn der 3D-Viewer (Beta) der Dateierweiterung FBX zugeordnet werden soll, deinstallieren und installieren Sie ihn neu.

### Die Schaltfläche „Datei öffnen“ im 3D-Viewer (Beta) öffnet keine App.

Die Schaltfläche **Datei öffnen** öffnet die App, die mit der Dateiauswahl-Funktion in HoloLens verknüpft ist. Wenn OneDrive installiert ist, sollte die Schaltfläche **Datei öffnen** OneDrive starten. Wenn derzeit keine App mit der Dateiauswahl-Funktion verknüpft ist, die auf HoloLens installiert ist, werden Sie zum Microsoft Store weitergeleitet.

Wenn die Schaltfläche **Datei öffnen** eine andere App als OneDrive startet, wurde diese App wahrscheinlich nach OneDrive installiert und hat die Zuordnung zur Dateiauswahl-Funktion übernommen. Wenn OneDrive starten soll, wenn Sie die Schaltfläche **Datei öffnen** im 3D-Viewer (Beta) auswählen, deinstallieren Sie OneDrive, und installieren Sie es neu.

Wenn die Schaltfläche **Datei öffnen** nicht aktiv ist, haben Sie möglicherweise die maximale Anzahl von Modellen erreicht, die gleichzeitig im 3D-Viewer (Beta) geöffnet sein kann. Wenn im 3D-Viewer (Beta) 40 Modelle geöffnet sind, müssen Sie einige schließen, bevor Sie weitere öffnen können.

## Zusätzliche Ressourcen

- [Support-Foren](http://forums.hololens.com/categories/3d-viewer-beta) – nur für Archivierungszwecke. Dieses Forum ist nicht mehr aktiv.
- [Hinweise von Drittanbietern](https://www.microsoft.com/{lang-locale}/legal/products)
