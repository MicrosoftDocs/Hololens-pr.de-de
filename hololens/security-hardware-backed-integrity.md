---
title: Hardwaregesicherter Integritäts- und Laufzeitnachweis
description: Hardwaregesicherter Integritäts- und Laufzeitnachweis
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: Sicherheit, HoloLens, hardwaregesicherte Integrität, Laufzeitnachweis, UEFI, UEFI Secure Boot, Secure Boot, TPM, Threat Protection, Windows-Antipersistenzzusicherung (Windows Anti-Persistence Assurance), Codeintegrität, Codeschutz,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0a89fa5e61e560f629444efd2728f6dd41db60d3
ms.sourcegitcommit: ab35169529776f0682eeb8fa448c9d9e8f598513
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/17/2021
ms.locfileid: "11340524"
---
# Hardwaregesicherter Integritäts- und Laufzeitnachweis

Hardwaregesicherter Integritäts- und Laufzeitnachweis schützt vor Bedrohungen, die vor dem Start eines Betriebssystems, während der Laufzeit entstehen, wenn das Gerät Hardware und Remotenachweisdienste verwendet, um sicherzustellen, dass die Integrität beim Start und während der gesamten Laufzeit beibehalten wird.

## Sicherer UEFI-Start

HoloLens 2 erzwingt den sicheren Start der Unified Extensible Firmware Interface (UEFI) immer, und UEFI startet nur Windows Holographic for Business. 
Der sichere Start gewährleistet, dass die gesamte Startkette auf Integrität überprüft und Windows immer mit den richtigen Sicherheitsrichtlinien gestartet wird. Erfahren Sie mehr über [den sicheren Start](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).

## TPM

Das Trusted Platform Module (TPM) ist ein spezieller Chip auf einem Endpunktgerät. HoloLens 2 verwendet ein TPM 2.0, das Hardware-verstärkte Schlüsselisolierung bietet. Erfahren Sie mehr über [die Grundlagen von TPM](https://docs.microsoft.com/windows/security/information-protection/tpm/tpm-fundamentals).

## Schutz vor der Bedrohung durch dauerhaften Zugriff

Das Ziel der meisten Cyberangriffe besteht darin, einen dauerhaften Zugriff auf ein Gerät aufrecht zu erhalten. Im Rahmen der Cyberkriminalität können Angreifer durch Aufrechterhalten dieses dauerhaften Zugriffs (Persistenz) mit einem kompromittierten Windows-Gerät an einem Botnet teilnehmen, Zugriff auf das Gerät oder an andere ruchlosen Benutzer verkaufen oder wiederholt Datendiebstahl begehen. In der Welt der gezielten Angriffe ist dauerhafter Zugriff für erfolgreiche Cyberangriffe unerlässlich – ganz gleich, ob auf einem Gerät oder (häufiger) in einem ganzen Netzwerk.  

Tatsächlich werden gezielte Angriffe aufgrund ihrer strategischen Notwendigkeit, den Zugriff auf ein Zielgerät oder -netzwerk aufrechtzuerhalten, als "fortgeschrittene persistente Bedrohungen" betrachtet. Aus diesem Grund erachtet Windows Holographic for Business die Verteidigung gegen dauerhaften Zugriff als absolut unerlässlich und setzt Antipersistenztechnologie ein, um den Kunden ein eisernes Sicherheitsversprechen zu geben.

### Sicheres Starten

HoloLens2 erzwingt den sicheren UEFI-Start (Unified Extensible Firmware Interface) auf allen Kernbetriebssystemen. UEFI startet nur Microsoft-vertrauenswürdige Plattformen, wodurch sichergestellt wird, dass die gesamte Startkette auf Integrität überprüft wird und Windows immer mit den korrekten Sicherheitsrichtlinien gestartet wird.  Bei HoloLens2 lässt weder das Deaktivieren des sicheren Starts noch die Verwendung von Bootloadern von Drittanbietern zu.

> [!Tip]
> Weitere Informationen zum [sicheren Start](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).

### Windows-Antipersistenzzusicherung

Durch die Antipersistenzzusicherung garantiert HoloLens2 seinen Benutzern, dass selbst in dem unwahrscheinlichen Fall einer Laufzeitkompromittierung des Systems – wie z.B. bei einem Remote-Exploit – ein solches Ereignis abgemildert wird, indem der gesamte bösartige Code durch einfaches Ausschalten des Geräts aus dem System entfernt wird. Um die Antipersistenz noch weiter zu verbessern, hat HoloLens2 einen leistungsfähigen Integritätsschutz hinzugefügt und Schreibschutzmechanismen eingerichtet.

Dauerhafter Zugriff auf Betriebssystemdaten in Form von Daten ist nach wie vor möglich, es sei denn, der Benutzer führt am Gerät ein Zurücksetzen mit einem Knopfdruck (PBR) durch, wodurch alle veränderbaren Partitionen gelöscht werden. Während die Persistenz auf unveränderlichen Partitionen deutlich erschwert wird, muss der Benutzer die HoloLens 2 durch PBR zurücksetzen, um eine mögliche Bedrohungspersistenz von veränderlichen Teilen zu entfernen.

## Codeintegritätsschutz

Codeintegrität (CI) ist eine wichtige Sicherheitseigenschaft eines modernen Betriebssystems. Durch Erzwingen von Codeintegrität lassen sich solide Sicherheitsentscheidungen treffen, da sie die Herkunft des Codes für den Benutzer und das Betriebssystem transparent macht. Die vollständige Codeintegrität muss die bisherige binäre Bildsignierung erweitern und die Durchsetzung zur Laufzeit umfassen, z.B. Kontrollflussintegrität und dynamische Codebeschränkungen. Codeintegrität ist entscheidend, um zahlreiche Angriffsklassen zu verhindern, einschließlich Social-Engineering-Schadsoftware, wie Ransomware, Remotecodeausführungs-Exploits und verschiedene andere Angriffsklassen.
