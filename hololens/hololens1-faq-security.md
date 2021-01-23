---
title: Häufig gestellte Fragen zur Sicherheit
description: Halten Sie sich mit Antworten auf häufig gestellte Sicherheitsfragen zu Mixed-Reality-Geräten mit HoloLens auf dem Laufenden.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: pawinfie
ms.author: pawinfie
ms.date: 02/19/2020
keywords: Microsoft HoloLens, Windows Mixed Reality, Sicherheit
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: high
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: bradke
ms.openlocfilehash: 0e3b7f40aa6d5163b6d58b7f21b9ea6daa9cc9b4
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284006"
---
# Häufig gestellte Sicherheitsfragen zu HoloLens (1. Gen.)

1. **Welches Maß an Datenschutz bietet HoloLens 1?**
    1. Lesen Sie dazu [BitLocker-Verschlüsselung von HoloLens (1. Gen.)](hololens1-encryption.md)
1. **Welche Drahtlostechnologie wird verwendet?**
    1. 802.11ac und Bluetooth 4.1 LE
1. **Welche Art von Architektur ist integriert?  Zum Beispiel: Punkt-zu-Punkt, Mesh oder andere?**
    1. WLAN kann im Infrastrukturmodus verwendet werden, um mit anderen Drahtloszugriffspunkten zu kommunizieren.
    1. Bluetooth kann für Peer-zu-Peer-Unterhaltungen zwischen mehreren Microsoft HoloLens verwendet werden, wenn die Kundenanwendung dies oder andere Bluetooth-Geräte unterstützt.
1. **Was ist die FCC ID?**
    1. C3K1688
1. **In welchem Frequenzbereich und über welche Kanäle operiert das Gerät, und ist dies konfigurierbar?**
    1. WLAN: Der Frequenzbereich ist nicht konfigurierbar und vom jeweiligen Verwendungsland abhängig. In den USA verwendet WLAN sowohl 2,4-GHz-Kanäle (1-11) als auch 5-GHz-Kanäle (36-64, 100-165).
    1. Bluetooth: Bluetooth verwendet den standardmäßigen 2,4-2.48 GHz-Bereich.
1. **Kann das Gerät spezifische Frequenzen zulassen oder blocken?**
    1. Dies ist vom Benutzer bzw. dem Gerät nicht steuerbar.
