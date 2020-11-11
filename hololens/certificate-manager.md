---
title: Zertifikat-Manager
description: Erfahren Sie mehr über das manuelle Verwalten von Zertifikaten auf HoloLens 2.
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
ms.openlocfilehash: 04d7e8cb78357b5398c58e0a0c55e6e530fa363a
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163220"
---
# Zertifikat-Manager

- Verbesserte Überwachungs-, Diagnose-und Validierungstools für Gerätesicherheit und-Compliance durch den neuen Zertifikat-Manager. Mit dieser Funktion können Sie Ihre Zertifikate in kommerzieller Umgebung bereitstellen, beheben und überprüfen.

In Windows holographisch, Version 20H2, fügen wir einen Zertifikat-Manager in die HoloLens 2-Einstellungs-APP ein. Wechseln Sie zu **Einstellungen > Update & Security >-Zertifikate**. Dieses Feature bietet eine einfache und benutzerfreundliche Möglichkeit, Zertifikate auf Ihrem Gerät anzuzeigen, zu installieren und zu entfernen. Mit dem neuen Zertifikat-Manager verfügen Administratoren und Benutzer nun über verbesserte Überwachungs-, Diagnose-und Validierungstools, um sicherzustellen, dass die Geräte sicher und kompatibel sind. 

-   **Überwachung:** Fähigkeit, zu überprüfen, ob ein Zertifikat richtig bereitgestellt wurde, oder zu bestätigen, dass es ordnungsgemäß entfernt wurde. 
-   **Diagnose:** Wenn Probleme auftreten, können Sie überprüfen, ob die entsprechenden Zertifikate auf dem Gerät vorhanden sind, Zeit sparen und bei der Problembehandlung helfen. 
-   **Validierung:** Wenn Sie überprüfen, ob ein Zertifikat den beabsichtigten Zweck erfüllt und funktionell ist, können Sie vor allem in kommerziellen Umgebungen beträchtliche Zeit sparen, bevor Sie Zertifikate im größeren Maßstab bereitstellen.

Um schnell ein bestimmtes Zertifikat in der Liste zu finden, gibt es Optionen zum Sortieren nach Name, Store oder Ablaufdatum. Benutzer können auch direkt nach einem Zertifikat suchen. Wenn Sie einzelne Zertifikateigenschaften anzeigen möchten, wählen Sie das Zertifikat aus, und klicken Sie auf **Info**. 

Die Zertifikatinstallation unterstützt derzeit CER-und CRT-Dateien. Gerätebesitzer können Zertifikate auf dem lokalen Computer und dem aktuellen Benutzer installieren.  alle anderen Benutzer können nur in den aktuellen Benutzer installieren. Benutzer können nur Zertifikate entfernen, die direkt von der UI für Einstellungen installiert wurden. Wenn ein Zertifikat auf andere Weise installiert wurde, muss es auch vom gleichen Mechanismus entfernt werden.

## So installieren Sie ein Zertifikat: 

1.  Verbinden Sie Ihr HoloLens 2 mit einem PC.
1.  Legen Sie die Zertifikatdatei, die Sie installieren möchten, an einem Speicherort auf Ihrem HoloLens 2 ab.
1.  Navigieren Sie zu **Einstellungen-app > aktualisieren Sie & Security >-Zertifikate**, und wählen Sie Zertifikat installieren aus.
1.  Klicken Sie auf **Datei importieren** , und navigieren Sie zu dem Speicherort, an dem Sie das Zertifikat gespeichert haben.
1.  Wählen Sie **Store Location**aus.
1.  Wählen Sie **Zertifikatspeicher**aus.
1.  Klicken Sie auf **Installieren**.

Das Zertifikat sollte nun auf dem Gerät installiert sein.

## So entfernen Sie ein Zertifikat: 
1. Navigieren Sie zu **Einstellungen-app > Update-und Sicherheits > Zertifikate**.
1. Suchen Sie im Suchfeld nach dem Namen des Zertifikats.
1. Wählen Sie das Zertifikat aus.
1. Klicken Sie auf **Entfernen** .
1. Wählen Sie **Ja** aus, wenn Sie zur Bestätigung aufgefordert werden.


![Zertifikatanzeige in der Einstellungs-APP unter Ceritifcates](images/certificate-viewer-device.jpg)

![Abbildung, die zeigt, wie Sie mithilfe der Zertifikat-UI ein Zertifikat in Einstellungen installieren.](images/certificate-device-install.jpg)
