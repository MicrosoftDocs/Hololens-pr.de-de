---
title: Herunterladen und Installieren von apps über das HoloLens 2-App-Installationsprogramm
description: Laden und Installieren von apps über die Benutzeroberfläche
keywords: App-Verwaltung, APP, hololens, App-Installationsprogramm
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2387c0eb65efc312db4eea7118f3cca44ce6d4b6
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027470"
---
# Installieren von apps auf HoloLens 2 über das App-Installationsprogramm

Benutzer können jetzt Apps über AppX-Bundles jetzt installieren, ohne den Entwicklermodus aktivieren oder Device Portal verwenden zu müssen. Diese Vorgehensweise ist einfach für die Installation von apps auf lokalen Geräten oder das Freigeben einer APP für eine andere Person, die mit anderen APP-Installationsmethoden auf HoloLens nicht vertraut ist. 

> [!IMPORTANT]
> Dieses Feature ist derzeit nur avalible in Windows Insider-Builds 19041.1377 +. [Weitere Informationen zum Registrieren von Windows Insider-Builds](hololens-insider.md).

> [!NOTE]
> Die Projektmappenkonfiguration der APP muss entweder **Master** oder **Release** sein, da vom APP-Installationsprogramm Abhängigkeiten aus dem Store verwendet werden. Weitere Informationen finden Sie unter [Erstellen von App-Paketen](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).

1.  Stellen Sie sicher, dass Ihr HoloLens 2-Gerät eingeschaltet ist und Sie angemeldet sind.
1.  Navigieren Sie auf Ihrem PC zu Ihrer benutzerdefinierten APP, und kopieren Sie yourapp. appxbundle nach yourdevicename\Internal Storage\Downloads. 
    Nachdem Sie Ihre Datei fertig kopiert haben, können Sie Ihr Gerät trennen und die Installation später abschließen.
1.  Öffnen Sie auf Ihrem HoloLens 2-Gerät das **Startmenü**, wählen Sie **alle apps** aus, und starten Sie die **Datei-Explorer** -app.
1.  Navigieren Sie zum Ordner Downloads. Möglicherweise müssen Sie auf der linken Seite der APP zuerst **dieses Gerät** auswählen und dann zu Downloads navigieren.
1.  Wählen Sie die Datei "yourapp. appxbundle" aus. 
1.  Das App-Installationsprogramm wird gestartet. Wählen Sie die Schaltfläche **Installieren** aus, um Ihre APP zu installieren. 

Die installierte APP wird nach Abschluss der Installation automatisch gestartet. 

![Installieren von MRTK-Beispielen über das App-Installationsprogramm](images/hololens-app-installer-picture.jpg)

Wenn Ihre APP nicht installiert werden konnte, prüfen Sie Folgendes:
-   Ihre APP ist entweder ein Master-oder Release-Build.
-   Sie sind [mit dem Internet verbunden](hololens-network.md).
-   Ihre [Endpunkte für den Microsoft Store](hololens-offline.md) sind ordnungsgemäß konfiguriert.  