1. **Welches ist die Leistungsstufe für Übertragung und Empfang? Kann dies angepasst werden? Welches ist der Betriebsbereich?**
    1. Unsere Prüfstandards für Emissionen können Sie [hier](https://fccid.io/C3K1688) finden. Der Betriebsbereich ist in hohem Maße vom Zugriffspunkt und der Umgebung abhängig, entspricht aber ungefähr dem anderer hochwertiger Smartphones, Tablets oder PCs.
1. **Welches ist die Einschaltdauer/Akkulebensdauer bei normalem Betrieb?**
    1. 2-3 Stunden aktive Nutzung und bis zu zwei Wochen Standby-Zeit.
    1. Daten zur Akkulebensdauer sind nicht verfügbar.
1. **Wie ist das Übertragungs- und Empfangsverhalten, wenn sich ein Tool außerhalb des Bereichs befindet?**
    1. Für Übertragung und Empfang folgt Microsoft HoloLens dem standardmäßigen WLAN-/Bluetooth-Muster. An der Bereichsgrenze werden Sie wahrscheinlich bemerken, dass die Eingabe zu stocken beginnt, bis die Verbindung vollständig getrennt wird; sobald Sie aber wieder innerhalb des Bereichs sind, sollte die Verbindung schnell wiederhergestellt werden.
1. **Wie hoch ist die Bereitstellungsdichte pro Quadratfuß?**
    1. Dies hängt von Ihrer Netzwerkinfrastruktur ab.
1. **Kann das Gerät die Infrastruktur als Client nutzen?**
    1. Ja
1. **Welches Protokoll wird verwendet?**
    1. Microsoft HoloLens verwendet keine proprietären Protokolle.
1. **Betriebssystem-Updatehäufigkeit: Wie hoch ist die Häufigkeit der BS-Updates für HoloLens?  Gibt es hierfür einen festgelegten Zeitplan?  Veröffentlicht Microsoft Sicherheitsupdates nach Bedarf, usw.?**
    1. Microsoft bietet Betriebssystemupdates für HoloLens auf genau die gleiche Weise wie für Windows 10. Normalerweise gibt es zwei Hauptupdates pro Jahr, eines im Frühjahr und eines im Herbst. Da Microsoft HoloLens ein Windows-Gerät ist, ist das Updatekonzept das gleiche wie für jedes andere Windows-Gerät. Microsoft veröffentlicht Sicherheitsupdates nach Bedarf und folgt dabei demselben Konzept wie bei jedem anderen Windows-Gerät.
1. **Betriebssystemhärtung – welche Optionen stehen zum Härten des Betriebssystems zur Verfügung?  Können nicht benötigte Apps oder Dienste entfernt oder heruntergefahren werden?**
    1. Microsoft HoloLens verhält sich wie ein Smartphone. Es ist mit anderen modernen Windows-Geräten vergleichbar. Microsoft HoloLens kann über Microsoft Intune oder andere moderne Geräte-Verwaltungslösungen wie MobileIron, Airwatch oder Soti verwaltet werden. In diesen Verwaltungssystemen können Sie Richtlinien einrichten, um Sicherheitsrichtlinien auf das Gerät zu übertragen und um es zu härten. Bei Bedarf gibt es auch die Möglichkeit, alle nicht benötigten Anwendungen zu löschen.
1. **Wie lassen sich Softwareanwendungen verwalten und aktualisieren? Welche Steuerungsmöglichkeiten gibt es, um festzulegen, welche Apps geladen werden und den Aktualisierungsvorgang für Apps, die sich im Microsoft Store befinden, zu steuern?**
    1. Microsoft HoloLens ruft Softwareanwendungen nur über den Windows Store ab. Es können nur Appx-Anwendungspakete installiert werden, die zur Verwendung von Microsoft HoloLens entwickelt wurden. Sie können diese im Microsoft Store an einem kleinen Logo neben der jeweiligen Anwendung erkennen, auf dem das HoloLens-Gerät dargestellt ist. Alle Steuerungsmöglichkeiten, die Sie zur Verwaltung von Store-Anwendungen verwenden können, gelten auch für Microsoft HoloLens. Sie können das Konzept des offiziellen Stores oder des Stores für Unternehmen anwenden. Apps können entweder quergeladen werden (manuelles Verfahren zum Laden einer App auf ein Windows-Gerät) oder über die MDM (Mobile Device Management, Verwaltung mobiler Geräte) verwaltet werden, sodass sie bei Bedarf automatisch aus dem Store abgerufen werden können.
1. **Wie hoch ist die Häufigkeit von Updates für Apps im Store für Microsoft HoloLens?**
    1. Da das gleiche Konzept wie für den Microsoft Store befolgt wird und Apps von dort abgerufen werden, wird der Aktualisierungszyklus vom Entwickler der Anwendung bestimmt. Alle Verwaltungsoptionen, mit denen Sie den Aktualisierungsmechanismus im Store steuern können, gelten auch für Microsoft HoloLens.
1. **Gibt es eine sichere Boot-Funktion für Microsoft HoloLens?**
    1. Ja
1. **Gibt es eine Möglichkeit zum Deaktivieren oder Trennen der Peripherieunterstützung über das Gerät?**
    1. Ja
1. **Gibt es eine Möglichkeit zum Steuern oder Deaktivieren der Verwendung von Ports auf dem Gerät?**
    1. Microsoft HoloLens verfügt über nur zwei Ports (einen für Kopfhörer und einen für das Laden oder die Verbindung zu PCs). Aufgrund von Funktionalitäts- und Wiederherstellungsgründen gibt es keine Möglichkeit zum Deaktivieren der Ports.
1. **Antivirus, Endpunkterkennung, IPS, App-Kontrolle-Zulassungsliste – Jede Fähigkeit zum Ausführen von Antivirus, Endpunkterkennung, IPS, App-Kontrolle-Zulassungsliste etc.**
    1. Windows Holographic for Business (Commercial Suite) unterstützt Windows Defender Smart Screen. Sollte ein Antivirusanbieter seine Apps auf der Universellen Windows-Plattform erstellen und veröffentlichen, könnten diese auf Microsoft HoloLens heruntergeladen werden. Gegenwärtig hat dies kein Anbieter für Microsoft HoloLens getan.
    1. Das Zulassen von Apps ist über den Microsoft Enterprise Store möglich, wo Sie nur auswählen können, welche bestimmten Apps heruntergeladen werden können. Darüber hinaus können Sie über MDM festlegen, welche Apps auf dem Gerät ausgeführt oder auch nur angezeigt werden können.
1. **Kann ein Gerät aus dem Produktionsnetzwerk isoliert werden, bis es aktualisiert wurde, wenn es über einen längeren Zeitraum offline war?  Zum Beispiel: Das Gerät lag über einen längeren Zeitraum (6 Monate) in einer Schublade und wurde nicht eingeschaltet, es wurden keine Updates, Patches usw. installiert. Ist es möglich, wenn es dann versucht, sich in das Netzwerk einzuklinken, es zu kennzeichnen und dem Benutzer mitzuteilen, dass er eine Aktualisierung in einem anderen Netzwerk durchführen muss, um zu diesem zugelassen zu werden?**
    1. Dies kann auf Infrastrukturebene entweder über MDM oder einen lokalen Server verwaltet werden. Das Gerät kann als nicht kompatibel gekennzeichnet werden, wenn es eine bestimmte Update-Version nicht aufweist.
1. **Bietet Microsoft Hintertüren oder den Zugriff auf Dienste, über die Microsoft eine Verbindung mit dem Gerät für die Bildschirmfreigabe oder Remoteunterstützung nach Belieben herstellen kann?**
    1. Nein
1. **Wenn ein PKI-Zertifikat für vertrauenswürdige Kommunikation generiert wird, sollte das Zertifikat auf dem Gerät generiert werden, damit wir wissen, dass es sich nur auf diesem Gerät befindet und für dieses Gerät eindeutig ist und dass es nicht exportiert oder dazu verwendet werden kann, die Identität des Geräts anzunehmen. Gilt dies für Microsoft HoloLens? Falls nicht, gibt es potenzielle Abhilfemaßnahmen?**
    1. CSR für SCEP wird auf dem Gerät selbst generiert. Intune und der lokale SCEP-Connector tragen dazu bei, die Anforderungen selbst zu schützen, indem sie eine Abfragezeichenfolge hinzufügen und überprüfen, die an den Client gesendet wird.
    1. Da Microsoft HoloLens (1. Gen. und 2. Gen.) über ein TPM-Modul verfügen, würden diese Zertifikate im TPM-Modul gespeichert und könnten nicht extrahiert werden. Und selbst wenn sie extrahiert würden, könnten die Abfragezeichenfolgen nicht auf einem anderen Gerät verifiziert werden, wodurch die Zertifikate bzw. Schlüssel auf anderen Geräten unbrauchbar würden.
