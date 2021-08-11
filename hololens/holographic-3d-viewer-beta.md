---
title: Verwenden des 3D-Viewers (Beta) mit HoloLens (1. Generation)
description: Beschreibt die Dateitypen und Features, die vom 3D-Viewer (Beta) auf HoloLens (1. Generation) unterstützt werden, sowie Informationen zur Verwendung und Problembehandlung für die App.
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
ms.openlocfilehash: d25a87bd210535e36e18f165b5461141c40aa292a07c560018ba7c0cbf76f6ba
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664926"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>Verwenden des 3D-Viewers (Beta) mit HoloLens (1. Generation)

3D-Viewer (Beta) ermöglicht das Anzeigen von 3D-Modellen auf HoloLens (1. Generation). Sie können *unterstützte* FBX-Dateien von Microsoft Edge, OneDrive und anderen Apps öffnen und anzeigen.

>[!NOTE]
>Dieser Artikel bezieht sich auf die immersive Unity-App **3D-Viewer (Beta)** , die FBX-Dateien unterstützt und nur auf HoloLens (1. Generation) verfügbar ist. Die vorinstallierte App **3D Viewer** auf HoloLens 2 unterstützt das Öffnen benutzerdefinierter GLB-3D-Modelle in der Mixed Reality-Startumgebung (weitere Informationen finden Sie unter [Ressourcenanforderungen – Übersicht](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview).

>[!IMPORTANT]
>Der 3D Viewer (Beta) bleibt zwar möglicherweise im Microsoft Store für HoloLens (1. Generation) weiterhin verfügbar, sie wird aber nicht mehr aktiv weiterentwickelt und auch nicht mehr unterstützt.

Wenn es beim Öffnen eines 3D-Modells im 3D-Viewer (Beta) Probleme gibt oder bestimmte Features Ihres 3D-Modells nicht unterstützt werden, lesen Sie die[Spezifikationen für unterstützte Inhalte](#supported-content-specifications) weiter unten.

Informationen zum Erstellen oder Optimieren von 3D-Modellen für die Verwendung mit 3D-Viewer (Beta) finden Sie weiter unten unter [Optimieren von 3D-Modellen für 3D-Viewer (Beta)](#optimizing-3d-models-for-3d-viewer-beta).

Es gibt zwei Möglichkeiten, um ein 3D-Modell auf HoloLens zu öffnen. Mehr dazu erfahren Sie weiter unten unter [Anzeigen von FBX-Dateien auf HoloLens](#viewing-fbx-files-on-hololens).

Wenn Sie nach dem Lesen dieser Themen Probleme haben, finden Sie weitere Informationen unter [Problembehandlung](#troubleshooting) weiter unten.

## <a name="supported-content-specifications"></a>Spezifikationen für unterstützte Inhalte

### <a name="file-format"></a>Dateiformat

- FBX-Format
- Maximale FBX-Version 2015.1.0

### <a name="file-size"></a>Dateigröße

- Mindestens 5 KB
- Höchstens 500 MB

### <a name="geometry"></a>Geometrie

- Nur Polygonmodelle. Keine Unterteilungsflächen oder NURBs
- Rechtshändiges Koordinatensystem
- Scheren in Transformationsmatrizen werden nicht unterstützt.

### <a name="textures"></a>Texturen

- Texturkarten müssen in die FBX-Datei eingebettet sein
- Unterstützte Bildformate
  - JPEG- und PNG-Bilder
  - BMP-Bilder (24-Bit RGB-True-Color)
  - TGA-Bilder (24-Bit RGB- und 32-Bit RGBQ-True-Color)
- Maximale Texturauflösung von 2048 x 2048
- Maximale Anzahl einer Texturkarte, einer normalen Karte und einer Reflexionswürfelkarte pro Gittermodell
- Alpha-Kanal in diffusen Texturen bewirkt, dass Pixel unter 50 % verworfen werden

### <a name="animation"></a>Animation

- Skalieren/Drehung/Translation von Animationen auf einzelne Objekte
- Skelettartige (manipulierte) Animation unter Anwendung von Skins
  - Maximal 4 Einflüsse pro Scheitelpunkt

### <a name="materials"></a>Materialien

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

### <a name="file-and-model-limitations"></a>Datei- und Modellbeschränkungen

Es gibt feste Beschränkungen hinsichtlich der Dateigröße sowie der Anzahl der Modelle, Scheitelpunkte und Gittermodelle, die im 3D-Viewer (Beta) gleichzeitig geöffnet sein können:

- 500 MB maximale Dateigröße pro Modell
- Scheitelpunkte: 600.000 insgesamt in allen geöffneten Modellen
- Gittermodelle: 1.600 insgesamt in allen geöffneten Modellen
- Höchstens 40 Modelle gleichzeitig geöffnet

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a>Optimieren von 3D-Modellen für 3D-Viewer (Beta)

### <a name="special-considerations"></a>Besondere Überlegungen

- Vermeiden Sie schwarze Materialien oder schwarze Bereiche in Textkurkarten. Hologramme bestehen aus Licht. Deshalb rendert HoloLens schwarz (die Abwesenheit von Licht) als transparent.
- Vergewissern Sie sich vor dem Exportieren nach FBX aus dem Erstellungstool, dass alle Geometrien sichtbar und entriegelt sind und keine Ebenen, die Geometrie enthalten, deaktiviert oder mit einer Vorlage versehen sind. Sichtbarkeit wird nicht beachtet.
- Vermeiden Sie sehr große Translation-Offsets zwischen den Knoten (beispielsweise 100.000 Einheiten). Das kann dazu führen, dass das Modell beim Verschieben/Skalieren/Drehen wackelt.

### <a name="performance-optimization"></a>Leistungsoptimierung

Berücksichtigen Sie beim Erstellen von Inhalten die Leistung, und überprüfen Sie sie während des Erstellungsprozesses in der 3D-Viewer-App (Beta) auf HoloLens, um optimale Ergebnisse zu erzielen. 3D-Viewer (Beta) rendert Inhalte in Echtzeit. Die Leistung ist an die HoloLens-Hardwarefunktionen gebunden.  

Ein 3D-Modell enthält zahlreiche Variablen, die sich auf die Leistung auswirken können. Im 3D-Viewer (Beta) wird beim Laden eine Warnung angezeigt, wenn mehr als 150.000 Scheitelpunkte oder mehr als 400 Gittermodelle vorhanden sind. Animationen können sich auf die Leistung anderer geöffneter Modelle auswirken. Es gibt feste Beschränkungen hinsichtlich der Dateigröße sowie der Anzahl der Modelle, Scheitelpunkte und Gittermodelle, die in 3D-Viewer (Beta) gleichzeitig geöffnet sein können (siehe [Datei- und Modellbeschränkungen](#file-and-model-limitations)).  

Wenn das 3D-Modell aufgrund der Komplexität des Modells nicht ordnungsgemäß ausgeführt wird, ziehen Sie Folgendes in Betracht:

- Reduzieren der Polygonanzahl
- Verringern der Anzahl von Knochen in Rigging-Animationen
- Vermeiden von Selbstokklusion

Das beidseitige Rendering wird im 3D-Viewer (Beta) unterstützt, aus Leistungsgründen ist es jedoch standardmäßig deaktiviert. Es kann über die Schaltfläche **Doppelseitig** auf der Seite **Details** aktiviert werden. Vermeiden Sie das Erfordernis von beidseitigem Rendering Ihrer Inhalte, um eine optimale Leistung zu erzielen.

### <a name="validating-your-3d-model"></a>Überprüfen Ihres 3D-Modells

Überprüfen Sie das Modell, indem Sie es im 3D-Viewer (Beta) auf HoloLens öffnen. Wählen Sie die Schaltfläche **Details** aus, um die Eigenschaften des Modells und Warnungen für nicht unterstützte Inhalte anzuzeigen (sofern vorhanden).

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>Rendern von 3D-Modellen mit realer Bemaßung

Standardmäßig zeigt 3D-Viewer (Beta) 3D-Modelle in komfortabler Größe und Position in Relation zur benutzenden Person an. Wenn es jedoch wichtig ist, ein 3D-Modell mit realen Maßen darzustellen (wenn Sie beispielsweise Möbelmodelle in einem Raum evaluieren), kann die/der Ersteller/in der Inhalte in den Metadaten der Datei eine Kennzeichnung festlegen, um eine Größenänderung des Modells durch die Anwendung oder die Benutzer zu verhindern.

Wenn Sie das Skalieren des Modells verhindern möchten, fügen Sie jedem Objekt in der Szene ein boolesches benutzerdefiniertes Attribut mit dem Namen „Microsoft_DisableScale“ hinzu und legen es auf „True“ fest. 3D-Viewer (Beta) berücksichtigt dann die FbxSystemUnit-Informationen, die in der FBX-Datei gespeichert sind. Der Maßstab in 3D-Viewer (Beta) entspricht 1 m pro FBX-Einheit.

## <a name="viewing-fbx-files-on-hololens"></a>Anzeigen von FBX-Dateien auf HoloLens

### <a name="open-an-fbx-file-from-microsoft-edge"></a>Öffnen einer FBX-Datei über Microsoft Edge

FBX-Dateien können direkt von einer Website mithilfe von Microsoft Edge auf HoloLens geöffnet werden.

1. Navigieren Sie in Microsoft Edge zu der Webseite mit der FBX-Datei, die Sie anzeigen möchten.
1. Wählen Sie die Datei zum Download aus.
1. Wählen Sie nach Abschluss des Downloads die Schaltfläche **Öffnen** in Microsoft Edge aus, um die Datei im 3D-Viewer (Beta) zu öffnen.

Die heruntergeladene Datei kann später mithilfe von „Downloads“ in Microsoft Edge aufgerufen und erneut geöffnet werden. Wenn Sie ein 3D-Modell speichern und den fortgesetzten Zugriff sicherstellen möchten, laden Sie die Datei auf Ihren Computer herunter, und speichern sie in Ihrem OneDrive-Konto. Die Datei kann dann über die OneDrive-App auf HoloLens geöffnet werden.

> [!NOTE]
> Einige Websites mit herunterladbaren FBX-Modellen stellen sie im komprimierten ZIP-Format bereit. 3D-Viewer (Beta) kann ZIP-Dateien nicht direkt öffnen. Verwenden Sie stattdessen Ihren Computer, um die FBX-Datei zu extrahieren und in Ihrem OneDrive-Konto zu speichern. Die Datei kann dann über die OneDrive-App auf HoloLens geöffnet werden.

### <a name="open-an-fbx-file-from-onedrive"></a>Öffnen einer FBX-Datei von OneDrive

FBX-Dateien lassen sich mithilfe der OneDrive-App auf HoloLens von OneDrive öffnen. Dazu müssen Sie OneDrive mithilfe der Microsoft Store-App auf HoloLens installiert haben, und Sie müssen die FBX-Datei bereits mit Ihrem PC auf OneDrive hochgeladen haben.

Sobald sich FBX-Dateien in OneDrive befinden, können sie auf HoloLens auf zwei Arten mit dem 3D-Viewer (Beta) geöffnet werden:

- Starten Sie OneDrive auf HoloLens, und wählen Sie die FBX-Datei aus, die Sie in 3D-Viewer (Beta) öffnen möchten.
- Starten Sie den 3D-Viewer (Beta). Tippen Sie in die Luft, um die Symbolleiste anzuzeigen, und wählen Sie **Datei öffnen** aus. OneDrive wird gestartet, und Sie können eine FBX-Datei auswählen.

## <a name="troubleshooting"></a>Problembehandlung

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>Beim Öffnen eines 3D-Modells wird eine Warnung angezeigt

Sie sehen beim Öffnen eine Warnung, wenn ein 3D-Modell von 3D-Viewer (Beta) nicht unterstützte Features enthält, oder wenn das Modell zu komplex ist und die Leistung beeinträchtigt werden kann. 3D-Viewer (Beta) lädt zwar weiterhin das 3D-Modell, die Leistung oder die visuelle Wiedergabetreue ist jedoch möglicherweise beeinträchtigt.

Weitere Informationen finden Sie unter [Spezifikationen für unterstützte Inhalte](#supported-content-specifications) und [Optimieren von 3D-Modellen für 3D-Viewer (Beta)](#optimizing-3d-models-for-3d-viewer-beta).

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>Eine Warnung wird angezeigt, und das 3D-Modell wird nicht geladen

Es wird eine Fehlermeldung angezeigt, wenn 3D-Viewer (Beta) ein 3D-Modell aufgrund der Komplexität oder Dateigröße nicht laden kann, oder wenn die FBX-Datei beschädigt oder ungültig ist. Ferner wird eine Fehlermeldung angezeigt, wenn die maximale Anzahl von Modellen, Scheitelpunkten oder Gittermodellen erreicht ist, die gleichzeitig geöffnet sein können.  

Weitere Informationen finden Sie unter [Spezifikationen für unterstützte Inhalte](#supported-content-specifications) und [Datei- und Modelleinschränkungen](#file-and-model-limitations).

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>Mein 3D-Modell wird geladen, es wird jedoch nicht wie erwartet angezeigt

Wenn Ihr 3D-Modell in 3D-Viewer (Beta) nicht erwartungsgemäß aussieht, tippen Sie in die Luft, um die Symbolleiste anzuzeigen, und wählen Sie dann **Details** aus. Aspekte der Datei, die von 3D-Viewer (Beta) nicht unterstützt werden, werden als Warnungen hervorgehoben.

Das häufigste Problem sind fehlende Texturen, wahrscheinlich, weil sie nicht in die FBX-Datei eingebettet sind. In diesem Fall wird das Modell weiß angezeigt. Dieses Problem kann bei der Erstellung behoben werden. Wählen Sie dazu beim Export aus Ihrem Erstellungstool nach FBX die Option zum Einbetten der Texturen aus.

Weitere Informationen finden Sie unter [Spezifikationen für unterstützte Inhalte](#supported-content-specifications) und [Optimieren von 3D-Modellen für 3D-Viewer (Beta)](#optimizing-3d-models-for-3d-viewer-beta).

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>Beim Anzeigen meines 3D-Modells sinkt die Leistung

Die Leistung beim Laden und Anzeigen eines 3D-Modells kann durch die Komplexität des Modells, die Anzahl der gleichzeitig geöffneten Modelle oder die Anzahl der Modelle mit aktiven Animationen beeinflusst werden.

Weitere Informationen finden Sie unter [Optimieren von 3D-Modellen für 3D-Viewer (Beta)](#optimizing-3d-models-for-3d-viewer-beta) und [Datei- und Modelleinschränkungen](#file-and-model-limitations).

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>Wenn ich eine FBX-Datei auf HoloLens öffne, wird sie nicht in 3D-Viewer (Beta) geöffnet.

3D-Viewer (Beta) wird bei der Installation automatisch mit der Dateierweiterung FBX verknüpft.

Wenn beim Versuch eine FBX-Datei zu öffnen ein Dialogfeld angezeigt wird, das Sie zum Microsoft Store weiterleitet, dann ist derzeit keine App mit der Dateierweiterung FBX in HoloLens verknüpft.

Vergewissern Sie sich, dass 3D Viewer (Beta) installiert ist. Wenn er nicht installiert ist, laden Sie ihn aus dem Microsoft Store auf HoloLens herunter.

Wenn 3D-Viewer (Beta) bereits installiert ist, starten Sie ihn, und versuchen Sie dann erneut, die Datei zu öffnen. Wenn das Problem weiterhin besteht, deinstallieren Sie 3D-Viewer (Beta), und installieren ihn neu. Dadurch wird die FBX-Dateierweiterung mit 3D-Viewer (Beta) verknüpft.

Wenn beim Versuch, eine FBX-Datei zu öffnen, eine andere App als 3D-Viewer (Beta) geöffnet wird, wurde diese App wahrscheinlich nach 3D-Viewer (Beta) installiert und hat die Zuordnung zur Dateierweiterung FBX übernommen. Wenn 3D-Viewer (Beta) der Dateierweiterung FBX zugeordnet werden soll, deinstallieren und installieren Sie ihn neu.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>Die Schaltfläche „Datei öffnen“ in 3D-Viewer (Beta) öffnet keine App.

Mit der Schaltfläche **Datei öffnen** wird die App geöffnet, die mit der Dateiauswahl-Funktion in HoloLens verknüpft ist. Wenn OneDrive installiert ist, sollte mit der Schaltfläche **Datei öffnen** OneDrive gestartet werden. Wenn derzeit keine auf HoloLens installierte App mit der Dateiauswahl-Funktion verknüpft ist, werden Sie zum Microsoft Store weitergeleitet.

Wenn die Schaltfläche **Datei öffnen** eine andere App als OneDrive startet, wurde diese App wahrscheinlich nach OneDrive installiert und hat die Zuordnung zur Dateiauswahl-Funktion übernommen. Wenn beim Auswählen der Schaltfläche **Datei öffnen** in 3D-Viewer (Beta) OneDrive gestartet werden soll, deinstallieren Sie OneDrive, und installieren Sie es neu.

Wenn die Schaltfläche **Datei öffnen** nicht aktiv ist, haben Sie möglicherweise die maximale Anzahl Modelle erreicht, die in 3D-Viewer (Beta) gleichzeitig geöffnet sein kann. Wenn in 3D-Viewer (Beta) 40 Modelle geöffnet sind, müssen Sie einige schließen, bevor Sie weitere öffnen können.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- [Supportforen](http://forums.hololens.com/categories/3d-viewer-beta): Nur zu Archivierungszwecken. Dieses Forum ist nicht mehr aktiv.
- [Hinweise zu Drittanbietern](https://www.microsoft.com/{lang-locale}/legal/products)
