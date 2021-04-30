---
title: Installieren lokalisierter Versionen von HoloLens
description: Erfahren Sie, wie Sie die lokalisierten Versionen von HoloLens (1. Generation) installieren, einschließlich chinesischer und japanischer Versionen.
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
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310058"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Installieren lokalisierter Versionen von HoloLens (1. Generation)

Um zur chinesischen oder japanischen Version von HoloLens zu wechseln, müssen Sie das Windows Device Recovery Tool (WDRT) verwenden, um den Build für die Sprache auf einem PC herunterzuladen und dann auf Ihrer HoloLens zu installieren.

> [!IMPORTANT]
> Wenn Sie WDRT zum Installieren der chinesischen oder japanischen Builds von HoloLens verwenden, werden vorhandene Daten wie persönliche Dateien und Einstellungen aus HoloLens gelöscht. 

1. Laden Sie auf Ihrem PC [das Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)herunter, und installieren Sie es.
1. Laden Sie das Paket für die Gewünschte Sprache auf Ihren PC herunter: [Vereinfachtes Chinesisch](https://aka.ms/hololensdownload-ch) oder [Japanisch.](https://aka.ms/hololensdownload-jp)
1. Wenn der Download abgeschlossen ist, wählen Sie **Datei-Explorer**  >  **lädt aus.** Klicken Sie mit der rechten Maustaste auf den gezippten Ordner, den Sie gerade heruntergeladen haben, und wählen **Sie Alle**  >  **extrahieren** aus, um ihn zu entzippen.
1. Verbinden Sie Ihre HoloLens mit ihrem PC, indem Sie das Micro-USB-Kabel verwenden, mit dem sie geliefert wurde. (Auch wenn Sie andere Kabel verwendet haben, um Ihre HoloLens zu verbinden, funktioniert dieses am besten.)
1. Nachdem das Tool Ihre HoloLens automatisch erkannt hat, wählen Sie die Kachel Microsoft HoloLens aus.
1. Klicken Sie auf dem nächsten Bildschirm auf **Manuelle Paketauswahl,**   und wählen Sie die Installationsdatei aus, die sich in dem Ordner befindet, den Sie in Schritt 4 entpackt haben. (Suchen Sie nach einer Datei mit der Erweiterung ".ffu".) 
1. Wählen Sie **Software installieren** aus, und befolgen Sie die Anweisungen. 
1. Nach der Installation des Builds wird das HoloLens-Setup automatisch gestartet. Setzen Sie auf das Gerät, und befolgen Sie die Anweisungen für die Einrichtung. 

Wenn Sie mit dem Setup fertig sind, wechseln Sie zu **Einstellungen**  >  **aktualisieren & Security** Windows-Insider  >  **Program**, und überprüfen Sie, ob Sie für den Empfang der neuesten Vorschaubuilds konfiguriert sind. Wie bei der englischen Vorschauversion hält das Windows-Insider-Programm die chinesische und japanische Version von HoloLens mit den neuesten Vorschaubuilds auf dem neuesten Stand.

> [!NOTE]
>  
> - Sie können die Einstellungs-App nicht verwenden, um die Systemsprache zwischen Englisch, Japanisch und Chinesisch zu ändern. Das Flashen eines neuen Build ist die einzige unterstützte Möglichkeit, die Gerätesystemsprache zu ändern.
> - Während Sie die Pinyin-Tastatur auf dem Bildschirm verwenden können, um vereinfachten chinesischen oder japanischen Text eineingaben zu können, wird die Verwendung einer Bluetooth-Hardwaretastatur zum Eingeben von vereinfachtem chinesischem oder japanischem Text derzeit nicht unterstützt.  Auf der chinesischen oder japanischen HoloLens können Sie jedoch weiterhin eine Bluetooth-Tastatur verwenden, um Englisch eineingaben zu können (drücken Sie zum Umschalten einer Hardwaretastatur auf Englisch die Taste ~).
