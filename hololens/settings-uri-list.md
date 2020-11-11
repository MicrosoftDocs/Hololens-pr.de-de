---
title: Sichtbarkeit von Seiteneinstellungen
description: Liste der von HoloLens unterstützten URIs für PageVisibilityList und Guide
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: HoloLens, HoloLens 2, zugewiesener Zugriff, Kiosk, Einstellungsseite
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8cd336ce64cf7d4549b031a7977f592ca82dd6e4
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163138"
---
# Sichtbarkeit von Seiteneinstellungen

Zu den verwaltbaren Features für HoloLens-Geräte gehört die [Einstellungen/PageVisibilityList-Richtlinie](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist), mit der die in der App „Einstellungen“ angezeigten Seiten eingeschränkt werden können. Die PageVisibilityList ist eine Richtlinie, die es IT-Administratoren ermöglicht, entweder zu verhindern, dass bestimmte Seiten in der Systemeinstellungs-App sichtbar oder zugänglich sind oder Sie können das für alle Seiten tun, außer den angegebenen. 

> [!NOTE]
> Diese Funktion ist nur in [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) für HoloLens 2-Geräte verfügbar. Stellen Sie sicher, dass die Geräte aktualisiert sind, wenn Sie die Funktion verwenden möchten.

Das folgende Beispiel zeigt eine Richtlinie, die nur Zugriff auf die Seiten „Über“ und „Bluetooth“ ermöglichen würde, die jeweils über URI „ms-settings:network-wifi“ und „ms-settings:bluetooth“ verfügen:
- showonly:network-wifi;network-proxy;bluetooth

So legen Sie dies über ein Provsioning-Paket fest: 
1. Während Sie Ihr Paket im Windows Configuration Designer erstellen, navigieren Sie zu **Policies > Settings > PageVisibilityList**.
1. Geben Sie den String **showonly:network-wifi;network-proxy;bluetooth**ein.
1. Exportieren Sie Ihr Provsioning-Paket.
1. Wenden des Paket auf Ihrem Gerät an. Ausführliche Informationen über die Erstellung und Anwendung eines Provsioning-Pakets finden Sie unter [this page](hololens-provisioning.md). 

Dies kann über Intune mit OMA-URI erfolgen.
1. Verwenden Sie eine **benutzerdefinierte Richtlinie**.
1. Verwenden Sie beim Einstellen des OMA-URI den String: **./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList**
1. Wählen Sie bei der Auswahl der Daten: **String**
1. Wenn Sie den Wert eingeben, verwenden Sie:**showonly:network-wifi;network-proxy;bluetooth**
1. Stellen Sie sicher, dass die benutzerdefinierte Gerätekonfiguration der Gruppe zugeordnet wird, zu der das Gerät gehören soll.
Weitere Informationen zu Intune-Gruppen und Gerätekonfigurationen [finden Sie hier](hololens-mdm-configure.md).

Unabhängig von der gewählten Methode, sollte Ihr Gerät nun die Änderungen erhalten, und die Benutzer erhalten die folgende Einstellungs-App. 

![Screenshot der Nutzungszeit, die in der Einstellungs-App geändert werden](images/hololens-page-visibility-list.jpg)

Um die Einstellungsseiten der App so zu konfigurieren, dass Sie Ihre eigene Auswahl an Seiten ein- oder ausblenden können, werfen Sie bitte einen Blick auf die auf HoloLens verfügbaren Einstellungs-URIs. 

## Einstellungs-URIs

HoloLens-Geräte und Windows 10-Geräte weisen in der App „Einstellungen“ eine unterschiedliche Seitenauswahl auf. Auf dieser Seite finden Sie nur die Einstellungen, die auf HoloLens vorhanden sind. 

### Konten
| Einstellungsseite           | URI                                            |
|-------------------------|------------------------------------------------|
| Anmeldeoptionen         | ms-settings:signinoptions                      |
| Iris-Registrierung       | ms-settings:signinoptions-launchirisenrollment |
| Geschäfts- oder Schulkonto öffnen | ms-settings:workplace                          |

