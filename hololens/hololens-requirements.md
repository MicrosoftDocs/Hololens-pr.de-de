---
title: Einrichten von HoloLens in einer kommerziellen Umgebung
description: Erfahren Sie mehr über die Bereitstellung und Verwaltung von HoloLens in Unternehmensumgebungen, einschließlich Infrastruktur, Azure Active Directory und Verwaltung mobiler Geräte.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
ms.openlocfilehash: 9458a6fd02cf96dd265580cb099e39fa221d4206
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284046"
---
# Bereitstellung und Verwaltung von HoloLens 2 Enterprise

Diese Übersicht soll it-Experten dabei helfen, Überlegungen zur Bereitstellung und Verwaltung von Microsoft HoloLens 2-Geräten im Unternehmen zu verstehen.

HoloLens 2 wird unter Windows 10 Holographic ausgeführt, das Organisationen stabile, flexible integrierte Technologien für die Verwaltung mobiler Geräte und Apps bietet. Windows 10 Holographic unterstützt die End-to-End-Verwaltung des Gerätelebenszyklus, um Unternehmen die Kontrolle über ihre Geräte, Daten und Apps zu geben. HoloLens 2 kann problemlos in standardmäßige Lebenszykluspraktiken integriert werden, von der Geräteregistrierung, Konfiguration und Anwendungsverwaltung bis zur Wartung und Einstellung mithilfe einer umfassenden Verwaltungslösung für mobile Geräte.

## Vorbereiten

Während Sie sich auf die Bereitstellung von HoloLens 2 in Ihrer Unternehmensumgebung vorbereiten, sollten Sie verschiedene Aspekte überprüfen und verstehen, während Sie mit der Planung von Skalierungsbereitstellungen von HoloLens 2 beginnen.

### Infrastructure Essentials

Für HoloLens 2 in einem Unternehmensbereitstellungsszenario sind bestimmte grundlegende Infrastrukturdienste erforderlich, um den vollständigen Satz von Funktionen zu unterstützen. HoloLens 2 wurde im Sinne der [modernen mobilen Geräteverwaltung](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) für die Bereitstellung und Verwaltung entwickelt. Mit Azure AD Join + MDM als primäres Mittel, um dies in einer ständig wachsenden mobilen Belegschaft zu erreichen. Die folgenden Themen bieten eine kurze Übersicht über die einzelnen Infrastrukturkomponenten, die bei der Bereitstellungsplanung für HoloLens 2 berücksichtigt werden sollten.

