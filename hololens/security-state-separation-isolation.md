---
title: Statustrennung und -isolation
description: Informationen zu Zustandstrennung, Isolation, Codesignierung und Defender-Anwendungen auf Ihrem Mixed Reality-Gerät von HoloLens 2.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: Sicherheit, HoloLens, Statustrennung, Statustrennung und -isolation, HoloLens 2, HoloLens2 Sicherheit, Sicherheitsübersicht, Sicherheitsarchitektur, Architektur, HoloLens 2-Architektur
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 60d6d7c0e281395957ce9158144a5f3d60927682
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11282806"
---
# Statustrennung und -isolation

Statustrennung und -isolation schützt kritische Teile des HoloLens 2-Betriebssystems vor Veränderungen – wie z.B. diejenigen, die erforderlich sind, damit das Betriebssystem in einen vertrauenswürdigen Status booten kann. Bei der Isolationstechnologie werden nicht vertrauenswürdige Anwendungen in eine isolierte Sandbox-Umgebung verschoben, um sicherzustellen, dass sie die Systemsicherheit nicht beeinträchtigen.

## Statustrennung

Die Statustrennung bei HoloLens 2 verbessert die Sicherheit und Wartbarkeit (Aktualisierung) erheblich und trägt zum Schutz Ihrer Anwendungsdaten bei.  Die Statustrennung funktioniert wie folgt:
  * Das Core-Betriebssystem ist im Core-Betriebssystemvolume gespeichert (vertrauenswürdige oder verifizierte Microsoft-Betriebssysteme, die das Betriebssystem aktualisieren).
  * Die Teile des Betriebssystems, die zur Laufzeit geändert werden können (z. B. herunterladbare Treiber und Konfigurationen), verwenden eine weitere Statustrennung, um die Daten zu partitionieren und an sicheren, separaten Speicherorten zu speichern.
  * Jedem sicheren Speicherort sind unterschiedliche Sicherheitsrichtlinien zugeordnet, die verschiedene Sicherheitsvorteile bieten, die im folgenden Abschnitt näher erläutert werden.

## Vorteile der Statustrennung

  * Sicherheit: Die in HoloLens 2 enthaltene Statustrennung verbessert die Plattformintegrität, die Resistenz gegen Schadsoftware und den Schutz der Benutzerdaten erheblich. Durch die Trennung des unveränderlichen Teils des Betriebssystems und indem es schreibgeschützt oder integritätsgeschützt gemacht wird, macht die Statustrennung es für Schadsoftware extrem schwierig, nach einem Kaltstart weiter zu bestehen. 
  * Updates: Mit HoloLens 2 werden Updates einfach und zuverlässig, sobald das Core-Betriebssystem unveränderbar ist und sauber vom Rest der Daten auf dem Gerät getrennt wurde.  Darüber hinaus schafft die Statustrennung die entscheidende Grundlage für dramatisch schnellere Updates, wodurch das Betriebssystem in einem einzigen Schritt ersetzt werden kann (Atomeinheit).
  * Zurücksetzen des Geräts: Das Zurücksetzen von HoloLens 2 löscht benutzergenerierte Daten und Benutzeranwendungsdaten auf dem Gerät – einschließlich interner und externer Speicherorte. Es bewahrt die aktuellen Anwendungen für das Betriebssystem und sicherheitskritische Anwendungen sowie die aktuellen kundenspezifischen Anwendungen von Microsoft und OEM (vorinstalliert). Diese vorinstallierten Anwendungen können nach Abschluss des Zurücksetzens auf dem Gerät reaktiviert werden.

### Status der Statustrennung

Die Statustrennung gewährleistet, dass das Betriebssystem nur durch vertrauenswürdige Gerätekomponenten von Microsoft geändert werden kann und nur ein hochwertiger Status über Neustarts weiter bestehen kann; ein anderer Systemstatus existiert nur für die Dauer der Startsitzung und wird nach einem Neustart verworfen. Durch die Statustrennung wird das Gerät schnell wieder in den Herstellerstatus zurückversetzt. Die Status von Windows Holographic for Business lassen sich in diese unterschiedlichen Kategorien einteilen:
  * Core-Betriebssystem – nicht änderbarer Status
  * Betriebssystem-Daten – änderbarer Status 
  * Benutzerdaten – änderbarer Status

Jeder dieser Betriebszustände von HoloLens 2 wird im folgenden Abschnitt beschrieben.

#### Core-Betriebssystem

Ein unveränderlicher Status besteht aus ausführbaren Dateien und Daten, die unveränderlich sind und nur von Microsoft während der Installation von Updates geändert werden können. Während einer solchen Aktualisierung des Core-Betriebssystems wird ein neues Image aktiviert, das den letzten gewünschten Betriebszustand enthält.
Der nicht änderbare Status wird als schreibgeschützt gekennzeichnet (oder ist anderweitig integritätsgeschützt), wodurch das Fortbestehen von Schadsoftware mit erhöhten Rechten verhindert wird. Die folgenden ausführbaren Dateien und Daten sind im unveränderlichen Status geschützt:
  * Windows Holographic-Posteingangstreiber
  * Betriebssystem-Binärdateien
  * Windows-Posteingangstreiber
  * Statische Windows Holographic-Einstellungen, die in der Windows-Registrierungsstruktur (HKLM) gespeichert sind
    * Beispiel: HKLM speichert die Konfigurationsinformationen für die auf einem Computer installierten Anwendungen. Es speichert auch Informationen zur Erkennung von Hardware und den entsprechenden Treibern.
