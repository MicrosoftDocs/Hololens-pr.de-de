---
title: HoloLens 2-Displays
description: Erwartungen im Hinblick auf HoloLens 2-Displays. Anleitung zum Konfigurieren von Displays für optimale Bildqualität.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: Display, Kalibrierung, Komfort, visuelle Elemente, Qualität, Pupillendistanz
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 80ac6348dd2cba932316b690cafc4c5dc0331353
ms.sourcegitcommit: 77eb85608066d9a4ed01b3862afe356f7e54d583
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2020
ms.locfileid: "10940205"
---
# Das HoloLens 2-Display

Das HoloLens 2-Display ist eine Kombination aus Wellenleitern und Lichtprojektoren. Benutzer blicken beim Tragen des Headsets durch die Wellenleiter, d. h. die Linsen im Visier. Die Lichtprojektoren befinden sich im Gehäuse über dem Stirnbereich. Das HoloLens 2-Display wird durch Laserlicht beleuchtet.

## Problembehandlung

Führen Sie für HoloLens 2 die folgenden Schritte aus, um die höchste visuelle Qualität von Hologrammen auf Displays zu gewährleisten:

* **Erhöhen Sie die Helligkeit des Displays.** Hologramme sehen am besten aus, wenn die höchste Helligkeitsstufe des Displays eingestellt ist.
* **Drücken Sie das Visier so nah wie möglich an Ihre Augen.** Drehen Sie das Visier nach unten, sodass es sich möglichst nah an Ihren Augen befindet.
* **Schieben Sie das Visier nach unten.** Versuchen Sie, das Stirnpolster auf der Stirn nach unten zu bewegen, was dazu führt, dass sich das Visier in einer tieferen Position und näher an der Nase befindet.
* **Führen Sie die Kalibrierung der Augen aus.** Auf dem Display werden Bilder anhand Ihrer Pupillendistanz (PD) und der Blickerkennung optimiert. Wenn Sie keine Augenkalibrierung ausführen, kann sich die Bildqualität verschlechtern. Wenn Sie die Augenkalibrierung ausführen möchten, wechseln Sie zu **Einstellungen** > **System** > **Kalibrierung** > **Augenkalibrierung ausführen**.

## FAQ

### Was sind die Muster, die gelegentlich in den unteren Ecken des Displays aufleuchten?

Auf dem Display Ihrer HoloLens 2 sind gelegentlich unterschiedliche Muster in den unteren linken und rechten Ecken zu sehen. Beispiele hierfür sind nachstehend dargestellt (animierte GIFs). Dieses Muster gehört zum normalen Betrieb des HoloLens 2-Geräts zum Kalibrieren des Displays für optimale Benutzerfreundlichkeit.

![Zweiphasiges Muster](./images/DAT-Biphase-Fiducial.gif) ![Geo-Muster](./images/DAT-GEO-Fiducial.gif)

### Warum kann ich kein getreues Foto meines HoloLens 2-Displays aufnehmen?

Das HoloLens 2-Display ist für die Betrachtung durch das menschliche Auge konzipiert. Das Gerät verfügt über ein aktives Farbkorrektursystem, das sich an die Augen eines Benutzers anpasst. Kameras „sehen“ Umgebungen anders als das menschliche Auge. Nachfolgend sind einige Faktoren aufgeführt, die zu Abweichungen zwischen Kameraaufnahmen und dem, was ein Benutzer sieht, führen können.

