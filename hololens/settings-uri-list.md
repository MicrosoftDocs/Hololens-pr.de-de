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
ms.openlocfilehash: 92040019b093c5ef63d74f095dcb3809112ae7a0
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428717"
---
# <a name="page-settings-visibility"></a>Sichtbarkeit von Seiteneinstellungen

Eine der verwaltbaren Funktionen für HoloLens Geräte ist die Verwendung der [Richtlinie Einstellungen/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) um die Seiten einzuschränken, die in der Einstellungen-App angezeigt werden. Die PageVisibilityList ist eine Richtlinie, die es IT-Administratoren ermöglicht, entweder zu verhindern, dass bestimmte Seiten in der Systemeinstellungen-App sichtbar oder zugänglich sind oder Sie können das für alle Seiten tun, mit Ausnahme der angegebenen Seiten.

> [!NOTE]
> Diese Funktion ist nur in [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) oder höher, für HoloLens 2-Geräte geeignet. Stellen Sie bitte sicher, dass die Geräte, für die Sie diese Funktion verwenden möchten, aktualisiert sind.


## <a name="examples"></a>Beispiele
Die Seiten werden durch eine gekürzte Version ihrer veröffentlichten URIs identifiziert, was praktisch den URI ohne das Präfix „ms-settings:“ bedeutet.

Das folgende Beispiel zeigt eine Richtlinie, die nur Zugriff auf die Seiten „Info“ und „Bluetooth“ ermöglicht, die jeweils den URI „network-wifi“ und „bluetooth“ aufweisen:
- `showonly:network-wifi;network-proxy;bluetooth`

Im folgenden Beispiel wird eine Richtlinie veranschaulicht, die die Seite „Betriebssystemzurücksetzung“ ausblendet:
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a>Bereitstellen dieser Richtlinie über Intune

Dies sind die Konfigurationswerte, die für Intune bereitgestellt werden:

- **Name:** Ein vom Administrator bevorzugter Anzeigename für das Profil.
- **OMA-URI:** Der vollqualifizierte URI der Einstellungsseite, einschließlich des [Bereichs](/windows/client-management/mdm/policy-configuration-service-provider). In den Beispielen auf dieser Seite wird der Bereich `./Device` verwendet.
- **Wert:** Ein Zeichenfolgenwert, der angibt, ob *nur* die angegebenen Seiten ausgeblendet oder angezeigt werden. Mögliche Werte sind `hide:<pagename>` und `showonly:<pagename>`. 
 
Mehrere Seiten können angegeben werden, indem Sie sie durch ein Semikolon trennen, und eine Liste gängiger Seiten finden Sie unten.

1. Eine **Benutzerdefinierte Richtlinie** erstellen.
1. Geben Sie beim Festlegen des **OMA-URI** den vollständigen bereichsspezifischen URI ein. Beispiel: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Wählen Sie bei der Datenauswahl: **Zeichenfolge**
1. Verwenden Sie zum Angeben des **Werts** die obige Anleitung. Beispiel: **`showonly:network-wifi;network-proxy;bluetooth`** oder **`hide:reset`** 
> [!IMPORTANT]
> Stellen Sie sicher, dass die benutzerdefinierte Gerätekonfiguration einer Gruppe zugeordnet wird, zu der das Gerät gehören soll. Wenn dieser Schritt nicht ausgeführt wird, wird die Richtlinie gepusht, aber nicht angewendet.

Weitere Informationen zu Intune-Gruppen und Gerätekonfigurationen finden Sie unter [HoloLens MDM-Konfiguration](hololens-mdm-configure.md).


## <a name="deploying-this-policy-via-a-provisioning-package"></a>Bereitstellen dieser Richtlinie über ein Bereitstellungspaket

Dies sind die Konfigurationswerte, die in Windows Configuration Designer angegeben werden:

