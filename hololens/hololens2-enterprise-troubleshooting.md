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
# <a name="troubleshooting-implementation-and-managed-devices"></a>Behandeln von Problemen bei der Implementierung und Verwaltung von Geräten 

In diesem Artikel wird beschrieben, wie Sie verschiedene Probleme und Fragen zur Implementierung und Verwaltung von HoloLens 2 klären können.

>[!IMPORTANT]
> Bevor Sie mit der Problembehandlung beginnen, stellen Sie sicher, dass Ihr Gerät nach Möglichkeit auf **20-40 %** der Akkukapazität aufgeladen ist. Die [Akkukontrollleuchten](hololens2-setup.md#lights-that-indicate-the-battery-level) unter dem Netzschalter sind eine schnelle Möglichkeit, die Akkukapazität zu überprüfen, ohne sich beim Gerät anzumelden.


<a id="list"></a>
- [Behandlung von EAP-Problemen](#eap-troubleshooting)
- [Behandlung von WLAN-Problemen](#wi-fi-troubleshooting)
- [Behandlung von Netzwerkproblemen](#network-troubleshooting)
- [Anmeldung bei einem zuvor eingerichteten HoloLens-Gerät nicht möglich](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Nach Update auf Windows Holographic 21H1 keine Anmeldung mehr möglich](#cant-login-after-updating-to-windows-holographic-21h1)
- [Behandlung von Autopilot-Problemen](#autopilot-troubleshooting)
- [Häufig gestellte Fragen zu verwalteten HoloLens-Geräten](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>Behandlung von EAP-Problemen
1. Prüfen Sie sorgfältig, ob das WLAN-Profil die richtigen Einstellungen aufweist:
    - EAP-Typ ist ordnungsgemäß konfiguriert, gängige EAP-Typen: EAP-TLS (13), EAP-TTLS (21) und PEAP (25).
    - Der WLAN-SSID-Name ist richtig und stimmt mit der HEX-Zeichenfolge überein.
    - Für EAP-TLS enthält TrustedRootCA den SHA-1-Hash des Zertifikats der vertrauenswürdigen Stammzertifizierungsstelle des Servers. Auf einem Windows-PC zeigt der Befehl „certutil.exe -dump cert_Dateiname“ die SHA-1-Hashzeichenfolge eines Zertifikats.
2. Starten Sie die Aufzeichnung von Netzwerkpaketen in den Protokollen von Zugriffspunkt, Controller oder AAA-Server, um herauszufinden, wo die EAP-Sitzung fehlschlägt.
    - Wenn die von der HoloLens bereitgestellte EAP-Identität nicht erwartet wird, prüfen Sie, ob die Identität korrekt über das WLAN-Profil oder Clientzertifikat bereitgestellt wurde.
    - Wenn der Server das HoloLens-Clientzertifikat ablehnt, prüfen Sie, ob das erforderliche Clientzertifikat auf dem Gerät bereitgestellt wurde.
    - Wenn HoloLens das Serverzertifikat ablehnt, prüfen Sie, ob das Zertifikat der Stammzertifizierungsstelle des Servers auf der HoloLens bereitgestellt wurde.
3. Wenn das Unternehmensprofil über das WLAN-Bereitstellungspaket bereitgestellt wird, sollten Sie das Bereitstellungspaket auf einen Windows 10-PC anwenden. Wenn es auch auf einem Windows 10-PC zu einem Fehler kommt, befolgen Sie den Leitfaden zur Problembehandlung der  802.1X-Authentifizierung für Windows-Clients.
4. Senden Sie uns Feedback über den Feedback-Hub.

[Zurück zur Liste](#list)

## <a name="wi-fi-troubleshooting"></a>Behandlung von WLAN-Problemen

Hier sind einige Dinge, die Sie ausprobieren sollten, wenn Sie Ihre HoloLens nicht mit einem WLAN verbinden können:

1. Stellen Sie sicher, dass das WLAN aktiviert ist. Überprüfen Sie dies mit der Startgeste und durch Wählen von „Einstellungen“ > „Netzwerk & Internet“ > WLAN“. Wenn das WLAN eingeschaltet ist, schalten Sie es aus und dann wieder ein.
2. Verringern Sie den Abstand zum Router oder Zugangspunkt.
3. Starten Sie erst Ihren WLAN-Router und dann die HoloLens neu. Try connecting again.
4. Wenn keiner dieser Schritte funktioniert, prüfen Sie, ob Ihr Router die neueste Firmware verwendet. Diese Informationen finden Sie auf der Website des Herstellers.

Wenn Sie sich auf dem Gerät bei einem Unternehmens- oder Organisationskonto anmelden, wird möglicherweise eine MDM-Richtlinie (Mobile Device Management, Verwaltung mobiler Geräte) angewendet, sofern diese von Ihrem IT-Administrator konfiguriert wurde.

## <a name="network-troubleshooting"></a>Behandlung von Netzwerkproblemen
Wenn Netzwerkprobleme ein Hindernis für die erfolgreiche Bereitstellung und Nutzung der HoloLens 2 in Ihrer Organisation darstellen, erfahren Sie, wie Ihnen zwei bekannte Tools zur Netzwerkdiagnose, Fiddler und Wireshark, beim Suchen, Diagnostizieren und Identifizieren von Problemen helfen können. Weitere Informationen finden Sie in diesem [Blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).

[Zurück zur Liste](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Anmeldung bei einem zuvor eingerichteten HoloLens-Gerät nicht möglich

Wenn Ihr Gerät zuvor für eine andere Person eingerichtet war, entweder für einen Kunden oder für einen ehemaligen Mitarbeiter, und Sie nicht über deren Kennwort zum Entsperren des Geräts verfügen, können Sie das Gerät mit Intune remote [zurücksetzen](https://docs.microsoft.com/intune/remote-actions/devices-wipe). Das Gerät führt dann selbst einen Flash aus.  
> [!IMPORTANT]
> Wenn Sie das Gerät zurücksetzen, stellen Sie sicher, dass **Registrierungszustand und Benutzerkonto beibehalten** deaktiviert bleibt.
[Zurück zur Liste](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Nach Update auf Windows Holographic 21H1 keine Anmeldung mehr möglich

### <a name="symptoms"></a>Symptome
- Die Anmeldung mit PIN schlägt nach Eingabe der richtigen PIN fehl.
- Die Webanmeldemethode schlägt nach erfolgreicher Anmeldung auf der Webseite fehl.
- Das Gerät ist im [Azure-Portal](https://portal.azure.com/) unter „Azure Active Directory“ -> „Geräte“ nicht als „In Azure AD eingebunden“ aufgeführt.

### <a name="cause"></a>Ursache
Das betroffene Gerät wurde möglicherweise aus dem Azure AD-Mandanten gelöscht. Dies kann beispielsweise aus folgenden Gründen geschehen:

- Ein Administrator oder Benutzer hat das Gerät im Azure-Portal oder mithilfe von PowerShell gelöscht.
- Das Gerät wurde aufgrund von Inaktivität aus Azure AD entfernt. Für eine effizient verwaltete Umgebung empfehlen wir IT-Administratoren in der Regel, [veraltete, inaktive Geräte aus ihrem Azure AD-Mandanten zu entfernen](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).

Wenn ein betroffenes Gerät versucht, den Azure AD-Mandanten erneut zu kontaktieren, nachdem es gelöscht wurde, schlägt die Authentifizierung bei Azure AD fehl. Dieser Effekt ist für den Benutzer des Geräts oft nicht sichtbar, da die zwischengespeicherte Anmeldung per PIN dem Benutzer weiterhin die Anmeldung ermöglicht.

### <a name="mitigation"></a>Minderung
Es gibt derzeit keine Möglichkeit, ein gelöschtes HoloLens-Gerät wieder in Azure AD einzubinden. Für betroffene Geräte ist ein sog. Clean-Reflash gemäß den Anweisungen [in diesem Artikel](hololens-recovery.md#clean-reflash-the-device) erforderlich.

## <a name="autopilot-troubleshooting"></a>Behandlung von Autopilot-Problemen

Die folgenden Artikel können eine nützliche Ressource für Sie sein, um mehr Informationen zu erhalten und Autopilot-Probleme zu beheben. Beachten Sie jedoch, dass diese Artikel auf dem Windows 10 Desktop basieren und möglicherweise nicht alle Informationen für die HoloLens gelten:

- [Windows Autopilot: bekannte Probleme](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Behandeln von Problemen bei der Windows-Geräteregistrierung in Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot: Richtlinienkonflikte](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a>Häufig gestellte Fragen zu verwalteten HoloLens-Geräten

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Kann ich mit System Center Configuration Manager (SCCM) HoloLens-Geräte verwalten?

Nein. Sie müssen HoloLens-Geräte mit einem MDM-System verwalten.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Kann ich mit Active Directory Domain Services (AD DS) HoloLens-Benutzerkonten verwalten?

Nein. Sie müssen Benutzerkonten für HoloLens-Geräte mit Azure Active Directory (Azure AD) verwalten.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>Ist für HoloLens eine automatische Registrierung bei ADCS-Lösungen (Automated Data Capture Systems, automatisierte Datenerfassungssysteme) möglich?

Nein.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>Kann HoloLens an der integrierten Windows-Authentifizierung teilnehmen?

Nein.

### <a name="does-hololens-support-branding"></a>Unterstützt HoloLens Branding?

Nein. Sie können dieses Problem allerdings mithilfe einer der folgenden Methoden umgehen:

- Erstellen Sie eine benutzerdefinierte App, und aktivieren Sie dann den [Kioskmodus](hololens-kiosk.md). Die benutzerdefinierte App kann Branding aufweisen und andere Apps starten (z. B. Remote Assist).  
- Ändern Sie alle Benutzerprofilbilder in Azure AD in Ihr Unternehmenslogo. Dies ist jedoch möglicherweise nicht für alle Szenarien wünschenswert.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Welche Protokollierungsmöglichkeiten bietet HoloLens 2?

Die Protokollierung ist auf Ablaufverfolgungen beschränkt, die in Entwicklungs- oder Problembehandlungsszenarien erfasst werden können, oder auf Telemetriedaten, die die Geräte an Microsoft-Server senden.

## <a name="questions-about-securing-hololens-devices"></a>Fragen zum Absichern von HoloLens-Geräten

Lesen Sie [unsere Informationen zur Sicherheit von HoloLens 2](security-overview.md).
Informationen zu HoloLens-Geräten der 1. Generation finden Sie in [diesen häufig gestellten Fragen](hololens1-faq-security.md).

[Zurück zur Liste](#list)
