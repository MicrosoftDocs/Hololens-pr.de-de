---
title: Statustrennung und -isolation
description: Erfahren Sie mehr zu Statustrennung, Isolation, Codesignierung und Defender-Anwendungen auf Ihrem HoloLens 2-Mixed Reality-Gerät.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: Sicherheit, HoloLens, Statustrennung, Statustrennung und -isolation, HoloLens 2, HoloLens2-Sicherheit, Sicherheitsübersicht, Sicherheitsarchitektur, Architektur, HoloLens 2-Architektur
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0487ea49c706c753f4dfca7da7daa499d1715e9f
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639793"
---
# <a name="state-separation-and-isolation"></a>Statustrennung und -isolation

Statustrennung und -isolation schützen kritische Teile des HoloLens 2-Betriebssystems vor Veränderungen – wie z. B. diejenigen, die erforderlich sind, damit das Betriebssystem in einen vertrauenswürdigen Status gestartet werden kann. Bei der Isolationstechnologie werden nicht vertrauenswürdige Anwendungen in eine isolierte Sandbox-Umgebung verschoben, um sicherzustellen, dass sie die Systemsicherheit nicht beeinträchtigen.

## <a name="state-separation"></a>Statustrennung

Die Statustrennung in HoloLens 2 verbessert die Sicherheit und Wartbarkeit (Aktualisierung) erheblich und trägt zum Schutz Ihrer Anwendungsdaten bei.  Die Statustrennung funktioniert wie folgt:
  * Das Core-Betriebssystem ist im Core-Betriebssystemvolume gespeichert (bei vertrauenswürdigen oder verifizierten Microsoft-Betriebssystemen, die das Betriebssystem aktualisieren).
  * Die Teile des Betriebssystems, die zur Laufzeit geändert werden können (z. B. herunterladbare Treiber und Konfigurationen), verwenden eine weitere Statustrennung, um die Daten zu partitionieren und sie an sicheren, separaten Speicherorten zu speichern.
  * Jedem sicheren Speicherort sind unterschiedliche Sicherheitsrichtlinien zugeordnet, die verschiedene Sicherheitsvorteile bieten, die im folgenden Abschnitt näher erläutert werden.

## <a name="state-separation-benefits"></a>Vorteile der Statustrennung

  * Sicherheit: Die in HoloLens 2 enthaltene Statustrennung verbessert die Plattformintegrität, die Resistenz gegen Schadsoftware und den Schutz der Benutzerdaten erheblich. Indem der unveränderliche Teil des Betriebssystems getrennt und schreibgeschützt oder integritätsgeschützt gemacht wird, macht die Statustrennung es für Schadsoftware extrem schwierig, nach einem Kaltstart weiter zu bestehen. 
  * Updates: Mit HoloLens 2 werden Updates einfach und zuverlässig, sobald das Core-Betriebssystem unveränderbar ist und sauber vom Rest der Daten auf dem Gerät getrennt wurde.  Darüber hinaus schafft die Statustrennung die entscheidende Grundlage für dramatisch schnellere Updates, wodurch das Betriebssystem in einem einzigen Schritt ersetzt werden kann (atomare Einheit).
  * Zurücksetzen des Geräts: Das Zurücksetzen von HoloLens 2 löscht benutzergenerierte Daten und Benutzeranwendungsdaten auf dem Gerät – einschließlich interner und externer Speicherorte. Die aktuellen Anwendungen für das Betriebssystem und sicherheitskritische Anwendungen sowie die aktuellen kundenspezifischen Anwendungen von Microsoft und OEM (vorinstalliert) bleiben erhalten. Diese vorinstallierten Anwendungen können nach Abschluss des Zurücksetzens auf dem Gerät reaktiviert werden.

### <a name="state-separation-states"></a>Status der Statustrennung

Die Statustrennung gewährleistet, dass das Betriebssystem nur durch vertrauenswürdige Gerätekomponenten von Microsoft geändert werden und nur ein hochwertiger Status über Neustarts hinweg bestehen kann. Ein weiterer Systemstatus besteht nur für die Dauer der Startsitzung und wird nach einem Neustart verworfen. Aufgrund der Statustrennung kann das Gerät schnell wieder in den Werkszustand zurückversetzt werden. Die Status von Windows Holographic for Business lassen sich in diese verschiedenen Kategorien einteilen:
  * Core-Betriebssystem: nicht änderbarer Status
  * Betriebssystemdaten: änderbarer Status 
  * Benutzerdaten: änderbarer Status

Jeder dieser Betriebszustände von HoloLens 2 wird im folgenden Abschnitt beschrieben.

#### <a name="core-operating-system"></a>Core-Betriebssystem

Ein unveränderlicher Status besteht aus ausführbaren Dateien und Daten, die unveränderlich sind und nur von Microsoft während der Installation von Updates geändert werden können. Während einer solchen Aktualisierung des Core-Betriebssystems wird ein neues Image aktiviert, das den letzten gewünschten Betriebszustand enthält.
Der nicht änderbare Status wird als schreibgeschützt gekennzeichnet (oder ist anderweitig integritätsgeschützt), wodurch das Fortbestehen von Schadsoftware mit erhöhten Rechten verhindert wird. Die folgenden ausführbaren Dateien und Daten sind im unveränderlichen Status geschützt:
  * Windows Holographic-Posteingangstreiber
  * Betriebssystem-Binärdateien
  * Windows-Posteingangstreiber
  * Statische Windows Holographic-Einstellungen, die in der Windows-Registrierungsstruktur (HKLM) gespeichert sind
    * Beispiel: HKLM speichert die Konfigurationsinformationen für die auf einem Computer installierten Anwendungen. Es speichert außerdem Informationen zur Erkennung von Hardware und den entsprechenden Treibern.
