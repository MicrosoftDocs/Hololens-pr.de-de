---
title: Allgemeine Geräteeinschränkungen
description: Geräte restrctions, die häufig auf HoloLens eingestellt sind.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ace1e071b3d73855daacc8a11ac87770fb7f5f99
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016779"
---
# Allgemeine Geräteeinschränkungen 

Dieser Leitfaden hilft IT-Experten, die häufiger verwendeten Verwaltungsoptionen für das Windows 10 holographische Betriebssystem im Unternehmen zu verstehen. In der Dokumentation zu Ihrem MDM-System finden Sie Informationen darüber, wie diese Richtlinien von Ihrem MDM-Anbieter aktiviert werden. Nicht alle MDM-Systeme unterstützen jede in diesem Handbuch beschriebene Einstellung. Einige unterstützen benutzerdefinierte Richtlinien über OMA-URI-XML-Dateien. Weitere Informationen finden Sie unter [Microsoft Intune-Unterstützung für benutzerdefinierte Richtlinien](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10). Namenskonventionen können zwischen MDM-Anbietern ebenfalls variieren.

## Ändern der Einstellungen verhindern
In der Regel dürfen Mitarbeiter bestimmte Einstellungen auf persönlichen Geräten ändern, die Sie auf unternehmenseigenen Geräten möglicherweise sperren würden. Mitarbeiter können bestimmte Einstellungen des HoloLens interaktiv über die UI Einstellungen anpassen. Mithilfe von MDM können Sie einschränken, welche Einstellungen Benutzer ändern können. In der folgenden Liste sind häufig verwendete MDM-Einstellungen aufgeführt, die von Windows 10 holographisch unterstützt werden, um Einstellungs Einschränkungen zu konfigurieren:
-   [VPN zulassen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Ermöglicht es dem Benutzer, VPN-Einstellungen zu ändern
-   [Manuelle WLAN-Konfiguration zulassen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Ermöglicht Benutzern das Herstellen von WLAN-Verbindungen außerhalb von MDM-bereitgestellten Netzwerken
-   [Manuelle MDM-Registrierung zulassen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Ob Benutzer das Workplace-Konto löschen können (d. h., das Gerät vom MDM-System abzumelden)

Weitere Informationen zu Richtlinienoptionen finden Sie unter Unterstützte HoloLens- [Richtlinien Kryptografiedienstanbieter](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## Hardwareeinschränkungen
Windows 10 holographische Geräte verwenden modernste Technologie, die beliebte Hardware Features wie Kameras, Mikrofone, Lautsprecher, USB-Schnittstellen, Bluetooth-Schnittstellen und WLAN umfasst. Die Verfügbarkeit dieser Features kann mit Hardwareeinschränkungen gesteuert werden.
In der folgenden Liste sind häufig verwendete MDM-Einstellungen aufgeführt, die von Windows 10 holographisch unterstützt werden, um Hardwareeinschränkungen zu konfigurieren:

> [!NOTE]
> Einige dieser Hardwareeinschränkungen wirken sich auf die Konnektivität aus und unterstützen den Datenschutz.

-   [WLAN zulassen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Ob Benutzer das WiFi-Radio auf Ihren Geräten aktivieren und nutzen können.
-   [USB-Verbindung zulassen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Ob die USB-Verbindung aktiviert ist (hat keinen Einfluss auf den USB-Ladevorgang)
-   [Bluetooth zulassen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Ob Benutzer das Bluetooth-Radio auf Ihren Geräten aktivieren und verwenden können.
-   [Kamera einschränken:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Gibt an, ob Windows-apps auf die Kamera zugreifen können.
-   [Einschränken von Mikrofonen:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Gibt an, ob Windows-apps auf das Mikrofon zugreifen können.