### Azure Active Directory
AzureAD ist ein cloudbasierter Verzeichnisdienst zur Identitäts- und Zugriffsverwaltung. Dank der Möglichkeit zur Integration in bereits vorhandene lokale Verzeichnisse lässt sich eine Hybrid-Identitätslösung realisieren. Organisationen, die Microsoft Office 365 oder Intune verwenden, verwenden bereits Azure AD mit drei Editionen: Kostenlos, Premium P1 und Premium P2 (siehe [Azure Active Directory-Editionen).](https://azure.microsoft.com/documentation/articles/active-directory-editions/) Alle Editionen unterstützen die Azure AD-Geräteregistrierung, Premium P1 ist jedoch erforderlich, um die automatische Registrierung von MDM zu aktivieren. HoloLens 2 erfordert Azure Active Directory Join, um die meisten Features und Funktionen auf Unternehmensebene zu ermöglichen.

> [!NOTE]
> Der lokale Active Directory Join wird auf HoloLens 2 nicht unterstützt.

### Verwaltung mobiler Geräte
HoloLens 2 wurde speziell für die Verwaltung durch Mobile Device Management (MDM)-Systeme in einer Unternehmensumgebung entwickelt. Microsoft [Intune,](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)Teil von Enterprise Mobility + Security, ist ein cloudbasiertes MDM-System, das Geräte im Unternehmen verwaltet. Wie Office 365 verwendet Intune Azure AD für die Identitätsverwaltung, sodass Mitarbeiter die gleichen Anmeldeinformationen verwenden, um Geräte in Intune zu registrieren, die sie zum Anmelden bei Office 365 verwenden. Mehrere MDM-Systeme unterstützen Windows10, und die meisten unterstützen Bereitstellungsszenarien für persönliche und unternehmenseigene Geräte. MdM-Systeme können auch Anwendungsbereitstellungen und Updates für HoloLens 2 verwalten. Andere MDM-Anbieter, die HoloLens 2 unterstützen, sind derzeit: AirWatch, MobileIron und andere. Alle #A0 haben den gleichen Zugriff auf Konfigurationsdienstanbieter (CSP) für die Geräteverwaltung von Windows 10, wodurch #A1 die Freiheit haben, das System auszuwählen, das ihren Verwaltungsanforderungen am besten entspricht, ob Microsoft Intune oder ein #A2 eines Drittanbieters.

> [!NOTE]
> Herkömmliche lokale PC-Verwaltungssysteme wie System Center Configuration Manager werden auf HoloLens 2 nicht unterstützt.

### Windows Update for Business
Microsoft hat Windows Update for Business entwickelt, um IT-Administratoren weitere Verwaltungsfunktionen rund um Windows Update bereitzustellen, wie beispielsweise die Möglichkeit, Updates für Gruppen von Geräten bereitzustellen oder Wartungszeitfenster für die Installation von Updates festzulegen. Ausführliche Informationen [zur Verwaltung von HoloLens](https://docs.microsoft.com/hololens/hololens-updates) 2-Updates finden Sie in der Dokumentation zu HoloLens-Updates.

### Zertifikate
HoloLens 2 unterstützt die Bereitstellung von Zertifikaten über MDM, wenn Ihre Umgebung Zertifikate für die Netzwerkauthentifizierung von Corp Wi-Fi oder den Zugriff auf andere Ressourcen erfordert. Einige KONFIGURATIONen der MDM-Infrastruktur sind möglicherweise erforderlich, um Zertifikatbereitstellungen für HoloLens 2 zu ermöglichen. Erfahren Sie, wie [Sie Zertifikate und Netzwerkprofile für HoloLens 2 vorbereiten.](https://docs.microsoft.com/hololens/hololens-certificates-network) Wenn Sie Intune verwenden, sehen Sie sich die [Konfigurationsdetails zur Zertifizierung](https://docs.microsoft.com/mem/intune/protect/certificates-configure) an.

## Konfigurieren

MdM-Administratoren können Richtlinieneinstellungen auf jedem Unternehmensgerät definieren und implementieren, das in einem MDM-System registriert ist. Welche Konfigurationseinstellungen Sie verwenden, unterscheidet sich je nach Bereitstellungsszenario. In Windows 10 sind Konfigurationsdienstanbieter (Configuration Service Providers, CSP) eine Schnittstelle zum Lesen, Festlegen, Ändern oder Löschen von Konfigurationseinstellungen auf dem Gerät. Diese Einstellungen sind mit Registrierungsschlüsseln oder Dateien verknüpft. Weitere Informationen zu Windows 10-Geräteverwaltungs-CSPs für HoloLens 2 finden Sie in der vollständigen Liste der [csPs, die auf HoloLens-Geräten unterstützt werden.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)

HoloLens 2 unterstützt auch das Festlegen einer begrenzten Gruppe von #A0 über benutzerdefinierte Bereitstellungspakete. Bereitstellungspakete werden in der Regel für nicht von MDM verwaltete Geräte genutzt und müssen manuell auf jedes Gerät angewendet werden. Ausführliche Informationen [zum Erstellen benutzerdefinierter](https://docs.microsoft.com/hololens/hololens-provisioning) Bereitstellungspakete finden Sie in der HoloLens-Bereitstellungsdokumentation.

> [!NOTE]
> HoloLens 2 unterstützt [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)und bietet einen einfachen und einfachen Prozess für die Verwaltung Ihrer Windows 10-Gerätekonfigurationen im Unternehmen.

### Identitätsverwaltung

Mitarbeiter können nur ein Konto verwenden, um ein Gerät zu initialisieren, sodass es&#39;, dass Ihre Organisation steuert, welches Konto zuerst aktiviert wird. Die Wahl des Kontos bestimmt, wer das Gerät kontrolliert und welche Verwaltungsfunktionen Ihnen zur Verfügung stehen. HoloLens 2 unterstützt drei Kontotypen: lokales Benutzerkonto, persönliches Microsoft-Konto und Azure Active Directory-Konten. Es wird dringend empfohlen, Azure Active Directory für Ihre Enterprise Identity Management-Lösung zu nutzen, da sie die vollständigen Funktionen auf Ihren HoloLens 2-Geräten ermöglicht. Weitere Informationen [zu Identitäten für HoloLens](https://docs.microsoft.com/hololens/hololens-identity) 2 finden Sie in der HoloLens-Identität.

### Netzwerk und Konnektivität

Da HoloLens 2 ein erstes Cloudgerät ist, ist netzwerkzugriff auf Onlineressourcen erforderlich, um alle Funktionen und Funktionen verfügbar zu machen. Wenn Sie HoloLens 2-Geräte mit Verbindung mit Ihrem Unternehmensintranetnetzwerk bereitstellen, müssen Sie möglicherweise Ihre Proxy-/Firewallregeln aktualisieren, um den Zugriff auf HoloLens 2-Clouddienste zu ermöglichen. Weitere Informationen finden Sie in der Liste der allgemeinen [Endpunkte für das HoloLens 2-Betriebssystem.](https://docs.microsoft.com/hololens/hololens-offline) Möglicherweise ist der Zugriff auf zusätzliche Endpunkte erforderlich, damit Anwendungen oder andere Clouddienste auf HoloLens 2 erfolgreich ausgeführt werden können.

Einige allgemeine HoloLens 2-Dienste, die zusätzlichen Endpunktzugriff erfordern, sind wie folgt:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365-Handbücher](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 Remote Assist (O365 Teams-Infrastruktur)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### Zertifikatbereitstellung

Wenn Zertifikate für den Zugriff auf Unternehmensnetzwerke Wi-Fi oder andere Dienste innerhalb Ihrer Organisation erforderlich sind, unterstützt HoloLens 2 die Bereitstellung von Benutzer- und Gerätezertifikaten über MDM. Hinweis: Ihre MDM-Lösung erfordert möglicherweise eine zusätzliche Infrastrukturkonfiguration, um Zertifikate auf Windows 10-Geräten bereitstellen zu können.

### Sicherheitsüberprüfung

Die meisten Unternehmens-IT-Abteilungen müssen neue Geräte, die in einem Unternehmensnetzwerk bereitgestellt werden, bewerten und überprüfen. Wenn Ihre Organisation eine Sicherheitsüberprüfung von HoloLens 2 benötigt, finden Sie weitere Details, die Sie beim Abrufen von [Sicherheitsgenehmigungen unterstützen können.](https://docs.microsoft.com/hololens/security-overview)

### Allgemeine HoloLens 2-Geräteeinstellungen

Bei der Bereitstellung von HoloLens 2-Geräten in einer Unternehmensumgebung gibt es eine Reihe gängiger Gerätekonfigurationen, die bei der Planung Ihrer Bereitstellung von HoloLens 2 berücksichtigt werden können. In dieser Liste werden Konfigurationen und Einstellungen aufgeführt, die sich als ziemlich üblich herausgefunden haben und die keine vollständige Liste der verfügbaren Optionen enthalten:

| Geräteeinstellung | Kurze Beschreibung.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Hardwareeinschränkungen](hololens-requirements.md#hardware-restrictions)               | Hardwareeinschränkungen verringern die Konnektivität und unterstützen den Datenschutz.                        |
| [WLAN-Profile](hololens-requirements.md#wi-fi-profiles)               | Konfigurieren Wi-Fi Profile ohne Benutzereingriff oder -interaktion.                              |
| [Zertifikate](hololens-requirements.md#certificates-1)               | Bereitstellen der Konto- und/oder Wi-Fi Authentifizierung, der VPN-Verschlüsselung und der SSL-Verschlüsselung von Webinhalten. |
| [Proxy](hololens-requirements.md#proxy)              | Verwalten des internen Datenverkehrs.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Steuern des Zugriffs auf Apps und Ressourcen im Intranet des Unternehmens.                               |
| [Kioskmodus](hololens-requirements.md#kiosk-mode) | Schränkt die Anwendungen ein, die Benutzern über die Benutzeroberfläche angezeigt werden. |

#### Hardwareeinschränkungen

HoloLens 2 verwendet die moderne Technologie, die beliebte Hardwarefeatures wie Kameras, Mikrofone, Lautsprecher, USB-Schnittstellen, Bluetooth und WLAN umfasst. Die Verfügbarkeit dieser Features kann mit Hardwareeinschränkungen gesteuert werden.

Im Folgenden sind die am häufigsten verwendeten MDM-Einstellungen aufgeführt, die HoloLens 2 zum Konfigurieren von Hardwareeinschränkungen unterstützt. Einige diese Hardwareeinschränkungen sorgen für Konnektivität und tragen zum Datenschutz bei.

- [**WLAN zulassen:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Gibt an, ob Benutzer das Wi-Fi auf ihren Geräten aktivieren und verwenden können.
- [**Lassen Sie die USB-Verbindung zu:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Gibt an, ob die USB-Verbindung aktiviert ist (&#39;keine Auswirkungen auf die USB-Aufladung)
- [**Zulassen Bluetooth:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Gibt an, ob Benutzer das Bluetooth auf ihren Geräten aktivieren und verwenden können.

Weitere Informationen zu anderen [allgemeinen Geräteeinschränkungen.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### WLAN-Profile

Die meisten WLAN-Netzwerke von Unternehmen erfordern Zertifikate und andere komplexe Informationen, um den Zugriff einzuschränken und zu schützen. Diese erweiterten Wi-Fi können für typische Benutzer nur schwer konfiguriert werden, aber die Systeme von MDM können diese Wi-Fi ohne Benutzereingriff vollständig konfigurieren. Sie können mehrere WLAN-Profile in Ihrem MDM-System erstellen.

Weitere Informationen zu den Wi-Fi für Windows 10 finden Sie unter [Enterprise Profile WiFi settings](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile).

#### Zertifikate

Zertifikate tragen zur Verbesserung der Sicherheit bei, indem sie die Kontoauthentifizierung, Wi-Fi, die VPN-Verschlüsselung und die SSL-Verschlüsselung von Webinhalten bereitstellen. Administratoren können Zertifikate auf Geräten zwar über Bereitstellungspakete manuell verwalten, es ist jedoch eine bewährte Methode&#39;diese Zertifikate über ihren gesamten Lebenszyklus hinweg mithilfe Ihres MDM-Systems zu verwalten – von der Registrierung über die Verlängerung bis hin zur Sperrung. Ihr #A0 kann diese Zertifikate automatisch auf den Geräten&#39; Zertifikatspeichern bereitstellen, nachdem Sie das Gerät registriert haben (solange das #A1 das Simple Certificate Enrollment Protocol (SCEP) oder public Key Cryptography Standards #12 (PKCS#12)) unterstützt. MDM kann auch registrierte Clientzertifikate abfragen und löschen oder eine neue Registrierungsanforderung auslösen, bevor das aktuelle Zertifikat abläuft.

Erfahren Sie mehr über die [Vorbereitung von Zertifikaten und Netzwerkprofilen für HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### Proxy

Die meisten Unternehmensintranetnetzwerke nutzen einen Proxy zum Verwalten des internen Datenverkehrs. Mit HoloLens 2 können Sie einen Proxyserver für Ethernet- und Wi-Fi konfigurieren. Diese Einstellungen gelten nicht für VPN-Verbindungen.

Weitere Informationen zu Proxyeinstellungen für Windows 10 finden Sie unter [NetworkProxy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

#### VPN

Organisationen verwenden häufig ein VPN, um den Zugriff auf Apps und Ressourcen im Intranet&#39;Unternehmens zu steuern. HoloLens 2 unterstützt SSL-VPN-Verbindungen, die ein herunterladbares Plug-In aus dem Microsoft Store erfordern und spezifisch für den jeweiligen VPN-Anbieter sind.

Weitere Informationen zu VPN-Profilen finden Sie unter [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### Kioskmodus

Sie können ein HoloLens 2-Gerät so konfigurieren, dass es als ein Gerät mit festem Zweck, auch Kiosk genannt, funktioniert, indem Sie das Gerät für die Ausführung im Kioskmodus konfigurieren. Der Kioskmodus schränkt die Anwendungen (oder Benutzer) ein, die auf dem Gerät verfügbar sind. Der Kioskmodus ist ein praktisches Feature, mit dem Sie ein HoloLens 2-Gerät für Geschäfts-Apps verwenden oder das HoloLens 2-Gerät in einer App-Demo verwenden können.

Weitere Informationen zum Konfigurieren einer HoloLens 2 im Kioskmodus finden Sie unter Einrichten von [HoloLens als Kiosk](https://docs.microsoft.com/hololens/hololens-kiosk)

## Bereitstellen

### Registrierung von MDM-Geräten

Für Unternehmensbereitstellungen wird empfohlen, Geräte nur mit Azure AD-Beitritt und automatischer MDM-Registrierung (Azure AD+MDM) als Unternehmensgeräte bei MDM zu registrieren. [](https://docs.microsoft.com/hololens/hololens-enroll-mdm) Dies erfordert Azure AD Premium und unterstützt die automatische Registrierung bei mehreren MDM-Anbietern, einschließlich Intune.

Erfahren Sie mehr über die Self-Deploying-Registrierungsmethode [Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot).

### Anwendungsbereitstellung

Die Benutzerproduktivität auf mobilen Geräten wird oft durch Apps ermöglicht.

Mithilfe der Universellen Windows-Plattform (UWP) für Windows-Apps ermöglicht Windows10 das Entwickeln von Apps, die nahtlos geräteübergreifend funktionieren.

Es gibt mehrere Möglichkeiten zum Bereitstellen von Anwendungen auf HoloLens 2-Geräten. Apps können direkt über MDM, den Microsoft Store für Unternehmen oder über ein Bereitstellungspaket bereitgestellt werden. Weitere Informationen [finden](https://docs.microsoft.com/hololens/app-deploy-overview) Sie in der Dokumentation zur App-Bereitstellung.

> [!NOTE]
> HoloLens 2 unterstützt nur die Ausführung von UWP-ARM64-Apps.

## Warten

In IT-Umgebungen von Unternehmen muss ein Ausgleich zwischen dem Wunsch, Benutzern stets die neuesten Technologien zur Verfügung zu stellen, und dem Bedarf an Sicherheit und Kostenkontrolle gefunden werden. Da Cyberangriffe zu einem alltäglichen Ereignis geworden sind, ist es wichtig, den Zustand Ihrer Windows 10-Geräte ordnungsgemäß zu verwalten. Die IT muss die Konfigurationseinstellungen steuern, deren Kompatibilität aufrechterhalten und vorschreiben, welche Geräte auf interne Anwendungen zugreifen dürfen. HoloLens 2 bietet die erforderlichen Verwaltungsfunktionen für mobile Vorgänge, um sicherzustellen, dass geräte die Unternehmensrichtlinien einhalten.

### Betriebssystemwartungsoptionen

**Ein optimierter Updateprozess**

Microsoft hat den Windows-Engineering- und -Freigabezyklus optimiert, sodass neue Features, Umgebungen und Funktionen, die auf dem Markt nachgefragt werden, schneller bereitgestellt werden können als jemals zuvor. Microsoft plant die Bereitstellung von zwei Funktionsupdates pro Jahr (12-Monats-Zeitraum). **Featureupdates** richten einen Current Branch oder CB ein und verfügen über eine zugeordnete Version.

Microsoft wird updates für Sicherheit und Stabilität auch direkt auf HoloLens 2-Geräten bereitstellen und installieren. Diese **Qualitätsupdates,** die unter der Kontrolle von Microsoft über Windows Update veröffentlicht werden, sind monatlich verfügbar. HoloLens 2 verbraucht Featureupdates und Qualitätsupdates als Teil desselben Standardupdateprozesses.

Unternehmenskunden können die Updateerfahrung und den Prozess auf HoloLens 2s mithilfe eines MDM-Systems verwalten. In den meisten Fällen gelten die Richtlinien zum Verwalten des Updateprozesses sowohl für Funktions- als auch für Qualitätsupdates. Weitere Details zum [Konfigurieren von MDM für HoloLens-Updates.](https://docs.microsoft.com/hololens/hololens-updates)

### Verwalten von Anwendungen

IT-Administratoren können steuern, welche Apps auf HoloLens 2 installiert werden dürfen und wie sie auf dem neuesten Stand gehalten werden sollen.

HoloLens 2 unterstützt [Windows Defender Application Control (WDAC),](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)mit dem Administratoren Listen von Apps aus dem Microsoft Store erstellen, zulassen oder nicht zulassen können. Diese Funktion gilt auch für integrierte Apps. Die Möglichkeit, Apps zu erlauben oder zu verweigern, trägt dazu bei, dass Benutzer ihre Geräte für ihre beabsichtigten Zwecke verwenden. Es ist jedoch nicht immer leicht, Anforderungen und Wünschen der Mitarbeiter und Sicherheitsaspekten gleichermaßen gerecht zu werden. Beim Erstellen von Positiv- oder Negativlisten muss außerdem die sich ändernde App-Landschaft des Microsoft Store berücksichtigt werden.

Weitere Informationen finden Sie unter [Anwendungssteuerungs-CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp).

### Ausmustern

Die Geräteausstieg ist die letzte Phase des Gerätelebenszyklus. Es&#39;wichtig, dass Geräte, die durch neuere Modelle ersetzt werden, sicher eingestellt werden, da Sie nicht möchten&#39;dass Unternehmensdaten auf verworfenen Geräten verbleiben, was die Vertraulichkeit Ihrer Daten beeinträchtigt. Die IT erfordert auch eine Möglichkeit, Benutzer beim Zurücksetzen von gestohlenen oder verloren gegangenen Geräten angemessen zu unterstützen.

HoloLens 2 unterstützt drei Methoden zum Wischen des Geräts.

**MDM Factory Wipe:** Setzt HoloLens 2 über den vom Administrator initiierten MDM-Befehl zurück auf das Factoryimage. Löscht alle gespeicherten Daten auf dem Gerät.

**Gerätezurücksetzung in den Einstellungen:** Endbenutzer können HoloLens 2 in der App "Einstellungen" auf dem Gerät manuell zurücksetzen. Löscht alle gespeicherten Daten auf dem Gerät.

**Advanced Recovery Companion (ARC):** Auf einem PC, auf dem das Tool ARC ausgeführt wird, kann ein Benutzer oder Administrator eine HoloLens 2 flashen, die über ein USB-Kabel mit dem PC verbunden ist. Löscht alle gespeicherten Daten auf dem Gerät.

> [!div class="nextstepaction"]
> [Allgemeine Bereitstellungsszenarien](common-scenarios.md)
