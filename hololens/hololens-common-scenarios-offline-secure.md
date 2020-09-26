---
title: Häufige Szenarien – Offline Secure HoloLens 2
description: Eine Offline sichere Bereitstellung und App-Bereitstellung über die Bereitstellung.
keywords: HoloLens, Verwaltung, offline, Offline sicher
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
ms.openlocfilehash: d53f9ce19b020a866770b756dde6ab97b8331362
ms.sourcegitcommit: e6885d03c980b33dd0bab5c418cbd1892d5ff123
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "11080493"
---
# Häufige Szenarien – Offline Secure HoloLens 2

## Übersicht
Dieses Handbuch enthält Anleitungen zum Anwenden eines Beispiel Bereitstellungspakets, das eine HoloLens 2 für die Verwendung in sicheren Umgebungen mit den folgenden Einschränkungen sperrt:
-   WLAN deaktivieren.
-   Deaktivieren Sie Bluetooth.
-   Mikrofone deaktivieren.
-   Verhindert das Hinzufügen oder Entfernen von Bereitstellungspaketen.
-   Keine der oben genannten eingeschränkten Komponenten kann von Benutzern aktiviert werden.

## Vorbereiten 
Windows 10-PC-Setup
1. [Laden Sie die neueste HoloLens 2-Betriebssystemdatei](https://aka.ms/hololens2download) direkt auf einen PC herunter. 
   1. Die Unterstützung für diese Konfiguration ist in Build 19041,1117 und höher enthalten.
1. Herunterladen/Installieren des Advanced Recovery Companion (ARC)-Tools [aus dem Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) auf Ihren PC
1. Laden Sie das neueste Tool für [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) aus dem Microsoft Store auf Ihren PC herunter, und installieren Sie es.
1. [Laden Sie den OfflineSecureHL2_Sample-Ordner mit den Projektdateien herunter](https://aka.ms/HoloLensDocs-SecureOfflineSample) , um den PPKG zu erstellen.
1. Vorbereiten der Offline [Geschäftsanwendung für die PPKG-Bereitstellung](app-deploy-provisioning-package.md) 


## Konfigurieren
Erstellen eines sicheren Bereitstellungspakets für die Konfiguration

1. Starten Sie das WCD-Tool auf Ihrem PC.
1. Wählen Sie **Datei – > Projekt öffnen**aus.
  1. Navigieren Sie zum Speicherort des zuvor gespeicherten OfflineSecureHL2_Sample Ordners, und wählen Sie Folgendes aus: OfflineSecureHL2_Sample.icdproj.xml
1. Das Projekt sollte geöffnet sein, und Sie sollten nun über eine Liste der verfügbaren Anpassungen verfügen: 

   > [!div class="mx-imgBorder"]
   > ![Screenshot des in WCD geöffneten Konfigurationspakets](images/offline-secure-sample-wcd.png)

In diesem Bereitstellungspaket eingestellte Konfigurationen:

|     Element                                                |     Einstellung                       |     Beschreibung                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     Konten/Benutzer                                    |     Lokaler Benutzer Name & Kennwort    |     Bei diesen Offline Geräten müssen ein einzelner Benutzername und ein Kennwort für alle Benutzer des Geräts eingerichtet und freigegeben werden.          |
|     First Experience/HoloLens/SkipCalibration       |     Wahr                          |     Überspringt die Kalibrierung nur bei der erstmaligen Einrichtung des Geräts                                                                             |
|     First Experience/HoloLens/SkipTraining          |     Wahr                          |     Überspringt die Geräteschulung während des anfänglichen Geräte Setups                                                                              |
|     First Experience/HoloLens/WLAN                  |     Wahr                          |     Überspringt die Wi-Fi-Konfiguration während der ersten Einrichtung des Geräts                                                                                 |
|     Richtlinien/Konnektivität/AllowBluetooth                |     Nein                            |     Deaktiviert Bluetooth                                                                                                             |
|     Richtlinien/Erfahrung/AllowCortana                    |     Nein                            |     Deaktiviert Cortana (um potenzielle Probleme zu eliminieren, da die Mikrofone deaktiviert sind)                                          |
|     Richtlinien/MixedReality/MicrophoneDisabled            |     Ja                           |     Deaktiviert das Mikrofon                                                                                                            |
|     Richtlinien/Datenschutz/LetAppsAccessLocation              |     Verweigern erzwingen                    |     Verhindert, dass apps auf Standortdaten zugreifen können (um potenzielle Probleme zu eliminieren, da die Standortverfolgung deaktiviert ist)    |
|     Richtlinien/Datenschutz/LetAppsAccessMicrophone            |     Verweigern erzwingen                    |     Verhindert, dass apps auf Mikrofone zugreifen können (um potenzielle Probleme zu vermeiden, da die Mikrofone deaktiviert sind)           |
|     Richtlinien/Sicherheit/AllowAddProvisioningPackage       |     Nein                            |     Verhindert, dass alle Bereitstellungspakete hinzugefügt werden, die möglicherweise versuchen, gesperrte Richtlinien zu überschreiben.                         |
|     Richtlinien/Sicherheit/AllowRemoveProvisioningPackage    |     Nein                            |     Verhindert, dass Benutzer dieses gesperrte Bereitstellungspaket entfernen.                                                           |
|     Richtlinien/System-AllowLocation                       |     Nein                            |     Verhindert, dass das Gerät versucht, Standortdaten zu überwachen.                                                                        |
|     Richtlinien/WLAN/AllowWiFi                             |     Nein                            |     Deaktiviert Wi-Fi                                                                                                                 |

4. Wählen Sie unter Laufzeiteinstellungen die Option **Konten/Benutzer/Benutzername: Holo/Kennwort** aus. 
    - Notieren Sie sich das Kennwort und zurücksetzen, falls gewünscht.
5. Navigieren Sie zu UniversalAppInstall/UserContextApp, und [Konfigurieren Sie die Lob-APP, die](app-deploy-provisioning-package.md) Sie auf diesen Geräten bereitstellen werden.

   > [!div class="mx-imgBorder"]
   > ![Screenshot der Stelle, an der Ihre APP in WCD hinzugefügt werden soll.](images/offline-secure-sample-wcd-usercontextapp.png)

6. Wenn Sie den Vorgang abgeschlossen haben, wählen Sie die Schaltfläche "Exportieren" aus, und folgen Sie allen Eingabeaufforderungen, bis Ihr Bereitstellungspaket erstellt wurde.

   > [!div class="mx-imgBorder"]
   > ![Screenshot der Schaltfläche "Exportieren" für dieses Paket in WCD](images/offline-secure-sample-wcd-export.png)


## Bereitstellen
1. Verbinden Sie das HL2 mit Ihrem Windows 10-PC über ein USB-Kabel.
1. Starten des Bogen Tools und Auswählen von **HoloLens 2**

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. Wählen Sie auf dem nächsten Bildschirm **Manuelle Paketauswahl**aus.
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. Navigieren Sie zu der zuvor heruntergeladenen FFU-Datei, und wählen Sie **Öffnen**aus.
1. Klicken Sie auf der Seite Warnung auf **weiter**.

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. Warten Sie, bis das Arc-Tool die HoloLens 2-Betriebssysteminstallation abgeschlossen hat.
1. Nachdem das Gerät die Installation abgeschlossen und die Wiedergabe gestartet hat, navigieren Sie von Ihrem PC zum Datei-Explorer, und kopieren Sie die zuvor gespeicherte PPKG-Datei in den Geräteordner.

   > [!div class="mx-imgBorder"]
   > ![PPKG-Datei auf dem PC im Datei-Explorer-Fenster.](images/offline-secure-file-explorer.png)

1. Drücken Sie auf der HoloLens 2 die folgende Tastenkombination, um das Bereitstellungspaket auszuführen: Tippen Sie auf die Schaltfläche " **Lautstärke** **" und "Netzschalter"** gleichzeitig.
1. Sie werden aufgefordert, das Bereitstellungspaket anzuwenden, wählen Sie **bestätigen** aus.
1. Nachdem das Bereitstellungspaket abgeschlossen ist, wählen Sie **OK**aus.
1. Sie sollten dann aufgefordert werden, sich mit dem freigegebenen lokalen Konto und Kennwort beim Gerät anzumelden.

## Warten
Bei dieser Konfiguration wird empfohlen, den Vorgang oben neu zu starten und das Gerät mit dem Arc-Tool erneut zu blinken und ein neues PPKG anzuwenden, um alle Updates für das Betriebssystem und/oder die Anwendung (en) zu erstellen. 

