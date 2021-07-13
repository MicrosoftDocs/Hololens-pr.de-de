---
title: Sichtbarkeit von Seiteneinstellungen
description: Bleiben Sie mit unserer Liste der unterstützten URIs für PageVisibilityList und Guide auf Mixed-Reality-HoloLens-Geräten auf dem Laufenden.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: HoloLens, HoloLens 2, zugewiesener Zugriff, Kiosk, Einstellungsseite
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924331"
---
# <a name="page-settings-visibility"></a>Sichtbarkeit von Seiteneinstellungen

Eine der verwaltbaren Funktionen für HoloLens Geräte ist die Verwendung der [Richtlinie Einstellungen/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) um die Seiten einzuschränken, die in der Einstellungen-App angezeigt werden. Die PageVisibilityList ist eine Richtlinie, die es IT-Administratoren ermöglicht, entweder zu verhindern, dass bestimmte Seiten in der Systemeinstellungen-App sichtbar oder zugänglich sind oder Sie können das für alle Seiten tun, mit Ausnahme der angegebenen Seiten.

> [!NOTE]
> Diese Funktion ist nur in [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) oder höher, für HoloLens 2-Geräte geeignet. Stellen Sie bitte sicher, dass die Geräte, für die Sie diese Funktion verwenden möchten, aktualisiert sind.

Das folgende Beispiel zeigt eine Richtlinie, die nur Zugriff auf die Seiten „Über“ und „Bluetooth“ ermöglichen würde, die jeweils über URI „ms-settings:network-wifi“ und „ms-settings:bluetooth“ verfügen:
- `showonly:network-wifi;network-proxy;bluetooth`

So legen Sie dies über ein Bereitstellungspaket fest:

1. Während Sie Ihr Paket im Windows Configuration Designer erstellen, navigieren Sie zu **Richtlinien > Einstellungen > PageVisibilityList**
1. Geben Sie die folgende Zeichenfolge ein: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exportieren Sie Ihr Bereitstellungspaket.
1. Wenden Sie das Paket auf Ihr Gerät an.
Ausführliche Informationen zum Erstellen und Anwenden eines Bereitstellungspakets finden Sie auf [dieser Seite](hololens-provisioning.md).

Dies kann über Intune mit OMA-URI durchgeführt werden:

1. Eine **Benutzerdefinierte Richtlinie** erstellen.
1. Verwenden Sie beim Festlegen des OMA-URI die Zeichenfolge: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Wählen Sie bei der Datenauswahl: **Zeichenfolge**
1. Verwenden Sie beim Eingeben des Werts: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Stellen Sie sicher, dass die benutzerdefinierte Gerätekonfiguration einer Gruppe zugeordnet wird, zu der das Gerät gehören soll.

Weitere Informationen zu Intune-Gruppen und Gerätekonfigurationen finden Sie unter [HoloLens MDM-Konfiguration](hololens-mdm-configure.md).

Unabhängig von der gewählten Methode sollte Ihr Gerät jetzt die Änderungen erhalten, und den Benutzern wird die folgende Einstellungen-App angezeigt.

![Screenshot der Nutzungszeit, die in der Einstellungen-App geändert werden](images/hololens-page-visibility-list.jpg)

Um die Einstellungen-App-Seiten so zu konfigurieren, dass Ihre eigene Auswahl von Seiten ein- oder ausgeblendet wird, sehen Sie sich die Einstellungen-URIs an, die auf HoloLens verfügbar sind.

## <a name="settings-uris"></a>Einstellungen-URIs

HoloLens-Geräte und Windows 10-Geräte weisen in der App „Einstellungen“ eine unterschiedliche Seitenauswahl auf. Auf dieser Seite finden Sie nur die auf HoloLens vorhandenen Einstellungen.

