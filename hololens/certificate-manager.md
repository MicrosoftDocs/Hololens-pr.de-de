---
title: Zertifikat-Manager
description: Erfahren Sie, wie Sie Zertifikate auf Mixed -Reality-Geräten von HoloLens 2 manuell installieren, verwalten und entfernen.
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
ms.openlocfilehash: 9d221321adcb8062206695e3e610d35dee14523e
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283686"
---
# Zertifikat-Manager

- Verbesserte Überwachungs-, Diagnose- und Validierungstools für Gerätesicherheit und -kompatibilität durch den neuen Zertifikat-Manager. Mit dieser Funktion können Sie Ihre Zertifikate in kommerziellen Umgebungen bereitstellen, Eine Problembehandlung und Validierung ihrer Zertifikate im großen Maßstab ermöglichen.

In Windows Holographic, Version 20H2, fügen wir einen Zertifikat-Manager in der HoloLens 2-Einstellungs-App hinzu. Wechseln Sie **zu "Einstellungen > update & Security > Certificates".** Dieses Feature bietet eine einfache und benutzerfreundliche Möglichkeit zum Anzeigen, Installieren und Entfernen von Zertifikaten auf Ihrem Gerät. Mit dem neuen Zertifikat-Manager verfügen Administratoren und Benutzer jetzt über verbesserte Überwachungs-, Diagnose- und Validierungstools, um sicherzustellen, dass Geräte sicher und kompatibel bleiben. 

-   **Überwachung:** Möglichkeit, zu überprüfen, ob ein Zertifikat ordnungsgemäß bereitgestellt wurde, oder um zu bestätigen, dass es ordnungsgemäß entfernt wurde. 
-   **Diagnose:** Wenn Probleme auftreten, spart die Validierung, dass die entsprechenden Zertifikate auf dem Gerät vorhanden sind, Zeit und hilft bei der Problembehandlung. 
-   **Überprüfung:** Die Überprüfung, ob ein Zertifikat dem beabsichtigten Zweck dient und funktionsfähig ist, kann erhebliche Zeit sparen, insbesondere in kommerziellen Umgebungen, bevor Zertifikate in größerem Umfang bereitgestellt werden.

Um ein bestimmtes Zertifikat schnell in der Liste zu finden, gibt es Optionen zum Sortieren nach Name, Speicher oder Ablaufdatum. Benutzer können auch direkt nach einem Zertifikat suchen. Um einzelne Zertifikateigenschaften anzeigen zu können, wählen Sie das Zertifikat aus, und klicken Sie auf **"Info".** 

Die Zertifikatinstallation unterstützt derzeit CER- und CRT-Dateien. Gerätebesitzer können Zertifikate auf dem lokalen Computer und dem aktuellen Benutzer installieren.  Alle anderen Benutzer können nur im aktuellen Benutzer installiert werden. Benutzer können nur Direkt installierte Zertifikate aus der Einstellungsbenutzeroberfläche entfernen. Wenn ein Zertifikat auf andere Weise installiert wurde, muss es auch mit demselben Mechanismus entfernt werden.

## So installieren Sie ein Zertifikat: 

1.  Verbinden Sie Ihre HoloLens 2 mit einem PC.
1.  Platzieren Sie die zertifikatsdatei, die Sie installieren möchten, an einem Speicherort auf Ihrer HoloLens 2.
1.  Navigieren Sie **zu "Settings App > Update & Security > Certificates",** und wählen Sie "Zertifikat installieren" aus.
1.  Klicken **Sie auf "Datei importieren",** und navigieren Sie zu dem Speicherort, an dem Sie das Zertifikat gespeichert haben.
1.  Wählen Sie **"Speicherort" aus.**
1.  Wählen Sie **Zertifikatspeicher aus.**
1.  Klicken Sie auf **Installieren**.

Das Zertifikat sollte nun auf dem Gerät installiert werden.

## So entfernen Sie ein Zertifikat: 
1. Navigieren Sie zu **"Settings App > Update and Security > Certificates".**
1. Suchen Sie im Suchfeld nach dem Namen des Zertifikats.
1. Wählen Sie das Zertifikat aus.
1. Klicken Sie auf **"Entfernen".**
1. Wählen **Sie "Ja"** aus, wenn Sie zur Bestätigung aufgefordert werden.


![Zertifikatanzeige in der App "Einstellungen" unter "Ceritifcates"](images/certificate-viewer-device.jpg)

![Abbildung der Verwendung der Zertifikatbenutzeroberfläche zum Installieren eines Zertifikats in den Einstellungen.](images/certificate-device-install.jpg)
