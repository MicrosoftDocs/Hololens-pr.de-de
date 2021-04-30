---
title: Häufig gestellte Fragen zur Sicherheit
description: Bleiben Sie mit häufig gestellten Sicherheitsfragen und Antworten zu HoloLens Mixed Reality-Geräten auf dem laufenden.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: pawinfie
ms.author: pawinfie
ms.date: 02/19/2020
keywords: HoloLens, Windows Mixed Reality, Sicherheit
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: bradke
ms.openlocfilehash: 371c901acbf23feecfe98e72569caeaf63e2198f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309977"
---
# <a name="frequently-asked-hololens-1st-gen-security-questions"></a>Häufig gestellte Fragen zur Sicherheit von HoloLens (1. Generation)

1. **Welche Datenschutzebene bietet HoloLens 1?**
    1. Siehe [HoloLens-BitLocker-Verschlüsselung (1. Generation)](hololens1-encryption.md)
1. **Welche Art von Drahtlosverbindung wird verwendet?**
    1. 802.11ac und Bluetooth 4.1 LE
1. **Welche Art von Architektur ist integriert?  Beispiel: Point-to-Point, Mesh oder etwas anderes?**
    1. Wi-Fi kann im Infrastrukturmodus für die Kommunikation mit anderen Drahtlosen Zugriffspunkten verwendet werden.
    1. Bluetooth kann verwendet werden, um peer-to-peer zwischen mehreren HoloLens zu sprechen, wenn die Anwendung des Kunden dies unterstützt, oder mit anderen Bluetooth-Geräten.
1. **Was ist die FCC-ID?**
    1. C3K1688
1. **Mit welchem Frequenzbereich und welchen Kanälen wird das Gerät betrieben, und ist es konfigurierbar?**
    1. WLAN: Der Häufigkeitsbereich ist nicht vom Benutzer konfigurierbar und hängt vom Nutzungsland ab. In den USA Wi-Fi sowohl 2,4-GHz-Kanäle (1-11) als auch 5-GHz-Kanäle (36-64, 100-165) verwendet.
    1. Bluetooth: Bluetooth verwendet den standardmäßigen Bereich von 2,4 bis 2,48 GHz.
1. **Kann das Gerät bestimmte Frequenzen zulassen oder blockieren?**
    1. Dies kann vom Benutzer/Gerät nicht kontrolliert werden.