### <a name="accounts"></a>Konten
| Seite "Einstellungen"           | URI                                            |
|-------------------------|------------------------------------------------|
| Auf Arbeits- oder Schulkonto zugreifen | `ms-settings:workplace`                         |
| Iris-Registrierung       | `ms-settings:signinoptions-launchirisenrollment` |
| Anmeldeoptionen         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a>Apps
| Seite "Einstellungen" | URI                          |
|---------------|------------------------------|
| Apps & Funktionen<sup>2</sup>     | `ms-settings:appsfeatures` <br> |
| Apps & Funktionen > Erweiterte Optionen <sup>2</sup>     | `ms-settings::appsfeatures-app` <br> |
| Apps & Funktionen > Offline Azure Maps<sup>2</sup>     | `ms-settings:maps-maps` <br> |
| Apps & Funktionen > Offline Azure Maps > Download Azure Maps <sup>2</sup>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a>Geräte
| Seite "Einstellungen" | URI                          |
|---------------|------------------------------|
| Bluetooth     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| Maus <sup>2</sup>      | `ms-settings:mouse` <br>  |
| USB <sup>2</sup>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a>Datenschutz
| Seite "Einstellungen"            | URI                                             |
|--------------------------|-------------------------------------------------|
| Kontoinformationen             | `ms-settings:privacy-accountinfo`              |
| App-Diagnose        | `ms-settings:privacy-appdiagnostics`              |
| Hintergrund-Apps        | `ms-settings:privacy-backgroundapps`              |
| Kalender                 | `ms-settings:privacy-calendar`                    |
| Anrufliste             | `ms-settings:privacy-callhistory`                 |
| Kamera                   | `ms-settings:privacy-webcam`                      |
| Kontakte                 | `ms-settings:privacy-contacts`                    |
| Diagnose & Feedback | `ms-settings:privacy-feedback`                    |
| Dokumente                | `ms-settings:privacy-documents`                   |
| E-Mail                    | `ms-settings:privacy-email`                       |
| Dateisystem              | `ms-settings:privacy-broadfilesystemaccess`       |
| Allgemein <sup>2</sup>             | `ms-settings:privacy-general`       |
| Personalisierung von Freihand- & Tastatureingaben <sup>2</sup>             | `ms-settings:privacy-speechtyping`       |
| Ort                 | `ms-settings:privacy-location`                    |
| Nachrichten                | `ms-settings:privacy-messaging`                   |
| Mikrofon               | `ms-settings:privacy-microphone`                  |
| Bewegung <sup>2</sup>               | `ms-settings:privacy-motion`                  |
| Benachrichtigungen            | `ms-settings:privacy-notifications`               |
| Weitere Geräte            | `ms-settings:privacy-customdevices`               |
| Bilder                 | `ms-settings:privacy-pictures`                    |
| Funkempfang                   | `ms-settings:privacy-radios`                      |
| Screenshot Ränder <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| Screenshots und Apps <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| Spracheingabe                   | `ms-settings:privacy-speech`                      |
| Aufgaben                    | `ms-settings:privacy-tasks`                       |
| Benutzerbewegungen           | `ms-settings:privacy-backgroundspatialperception` |
| Videos                   | `ms-settings:privacy-videos`                      |
| Voice-Aktivierung       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a>Netzwerk und Internet
| Seite "Einstellungen" | URI                              |
|---------------|----------------------------------|
| Flugmodus <sup>2</sup> | `ms-settings:network-airplanemode`        |
| Proxy | `ms-settings:network-proxy`        |
| VPN   | `ms-settings:network-vpn`          |
| WLAN  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a>System
| Seite "Einstellungen"      | URI                                |
|--------------------|------------------------------------|
| Akku <sup>2</sup>           | `ms-settings:batterysaver`<br>|
| Akku <sup>2</sup>           | `ms-settings:batterysaver-settings`<br>|
| Farben             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| Hologramme <sup>2</sup>  |  `ms-settings:holograms`  |
| Kalibrierung <sup>2</sup> |  `ms-settings:calibration` |
| Benachrichtigungen & Infos  | `ms-settings:notifications`          |
| Gemeinsame Erfahrungen | `ms-settings:crossdevice` 
| Sound <sup>2</sup>           | `ms-settings:sound`<br>|
| Sound > App-Lautstärke und Geräteeinstellung <sup>2</sup>           | `ms-settings:apps-volume`<br>|
| Sound > Verwalten von Soundgeräten <sup>2</sup>           | `ms-settings:sound-devices`<br>|
| Storage            | `ms-settings:storagesense`           |
| Speicher > Konfigurieren Speicheroptimierung <sup>2</sup>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a>Uhrzeit und Sprache
| Seite "Einstellungen" | URI                                           |
|---------------|-----------------------------------------------|
| Datum/Uhrzeit: <sup>2</sup> | `ms-settings:dateandtime`                  |
| Tastatur <sup>2</sup> | `ms-settings:keyboard`                  |
| Sprache <sup>2</sup> | `ms-settings:language`                  |
| Sprache <sup>2</sup> | `ms-settings:regionlanguage-languageoptions`                  |
| Sprache      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| Region        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a>Update & Sicherheit
| Seite "Einstellungen"                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Erweiterte Optionen                    | `ms-settings:windowsupdate-options`         |
| Zurücksetzen & Wiederherstellen <sup>2</sup>      | `ms-settings:reset`         |
| Windows-Insider-Programm               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows-Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows Update – Sucht nach Updates | `ms-settings:windowsupdate-action`          |


- <sup>1</sup> – Bei Versionen vor Windows Holographic, Version 21H1, werden Sie durch die folgenden beiden URIs nicht zu den Seiten **Erweiterte Optionen** oder **Optionen** geführt. Sie blockieren oder zeigen nur die Hauptseite Windows Update an.
  -  ms-settings:windowsupdate-options
  -  ms-settings:windowsupdate-restartoptions

- <sup>2</sup> – Verfügbar in Windows Holographic 21H1 oder höher.


Eine vollständige Liste der URIs für Windows 10-Einstellungen finden Sie in der Dokumentation [Starteinstellungen](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).
