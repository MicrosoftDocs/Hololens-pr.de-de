---
title: Allgemeine Geräteeinschränkungen
description: Halten Sie sich über allgemeine Geräteeinschränkungen und -einstellungen für das HoloLens Mixed Reality-Gerät auf dem Laufenden.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e9c44466da375611f8864eae1b6e6ceea3ef9b09
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308555"
---
# <a name="common-device-restrictions"></a>Allgemeine Geräteeinschränkungen 

Dieser Leitfaden hilft IT-Experten dabei, die häufig verwendeten Verwaltungsoptionen zu verstehen, die für das Windows 10 Holographic Betriebssystem im Unternehmen verfügbar sind. In der Dokumentation zu Ihrem MDM-System finden Sie Informationen darüber, wie diese Richtlinien von Ihrem MDM-Anbieter aktiviert werden. Nicht alle MDM-Systeme unterstützen jede in diesem Handbuch beschriebene Einstellung. Einige unterstützen benutzerdefinierte Richtlinien über OMA-URI-XML-Dateien. Weitere Informationen finden Sie unter [Microsoft Intune-Unterstützung für benutzerdefinierte Richtlinien](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10). Namenskonventionen können zwischen MDM-Anbietern ebenfalls variieren.

## <a name="prevent-changing-of-settings"></a>Ändern der Einstellungen verhindern
In der Regel dürfen Mitarbeiter bestimmte Einstellungen auf persönlichen Geräten ändern, die Sie auf unternehmenseigenen Geräten möglicherweise sperren würden. Mitarbeiter können bestimmte Einstellungen der HoloLens interaktiv über die Benutzeroberfläche für Einstellungen anpassen. Mithilfe von MDM können Sie einschränken, welche Einstellungen Benutzer ändern können. Im Folgenden werden häufig verwendete MDM-Einstellungen aufgeführt, die Windows 10 Holographic zum Konfigurieren von Einstellungseinschränkungen unterstützt:
-   [VPN zulassen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Ermöglicht dem Benutzer, VPN-Einstellungen zu ändern.
-   [Manuelle WLAN-Konfiguration zulassen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Ermöglicht Benutzern das Herstellen Wi-Fi Verbindungen außerhalb von MDM-bereitgestellten Netzwerken.
-   [Manuelle MDM-Registrierung zulassen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Gibt an, ob Benutzer das Arbeitsplatzkonto löschen dürfen (d. h. die Registrierung des Geräts beim MDM-System aufheben).

Hinzugefügt in [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) für HoloLens 2 Geräte:
- [Bereitstellungspaket hinzufügen zulassen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Schalten Sie um, wenn Benutzer neue Bereitstellungspakete hinzufügen und mit neuen Werten überschreiben können.
- [Bereitstellungspaket entfernen zulassen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Schalten Sie um, wenn Benutzer Bereitstellungspakete entfernen können, sodass sie zuvor gesperrte Einstellungen umschalten können.

Weitere Informationen zu Richtlinienoptionen finden Sie in den von HoloLens unterstützten [Richtlinien-CSPs.](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Hardwareeinschränkungen
Windows 10 Holographic Geräte verwenden moderne Technologie, die beliebte Hardwarefeatures wie Kameras, Mikrofone, Lautsprecher, USB-Schnittstellen, Bluetooth-Schnittstellen und WLAN umfasst. Die Verfügbarkeit dieser Features kann mit Hardwareeinschränkungen gesteuert werden.
Im Folgenden werden häufig verwendete MDM-Einstellungen aufgeführt, die Windows 10 Holographic zum Konfigurieren von Hardwareeinschränkungen unterstützt:

> [!NOTE]
> Einige dieser Hardwareeinschränkungen wirken sich auf die Konnektivität aus und unterstützen den Datenschutz.

-   [WLAN zulassen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Gibt an, ob Benutzer das WLAN-Radio auf ihren Geräten aktivieren und verwenden können.
-   [USB-Verbindung zulassen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Gibt an, ob die USB-Verbindung aktiviert ist (ohne Auswirkungen auf usb-Ladevorgänge).)
-   [Bluetooth zulassen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Gibt an, ob Benutzer das Bluetooth-Radio auf ihren Geräten aktivieren und verwenden können.
-   [Kamera einschränken:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Gibt an, ob Windows-Apps auf die Kamera zugreifen können.
-   [Mikrofone einschränken:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Gibt an, ob Windows-Apps auf das Mikrofon zugreifen können.

Hinzugefügt in [Windows Holographic, Verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) für HoloLens 2 Geräte. 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Legen Sie die Zeit fest, bis die Anzeige deaktiviert ist, und sperrt das Gerät, indem Sie die Anzeige deaktivieren. 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Legen Sie die Zeit fest, bis die Anzeige deaktiviert ist, und sperrt das Gerät, indem Sie die Anzeige deaktivieren. 
