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
# <span data-ttu-id="9a24a-104">Drahtlos und WLAN</span><span class="sxs-lookup"><span data-stu-id="9a24a-104">Wireless and Wi-Fi</span></span>

<span data-ttu-id="9a24a-105">Die WLAN-Konnektivität für HoloLens 2 unterstützt ein beeindruckendes Spektrum der neuesten WLAN-Sicherheitsstandards, wie z. B.:</span><span class="sxs-lookup"><span data-stu-id="9a24a-105">HoloLens 2 Wireless LAN connectivity supports an impressive range of the latest Wi-Fi security standards, such as:</span></span>
  * <span data-ttu-id="9a24a-106">WPA2 (WLAN-geschützter Zugriff 2)</span><span class="sxs-lookup"><span data-stu-id="9a24a-106">WPA2 (Wi-Fi Protected Access 2)</span></span>  
  * <span data-ttu-id="9a24a-107">TEAP (Tunnel Extensible Authentication Protocol)</span><span class="sxs-lookup"><span data-stu-id="9a24a-107">TEAP (Tunnel Extensible Authentication Protocol)</span></span>  
  * <span data-ttu-id="9a24a-108">OWE (Opportunistic Wireless Encryption)</span><span class="sxs-lookup"><span data-stu-id="9a24a-108">OWE (Opportunistic Wireless Encryption)</span></span>

<span data-ttu-id="9a24a-109">TEAP, die nächste Generation von Netzwerkauthentifizierung in Unternehmen, bietet die Möglichkeit, mehrere Anmeldeinformationen in einer einzigen Transaktion sicher zu verketten.</span><span class="sxs-lookup"><span data-stu-id="9a24a-109">TEAP, the next generation of enterprise network authentication, provides the ability to securely chain multiple credentials into a single transaction.</span></span>  <span data-ttu-id="9a24a-110">Auf diese Weise können Administratoren eine stärkere Sicherheitshaltung erzwingen – eine, die während der gleichen Authentifizierungstransaktion gültige Identitäten für Computer und Benutzer erfordert.</span><span class="sxs-lookup"><span data-stu-id="9a24a-110">This allows administrators to enforce a stronger security stance – one that requires valid identities for both machine and user during the same authentication transaction.</span></span>

<span data-ttu-id="9a24a-111">HoloLens 2 bietet moderne Drahtlos- und WLAN-Protokolle, die Kunden maximalen Support bieten.</span><span class="sxs-lookup"><span data-stu-id="9a24a-111">HoloLens 2 has modern wireless and Wi-Fi protocols that enable customers with maximum support.</span></span> <span data-ttu-id="9a24a-112">Der HoloLens 2-Funk ist eine Qualcomm WCN3990-Lösung, die eine erstklassige Funkleistung bietet.</span><span class="sxs-lookup"><span data-stu-id="9a24a-112">The HoloLens 2 radio is a Qualcomm WCN3990 solution delivering a premium radio experience.</span></span> <span data-ttu-id="9a24a-113">Das unterstützte WLAN ist 802.11 ac/n.</span><span class="sxs-lookup"><span data-stu-id="9a24a-113">The Wi-Fi supported is 802.11 ac/n.</span></span> <span data-ttu-id="9a24a-114">Der Frequenzbereich ist nicht konfigurierbar und vom jeweiligen Verwendungsland abhängig.</span><span class="sxs-lookup"><span data-stu-id="9a24a-114">The frequency range is not user configurable and depends on the country of use.</span></span> <span data-ttu-id="9a24a-115">In den USA verwendet Wi-Fi sowohl 2,4-GHz-Kanäle (1-11) als auch 5-GHz-Kanäle (36-64, 100-165).</span><span class="sxs-lookup"><span data-stu-id="9a24a-115">In the United States, Wi-Fi uses both 2.4GHz (1-11) channels and 5GHz (36-64, 100-165) channels.</span></span> <span data-ttu-id="9a24a-116">Weder der Benutzer noch das Gerät können Zulassungs- und Verweigerungslisten für bestimmte Frequenzen erstellen.</span><span class="sxs-lookup"><span data-stu-id="9a24a-116">Neither user nor device can make allow/deny lists for specific frequencies.</span></span> <span data-ttu-id="9a24a-117">Bluetooth SIC Core 5.0 verfügt über eine dedizierte 2,4-GHz-Antenne für Bluetooth, die nicht mit WLAN geteilt wird.</span><span class="sxs-lookup"><span data-stu-id="9a24a-117">Bluetooth SIC Core 5.0 has a dedicated 2.4GHz antenna for Bluetooth which is not shared with Wi-Fi.</span></span> <span data-ttu-id="9a24a-118">Der Softwarestapel von HoloLens 2 unterstützt mehrere Protokolle und Profile, einschließlich HID, HOGP, A2DP und GATT.</span><span class="sxs-lookup"><span data-stu-id="9a24a-118">HoloLens 2’s software stack supports several protocols and profiles including HID, HOGP, A2DP, and GATT.</span></span> 

<span data-ttu-id="9a24a-119">IT-Administratoren haben die folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="9a24a-119">IT admins can:</span></span> 
  * <span data-ttu-id="9a24a-120">Aktivieren oder Einschränken des [Bluetooth-Zugriffs](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth).</span><span class="sxs-lookup"><span data-stu-id="9a24a-120">Enable or restrict  [Bluetooth access](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)</span></span>
  * <span data-ttu-id="9a24a-121">Festlegen von [lokalen Bluetooth-Gerätenamen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename).</span><span class="sxs-lookup"><span data-stu-id="9a24a-121">Set [local Bluetooth device names](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)</span></span>
  * <span data-ttu-id="9a24a-122">Zulassen, dass [Geräte auffindbar sind](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode).</span><span class="sxs-lookup"><span data-stu-id="9a24a-122">Allow [devices to be discoverable](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)</span></span>
  * <span data-ttu-id="9a24a-123">Zulassen/Verweigern von [WLAN-Verbindungen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi).</span><span class="sxs-lookup"><span data-stu-id="9a24a-123">Allow/disallow [Wi-Fi connections](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)</span></span> 
  * <span data-ttu-id="9a24a-124">Zulassen/Verweigern einer [WLAN-Verbindung außerhalb von auf dem MDM-Server eingerichteten Netzwerken](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration).</span><span class="sxs-lookup"><span data-stu-id="9a24a-124">Allow or disallow [connecting to Wi-Fi outside of MDM server-installed networks](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)</span></span>
