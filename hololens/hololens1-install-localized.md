---
title: Installieren lokalisierter Versionen von HoloLens
description: Erfahren Sie, wie Sie die lokalisierten Versionen von HoloLens (1. Generation), einschließlich chinesischer und japanischer Versionen, installieren.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: fe29e4ed611f86764f0db576b1a8794fa0ceec3047cadd26f502209faadea8b0
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661803"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Installieren lokalisierter Versionen von HoloLens (1. Generation)

Um zur chinesischen oder japanischen Version von HoloLens zu wechseln, müssen Sie das Windows Device Recovery Tool (WDRT) verwenden, um den Build für die Sprache auf einen PC herunterzuladen und ihn dann auf Ihrem Computer HoloLens.

> [!IMPORTANT]
> Durch die Verwendung von WDRT zum Installieren der chinesischen oder japanischen Builds von HoloLens vorhandene Daten, z. B. persönliche Dateien und Einstellungen, aus Ihrer HoloLens. 

1. Laden Sie auf Ihrem PC das [WDRT (Device Recovery Tool Windows) herunter,](https://support.microsoft.com/help/12379)und installieren Sie es.
1. Laden Sie das Paket für die Sprache herunter, die Sie auf Ihren PC laden möchten: [Vereinfachtes Chinesisch](https://aka.ms/hololensdownload-ch) oder [Japanisch.](https://aka.ms/hololensdownload-jp)
1. Wenn der Download abgeschlossen ist, wählen Sie **Datei-Explorer**  >  **Downloads aus.** Klicken Sie mit der rechten Maustaste auf den zip-Ordner, den Sie gerade heruntergeladen haben, und wählen Sie **Alle** extrahieren  >  **aus,** um ihn zu entzippen.
1. Verbinden Sie HoloLens micro-USB-Kabel an Ihren PC weiter. (Auch wenn Sie andere Kabel verwendet haben, um Ihre Verbindung HoloLens, funktioniert dies am besten.)
1. Nachdem das Tool Ihre Daten automatisch erkannt HoloLens, wählen Sie die kachel Microsoft HoloLens aus.
1. Wählen Sie auf dem nächsten Bildschirm **Manuelle** Paketauswahl und dann die Installationsdatei aus, die sich in dem Ordner befindet, den Sie in Schritt   4 entpackt haben. (Suchen Sie nach einer Datei mit der Erweiterung ".ffu".) 
1. Wählen Sie **Software installieren aus,** und befolgen Sie die Anweisungen. 
1. Nachdem der Build installiert wurde, HoloLens das Setup automatisch gestartet. Setzen Sie das Gerät ein, und befolgen Sie die Einrichtungsrichtungen. 

Wenn Sie mit dem Setup fertig sind, wechseln Sie zu **Einstellungen**  >  **Update & Security** Windows Insider  >  **Program,** und überprüfen Sie, ob Sie für den Empfang der neuesten Vorschauversionen konfiguriert sind. Wie die englischen Vorschauversionen hält das Windows Insider-Programm die chinesischen und japanischen Versionen von HoloLens mit den neuesten Vorschauversionen auf dem neuesten Stand.

> [!NOTE]
>  
> - Sie können die Einstellungen-App nicht verwenden, um die Systemsprache zwischen Englisch, Japanisch und Chinesisch zu ändern. Das Flashen eines neuen Build ist die einzige unterstützte Möglichkeit, die Gerätesystemsprache zu ändern.
> - Während Sie die Pinyin-Tastatur auf dem Bildschirm verwenden können, um vereinfachten chinesischen oder japanischen Text eineingaben zu können, wird die Verwendung einer Bluetooth-Hardwaretastatur zum Eingeben von vereinfachtem chinesischem oder japanischem Text derzeit nicht unterstützt.  Auf chinesisch oder japanisch HoloLens können Sie jedoch weiterhin eine Bluetooth-Tastatur verwenden, um Englisch eineingaben zu können (um eine Hardwaretastatur für die Eingabe in Englisch umschalten, drücken Sie die Taste ~).
