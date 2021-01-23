---
title: Übersicht über CSPs und Geräteverwaltung konfigurieren
description: Erfahren Sie, wie Sie CSPs, Richtlinien und Geräteverwaltung mithilfe von Mobile Device Management und Bereitstellungspaketen konfigurieren.
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
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283246"
---
# Übersicht über CSPs und Geräteverwaltung konfigurieren

IT-Administratoren können Richtlinieneinstellungen auf HoloLens 2 definieren und implementieren. Die verwendeten Konfigurationseinstellungen sind abhängig vom Bereitstellungsszenario. Dabei bieten unternehmenseigene Geräte die umfassendsten Kontrollmöglichkeiten für die IT. In Windows 10 sind Konfigurationsdienstanbieter (Configuration Service Providers, CSP) eine Schnittstelle zum Lesen, Festlegen, Ändern oder Löschen von Konfigurationseinstellungen auf dem Gerät. Diese Einstellungen sind mit Registrierungsschlüsseln oder Dateien verknüpft. Einige Konfigurationsdienstanbieter unterstützen das WAP-Format, andere syncML und einige unterstützen beide.

Weitere Informationen zu Windows 10 Holographic-Geräteverwaltungs-CSPs finden Sie in der vollständigen Liste der [CSPs, die auf HoloLens-Geräten unterstützt werden.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)
#A0 können den Richtlinien-CSP auch auf Geräten verwalten. Eine vollständige Liste der von [HoloLens 2 unterstützten Richtlinien-CSPs finden Sie in der liste.](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## Konfigurationsmethoden

### Konfigurieren mit MDM

CSPs und Richtlinien können problemlos auf jedem persönlichen oder Unternehmensgerät verwaltet werden, das in einem MDM-System registriert ist. Sobald ein Gerät in Ihrer MDM-Lösung registriert ist, können Sie dieses Gerät oder gerätesatz mithilfe von Gerätekonfigurationen verwalten. Erfahren Sie mehr über die [Verwaltung Ihrer HoloLens-Geräte über MDM.](hololens-mdm-configure.md)

### Konfigurieren mit Bereitstellungspaketen

HoloLens 2 unterstützt auch das Festlegen einer begrenzten Gruppe von #A0 für HoloLens 2-Geräte über benutzerdefinierte Bereitstellungspakete. Bereitstellungspakete werden in der Regel für nicht von MDM verwaltete Geräte genutzt und müssen manuell auf jedes Gerät angewendet werden. Lesen Sie Informationen zum Erstellen [benutzerdefinierter Bereitstellungspakete für HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning)

## Konfigurationen

### Allgemeine Geräteeinschränkungen

Einige Geräteeinschränkungen sind so einfach und deaktivieren eine Funktionalität oder Verbindung mit dem Gerät. Weitere Informationen zu diesen Informationen finden Sie unter [allgemeinen Geräteeinschränkungen.](hololens-common-device-restrictions.md)

### Kioskmodi

Verwenden Sie den Kioskmodus, um zu steuern, welche Identitäten standardmäßig auf welche Apps zugreifen können. Kioske können für eine einzelne App oder eine Benutzeroberfläche mit mehreren Apps verwendet werden. Kioskkonfigurationen reichen von einer einzelnen App für alle Benutzer des Geräts bis zu verschiedenen Auswahlen von Apps für unterschiedliche Gruppen. Der Kioskmodus hält "zugelassene Apps" nicht am Starten anderer Apps ab und sollte niemals verwendet werden. Weitere Informationen finden [Sie in den Kioskmodi und deren Verwendung.](hololens-kiosk.md)

### Sichtbarkeit der Einstellungsseite

Verwenden Sie die Einstellungs-App-Richtlinie, um zu steuern, welche Identitäten standardmäßig zugriff auf Einstellungen haben. Mithilfe dieser Richtlinie kann die App "Einstellungen" so konfiguriert werden, dass entweder nur die ausgewählten Seiten angezeigt oder alle ausgewählten Seiten ausgeblendet werden. [Erfahren Sie, wie Sie die verfügbaren Seiten konfigurieren.](settings-uri-list.md)

Dieses Feature ist derzeit nur in [Windows-Insider-Builds verfügbar.](hololens-insider.md) Stellen Sie sicher, dass Geräte, für die Sie dieses Feature verwenden möchten, ab Build 19041.1349 verfügbar sind.

### WDAC

Verwenden Sie die WDAC-Konfiguration, um zu steuern, welche Apps/Prozesse zulässig/nicht gestartet werden dürfen, unabhängig davon, ob sich das System im Kioskmodus befindet oder nicht.
[Sehen Sie sich unsere Übersicht für WDAC an.](windows-defender-application-control-wdac.md)
