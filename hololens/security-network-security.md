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
ms.openlocfilehash: f1e5304408a9a9543eb0703ad7321725484eef01
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009423"
---
# <span data-ttu-id="f3c92-104">Netzwerksicherheit</span><span class="sxs-lookup"><span data-stu-id="f3c92-104">Network security</span></span>

## <span data-ttu-id="f3c92-105">Netzwerkprotokolle</span><span class="sxs-lookup"><span data-stu-id="f3c92-105">Network protocols</span></span>

<span data-ttu-id="f3c92-106">Das veraltete NetBIOS (Network Basic Input/Output System) wurde in früheren LAN-Szenarien häufig verwendet – meist für die Bereitstellung von Namensauflösung für einen Computer und freigegebene Ordner.</span><span class="sxs-lookup"><span data-stu-id="f3c92-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="f3c92-107">Im Verlauf der Zeit hat sich NetBIOS aber als anfällig für verschiedene Angriffe erwiesen und seine Bedeutung verringerte sich zugunsten anderer Protokolle, die mehr Sicherheit bieten.</span><span class="sxs-lookup"><span data-stu-id="f3c92-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="f3c92-108">Um dieses Problem des Sicherheitsrisikos zu beseitigen, hat HoloLens2 den NetBIOS-bezogenen Code aus dem Betriebssystem entfernt.</span><span class="sxs-lookup"><span data-stu-id="f3c92-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="f3c92-109">TLS-Protokolle (Transport Layer Security) werden ständig weiterentwickelt.</span><span class="sxs-lookup"><span data-stu-id="f3c92-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="f3c92-110">Um mit den unterschiedlichen Sicherheits-Exploits, die in diesem Bereich aufgedeckt wurden, Schritt zu halten, ist die Computerbranche auf neuere und effektivere Versionen umgestiegen.</span><span class="sxs-lookup"><span data-stu-id="f3c92-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="f3c92-111">Aufgrund der Zeit, die alle Serverbereitstellungen benötigen, um die neuen TLS-Protokollversionen zu übernehmen, kann ein Fallbackmechanismus implementiert werden, der es erlaubt, dass Client und Server während der Übergangszeit noch mit verschiedenen Standardprotokollversionen kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="f3c92-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

## <span data-ttu-id="f3c92-112">Sichere Verbindungen</span><span class="sxs-lookup"><span data-stu-id="f3c92-112">Secure connectivity</span></span> 

<span data-ttu-id="f3c92-113">Die Windows Defender-Firewall bietet wichtige Funktionen zur Sicherung der Gerätekonnektivität.</span><span class="sxs-lookup"><span data-stu-id="f3c92-113">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="f3c92-114">Bei HoloLens2 ist die Firewall immer aktiviert, und es gibt keine Möglichkeit, Sie programmgesteuert oder über die Benutzeroberfläche zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f3c92-114">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="f3c92-115">Remotezugriff und Verbindungsdatenschutz für mobile Clients können über die [UWP VPN-Plug-In-Plattform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041) sichergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f3c92-115">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="f3c92-116">VPN-Drittanbieter können ihre eigenen Plug-Ins mithilfe von WinRT-APIs erstellen. Diese werden in der AppContainer-Sandbox ausgeführt, was Schreibvorgänge in Treiber auf Systemebene unproblematischer und weniger komplex macht.</span><span class="sxs-lookup"><span data-stu-id="f3c92-116">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
