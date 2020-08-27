---
title: Einstellungs-URIs
description: Liste der von HoloLens unterstützten URIs für PageVisibilityList
author: evmill
ms.author: v-evmill
ms.date: 8/1/2020
ms.topic: article
keywords: HoloLens, HoloLens 2, zugewiesener Zugriff, Kiosk, Einstellungsseite
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 6b506b36915c8f34b90c455410db67e55a2cca09
ms.sourcegitcommit: 7f48e7103f869a22a0d20a54dc8f9b708b22484c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2020
ms.locfileid: "10963714"
---
# Einstellungs-URIs

Zu den verwaltbaren Features für HoloLens-Geräte gehört die [Einstellungen/PageVisibilityList-Richtlinie](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist), mit der die in der App „Einstellungen“ angezeigten Seiten eingeschränkt werden können. HoloLens-Geräte und Windows 10-Geräte weisen in der App „Einstellungen“ eine unterschiedliche Seitenauswahl auf. Auf dieser Seite finden Sie nur die Einstellungen, die auf HoloLens vorhanden sind. 

## Konten
| Einstellungsseite           | URI                                            |
|-------------------------|------------------------------------------------|
| Anmeldeoptionen         | ms-settings:signinoptions                      |
| Iris-Registrierung       | ms-settings:signinoptions-launchirisenrollment |
| Geschäfts- oder Schulkonto öffnen | ms-settings:workplace                          |

## Geräte
| Einstellungsseite | URI                          |
|---------------|------------------------------|
| Bluetooth     | ms-settings:bluetooth <br> ms-settings:connecteddevices |

## Vertraulichkeit
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

## Netzwerk und Internet
| Einstellungsseite | URI                              |
|---------------|----------------------------------|
| WLAN  | ms-settings:network-wifi<br>ms-settings:network-wifisettings<br>ms-settings:network-status<br>ms-settings:wifi-provisioning    |
| VPN   | ms-settings:network-vpn          |
| Proxy | ms-settings:network-proxy        |

## System
| Einstellungsseite      | URI                                |
|--------------------|------------------------------------|
| Gemeinsame Erfahrung | ms-settings:crossdevice            |
| Farben             | ms-settings:colors<br>ms-settings:personalization-colors |
| Benachrichtigungen & Infos  | ms-settings:notifications          |
| Speicher            | ms-settings:storagesense           |

## Zeit & Sprache
| Einstellungsseite | URI                                           |
|---------------|-----------------------------------------------|
| Region        | ms-settings:regionformatting                  |
| Sprache      | ms-settings:regionlanguage<br>ms-settings:regionlanguage-adddisplaylanguage<br>ms-settings:regionlanguage-setdisplaylanguage |

## Update und Sicherheit
| Einstellungsseite                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Windows-Insider-Programm               | ms-settings:windowsinsider <br>ms-settings:windowsinsider-optin          |
| Windows Update                        | ms-settings:windowsupdate<br> ms-settings:windowsupdate-activehours  <br> ms-settings:windowsupdate-history <br> ms-settings:windowsupdate-optionalupdates <br><sup>1</sup>ms-settings:windowsupdate-options<br><sup>1</sup>ms-settings:windowsupdate-restartoptions |
| Windows Update – Suche nach Updates | ms-settings:windowsupdate-action          |
| Erweiterte Optionen                    | ms-settings:windowsupdate-options         |

> [!NOTE]
>  1 Die folgenden beiden URI führen Sie nicht tatsächlich zur Seite „Erweiterte Optionen“ oder „Optionen“. Sie blockieren/zeigen nur die Hauptseite von Windows Update. 
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions 

Eine vollständige Liste der URIs von Windows 10-Einstellungen finden Sie [hier](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference). 
