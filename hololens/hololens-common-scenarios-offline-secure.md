---
title: Häufige Szenarien – Offline Secure HoloLens 2
description: Erfahren Sie, wie Sie ein Szenario für eine sichere Offlinebereitstellung und eine App mit Bereitstellung für HoloLens-Geräte einrichten.
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
ms.openlocfilehash: 03003995f1e63708652955e6217e506d53555c1b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283416"
---
# Häufige Szenarien – Offline Secure HoloLens 2

## Übersicht

Dieses Handbuch enthält Anleitungen zum Anwenden eines Beispielbereitstellungspakets, das eine HoloLens 2 für die Verwendung in sicheren Umgebungen mit den folgenden Einschränkungen sperrt:
-   Deaktivieren Sie WLAN.
-   Deaktivieren Sie BlueTooth.
-   Deaktivieren Sie Mikrofone.
-   Verhindert das Hinzufügen oder Entfernen von Bereitstellungspaketen.
-   Kein Benutzer kann eine der oben genannten eingeschränkten Komponenten aktivieren.

## Vorbereiten

Windows 10-PC-Setup
1. [Laden Sie die neueste HoloLens 2-Betriebssystemdatei](https://aka.ms/hololens2download) direkt auf einen PC herunter. 
   1. Unterstützung für diese Konfiguration ist in Build 19041.1117 und höher enthalten.
1. Herunterladen/Installieren des Advanced Recovery Companion(ARC)-Tools [aus dem Microsoft Store auf](https://www.microsoft.com/store/productId/9P74Z35SFRS8) Ihren PC
1. Laden Sie das neueste [Windows Configuration Designer (WCD)-Tool aus](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) dem Microsoft Store auf Ihren PC herunter bzw. installieren Sie es.
1. [Laden Sie den OfflineSecureHL2_Sample mit den Projektdateien herunter,](https://aka.ms/HoloLensDocs-SecureOfflineSample) um die PPKG zu erstellen.
1. Bereiten Sie Ihre [Offlineanwendung für die Bereitstellung von PPKG vor.](app-deploy-provisioning-package.md) 


## Konfigurieren

Erstellen eines Bereitstellungspakets für die sichere Konfiguration

1. Starten Sie das Tool WCD auf Ihrem PC.
1. Select **File -> Open project**.
  1. Navigieren Sie zum Speicherort des zuvor gespeicherten ordners OfflineSecureHL2_Sample, und wählen Sie: OfflineSecureHL2_Sample.icdproj.xml
1. Das Projekt sollte geöffnet werden, und Sie sollten nun über eine Liste der verfügbaren Anpassungen verfügen: 

   > [!div class="mx-imgBorder"]
   > ![Screenshot des in WCD geöffneten Konfigurationspakets](images/offline-secure-sample-wcd.png)

Konfigurationen, die in diesem Bereitstellungspaket festgelegt sind:

|     Element                                                |     Einstellung                       |     Beschreibung                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     Konten/Benutzer                                    |     Lokales Kennwort für & Benutzernamen    |     Für diese Offlinegeräte müssen ein einzelner Benutzername und ein Kennwort festgelegt und von allen Benutzern des Geräts freigegeben werden.          |
|     First Experience / HoloLens / SkipCalibration       |     Wahr                          |     Überspringt die Kalibrierung nur während der ersteinrichtung des Geräts                                                                             |
|     First Experience / HoloLens / SkipTraining          |     Wahr                          |     Überspringt Geräteschulungen während der ersteinrichtung des Geräts                                                                              |
|     First Experience / HoloLens / WiFi                  |     Wahr                          |     Überspringt Wi-Fi Konfiguration während der ersteinrichtung des Geräts                                                                                 |
|     Policies/Connectivity/AllowBluetooth                |     Nein                            |     Deaktiviert Bluetooth                                                                                                             |
|     Richtlinien/Erfahrung/AllowCortana                    |     Nein                            |     Deaktiviert Cortana (um potenzielle Probleme zu vermeiden, da die Mikrofone deaktiviert sind)                                          |
|     Policies/MixedReality/MicrophoneDisabled            |     Ja                           |     Deaktiviert mikrofon                                                                                                            |
|     Richtlinien/Datenschutz/LetAppsAccessLocation              |     Verweigern erzwingen                    |     Verhindert, dass Apps versuchen, auf Standortdaten zu zugreifen (um potenzielle Probleme zu beseitigen, da die Standortverfolgung deaktiviert ist)    |
|     Richtlinien/Datenschutz/LetAppsAccessMicrophone            |     Verweigern erzwingen                    |     Verhindert, dass Apps versuchen, auf Mikrofone zu zugreifen (um potenzielle Probleme zu beseitigen, da die Mikrofone deaktiviert sind)           |
|     Richtlinien/Sicherheit/AllowAddProvisioningPackage       |     Nein                            |     Verhindert das Hinzufügen von Bereitstellungspaketen, die möglicherweise versuchen, gesperrte Richtlinien außer Kraft zu setzen.                         |
|     Richtlinien/Sicherheit/AllowRemoveProvisioningPackage    |     Nein                            |     Verhindert, dass dieses gesperrte Bereitstellungspaket entfernt wird.                                                           |
|     Richtlinien/System/AllowLocation                       |     Nein                            |     Verhindert, dass das Gerät versucht, Standortdaten nachverfolgt.                                                                        |
|     Richtlinien/WIFi/AllowWiFi                             |     Nein                            |     Deaktiviert Wi-Fi                                                                                                                 |

4. Wählen Sie unter Laufzeiteinstellungen **"Konten/Benutzer/Benutzername: Holo/Kennwort" aus.** 
    - Notieren Sie sich das Kennwort, und setzen Sie es bei Bedarf zurück.
5. Navigieren Sie zu "UniversalAppInstall/UserContextApp", und konfigurieren Sie die [Branchen-App,](app-deploy-provisioning-package.md) die Sie auf diesen Geräten bereitstellen möchten.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp.png)

6. Wählen Sie nach Abschluss des Vorgangs die Schaltfläche "Exportieren" aus, und befolgen Sie alle Eingabeaufforderungen, bis das Bereitstellungspaket erstellt wird.

   > [!div class="mx-imgBorder"]
   > ![Screenshot der Schaltfläche "Exportieren" für dieses Paket in WCD.](images/offline-secure-sample-wcd-export.png)


## Bereitstellen

1. Schließen Sie das HL2 über ein #A0 an Ihren Windows 10-PC an.
1. Starten Sie das ARC-Tool, und wählen **Sie HoloLens 2 aus.**

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. Wählen Sie auf dem nächsten Bildschirm manuelle **Paketauswahl aus.**
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. Navigieren Sie zur zuvor heruntergeladenen FFU-Datei, und wählen Sie **"Öffnen" aus.**
1. Wählen Sie auf der Warnseite **"Weiter" aus.**

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. Warten Sie, bis das Tool ARC die Installation des HoloLens 2-Betriebssystems abgeschlossen hat.
1. Sobald das Gerät die Installation abgeschlossen und die Installation gestartet hat, navigieren Sie vom PC zum Datei-Explorer, und kopieren Sie die zuvor gespeicherte PPKG-Datei in den Geräteordner.

   > [!div class="mx-imgBorder"]
   > ![DATEI "PPKG" auf dem PC im Fenster "Datei-Explorer".](images/offline-secure-file-explorer.png)

1. Drücken Sie auf HoloLens 2 die folgende Tastenkombination, **** um das **** Bereitstellungspaket ausführen zu können: Tippen Sie gleichzeitig auf "Lautstärke" und "Netzschalter".
1. Sie werden aufgefordert, das Bereitstellungspaket anzuwenden. Wählen Sie **"Bestätigen" aus.**
1. Sobald das Bereitstellungspaket abgeschlossen ist, wählen Sie **OK aus.**
1. Sie sollten dann aufgefordert werden, sich mit dem freigegebenen lokalen Konto und Kennwort beim Gerät zu anmelden.

## Warten

Bei dieser Konfiguration wird empfohlen, den obigen Prozess neu zu starten und das Gerät mit dem Tool ARC neu zu schrägen und eine neue PPKG anzuwenden, um Aktualisierungen des Betriebssystems und/oder der Anwendung(en) zu erstellen. 

