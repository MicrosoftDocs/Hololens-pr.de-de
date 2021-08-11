---
title: 'Häufige Szenarien: Sichere Offline-HoloLens 2'
description: Erfahren Sie, wie Sie ein Szenario mit sicherer Offlinebereitstellung und App-Bereitstellung mit Bereitstellung für HoloLens Geräte einrichten.
keywords: HoloLens, Verwaltung, offline, offline sicher
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 1da19665dd3298ece8b007e86695bfe9f298f2347a0e7e058cbd30f0ad5d35c3
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664518"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Häufige Szenarien: Sichere Offline-HoloLens 2

## <a name="overview"></a>Überblick

Dieser Leitfaden enthält Anleitungen zum Anwenden eines Beispielbereitstellungspakets, das eine HoloLens 2 für die Verwendung in sicheren Umgebungen mit den folgenden Einschränkungen sperrt:

-   Deaktivieren Sie WLAN.
-   Deaktivieren Sie BlueTooth.
-   Deaktivieren Sie Mikrofone.
-   Verhindert das Hinzufügen oder Entfernen von Bereitstellungspaketen.
-   Benutzer können keine der oben genannten eingeschränkten Komponenten aktivieren.

[![Sicheres Offlineszenario ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Vorbereiten

Windows 10 PC-Setup
1. [Laden Sie die neueste HoloLens 2 Betriebssystemdatei](https://aka.ms/hololens2download) direkt auf einen PC herunter. 
   1. Unterstützung für diese Konfiguration ist in Build 19041.1117 und höher enthalten.
1. Laden Sie das Advanced Recovery Companion(ARC)-Tool [von der Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) auf Ihren PC herunter, oder installieren Sie es.
1. Laden Sie das neueste [tool Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) von der Microsoft Store auf Ihren PC herunter, und installieren Sie es.
1. [Laden Sie den Ordner OfflineSecureHL2_Sample mit den Projektdateien](https://aka.ms/HoloLensDocs-SecureOfflineSample) herunter, um das PPKG zu erstellen.
1. Bereiten Sie Ihre [Offline-Branchenanwendung für die PPKG-Bereitstellung](app-deploy-provisioning-package.md)vor. 


## <a name="configure"></a>Konfigurieren

Erstellen eines Pakets für die sichere Konfigurationsbereitstellung

1. Starten Sie das WCD-Tool auf Ihrem PC.
1. Wählen Sie **Datei -> Projekt öffnen** aus.
  1. Navigieren Sie zum Speicherort des zuvor gespeicherten Ordners OfflineSecureHL2_Sample, und wählen Sie Folgendes aus: OfflineSecureHL2_Sample.icdproj.xml
1. Das Projekt sollte geöffnet werden, und Sie sollten nun über eine Liste der verfügbaren Anpassungen verfügen:

   > [!div class="mx-imgBorder"]
   > ![Screenshot des in WCD geöffneten Konfigurationspakets](images/offline-secure-sample-wcd.png)

   In diesem Bereitstellungspaket festgelegte Konfigurationen:
   
   |     Element                                                |     Einstellung                       |     BESCHREIBUNG                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Konten/Benutzer                                    |     Local User Name & Password    |     Für diese Offlinegeräte müssen ein einzelner Benutzername und ein Kennwort festgelegt und von allen Benutzern des Geräts freigegeben werden.          |
   |     Erste Erfahrung/HoloLens/SkipCalibration       |     True                          |     Überspringt die Kalibrierung nur während der ersten Geräteeinrichtung                                                                             |
   |     Erste Erfahrung/HoloLens/SkipTraining          |     True                          |     Überspringt das Gerätetraining während der ersten Geräteeinrichtung.                                                                              |
   |     Erste Erfahrung/HoloLens/WLAN                  |     True                          |     Überspringt Wi-Fi Konfiguration während der ersten Geräteeinrichtung.                                                                                 |
   |     Richtlinien/Konnektivität/AllowBluetooth                |     No                            |     Deaktiviert Bluetooth                                                                                                             |
   |     Policies/Experience/AllowCororpora                    |     No                            |     Deaktiviert Cortana (um potenzielle Probleme zu beseitigen, da die Mikrofone deaktiviert sind)                                          |
   |     Richtlinien/MixedReality/MicrophoneDisabled            |     Yes                           |     Deaktiviert das Mikrofon.                                                                                                            |
   |     Richtlinien/Datenschutz/LetAppsAccessLocation              |     Verweigern erzwingen                    |     Verhindert, dass Apps versuchen, auf Standortdaten zuzugreifen (um potenzielle Probleme zu beseitigen, da die Standortnachverfolgung deaktiviert ist)    |
   |     Richtlinien/Datenschutz/LetAppsAccessMicrophone            |     Verweigern erzwingen                    |     Verhindert, dass Apps versuchen, auf Mikrofone zuzugreifen (um potenzielle Probleme zu beseitigen, da die Mikrofone deaktiviert sind)           |
   |     Policies/Security/AllowAddProvisioningPackage       |     No                            |     Verhindert das Hinzufügen von Bereitstellungspaketen, die möglicherweise versuchen, gesperrte Richtlinien außer Kraft zu setzen.                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     No                            |     Verhindert, dass dieses gesperrte Bereitstellungspaket entfernt wird.                                                           |
   |     Richtlinien/System/AllowLocation                       |     No                            |     Verhindert, dass das Gerät versucht, Standortdaten nachzuverfolgen.                                                                        |
   |     Richtlinien/WLAN/AllowWiFi                             |     No                            |     Deaktiviert Wi-Fi                                                                                                                 |

1. Wählen Sie unter Runtime Einstellungen die Option **Konten/Benutzer/Benutzername: Holo/Kennwort** aus.

   Notieren Sie sich das Kennwort, und setzen Sie es bei Bedarf zurück.

1. Navigieren Sie zu UniversalAppInstall/UserContextApp, und konfigurieren Sie [die BRANCHEN-App, die](app-deploy-provisioning-package.md) Sie auf diesen Geräten bereitstellen möchten.

   > [!div class="mx-imgBorder"]
   > ![Screenshot: Hinzufügen Ihrer App in WCD](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Wählen Sie nach Abschluss des Vorgangs die Schaltfläche "Exportieren" aus, und folgen Sie allen Aufforderungen, bis Das Bereitstellungspaket erstellt wurde.

   > [!div class="mx-imgBorder"]
   > ![Screenshot: Schaltfläche "Exportieren" für dieses Paket in WCD](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Bereitstellen

1. Verbinden hl2 über ein USB-Kabel an Ihren Windows 10-PC.
1. Starten Sie das ARC-Tool, und wählen Sie **HoloLens 2**

   ![„Clean Reflash“ für HoloLens 2 – Startbildschirm](images/ARC2.png)

1. Wählen Sie auf dem nächsten Bildschirm **Manuelle Paketauswahl** aus.

   ![HoloLens 2 ARC-Infobildschirm](images/arc_device_info.png)

1. Navigieren Sie zur zuvor heruntergeladenen FFU-Datei, und wählen Sie **Öffnen** aus.
1. Wählen Sie auf der Seite Warnung die Option **Weiter** aus.

   ![HoloLens 2 ARC-Warnbildschirm](images/arc_warning.png)

1. Warten Sie, bis das ARC-Tool die Installation HoloLens 2 Betriebssystems abgeschlossen hat.
1. Nachdem das Gerät die Installation abgeschlossen und die Sicherung gestartet hat, navigieren Sie von Ihrem PC zum Datei-Explorer, und kopieren Sie die zuvor gespeicherte PPKG-Datei in den Geräteordner.

   > [!div class="mx-imgBorder"]
   > ![PPKG-Datei auf dem PC im Datei-Explorer-Fenster.](images/offline-secure-file-explorer.png)

1. Klicken Sie auf dem HoloLens 2 auf die folgende Schaltflächenkombination, um das Bereitstellungspaket auszuführen: Tippen Sie gleichzeitig auf **"Lautstärke herunterfahren"** und **"Netzschalter".**
1. Sie werden aufgefordert, das Bereitstellungspaket anzuwenden, und wählen **Sie Bestätigen** aus.
1. Wählen Sie nach Abschluss des Bereitstellungspakets **OK** aus.
1. Sie sollten dann aufgefordert werden, sich mit dem freigegebenen lokalen Konto und Kennwort beim Gerät anzumelden.

## <a name="maintain"></a>Verwalten

Bei dieser Konfiguration wird empfohlen, den oben genannten Prozess neu zu starten und das Gerät mit dem ARC-Tool neu zu schräglegen und eine neue PPKG-Datei anzuwenden, um Updates für das Betriebssystem und/oder die Anwendungen vorzunehmen.
