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
ms.openlocfilehash: 9f3950de51e4bfa2a76431a2a070d87aa81ed443
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034337"
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

[Zurück zur Liste](#list)

## <a name="network-troubleshooting"></a>Behandlung von Netzwerkproblemen
Wenn Netzwerkprobleme ein Hindernis für die erfolgreiche Bereitstellung und Verwendung von HoloLens 2 in Ihrer Organisation darstellen, konfigurieren Sie Fiddler und/oder Wireshark, um den HTTP/HTTPS-Datenverkehr zu erfassen und zu analysieren. 

### <a name="configure-fiddler-to-capture-http-traffic"></a>Konfigurieren von Fiddler zum Erfassen von HTTP-Datenverkehr
Fiddler ist ein Webdebugproxy und wird zur Behandlung von HTTP(S)-Problemen verwendet. Er erfasst jede vom Computer eingeleitete HTTP-Anforderung und zeichnet alles auf, was ihr zugeordnet ist. Das Aufdecken von Problemen bei der Endbenutzerauthentifizierung für Ihre HTTPS-Apps steigert die Produktivität und Effizienz Ihrer HoloLens 2-Zielanwendungsfälle. 

#### <a name="prerequisites"></a>Voraussetzungen
 
- HoloLens 2-Geräte und Ihr PC müssen sich im gleichen Netzwerk befinden
- Notieren Sie die IP-Adresse Ihres Computers

#### <a name="install-and-configure-fiddler"></a>Installieren und Konfigurieren von Fiddler

1. [Installieren](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) und starten Sie Fiddler auf Ihrem PC.  
1. Konfigurieren Sie Fiddler auf Ihrem PC so, dass Remotecomputer eine Verbindung herstellen können.
    1. Wechseln Sie zu „Fiddler-Einstellungen“ > „Verbindungen“
    1. Notieren Sie sich den Lauschport für Fiddler (der Standardwert ist 8866)
    1. Aktivieren Sie „Verbindungen von Remotecomputern zulassen“
    1. Klicken Sie auf Speichern.
3. Konfigurieren Sie Fiddler auf Ihrer HoloLens 2 als Proxyserver<sup>1</sup>:
    1. Öffnen Sie das Startmenü, und wählen Sie „Einstellungen“ aus
    1. Wählen Sie „Netzwerk & Internet“ und dann im linken Menü „Proxy“ aus
    1. Scrollen Sie nach unten zu „Manuelle Proxyeinrichtung“, und stellen Sie den Umschalter „Proxyserver verwenden“ auf „Ein“
    1. Geben Sie die IP-Adresse des PCs ein, auf dem Fiddler installiert ist
    1. Geben Sie die oben notierte Portnummer ein (Standardwert: 8866)
    1. Klicken Sie auf Speichern.

<sup>1</sup> Verwenden Sie für Builds ab Version 20279.1006 (Insider und das bevorstehende Release) die folgenden Schritte, um den Proxy zu konfigurieren:
1. Öffnen Sie das Startmenü, und wechseln Sie zur Seite „Eigenschaften“ Ihres WLAN-Netzwerks 
1. Scrollen Sie nach unten zu Proxy
1. Wechseln Sie zu Manuelles Setup
1. Geben Sie die IP-Adresse des PCs ein, auf dem Fiddler installiert ist
1. Geben Sie die oben notierte Portnummer ein. (Der Standardwert ist 8866.)
1. Klicken Sie auf „Übernehmen“
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>Entschlüsseln von HTTPS-Datenverkehr aus HoloLens 2

1. Exportieren Sie auf Ihrem PC das Fiddler-Zertifikat.
    1. Wechseln Sie zu „Fiddler Einstellungen“ > „HTTPS“, und erweitern Sie „Erweiterte Einstellungen“
    2. Klicken Sie auf „Fiddler-Zertifikat exportieren“. Es wird auf Ihrem Desktop gespeichert
    3. Verschieben Sie das Zertifikat in den Ordner „Downloads“ auf Ihrer HoloLens 2

2.  Importieren Sie auf Ihrer HoloLens 2 das Fiddler-Zertifikat.
    1. Wechseln Sie zu „Einstellungen“ > „Update und Sicherheit“ > „Zertifikate“
    2. Klicken Sie auf „Zertifikat installieren“, navigieren Sie zum Ordner „Downloads“, und wählen Sie das Fiddler-Zertifikat aus
    3. Ändern Sie den Speicherort in „Lokaler Computer“
    4. Ändern Sie den Zertifikatspeicher in das Stammverzeichnis (root)
    5. Wählen Sie „Installieren“ aus
    6. Vergewissern Sie sich, dass das Zertifikat in der Liste der Zertifikate angezeigt wird. Wiederholen Sie andernfalls die Schritte oben

#### <a name="inspect-https-sessions"></a>Untersuchen von HTTP(S)-Sitzungen

Auf Ihrem PC zeigt Fiddler die HTTP(S)-Livesitzungen der HoloLens 2 an. Im Bereich „Inspektoren“ in Fiddler können HTTP(S)-Anforderungen/-Antworten in verschiedenen Ansichten angezeigt werden. In der Ansicht „Raw“ wird beispielsweise die unformatierte Anforderung oder Antwort als reiner Text angezeigt. 

### <a name="configure-wireshark-to-capture-network-traffic"></a>Konfigurieren von Wireshark zur Erfassung von Netzwerkverkehr
Wireshark ist ein Tool zur Netzwerkprotokollanalyse und wird verwendet, um TCP/UDP-Datenverkehr von und zu Ihren HoloLens 2-Geräten zu untersuchen. Dadurch können Sie leicht erkennen, welcher Datenverkehr Ihr Netzwerk zu Ihrer HoloLens 2 durchquert, wie viel es davon gibt, wie häufig er ist, wie viel Latenz zwischen bestimmten Hops besteht usw.

#### <a name="prerequisites"></a>Voraussetzungen:
- Der PC muss über Internetzugriff verfügen und die Internetfreigabe über WLAN unterstützen

#### <a name="install-and-configure-wireshark"></a>Installieren und Konfigurieren von Wireshark
1. Installieren Sie [Wireshark](https://www.wireshark.org/#download) auf Ihrem PC 
1. Aktivieren Sie auf Ihrem PC den mobilen Hotspot, um Ihre Internetverbindung über WLAN zu teilen.
1. Starten Sie Wireshark auf Ihrem PC, und erfassen Sie Datenverkehr über die mobile Hotspot-Schnittstelle. 
1. Ändern Sie auf Ihrer HoloLens 2 das WLAN-Netzwerk in den mobilen Hotspot des PCs. Der HoloLens 2-IP-Datenverkehr wird in Wireshark angezeigt.

#### <a name="analyze-wireshark-logs"></a>Analysieren von Wireshark-Protokollen
Wireshark-Filter können beim Herausfiltern der interessierenden Pakete helfen. 

Sehen Sie sich den ursprünglichen [Blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) an.

[Zurück zur Liste](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Anmeldung bei einem zuvor eingerichteten HoloLens-Gerät nicht möglich

Wenn Ihr Gerät zuvor für eine andere Person eingerichtet war, entweder für einen Kunden oder für einen ehemaligen Mitarbeiter, und Sie nicht über deren Kennwort zum Entsperren des Geräts verfügen, können Sie das Gerät mit Intune remote [zurücksetzen](/intune/remote-actions/devices-wipe). Das Gerät führt dann selbst einen Flash aus.  
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
- Das Gerät wurde aufgrund von Inaktivität aus Azure AD entfernt. Für eine effizient verwaltete Umgebung empfehlen wir IT-Administratoren in der Regel, [veraltete, inaktive Geräte aus ihrem Azure AD-Mandanten zu entfernen](/azure/active-directory/devices/manage-stale-devices).

Wenn ein betroffenes Gerät versucht, den Azure AD-Mandanten erneut zu kontaktieren, nachdem es gelöscht wurde, schlägt die Authentifizierung bei Azure AD fehl. Dieser Effekt ist für den Benutzer des Geräts oft nicht sichtbar, da die zwischengespeicherte Anmeldung per PIN dem Benutzer weiterhin die Anmeldung ermöglicht.

### <a name="mitigation"></a>Minderung
Es gibt derzeit keine Möglichkeit, ein gelöschtes HoloLens-Gerät wieder in Azure AD einzubinden. Für betroffene Geräte ist ein sog. Clean-Reflash gemäß den Anweisungen [in diesem Artikel](hololens-recovery.md#clean-reflash-the-device) erforderlich.

[Zurück zur Liste](#list)

## <a name="autopilot-troubleshooting"></a>Behandlung von Autopilot-Problemen

Die folgenden Artikel können eine nützliche Ressource für Sie sein, um mehr Informationen zu erhalten und Autopilot-Probleme zu beheben. Beachten Sie jedoch, dass diese Artikel auf dem Windows 10 Desktop basieren und möglicherweise nicht alle Informationen für die HoloLens gelten:

- [Windows Autopilot: bekannte Probleme](/mem/autopilot/known-issues)
- [Behandeln von Problemen bei der Windows-Geräteregistrierung in Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot: Richtlinienkonflikte](/mem/autopilot/policy-conflicts)

[Zurück zur Liste](#list)

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
Informationen zu HoloLens-Geräten der 1. Generation finden Sie in [diesen häufig gestellten Fragen](hololens1-faq-security.yml).

[Zurück zur Liste](#list)