Durch den Schutz dieser Bestandteile im unveränderlichen Status (Schutz durch Integrität und Schreibschutz) stellen wir sicher, dass das Core-Betriebssystem immer in einen vertrauenswürdigen Status gestartet wird. Darüber hinaus können wir beim Zurücksetzen eines Geräts sicherstellen, dass das Gerät nur in die Komponenten gestartet wird, die sich in diesem unveränderlichen Bereich befinden. 

#### <a name="operating-system-data"></a>Betriebssystemdaten 

Es ist wichtig zu beachten, dass ausführbare Dateien und Daten, die zur Laufzeit veränderbar sind (und nicht kritisch für die Funktion des Betriebssystems sind), verworfen und neu erstellt werden können, wenn die Daten beschädigt oder kompromittiert sind. Ein veränderlicher Status mit hohem Wert muss entweder aus funktionalen Gründen vom Betriebssystem aufrechterhalten werden, oder es wird erwartet, dass er über das Herunterfahren oder Neustarten des Betriebssystems durch unterstützte Szenarien für Windows-Betriebssysteme und Geräte hinweg erhalten bleibt. Beispiele für einen veränderlichen Status mit hohem Wert sind:
  * Globale Geräteeinstellungen, wie z. B. die Deaktivierung des Speicherorts für alle Benutzer, die vom IT-Administrator konfiguriert wurden.
  * Zugriff auf WLAN-Netzwerkverbindungen mit Beibehaltung der Daten-/Geräteverknüpfungen und der zugehörigen Verbindungskennwörter.
  * Absturzabbilder einschließlich Einstellungen, Protokollen.
  * Für neu erkannte Geräte bei Bedarf heruntergeladene Treiber.
Ein veränderlicher Status mit hohem Wert ist auf HoloLens 2 im Daten-Sicherheits-Speicherort gespeichert, entweder als gespeicherte Datei auf einem Datenträger oder in einer dauerhaften Registrierungsstruktur.

#### <a name="user-data"></a>Benutzerdaten

Die letzte Kategorie von Status stellen Benutzerdaten dar, die von UWP-Anwendungen oder dem Betriebssystem erstellt oder beibehalten werden. Alle bekannten Benutzerordner wie „Downloads“, „Dokumente“, „Videos“, Benutzerprofile und die Struktur HKEY_CURRENT_USER sind ebenfalls an diesem Ort gespeichert. Diese Daten können nicht ohne ordnungsgemäße Anmeldeinformationen extrahiert werden. Weitere Informationen darüber, wie Ihre Daten geschützt werden, finden Sie unter [Verschlüsselung und Datenschutz](security-encryption-data-protection.md).

##  <a name="isolation"></a>Isolation

Zum Erreichen dieses Gleichgewichts verfügt HoloLens 2 über ein Core-Betriebssystem, das für primäre Funktionen wie Hochfahren, Hardwaresteuerung, Anmeldung usw. verwendet wird. Es gibt nur zwei Sätze von Anwendungen, die unter dem Core-Betriebssystem laufen – vorinstallierte Anwendungen und UWP-Anwendungen.

## <a name="code-signing"></a>Codesignierung

Das digitale Signieren von Code ermöglicht den Nachweis, dass ausführbare Dateien und Skripts nicht verändert wurden, da sie von einer vertrauenswürdigen Quelle signiert wurden und somit Authentizität und Integrität bieten. Die Stellen, denen HoloLens 2 standardmäßig vertraut, sind Microsoft und Microsoft Store. IT-Administratoren können dem Gerät über die CSPs [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) und [RootCATrustedCertificates](/windows/client-management/mdm/rootcacertificates-csp) neue Zertifikate hinzufügen. Sie können darüber hinaus die [AllowAllTrustedApps-Richtlinie](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) verwenden, um zusätzlichen quergeladenen oder [branchenbezogenen Apps](/intune/apps/lob-apps-windows)zu vertrauen. Die Zertifikate befinden sich im Zertifikatspeicher des lokalen Computers, der bei Verwendung von „Gerät“ in HKLM/Stamm und bei Verwendung von „Benutzer“ in HKCU gespeichert ist.

## <a name="defender-protections"></a>Defender-Schutzmaßnahmen
HoloLens 2 verwendet Microsoft-Dienste, um den Benutzern ein hohes Maß an Sicherheit zu bieten:

* [Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) wird vom Betriebssystem automatisch auf Windows Holographic aktiviert und schützt vor Phishing und Schadsoftware sowie vor dem Herunterladen potenziell schädlicher Dateien auf Edge. Er kann nicht vom Benutzer deaktiviert werden, wohl aber durch Richtlinien deaktiviert werden.

* [Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) blockiert nicht autorisierten Netzwerkverkehr von und zu Ihrem Gerät. Diese ist standardmäßig aktiviert und kann vom Kunden nicht durch lokale Aktionen oder Richtlinien konfiguriert werden. 

* [Windows Defender Anwendungssteuerung](/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview): HoloLens 2 unterstützt WDAC, wodurch IT-Administratoren Anwendungssteuerungsrichtlinien per Push auf das Gerät übertragen können. Weitere Informationen finden Sie unter [Verwenden von WDAC auf HoloLens 2-Geräten mit MSFT Intune](/mem/intune/configuration/custom-profile-hololens). 

IT-Administratoren können das SmartScreen-Verhalten mithilfe von [AllowSmartScreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) und das Browserverhalten mithilfe [dieser Richtlinien](/windows/client-management/mdm/policy-csps-supported-by-hololens2) verwalten. 

