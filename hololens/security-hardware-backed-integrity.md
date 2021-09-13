---
title: Hardwaregestützter Integritäts- und Laufzeitnachweis
description: Hardwaregestützter Integritäts- und Laufzeitnachweis
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: Sicherheit, Hololens, hardwaregestützte Integrität, Laufzeitnachweis, UEFI, sicherer UEFI-Start, sicherer Start, TPM, Bedrohungsschutz, Windows-Antipersistenzsicherheit, Codeintegrität, Codeschutz,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 037f9325555244314518c81d7814bf983c345af6
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034405"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Hardwaregestützter Integritäts- und Laufzeitnachweis

Der hardwaregestützte Integritäts- und Laufzeitnachweis schützt vor Bedrohungen, deren Ursprung noch vor dem Zeitpunkt des Betriebssystemstarts liegt, während der Laufzeit, wenn das Gerät Hardware verwendet, und bietet Remotenachweisdienste, um sicherzustellen, dass die Integrität beim Systemstart und während des Betriebs ständig aufrecht erhalten wird.

## <a name="uefi-secure-boot"></a>Sicherer UEFI-Start

HoloLens 2 erzwingt immer einen sicheren UEFI-Start (Unified Extensible Firmware Interface), und UEFI startet nur Windows Holographic for Business.
Sicherer Start stellt sicher, dass die gesamte Startkette auf Integrität überprüft wird und Windows immer mit den richtigen Sicherheitsrichtlinien gestartet wird. Weitere Informationen dazu finden Sie unter [Sicherer Start](/windows-hardware/design/device-experiences/oem-secure-boot).

## <a name="tpm"></a>TPM

Das Trusted Platform Module (TPM) ist ein spezialisierter Chip auf einem Endpunktgerät. HoloLens 2 verwendet TPM 2.0, das mithilfe von Hardware durchgesetzte Schlüsselisolation bereitstellt. Mehr dazu erfahren Sie unter [TPM-Grundlagen](/windows/security/information-protection/tpm/tpm-fundamentals).

## <a name="persistence-access-threat-protection"></a>Bedrohungsschutz vor Persistenzzugriff

Das Ziel der meisten Cyberangriffe besteht darin, dauerhaften Zugriff auf ein Gerät zu erreichen und aufrecht zu erhalten. In einem Cybercrime-Szenario ermöglicht diese Dauerhaftigkeit den Beitritt eines kompromittierten Windows-Geräts zu einem Botnet, den Verkauf von Zugriff zu dem Gerät an andere skrupellose Benutzer oder wiederholten Datendiebstahl. In der Welt der gezielten Angriffe ist Persistenz für einen erfolgreichen Cyberangriff unerlässlich – ganz gleich, ob auf einem Gerät oder (häufiger) in einem gesamten Netzwerk.  

Tatsächlich werden gezielte Angriffe aufgrund ihrer strategischen Notwendigkeit, den Zugriff auf ein Zielgerät oder Netzwerk beizubehalten, als „erweiterte persistente Bedrohungen“ betrachtet. Aus diesem Grund betrachtet Windows Holographic for Business die Verteidigung gegen Persistenz als absolut entscheidend und verwendet Antipersistenztechnologie, um eine hieb- und stichfeste Kundensicherheitszusage zu geben.

### <a name="secure-boot"></a>Sicherer Start

HoloLens 2 erzwingt den sicheren UEFI-Start (Unified Extensible Firmware Interface) für alle Betriebssystemstatus des Kerns. UEFI startet nur Plattformen, die einen Microsoft-Vertrauensstatus besitzen, wodurch sichergestellt ist, dass die gesamte Startkette auf Integrität überprüft wird und Windows immer mit den richtigen Sicherheitsrichtlinien gestartet wird. HoloLens 2 erlaubt keine Deaktivierung des sicheren Systemstarts und lässt auch keine Startladeprogramme von Drittanbietern zu.

> [!Tip]
> Weitere Informationen zum [Sicheren Start](/windows-hardware/design/device-experiences/oem-secure-boot).

### <a name="windows-anti-persistence-assurance"></a>Windows-Antipersistenzsicherheit

HoloLens 2-Antipersistenz garantiert den Benutzern, dass selbst in der seltenen Situation, dass jemals eine Laufzeitkompromittierung des Systems auftritt (z. B. ein Remote-Exploit), ein solches Ereignis durch einfaches Ausschalten des Geräts entschärft und der gesamte Schadcode vom System entfernt würde. Zum weiteren Stärken der Antipersistenz verfügt HoloLens 2 zusätzlich über leistungsstarken Integritätsschutz und weist schreibgeschützte Schutzmaßnahmen auf.

Persistenz ist für Betriebssystemdaten in Form von Daten weiterhin möglich, es sei denn, der Benutzer führt ein Zurücksetzen des Geräts auf Knopfdruck (Push-Button Reset, PBR) aus, das alle veränderlichen Partitionen zurücksetzt. Zwar ist der Persistenzschutz für unveränderliche Partitionen stark verbessert, jedoch muss der Benutzer einen PBR von HoloLens 2 ausführen, um jede mögliche Bedrohungspersistenz aus veränderlichen Teilen zu entfernen.

## <a name="code-integrity-protection"></a>Schutz der Codeintegrität

Codeintegrität (CI) ist eine zentrale Sicherheitseigenschaft moderner Betriebssysteme. Das Durchsetzen von CI ermöglicht fundierte Sicherheitsentscheidungen, da dadurch sichergestellt wird, dass die Herkunft von Code sowohl für den Benutzer als auch für das Betriebssystem transparent ist. Vollständige Codeintegrität muss sich über das Signieren von binären Images hinaus erstrecken und Durchsetzung zur Laufzeit beinhalten, etwa in Form von Steuerungsflussintegrität und dynamischen Codeeinschränkungen. CI ist wichtig, um mehrere Klassen von Angriffen zu verhindern, einschließlich Social Engineering-Schadsoftware, z. B. Ransomware, Exploits für Remotecodeausführung und verschiedene andere Angriffsklassen.