* **Augenstellung.** Das HoloLens 2-Display ist speziell für die Augenstellung des Benutzers konzipiert. HoloLens 2 setzt Eye-Tracking-Technologien ein, um sich an die Augenstellung des Benutzers anzupassen. Wenn eine Kamera um nur wenige Millimeter verstellt ist, kann dies zu Bildverzerrungen führen. Eine genaue Positionierung mit einer Kamera ist schwierig und muss exakt der Position und dem Abstand zwischen Auge und Linse entsprechen, für die das Gerät Farbkorrekturen durchführt.
* **Augenbewegungen.** Das Display passt sich an die Augenbewegungen eines Benutzers an, um die Farben anzupassen. Was auf dem Display angezeigt wird, hängt davon ab, ob der Benutzer die Mitte, den Rand oder eine Ecke des Displays betrachtet. Bei einer einzelnen Aufnahme kann im günstigsten Sinn nur festgehalten werden, wie das Display von der Achse aus aussieht, die mit der Blickrichtung des Auges übereinstimmt.
* **Beidäugiges Sehen.** Das HoloLens 2-Display ist für die Ansicht mit beiden Augen konzipiert. Das Gehirn passt sich der Wahrnehmung zweier Bildern an und macht daraus eines. Bilder von nur einem Display ignorieren die Informationen des anderen Displays.
* **Kamera-Belichtungszeit.** Die Belichtungszeit der Kamera muss ein genaues Vielfaches von 1/120stel einer Sekunde betragen. Die HoloLens-Display-Bildfrequenz beträgt 120 Hz. Aufgrund der Art und Weise, wie die HoloLens 2 Bilder zeichnet, reicht das Aufnehmen eines einzelnen Frames nicht aus, um die Wahrnehmung des menschlichen Auges wiederzugeben. Wenn sich das Gerät außerdem bewegt – auch nur minimal –, wird das Bild auf dem Display zur Stabilisierung von Hologrammen neu projiziert. Das Aufnehmen mehrerer Frames bei unbewegter HoloLens erfordert in der Regel eine Laboranordnung.
* **Kamera-Blendengröße.** Die Blendengröße der Kamera muss mindestens 3 mm betragen, um ein getreues Bild erfassen zu können. Handy-Kameras mit kleinen Blendenöffnungen beziehen Licht aus einem kleineren Bereich als das menschliche Auge ein. Das Gerät wendet die Farbkorrektur für Muster an, die für größere Blenden typisch sind. Bei kleinen Blenden sind Homogenitätsmuster schärfer und bleiben trotz Farbkorrekturen durch das System sichtbar.
* **Kamera-Eintrittspupille.** Für die Aufnahme eines getreuen Bildes sollte die Eintrittspupille der Kamera einen Durchmesser von mindestens 3 mm aufweisen. Andernfalls werden einige Hochfrequenzmuster erfasst, die für das Auge nicht sichtbar sind. Die Eintrittspupille muss sich vorne an der Kamera und im Abstand Pupille-Linse befinden, um Abbildungsfehler und andere Abweichungen bei dem aufgenommenen Bild zu vermeiden.
* **Kameraposition** Kameras, die die Anforderungen erfüllen, um das HoloLens 2-Display darzustellen, sind größer, außerdem ist es schwierig, die Kamera nahe genug am HoloLens 2-Display zu positionieren, um das farbkorrigierte Bild zu beobachten. Wenn sich die Kamera an der falschen Stelle befindet, kann sich die Farbkorrektur negativ auf die Erfassung des HoloLens 2-Displays auswirken.
* **Bildkorrektur.** Typische digitale Kameras und Smartphone-Kameras wenden eine Tonwiedergabekurve (Tone Reproduction Curve, TRC) zur Verstärkung von Kontrast und Farben an, um knackigere Ergebnisse zu erzielen. Wenn sie auf ein HoloLens 2-Display angewendet wird, werden durch diese Tonwertkorrektur Ungleichförmigkeiten verstärkt.

Dennoch können spezielle Industriekameras gute Bilder des HoloLens 2-Displays aufnehmen. Leider erfassen Smartphone-, Consumer- und professionelle Kameras keine Bilder, die dem entsprechen, was ein Benutzer in HoloLens 2 sieht.

### Wie wirkt sich die Augenkalibrierung auf die Qualität des angezeigten Bildes aus?

Das HoloLens 2-Display korrigiert aktiv die Farben von Bildern basierend auf der Position der Augen des Benutzers. Die [Augenkalibrierung](hololens-calibration.md) bietet zwei wichtige Eingaben: (1) die Pupillendistanz (PD) des Benutzers und (2) die Blickrichtung der einzelnen Augen. Ohne Augenkalibrierung gilt im System standardmäßig eine nominale Augenstellung ohne Augenbewegungen. Der Unterschied zwischen aktiver Farbkorrektur und keiner Korrektur hängt von den physischen Merkmalen des Benutzers ab. Bei einem Benutzer mit der gleichen PD wie der Systemstandard erfolgen beispielsweise weniger Farbkorrekturen. Während bei Benutzern mit einer viel engeren oder weiteren PD als die Systemstandardeinstellung mehr Änderungen am Anzeigebild vorgenommen werden.

