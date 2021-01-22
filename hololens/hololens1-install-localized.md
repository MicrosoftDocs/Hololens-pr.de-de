---
title: Installieren lokalisierter Versionen von HoloLens
description: Erfahren Sie, wie Sie die lokalisierten Versionen von HoloLens (1. Generation) installieren, einschließlich chinesischer und japanischer Versionen.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: high
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: af79e42477a3a317dde03a795c442fa31241600d
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11282976"
---
# Installieren lokalisierter Versionen von HoloLens (1. Generation)

Um zur chinesischen oder japanischen Version von HoloLens zu wechseln, müssen Sie das Windows Device Recovery Tool (WDRT) verwenden, um den Build für die Sprache auf einem PC herunterzuladen und dann auf Ihrer HoloLens zu installieren.

> [!IMPORTANT]
> Wenn Sie WDRT verwenden, um die chinesischen oder japanischen Builds von HoloLens zu installieren, werden vorhandene Daten wie persönliche Dateien und Einstellungen aus Ihrer HoloLens gelöscht. 

1. Laden Sie auf Ihrem PC das [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) herunter, und installieren Sie es.
1. Laden Sie das Paket für die gewünschte Sprache auf Ihren PC herunter: [Chinesisch (vereinfacht](https://aka.ms/hololensdownload-ch) ) oder [Japanisch](https://aka.ms/hololensdownload-jp).
1. Wenn der Download abgeschlossen ist, wählen Sie **Datei-Explorer** > **Downloads** aus. Klicken Sie mit der rechten Maustaste auf den soeben heruntergeladenen gezippten Ordner, und wählen Sie **Alle extrahieren** > **Extrahieren** aus, um die Dateien zu entpacken.
1. Schließen Sie Ihre HoloLens mit dem mitgelieferten Micro-USB-Kabel an Ihren PC an. (Auch wenn Sie Ihre HoloLens mit anderen Kabeln verbunden haben, funktioniert dies am besten.)
1. Nachdem das Tool Ihre HoloLens automatisch erkannt hat, wählen Sie die Kachel „Microsoft HoloLens” aus.
1. Wählen Sie auf dem nächsten Bildschirm  **Manuelle Paketauswahl**  aus, und wählen Sie die Installationsdatei aus, die sich in dem Ordner befindet, den Sie in Schritt 4 entpackt haben. (Suchen Sie nach einer Datei mit der Erweiterung „FFU”.) 
1. Wählen Sie  **Software installieren** aus, und folgen Sie den Anweisungen. 
1. Nachdem der Build installiert wurde, wird das Einrichten der HoloLens automatisch gestartet. Schalten Sie das Gerät ein und folgen Sie den Anweisungen für die Einrichtung. 

Wenn Sie mit dem Einrichten fertig sind, wechseln Sie zu **Einstellungen** > **Update und Sicherheit** > **Windows-Insider-Programm** und überprüfen Sie, ob alles so konfiguriert ist, dass Sie die neuesten Preview-Builds erhalten. Wie bei den englischen Preview-Builds werden mit dem Windows-Insider-Programm die chinesischen und japanischen Versionen von HoloLens mit den neuesten Preview-Builds auf dem neuesten Stand gehalten.

> [!NOTE]
>  
> - Sie können die Einstellungs-App nicht verwenden, um die Systemsprache zwischen Englisch, Japanisch und Chinesisch zu ändern. Das Flashen eines neuen Builds ist die einzige unterstützte Möglichkeit, die Systemsprache des Geräts zu ändern.
> - Sie können zwar die Pinyin-Bildschirmtastatur zur Eingabe von vereinfachtem Chinesisch oder Japanisch verwenden, die Verwendung einer Bluetooth-Hardwaretastatur zur Eingabe von vereinfachtem Chinesisch oder Japanisch wird derzeit jedoch nicht unterstützt.  Bei chinesischen oder japanischen HoloLens können Sie jedoch weiterhin eine Bluetooth-Tastatur verwenden, um Englisch einzugeben (um auf eine Hardwaretastatur auf Englisch umzuschalten, drücken Sie die Taste „~”).
