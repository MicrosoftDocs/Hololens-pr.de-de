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
ms.openlocfilehash: c88a9af7369a6a9d6fb115fb820c0a4da13eafdc
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865744"
---
# <span data-ttu-id="d9171-104">Netzwerksicherheit</span><span class="sxs-lookup"><span data-stu-id="d9171-104">Network security</span></span>

## <span data-ttu-id="d9171-105">Netzwerkprotokolle</span><span class="sxs-lookup"><span data-stu-id="d9171-105">Network protocols</span></span>

<span data-ttu-id="d9171-106">Das veraltete NetBIOS (Network Basic Input/Output System) wurde in früheren LAN-Szenarien häufig verwendet – meist für die Bereitstellung von Namensauflösung für einen Computer und freigegebene Ordner.</span><span class="sxs-lookup"><span data-stu-id="d9171-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="d9171-107">Im Verlauf der Zeit hat sich NetBIOS aber als anfällig für verschiedene Angriffe erwiesen und seine Bedeutung verringerte sich zugunsten anderer Protokolle, die mehr Sicherheit bieten.</span><span class="sxs-lookup"><span data-stu-id="d9171-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="d9171-108">Um dieses Problem des Sicherheitsrisikos zu beseitigen, hat HoloLens2 den NetBIOS-bezogenen Code aus dem Betriebssystem entfernt.</span><span class="sxs-lookup"><span data-stu-id="d9171-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="d9171-109">TLS-Protokolle (Transport Layer Security) werden ständig weiterentwickelt.</span><span class="sxs-lookup"><span data-stu-id="d9171-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="d9171-110">Um mit den unterschiedlichen Sicherheits-Exploits, die in diesem Bereich aufgedeckt wurden, Schritt zu halten, ist die Computerbranche auf neuere und effektivere Versionen umgestiegen.</span><span class="sxs-lookup"><span data-stu-id="d9171-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="d9171-111">Aufgrund der Zeit, die alle Serverbereitstellungen benötigen, um die neuen TLS-Protokollversionen zu übernehmen, kann ein Fallbackmechanismus implementiert werden, der es erlaubt, dass Client und Server während der Übergangszeit noch mit verschiedenen Standardprotokollversionen kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="d9171-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

<span data-ttu-id="d9171-112">Allerdings erhöhen solche Fallbackmechanismen die Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="d9171-112">However, such fallback mechanisms increase security risks.</span></span> <span data-ttu-id="d9171-113">Da man dieses Problem erkannt hat, wurde in HoloLens2 das Fallback von TLS 1.2 auf TLS 1.1 oder 1.0 deaktiviert, und es gibt keine Benutzerschnittstelle, mit der es wieder aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d9171-113">Understanding this issue, in HoloLens 2 the fallback from TLS 1.2 to TLS 1.1 or 1.0 has been disabled, and there is no user interface to enable it.</span></span> <span data-ttu-id="d9171-114">Darüber hinaus fragt der Client während des TLS-Handshakes nach TLS 1.2 und lässt nicht zu, dass der Server auf eine niedrigere Version herabgestuft wird.</span><span class="sxs-lookup"><span data-stu-id="d9171-114">Furthermore, during the TLS handshake, the client will ask for TLS 1.2, and does not allow the server to downgrade to a lower version.</span></span>

## <span data-ttu-id="d9171-115">Sichere Verbindungen</span><span class="sxs-lookup"><span data-stu-id="d9171-115">Secure connectivity</span></span> 

<span data-ttu-id="d9171-116">Die Windows Defender-Firewall bietet wichtige Funktionen zur Sicherung der Gerätekonnektivität.</span><span class="sxs-lookup"><span data-stu-id="d9171-116">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="d9171-117">Bei HoloLens2 ist die Firewall immer aktiviert, und es gibt keine Möglichkeit, Sie programmgesteuert oder über die Benutzeroberfläche zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d9171-117">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="d9171-118">Remotezugriff und Verbindungsdatenschutz für mobile Clients können über die [UWP VPN-Plug-In-Plattform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041) sichergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d9171-118">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="d9171-119">VPN-Drittanbieter können ihre eigenen Plug-Ins mithilfe von WinRT-APIs erstellen. Diese werden in der AppContainer-Sandbox ausgeführt, was Schreibvorgänge in Treiber auf Systemebene unproblematischer und weniger komplex macht.</span><span class="sxs-lookup"><span data-stu-id="d9171-119">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
