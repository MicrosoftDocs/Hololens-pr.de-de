---
title: Netzwerksicherheit
description: Netzwerksicherheit
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: Sicherheit, HoloLens, Netzwerk, Netzwerksicherheit
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 147401331cb6da732a6fe37e57964d61a10dce99
ms.sourcegitcommit: 47bc3b696936dd7011b3f9dd683deb872ed25b90
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2020
ms.locfileid: "10883139"
---
# Netzwerksicherheit

## Netzwerkprotokolle

Das veraltete NetBIOS (Network Basic Input/Output System) wurde in früheren LAN-Szenarien häufig verwendet – meist für die Bereitstellung von Namensauflösung für einen Computer und freigegebene Ordner. Im Verlauf der Zeit hat sich NetBIOS aber als anfällig für verschiedene Angriffe erwiesen und seine Bedeutung verringerte sich zugunsten anderer Protokolle, die mehr Sicherheit bieten. Um dieses Problem des Sicherheitsrisikos zu beseitigen, hat HoloLens 2 den NetBIOS-bezogenen Code aus dem Betriebssystem entfernt.

TLS-Protokolle (Transport Layer Security) werden ständig weiterentwickelt. Um mit den unterschiedlichen Sicherheits-Exploits, die in diesem Bereich aufgedeckt wurden, Schritt zu halten, ist die Computerbranche auf neuere und effektivere Versionen umgestiegen. Aufgrund der Zeit, die alle Serverbereitstellungen benötigen, um die neuen TLS-Protokollversionen zu übernehmen, kann ein Fallbackmechanismus implementiert werden, der es erlaubt, dass Client und Server während der Übergangszeit noch mit verschiedenen Standardprotokollversionen kommunizieren können.

## Sichere Verbindungen 

Die Windows Defender-Firewall bietet wichtige Funktionen zur Sicherung der Gerätekonnektivität. Bei HoloLens 2 ist die Firewall immer aktiviert, und es gibt keine Möglichkeit, Sie programmgesteuert oder über die Benutzeroberfläche zu deaktivieren.

Remotezugriff und Verbindungsdatenschutz für mobile Clients können über die [UWP VPN-Plug-In-Plattform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041) sichergestellt werden. VPN-Drittanbieter können ihre eigenen Plug-Ins mithilfe von WinRT-APIs erstellen. Diese werden in der AppContainer-Sandbox ausgeführt, was Schreibvorgänge in Treiber auf Systemebene unproblematischer und weniger komplex macht.
