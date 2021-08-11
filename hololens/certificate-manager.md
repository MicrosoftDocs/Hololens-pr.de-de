---
title: Zertifikat-Manager
description: Erfahren Sie, wie Sie Zertifikate manuell auf Mixed Reality-Geräten HoloLens 2, verwalten und entfernen.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 438a132a6bafd8c93b148b9c2c817ec93cc3bc73651f08275acc130695fa09c1
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665181"
---
# <a name="certificate-manager"></a>Zertifikat-Manager

- Verbesserte Überwachungs-, Diagnose- und Überprüfungstools für Gerätesicherheit und -konformität über den neuen Zertifikat-Manager. Mit dieser Funktion können Sie Ihre Zertifikate in kommerziellen Umgebungen im großen Stil bereitstellen, behandeln und überprüfen.

In Windows Holographic Version 20H2 fügen wir der App einen Zertifikat-Manager HoloLens 2 Einstellungen hinzu. Wechseln Sie **zu Einstellungen > Update & Security > Certificates**. Dieses Feature bietet eine einfache und benutzerfreundliche Möglichkeit zum Anzeigen, Installieren und Entfernen von Zertifikaten auf Ihrem Gerät. Mit dem neuen Zertifikat-Manager verfügen Administratoren und Benutzer jetzt über verbesserte Überwachungs-, Diagnose- und Validierungstools, um sicherzustellen, dass Geräte sicher und konform bleiben. 

-   **Überwachung:** Möglichkeit, zu überprüfen, ob ein Zertifikat ordnungsgemäß bereitgestellt wurde, oder um zu bestätigen, dass es ordnungsgemäß entfernt wurde. 
-   **Diagnose:** Wenn Probleme auftreten, spart die Validierung, ob die entsprechenden Zertifikate auf dem Gerät vorhanden sind, Zeit und hilft bei der Problembehandlung. 
-   **Überprüfung:** Die Überprüfung, ob ein Zertifikat dem beabsichtigten Zweck dient und funktionsfähig ist, kann insbesondere in kommerziellen Umgebungen viel Zeit sparen, bevor Zertifikate in größerem Umfang bereitgestellt werden.

Um ein bestimmtes Zertifikat schnell in der Liste zu finden, gibt es Optionen zum Sortieren nach Name, Speicher oder Ablaufdatum. Benutzer können auch direkt nach einem Zertifikat suchen. Wählen Sie zum Anzeigen einzelner Zertifikateigenschaften das Zertifikat aus, und klicken Sie auf **Info**. 

Die Zertifikatinstallation unterstützt derzeit CER- und CRT-Dateien. Gerätebesitzer können Zertifikate auf dem lokalen Computer und dem aktuellen Benutzer installieren.  alle anderen Benutzer können nur in Current User installieren.

## <a name="to-install-a-certificate"></a>So installieren Sie ein Zertifikat: 

1.  Verbinden Sie ihre HoloLens 2 pc.
1.  Platzieren Sie die Zertifikatdatei, die Sie installieren möchten, an einem Speicherort auf Ihrem HoloLens 2.
1.  Navigieren Sie **zu Einstellungen App > Update & Security > Certificates**, und wählen Sie Zertifikat installieren aus.
1.  Klicken **Sie auf Datei** importieren, und navigieren Sie zu dem Speicherort, an dem Sie das Zertifikat gespeichert haben.
1.  Wählen Sie **Store Speicherort aus.**
1.  Wählen Sie **Zertifikat Store.**
1.  Klicken Sie auf **Installieren**.

Das Zertifikat sollte jetzt auf dem Gerät installiert sein.

![Zertifikatanzeige in der Einstellungen-App unter Zertifikate.](images/certificate-viewer-device.jpg)

![Abbildung: Verwenden der Zertifikatbenutzeroberfläche zum Installieren eines Zertifikats in Einstellungen.](images/certificate-device-install.jpg)

## <a name="to-remove-a-certificate"></a>So entfernen Sie ein Zertifikat:

> [!WARNING]
> Mithilfe des Zertifikat-Managers können Benutzer nur Zertifikate entfernen, die direkt über die benutzeroberfläche Einstellungen wurden. Wenn ein Zertifikat auf andere Weise installiert wurde, muss es auch mit demselben Mechanismus entfernt werden und kann nicht aus dem Zertifikat-Manager entfernt werden. Sie können mit MDM bereitgestellte Zertifikate zwar im Zertifikat-Manager anzeigen, aber nicht im Zertifikat-Manager deinstallieren. Sie müssen sie über MDM deinstallieren.

1. Navigieren Sie **zu Einstellungen App > Update- und > Zertifikate.**
1. Suchen Sie im Suchfeld nach dem Namen des Zertifikats.
1. Wählen Sie das Zertifikat aus.
1. Klicken Sie auf **Entfernen.**
1. Wählen Sie **Ja** aus, wenn Sie zur Bestätigung aufgefordert werden.

