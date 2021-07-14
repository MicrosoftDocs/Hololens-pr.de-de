---
title: Behandeln von Problemen bei der Implementierung und Verwaltung von HoloLens 2-Geräten
description: Behandeln von Problemen bei HoloLens 2-Geräten in einer Unternehmensumgebung
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: Problembehandlung
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961500"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="edc81-104">Behandeln von Problemen bei der Implementierung und Verwaltung von Geräten</span><span class="sxs-lookup"><span data-stu-id="edc81-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="edc81-105">In diesem Artikel wird beschrieben, wie Sie verschiedene Probleme und Fragen zur Implementierung und Verwaltung von HoloLens 2 klären können.</span><span class="sxs-lookup"><span data-stu-id="edc81-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="edc81-106">Bevor Sie mit der Problembehandlung beginnen, stellen Sie sicher, dass Ihr Gerät nach Möglichkeit auf **20-40 %** der Akkukapazität aufgeladen ist.</span><span class="sxs-lookup"><span data-stu-id="edc81-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="edc81-107">Die [Akkukontrollleuchten](hololens2-setup.md#lights-that-indicate-the-battery-level) unter dem Netzschalter sind eine schnelle Möglichkeit, die Akkukapazität zu überprüfen, ohne sich beim Gerät anzumelden.</span><span class="sxs-lookup"><span data-stu-id="edc81-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="edc81-108">Behandlung von EAP-Problemen</span><span class="sxs-lookup"><span data-stu-id="edc81-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="edc81-109">Behandlung von WLAN-Problemen</span><span class="sxs-lookup"><span data-stu-id="edc81-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="edc81-110">Behandlung von Netzwerkproblemen</span><span class="sxs-lookup"><span data-stu-id="edc81-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="edc81-111">Anmeldung bei einem zuvor eingerichteten HoloLens-Gerät nicht möglich</span><span class="sxs-lookup"><span data-stu-id="edc81-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="edc81-112">Nach Update auf Windows Holographic 21H1 keine Anmeldung mehr möglich</span><span class="sxs-lookup"><span data-stu-id="edc81-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="edc81-113">Behandlung von Autopilot-Problemen</span><span class="sxs-lookup"><span data-stu-id="edc81-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="edc81-114">Häufig gestellte Fragen zu verwalteten HoloLens-Geräten</span><span class="sxs-lookup"><span data-stu-id="edc81-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="edc81-115">Behandlung von EAP-Problemen</span><span class="sxs-lookup"><span data-stu-id="edc81-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="edc81-116">Prüfen Sie sorgfältig, ob das WLAN-Profil die richtigen Einstellungen aufweist:</span><span class="sxs-lookup"><span data-stu-id="edc81-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="edc81-117">EAP-Typ ist ordnungsgemäß konfiguriert, gängige EAP-Typen: EAP-TLS (13), EAP-TTLS (21) und PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="edc81-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="edc81-118">Der WLAN-SSID-Name ist richtig und stimmt mit der HEX-Zeichenfolge überein.</span><span class="sxs-lookup"><span data-stu-id="edc81-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="edc81-119">Für EAP-TLS enthält TrustedRootCA den SHA-1-Hash des Zertifikats der vertrauenswürdigen Stammzertifizierungsstelle des Servers.</span><span class="sxs-lookup"><span data-stu-id="edc81-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="edc81-120">Auf einem Windows-PC zeigt der Befehl „certutil.exe -dump cert_Dateiname“ die SHA-1-Hashzeichenfolge eines Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="edc81-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="edc81-121">Starten Sie die Aufzeichnung von Netzwerkpaketen in den Protokollen von Zugriffspunkt, Controller oder AAA-Server, um herauszufinden, wo die EAP-Sitzung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="edc81-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="edc81-122">Wenn die von der HoloLens bereitgestellte EAP-Identität nicht erwartet wird, prüfen Sie, ob die Identität korrekt über das WLAN-Profil oder Clientzertifikat bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="edc81-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="edc81-123">Wenn der Server das HoloLens-Clientzertifikat ablehnt, prüfen Sie, ob das erforderliche Clientzertifikat auf dem Gerät bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="edc81-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="edc81-124">Wenn HoloLens das Serverzertifikat ablehnt, prüfen Sie, ob das Zertifikat der Stammzertifizierungsstelle des Servers auf der HoloLens bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="edc81-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="edc81-125">Wenn das Unternehmensprofil über das WLAN-Bereitstellungspaket bereitgestellt wird, sollten Sie das Bereitstellungspaket auf einen Windows 10-PC anwenden.</span><span class="sxs-lookup"><span data-stu-id="edc81-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="edc81-126">Wenn es auch auf einem Windows 10-PC zu einem Fehler kommt, befolgen Sie den Leitfaden zur Problembehandlung der  802.1X-Authentifizierung für Windows-Clients.</span><span class="sxs-lookup"><span data-stu-id="edc81-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="edc81-127">Senden Sie uns Feedback über den Feedback-Hub.</span><span class="sxs-lookup"><span data-stu-id="edc81-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="edc81-128">Zurück zur Liste</span><span class="sxs-lookup"><span data-stu-id="edc81-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="edc81-129">Behandlung von WLAN-Problemen</span><span class="sxs-lookup"><span data-stu-id="edc81-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="edc81-130">Hier sind einige Dinge, die Sie ausprobieren sollten, wenn Sie Ihre HoloLens nicht mit einem WLAN verbinden können:</span><span class="sxs-lookup"><span data-stu-id="edc81-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="edc81-131">Stellen Sie sicher, dass das WLAN aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="edc81-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="edc81-132">Überprüfen Sie dies mit der Startgeste und durch Wählen von „Einstellungen“ > „Netzwerk & Internet“ > WLAN“.</span><span class="sxs-lookup"><span data-stu-id="edc81-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="edc81-133">Wenn das WLAN eingeschaltet ist, schalten Sie es aus und dann wieder ein.</span><span class="sxs-lookup"><span data-stu-id="edc81-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="edc81-134">Verringern Sie den Abstand zum Router oder Zugangspunkt.</span><span class="sxs-lookup"><span data-stu-id="edc81-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="edc81-135">Starten Sie erst Ihren WLAN-Router und dann die HoloLens neu.</span><span class="sxs-lookup"><span data-stu-id="edc81-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="edc81-136">Try connecting again.</span><span class="sxs-lookup"><span data-stu-id="edc81-136">Try connecting again.</span></span>
4. <span data-ttu-id="edc81-137">Wenn keiner dieser Schritte funktioniert, prüfen Sie, ob Ihr Router die neueste Firmware verwendet.</span><span class="sxs-lookup"><span data-stu-id="edc81-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="edc81-138">Diese Informationen finden Sie auf der Website des Herstellers.</span><span class="sxs-lookup"><span data-stu-id="edc81-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="edc81-139">Wenn Sie sich auf dem Gerät bei einem Unternehmens- oder Organisationskonto anmelden, wird möglicherweise eine MDM-Richtlinie (Mobile Device Management, Verwaltung mobiler Geräte) angewendet, sofern diese von Ihrem IT-Administrator konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="edc81-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="network-troubleshooting"></a><span data-ttu-id="edc81-140">Behandlung von Netzwerkproblemen</span><span class="sxs-lookup"><span data-stu-id="edc81-140">Network Troubleshooting</span></span>
<span data-ttu-id="edc81-141">Wenn Netzwerkprobleme ein Hindernis für die erfolgreiche Bereitstellung und Nutzung der HoloLens 2 in Ihrer Organisation darstellen, erfahren Sie, wie Ihnen zwei bekannte Tools zur Netzwerkdiagnose, Fiddler und Wireshark, beim Suchen, Diagnostizieren und Identifizieren von Problemen helfen können.</span><span class="sxs-lookup"><span data-stu-id="edc81-141">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, learn how two well-known network diagnostic tools, Fiddler and Wireshark can help you scan, diagnose, and identify problems.</span></span> <span data-ttu-id="edc81-142">Weitere Informationen finden Sie in diesem [Blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).</span><span class="sxs-lookup"><span data-stu-id="edc81-142">Check out this [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) for more details.</span></span>

[<span data-ttu-id="edc81-143">Zurück zur Liste</span><span class="sxs-lookup"><span data-stu-id="edc81-143">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="edc81-144">Anmeldung bei einem zuvor eingerichteten HoloLens-Gerät nicht möglich</span><span class="sxs-lookup"><span data-stu-id="edc81-144">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="edc81-145">Wenn Ihr Gerät zuvor für eine andere Person eingerichtet war, entweder für einen Kunden oder für einen ehemaligen Mitarbeiter, und Sie nicht über deren Kennwort zum Entsperren des Geräts verfügen, können Sie das Gerät mit Intune remote [zurücksetzen](https://docs.microsoft.com/intune/remote-actions/devices-wipe).</span><span class="sxs-lookup"><span data-stu-id="edc81-145">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](https://docs.microsoft.com/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="edc81-146">Das Gerät führt dann selbst einen Flash aus.</span><span class="sxs-lookup"><span data-stu-id="edc81-146">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="edc81-147">Wenn Sie das Gerät zurücksetzen, stellen Sie sicher, dass **Registrierungszustand und Benutzerkonto beibehalten** deaktiviert bleibt.</span><span class="sxs-lookup"><span data-stu-id="edc81-147">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>
[<span data-ttu-id="edc81-148">Zurück zur Liste</span><span class="sxs-lookup"><span data-stu-id="edc81-148">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="edc81-149">Nach Update auf Windows Holographic 21H1 keine Anmeldung mehr möglich</span><span class="sxs-lookup"><span data-stu-id="edc81-149">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="edc81-150">Symptome</span><span class="sxs-lookup"><span data-stu-id="edc81-150">Symptoms</span></span>
- <span data-ttu-id="edc81-151">Die Anmeldung mit PIN schlägt nach Eingabe der richtigen PIN fehl.</span><span class="sxs-lookup"><span data-stu-id="edc81-151">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="edc81-152">Die Webanmeldemethode schlägt nach erfolgreicher Anmeldung auf der Webseite fehl.</span><span class="sxs-lookup"><span data-stu-id="edc81-152">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="edc81-153">Das Gerät ist im [Azure-Portal](https://portal.azure.com/) unter „Azure Active Directory“ -> „Geräte“ nicht als „In Azure AD eingebunden“ aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="edc81-153">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="edc81-154">Ursache</span><span class="sxs-lookup"><span data-stu-id="edc81-154">Cause</span></span>
<span data-ttu-id="edc81-155">Das betroffene Gerät wurde möglicherweise aus dem Azure AD-Mandanten gelöscht.</span><span class="sxs-lookup"><span data-stu-id="edc81-155">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="edc81-156">Dies kann beispielsweise aus folgenden Gründen geschehen:</span><span class="sxs-lookup"><span data-stu-id="edc81-156">For example, this may happen because:</span></span>

- <span data-ttu-id="edc81-157">Ein Administrator oder Benutzer hat das Gerät im Azure-Portal oder mithilfe von PowerShell gelöscht.</span><span class="sxs-lookup"><span data-stu-id="edc81-157">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="edc81-158">Das Gerät wurde aufgrund von Inaktivität aus Azure AD entfernt.</span><span class="sxs-lookup"><span data-stu-id="edc81-158">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="edc81-159">Für eine effizient verwaltete Umgebung empfehlen wir IT-Administratoren in der Regel, [veraltete, inaktive Geräte aus ihrem Azure AD-Mandanten zu entfernen](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span><span class="sxs-lookup"><span data-stu-id="edc81-159">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="edc81-160">Wenn ein betroffenes Gerät versucht, den Azure AD-Mandanten erneut zu kontaktieren, nachdem es gelöscht wurde, schlägt die Authentifizierung bei Azure AD fehl.</span><span class="sxs-lookup"><span data-stu-id="edc81-160">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="edc81-161">Dieser Effekt ist für den Benutzer des Geräts oft nicht sichtbar, da die zwischengespeicherte Anmeldung per PIN dem Benutzer weiterhin die Anmeldung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="edc81-161">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="edc81-162">Minderung</span><span class="sxs-lookup"><span data-stu-id="edc81-162">Mitigation</span></span>
<span data-ttu-id="edc81-163">Es gibt derzeit keine Möglichkeit, ein gelöschtes HoloLens-Gerät wieder in Azure AD einzubinden.</span><span class="sxs-lookup"><span data-stu-id="edc81-163">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="edc81-164">Für betroffene Geräte ist ein sog. Clean-Reflash gemäß den Anweisungen [in diesem Artikel](hololens-recovery.md#clean-reflash-the-device) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="edc81-164">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="edc81-165">Behandlung von Autopilot-Problemen</span><span class="sxs-lookup"><span data-stu-id="edc81-165">Autopilot Troubleshooting</span></span>

<span data-ttu-id="edc81-166">Die folgenden Artikel können eine nützliche Ressource für Sie sein, um mehr Informationen zu erhalten und Autopilot-Probleme zu beheben. Beachten Sie jedoch, dass diese Artikel auf dem Windows 10 Desktop basieren und möglicherweise nicht alle Informationen für die HoloLens gelten:</span><span class="sxs-lookup"><span data-stu-id="edc81-166">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="edc81-167">Windows Autopilot: bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="edc81-167">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="edc81-168">Behandeln von Problemen bei der Windows-Geräteregistrierung in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="edc81-168">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="edc81-169">Windows Autopilot: Richtlinienkonflikte</span><span class="sxs-lookup"><span data-stu-id="edc81-169">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="edc81-170">Häufig gestellte Fragen zu verwalteten HoloLens-Geräten</span><span class="sxs-lookup"><span data-stu-id="edc81-170">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="edc81-171">Kann ich mit System Center Configuration Manager (SCCM) HoloLens-Geräte verwalten?</span><span class="sxs-lookup"><span data-stu-id="edc81-171">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="edc81-172">Nein.</span><span class="sxs-lookup"><span data-stu-id="edc81-172">No.</span></span> <span data-ttu-id="edc81-173">Sie müssen HoloLens-Geräte mit einem MDM-System verwalten.</span><span class="sxs-lookup"><span data-stu-id="edc81-173">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="edc81-174">Kann ich mit Active Directory Domain Services (AD DS) HoloLens-Benutzerkonten verwalten?</span><span class="sxs-lookup"><span data-stu-id="edc81-174">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="edc81-175">Nein.</span><span class="sxs-lookup"><span data-stu-id="edc81-175">No.</span></span> <span data-ttu-id="edc81-176">Sie müssen Benutzerkonten für HoloLens-Geräte mit Azure Active Directory (Azure AD) verwalten.</span><span class="sxs-lookup"><span data-stu-id="edc81-176">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="edc81-177">Ist für HoloLens eine automatische Registrierung bei ADCS-Lösungen (Automated Data Capture Systems, automatisierte Datenerfassungssysteme) möglich?</span><span class="sxs-lookup"><span data-stu-id="edc81-177">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="edc81-178">Nein.</span><span class="sxs-lookup"><span data-stu-id="edc81-178">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="edc81-179">Kann HoloLens an der integrierten Windows-Authentifizierung teilnehmen?</span><span class="sxs-lookup"><span data-stu-id="edc81-179">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="edc81-180">Nein.</span><span class="sxs-lookup"><span data-stu-id="edc81-180">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="edc81-181">Unterstützt HoloLens Branding?</span><span class="sxs-lookup"><span data-stu-id="edc81-181">Does HoloLens support branding?</span></span>

<span data-ttu-id="edc81-182">Nein.</span><span class="sxs-lookup"><span data-stu-id="edc81-182">No.</span></span> <span data-ttu-id="edc81-183">Sie können dieses Problem allerdings mithilfe einer der folgenden Methoden umgehen:</span><span class="sxs-lookup"><span data-stu-id="edc81-183">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="edc81-184">Erstellen Sie eine benutzerdefinierte App, und aktivieren Sie dann den [Kioskmodus](hololens-kiosk.md).</span><span class="sxs-lookup"><span data-stu-id="edc81-184">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="edc81-185">Die benutzerdefinierte App kann Branding aufweisen und andere Apps starten (z. B. Remote Assist).</span><span class="sxs-lookup"><span data-stu-id="edc81-185">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="edc81-186">Ändern Sie alle Benutzerprofilbilder in Azure AD in Ihr Unternehmenslogo.</span><span class="sxs-lookup"><span data-stu-id="edc81-186">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="edc81-187">Dies ist jedoch möglicherweise nicht für alle Szenarien wünschenswert.</span><span class="sxs-lookup"><span data-stu-id="edc81-187">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="edc81-188">Welche Protokollierungsmöglichkeiten bietet HoloLens 2?</span><span class="sxs-lookup"><span data-stu-id="edc81-188">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="edc81-189">Die Protokollierung ist auf Ablaufverfolgungen beschränkt, die in Entwicklungs- oder Problembehandlungsszenarien erfasst werden können, oder auf Telemetriedaten, die die Geräte an Microsoft-Server senden.</span><span class="sxs-lookup"><span data-stu-id="edc81-189">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="edc81-190">Fragen zum Absichern von HoloLens-Geräten</span><span class="sxs-lookup"><span data-stu-id="edc81-190">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="edc81-191">Lesen Sie [unsere Informationen zur Sicherheit von HoloLens 2](security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="edc81-191">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="edc81-192">Informationen zu HoloLens-Geräten der 1. Generation finden Sie in [diesen häufig gestellten Fragen](hololens1-faq-security.md).</span><span class="sxs-lookup"><span data-stu-id="edc81-192">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.md).</span></span>

[<span data-ttu-id="edc81-193">Zurück zur Liste</span><span class="sxs-lookup"><span data-stu-id="edc81-193">Back to list</span></span>](#list)
