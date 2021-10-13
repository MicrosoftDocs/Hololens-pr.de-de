---
title: Allgemeine Geräteeinschränkungen
description: Halten Sie sich über allgemeine Geräteeinschränkungen und -einstellungen für das HoloLens Mixed Reality-Gerät auf dem Laufenden.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2021
ms.reviewer: aboeger
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 12dd061565c88fed65d1152c224be9ebbc7185d4
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924303"
---
# <a name="common-device-restrictions"></a>Allgemeine Geräteeinschränkungen

Dieser Leitfaden hilft IT-Experten dabei, die häufig verwendeten Verwaltungsoptionen zu verstehen, die für das Windows 10 Holographic Betriebssystem im Unternehmen verfügbar sind. In der Dokumentation zu Ihrem MDM-System finden Sie Informationen darüber, wie diese Richtlinien von Ihrem MDM-Anbieter aktiviert werden. Nicht alle MDM-Systeme unterstützen jede in diesem Handbuch beschriebene Einstellung. Einige unterstützen benutzerdefinierte Richtlinien über OMA-URI-XML-Dateien. Weitere Informationen finden Sie unter [Microsoft Intune-Unterstützung für benutzerdefinierte Richtlinien](/mem/intune/configuration/custom-settings-windows-10). Namenskonventionen können zwischen MDM-Anbietern ebenfalls variieren.

## <a name="prevent-changing-of-settings"></a>Ändern der Einstellungen verhindern

In der Regel dürfen Mitarbeiter bestimmte Einstellungen auf persönlichen Geräten ändern, die Sie auf unternehmenseigenen Geräten möglicherweise sperren würden. Mitarbeiter können bestimmte Einstellungen der HoloLens über die Benutzeroberfläche für Einstellungen interaktiv anpassen. Mithilfe von MDM können Sie einschränken, welche Einstellungen Benutzer ändern können.
Im Folgenden werden häufig verwendete MDM-Einstellungen aufgeführt, die Windows 10 Holographic zum Konfigurieren von Einstellungseinschränkungen unterstützt:

- [VPN zulassen:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Ermöglicht dem Benutzer das Ändern von VPN-Einstellungen
- [Manuelle WLAN-Konfiguration zulassen:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Ermöglicht Benutzern das Herstellen Wi-Fi Verbindungen außerhalb von MDM-bereitgestellten Netzwerken.
- [Manuelle MDM-Registrierung zulassen](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Gibt an, ob Benutzer das Arbeitsplatzkonto löschen dürfen (d. h. die Registrierung des Geräts beim MDM-System aufheben).

Hinzugefügt in [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) für HoloLens 2 Geräte:

- [Bereitstellungspaket hinzufügen zulassen:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Schalten Sie um, wenn Benutzer neue Bereitstellungspakete hinzufügen und mit neuen Werten überschreiben können.
- [Bereitstellungspaket entfernen zulassen:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Schalten Sie um, wenn Benutzer Bereitstellungspakete entfernen können, sodass sie zuvor gesperrte Einstellungen umschalten können.

Hinzugefügt in [Windows Holographic, Version 21H2:](hololens-release-notes.md#windows-holographic-version-21h2)

- Mit der [RequirePrivateStoreOnly-Richtlinie](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly) kann die Microsoft Store-App so konfiguriert werden, dass nur der private Speicher angezeigt wird, der für Ihre Organisation konfiguriert ist, und der Zugriff auf die Apps beschränkt wird, die Sie zur Verfügung gestellt haben.

Weitere Informationen zu Richtlinienoptionen finden Sie in den HoloLens unterstützten [Richtlinien-CSPs.](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Hardwareeinschränkungen

Windows 10 Holographic Geräte verwenden moderne Technologie, die beliebte Hardwarefeatures wie Kameras, Mikrofone, Lautsprecher, USB-Schnittstellen, Bluetooth Schnittstellen und WLAN umfasst. Die Verfügbarkeit dieser Features kann mit Hardwareeinschränkungen gesteuert werden.
Im Folgenden werden häufig verwendete MDM-Einstellungen aufgeführt, die Windows 10 Holographic zum Konfigurieren von Hardwareeinschränkungen unterstützt:

> [!NOTE]
> Einige dieser Hardwareeinschränkungen wirken sich auf die Konnektivität aus und unterstützen den Datenschutz.

- [WLAN zulassen:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Gibt an, ob Benutzer das WLAN-Radio auf ihren Geräten aktivieren und verwenden können.
- [USB-Verbindung zulassen:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Gibt an, ob die USB-Verbindung aktiviert ist (ohne Auswirkungen auf usb-Ladevorgänge).)
- [Bluetooth zulassen:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Gibt an, ob Benutzer das Bluetooth Radio auf ihren Geräten aktivieren und verwenden können.
- [Kamera einschränken:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Gibt an, ob Windows Apps auf die Kamera zugreifen können.
- [Mikrofone einschränken:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Gibt an, ob Windows Apps auf das Mikrofon zugreifen können.

Hinzugefügt in [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) für HoloLens 2 Geräte:

- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Legen Sie die Zeitspanne fest, bis die Anzeige ausgeschaltet wird, und sperrt das Gerät, indem Sie die Anzeige deaktivieren.
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Legen Sie die Zeitspanne fest, bis die Anzeige ausgeschaltet wird, und sperrt das Gerät, indem Sie die Anzeige deaktivieren.