### Geräte
| Einstellungsseite | URI                          |
|---------------|------------------------------|
| Bluetooth     | ms-settings:bluetooth <br> ms-settings:connecteddevices |

### Vertraulichkeit
| Einstellungsseite            | URI                                             |
|--------------------------|-------------------------------------------------|
| Kontoinformationen             | ms-settings:privacy-accountinfo                 |
| App-Diagnose        | ms-settings:privacy-appdiagnostics              |
| Hintergrund-Apps        | ms-settings:privacy-backgroundapps              |
| Benutzerbewegungen           | ms-settings:privacy-backgroundspatialperception |
| Dateisystem              | ms-settings:privacy-broadfilesystemaccess       |
| Calendar                 | ms-settings:privacy-calendar                    |
| Anrufliste             | ms-settings:privacy-callhistory                 |
| Kontakte                 | ms-settings:privacy-contacts                    |
| Weitere Geräte            | ms-settings:privacy-customdevices               |
| Dokumente                | ms-settings:privacy-documents                   |
| E-Mail                    | ms-settings:privacy-email                       |
| Diagnose und Feedback | ms-settings:privacy-feedback                    |
| Pfad                 | ms-settings:privacy-location                    |
| Microsoft-Nachrichten                | ms-settings:privacy-messaging                   |
| Mikrofon               | ms-settings:privacy-microphone                  |
| Benachrichtigungen            | ms-settings:privacy-notifications               |
| Bilder                 | ms-settings:privacy-pictures                    |
| Funkempfang                   | ms-settings:privacy-radios                      |
| Spracherkennung                   | ms-settings:privacy-speech                      |
| Aufgaben                    | ms-settings:privacy-tasks                       |
| Videos                   | ms-settings:privacy-videos                      |
| Stimmaktivierung       | ms-settings:privacy-voiceactivation             |
| Kamera                   | ms-settings:privacy-webcam                      |

### Netzwerk und Internet
| Einstellungsseite | URI                              |
|---------------|----------------------------------|
| WLAN  | ms-settings:network-wifi<br>ms-settings:network-wifisettings<br>ms-settings:network-status<br>ms-settings:wifi-provisioning    |
| VPN   | ms-settings:network-vpn          |
| Proxy | ms-settings:network-proxy        |

### System
| Einstellungsseite      | URI                                |
|--------------------|------------------------------------|
| Gemeinsame Erfahrung | ms-settings:crossdevice            |
| Farben             | ms-settings:colors<br>ms-settings:personalization-colors |
| Benachrichtigungen & Infos  | ms-settings:notifications          |
| Speicher            | ms-settings:storagesense           |

### Zeit & Sprache
| Einstellungsseite | URI                                           |
|---------------|-----------------------------------------------|
| Region        | ms-settings:regionformatting                  |
| Sprache      | ms-settings:regionlanguage<br>ms-settings:regionlanguage-adddisplaylanguage<br>ms-settings:regionlanguage-setdisplaylanguage |

### Update und Sicherheit
| Einstellungsseite                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Windows-Insider-Programm               | ms-settings:windowsinsider <br>ms-settings:windowsinsider-optin          |
| Windows Update                        | ms-settings:windowsupdate<br> ms-settings:windowsupdate-activehours  <br> ms-settings:windowsupdate-history <br> ms-settings:windowsupdate-optionalupdates <br><sup>1</sup>ms-settings:windowsupdate-options<br><sup>1</sup>ms-settings:windowsupdate-restartoptions |
| Windows Update – Suche nach Updates | ms-settings:windowsupdate-action          |
| Erweiterte Optionen                    | ms-settings:windowsupdate-options         |

>  <sup>1 </sup> Die folgenden beiden URIs führen Sie nicht zu den Seiten **Erweiterte Optionen** oder **Optionen**; sie blockieren oder zeigen nur die Windows Update-Hauptseite an. 
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions 

Eine vollständige Liste der URIs von Windows 10-Einstellungen finden Sie [hier](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference). 
