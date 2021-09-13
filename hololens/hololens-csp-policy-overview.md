---
title: Übersicht über CSPs und Geräteverwaltung konfigurieren
description: Erfahren Sie, wie Sie CSPs, Richtlinien und Geräteverwaltung mithilfe von Mobilen Geräteverwaltung und Bereitstellungspaketen konfigurieren.
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
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032426"
---
# <a name="configure-csps-and-device-management-overview"></a>Übersicht über CSPs und Geräteverwaltung konfigurieren

IT-Administratoren können Richtlinieneinstellungen für HoloLens 2 definieren und implementieren. Die verwendeten Konfigurationseinstellungen sind abhängig vom Bereitstellungsszenario. Dabei bieten unternehmenseigene Geräte die umfassendsten Kontrollmöglichkeiten für die IT. In Windows 10 sind Konfigurationsdienstanbieter (Configuration Service Providers, CSP) eine Schnittstelle zum Lesen, Festlegen, Ändern oder Löschen von Konfigurationseinstellungen auf dem Gerät. Diese Einstellungen sind mit Registrierungsschlüsseln oder Dateien verknüpft. Einige Konfigurationsdienstanbieter unterstützen das WAP-Format, einige unterstützen SyncML und andere beides.

Weitere Informationen zu Windows 10 Holographic-Geräteverwaltungs-CSPs finden Sie in der vollständigen Liste der [in HoloLens Geräten unterstützten CSPs.](/windows/client-management/mdm/configuration-service-provider-reference#hololens)
IT-Administratoren können richtlinien-CSP auch auf Geräten verwalten. Die vollständige Liste der [richtlinienseitigen CSPs,](/windows/client-management/mdm/policy-csps-supported-by-hololens2)die von HoloLens 2 unterstützt werden.

## <a name="configuration-methods"></a>Konfigurationsmethoden

### <a name="configure-with-mdm"></a>Konfigurieren mit MDM

CSPs und Richtlinien können problemlos auf jedem persönlichen oder Unternehmensgerät verwaltet werden, das in einem MDM-System registriert ist. Sobald ein Gerät in Ihrer MDM-Lösung registriert ist, können Sie dieses Gerät oder eine Gruppe von Geräten mithilfe von Gerätekonfigurationen verwalten. Erfahren Sie mehr über das [Verwalten Ihrer HoloLens-Geräte über MDM.](hololens-mdm-configure.md)

### <a name="configure-with-provisioning-packages"></a>Konfigurieren mit Bereitstellungspaketen

HoloLens 2 unterstützt auch das Festlegen eines begrenzten Satzes von CSP-Konfigurationen für HoloLens 2 Geräte über benutzerdefinierte Bereitstellungspakete. Bereitstellungspakete werden in der Regel für Nicht-MDM-verwaltete Geräte genutzt und müssen manuell auf jedes Gerät angewendet werden. Lesen Sie Informationen zum Erstellen von [benutzerdefinierten Bereitstellungspaketen für HoloLens](hololens-provisioning.md).

## <a name="configurations"></a>Konfigurationen

### <a name="common-device-restrictions"></a>Allgemeine Geräteeinschränkungen

Einige Geräteeinschränkungen sind so einfach und deaktivieren eine Funktionalität oder Verbindung mit dem Gerät. Weitere Informationen zu diesen Finden Sie unter [Allgemeine Geräteeinschränkungen.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Kioskmodi

Verwenden Sie den Kioskmodus, um zu steuern, welche Identitäten standardmäßig Zugriff auf welche Apps haben. Kiosks können für eine einzelne App oder mehrere App-Benutzeroberflächen verwendet werden. Kioskkonfigurationen reichen von einer einzelnen App für alle Benutzer des Geräts bis hin zu unterschiedlichen Apps für verschiedene Gruppen. Der Kioskmodus hindert "zulässige Apps" nicht daran, andere Apps zu starten, und war dafür nicht vorgesehen. Weitere Informationen [finden Sie unter Kioskmodi und deren Verwendung.](hololens-kiosk.md)

### <a name="settings-page-visibility"></a>Einstellungen Seitensichtbarkeit

Verwenden Sie Einstellungen App-Richtlinie, um zu steuern, welche Identitäten standardmäßig Zugriff auf Einstellungen haben. Mit dieser Richtlinie kann die Einstellungen-App so konfiguriert werden, dass entweder nur die ausgewählten Seiten angezeigt oder alle ausgewählten Seiten ausgeblendet werden. [Erfahren Sie, wie Sie die verfügbaren Seiten konfigurieren.](settings-uri-list.md)

Dieses Feature ist derzeit nur in [Windows Insider-Builds](hololens-insider.md)verfügbar. Stellen Sie sicher, dass geräte, für die Sie dieses Feature verwenden möchten, build 19041.1349+ verwendet werden.

### <a name="wdac"></a>WDAC

Verwenden Sie die WDAC-Konfiguration, um zu steuern, welche Apps/Prozesse gestartet werden dürfen bzw. nicht, unabhängig davon, ob sich das System im Kioskmodus befindet oder nicht.
[Weitere Informationen finden Sie in unserer Übersicht für WDAC.](windows-defender-application-control-wdac.md)
