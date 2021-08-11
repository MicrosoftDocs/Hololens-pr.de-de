---
title: Übersicht über CSPs und Geräteverwaltung konfigurieren
description: Erfahren Sie, wie Sie CSPs, Richtlinien und die Geräteverwaltung mithilfe von Mobile Geräteverwaltung und Bereitstellungspaketen konfigurieren.
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
ms.openlocfilehash: ed28033f10f7a6d0e826775e95d040d0cac7f9e9c6266acd6975d3532f6d8067
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664255"
---
# <a name="configure-csps-and-device-management-overview"></a>Übersicht über CSPs und Geräteverwaltung konfigurieren

IT-Administratoren können Richtlinieneinstellungen für die HoloLens 2. Die verwendeten Konfigurationseinstellungen sind abhängig vom Bereitstellungsszenario. Dabei bieten unternehmenseigene Geräte die umfassendsten Kontrollmöglichkeiten für die IT. In Windows 10 konfigurationsdienstanbieter (Configuration Service Providers, CSP) eine Schnittstelle zum Lesen, Festlegen, Ändern oder Löschen von Konfigurationseinstellungen auf dem Gerät. Diese Einstellungen sind mit Registrierungsschlüsseln oder Dateien verknüpft. Einige Konfigurationsdienstanbieter unterstützen das WAP-Format, einige unterstützen SyncML und einige unterstützen beides.

Weitere Informationen zu den Windows 10 Holographic-Verwaltungs-CSPs finden Sie in der vollständigen Liste der [CSPs,](/windows/client-management/mdm/configuration-service-provider-reference#hololens)die in HoloLens unterstützt werden.
IT-Administratoren können den Richtlinien-CSP auch auf Geräten verwalten. Eine vollständige Liste der richtlinienverwaltenden [CSPs,](/windows/client-management/mdm/policy-csps-supported-by-hololens2)die von HoloLens 2.

## <a name="configuration-methods"></a>Konfigurationsmethoden

### <a name="configure-with-mdm"></a>Konfigurieren mit MDM

CSPs und Richtlinien können problemlos auf jedem persönlichen oder Unternehmensgerät verwaltet werden, das in einem MDM-System registriert ist. Sobald ein Gerät in Ihrer MDM-Lösung registriert ist, können Sie dieses Gerät oder eine Gruppe von Geräten mithilfe von Gerätekonfigurationen verwalten. Erfahren Sie mehr darüber, wie [Sie Ihre HoloLens-Geräte über MDM verwalten.](hololens-mdm-configure.md)

### <a name="configure-with-provisioning-packages"></a>Konfigurieren mit Bereitstellungspaketen

HoloLens 2 unterstützt auch das Festlegen einer begrenzten Anzahl von CSP-Konfigurationen für HoloLens 2-Geräte über benutzerdefinierte Bereitstellungspakete. Bereitstellungspakete werden in der Regel für Nicht-MDM-verwaltete Geräte genutzt und müssen manuell auf jedes Gerät angewendet werden. Lesen Sie Informationen zum Erstellen [benutzerdefinierter Bereitstellungspakete für HoloLens](hololens-provisioning.md).

## <a name="configurations"></a>Configurations

### <a name="common-device-restrictions"></a>Allgemeine Geräteeinschränkungen

Einige Geräteeinschränkungen sind einfach und deaktivieren eine Funktion oder Verbindung mit dem Gerät. Weitere Informationen zu diesen Einschränkungen finden Sie [unter Allgemeine Geräteeinschränkungen.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Kioskmodi

Verwenden Sie den Kioskmodus, um zu steuern, welche Identitäten standardmäßig Zugriff auf welche Apps haben. Kioske können für eine einzelne App oder mehrere Benutzeroberflächen der App verwendet werden. Kioskkonfigurationen reichen von einer einzelnen App für jeden, der das Gerät verwendet, bis zu einer anderen Auswahl von Apps für verschiedene Gruppen. Der Kioskmodus stoppt nicht, dass "zulässige Apps" andere Apps starten, und war nie vorgesehen. Weitere Informationen finden [Sie unter Kioskmodi und deren Verwendung.](hololens-kiosk.md)

### <a name="settings-page-visibility"></a>Einstellungen Seitensichtbarkeit

Verwenden Einstellungen App-Richtlinie, um zu steuern, welche Identitäten standardmäßig Zugriff auf Einstellungen haben. Mit dieser Richtlinie kann die Einstellungen-App so konfiguriert werden, dass entweder nur die ausgewählten Seiten angezeigt oder alle ausgewählten Seiten ausblendet werden. [Erfahren Sie, wie Sie die verfügbaren Seiten konfigurieren.](settings-uri-list.md)

Dieses Feature ist derzeit nur in [Insider-builds Windows verfügbar.](hololens-insider.md) Stellen Sie sicher, dass Geräte, für die Sie dieses Feature verwenden möchten, auf Build 19041.1349 und mehr verfügbar sind.

### <a name="wdac"></a>WDAC

Verwenden Sie die WDAC-Konfiguration, um zu steuern, welche Apps/Prozesse gestartet werden dürfen, unabhängig davon, ob sich das System im Kioskmodus befindet oder nicht.
[Weitere Informationen finden Sie in unserer Übersicht über WDAC.](windows-defender-application-control-wdac.md)