**Wert:** Ein Zeichenfolgenwert, der angibt, ob *nur* die angegebenen Seiten ausgeblendet oder angezeigt werden. Mögliche Werte sind `hide:<pagename>` und `showonly:<pagename>`. Mehrere Seiten können angegeben werden, indem Sie sie durch ein Semikolon trennen, und eine Liste gängiger Seiten finden Sie unten.


1. Während Sie Ihr Paket im Windows Configuration Designer erstellen, navigieren Sie zu **Richtlinien > Einstellungen > PageVisibilityList**
1. Geben Sie die folgende Zeichenfolge ein: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exportieren Sie Ihr Bereitstellungspaket.
1. Wenden Sie das Paket auf Ihr Gerät an.
Ausführliche Informationen zum Erstellen und Anwenden eines Bereitstellungspakets finden Sie auf der [Seite zur HoloLens-Bereitstellung](hololens-provisioning.md).


Unabhängig von der gewählten Methode sollte Ihr Gerät jetzt die Änderungen erhalten, und den Benutzern wird die folgende Einstellungen-App angezeigt.

![Screenshot der Nutzungszeit, die in der Einstellungen-App geändert werden.](images/hololens-page-visibility-list.jpg)

Um die Einstellungen-App-Seiten so zu konfigurieren, dass Ihre eigene Auswahl von Seiten ein- oder ausgeblendet wird, sehen Sie sich die Einstellungen-URIs an, die auf HoloLens verfügbar sind.

## <a name="settings-uris"></a>Einstellungen-URIs

HoloLens-Geräte und Windows 10-Geräte weisen in der App „Einstellungen“ eine unterschiedliche Seitenauswahl auf. Auf dieser Seite finden Sie nur die auf HoloLens vorhandenen Einstellungen.

### <a name="accounts"></a>Konten
| Seite "Einstellungen"           | URI                                            |
|-------------------------|------------------------------------------------|
| Auf Arbeits- oder Schulkonto zugreifen | `workplace`                         |
| Iris-Registrierung       | `signinoptions-launchirisenrollment` |
| Anmeldeoptionen         | ` signinoptions `                   |

### <a name="apps"></a>Apps
| Seite "Einstellungen" | URI                          |
|---------------|------------------------------|
| Apps und Features <sup>2</sup>     | `appsfeatures` <br> |
| Apps & Funktionen > Erweiterte Optionen <sup>2</sup>     | `appsfeatures-app` <br> |
| Apps & Funktionen > Offline Azure Maps<sup>2</sup>     | `maps-maps` <br> |
| Apps & Funktionen > Offline Azure Maps > Download Azure Maps <sup>2</sup>     | `maps-downloadmaps` <br> |

### <a name="devices"></a>Geräte
| Seite "Einstellungen" | URI                          |
|---------------|------------------------------|
| Bluetooth     | `bluetooth` <br> `connecteddevices` |
| Maus <sup>2</sup>      | `mouse` <br>  |
| USB <sup>2</sup>      | `usb` <br>  |

### <a name="privacy"></a>Datenschutz
| Seite "Einstellungen"            | URI                                             |
|--------------------------|-------------------------------------------------|
| Kontoinformationen             | `privacy-accountinfo`              |
| App-Diagnose        | `privacy-appdiagnostics`              |
| Hintergrund-Apps        | `privacy-backgroundapps`              |
| Kalender                 | `privacy-calendar`                    |
| Anrufliste             | `privacy-callhistory`                 |
| Kamera                   | `privacy-webcam`                      |
| Kontakte                 | `privacy-contacts`                    |
| Diagnose & Feedback | `privacy-feedback`                    |
| Dokumente                | `privacy-documents`                   |
| E-Mail                    | `privacy-email`                       |
| Dateisystem              | `privacy-broadfilesystemaccess`       |
| Allgemein <sup>2</sup>             | `privacy-general`       |
| Personalisierung von Freihand- & Tastatureingaben <sup>2</sup>             | `privacy-speechtyping`       |
| Ort                 | `privacy-location`                    |
| Nachrichten                | `privacy-messaging`                   |
| Mikrofon               | `privacy-microphone`                  |
| Bewegung <sup>2</sup>               | `privacy-motion`                  |
| Benachrichtigungen            | `privacy-notifications`               |
| Weitere Geräte            | `privacy-customdevices`               |
| Bilder                 | `privacy-pictures`                    |
| Funkempfang                   | `privacy-radios`                      |
| Screenshot Ränder <sup>2</sup>             | `privacy-graphicsCaptureWithoutBorder`       |
| Screenshots und Apps <sup>2</sup>             | `privacy-graphicsCaptureProgrammatic`       |
| Spracheingabe                   | `privacy-speech`                      |
| Aufgaben                    | `privacy-tasks`                       |
| Benutzerbewegungen           | `privacy-backgroundspatialperception` |
| Videos                   | `privacy-videos`                      |
| Voice-Aktivierung       | `privacy-voiceactivation`             |

