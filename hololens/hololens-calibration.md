---
title: Verbessern von Grafikqualität und Komfort
description: Erfahren Sie, wie Sie Ihren Augenabstand (IPD) kalibrieren können, um die Qualität Ihrer Visualisierung auf HoloLens-Geräten zu verbessern.
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
ms.openlocfilehash: b3d917c71ac7441aeaf8dcbc25748ee07b9fbfa3
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189204"
---
# <a name="improve-visual-quality-and-comfort"></a>Verbessern von Grafikqualität und Komfort

HoloLens 2 und HoloLens (1. Generation) funktionieren beide besser, wenn sie spezifisch für Ihre Augen kalibriert werden.

Beide Geräte müssen zwar für eine optimale Darstellung des Hologramms kalibriert werden, verwenden jedoch unterschiedliche Kalibrierungstechnologien und -techniken.  Wechseln Sie zu [HoloLens 2 Kalibrierung](#calibrating-your-hololens-2) oder [HoloLens Kalibrierung (1. Generation)](#calibrating-your-hololens-1st-gen).

## <a name="calibrating-your-hololens-2"></a>Kalibrieren Ihrer HoloLens 2

HoloLens 2 verwendet die Eye Tracking-Technologie, um das Sehen von und die Interaktion mit der virtuellen Umgebung zu verbessern. Durch die Kalibrierung der HoloLens 2 wird sichergestellt, dass Ihre Augen (und die Augen aller anderen Benutzer des Geräts) genau nachverfolgt werden können. Es hilft außerdem beim Benutzerkomfort, der Hologramm-Ausrichtung und der Hand Verfolgung. Nach der Kalibrierung werden Hologramme korrekt angezeigt, auch wenn sich das Visier auf Ihrem Kopf verschiebt.

HoloLens 2 fordert den Benutzer auf, das Gerät unter den folgenden Umständen zu kalibrieren:

- Der Benutzer verwendet das Gerät zum ersten Mal
- Der Benutzer hat sich zuvor von dem Kalibrierungsvorgang abgemeldet
- Der Kalibrierungsvorgang war bei der letzten Verwendung des Geräts durch den Benutzer nicht erfolgreich
- Der Benutzer hat seine Kalibrierungsprofile gelöscht
- Das Gerät wird abgenommen und wieder aufgesetzt und einer der oben genannten Umstände trifft zu 


![Kalibrierungsabfrage zur Anpassung an die Augen.](./images/07-et-adjust-for-your-eyes.png)

Während dieses Vorgangs sehen Sie sich eine Reihe von Zielen (Edelsteinen) an. Es ist in Ordnung, wenn Sie während der Kalibrierung blinzeln. Versuchen Sie sich jedoch auf die Edelsteine zu konzentrieren, und nicht auf andere Gegenstände im Raum.  Durch die Fokussierung auf die Edelsteine kann HoloLens Ihre Augenposition ermitteln, um Ihre holografische Welt darzustellen.

![Die Kalibrierungsaufforderung fordert die Benutzer auf, den Kopf ruhig zu halten und den Punkten mit den Augen zu folgen.](./images/07-et-hold-head-still.png)

![Beispiel-Kalibrierungsabfrage mit Edelstein.](./images/08-et-gems.png)

![Kalibrierungsabfrage anpassen.](./images/09-et-adjusting.png)

Wenn die Kalibrierung erfolgreich war, wird ein Erfolgsbildschirm angezeigt.  Falls nicht, erfahren Sie mehr über [die Diagnose von Kalibrierungsfehlern](hololens2-display.md#troubleshooting).

![Erfolgreicher Kalibrierungabfrage.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Kalibrierung bei gemeinsamer Nutzung eines Geräts oder einer Sitzung

Mehrere Benutzer können ein HoloLens 2-Gerät gemeinsam nutzen, ohne dass jede Person die Geräteeinrichtung durchführen muss. Wenn ein neuer Benutzer das Gerät zum ersten Mal auf den Kopf setzt, fordert HoloLens 2 ihn automatisch auf, die visuellen Elemente zu kalibrieren. Wenn ein Benutzer, der zuvor die visuellen Elemente kalibriert hat, das Gerät auf den Kopf setzt, passt die Anzeige die Qualität sowie die komfortable Anzeigeumgebung nahtlos an.  

### <a name="manually-starting-the-calibration-process"></a>Manuelles Starten des Kalibrierungsvorgangs

1. Verwenden Sie die Startgeste, um das [**Startmenü**](hololens2-basic-usage.md#start-gesture) zu öffnen.
1. Wenn die Einstellungen-App nicht an **Start** angeheftet ist, wählen Sie **Alle Apps** aus.
1. Wählen Sie **Einstellungen** und dann **System** > **Kalibrierung** > **Augenkalibrierung** > **Augenkalibrierung ausführen** aus.

   ![Die App „Einstellungen“, die die Option „Augenkalibrierung ausführen“ anzeigt.](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Unterstützung der automatischen Augenstellung

Bei HoloLens 2 wird durch die Augenstellungen eine genaue Hologramm-Positionierung, ein komfortables Seherlebnis und eine verbesserte Anzeigequalität ermöglicht. Die Augenstellungen werden intern im Rahmen der Eye-Tracking-Berechnung bestimmt. Dies erfordert jedoch, dass jeder Benutzer eine Eye-Tracking-Kalibrierung durchläuft, auch wenn das Erlebnis möglicherweise keine Blickeingabe erfordert.

**Auto Eye Position (AEP)** ermöglicht diese Szenarien durch eine interaktionsfreie Methode zur Berechnung der Augenstellung des Benutzers. Auto Eye Position beginnt automatisch im Hintergrund zu laufen, sobald der Benutzer das Gerät aufsetzt. Wenn ein Benutzer zuvor keine Eye Tracking-Kalibrierung durchgeführt hat, beginnt Auto Eye Position nach einer Verarbeitungszeit von 20-30 Sekunden, die Augenstellungen des Benutzers an das Anzeigesystem bereitzustellen. Die Benutzerdaten werden nicht auf dem Gerät gespeichert, und dieser Vorgang wird wiederholt, wenn der Benutzer das Gerät abnimmt und wieder aufsetzt, oder wenn das Gerät neu gestartet oder aus dem Ruhezustand reaktiviert wird.

Es gibt ein paar Änderungen hinsichtlich des Systemverhaltens bei der Funktion Auto Eye Position, wenn ein nicht kalibrierter Benutzer das Gerät aufsetzt. In diesem Zusammenhang bezieht sich der Begriff „nicht kalibrierter Benutzer“ auf eine Person, die den Eye-Tracking-Kalibrierungsprozess auf dem Gerät zuvor noch nicht durchlaufen hat.

| Aktive Anwendung | Früheres Verhalten | Verhalten ab Windows Holographic, Version 20H2-Update |
|:-------------------|:-----------------|:-----------------------------------|
| Nicht-Anvisieren ist in der App oder Holographic Shell aktiviert |Eingabeaufforderung zur Eye-Tracking-Kalibrierung wird angezeigt. | Es wird kein Eingabeaufforderung angezeigt. |
| Anvisieren ist in der App aktiviert | Eingabeaufforderung zur Eye-Tracking-Kalibrierung wird angezeigt. | Das Dialogfeld zur Eye-Tracking-Kalibrierung wird nur angezeigt, wenn die Anwendung auf den Blickfluss zugreift. |

Wenn Benutzer von einer Anwendung mit aktiviertem Nicht-Anvisieren zu einer Anwendung wechseln, die auf Blickdaten zugreift, wird die Kalibrierungsaufforderung angezeigt. 

Alle anderen Systemverhalten sind denen ähnlich, die keine aktive Eye Tracking-Kalibrierung für den aktuellen Benutzer haben. Beispielsweise wird die einhändige Startgeste nicht aktiviert sein. Die Out-Of-Box-Experience für die Ersteinrichtung wird nicht verändert.

Bei Umgebungen, für die Blickdaten oder eine präzise Hologramm-Positionierung erforderlich sind, empfehlen wir nicht kalibrierten Benutzern, die Eye Tracking-Kalibrierung durchzuführen. Sie kann über das Eingabeaufforderung zur Eye-Tracking-Kalibrierung aufgerufen werden. Starten Sie alternativ die Einstellungen-App aus dem Startmenü, und wählen Sie dann **System > Kalibrierung > Augenkalibrierung > Augenkalibrierung durchführen**.

#### <a name="deferred-calibration-prompt"></a>Verzögerte Anzeige des Kalibrierungsaufforderung

Bei aktivierter Auto Eye Position-Funktion wird die Anzeige des Dialogfelds so lange verzögert, bis eine Anwendung die Blickdaten anfordert. Dadurch wird sichergestellt, dass dem Benutzer das Dialogfeld nicht angezeigt wird, wenn die aktive Anwendung keine Blickdaten erfordert. Wenn die Anwendung Blickdaten erfordert und der aktuelle Benutzer nicht kalibriert ist, wird ihm das Kalibrierungsdialogfeld angezeigt. Dieses Verhalten kann dazu genutzt werden, das Dialogfeld zur Eye-Tracking-Kalibrierung zu einem geeigneten Zeitpunkt für die Erfahrung anzuzeigen. Diese Methode empfiehlt sich aus den folgenden Gründen

1.  Das Dialogfeld zur Eye-Tracking-Kalibrierung informiert den Benutzer mit Hinweisen darüber, warum das Eye-Tracking erforderlich ist.
2.  Es bietet dem Benutzer eine Möglichkeit, die Kalibrierung seiner Augen abzulehnen.

Wenn der Benutzer die Eye-Tracking-Kalibrierung startet, sollte der Fokus nach Abschluss der Kalibrierung wieder zur ursprünglichen Anwendung zurückkehren. 

### <a name="calibration-data-and-security"></a>Kalibrierungsdaten und Sicherheit

Kalibrierungsinformationen werden lokal auf dem Gerät gespeichert und sind keinem Konto zugeordnet. Es gibt keine Aufzeichnung darüber, wer das Gerät ohne Kalibrierung verwendet hat. Dies bedeutet, dass neue Benutzer bei der ersten Verwendung des Geräts aufgefordert werden, visuelle Elemente zu kalibrieren, sowie Benutzer, die sich zuvor von der Kalibrierung abgemeldet haben oder wenn die Kalibrierung nicht erfolgreich war.

Auf dem Gerät können bis zu 50 Kalibrierungsprofile lokal gespeichert werden. Wenn diese Zahl erreicht ist, löscht das Gerät automatisch das älteste nicht verwendete Profil.

Kalibrierungsinformationen können immer von dem Gerät gelöscht werden. Wählen Sie dafür auf Ihrem Gerät **Einstellungen** > **Datenschutz** > **Eye Tracker**.  

### <a name="disable-calibration"></a>Kalibrierung deaktivieren

Sie können die Kalibrierungsaufforderung auch deaktivieren, indem Sie die folgenden Schritte ausführen:

1. Wählen Sie **Einstellungen** > **System** > **Kalibrierung**.
1. Deaktivieren Sie **Wenn eine neue Person diese HoloLens benutzt, automatisch dazu auffordern, eine Augenkalibrierung durchzuführen**.

   > [!IMPORTANT]
   > Diese Einstellung kann die Qualität und den Komfort der Hologrammwiedergabe ungünstig beeinträchtigen.  Wenn Sie diese Einstellung deaktivieren, funktionieren Funktionen, die von Eye Tracking abhängig sind (z, B. Textbildlauf), nicht mehr in immersiven Anwendungen.

> [!NOTE]
> Der Schalter „Einstellungen“ wurde entfernt, beginnend mit Windows Holographic, Version 20H2, mit der Einführung der [Auto Eye Position-Unterstützung](hololens-release-notes.md#auto-eye-position-support). Die Kalibrierungsaufforderung wird nur dann automatisch angezeigt, wenn ein nicht kalibrierter Benutzer eine App verwendet, für die Eye Tracking aktiviert ist.

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2 Eye Tracking-Technologie

Das Gerät verwendet seine Eye Tracking-Technologie, um die Anzeigequalität zu verbessern und um sicherzustellen, dass alle Hologramme exakt und bequem in 3D positioniert werden können. Da die Augen als Orientierungspunkte verwendet werden, kann sich das Gerät selbst an jeden Benutzer anpassen und seine visuellen Elemente optimieren, wenn das Headset während der Verwendung geringfügig verschoben wird.  Alle Anpassungen erfolgen im Handumdrehen, ohne die Notwendigkeit einer manuellen Einstellung.
> [!NOTE]
> Das Einstellen des IPD ist für HoloLens 2 nicht anwendbar, da die Augenpositionen vom System berechnet werden.

HoloLens-Anwendungen verwenden Eye Tracking, um in Echtzeit nachzuverfolgen, wo Sie hinschauen. Dies ist die Hauptfunktion, die Entwickler nutzen können, um eine ganz neue Ebene von Kontext, menschlichem Verstehen und Interaktionen innerhalb der holografischen Erfahrung zu ermöglichen. Entwickler müssen nichts unternehmen, um diese Fähigkeit nutzen zu können.

## <a name="calibrating-your-hololens-1st-gen"></a>Kalibrieren Ihrer HoloLens (1. Generation)

HoloLens (1. Generation) passt die Hologrammanzeige an Ihren [Augenabstand](https://en.wikipedia.org/wiki/Interpupillary_distance) (Interpupillary Distance, IPD) an. Wenn der IPD nicht genau ist, erscheinen Hologramme möglicherweise instabil oder in falschem Abstand. Sie können die Qualität der visuellen Darstellung verbessern, indem Sie das Gerät auf Ihren Augenabstand (IPD) kalibrieren.

Beim Einrichten Ihrer HoloLens (1. Generation) werden Sie aufgefordert, Ihre visuellen Elemente zu kalibrieren, nachdem Cortana sich vorgestellt hat. Es wird empfohlen, den Kalibrierungsvorgang während dieser Einrichtungsphase abzuschließen. Sie können ihn jedoch überspringen, indem Sie warten, bis Cortana Sie auffordert, und dann „Überspringen” sagen.

Während des Kalibrierungsvorgangs fordert HoloLens Sie auf, Ihren Finger an einer Folge von sechs Zielen pro Auge auszurichten. HoloLens verwendet diesen Vorgang, um den IPD für Ihre Augen richtig einzustellen.

![Der IPD-Fingerausrichtungsbildschirm im zweiten Schritt.](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Manuelles Starten des Kalibrierungsvorgangs

Wenn Sie die Kalibrierung aktualisieren müssen oder wenn ein neuer Benutzer sie anpassen muss, können Sie die Kalibrierung-App jederzeit manuell ausführen. Die Kalibrierung-App ist standardmäßig installiert. Sie können über das **Startmenü** oder in der Einstellungen-App darauf zugreifen.

Führen Sie die folgenden Schritte aus, um die Kalibrierung-App über das **Startmenü** auszuführen:

1. Verwenden Sie die Geste [Bloom](hololens1-basic-usage.md), um das **Startmenü** zu öffnen.
1. Wählen Sie **+** aus, um alle Apps anzuzeigen.
1. Wählen Sie **Kalibrierung** aus.

   ![Zugreifen auf die Kalibrierungs-App aus der Shell.](./images/calibration-shell.png)

   ![Die Kalibrierungs-App wird nach dem Start als Live-Cube angezeigt.](./images/calibration-livecube-200px.png)

Führen Sie die folgenden Schritte aus, um die Kalibrierung-App über die Einstellungen-App auszuführen:

1. Verwenden Sie die Geste [Bloom](hololens1-basic-usage.md), um das **Startmenü** zu öffnen.
1. Wenn **Einstellungen** nicht an **Start** angeheftet ist, wählen Sie **+** aus, um alle Apps anzuzeigen.
1. Wählen Sie **Settings** aus.
1. Wählen Sie **System** > **Dienstprogramme** > **Kalibrierung öffnen** aus.

   ![Starten der Kalibrierungs-App aus der Einstellungen-App.](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Immersive Headsets

Einige immersive Headsets bieten die Möglichkeit, die IPD-Einstellung anzupassen. Um die IPD für Ihr Headset zu ändern, öffnen Sie die Einstellungen-App und wählen Sie **Mixed Reality** > **Headset-Anzeige** aus und verschieben Sie dann das Schieberegler-Steuerelement. Die Änderungen werden in Echtzeit in Ihrem Headset angezeigt. Wenn Sie Ihren IPD kennen, vielleicht durch einen Besuch beim Optiker, können Sie ihn auch direkt eingeben.

Sie können diese Einstellung auch auf Ihrem PC anpassen, indem Sie **Einstellungen** > **Mixed Reality** > **Headset-Anzeige** auswählen.

Wenn Ihr Headset die IPD-Anpassung nicht unterstützt, ist diese Einstellung deaktiviert.
