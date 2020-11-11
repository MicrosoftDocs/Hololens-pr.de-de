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
ms.openlocfilehash: f466d64da8ef122ce2917117a74ab904a573b4e3
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163050"
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


![Kalibrierungsaufforderung zur Anpassung an die Augen.](./images/07-et-adjust-for-your-eyes.png)

Während dieses Vorgangs sehen Sie sich eine Reihe von Zielen (Edelsteinen) an. Es ist in Ordnung, wenn Sie während der Kalibrierung blinzeln oder die Augen schließen. Versuchen Sie sich jedoch auf die Edelsteine zu konzentrieren, und nicht auf andere Gegenstände im Raum.  Auf diese Weise kann HoloLens Ihre Augenposition ermitteln, um Ihre holografische Welt darzustellen.

![Für die Kalibrierung werden Sie aufgefordert, den Kopf ruhig zu halten und den Punkten mit den Augen zu folgen.](./images/07-et-hold-head-still.png)

![Beispiel-Kalibrierung mit Edelstein.](./images/08-et-gems.png)

![Kalibrierung anpassen.](./images/09-et-adjusting.png)

Wenn die Kalibrierung erfolgreich war, wird ein Erfolgsbildschirm angezeigt.  Wenn dies nicht der Fall ist, lesen Sie [hier](#troubleshooting-hololens-2-calibration) mehr über die Diagnose von Kalibrierungsfehlern.

![Kalibrierung erfolgreich.](./images/10-et-success.png)

### Kalibrierung beim Freigeben eines Geräts oder einer Sitzung

Mehrere Benutzer können ein HoloLens 2-Gerät gemeinsam nutzen, ohne dass jede Person die Geräteeinrichtung durchführen muss. Wenn ein neuer Benutzer das Gerät zum ersten Mal aufsetzt, fordert HoloLens 2 ihn automatisch auf, die visuellen Elemente zu kalibrieren. Wenn ein Benutzer, der zuvor die visuellen Elemente kalibriert hat, das Gerät aufsetzt, passt die Anzeige die Qualität sowie die komfortable Anzeigeumgebung nahtlos an.  

### Manuelles Starten des Kalibrierungsvorgangs

1. Verwenden Sie die Startgeste, um das [**Startmenü**](hololens2-basic-usage.md#start-gesture) zu öffnen.
1. Wenn die Einstellungs-App nicht an **Start** angeheftet ist, wählen Sie **Alle Apps** aus.
1. Wählen Sie **Einstellungen** aus, und wählen Sie dann **System** > **Kalibrierung** > **Kalibrierung der Augen** > **Kalibrierung der Augen ausführen** aus.

   ![Die Einstellungs-App mit der Option „Kalibrierung der Augen ausführen”](./images/C-Settings.Calibration.png)

### Automatische Unterstützung der Augenposition
- Wir bieten jetzt eine höhere Genauigkeit bei der Hologramm-Positionierung durch die automatische Unterstützung der Augenposition für verbesserten Sehkomfort und bessere Anzeigequalität. 

Bei HoloLens 2 ermöglichen die Augenpositionen eine genaue Hologramm-Positionierung, ein komfortables Seherlebnis und eine verbesserte Anzeigequalität. Die Augenpositionen werden als Teil des Eyetracking-Ergebnisses berechnet. Dazu müssen alle Benutzer eine Eye Tracking-Kalibrierung durchführen, auch wenn keine Blickeingabe erforderlich ist.

**Auto Eye Position (AEP)** ermöglicht diese Szenarien mit einer interaktionsfreien Methode zur Berechnung der Augenpositionen für Benutzer.  Auto Eye Position beginnt automatisch im Hintergrund zu arbeiten, sobald Benutzer das Gerät anlegen. Wenn Benutzer keine vorherige Eye Tracking-Kalibrierung haben, beginnt Auto Eye Position nach einer kurzen Verarbeitungszeit mit der Bereitstellung der Augenpositionen der Benutzer an das Anzeigesystem. Diese Bearbeitungszeit liegt typischerweise zwischen 20 bis 60 Sekunden. Die Benutzerdaten werden nicht auf dem Gerät beibehalten. Deshalb wird dieser Vorgang wiederholt, wenn das Gerät wieder eingesetzt, neu gestartet oder aus dem Ruhezustand reaktiviert wird.  

Änderungen des Systemverhaltens mit der Funktion Auto Eye Position, wenn ein unkalibrierter Benutzer das Gerät anlegt. Ein nicht kalibrierter Benutzer ist eine Person, die den Eye-Tracking-Kalibrierungsprozess auf dem Gerät noch nicht durchlaufen hat.

|     Aktive Anwendung                           |     Bisheriges Verhalten                                   |     Verhalten für Windows HWindows Holographic, ab Version 20H2                                                     |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     App oder Holographic Shell ohne Blickkontakt    |     Aufforderung zur Eye-Tracking-Kalibrierung wird angezeigt.    |     Es wird keine Aufforderung angezeigt.                                                                                |
|     App mit Blickeingabe                             |     Aufforderung zur Eye-Tracking-Kalibrierung wird angezeigt.    |     Die Aufforderung zur Eye-Tracking-Kalibrierung wird nur angezeigt, wenn die Anwendung auf den Blickstrom des Auges zugreift.     |

 Wenn Benutzer von einer Anwendung ohne Blickeingabe zu einer Anwendung wechseln, die auf Blickdaten zugreift, wird die Kalibrierungsaufforderung angezeigt. Es wird nicht auf einen Out-Of-Box-Erfahrungsfluss umgestellt. 
 
Für Umgebungen, die Blickdaten oder eine sehr präzise Hologramm-Positionierung erfordern, empfehlen wir unkalibrierten Benutzern, die Eye Tracking-Kalibrierung über die Eingabeaufforderung auszuführen. Oder die App-Einstellungen im Startmenü zu starten und **System > Kalibrierung > Augenkalibrierung > Augenkalibrierung ausführen** auszuwählen.

**Bekannte Probleme**
 - Wir untersuchen ein Problem, bei dem der Eyetracking-Treiber-Host-Prozess bei starker Speicherauslastung abstürzt. Der Eyetracking-Treiber-Host-Prozess sollte sich automatisch erholen.


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