### <a name="network--internet"></a>Netzwerk und Internet
| Seite "Einstellungen" | URI                              |
|---------------|----------------------------------|
| Flugmodus <sup>2</sup> | `network-airplanemode`        |
| Proxy | `network-proxy`        |
| VPN   | `network-vpn`          |
| WLAN  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a>System
| Seite "Einstellungen"      | URI                                |
|--------------------|------------------------------------|
| Akku <sup>2</sup>           | `batterysaver`<br>|
| Akku <sup>2</sup>           | `batterysaver-settings`<br>|
| Farben             | `colors`<br>`personalization-colors` |
| Hologramme <sup>2</sup>  |  `holograms`  |
| Kalibrierung <sup>2</sup> |  `calibration` |
| Benachrichtigungen & Infos  | `notifications`          |
| Gemeinsame Erfahrungen | `crossdevice` 
| Sound <sup>2</sup>           | `sound`<br>|
| Sound > App-Lautstärke und Geräteeinstellung <sup>2</sup>           | `apps-volume`<br>|
| Sound > Verwalten von Soundgeräten <sup>2</sup>           | `sound-devices`<br>|
| Storage            | `storagesense`           |
| Speicher > Konfigurieren Speicheroptimierung <sup>2</sup>           | `storagepolicies`<br>|

### <a name="time--language"></a>Uhrzeit und Sprache
| Seite "Einstellungen" | URI                                           |
|---------------|-----------------------------------------------|
| Datum/Uhrzeit: <sup>2</sup> | `dateandtime`                  |
| Tastatur <sup>2</sup> | `keyboard`                  |
| Sprache <sup>2</sup> | `language`                  |
| Sprache <sup>2</sup> | `regionlanguage-languageoptions`                  |
| Sprache      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| Region        | `regionformatting`                  |

### <a name="update--security"></a>Update & Sicherheit
| Seite "Einstellungen"                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Erweiterte Optionen                    | `windowsupdate-options`         |
| Zurücksetzen & Wiederherstellen <sup>2</sup>      | `reset`         |
| Windows-Insider-Programm               | `windowsinsider` <br>`windowsinsider-optin`          |
| Windows-Update                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><sup>1</sup>`windowsupdate-options`<br><sup>1</sup>`windowsupdate-restartoptions` |
| Windows Update – Sucht nach Updates | `windowsupdate-action`          |


- <sup>1</sup> – Bei Versionen vor Windows Holographic, Version 21H1, werden Sie durch die folgenden beiden URIs nicht zu den Seiten **Erweiterte Optionen** oder **Optionen** geführt. Sie blockieren oder zeigen nur die Hauptseite Windows Update an.
  -  windowsupdate-options
  -  windowsupdate-restartoptions

- <sup>2</sup> – Verfügbar in Windows Holographic 21H1 oder höher.


Eine vollständige Liste der URIs für Windows 10-Einstellungen finden Sie in der Dokumentation [Starteinstellungen](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).
