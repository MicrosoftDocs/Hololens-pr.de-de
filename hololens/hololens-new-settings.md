---
title: Einführung in die neue Einstellungen-App
description: Informationen zur neuen Einstellungen-App
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, Einstellungen, App-Auswahl, Lautstärke
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bcde697b5887573826a3a1a61e8c3707b4d0337a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034387"
---
# <a name="new-settings-app"></a>Neue Einstellungen-App

Mit [Windows Holographic, Version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) führen wir eine neue Version der Einstellungen-App ein. Die neue Einstellungen-App enthält neue Funktionen und erweiterte Einstellungen für HoloLens 2 in den folgenden Bereichen: Sound, Energie & Ruhezustand, Netzwerk & Internet, Apps, Konten, Erleichterte Bedienung und mehr.

> [!NOTE]
> Da sich die neue Einstellungen-App von der Legacy-Einstellungen-App unterscheidet, werden alle Fenster mit Einstellungen, die Sie zuvor in Ihrer Umgebung platziert haben, nach dem Update entfernt.

![Startseite mit der „Neue Einstellungen“-App.](images/new-settings-app.png)

**Neue Funktionen und Einstellungen**
- Suchen von Einstellungen: Suchen Sie auf der Startseite der Einstellungen nach Einstellungen, indem Sie Schlüsselwörter oder den Namen der Einstellung verwenden.
- System > [Farbenkalibrierung](hololens2-display.md#how-to-use-display-color-calibration)
    - Wählen Sie ein alternatives Farbprofil für Ihre HoloLens 2 Anzeigen aus.
- System > Sound:
  - Eingabe- und Ausgabeaudiogeräte: Wählen Sie unabhängig Ihre Eingabe- und Ausgabeaudiogeräte aus (z B. hören Sie Audios über Bluetooth Kopfhörer an oder verwenden Sie ein USB-C-Mikrofon für die Audioeingabe).
    > [!NOTE]
    > Bluetooth-Mikrofone werden von HoloLens 2 nicht unterstützt.
  - App-Lautstärke: Passen Sie die Lautstärke der einzelnen Apps unabhängig an. Weitere Informationen finden Sie unter[ Lautstärkesteuerung per App](holographic-home.md#per-app-volume-control).
- System > Energie & Ruhezustand: Legen Sie fest, wann das Gerät nach einer gewissen Zeit der Inaktivität in den Ruhezustand übergehen soll.
- System > Akku: Aktivieren Sie manuell den Stromsparmodus Modus, oder legen Sie einen Akkuschwellenwert fest, an dem Stromsparmodus Modus automatisch eingeschaltet wird.
- Geräte > USB: Sie können USB-Verbindungen standardmäßig deaktivieren.
- Netzwerk & Internet:
  - USB-C-Ethernet-Adapter werden jetzt in Netzwerk & Internet angezeigt.
  - USB-C Ethernet-Adaptereinstellungen sind jetzt verfügbar, einschließlich der IP-Adresse.
  - Sie können jetzt den Flugzeugmodus auf HoloLens 2 aktivieren.
- Apps: Sie können die Standard-Apps, die für Datei- und Linktypen verwendet werden, zurücksetzen. Weitere Informationen finden Sie unter [Standardapp-Auswahl](holographic-home.md#default-app-picker).
- Konten > Andere Benutzer: Gerätebesitzer können Benutzer hinzufügen, Standardbenutzer auf Gerätebesitzer höherstufen, Gerätebesitzer auf Standardbenutzer herabstufen und Benutzer entfernen.
- Erleichterte Bedienung: Ändern der Textgröße und einiger visueller Effekte.

**Bekannte Probleme**
- Fenster mit zuvor platzierten Einstellungen werden entfernt (siehe Hinweis oben).
- Sie können Ihr Gerät nicht mehr mit der Einstellungen-App umbenennen. IT-Administratoren können Geräte umbenennen, indem sie die [Windows Autopilot für HoloLens 2](hololens2-autopilot.md)-Vorlage für Gerätenamen oder den MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName Knoten verwenden.
- Auf der Seite „Ethernet“ wird jederzeit ein virtuelles Ethernet-Gerät („UsbNcm“) angezeigt.
- Der Akkuverbrauch für den neuen Microsoft Edge ist aufgrund seiner Art als Win32-Desktopanwendung, die von einer UWP-Adapterebene unterstützt wird, möglicherweise nicht korrekt (es wird in Kürze keine Korrektur erwartet).

