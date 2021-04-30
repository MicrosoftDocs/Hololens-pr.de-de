---
title: Konfigurieren von CSPs und Geräteverwaltung – Übersicht
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
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309718"
---
# <a name="configure-csps-and-device-management-overview"></a>Konfigurieren von CSPs und Geräteverwaltung – Übersicht

IT-Administratoren können Richtlinieneinstellungen für HoloLens 2 definieren und implementieren. Die verwendeten Konfigurationseinstellungen sind abhängig vom Bereitstellungsszenario. Dabei bieten unternehmenseigene Geräte die umfassendsten Kontrollmöglichkeiten für die IT. In Windows 10 sind Konfigurationsdienstanbieter (Configuration Service Providers, CSP) eine Schnittstelle zum Lesen, Festlegen, Ändern oder Löschen von Konfigurationseinstellungen auf dem Gerät. Diese Einstellungen sind mit Registrierungsschlüsseln oder Dateien verknüpft. Einige Konfigurationsdienstanbieter unterstützen das WAP-Format, einige unterstützen SyncML und andere beides.

Weitere Informationen zu Windows 10 Holographic-Geräteverwaltungs-CSPs finden Sie in der vollständigen Liste der [in HoloLens-Geräten unterstützten CSPs.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)
IT-Administratoren können den Richtlinien-CSP auch auf Geräten verwalten. Die vollständige Liste der [Richtlinien-CSPs,](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)die von HoloLens 2 unterstützt werden.

## <a name="configuration-methods"></a>Konfigurationsmethoden

### <a name="configure-with-mdm"></a>Konfigurieren mit MDM

CSPs und Richtlinien können problemlos auf jedem persönlichen oder Unternehmensgerät verwaltet werden, das in einem MDM-System registriert ist. Sobald ein Gerät in Ihrer MDM-Lösung registriert ist, können Sie dieses Gerät oder eine Gruppe von Geräten mithilfe von Gerätekonfigurationen verwalten. Erfahren Sie mehr über das [Verwalten Ihrer HoloLens-Geräte über MDM.](hololens-mdm-configure.md)

### <a name="configure-with-provisioning-packages"></a>Konfigurieren mit Bereitstellungspaketen

HoloLens 2 unterstützt auch das Festlegen eines begrenzten Satzes von CSP-Konfigurationen für HoloLens 2 Geräte über benutzerdefinierte Bereitstellungspakete. Bereitstellungspakete werden in der Regel für Nicht-MDM-verwaltete Geräte genutzt und müssen manuell auf jedes Gerät angewendet werden. Lesen Sie Informationen zum Erstellen von [benutzerdefinierten Bereitstellungspaketen für HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="configurations"></a>Configurations

### <a name="common-device-restrictions"></a>Allgemeine Geräteeinschränkungen

Einige Geräteeinschränkungen sind so einfach und deaktivieren eine Funktionalität oder Verbindung mit dem Gerät. Weitere Informationen zu diesen Finden Sie unter [Allgemeine Geräteeinschränkungen.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Kioskmodi

Verwenden Sie den Kioskmodus, um zu steuern, welche Identitäten standardmäßig Zugriff auf welche Apps haben. Kioske können für eine einzelne App oder mehrere Benutzeroberflächen der App verwendet werden. Kioskkonfigurationen reichen von einer einzelnen App für jeden, der das Gerät verwendet, bis zu einer anderen Auswahl von Apps für verschiedene Gruppen. Der Kioskmodus stoppt nicht, dass "zulässige Apps" andere Apps starten, und war nie vorgesehen. Weitere Informationen finden [Sie unter Kioskmodi und deren Verwendung.](hololens-kiosk.md)

### <a name="settings-page-visibility"></a>Sichtbarkeit der Einstellungsseite

Verwenden Sie die App-Richtlinie Einstellungen, um zu steuern, welche Identitäten standardmäßig Zugriff auf Einstellungen haben. Mit dieser Richtlinie kann die App Einstellungen so konfiguriert werden, dass entweder nur die ausgewählten Seiten angezeigt oder alle ausgewählten Seiten ausblendet werden. [Erfahren Sie, wie Sie die verfügbaren Seiten konfigurieren.](settings-uri-list.md)

Dieses Feature ist derzeit nur in Windows-Insider [verfügbar.](hololens-insider.md) Stellen Sie sicher, dass Geräte, für die Sie dieses Feature verwenden möchten, auf Build 19041.1349 und mehr verfügbar sind.

### <a name="wdac"></a>WDAC

Verwenden Sie die WDAC-Konfiguration, um zu steuern, welche Apps/Prozesse gestartet werden dürfen, unabhängig davon, ob sich das System im Kioskmodus befindet oder nicht.
[Weitere Informationen finden Sie in unserer Übersicht über WDAC.](windows-defender-application-control-wdac.md)