1. **Wie ist die Leistungsstufe für Übertragung und Empfang? Ist es anpassbar? Was ist der Bereich des Vorgangs?**
    1. Unsere Standards für DieMissionstests finden Sie [hier.](https://fccid.io/C3K1688) Der Umfang des Vorgangs hängt stark vom Zugriffspunkt und der Umgebung ab, entspricht aber in etwa anderen qualitativ hochwertigen Smartphones, Tablets oder PCs.
1. **Wie lautet der Arbeitszyklus/die Lebensdauer für den normalen Betrieb?**
    1. 2-3 Stunden aktive Nutzung und bis zu zwei Wochen Standbyzeit
    1. Die Akkulebensdauer ist nicht verfügbar.
1. **Was ist Übertragungs- und Empfangsverhalten, wenn sich ein Tool nicht im Bereich befindet?**
    1. HoloLens-Übertragung/-Empfang folgt dem Standardmäßigen WLAN-/Bluetooth-Muster. Am Rand des Bereichs werden Sie wahrscheinlich feststellen, dass die Eingabe langsam wird, bis die Verbindung vollständig getrennt wird, aber nachdem Sie wieder in den Bereich gelangt sind, sollte die Verbindung schnell wiederhergestellt werden.
1. **Was ist die Bereitstellungsdichte pro Quadratfuß?**
    1. Dies hängt von Ihrer Netzwerkinfrastruktur ab.
1. **Kann das Gerät die Infrastruktur als Client verwenden?**
    1. Ja
1. **Welches Protokoll wird verwendet?**
    1. HoloLens verwendet keine proprietären Protokolle.
1. **Häufigkeit von Betriebssystemupdates: Wie oft werden Betriebssystemupdates für hl aktualisiert?  Gibt es einen festgelegten Zeitplan?  Gibt Microsoft Sicherheitspatches nach Bedarf usw. frei?**
    1. Microsoft stellt Betriebssystemupdates für HoloLens genauso bereit wie für Windows 10. Normalerweise gibt es zwei wichtige Updates pro Jahr: eine im Spring, eine im Fall. Da HoloLens ein Windows-Gerät ist, ist das Updatekonzept identisch mit jedem anderen Windows-Gerät. Microsoft veröffentlicht Sicherheitspatches nach Bedarf und folgt dem gleichen Konzept wie auf jedem anderen Windows-Gerät.
1. **Betriebssystemhärtung: Welche Optionen gibt es, um das Betriebssystem zu härten?  Können wir unnötige Apps oder Dienste entfernen oder herunterfahren?**
    1. HoloLens verhält sich wie ein Smartphone. Sie ist vergleichbar mit anderen modernen Windows-Geräten. HoloLens kann entweder von Microsoft Intune oder anderen modernen Geräteverwaltung-Lösungen wie MobileIron, Airwatch oder Soti verwaltet werden. Es gibt Richtlinien, die Sie in diesen Verwaltungssystemen festlegen können, um Sicherheitsrichtlinien auf dem Gerät zu speichern und das Gerät zu härten. Es gibt auch die Option zum Löschen unnötiger Anwendungen, falls gewünscht.
1. **Wie werden Softwareanwendungen verwaltet und aktualisiert? Welche Kontrolle müssen wir definieren, welche Apps geladen werden und welche App-Updateprozesse für Apps im Microsoft Store verwendet werden?**
    1. HoloLens ruft Softwareanwendungen nur über den Windows Store ab. Es können nur Appx-Anwendungspakete installiert werden, die für die Verwendung von HoloLens entwickelt wurden. Sie können dies in der Microsoft Store mit einem kleinen Logo neben der Anwendung sehen, die das HoloLens-Gerät zeigt. Jede Kontrolle über die Verwaltung von Store-Anwendungen gilt auch für HoloLens. Sie können das Konzept des offiziellen Geschäfts oder des Geschäfts verwenden. Apps können entweder per Sideloaded (manueller Prozess zum Laden einer App auf ein Windows-Gerät) oder über mdm verwaltet werden, sodass Apps bei Bedarf automatisch aus dem Store gezogen werden.
1. **Wie häufig werden Apps im Store für HoloLens aktualisiert?**
    1. Da wir das gleiche Konzept der Anwendung Microsoft Store und Apps von dort pullen, wird der Updatezyklus vom Entwickler der Anwendung bestimmt. Alle Verwaltungsoptionen, die Sie zum Steuern des Updatemechanismus im Store haben, gelten auch für HoloLens.
1. **Gibt es eine sichere Startfunktion für die HoloLens?**
    1. Ja
1. **Gibt es die Möglichkeit, die Peripheriegeräteunterstützung vom Gerät zu deaktivieren oder zu trennen?**
    1. Ja
1. **Gibt es die Möglichkeit, die Verwendung von Ports auf dem Gerät zu steuern oder zu deaktivieren?**
    1. Die HoloLens enthält nur zwei Ports (einer für Dielens und einer für das Laden oder Verbinden mit PCs). Der Port kann aus Funktions- und Wiederherstellungsgründen nicht deaktiviert werden.
1. **Antivirus, Endpunkterkennung, IPS, App-Steuerungs-Allow List: Beliebige Möglichkeit zum Ausführen von Antivirensoftware, Endpunkterkennung, IPS, App-Steuerungs-Allow List usw.**
    1. Windows Holographic for Business (kommerzielle Suite) unterstützt Windows Defender Smart Screen. Wenn ein Antivirenunternehmen seine App erstellen und auf dem Universelle Windows-Plattform veröffentlichen würde, könnte es auf HoloLens heruntergeladen werden. Derzeit haben keine Unternehmen dies für HoloLens getan.
    1. Das Zulassen von Apps ist mit dem Microsoft Enterprise Store möglich, in dem Sie nur auswählen können, welche spezifischen Apps heruntergeladen werden können. Darüber hinaus können Sie über MDM sperren, welche bestimmten Apps auf dem Gerät ausgeführt oder sogar angezeigt werden können.
1. **Können wir das Gerät aus dem Prod-Netzwerk unter Quarantäne stellen, bis wir das Gerät aktualisieren, wenn es über einen längeren Zeitraum offline war?  Beispiel: Das Gerät befindet sich für einen Zeitraum (sechs Monate) nicht in einer Schublade und hat keine Updates, Patches usw. erhalten.  Wenn versucht wird, in das Netzwerk zu gelangen, können wir es kennzeichnen und sagen, dass Sie ein Update in einem anderen Netzwerk durchführen müssen, bevor Sie mit dem Beitritt zum Netzwerk rechnen.**
    1. Dies ist etwas, das auf Infrastrukturebene entweder von einem MDM- oder einem on-prem-Server verwaltet werden kann. Das Gerät kann als nicht konform gekennzeichnet werden, wenn es keiner angegebenen Updateversion entspricht.
1. **Schließt Microsoft Hintertüren oder Zugriff auf Dienste ein, die es Microsoft ermöglichen, sich zur Bildschirmfreigabe oder remoten Unterstützung nach Beweggründen mit dem Gerät zu verbinden?**
    1. Nein
1. **Wenn ein PKI-Zertifikat für die vertrauenswürdige Kommunikation generiert wird, soll das Zertifikat auf dem Gerät generiert werden, damit wir wissen, dass es sich nur auf diesem Gerät befindet, für dieses Gerät eindeutig ist und nicht exportiert oder verwendet werden kann, um die Identität des Geräts zu annehmen. Gilt dies für HoloLens? Wenn nicht, gibt es eine mögliche Entschärfung?**
    1. CSR für SCEP wird auf dem Gerät selbst generiert. Intune und der lokale SCEP-Connector tragen dazu bei, die Anforderungen selbst zu schützen, indem eine Abfragezeichenfolge hinzugefügt und überprüft wird, die an den Client gesendet wird.
    1. Da HoloLens (1. Generation und 2. Generation) über ein TPM-Modul verfügt, werden diese Zertifikate im TPM-Modul gespeichert und können nicht extrahiert werden. Auch wenn sie extrahiert werden könnten, konnten die Zeichenfolgen nicht auf einem anderen Gerät überprüft werden, wodurch die Zertifikate/Schlüssel auf verschiedenen Geräten unbrauchbar werden.
