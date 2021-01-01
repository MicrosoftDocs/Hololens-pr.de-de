---
title: Übersicht über CSPs und Geräteverwaltung konfigurieren
description: Konfigurieren von Kryptografiedienstanbieter, Richtlinien-und Geräteverwaltung
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c6da29506035525b1b1b5141a04603f63de1ef24
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252776"
---
# Übersicht über CSPs und Geräteverwaltung konfigurieren

IT-Administratoren können Richtlinieneinstellungen auf HoloLens 2 definieren und implementieren. Die verwendeten Konfigurationseinstellungen sind abhängig vom Bereitstellungsszenario. Dabei bieten unternehmenseigene Geräte die umfassendsten Kontrollmöglichkeiten für die IT. In Windows 10 sind Configuration Service Providers (CSP) eine Schnittstelle zum Lesen, festlegen, ändern oder Löschen von Konfigurationseinstellungen auf dem Gerät. Diese Einstellungen sind mit Registrierungsschlüsseln oder Dateien verknüpft. Einige Konfigurationsdienst Anbieter unterstützen das WAP-Format, einige unterstützen SyncML und einige unterstützen beide.

Weitere Informationen zu Windows 10 holographischen Device Management-Kryptografiedienstanbieter finden Sie in der vollständigen Liste der [in HoloLens-Geräten unterstützten Kryptografiedienstanbieter](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).
IT-Administratoren können auch Richtlinien-CSP auf Geräten verwalten, finden Sie in der vollständigen Liste der [Richtlinien Kryptografiedienstanbieter, die von HoloLens 2 unterstützt](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)werden.

## Konfigurationsmethoden

### Konfigurieren mit MDM

Kryptografiedienstanbieter und Richtlinien können auf allen Personen-oder Unternehmensgeräten, die in einem MDM-System registriert sind, problemlos verwaltet werden. Nachdem ein Gerät für Ihre MDM-Lösung registriert wurde, können Sie dieses Gerät oder eine Gruppe von Geräten mithilfe von Gerätekonfigurationen verwalten. Erfahren Sie mehr darüber, wie [Sie Ihre HoloLens-Geräte über MDM verwalten](hololens-mdm-configure.md).

### Konfigurieren mit Bereitstellungspaketen

HoloLens 2 unterstützt auch das Festlegen eines eingeschränkten Satzes von CSP-Konfigurationen für HoloLens 2-Geräte über benutzerdefinierte Bereitstellungspakete. Bereitstellungspakete werden in der Regel für nicht-MDM-verwaltete Geräte genutzt und müssen manuell auf jedes Gerät angewendet werden. Lesen Sie Informationen zum Erstellen benutzerdefinierter [Bereitstellungspakete für HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).

## Konfigurationen

### Allgemeine Geräteeinschränkungen

Einige Geräteeinschränkungen sind so einfach, dass eine Funktion oder Verbindung mit dem Gerät deaktiviert wird. Weitere Informationen zu diesen Informationen finden Sie unter [Allgemeine Geräteeinschränkungen.](hololens-common-device-restrictions.md)

### Kiosk Modi

Verwenden Sie den Kiosk Modus, um zu steuern, welche Identitäten standardmäßig auf welche apps zugreifen können. Kiosks können für eine einzelne APP oder für mehrere App-Benutzeroberflächen verwendet werden. Kiosk-Konfigurationen sind von einer einzelnen App für alle Benutzer, die das Gerät verwenden, bis hin zu unterschiedlichen Auswahlmöglichkeiten für Apps für verschiedene Gruppen. Im Kiosk Modus werden die "erlaubten Apps" nicht dazu angehalten, andere apps zu starten. Weitere Informationen finden Sie unter [Informationen zu Kiosk Modi und deren Verwendung](hololens-kiosk.md).

### Sichtbarkeit der Seite "Einstellungen"

Verwenden Sie die Einstellungen-App-Richtlinie, um zu steuern, welche Identitäten standardmäßig Zugriff auf Einstellungen haben. Mit dieser Richtlinie kann die Einstellungs-APP so konfiguriert werden, dass entweder nur die Option "Seiten auswählen" oder "alle ausgewählten Seiten ausblenden" angezeigt wird. [Hier erfahren Sie, wie Sie die verfügbaren Seiten konfigurieren](settings-uri-list.md).

Dieses Feature ist derzeit nur in [Windows-Insider-Builds](hololens-insider.md)verfügbar. Stellen Sie sicher, dass Geräte, für die Sie dieses Feature verwenden möchten, auf Build 19041.1349 + sind.

### WDAC

Verwenden Sie die WDAC-Konfiguration, um zu steuern, welche apps/Prozesse zugelassen/nicht zulässig sind, unabhängig davon, ob sich das System im Kioskmodus befindet.
[Schauen Sie sich unsere Übersicht für WDAC.](windows-defender-application-control-wdac.md)
