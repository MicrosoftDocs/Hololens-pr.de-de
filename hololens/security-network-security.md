---
title: Netzwerksicherheit
description: Netzwerksicherheit
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: Sicherheit, HoloLens, Netzwerk, Netzwerksicherheit
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 416a4f7b9e3cf2e52b79fb29f50424a9c573a18a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034436"
---
# <a name="network-security"></a>Netzwerksicherheit

## <a name="network-protocols"></a>Netzwerkprotokolle

Das veraltete NetBIOS (Network Basic Input/Output System) wurde in früheren LAN-Szenarien häufig verwendet – oft für die Bereitstellung von Namensauflösung für einen Computer und freigegebene Ordner. Im Verlauf der Zeit hat sich NetBIOS aber als anfällig für verschiedene Angriffe erwiesen, und seine Bedeutung verringerte sich zugunsten anderer Protokolle, die mehr Sicherheit bieten. Um dieses Sicherheitsproblem zu beseitigen, wurde in HoloLens 2 der NetBIOS-bezogene Code aus dem Betriebssystem entfernt.

TLS-Protokolle (Transport Layer Security) werden ständig weiterentwickelt. Um mit den unterschiedlichen Sicherheits-Exploits, die in diesem Bereich aufgedeckt wurden, Schritt zu halten, ist die Computerbranche auf neuere und effektivere Versionen umgestiegen. Aufgrund des erforderlichen Zeitaufwands bis zur Übernahme der neuen TLS-Protokollversionen für alle Serverbereitstellungen kann ein Fallbackmechanismus implementiert werden, der es erlaubt, dass Client und Server während der Übergangszeit noch mit verschiedenen Standardprotokollversionen kommunizieren können.

## <a name="secure-connectivity"></a>Sichere Verbindungen 

Die Windows Defender-Firewall bietet kritische Funktionen zur Sicherung der Gerätekonnektivität. Bei HoloLens 2 ist die Firewall immer aktiviert, und es gibt keine Möglichkeit, sie programmgesteuert oder über die Benutzeroberfläche zu deaktivieren.

Remotezugriff und Verbindungsdatenschutz für mobile Clients können über die [UWP-VPN-Plug-In-Plattform](/uwp/api/Windows.Networking.Vpn?view=winrt-19041) sichergestellt werden. VPN-Drittanbieter können ihre eigenen Plug-Ins mithilfe von WinRT-APIs erstellen. Diese werden in der AppContainer-Sandbox ausgeführt, was die Komplexität und Probleme, die oftmals mit dem Schreiben von Treibern auf Systemebene einhergehen, beseitigt.
