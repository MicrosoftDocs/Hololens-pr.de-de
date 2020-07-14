---
title: Hardwaregesicherter Integritäts- und Laufzeitnachweis
description: Begrenzen der Verwendung von Kennwörtern für HoloLens
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: Sicherheit, HoloLens, hardwaregesicherte Integrität, Laufzeitnachweis, UEFI, UEFI Secure Boot, Secure Boot, TPM, Threat Protection, Windows-Antipersistenzzusicherung (Windows Anti-Persistence Assurance), Codeintegrität, Codeschutz,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens 2
ms.openlocfilehash: d1a3fe02b64ce1566806119e5309fd262667b181
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865716"
---
# Hardwaregesicherter Integritäts- und Laufzeitnachweis

Hardwaregesicherter Integritäts- und Laufzeitnachweis schützt vor Bedrohungen, die vor dem Start eines Betriebssystems, während der Laufzeit entstehen, wenn das Gerät Hardware und Remotenachweisdienste verwendet, um sicherzustellen, dass die Integrität beim Start und während der gesamten Laufzeit beibehalten wird.

## Sicherer UEFI-Start

Mit HoloLens2 wird zu jedem Zeitpunkt der sichere UEFI-Start (Unified Extensible Firmware Interface) erzwungen, und UEFI startet nur Windows Holographic for Business.
Der sichere Start gewährleistet, dass die gesamte Startkette auf Integrität überprüft und Windows immer mit den richtigen Sicherheitsrichtlinien gestartet wird. Weitere Informationen zum sicheren Start finden Sie hier.

## TPM

Das Trusted Platform Module (TPM) ist ein spezieller Chip auf einem Endpunktgerät. HoloLens2 verwendet ein TPM 2.0, das hardwaregestützter Schlüsselisolation bietet.

## Schutz vor der Bedrohung durch dauerhaften Zugriff

Das Ziel der meisten Cyberangriffe besteht darin, einen dauerhaften Zugriff auf ein Gerät aufrecht zu erhalten. Im Rahmen der Cyberkriminalität können Angreifer durch Aufrechterhalten dieses dauerhaften Zugriffs (Persistenz) mit einem kompromittierten Windows-Gerät an einem Botnet teilnehmen, Zugriff auf das Gerät oder an andere ruchlosen Benutzer verkaufen oder wiederholt Datendiebstahl begehen. In der Welt der gezielten Angriffe ist dauerhafter Zugriff für erfolgreiche Cyberangriffe unerlässlich – ganz gleich, ob auf einem Gerät oder (häufiger) in einem ganzen Netzwerk.  

Tatsächlich werden gezielte Angriffe aufgrund ihrer strategischen Notwendigkeit, den Zugriff auf ein Zielgerät oder -netzwerk aufrechtzuerhalten, als "fortgeschrittene persistente Bedrohungen" betrachtet. Aus diesem Grund erachtet Windows Holographic for Business die Verteidigung gegen dauerhaften Zugriff als absolut unerlässlich und setzt Antipersistenztechnologie ein, um den Kunden ein eisernes Sicherheitsversprechen zu geben.

### Sicheres Starten 

HoloLens2 erzwingt den sicheren UEFI-Start (Unified Extensible Firmware Interface) auf allen Kernbetriebssystemen. UEFI startet nur vertrauenswürdige Microsoft-Plattformen, wodurch gewährleistet wird, dass die gesamte Startkette auf Integrität überprüft und Windows immer mit den richtigen Sicherheitsrichtlinien gestartet wird. Bei HoloLens2 lässt weder das Deaktivieren des sicheren Starts noch die Verwendung von Bootloadern von Drittanbietern zu.

> [!Tip]
> Weitere Informationen zum [sicheren Start](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).

### Windows-Antipersistenzzusicherung

Durch die Antipersistenzzusicherung garantiert HoloLens2 seinen Benutzern, dass selbst in dem unwahrscheinlichen Fall einer Laufzeitkompromittierung des Systems – wie z.B. bei einem Remote-Exploit – ein solches Ereignis abgemildert wird, indem der gesamte bösartige Code durch einfaches Ausschalten des Geräts aus dem System entfernt wird. Um die Antipersistenz noch weiter zu verbessern, hat HoloLens2 einen leistungsfähigen Integritätsschutz hinzugefügt und Schreibschutzmechanismen eingerichtet.

Dauerhafter Zugriff auf Betriebssystemdaten in Form von Daten ist nach wie vor möglich, es sei denn, der Benutzer führt am Gerät ein Zurücksetzen mit einem Knopfdruck (PBR) durch, wodurch alle veränderbaren Partitionen gelöscht werden. Während der dauerhafte Zugriff auf unveränderliche Partitionen erheblich erschwert wird, muss der Benutzer Hololens2 durch PBR zurücksetzen, um mögliche Bedrohungspersistenz aus änderbaren Teilen zu entfernen.

## Codeintegritätsschutz 

Codeintegrität (CI) ist eine wichtige Sicherheitseigenschaft eines modernen Betriebssystems. Durch Erzwingen von Codeintegrität lassen sich solide Sicherheitsentscheidungen treffen, da sie die Herkunft des Codes für den Benutzer und das Betriebssystem transparent macht. Die vollständige Codeintegrität muss die bisherige binäre Bildsignierung erweitern und die Durchsetzung zur Laufzeit umfassen, z.B. Kontrollflussintegrität und dynamische Codebeschränkungen. Codeintegrität ist entscheidend, um zahlreiche Angriffsklassen zu verhindern, einschließlich Social-Engineering-Schadsoftware, wie Ransomware, Remotecodeausführungs-Exploits und verschiedene andere Angriffsklassen.