Hinweis: Ein neues Feature, das in einem zukünftigen Betriebssystemupdate bereitgestellt wird, wird die [Augenstellung automatisch erkennen](hololens-insider.md#auto-eye-position-support). Interessierte können sich für die [Insider Preview](hololens-insider.md) anmelden, um dieses Feature bereits jetzt auszuprobieren.

### Wie unterscheiden sich die Displays von HoloLens (1st Gen) und HoloLens 2?

Zu den häufigsten Wünschen, die Kunden nach der Erfahrung mit HoloLens 1 Microsoft gegenüber geäußert haben, zählten (1) ein größeres Sichtfeld und (2) größere Helligkeit. Technologische Entwicklungen ermöglichten Microsoft die Fertigung von Wellenleitern, die den Sichtbereich verdoppelten, und von Lichtprojektoren mit einer bis zu dreimal helleren Anzeige. Die Hardware bildet die Grundlage für drei miteinander in Konflikt stehende Elemente für die Qualität des Anzeigebilds: (1) Sichtfeld, (2) Helligkeit und (3) Farbhomogenität. Fortwährende technologische Fortschritte ermöglichen Verbesserungen in allen Bereichen, ohne dass bei einem Abstriche gemacht werden müssen. In der Zwischenzeit setzen die vorhandenen Technologien die Grenzen für die Lösung dieser Konflikte fest.

### Welche Verbesserungen wird es in puncto Bildqualität bei HoloLens 2 geben?

Während wir in mehreren Bereichen Forschungen zur Verbesserung der Bildqualität betreiben, werden die folgenden Bereiche voraussichtlich in bevorstehenden Updates eingeführt:

* **Automatische Augenstellung.** Mit dieser Funktion kann die Augenkalibrierung im Hintergrund ausgeführt werden. Benutzer müssen keine Augenkalibrierung mehr ausführen, damit die aktive Farbkorrektur funktioniert. Sie wird stattdessen einfach funktionieren.
* **Verbesserungen bei der Farbkalibrierung.** Bei diesem Update stehen die Farbwerte dunklerer Farben (beispielsweise dunkelgrau) im Mittelpunkt. Derzeit nehmen dunklere Farben einen Rotstich an. Dieses Problem tritt auch auf, wenn das gesamte Display abgedunkelt wird – die gesamte Anzeige wird rötlich. Die Ursache dieses Problems ist zu viel Aktivität im roten Farbkanal für diese dunkleren Farben. Wir haben die Laser-Beleuchtungskurven für diese dunkleren Farben charakterisiert und arbeiten an einer Lösung für die Benutzerkalibrierung. Das Ergebnis wird eine höhere Farbgenauigkeit über das gesamte Helligkeitsspektrum hinweg sein. Die Darstellung weißer Hintergründe bei voller Helligkeit wird dadurch nicht geändert. Weiterhin empfehlen wir die Verwendung von Designmustern für den Dunkel Modus in Apps.
* **Lesemodus.** App-Entwickler können das Display-Sichtfeld zugunsten einer höheren Winkelauflösung reduzieren. App-Entwickler können die Projektionsmatrix so überschreiben, dass Inhalte in der Zeichnen-Auflösung des Displays gerendert werden. Dieses Feature bewirkt eine Reduzierung des Sichtfelds um 30 % und eine entsprechende Erhöhung der Winkelauflösung. Wir arbeiten an der Einführung dieser Funktion in das Mixed Reality-Toolkit. Der Lesemodus wird auf jedem HoloLens 2-Betriebssystem funktionieren – er ist nicht von einem Betriebssystemupdate abhängig.

Betriebssystemupdates werden automatisch bereitgestellt. Sie können auch frühe Veröffentlichungen von Software-Verbesserungen über das Insider Preview-Programm testen.

### Welche Anleitungen stehen Entwicklern zum Anwenden von Designprinzipien für den dunklen Modus zur Verfügung?

Für Benutzer ist es am besten, wenn sie weiße Hintergründe vermeiden. Der dunkle Modus ist ein Designprinzip, das von Apps für schwarze oder dunkle Hintergründe verwendet wird. Bei den Systemeinstellungen wird standardmäßig der dunkle Modus festgelegt. Er kann über **Einstellungen** > **System** > **Farbe** angepasst werden.

Entwicklern wird empfohlen, die Designanleitung für den dunklen Modus zu beachten:

* [Designrichtlinien zu HoloLens-Displays für Entwickler](https://docs.microsoft.com/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Empfohlene Schriftgrade](https://docs.microsoft.com/windows/mixed-reality/typography#recommended-font-size)

Wenn für ein Hologramm ein weißer Hintergrund erforderlich ist, sollte es kleiner als das vollständige Sichtfeld des Displays sein. Bei dieser Größe können Benutzer das Hologramm in die Mitte des Displays setzen.

### Wie kann ich eine HoloLens 2-Anzeige reinigen?

Reinigen Sie das Visier vorsichtig mit einem Mikrofasertuch. Verwenden Sie zur Desinfektion des Visiers 70 %igen Isopropylalkohol: Befeuchten Sie damit ein Tuch und wischen sie das Visier ab. Eine vollständige Anleitung finden Sie unter [Reinigen von HoloLens 2: Häufig gestellte Fragen](hololens2-maintenance.md).
