---
title: Verbessern der Grafikqualität und des Komforts
description: Die Kalibrierung Ihres Pupillenabstands (Interpupillary Distance, IPD) kann die Qualität der visuellen Elemente verbessern. Sowohl HoloLens- als auch Windows Mixed Reality-immersive Headsets bieten Möglichkeiten zum Anpassen des IPD.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
keywords: Kalibrierung, Komfort, visuelle Elemente, Qualität, IPD
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 627631ee7070af6cb6c60e91890f05472ce0f6be
ms.sourcegitcommit: 8b56f4b9b5f9c928fc361f18efcbea729055a0b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919156"
---
# Verbessern der Grafikqualität und des Komforts

HoloLens 2 und HoloLens (1. Generation) funktionieren beide besser, wenn sie spezifisch für Ihre Augen kalibriert werden.

Beide Geräte müssen zwar für eine optimale Darstellung des Hologramms kalibriert werden, verwenden jedoch unterschiedliche Kalibrierungstechnologien und -techniken.  Wechseln Sie zu [HoloLens 2 Kalibrierung](#calibrating-your-hololens-2) oder [HoloLens (1. Generation) Kalibrierung](#calibrating-your-hololens-1st-gen).

## Kalibrieren Ihrer HoloLens 2

HoloLens 2 verwendet die Eye Tracking-Technologie, um das Sehen von und die Interaktion mit der virtuellen Umgebung zu verbessern. Durch die Kalibrierung der HoloLens 2 wird sichergestellt, dass Ihre Augen (und die Augen aller anderen Benutzer des Geräts) genau nachverfolgt werden können. Es hilft außerdem beim Benutzerkomfort, der Hologramm-Ausrichtung und der Hand Verfolgung. Nach der Kalibrierung werden Hologramme korrekt angezeigt, auch wenn sich das Visier auf Ihrem Kopf verschiebt.

HoloLens 2 fordert einen Benutzer auf, das Gerät unter den folgenden Umständen zu kalibrieren:

- Der Benutzer verwendet das Gerät zum ersten Mal
- Der Benutzer hat den Kalibrierungsvorgang zuvor deaktiviert
- Der Kalibrierungsvorgang war bei der letzten Verwendung durch den Benutzer nicht erfolgreich
- Der Benutzer hat seine Kalibrierungsprofile gelöscht.
- Das Gerät wird deaktiviert und wieder aktiviert, und es gelten die vorstehenden Umstände. 


![Aufforderung zur Kalibrierung](./images/07-et-adjust-for-your-eyes.png)

Während dieses Vorgangs sehen Sie sich eine Reihe von Zielen (Edelsteinen) an. Es ist in Ordnung, wenn Sie während der Kalibrierung blinzeln oder die Augen schließen. Versuchen Sie sich jedoch auf die Edelsteine zu konzentrieren, und nicht auf andere Gegenstände im Raum.  Auf diese Weise kann HoloLens Ihre Augenposition ermitteln, um Ihre holografische Welt darzustellen.

![Aufforderung zur Kalibrierung](./images/07-et-hold-head-still.png)

![Aufforderung zur Kalibrierung](./images/08-et-gems.png)

![Aufforderung zur Kalibrierung](./images/09-et-adjusting.png)

Wenn die Kalibrierung erfolgreich war, wird ein Erfolgsbildschirm angezeigt.  Wenn dies nicht der Fall ist, lesen Sie [hier](#troubleshooting-hololens-2-calibration) mehr über die Diagnose von Kalibrierungsfehlern.

![Aufforderung zur Kalibrierung](./images/10-et-success.png)

### Kalibrierung beim Freigeben eines Geräts oder einer Sitzung

Mehrere Benutzer können ein HoloLens 2-Gerät gemeinsam nutzen, ohne dass jede Person die Geräteeinrichtung durchführen muss. Wenn ein neuer Benutzer das Gerät zum ersten Mal aufsetzt, fordert HoloLens 2 ihn automatisch auf, die visuellen Elemente zu kalibrieren. Wenn ein Benutzer, der zuvor die visuellen Elemente kalibriert hat, das Gerät aufsetzt, passt die Anzeige die Qualität sowie die komfortable Anzeigeumgebung nahtlos an.  

### Manuelles Starten des Kalibrierungsvorgangs

1. Verwenden Sie die Startgeste, um das [**Startmenü**](hololens2-basic-usage.md#start-gesture) zu öffnen.
1. Wenn die Einstellungs-App nicht an **Start** angeheftet ist, wählen Sie **Alle Apps** aus.
1. Wählen Sie **Einstellungen** aus, und wählen Sie dann **System** > **Kalibrierung** > **Kalibrierung der Augen** > **Kalibrierung der Augen ausführen** aus.

   ![Die Einstellungs-App mit der Option „Kalibrierung der Augen ausführen”](./images/C-Settings.Calibration.png)

### Problembehandlung bei der HoloLens 2-Kalibrierung

Die Kalibrierung sollte für die meisten Menschen funktionieren, doch es gibt Fälle, in denen die Kalibrierung fehlschlägt.
  
Mögliche Ursachen für Kalibrierungsfehler sind unter anderem:

- Abgelenkt werden und den Kalibrierungszielen nicht folgen
- Schmutziges oder zerkratztes Visier oder nicht richtig positioniertes Visier
- Schmutzige oder verkratzte Brille
- Bestimmte Arten von Kontaktlinsen und Brillen (farbige Kontaktlinsen, einige torische Kontaktlinsen, IR-Schutzbrillen, einige hochwertige, verschreibungspflichtige Brillen, Sonnenbrillen oder Ähnliches)
- Stärkeres Make-up und einige Wimpernverlängerungen
- Haare oder dicke Brillenfassungen, wenn sie das Gerät daran hindern, Ihre Augen zu sehen
- Bestimmte Augenphysiologie, Augenleiden oder Augenchirurgie wie schmale Augen, lange Wimpern, Amblyopie, Nystagmus, einige Fälle von LASIK oder andere Augenoperationen

Wenn die Kalibrierung nicht erfolgreich ist, versuchen Sie Folgendes:

- Reinigen Sie das Visier des Geräts
- Reinigen Sie Ihre Brille
- Drücken Sie das Visier Ihres Geräts so nah wie möglich an Ihre Augen
- Räumen Sie Gegenstände aus dem Weg des Visiers (z. B. Haare)
- Schalten Sie Licht in Ihrem Zimmer ein oder weichen Sie direktem Sonnenlicht aus

Wenn Sie alle Richtlinien befolgt haben und die Kalibrierung weiterhin fehlschlägt, können Sie die Eingabeaufforderung zur Kalibrierung unter Einstellungen deaktivieren. Bitte teilen Sie uns auch im [Feedback-Hub](hololens-feedback.md) Ihre Meinung mit.

Lesen Sie auch die entsprechenden Informationen zur [Problembehandlung bei Bildfarbe oder Helligkeit](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right).

Beachten Sie, dass das Einstellen des IPD für HoloLens 2 nicht anwendbar ist, da die Augenpositionen vom System berechnet werden. 

### Kalibrierungsdaten und Sicherheit

Kalibrierinformationen werden lokal auf dem Gerät gespeichert und sind nicht mit Kontoinformationen verknüpft. Es gibt keine Aufzeichnung darüber, wer das Gerät ohne Kalibrierung verwendet hat. Dies bedeutet, dass neue Benutzer bei der ersten Verwendung des Geräts aufgefordert werden, visuelle Elemente zu kalibrieren, sowie Benutzer, die zuvor die Kalibrierung deaktiviert haben oder wenn die Kalibrierung nicht erfolgreich war.

Auf dem Gerät können bis zu 50-Kalibrierprofile lokal gespeichert werden. Wenn diese Zahl erreicht ist, löscht das Gerät automatisch das älteste nicht verwendete Profil.

Kalibrierinformationen können unter **Einstellungen** > **Datenschutz** > **Eyetracker** zu jeder Zeit vom Gerät gelöscht werden.  

### Kalibrierung deaktivieren

Sie können die Aufforderung zur Kalibrierung auch deaktivieren, indem Sie die folgenden Schritte ausführen:

1. Wählen Sie **Einstellungen** > **System** > **Kalibrierung** aus.
1. Deaktivieren Sie die Option **Wenn eine neue Person diese HoloLens verwendet, automatische Aufforderung zur Ausführung der Augenkalibrierung**.

> [!IMPORTANT]
> Diese Einstellung kann die Qualität und den Komfort der Hologrammwiedergabe beeinträchtigen.  Wenn Sie diese Einstellung deaktivieren, funktionieren Features, die von Eye Tracking abhängig sind (z.B. Textbildlauf), nicht mehr in immersiven Anwendungen.

### HoloLens 2 Eye Tracking-Technologie

Das Gerät verwendet seine Eye Tracking-Technologie, um die Anzeigequalität zu verbessern und um sicherzustellen, dass alle Hologramme exakt und bequem in 3D positioniert werden können. Da die Augen als Orientierungspunkte verwendet werden, kann sich das Gerät an jeden Benutzer anpassen und seine visuellen Elemente optimieren, wenn das Headset während der Verwendung geringfügig verschoben wird.  Alle Anpassungen erfolgen im Handumdrehen, ohne die Notwendigkeit einer manuellen Einstellung.
> [!NOTE]
> Das Einstellen des IPD ist für HoloLens 2 nicht anwendbar, da die Augenpositionen vom System berechnet werden.

HoloLens-Anwendungen verwenden Eye Tracking, um in Echtzeit nachzuverfolgen, wo Sie hinschauen. Dies ist die wichtigste Funktion, die Entwickler nutzen können, um eine völlig neue Ebene von Kontext, menschlichem Verständnis und Interaktionen innerhalb der holographischen Erfahrung zu schaffen. Entwickler müssen nichts unternehmen, um diese Funktion zu nutzen.

## Kalibrieren Ihrer HoloLens (1. Generation)

HoloLens (1. Generation) passt die Anzeige von Hologrammen entsprechend dem [Pupillenabstand](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD) an. Wenn der IPD nicht genau ist, erscheinen Hologramme möglicherweise instabil oder in einer falschen Entfernung. Sie können die Qualität Ihrer visuellen Elemente verbessern, indem Sie das Gerät auf Ihren Pupillenabstand (IPD) kalibrieren.

Beim Einrichten Ihrer Hololens (1. Generation) werden Sie aufgefordert, Ihre visuellen Elemente zu kalibrieren, nachdem Cortana sich vorgestellt hat. Es wird empfohlen, den Kalibrierungsvorgang während dieser Einrichtungsphase abzuschließen. Sie können ihn jedoch überspringen, indem Sie warten, bis Cortana Sie auffordert, und dann „Überspringen” sagen.

Während des Kalibrierungsvorgangs fordert HoloLens Sie auf, Ihren Finger mit einer Reihe von sechs Zielen pro Auge auszurichten. HoloLens verwendet diesen Vorgang, um den IPD für Ihre Augen richtig einzustellen.

![IPD-Fingerausrichtungsbildschirm im zweiten Schritt](./images/ipd-finger-alignment-300px.jpg)

### Manuelles Starten des Kalibrierungsvorgangs

Wenn Sie die Kalibrierung aktualisieren müssen oder wenn ein neuer Benutzer sie anpassen muss, können Sie die Kalibrierungs-App jederzeit manuell ausführen. Die Kalibrierungs-App ist standardmäßig installiert. Sie können über das **Startmenü** oder in der Einstellungs-App darauf zugreifen.

Führen Sie die folgenden Schritte aus, um die Kalibrierungs-App über das **Startmenü** auszuführen:

1. Verwenden Sie die [Öffnengeste](hololens1-basic-usage.md), um das **Startmenü** zu öffnen.
1. Um alle Apps anzuzeigen, wählen Sie **+** aus.
1. Wählen Sie **Kalibrierung** aus.

![Zugreifen auf die Kalibrierungs-App aus der Shell](./images/calibration-shell.png)

![Die Kalibrierungs-App wird nach dem Start als Live-Kachel angezeigt](./images/calibration-livecube-200px.png)

Führen Sie die folgenden Schritte aus, um die Kalibrierungs-App über die Einstellungs-App auszuführen:

1. Verwenden Sie die [Öffnengeste](hololens1-basic-usage.md), um das **Startmenü** zu öffnen.
1. Wenn **Einstellungen** nicht an **Start** angeheftet ist, wählen Sie **+** aus, um alle Apps anzuzeigen.
1. Wählen Sie **Einstellungen** aus.
1. Wählen Sie **System** > **Dienstprogramme** > **Kalibrierung öffnen** aus.

![Starten der Kalibrierungs-App aus der Einstellungs-App](./images/calibration-settings-500px.jpg)

## Immersive Headsets

Einige immersive Headsets bieten die Möglichkeit, die IPD-Einstellung anzupassen. Wenn Sie den IPD für Ihr Headset ändern möchten, öffnen Sie die Einstellungs-App und wählen Sie **Mixed Reality** > **Headsetanzeige** aus und bewegen Sie dann das Schieberegler-Steuerelement. Die Änderungen werden in Echtzeit in Ihrem Headset angezeigt. Wenn Sie Ihren IPD kennen, vielleicht durch einen Besuch beim Optiker, können Sie ihn auch direkt eingeben.

Sie können diese Einstellung auch auf Ihrem PC anpassen, indem Sie **Einstellungen** > **Mixed Reality** > **Headsetanzeige** auswählen.

Wenn Ihr Headset die IPD-Anpassung nicht unterstützt, ist diese Einstellung deaktiviert.
