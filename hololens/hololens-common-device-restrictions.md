---
title: Allgemeine Geräteeinschränkungen
description: Halten Sie sich mit allgemeinen Geräteeinschränkungen und Einstellungen für das Mixed -Reality-Gerät von HoloLens auf dem Laufenden.
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283356"
---
# Allgemeine Geräteeinschränkungen 

Dieses Handbuch hilft IT-Experten, die am häufigsten verwendeten Verwaltungsoptionen für das Windows 10 Holographic-Betriebssystem im Unternehmen zu verstehen. In der Dokumentation zu Ihrem MDM-System finden Sie Informationen darüber, wie diese Richtlinien von Ihrem MDM-Anbieter aktiviert werden. Nicht alle MDM-Systeme unterstützen jede in diesem Handbuch beschriebene Einstellung. Einige unterstützen benutzerdefinierte Richtlinien über OMA-URI-XML-Dateien. Weitere Informationen finden Sie unter [Microsoft Intune-Unterstützung für benutzerdefinierte Richtlinien](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10). Namenskonventionen können zwischen MDM-Anbietern ebenfalls variieren.

## Ändern der Einstellungen verhindern
In der Regel dürfen Mitarbeiter bestimmte Einstellungen auf persönlichen Geräten ändern, die Sie auf unternehmenseigenen Geräten möglicherweise sperren würden. Mitarbeiter können bestimmte Einstellungen der HoloLens interaktiv über die Einstellungsbenutzeroberfläche anpassen. Mithilfe von MDM können Sie einschränken, welche Einstellungen Benutzer ändern können. In der folgenden Liste sind häufig verwendete MDM-Einstellungen aufgeführt, die Von Windows 10 Holographic zum Konfigurieren von Einstellungseinschränkungen unterstützt werden:
-   [VPN zulassen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Ermöglicht dem Benutzer das Ändern von VPN-Einstellungen.
-   [Manuelle WLAN-Konfiguration zulassen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Ermöglicht Benutzern das Herstellen Wi-Fi von Verbindungen außerhalb von bereitgestellten MDM-Netzwerken.
-   [Manuelles Unenrollment für MDM zulassen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Gibt an, ob Benutzer das Arbeitsplatzkonto löschen dürfen (d. h. die Registrierung des Geräts aus dem MDM-System zu entfernen)

Hinzugefügt in [Windows Holographic, Version 20H2 für](hololens-release-notes.md#windows-holographic-version-20h2) HoloLens 2-Geräte:
- [Bereitstellungspaket hinzufügen zulassen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Umschalten, wenn Benutzer neue Bereitstellungspakete hinzufügen und mit neuen Werten überschreiben können.
- [Bereitstellungspaket entfernen zulassen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Umschalten, wenn Benutzer Bereitstellungspakete entfernen können, sodass sie zuvor gesperrte Einstellungen umschalten können.

Weitere Informationen zu Richtlinienoptionen finden Sie in den von HoloLens unterstützten [Richtlinien-CSPs.](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## Hardwareeinschränkungen
Windows 10 -Holographic-Geräte verwenden die moderne Technologie, die beliebte Hardwarefeatures wie Kameras, Mikrofone, Lautsprecher, USB-Schnittstellen, Bluetooth schnittstellen und WLAN umfasst. Die Verfügbarkeit dieser Features kann mit Hardwareeinschränkungen gesteuert werden.
In der folgenden Liste sind häufig verwendete MDM-Einstellungen aufgeführt, die Von Windows 10 Holographic zum Konfigurieren von Hardwareeinschränkungen unterstützt werden:

> [!NOTE]
> Einige dieser Hardwareeinschränkungen wirken sich auf die Konnektivität aus und unterstützen den Datenschutz.

-   [WLAN zulassen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Gibt an, ob Benutzer das WLAN auf ihren Geräten aktivieren und verwenden können.
-   [Lassen Sie die USB-Verbindung zu:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Gibt an, ob die USB-Verbindung aktiviert ist (wirkt sich nicht auf das Laden von USB aus.)
-   [Zulassen Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Gibt an, ob Benutzer das Bluetooth auf ihren Geräten aktivieren und verwenden können.
-   [Kamera einschränken:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Gibt an, ob Windows-Apps auf die Kamera zugreifen können.
-   [Einschränken von Mikrofonen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Gibt an, ob Windows-Apps auf das Mikrofon zugreifen können.

Hinzugefügt in [Windows Holographic, Verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) für HoloLens 2-Geräte. 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Legen Sie den Zeitraum bis zum Deaktivieren der Anzeige und durch Deaktivieren des Displays für das Gerät ein. 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Legen Sie den Zeitraum bis zum Deaktivieren der Anzeige und durch Deaktivieren des Displays für das Gerät ein. 