Durch den Schutz dieser im unveränderlichen Status (Integrität und schreibgeschützt) stellen wir sicher, dass das Core-Betriebssystem immer in einen vertrauenswürdigen Status bootet. Darüber hinaus können wir beim Zurücksetzen eines Geräts sicherstellen, dass das Gerät nur in die Komponenten bootet, die sich auf diesem unveränderlichen Abschnitt befinden. 

#### Betriebssystemdaten 

Es ist wichtig zu beachten, dass ausführbare Dateien und Daten, die zur Laufzeit veränderbar sind (und nicht kritisch für die Funktion des Betriebssystems sind), verworfen und neu erstellt werden können, wenn die Daten beschädigt oder kompromittiert sind. Ein hochwertiger änderbarer Status ist entweder funktional erforderlich, damit er vom Betriebssystem aufrechterhalten wird, oder es wird erwartet, dass er beim Herunterfahren des Betriebssystems und/oder bei Neustarts durch unterstützte Windows-Betriebssystem- und Geräte-Szenarien weiterhin bestehen bleibt. Beispiele für einen hochwertigen veränderbaren Status sind:
  * Globale Geräteeinstellungen, wie z.B. die Deaktivierung des Speicherorts für alle Benutzer, die vom IT-Administrator konfiguriert wurden.
  * Zugriff auf an Datengeräte erinnernde Netzwerke und zugehörige Verbindungspasswörter über Wi-Fi-Netzwerkverbindungen.
  * Absturzabbilder einschließlich Einstellungen, Protokolle.
  * Treiber, die bei Bedarf für neu entdeckte Geräte heruntergeladen werden.
Ein hochwertiger, änderbarer Status auf der HoloLens 2 befindet sich am Speicherort der Datensicherheit des Betriebssystems, entweder als gespeicherte Datei auf dem Datenträger oder in einer persistenten Registrierungsstruktur.

#### Benutzerdaten

Die letzte Kategorie von Status repräsentiert Benutzerdaten, die von UWP-Anwendungen oder dem Betriebssystem erstellt oder beibehalten werden. Alle bekannten Benutzerordner wie Downloads, Dokumente, Videos, Benutzerprofile und die Struktur HKEY_CURRENT_USER sind ebenfalls an diesem Ort gespeichert. Diese Daten können ohne ordnungsgemäße Anmeldeinformationen nicht extrahiert werden. Weitere Informationen darüber, wie Ihre Daten geschützt werden, finden Sie unter [Verschlüsselung und Datenschutz](security-encryption-data-protection.md).

##  Isolierung

Um dieses Gleichgewicht zu erreichen, verfügt HoloLens 2 über ein Core-Betriebssystem, das für primäre Funktionen wie Hochfahren, Hardwaresteuerung, Einloggen usw. verwendet wird. Es gibt nur zwei Sätze von Anwendungen, die auf dem Core-Betriebssystem laufen – vorinstallierte Anwendungen und UWP-Anwendungen.

## Codesignieren

Das digitale Signieren von Code ermöglicht den Nachweis, dass ausführbare Dateien und Skripte nicht verändert wurden, da sie von einer vertrauenswürdigen Quelle signiert wurden, und bietet somit Authentizität und Integrität. Die Stellen, die HoloLens 2 standardmäßig vertraut, sind Microsoft und Microsoft Store. IT-Administratoren können dem Gerät über die CSPs [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) und [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) neue Zertifikate hinzufügen. Sie können auch die [AllowAllTrustedApps-Richtlinie](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) verwenden, um zusätzlichen Sideloaded- oder [branchenspezifischen Anwendungen zu vertrauen](https://docs.microsoft.com/intune/apps/lob-apps-windows). Die Zertifikate befinden sich im lokalen Computer-Zertifikatspeicher, der bei Verwendung von "Gerät" in HKLM/Stamm und bei Verwendung von "Benutzer" in HKCU gespeichert ist.

## Defender-Schutzmaßnahmen
HoloLens 2 verwendet Microsoft-Dienste, um den Benutzern ein hohes Maß an Sicherheit zu bieten:

* [Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) wird vom Betriebssystem automatisch auf Windows Holographic aktiviert und schützt vor Phishing und Schadsoftware sowie vor dem Herunterladen potenziell schädlicher Dateien auf Edge. Er kann vom Benutzer nicht deaktiviert werden, aber er kann durch Richtlinien deaktiviert werden.

* [Defender Firewall](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) blockiert den nicht autorisierten Netzwerkverkehr von und zu Ihrem Gerät. Sie ist standardmäßig aktiviert und kann vom Kunden nicht durch lokale Aktionen oder Richtlinien konfiguriert werden. 

* [Windows Defender Application Control](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview):  HoloLens 2 unterstützt WDAC, das es IT-Administratoren ermöglicht, Richtlinien zur Anwendungssteuerung auf das Gerät zu übertragen. Weitere Informationen finden Sie unter [Verwendung von WDAC auf HoloLens 2-Geräten mit MSFT Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens). 

IT-Administratoren können das SmartScreen-Verhalten über [AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) und das Browser-Verhalten über [diese Richtlinien](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) verwalten. 

