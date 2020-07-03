---
title: Verwenden des 3D-Viewers mit HoloLens (1. Generation)
description: Beschreibt die Dateitypen und Features, die vom 3D-Viewer auf HoloLens (1. Generation) unterstützt werden, sowie Informationen zur Verwendung und Problembehandlung für die App.
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
ms.openlocfilehash: 47fe1fd5dc164c56ce22a09d7edf5bffdb60ea14
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828173"
---
# Verwenden des 3D-Viewers mit HoloLens (1. Generation)

3D-Viewer ermöglicht das Anzeigen von 3D-Modellen auf HoloLens (1. Generation). Sie können *unterstütze* FBX-Dateien von Microsoft Edge, OneDrive und anderen Apps öffnen und anzeigen.

>[!NOTE]
>Dieser Artikel bezieht sich auf die immersive Einheit **3D-Viewer**-APP, die FBX-Dateien unterstützt und nur auf HoloLens (1. Generation) verfügbar ist. Die vorinstallierte **3D-Viewer**-App auf HoloLens 2 unterstützt das Öffnen von benutzerdefinierten GLB 3D-Modellen in der Mixed-Reality-Startseite (Weitere Informationen finden Sie unter [Übersicht über die Asset-Voraussetzungen](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview)).

Wenn Sie Probleme beim Öffnen eines 3D-Modells in 3D-Viewer haben oder bestimmte Features Ihres 3D-Modells nicht unterstützt werden, lesen Sie die[Spezifikationen für unterstützte Inhalte](#supported-content-specifications).

Informationen zum Erstellen oder Optimieren von 3D-Modellen zur Verwendung mit 3D-Viewer finden Sie unter [Optimieren von 3D-Modellen für 3D-Viewer](#optimizing-3d-models-for-3d-viewer).

Es gibt zwei Möglichkeiten, um ein 3D-Modell auf HoloLens zu öffnen. Weitere Informationen hierzu finden Sie unter [Anzeigen von FBX-Dateien auf HoloLens](#viewing-fbx-files-on-hololens).

Wenn Sie nach dem Lesen dieser Themen Probleme haben, lesen Sie [Problembehandlung](#troubleshooting).

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

Es gibt feste Beschränkungen hinsichtlich der Dateigröße sowie der Anzahl der Modelle, Scheitelpunkte und Gittermodelle, die im 3D-Viewer gleichzeitig geöffnet sein können:

- 500MB maximale Dateigröße pro Modell
- Scheitelpunkte:600.000insgesamt in allen geöffneten Modellen
- Gittermodelle:1.600insgesamt in allen geöffneten Modellen
- Höchstens 40 Modelle gleichzeitig geöffnet

## Optimieren von 3D-Modellen für 3D-Viewer

### Praktische Überlegungen

- Vermeiden Sie schwarze Materialien oder schwarze Bereiche in Textkurkarten. Hologramme bestehen aus Licht. Deshalb rendert HoloLens schwarz (die Abwesenheit von Licht) als transparent.
- Vergewissern Sie sich vor dem Exportieren nach FBX aus dem Erstellungstool, dass alle Geometrien sichtbar und entriegelt sind und keine Ebenen, die Geometrie enthalten, deaktiviert oder mit einer Vorlage versehen sind. Sichtbarkeit wird nicht beachtet.
- Vermeiden Sie sehr große Translation-Offsets zwischen den Knoten (beispielsweise 100.000Einheiten). Das kann dazu führen, dass das Modell während des Verschiebens/Skalierens/Drehens wackelt.

### Leistungsoptimierung

Berücksichtigen Sie beim Erstellen von Inhalten und überprüfen Sie in der 3D-Viewer-App auf HoloLens während des Erstellungsprozesses die Leistung, um optimale Ergebnisse zu erzielen. 3D-Viewer rendert Inhalte in Echtzeit. Die Leistung unterliegt den HoloLens-Hardwarefunktionen.  

Ein 3D-Modell enthält zahlreiche Variablen, die sich auf die Leistung auswirken können. Im 3D-Viewer wird beim Laden eine Warnung angezeigt, wenn mehr als 150.000Scheitelpunkte oder mehr als 400 Gittermodelle vorhanden sind. Animationen können sich auf die Leistung anderer offener Modelle auswirken. Es gibt feste Beschränkungen hinsichtlich der Dateigröße sowie der Anzahl der Modelle, Scheitelpunkte und Gittermodelle, die im 3D-Viewer gleichzeitig geöffnet sein können (siehe [Datei- und Modellbeschränkungen](#file-and-model-limitations)).  

Wenn das 3D-Modell aufgrund der Komplexität des Modells nicht ordnungsgemäß ausgeführt wird, ziehen Sie Folgendes in Betracht:

- Reduzieren der Polygonanzahl
- Verringern der Anzahl von Bones in manipulierten Animationen
- Vermeiden von Selbstokklusion

Das beidseitige Rendering wird im 3D-Viewer unterstützt, obwohl es aus Leistungsgründen standardmäßig deaktiviert ist. Das kann über die Schaltfläche **Beidseitig** auf der Seite **Details** aktiviert werden. Vermeiden Sie beidseitiges Rendern Ihrer Inhalte, um eine optimale Leistung zu erzielen.

### Überprüfen Ihres 3D-Modells

Überprüfen Sie das Modell, indem Sie es im 3D-Viewer auf HoloLens öffnen. Wählen Sie die Schaltfläche **Details** aus, um die Eigenschaften des Modells und Warnungen für nicht unterstützte Inhalte anzuzeigen (sofern vorhanden).

### Rendern von 3D-Modellen mit realer Bemaßung

Standardmäßig zeigt 3D-Viewer 3D-Modelle in komfortabler Größe und Position in Relation zur benutzenden Person an. Wenn es jedoch wichtig ist, ein 3D-Modell mit realen Maßen darzustellen (wenn Sie beispielsweise Möbelmodelle in einem Raum evaluieren), kann die/der Ersteller/in der Inhalte eine Kennzeichnung in den Metadaten der Datei festlegen, um zu verhindern, dass das Modell sowohl von der Anwendung als auch von den Benutzenden geändert wird.

Wenn Sie das Skalieren des Modells verhindern möchten, fügen Sie ein boolesches benutzerdefiniertes Attribut zu jedem Objekt in der Szene mit dem Namen Microsoft_DisableScale hinzu und legen es auf „true“ fest. 3D-Viewer berücksichtigt dann die FbxSystemUnit-Informationen, die in der FBX-Datei gespeichert sind. Der Maßstab im 3D-Viewer entspricht 1 m pro FBX-Einheit.

## FBX-Dateien auf HoloLens ansehen

### FBX-Datei über Microsoft Edge öffnen

FBX-Dateien können direkt über eine Website mit Microsoft Edge auf HoloLens geöffnet werden.

1. Navigieren Sie in Microsoft Edge zu der FBX-Datei auf der Webseite, die Sie anzeigen möchten.
1. Wählen Sie die Datei zum Download aus.
1. Wählen Sie nach Abschluss des Downloads die Schaltfläche **Öffnen** in Microsoft Edge aus, um die Datei im 3D-Viewer zu öffnen.

Die heruntergeladene Datei kann später mithilfe von Downloads in Microsoft Edge aufgerufen und erneut geöffnet werden. Wenn Sie ein 3D-Modell speichern und den fortgesetzten Zugriff sicherstellen möchten, laden Sie die Datei auf Ihren Computer herunter, und speichern sie in Ihrem OneDrive-Konto. Die Datei kann dann über die OneDrive-App auf HoloLens geöffnet werden.

> [!NOTE]
> Einige Websites mit herunterladbaren FBX-Modellen stellen sie im ZIP-Format bereit. 3D-Viewer kann ZIP-Dateien nicht direkt öffnen. Verwenden Sie stattdessen Ihren Computer, um die FBX-Datei zu extrahieren und in Ihrem OneDrive-Konto zu speichern. Die Datei kann dann über die OneDrive-App auf HoloLens geöffnet werden.

### Eine FBX-Datei über Microsoft Edge öffnen

FBX-Dateien können über OneDrive geöffnet werden, indem Sie die OneDrive-App auf HoloLens verwenden. Dazu müssen Sie OneDrive mithilfe der Microsoft Store-App auf HoloLens installiert haben und die FBX-Datei muss sich bereits auf OneDrive auf Ihrem PC befinden.

Sobald sich FBX-Dateien in OneDrive befinden, können sie auf zwei Arten auf HoloLens mit dem 3D-Viewer geöffnet werden:

- Starten Sie OneDrive auf HoloLens und wählen Sie die FBX-Datei aus, die Sie im 3D-Viewer öffnen möchten.
- Starten Sie den 3D-Viewer. Tippen Sie in die Luft, um die Symbolleiste anzuzeigen, und wählen Sie **Datei öffnen**aus. OneDrive wird geöffnet und Sie können eine FBX-Datei auswählen.

## Problembehandlung

### Beim Öffnen eines 3D-Modells wird eine Warnung angezeigt

Sie sehen beim Öffnen eine Warnung, wenn ein 3D-Modell nicht von 3D-Viewer unterstützte Features enthält, oder wenn das Modell zu komplex ist und die Leistung beeinträchtigt werden kann. Der 3D-Viewer lädt zwar weiterhin das 3D-Modell, die Leistung oder die visuelle Wiedergabetreue ist jedoch möglicherweise beeinträchtigt.

Weitere Informationen hierzu finden Sie unter [Spezifikationen für unterstützte Inhalte](#supported-content-specifications) und [Optimieren von 3D-Modellen für 3D-Viewer](#optimizing-3d-models-for-3d-viewer).

### Eine Warnung wird angezeigt und das 3D-Modell wird nicht geladen

Eine Fehlermeldung wird angezeigt, wenn der 3D-Viewer aufgrund der Komplexität oder Dateigröße ein 3D-Modell nicht laden kann oder wenn die FBX-Datei fehlerhaft oder ungültig ist. Eine Fehlermeldung wird angezeigt, wenn die maximale Anzahl von Modellen, Scheitelpunkten oder Gittermodellen erreicht ist, die gleichzeitig geöffnet sein können.  

Weitere Informationen hierzu finden Sie unter [Spezifikationen für unterstützte Inhalte](#supported-content-specifications) und [Datei- und Modellbeschränkungen](#file-and-model-limitations).

Wenn Sie der Meinung sind, dass Ihr Modell die Spezifikationen für unterstützte Inhalte erfüllt und die Datei- oder Modellbeschränkungen nicht überschritten hat, können Sie Ihre FBX-Datei an das 3D-Viewer-Team unter holoapps@Microsoft.com senden. Wir können nicht persönlich antworten. Beispiele von Dateien, die nicht ordnungsgemäß geladen werden, helfen uns bei der Verbesserung zukünftiger Versionen der App.

### Mein 3D-Modell wird geladen, wird jedoch nicht wie erwartet angezeigt

Wenn Ihr 3D-Modell im 3D-Viewer nicht erwartungsgemäß aussieht, tippen Sie in die Luft, um die Symbolleiste anzuzeigen, und wählen Sie dann **Details**aus. Aspekte der Datei, die vom 3D-Viewer nicht unterstützt werden, werden als Warnungen hervorgehoben.

Das häufigste Problem sind fehlende Texturen, weil sie wahrscheinlich nicht in die FBX-Datei eingebettet sind. In diesem Fall wird das Modell weiß angezeigt. Dieses Problem kann bei der Erstellung behoben werden. Wählen Sie dazu beim Export aus Ihrem Erstellungstool nach FBX die Option zum Einbetten der Texturen aus.

Weitere Informationen hierzu finden Sie unter [Spezifikationen für unterstützte Inhalte](#supported-content-specifications) und [Optimieren von 3D-Modellen für 3D-Viewer](#optimizing-3d-models-for-3d-viewer).

### Beim Anzeigen meines 3D-Modells sinkt die Leistung

Die Leistung beim Laden und Anzeigen eines 3D-Modells kann durch die Komplexität des Modells, die Anzahl der gleichzeitig geöffneten Modelle oder die Anzahl der Modelle mit aktiven Animationen beeinflusst werden.

Weitere Informationen hierzu finden Sie unter [Optimieren von 3D-Modellen für 3D-Viewer](#optimizing-3d-models-for-3d-viewer) und [Datei- und Modellbeschränkungen](#file-and-model-limitations).

### Wenn ich eine FBX-Datei auf HoloLens öffne, wird sie nicht im 3D-Viewer geöffnet.

3D-Viewer wird bei der Installation automatisch mit der Dateierweiterung FBX verknüpft.

Wenn beim Versuch eine FBX-Datei zu öffnen ein Dialogfeld angezeigt wird, das Sie zum Microsoft Store weiterleitet, dann ist derzeit keine App mit der Dateierweiterung .fbx in HoloLens verknüpft.

Stellen Sie sicher, dass 3D Viewer installiert ist. Wenn er nicht installiert ist, laden Sie ihn aus dem Microsoft Store auf HoloLens herunter.

Wenn der 3D-Viewer bereits installiert ist, starten Sie den 3D-Viewer und versuchen Sie erneut, die Datei zu öffnen. Wenn das Problem weiterhin besteht, deinstallieren Sie 3D-Viewer und installieren ihn neu. Dadurch wird die FBX-Dateierweiterung mit 3D-Viewer verknüpft.

Wenn beim Versuch, eine FBX-Datei zu öffnen, eine andere App als 3D-Viewer geöffnet wird, wurde diese App wahrscheinlich nach 3D-Viewer installiert und hat die Zuordnung zur Dateierweiterung .fbx übernommen. Wenn 3D-Viewer der Dateierweiterung FBX zugeordnet werden soll, deinstallieren Sie 3D-Viewer und installieren ihn neu.

### Die Schaltfläche „Datei öffnen“ im 3D-Viewer startet keine App.

Die Schaltfläche **Datei öffnen** öffnet die App, die mit der Dateiauswahl-Funktion in HoloLens verknüpft ist. Wenn OneDrive installiert ist, sollte die Schaltfläche **Datei öffnen** OneDrive starten. Wenn derzeit keine App mit der Dateiauswahl-Funktion verknüpft ist, die auf HoloLens installiert ist, werden Sie zum Microsoft Store weitergeleitet.

Wenn die Schaltfläche **Datei öffnen** eine andere App als OneDrive startet, wurde diese App wahrscheinlich nach OneDrive installiert und hat die Zuordnung zur Dateiauswahl-Funktion übernommen. Wenn OneDrive starten soll wenn Sie die Schaltfläche **Datei öffnen** im 3D-Viewer auswählen, deinstallieren Sie OneDrive und installieren es neu.

Wenn die Schaltfläche **Datei öffnen** nicht aktiv ist, haben Sie möglicherweise die maximale Anzahl von Modellen erreicht, die gleichzeitig im 3D-Viewer geöffnet sein kann. Wenn im 3D-Viewer 40-Modelle geöffnet sind, müssen Sie einige schließen, bevor Sie weitere Modelle öffnen können.

## Zusätzliche Ressourcen

- [Supportforen](http://forums.hololens.com/categories/3d-viewer-beta)
- [Hinweise von Drittanbietern](https://www.microsoft.com/{lang-locale}/legal/products)
