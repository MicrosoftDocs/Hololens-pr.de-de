---
title: Drahtlos und WLAN
description: Drahtlos und WLAN
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: Sicherheit, hololens, drahtlos, Wi-Fi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2771e6e5e428b2705fc2f495823480a9514fa71a
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865704"
---
# Drahtlos und WLAN

Die WLAN-Konnektivität für HoloLens 2 unterstützt ein beeindruckendes Spektrum der neuesten WLAN-Sicherheitsstandards, wie z. B.:
  * WPA2 (WLAN-geschützter Zugriff 2)  
  * TEAP (Tunnel Extensible Authentication Protocol)  
  * OWE (Opportunistic Wireless Encryption)

TEAP, die nächste Generation von Netzwerkauthentifizierung in Unternehmen, bietet die Möglichkeit, mehrere Anmeldeinformationen in einer einzigen Transaktion sicher zu verketten.  Auf diese Weise können Administratoren eine stärkere Sicherheitshaltung erzwingen – eine, die während der gleichen Authentifizierungstransaktion gültige Identitäten für Computer und Benutzer erfordert.

HoloLens 2 bietet moderne Drahtlos- und WLAN-Protokolle, die Kunden maximalen Support bieten. Der HoloLens 2-Funk ist eine Qualcomm WCN3990-Lösung, die eine erstklassige Funkleistung bietet. Das unterstützte WLAN ist 802.11 ac/n. Der Frequenzbereich ist nicht konfigurierbar und vom jeweiligen Verwendungsland abhängig. In den USA verwendet Wi-Fi sowohl 2,4-GHz-Kanäle (1-11) als auch 5-GHz-Kanäle (36-64, 100-165). Weder der Benutzer noch das Gerät können Zulassungs- und Verweigerungslisten für bestimmte Frequenzen erstellen. Bluetooth SIC Core 5.0 verfügt über eine dedizierte 2,4-GHz-Antenne für Bluetooth, die nicht mit WLAN geteilt wird. Der Softwarestapel von HoloLens 2 unterstützt mehrere Protokolle und Profile, einschließlich HID, HOGP, A2DP und GATT. 

IT-Administratoren haben die folgenden Möglichkeiten: 
  * Aktivieren oder Einschränken des [Bluetooth-Zugriffs](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth).
  * Festlegen von [lokalen Bluetooth-Gerätenamen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename).
  * Zulassen, dass [Geräte auffindbar sind](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode).
  * Zulassen/Verweigern von [WLAN-Verbindungen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi). 
  * Zulassen/Verweigern einer [WLAN-Verbindung außerhalb von auf dem MDM-Server eingerichteten Netzwerken](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration).
