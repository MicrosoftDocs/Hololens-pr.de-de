---
title: Problembehandlung für das HoloLens 2-Display
description: Erwartungen an HoloLens 2-Displays. Anleitung zum Konfigurieren von Displays für optimale Bildqualität.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: Display, Kalibrierung, Komfort, visuelle Elemente, Qualität, Augenabstand
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 3567c1f33f10240a9cacbf258669a0e3274f4c6bb3c90fc1317a57a3a415fc7f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659943"
---
# <a name="hololens-2-display-troubleshooting"></a>Problembehandlung für das HoloLens 2-Display

## <a name="overview"></a>Übersicht
Das Display der HoloLens 2 ist eine Kombination aus Wellenleitern und Lichtprojektoren. Benutzer blicken beim Tragen des Headsets durch die Wellenleiter, d. h. die Linsen im Visier. Die Lichtprojektoren befinden sich im Gehäuse über dem Stirnbereich. Das HoloLens 2-Display wird durch Laserlicht beleuchtet.

## <a name="troubleshooting"></a>Problembehandlung

Führen Sie die folgenden Schritte aus, um die höchste visuelle Qualität von Hologrammen auf Displays zu gewährleisten:

* **Erhöhen Sie die Helligkeit des Displays.** Hologramme sehen am besten aus, wenn die höchste Helligkeitsstufe des Displays eingestellt ist. Beim Tragen der HoloLens befinden sich die Tasten für Helligkeit auf der linken Seite des Visiers in der Nähe Ihrer Schläfe.
* **Holen Sie das Visier näher an Ihre Augen heran.** Schwenken Sie das Visier nach unten in die Position, die Ihren Augen am nächsten ist.
* **Schieben Sie das Visier nach unten.** Versuchen Sie, das Stirnpolster auf der Stirn nach unten zu bewegen, was dazu führt, dass sich das Visier in einer tieferen Position und näher an der Nase befindet.
* **[Führen Sie die Kalibrierung der Augen aus.](hololens-calibration.md#calibrating-your-hololens-2)** Das Display optimiert Bilder auf dem Display anhand Ihres Augenabstands und Blicks. Wenn Sie keine Augenkalibrierung ausführen, kann sich die Bildqualität verschlechtern. Um die Augenkalibrierung auszuführen, wechseln Sie zu **Einstellungen** > **System** > **Kalibrierung** > **Augenkalibrierung ausführen**.
* **Führen Sie die Farbkalibrierung des Displays aus.** Ab der [Windows Holographic-Version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) können Sie für Ihr HoloLens 2-Display **ein alternatives Farbprofil auswählen**. Dies kann dazu beitragen, dass Farben genauer angezeigt werden, insbesondere bei niedrigeren Helligkeitsstufen im Display. Die Farbkalibrierung des Displays finden Sie in der App **Einstellungen** auf der Seite **System > Kalibrierung.**

    > [!NOTE]
    > Da durch diese Einstellung ein neues Farbprofil in der Firmware Ihres Displays gespeichert wird, handelt es sich um eine gerätespezifische Einstellung (und nicht um eine eindeutige für jedes Benutzerkonto).

### <a name="how-to-use-display-color-calibration"></a>Kalibrierung der Displayfarben
1. Starten Sie die App **Einstellungen**, und wechseln Sie zu **System > Kalibrierung**.
1. Wählen Sie unter **Display color calibration** (Farbkalibrierung des Displays) die Schaltfläche **Run display color calibration** (Farbkalibrierung des Displays ausführen) aus.
1. Die Oberfläche zur Farbkalibrierung des Displays wird eingeblendet und bittet Sie zu prüfen, um sich Ihr Visier in der richtigen Position befindet.
1. Nachdem Sie die Anweisungsdialogfelder durchlaufen haben, wird das Display automatisch auf eine Helligkeit von 30 % abgeblendet.
    > [!TIP]
    > Wenn Sie Probleme haben, die abgeblendete Szenerie in Ihrer Umgebung zu sehen, können Sie den Helligkeitspegel der HoloLens 2 manuell justieren, indem Sie links am Gerät auf die Tasten für Helligkeit drücken.
1. Wählen Sie die Tasten 1-6 aus, um die einzelnen Farbprofile sofort auszuprobieren und dasjenige zu finden, das in Ihren Augen am besten aussieht (dies bedeutet in der Regel das Profil, das die Szene am neutralsten erscheinen lässt, wobei die Graustufenmuster und Hautfarbtöne wie erwartet aussehen).

    ![Szenerie zur Farbkalibrierung des Displays](images/color-cal-ui.png)
    
6. Wenn Sie mit dem ausgewählten Profil zufrieden sind, wählen Sie die Schaltfläche **Speichern und beenden** aus.
1. Wenn Sie keine Änderungen vornehmen möchten, wählen Sie die Schaltfläche **Abbrechen und beenden** aus, woraufhin Ihre Änderungen zurückgesetzt werden.

> [!TIP]
> Es folgen einige hilfreiche Tipps, die Sie bei der Verwendung der Einstellung zur Farbkalibrierung des Displays beachten sollten:
> - Sie können in „Einstellungen“ die Farbkalibrierung des Displays nach Bedarf erneut ausführen.
> - Wenn jemand auf dem Gerät zuvor die Einstellung zum Ändern von Farbprofilen verwendet hat, werden Datum und Zeit dieser letzten Änderung auf der Seite „Einstellungen“ angezeigt.
> - Wenn Sie die Farbkalibrierung des Displays erneut ausführen, wird das zuvor gespeicherte Farbprofil hervorgehoben und Profil 0 nicht angezeigt (da Profil 0 das ursprüngliche Farbprofil des Displays darstellt).
> - Wenn Sie zum ursprünglichen Farbprofil des Displays zurückkehren möchten, wechseln Sie dazu zur Seite „Einstellungen“ (weitere Informationen zum [Zurücksetzen des Farbprofils](#how-to-reset-color-profile)).

### <a name="how-to-reset-color-profile"></a>Zurücksetzen des Farbprofils

Wenn Sie nicht mit dem benutzerdefinierten Farbprofil zufrieden sind, das in Ihrer HoloLens 2 gespeichert ist, können Sie das ursprüngliche Farbprofil des Geräts wiederherstellen:
1. Starten Sie die App **Einstellungen**, und wechseln Sie zu **System > Kalibrierung**.
1. Wählen Sie unter **Display color calibration** (Farbkalibrierung anzeigen) die Schaltfläche **Reset to default color profile** (Auf Standardfarbprofil zurücksetzen) aus.
1. Wenn das Dialogfeld geöffnet wird, wählen Sie **Neu starten** aus, wenn Sie die HoloLens 2 neu starten und Ihre Änderungen übernehmen möchten.

### <a name="top-display-color-calibration-known-issues"></a>Bekannte Probleme bei der Farbkalibrierung des Displays

- Auf der Seite „Einstellungen“ ist die Statuszeichenfolge, die angibt, wann das Farbprofil zuletzt geändert wurde, solange veraltet, bis Sie die Seite „Einstellungen“ neu laden. 
    - **Problemumgehung**: Wählen Sie eine andere Seite „Einstellungen“ und dann die Seite „Kalibrierung“ erneut aus.
- Wenn Ihre HoloLens 2 während der Farbkalibrierung des Displays in den Ruhezustand versetzt wird, wird sie später in Mixed Reality-Startumgebung fortgesetzt, und der Helligkeitspegel der Anzeige ist weiterhin abgeblendet.
- Möglicherweise müssen Sie die Tasten für Helligkeit links am Gerät einige Male nach oben/unten zu drücken, bevor sie wie erwartet funktionieren.
- Die Lokalisierung ist nicht für alle Märkte abgeschlossen.

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>Was sind die Muster, die gelegentlich in den unteren Ecken des Displays blinken?

Auf dem Display Ihrer HoloLens 2 sind in der linken und rechten unteren Ecke gelegentlich verschiedene Muster zu sehen. Beispiele hierfür sind nachstehend dargestellt (animierte GIFs). Dieses Muster gehört zum normalen Betrieb des HoloLens 2-Geräts zum Kalibrieren des Displays für ein optimales Erlebnis.

![Zweiphasiges Muster](./images/DAT-Biphase-Fiducial.gif) ![GEO-Muster](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>Warum kann ich kein einwandfreies Foto von meinem HoloLens 2-Display machen?

Das HoloLens 2-Display ist für die Betrachtung durch das menschliche Auge konzipiert. Das Gerät verfügt über ein aktives Farbkorrektursystem, das sich an die Augen eines Benutzers anpasst. Kameras „sehen“ Umgebungen anders als das menschliche Auge. Nachfolgend sind einige Faktoren aufgeführt, die zu Abweichungen zwischen Kameraaufnahmen und dem, was ein Benutzer sieht, führen können.

* **Augenstellung.** Das HoloLens 2-Display ist speziell für die Augenstellung des Benutzers konzipiert. HoloLens 2 nutzt Eye-Tracking-Technologie, um sich an die Augenstellung des Benutzers anzupassen. Eine um wenige Millimeter falsch positionierte Kamera kann zu Bildverzerrungen führen. Eine genaue Positionierung mit einer Kamera ist schwierig und muss exakt der Position und dem Abstand zwischen Auge und Linse entsprechen, für die das Gerät die Farbkorrektur durchführt.
* **Augenbewegung.** Das Display passt sich an die Augenbewegung eines Benutzers an, um Farben anzupassen. Was auf dem Display gezeigt wird, hängt davon ab, ob der Benutzer die Mitte, den Rand oder eine Ecke des Displays betrachtet. Eine einzelne Bildaufnahme könnte bestenfalls zeigen, wie die Anzeige für die Achse aussieht, die mit einer Blickrichtung übereinstimmt.
* **Beidäugiges Sehen.** Das Display der HoloLens 2 ist für die Betrachtung mit beiden Augen ausgelegt. Das Gehirn passt sich an das Sehen zweier Bilder an und verschmilzt sie miteinander. Bilder von nur einem Display ignorieren die Informationen des anderen Displays.
* **Kamerabelichtungszeit.** Die Belichtungszeit der Kamera muss ein exaktes Vielfaches von 1/120stel Sekunde sein. Die Bildfrequenz des HoloLens-Displays ist 120 Hz. Aufgrund der Art und Weise, wie die HoloLens 2 Bilder zeichnet, reicht das Aufnehmen eines Einzelbilds nicht aus, um die Wahrnehmung des menschlichen Auges wiederzugeben. Gleichzeitig projiziert das System bei jeder noch so kleinen Bewegung des Geräts das Bild auf dem Display neu, um Hologramme zu stabilisieren. Das Aufnehmen mehrerer Einzelbilder, ohne dass sich die HoloLens bewegt, erfordert normalerweise eine Laboranordnung.
* **Blendengröße der Kamera.** Die Blendengröße der Kamera muss mindestens 3 mm betragen, um ein getreues Bild aufnehmen zu können. Handykameras mit kleinen Blenden integrieren Licht aus einem kleineren Bereich als das menschliche Auge. Das Gerät wendet eine Farbkorrektur für Muster an, die für größere Blenden typisch sind. Bei kleinen Blenden sind Homogenitätsmuster schärfer und bleiben trotz Farbkorrekturen durch das System sichtbar.
* **Eintrittspupille der Kamera.** Für die Aufnahme eines getreuen Bilds muss die Eintrittspupille der Kamera einen Durchmesser von mindestens 3 mm aufweisen. Ansonsten nimmt die Kamera einige Hochfrequenzmuster auf, die für das Auge nicht sichtbar sind. Die Position der Eintrittspupille muss sich sowohl vor der Kamera als auch im Augenabstand befinden, damit keine Abbildungsfehler und andere Abweichungen in das aufgenommene Bild gelangen.
* **Kameraposition.** Kameras, die die Anforderungen für die Betrachtung des HoloLens 2-Displays erfüllen, sind größer, und es ist schwierig, die Kamera nahe genug am HoloLens 2-Display zu positionieren, um das farbkorrigierte Bild zu betrachten. Wenn sich die Kamera an der falschen Stelle befindet, kann sich die Farbkorrektur negativ auf die Aufnahme des HoloLens 2-Displays auswirken.
* **Bildkorrektur.** Handelsübliche Digital- und Smartphonekameras wenden eine Gradiationskurve an, die Kontrast und Farbe verstärkt, um ein schärferes Ergebnis zu erzielen. Bei Anwenden auf ein HoloLens 2-Display werden durch diese Tonwertkorrektur Ungleichmäßigkeiten verstärkt.

Dennoch ist es für spezialisierte Industriekameras möglich, repräsentative Bilder vom HoloLens 2-Display aufzunehmen. Leider können Smartphone-, normale und professionelle Kameras keine Bilder aufnehmen, die dem entsprechen, was ein Benutzer auf der HoloLens 2 sieht.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>Wie wirkt sich die Augenkalibrierung auf die Bildqualität des Displays aus?

Das HoloLens 2-Display korrigiert aktiv die Farben von Bildern basierend auf der Position der Augen des Benutzers. Die [Augenkalibrierung](hololens-calibration.md) bietet zwei wichtige Eingaben: (1) den Augenabstand des Benutzers und (2) die Blickrichtung der einzelnen Augen. Ohne Augenkalibrierung nimmt das System standardmäßig eine nominale Augenstellung ohne Augenbewegung ein. Der Unterschied zwischen aktiver Farbkorrektur und keiner Korrektur hängt von der Physiologie des Benutzers selbst ab. Benutzer, die z. B. den gleichen Augenabstand wie in der Standardeinstellung des Systems haben, sehen weniger Verbesserungen durch Farbkorrektur. Benutzer, die einen viel engeren oder weiteren Augenabstand als die Standardeinstellung des Systems haben, nehmen dagegen mehr Änderungen am Displaybild wahr.

Hinweis: ein neues Feature in der [Windows Holographic-Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) startet [die automatische Erkennung der Augenstellung](hololens-calibration.md#auto-eye-position-support). 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>Welche Unterschiede gibt es beim Display zwischen HoloLens (1. Generation) und HoloLens 2?

Zu den wichtigsten Wünschen, die Kunden an Microsoft herangetragen haben, nachdem sie die HoloLens 1 ausprobiert hatten, gehörten (1) ein größeres Sichtfeld und (2) höhere Helligkeit. Technologische Weiterentwicklungen ermöglichten Microsoft die Herstellung von Wellenleitern zur Verdoppelung der Sichtfeldfläche und die Herstellung von Lichtprojektoren mit einem bis zu dreimal helleren Display. Die Hardware bildet die Grundlage für drei miteinander in Konflikt stehende Elemente für die Bildqualität des Displays: (1) Sichtfeld, (2) Helligkeit und (3) Farbhomogenität. Fortwährende technologische Fortschritte ermöglichen Verbesserungen in allen Bereichen, ohne dass bei einem Abstriche gemacht werden müssen. In der Zwischenzeit legen die vorhandenen Technologien die Grenzen für die Lösung dieser Konflikte fest.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>Welche Verbesserungen wird es in puncto Bildqualität bei HoloLens 2 geben?

Während wir viele Anstrengungen zur Verbesserung der Bildqualität unternehmen, sind die folgenden Bereiche in den nächsten Updates zu erwarten:

* **Automatische Augenstellung.** Dank dieses Features können die Verfahren zur Augenkalibrierung im Hintergrund erfolgen. Benutzer müssen keine Augenkalibrierung mehr ausführen, damit die aktive Farbkorrektur funktioniert. Sie wird stattdessen einfach funktionieren.
* **Verbesserungen bei der Farbkalibrierung.** Bei diesem Update stehen die Farbwerte dunklerer Farben (beispielsweise dunkelgrau) im Mittelpunkt. Derzeit nehmen dunklere Farben einen Rotstich an. Dieses Problem tritt auch auf, wenn das gesamte Display abgedunkelt wird – das gesamte Display wird rötlich. Die Ursache dieses Problems ist zu viel Aktivität im roten Farbkanal für diese dunkleren Farben. Wir haben die Laserbeleuchtungskurven bei diesen dunkleren Farben spezifiziert und arbeiten daran, den Benutzern ein Kalibrierungsverfahren anzubieten. Das Ergebnis ist eine größere Farbgenauigkeit im gesamten Helligkeitsspektrum. Die Darstellung weißer Hintergründe bei voller Helligkeit wird dadurch nicht geändert. Wir empfehlen weiterhin die Verwendung von Entwurfsmustern im dunklen Modus in Apps.
* **Lesemodus.** App-Entwickler können das Sichtfeld des Displays zugunsten einer höheren Winkelauflösung reduzieren. App-Entwickler können die Projektionsmatrix so überschreiben, dass Inhalte in der Zeichnungsauflösung des Displays gerendert werden. Dieses Feature bewirkt eine Reduzierung des Sichtfelds um 30 % und eine entsprechende Erhöhung der Winkelauflösung. Es wird daran gearbeitet, diese Funktionalität in das [Mixed Reality Toolkit](https://github.com/Microsoft/MixedRealityToolkit-Unity) aufzunehmen. Sobald der Lesemodus verfügbar ist, funktioniert er mit jedem HoloLens 2-Betriebssystem und hängt nicht von einem Betriebssystemupdate ab.

Betriebssystemupdates werden automatisch bereitgestellt. Sie können auch frühe Releases der verbesserten Software im Rahmen des Insider Preview-Programms testen.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>Welche Anleitungen stehen Entwicklern zur Verfügung, um Entwurfsprinzipien für den dunklen Modus umzusetzen?

Benutzer sollten am besten weiße Hintergründe vermeiden. Der dunkle Modus ist ein Entwurfsprinzip, das von Apps für schwarze oder dunkle Hintergründe verwendet wird. In den Systemeinstellungen ist standardmäßig der dunklen Modus aktiviert, der über **Einstellungen** > **System** > **Farbe** angepasst werden kann.

Entwicklern wird empfohlen, die Entwurfsanleitung für den dunklen Modus zu befolgen:

* [Entwurfsrichtlinien für HoloLens-Displays für Entwickler](/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Empfohlene Schriftgrade](/windows/mixed-reality/typography#recommended-font-size)

Wenn für ein Hologramm ein weißer Hintergrund erforderlich ist, sollte es kleiner als das vollständige Sichtfeld des Displays sein. Bei dieser Größe können Benutzer das Hologramm in die Mitte des Displays platzieren.

### <a name="how-do-you-clean-a-hololens-2-display"></a>Wie lässt sich ein HoloLens 2-Display reinigen?

Reinigen Sie das Visier vorsichtig mit einem Mikrofasertuch. Desinfizieren Sie das Visier mit 70 %-igem Isopropylalkohol. Befeuchten Sie damit ein Tuch, und wischen sie das Visier ab. Lesen Sie die vollständige Anleitung in den [häufig gestellten Fragen zur HoloLens 2-Reinigung](hololens2-maintenance.md).
