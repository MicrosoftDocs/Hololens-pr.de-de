---
title: Verbessern der Grafikqualität und des Komforts
description: Erfahren Sie, wie Sie das Gerät auf Ihren Pupillenabstand (Interpupillary Distance, IPD) kalibrieren können, um die Qualität Ihrer visuellen Elemente auf HoloLens-Geräten zu verbessern.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: Kalibrierung, Komfort, visuelle Elemente, Qualität, IPD, HoloLens, Windows Mixed Reality, VR-Headsets
ms.openlocfilehash: e975e2ccd978d4ec6b5331af0ae566af116711c5
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283546"
---
# Verbessern der Grafikqualität und des Komforts

HoloLens 2 und HoloLens (1. Generation) funktionieren beide besser, wenn sie spezifisch für Ihre Augen kalibriert werden.

Beide Geräte müssen zwar für eine optimale Darstellung des Hologramms kalibriert werden, verwenden jedoch unterschiedliche Kalibrierungstechnologien und -techniken.  Wechseln Sie zu [HoloLens 2 Kalibrierung](#calibrating-your-hololens-2) oder [HoloLens (1. Generation) Kalibrierung](#calibrating-your-hololens-1st-gen).

## Kalibrieren Ihrer HoloLens 2

HoloLens 2 verwendet die Eye Tracking-Technologie, um das Sehen von und die Interaktion mit der virtuellen Umgebung zu verbessern. Durch die Kalibrierung der HoloLens 2 wird sichergestellt, dass Ihre Augen (und die Augen aller anderen Benutzer des Geräts) genau nachverfolgt werden können. Es hilft außerdem beim Benutzerkomfort, der Hologramm-Ausrichtung und der Hand Verfolgung. Nach der Kalibrierung werden Hologramme korrekt angezeigt, auch wenn sich das Visier auf Ihrem Kopf verschiebt.

HoloLens 2 fordert einen Benutzer auf, das Gerät unter den folgenden Umständen zu kalibrieren:

- Der Benutzer verwendet das Gerät zum ersten Mal
- Der Benutzer hat den Kalibrierungsvorgang zuvor deaktiviert
- Der Kalibrierungsvorgang war bei der letzten Verwendung des Geräts durch den Benutzer nicht erfolgreich
- Der Benutzer hat seine Kalibrierungsprofile gelöscht
- Das Gerät wird ausgeschaltet und wieder eingeschaltet, und eine der oben genannten Bedingungen trifft zu 


![Kalibrierungsdialog zur Anpassung an die Augen.](./images/07-et-adjust-for-your-eyes.png)

Während dieses Vorgangs sehen Sie sich eine Reihe von Zielen (Edelsteinen) an. Es ist in Ordnung, wenn Sie während der Kalibrierung blinzeln oder die Augen schließen. Versuchen Sie sich jedoch auf die Edelsteine zu konzentrieren, und nicht auf andere Gegenstände im Raum.  Durch die Fokussierung auf die Edelsteine kann HoloLens Ihre Augenposition ermitteln, um Ihre holografische Welt darzustellen.

![Für die Kalibrierung werden Sie aufgefordert, den Kopf ruhig zu halten und den Punkten mit den Augen zu folgen.](./images/07-et-hold-head-still.png)

![Beispiel-Kalibrierung mit Edelstein.](./images/08-et-gems.png)

![Kalibrierung anpassen.](./images/09-et-adjusting.png)

Wenn die Kalibrierung erfolgreich war, wird ein Erfolgsbildschirm angezeigt.  Falls nicht, lesen Sie mehr über die [Diagnose von Kalibrierungsfehlern](#troubleshooting-hololens-2-calibration).

![Dialogfenster zu erfolgreicher Kalibrierung.](./images/10-et-success.png)

### Kalibrierung beim Freigeben eines Geräts oder einer Sitzung

Mehrere Benutzer können ein HoloLens 2-Gerät gemeinsam nutzen, ohne dass jede Person die Geräteeinrichtung durchführen muss. Wenn ein neuer Benutzer das Gerät zum ersten Mal aufsetzt, fordert HoloLens 2 ihn automatisch auf, die visuellen Elemente zu kalibrieren. Wenn ein Benutzer, der zuvor die visuellen Elemente kalibriert hat, das Gerät aufsetzt, passt die Anzeige die Qualität sowie die komfortable Anzeigeumgebung nahtlos an.  

### Manuelles Starten des Kalibrierungsvorgangs

1. Verwenden Sie die Startgeste, um das [**Startmenü**](hololens2-basic-usage.md#start-gesture) zu öffnen.
1. Wenn die Einstellungs-App nicht an **Start** angeheftet ist, wählen Sie **Alle Apps** aus.
1. Wählen Sie **Einstellungen** aus, und wählen Sie dann **System** > **Kalibrierung** > **Kalibrierung der Augen** > **Kalibrierung der Augen ausführen** aus.

   ![Die Einstellungs-App mit der Option „Kalibrierung der Augen ausführen”](./images/C-Settings.Calibration.png)

### Unterstützung der automatischen Augenstellung

Bei HoloLens 2 wird durch die Augenstellungen eine genaue Hologramm-Positionierung, ein komfortables Seherlebnis und eine verbesserte Anzeigequalität ermöglicht. Die Augenstellungen werden intern im Rahmen der Eye-Tracking-Berechnung bestimmt. Dazu müssen alle Benutzer eine Eye Tracking-Kalibrierung durchführen, auch wenn keine Eingabe über Anvisieren erforderlich ist.

**Auto Eye Position (AEP, automatische Augenstellung)** ermöglicht diese Szenarien durch eine interaktionsfreie Methode zur Berechnung der Stellung der Augen des Benutzers. Auto Eye Position beginnt automatisch im Hintergrund zu arbeiten, sobald der Benutzer das Gerät anlegt. Wenn ein Benutzer zuvor keine Eye Tracking-Kalibrierung durchgeführt hat, beginnt Auto Eye Position nach einer kurzen Verarbeitungszeit von 20-30 Sekunden, die Augenstellungen des Benutzers an das Anzeigesystem zu übermitteln. Die Benutzerdaten werden nicht auf dem Gerät gespeichert, und dieser Vorgang wird wiederholt, wenn der Benutzer das Gerät ausschaltet und wieder einschaltet, oder wenn das Gerät neu gestartet oder aus dem Ruhezustand reaktiviert wird.

Es gibt ein paar Änderungen hinsichtlich des Systemverhaltens bei der Funktion Auto Eye Position, wenn ein nicht kalibrierter Benutzer das Gerät anlegt. In diesem Zusammenhang bezieht sich der Begriff „nicht kalibrierter Benutzer“ auf eine Person, die den Eye-Tracking-Kalibrierungsprozess auf dem Gerät zuvor noch nicht durchlaufen hat.

| Aktive Anwendung | Früheres Verhalten | Verhalten ab Windows Holographic, Version 20H2-Update |
|:-------------------|:-----------------|:-----------------------------------|
| App oder Holographic Shell ohne Eingabe über Anvisieren |Dialogfeld zur Eye-Tracking-Kalibrierung wird angezeigt. | Es wird kein Dialogfeld angezeigt. |
| App mit Eingabe über Anvisieren | Dialogfeld zur Eye-Tracking-Kalibrierung wird angezeigt. | Das Dialogfeld zur Eye-Tracking-Kalibrierung wird nur angezeigt, wenn die Anwendung auf Blickdaten zugreift. |

Wenn Benutzer von einer Anwendung ohne Eingabe über Anvisieren zu einer Anwendung wechseln, die auf Blickdaten zugreift, wird das Kalibrierungsdialogfeld angezeigt. 

Alle anderen Systemverhalten sind jenem ähnlich, wenn keine aktive Eye Tracking-Kalibrierung für den aktuellen Benutzer vorliegt. Beispielsweise wird die einhändige Startgeste nicht aktiviert sein. Bei der Ersteinrichtung wird es keine Änderung an der Standardumgebung geben.

Bei Umgebungen, für die Blickdaten oder eine präzise Hologramm-Positionierung erforderlich sind, empfehlen wir nicht kalibrierten Benutzern, die Eye Tracking-Kalibrierung durchzuführen. Sie kann über das Dialogfeld zur Eye-Tracking-Kalibrierung aufgerufen werden. Starten Sie alternativ die Einstellungs-App aus dem Startmenü, und wählen Sie dann **System > Kalibrierung > Augenkalibrierung > Augenkalibrierung auszuführen** aus.

#### Verzögerte Anzeige des Kalibrierungsdialogfelds

Bei aktivierter Auto Eye Position-Funktion wird die Anzeige des Dialogfelds zur Eye-Tracking-Kalibrierung so lange verzögert, bis eine Anwendung Blickdaten anfordert. Dadurch wird sichergestellt, dass dem Benutzer das Dialogfeld nicht angezeigt wird, wenn die aktive Anwendung keine Blickdaten erfordert. Wenn die Anwendung Blickdaten erfordert und der aktuelle Benutzer nicht kalibriert ist, wird ihm das Kalibrierungsdialogfeld angezeigt. Dieses Verhalten kann dazu genutzt werden, das Dialogfeld zur Eye-Tracking-Kalibrierung zu einem geeigneten Zeitpunkt während der Verwendung des Geräts anzuzeigen. Diese Methode empfiehlt sich aus den folgenden Gründen:

1.  Das Dialogfeld zur Eye-Tracking-Kalibrierung informiert den Benutzer darüber, warum das Eye-Tracking erforderlich ist.
2.  Es bietet dem Benutzer eine Möglichkeit, die Kalibrierung seiner Augen abzulehnen.

Wenn der Benutzer die Eye-Tracking-Kalibrierung startet, sollte der Fokus nach Abschluss der Kalibrierung wieder zur ursprünglichen Anwendung zurückkehren. 

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

Wenn Sie alle Anweisungen befolgt haben und die Kalibrierung weiterhin fehlschlägt, können Sie das Kalibrierungsdialogfeld in den Einstellungen deaktivieren. Teilen Sie uns dies auch mit, indem Sie Feedback im [Feedback Hub](hololens-feedback.md) abgeben.

Lesen Sie auch entsprechende Informationen zum [Behandeln von Problemen bei Bildfarbe oder Helligkeit](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right).

Das Einstellen des IPD ist für HoloLens 2 nicht anwendbar, da die Augenpositionen vom System berechnet werden. 

### Kalibrierungsdaten und Sicherheit

Kalibrierungsinformationen werden lokal auf dem Gerät gespeichert und keinem Konto zugeordnet. Es gibt keine Aufzeichnung darüber, wer das Gerät ohne Kalibrierung verwendet hat. Dies bedeutet, dass neue Benutzer bei der ersten Verwendung des Geräts aufgefordert werden, visuelle Elemente zu kalibrieren, sowie Benutzer, die zuvor die Kalibrierung deaktiviert haben oder wenn die Kalibrierung nicht erfolgreich war.

Auf dem Gerät können bis zu 50 Kalibrierungsprofile lokal gespeichert werden. Wenn diese Zahl erreicht ist, löscht das Gerät automatisch das älteste nicht verwendete Profil.

Kalibrierinformationen können unter **Einstellungen** > **Datenschutz** > **Eyetracker** zu jeder Zeit vom Gerät gelöscht werden.  

### Kalibrierung deaktivieren

Sie können die Aufforderung zur Kalibrierung auch deaktivieren, indem Sie die folgenden Schritte ausführen:

1. Wählen Sie **Einstellungen** > **System** > **Kalibrierung** aus.
1. Deaktivieren Sie die Option **Wenn eine neue Person diese HoloLens verwendet, automatische Aufforderung zur Ausführung der Augenkalibrierung**.

> [!IMPORTANT]
> Diese Einstellung kann die Qualität und den Komfort der Hologrammwiedergabe beeinträchtigen.  Wenn Sie diese Einstellung deaktivieren, funktionieren Features, die von Eye Tracking abhängig sind (z. B. Textbildlauf), nicht mehr in immersiven Anwendungen.

### HoloLens 2 Eye Tracking-Technologie

Das Gerät verwendet seine Eye Tracking-Technologie, um die Anzeigequalität zu verbessern und um sicherzustellen, dass alle Hologramme exakt und bequem in 3D positioniert werden können. Da die Augen als Orientierungspunkte verwendet werden, kann sich das Gerät an jeden Benutzer anpassen und seine visuellen Elemente optimieren, wenn das Headset während der Verwendung geringfügig verschoben wird.  Alle Anpassungen erfolgen im Handumdrehen, ohne die Notwendigkeit einer manuellen Einstellung.
> [!NOTE]
> Das Einstellen des IPD ist für HoloLens 2 nicht anwendbar, da die Augenpositionen vom System berechnet werden.

HoloLens-Anwendungen verwenden Eye Tracking, um in Echtzeit nachzuverfolgen, wo Sie hinschauen. Dies ist die Hauptfunktion, die Entwickler nutzen können, um eine ganz neue Ebene von Kontext, menschlichem Verständnis und Interaktionen innerhalb der holografischen Erfahrung zu ermöglichen. Entwickler müssen nichts unternehmen, um diese Funktion nutzen zu können.

## Kalibrieren Ihrer HoloLens (1. Generation)

HoloLens (1. Generation) passt die Anzeige von Hologrammen entsprechend dem [Pupillenabstand](https://en.wikipedia.org/wiki/Interpupillary_distance) (Interpupillary Distance, IPD) an. Wenn der IPD nicht genau ist, erscheinen Hologramme möglicherweise instabil oder in falschem Abstand. Sie können die Qualität der visuellen Darstellung verbessern, indem Sie das Gerät auf Ihren Pupillenabstand (IPD) kalibrieren.

Beim Einrichten Ihrer HoloLens (1. Generation) werden Sie aufgefordert, Ihre visuellen Elemente zu kalibrieren, nachdem Cortana sich vorgestellt hat. Es wird empfohlen, den Kalibrierungsvorgang während dieser Einrichtungsphase abzuschließen. Sie können ihn jedoch überspringen, indem Sie warten, bis Cortana Sie auffordert, und dann „Überspringen” sagen.

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
