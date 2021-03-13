---
title: Gängige Szenarien – Offline sichere HoloLens2
description: Erfahren Sie, wie Sie ein Szenario für sichere Offlinebereitstellung und App-Bereitstellung mit Bereitstellung für HoloLens-Geräte einrichten.
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
ms.openlocfilehash: 7eb084d3de222581fd2b97eaa1c1e2812310810c
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407582"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Gängige Szenarien – Offline sichere HoloLens2

## <a name="overview"></a>Übersicht

Dieses Handbuch enthält Anleitungen zum Anwenden eines Beispielbereitstellungspakets, das eine HoloLens 2 für die Verwendung in sicheren Umgebungen mit den folgenden Einschränkungen sperrt:

-   Deaktivieren Sie WLAN.
-   Deaktivieren Sie BlueTooth.
-   Deaktivieren Sie Mikrofone.
-   Verhindert das Hinzufügen oder Entfernen von Bereitstellungspaketen.
-   Kein Benutzer kann eine der oben genannten eingeschränkten Komponenten aktivieren.

## <a name="prepare"></a>Vorbereiten

Windows 10 PC Setup
1. [Laden Sie die neueste HoloLens 2-Betriebssystemdatei](https://aka.ms/hololens2download) direkt auf einen PC herunter. 
   1. Unterstützung für diese Konfiguration ist in Build 19041.1117 und höher enthalten.
1. Herunterladen/Installieren des Advanced Recovery Companion(ARC)-Tools [aus dem Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) auf Ihren PC
1. Laden Sie das neueste [Windows Configuration Designer (WCD)-Tool aus](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) dem Microsoft Store auf Ihren PC herunter.
1. [Laden Sie den OfflineSecureHL2_Sample mit den Projektdateien herunter, um](https://aka.ms/HoloLensDocs-SecureOfflineSample) das PPKG zu erstellen.
1. Bereiten Sie Ihre [Offline-Line-of-Business-Anwendung für die PPKG-Bereitstellung vor.](app-deploy-provisioning-package.md) 


## <a name="configure"></a>Konfigurieren

Erstellen eines Pakets für die Bereitstellung sicherer Konfigurationen

1. Starten Sie das WCD-Tool auf Ihrem PC.
1. Wählen **Sie Datei -> Projekt öffnen aus.**
  1. Navigieren Sie zum Speicherort des zuvor gespeicherten OfflineSecureHL2_Sample, und wählen Sie: OfflineSecureHL2_Sample.icdproj.xml
1. Das Projekt sollte geöffnet werden, und Sie sollten nun über eine Liste der verfügbaren Anpassungen verfügen:

   > [!div class="mx-imgBorder"]
   > ![Screenshot des in WCD geöffneten Konfigurationspakets](images/offline-secure-sample-wcd.png)

   In diesem Bereitstellungspaket festgelegte Konfigurationen:
   
   |     Element                                                |     Einstellung                       |     Beschreibung                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Konten /Benutzer                                    |     Local User Name & Password    |     Für diese Offlinegeräte müssen ein einzelner Benutzername und ein kennwort für alle Benutzer des Geräts festgelegt und freigegeben werden.          |
   |     Erste Erfahrung / HoloLens / SkipCalibration       |     Wahr                          |     Überspringt die Kalibrierung nur während der ersteinrichtung des Geräts                                                                             |
   |     First Experience / HoloLens / SkipTraining          |     Wahr                          |     Überspringt Geräteschulungen während der ersten Geräteeinrichtung                                                                              |
   |     First Experience / HoloLens / WiFi                  |     Wahr                          |     Überspringt Wi-Fi Konfiguration während der ersten Geräteeinrichtung                                                                                 |
   |     Richtlinien/Konnektivität/AllowBluetooth                |     Nein                            |     Deaktiviert Bluetooth                                                                                                             |
   |     Richtlinien/Erfahrung/AllowCortana                    |     Nein                            |     Deaktiviert Cortana (um potenzielle Probleme zu vermeiden, da die Mikrofone deaktiviert sind)                                          |
   |     Policies/MixedReality/MicrophoneDisabled            |     Ja                           |     Deaktiviert Mikrofon                                                                                                            |
   |     Richtlinien/Datenschutz/LetAppsAccessLocation              |     Erzwingen des Verweigerns                    |     Verhindert, dass Apps versuchen, auf Standortdaten zu zugreifen (um potenzielle Probleme zu beseitigen, da die Standortverfolgung deaktiviert ist)    |
   |     Richtlinien/Datenschutz/LetAppsAccessMicrophone            |     Erzwingen des Verweigerns                    |     Verhindert, dass Apps versuchen, auf Mikrofone zu zugreifen (um potenzielle Probleme zu beheben, da die Mikrofone deaktiviert sind)           |
   |     Richtlinien/Sicherheit/AllowAddProvisioningPackage       |     Nein                            |     Verhindert das Hinzufügen von Bereitstellungspaketen, die möglicherweise versuchen, gesperrte Richtlinien außer Kraft zu setzen.                         |
   |     Richtlinien/Sicherheit/AllowRemoveProvisioningPackage    |     Nein                            |     Verhindert, dass dieses gesperrte Bereitstellungspaket entfernt wird.                                                           |
   |     Policies/System/AllowLocation                       |     Nein                            |     Verhindert, dass das Gerät versucht, Standortdaten nachverfolgt zu werden.                                                                        |
   |     Policies/WiFi/AllowWiFi                             |     Nein                            |     Deaktiviert Wi-Fi                                                                                                                 |

1. Wählen Sie unter Laufzeiteinstellungen **Konten / Benutzer / Benutzername: Holo / Kennwort aus.**

   Notieren Sie sich das Kennwort, und setzen Sie es bei Bedarf zurück.

1. Navigieren Sie zu UniversalAppInstall /UserContextApp, und konfigurieren Sie die [Branchen-App,](app-deploy-provisioning-package.md) die Sie auf diesen Geräten bereitstellen möchten.

   > [!div class="mx-imgBorder"]
   > ![Screenshot des Orts, an dem Ihre App in WCD hinzugefügt werden soll.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Wählen Sie nach Abschluss die Schaltfläche "Exportieren" aus, und folgen Sie allen Eingabeaufforderungen, bis Das Bereitstellungspaket erstellt wurde.

   > [!div class="mx-imgBorder"]
   > ![Screenshot der Schaltfläche Exportieren für dieses Paket in WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Bereitstellen

1. Verbinden Sie das HL2 über ein #A0 mit Ihrem Windows 10-PC.
1. Starten Sie das ARC-Tool, und wählen **Sie HoloLens 2 aus.**

   ![„Clean Reflash“ für HoloLens 2 – Startbildschirm](images/ARC2.png)

1. Wählen Sie auf dem nächsten Bildschirm **Manuelle Paketauswahl aus.**

   ![HoloLens 2 ARC-Infobildschirm](images/arc_device_info.png)

1. Navigieren Sie zur zuvor heruntergeladenen FFU-Datei, und wählen Sie **Öffnen aus.**
1. Wählen Sie auf der Seite Warnung die Option **Weiter aus.**

   ![HoloLens 2 ARC-Warnbildschirm](images/arc_warning.png)

1. Warten Sie, bis das ARC-Tool die HoloLens 2-Betriebssysteminstallation abgeschlossen hat.
1. Nachdem das Gerät die Installation abgeschlossen und die Sicherungskopie gestartet hat, navigieren Sie von Ihrem PC zum Datei-Explorer, und kopieren Sie die zuvor gespeicherte PPKG-Datei in den Geräteordner.

   > [!div class="mx-imgBorder"]
   > ![PPKG-Datei auf dem PC im Datei-Explorer-Fenster.](images/offline-secure-file-explorer.png)

1. Drücken Sie in HoloLens 2 die folgende Tastenkombination, um das Bereitstellungspaket ausführen zu können: Tippen Sie gleichzeitig auf **Volume Down** und **Power Button.**
1. Sie werden aufgefordert, das Bereitstellungspaket anzuwenden, wählen Sie **Bestätigen aus.**
1. Sobald das Bereitstellungspaket abgeschlossen ist, wählen Sie **OK aus.**
1. Sie sollten dann aufgefordert werden, sich mit dem freigegebenen lokalen Konto und Kennwort beim Gerät zu registrieren.

## <a name="maintain"></a>Warten

Bei dieser Konfiguration wird empfohlen, den oben beschriebenen Prozess neu zu starten und das Gerät mit dem ARC-Tool neu zu schrägen und ein neues PPKG anzuwenden, um Updates für das Betriebssystem und/oder die Anwendung(en) zu erstellen.
