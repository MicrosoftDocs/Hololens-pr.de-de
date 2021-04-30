---
title: Einrichten von HoloLens in einer kommerziellen Umgebung
description: Erfahren Sie mehr über das Bereitstellen und Verwalten von HoloLens in Unternehmensumgebungen, einschließlich Infrastruktur, Azure Active Directory und Verwaltung mobiler Geräte.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308815"
---
# <a name="hololens-2-enterprise-deployment-and-management"></a>HoloLens 2 Enterprise-Bereitstellung und -Verwaltung

Diese Übersicht soll IT-Experten dabei helfen, überlegungen zur Bereitstellung und Verwaltung von Microsoft HoloLens 2-Geräten im Unternehmen zu verstehen.

HoloLens 2 auf einem Windows 10 Holographic, das Organisationen stabile, flexible, integrierte Technologien für die Verwaltung mobiler Geräte und Apps bietet. Windows 10 Holographic unterstützt die End-to-End-Verwaltung des Gerätelebenszyklus, um Unternehmen die Kontrolle über ihre Geräte, Daten und Apps zu geben. Die HoloLens 2 können mithilfe einer umfassenden Lösung für die Verwaltung mobiler Geräte problemlos in Standardmethoden für den Lebenszyklus integriert werden– von der Geräteregistrierung, Konfiguration und Anwendungsverwaltung bis zur Wartung und Ablösung.

## <a name="prepare"></a>Vorbereiten

Wenn Sie sich auf die Bereitstellung HoloLens 2 in Ihrer Unternehmensumgebung vorbereiten, müssen Sie bei der Planung von Skalierungsbereitstellungen von HoloLens 2.

### <a name="infrastructure-essentials"></a>Infrastructure Essentials

Für HoloLens 2 in einem Unternehmensbereitstellungsszenario sind bestimmte grundlegende Infrastrukturdienste erforderlich, um den vollständigen Satz von Funktionen zu unterstützen. HoloLens 2 wurde mit [modernen mobilen Geräteverwaltung](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) für die Bereitstellung und Verwaltung erstellt. Mit Azure AD join + MDM als primäres Mittel, um dies in einer ständig wachsenden mobilen Mitarbeiterzahl zu erreichen. Die folgenden Themen bieten eine kurze Übersicht über die einzelnen Infrastrukturkomponenten, die in Ihrer Bereitstellungsplanung für HoloLens 2.

### <a name="azure-active-directory"></a>Azure Active Directory
Azure AD ist ein cloudbasierter Verzeichnisdienst zur Identitäts- und Zugriffsverwaltung. Dank der Möglichkeit zur Integration in bereits vorhandene lokale Verzeichnisse lässt sich eine Hybrid-Identitätslösung realisieren. Organisationen, die Microsoft Office 365 oder Intune verwenden, verwenden bereits Azure AD mit drei Editionen: Free, Premium P1 und Premium P2 (siehe [Azure Active Directory Editionen).](https://azure.microsoft.com/documentation/articles/active-directory-editions/) Alle Editionen unterstützen Azure AD Geräteregistrierung, aber Premium P1 ist erforderlich, um die automatische MDM-Registrierung zu aktivieren. HoloLens 2 erfordert Azure Active Directory Join, um die meisten Features und Funktionen auf Unternehmensebene zu ermöglichen.

> [!NOTE]
> Die lokale Active Directory-Verknüpfung wird auf HoloLens 2 nicht unterstützt.

### <a name="mobile-device-management"></a>Verwaltung mobiler Geräte
HoloLens 2 wurde speziell für die Verwaltung durch Mobile Geräteverwaltung-Systeme (MDM) in einer Unternehmensumgebung entwickelt. Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)ist Teil der Enterprise Mobility + Security und ist ein cloudbasiertes MDM-System, das Geräte im Unternehmen verwaltet. Wie Office 365 verwendet Intune Azure AD für die Identitätsverwaltung, sodass Mitarbeiter die gleichen Anmeldeinformationen verwenden, um Geräte bei Intune zu registrieren, die sie für die Anmeldung bei Office 365 verwenden. Mehrere MDM-Systeme unterstützen Windows 10, und die meisten unterstützen Bereitstellungsszenarien für persönliche und unternehmenseigene Geräte. MDM-Systeme können auch Anwendungsbereitstellungen und Updates für die HoloLens 2 verwalten. Andere MDM-Anbieter, die HoloLens 2 derzeit unterstützen, sind: AirWatch, MobileIron und andere. Alle MDM-Systemanbieter haben gleichen Zugriff auf Windows 10 Konfigurationsdienstanbieter für die Geräteverwaltung (Device Management Configuration Service Provider, CSP), sodass IT-Organisationen unabhängig davon, welches System ihren Verwaltungsanforderungen am besten entspricht, unabhängig davon, ob Microsoft Intune oder ein MDM-Produkt eines Drittanbieters, die Wahl haben.

> [!NOTE]
> Herkömmliche lokale PC-Verwaltungssysteme wie System Center Konfigurations-Manager werden auf HoloLens 2 nicht unterstützt.

### <a name="windows-update-for-business"></a>Windows Update for Business
Microsoft hat Windows Update for Business entwickelt, um IT-Administratoren weitere Verwaltungsfunktionen rund um Windows Update bereitzustellen, wie beispielsweise die Möglichkeit, Updates für Gruppen von Geräten bereitzustellen oder Wartungszeitfenster für die Installation von Updates festzulegen. Ausführliche Informationen zum Verwalten HoloLens 2 Updates finden Sie in der Dokumentation zu [HoloLens-Updates.](https://docs.microsoft.com/hololens/hololens-updates)

### <a name="certificates"></a>Zertifikate
HoloLens 2 unterstützt die Bereitstellung von Zertifikaten über MDM, wenn Ihre Umgebung Zertifikate für corp Wi-Fi Netzwerkauthentifizierung oder Zugriff auf andere Ressourcen erfordert. Einige MDM-Infrastrukturkonfigurationen sind möglicherweise erforderlich, um Zertifikatbereitstellungen für HoloLens 2 zu aktivieren. Erfahren Sie, wie Sie [Zertifikate und Netzwerkprofile für HoloLens 2 vorbereiten.](https://docs.microsoft.com/hololens/hololens-certificates-network) Wenn Sie Intune verwenden, sehen Sie sich die Details zur [Zertifizierungskonfiguration](https://docs.microsoft.com/mem/intune/protect/certificates-configure) an.

## <a name="configure"></a>Konfigurieren

MDM-Administratoren können Richtlinieneinstellungen auf jedem Unternehmensgerät definieren und implementieren, das in einem MDM-System registriert ist. Welche Konfigurationseinstellungen Sie verwenden, hängt vom Bereitstellungsszenario ab. In Windows 10 konfigurationsdienstanbieter (Configuration Service Providers, CSP) eine Schnittstelle zum Lesen, Festlegen, Ändern oder Löschen von Konfigurationseinstellungen auf dem Gerät. Diese Einstellungen sind mit Registrierungsschlüsseln oder Dateien verknüpft. Weitere Informationen zu den Windows 10-Verwaltungs-CSPs für HoloLens 2 finden Sie in der vollständigen Liste der [CSPs, die in HoloLens-Geräten unterstützt werden.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)

HoloLens 2 unterstützt auch das Festlegen einer begrenzten Anzahl von CSP-Konfigurationen durch benutzerdefinierte Bereitstellungspakete. Bereitstellungspakete werden in der Regel für Nicht-MDM-verwaltete Geräte genutzt und müssen manuell auf jedes Gerät angewendet werden. Weitere Informationen [zum Erstellen von benutzerdefinierten Bereitstellungspaketen](https://docs.microsoft.com/hololens/hololens-provisioning) finden Sie in der HoloLens-Bereitstellungsdokumentation.

> [!NOTE]
> HoloLens 2 unterstützt [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)und stellt einen einfachen und einfachen Prozess zum Verwalten Ihrer Unternehmensgerätekonfigurationen Windows 10 zur Verfügung.

### <a name="identity-management"></a>Identitätsverwaltung

Mitarbeiter können nur ein Konto verwenden, um ein Gerät zu initialisieren, sodass es&#39;, dass Ihre Organisation zuerst steuert, welches Konto aktiviert wird. Die Wahl des Kontos bestimmt, wer das Gerät kontrolliert und welche Verwaltungsfunktionen Ihnen zur Verfügung stehen. HoloLens 2 unterstützt drei Kontotypen: lokales Benutzerkonto, persönliches Microsoft-Konto und Azure Active Directory Konten. Es wird dringend empfohlen, die Azure Active Directory für Ihre Unternehmensidentitätsverwaltungslösung zu nutzen, da sie die vollständigen Funktionen auf Ihren HoloLens 2 bietet. Weitere Informationen zu Identitäten finden Sie unter [HoloLens](https://docs.microsoft.com/hololens/hololens-identity) identity for HoloLens 2.

### <a name="network-and-connectivity"></a>Netzwerk und Konnektivität

Da HoloLens 2 Ein cloudbasiertes Gerät ist, ist Netzwerkzugriff auf Onlineressourcen erforderlich, damit vollständige Funktionen und Funktionen verfügbar gemacht werden können. Wenn Sie HoloLens 2-Geräte mit Konnektivität mit Ihrem Intranetnetzwerk ihres Unternehmens bereitstellen, müssen Sie möglicherweise Ihre Proxy-/Firewallregeln aktualisieren, um den Zugriff auf HoloLens 2 Clouddienste zu ermöglichen. Weitere Informationen finden Sie in der Liste der allgemeinen [Endpunkte für das](https://docs.microsoft.com/hololens/hololens-offline)HoloLens 2 Betriebssystem . Der Zugriff auf zusätzliche Endpunkte ist möglicherweise erforderlich, damit Anwendungen oder andere Clouddienste erfolgreich auf HoloLens 2 werden.

Einige gängige HoloLens 2, die zusätzlichen Endpunktzugriff erfordern, sind:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365-Handbücher](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 Remote Assist (O365 Teams-Infrastruktur)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### <a name="certificate-deployment"></a>Zertifikatbereitstellung

Wenn Zertifikate für den Zugriff auf Unternehmensnetzwerke Wi-Fi oder andere Dienste in Ihrer Organisation erforderlich sind, unterstützt HoloLens 2 die Bereitstellung von Benutzer- und Gerätezertifikaten über MDM. Hinweis: Ihre MDM-Lösung erfordert möglicherweise eine zusätzliche Infrastrukturkonfiguration, um Zertifikate auf Windows 10 Geräten bereitzustellen.

### <a name="security-review"></a>Sicherheitsüberprüfung

Die meisten IT-Abteilungen von Unternehmen erfordern die Bewertung und Überprüfung neuer Geräte, die in einem Unternehmensnetzwerk bereitgestellt werden. Wenn Ihre Organisation eine Sicherheitsüberprüfung von HoloLens 2 benötigt, finden Sie weitere Details, die Sie beim Abrufen von [Sicherheitsgenehmigungen](https://docs.microsoft.com/hololens/security-overview)unterstützen.

### <a name="common-hololens-2-device-settings"></a>Allgemeine HoloLens 2 Geräteeinstellungen

Beim Bereitstellen HoloLens 2 Geräten in einer Unternehmensumgebung gibt es eine Reihe allgemeiner Gerätekonfigurationen, die beim Planen der Bereitstellung von HoloLens 2 berücksichtigt werden können. In dieser Liste werden Konfigurationen und Einstellungen hervorgehoben, die als recht häufig gelten und nicht aus einer vollständigen Liste der verfügbaren Optionen bestehen:

| Geräteeinstellung | Kurze Beschreibung.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Hardwareeinschränkungen](hololens-requirements.md#hardware-restrictions)               | Hardwareeinschränkungen reduzieren die Konnektivität und unterstützen den Datenschutz.                        |
| [WLAN-Profile](hololens-requirements.md#wi-fi-profiles)               | Konfigurieren Sie Wi-Fi Profile ohne Benutzereingriff oder Interaktion.                              |
| [Zertifikate](hololens-requirements.md#certificates-1)               | Stellen Sie konto- und/oder Wi-Fi Authentifizierung, VPN-Verschlüsselung und SSL-Verschlüsselung von Webinhalten bereit. |
| [Proxy](hololens-requirements.md#proxy)              | Verwalten des internen Datenverkehrs.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Steuern Sie den Zugriff auf Apps und Ressourcen im Intranet ihres Unternehmens.                               |
| [Kioskmodus](hololens-requirements.md#kiosk-mode) | Schränkt die Anwendungen ein, die Benutzern über die Benutzeroberfläche angezeigt werden. |

#### <a name="hardware-restrictions"></a>Hardwareeinschränkungen

HoloLens 2 verwendet eine moderne Technologie, die beliebte Hardwarefeatures wie Kameras, Mikrofone, Lautsprecher, USB-Schnittstellen, Bluetooth-Schnittstellen und WLAN umfasst. Die Verfügbarkeit dieser Features kann mit Hardwareeinschränkungen gesteuert werden.

Im Folgenden werden die am häufigsten verwendeten MDM-Einstellungen aufgeführt, die HoloLens 2 zum Konfigurieren von Hardwareeinschränkungen unterstützt. Einige diese Hardwareeinschränkungen sorgen für Konnektivität und tragen zum Datenschutz bei.

- [**WLAN zulassen:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Gibt an, ob Benutzer das Wi-Fi auf ihren Geräten aktivieren und verwenden können
- [**USB-Verbindung zulassen:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Gibt an, ob die USB-Verbindung aktiviert ist (&#39;usb-Ladevorgang nicht beeinträchtigt)
- [**Bluetooth zulassen:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Gibt an, ob Benutzer das Bluetooth-Radio auf ihren Geräten aktivieren und verwenden können

Erfahren Sie mehr über andere [allgemeine Geräteeinschränkungen.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### <a name="wi-fi-profiles"></a>WLAN-Profile

Die meisten WLAN-Netzwerke von Unternehmen erfordern Zertifikate und andere komplexe Informationen, um den Zugriff einzuschränken und zu schützen. Diese erweiterten Wi-Fi ist für typische Benutzer schwierig zu konfigurieren, aber MDM-Systeme können diese Wi-Fi ohne Benutzereingriff vollständig konfigurieren. Sie können mehrere WLAN-Profile in Ihrem MDM-System erstellen.

Weitere Informationen zu den Wi-Fi für Windows 10 finden Sie unter [WLAN-Einstellungen für Unternehmensprofile.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)

#### <a name="certificates"></a>Zertifikate

Zertifikate tragen zur Verbesserung der Sicherheit bei, indem sie Kontoauthentifizierung, Wi-Fi Authentifizierung, VPN-Verschlüsselung und SSL-Verschlüsselung von Webinhalten bereitstellen. Obwohl Administratoren Zertifikate auf Geräten manuell über bereitstellungspakete verwalten können, ist es eine bewährte Methode&#39;Ihr MDM-System zu verwenden, um diese Zertifikate während des gesamten Lebenszyklus zu verwalten – von der Registrierung über die Verlängerung bis hin zur Sperrung. Ihr MDM-System kann diese Zertifikate automatisch auf den Geräten&#39;-Zertifikatspeichern bereitstellen, nachdem Sie das Gerät registriert haben (solange das MDM-System die Simple Certificate Enrollment-Protokoll (SCEP) oder Public Key Cryptography Standards #12 (PKCS #12)) unterstützt. MDM kann auch registrierte Clientzertifikate abfragen und löschen oder eine neue Registrierungsanforderung auslösen, bevor das aktuelle Zertifikat abgelaufen ist.

Erfahren Sie mehr über das [Vorbereiten von Zertifikaten und Netzwerkprofilen für HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### <a name="proxy"></a>Proxy

Die meisten Intranetnetzwerke des Unternehmens nutzen einen Proxy zum Verwalten des internen Datenverkehrs. Mit HoloLens 2 können Sie einen Proxyserver für Ethernet- und Wi-Fi konfigurieren. Diese Einstellungen gelten nicht für VPN-Verbindungen.

Weitere Informationen zu Proxyeinstellungen für Windows 10 finden Sie unter [NetworkProxy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

#### <a name="vpn"></a>VPN

Organisationen verwenden häufig ein VPN, um den Zugriff auf Apps und Ressourcen im Intranet ihres Unternehmens&#39;zu steuern. HoloLens 2 unterstützt SSL-VPN-Verbindungen, die ein herunterladbares Plug-In aus der Microsoft Store erfordern und für den VPN-Anbieter Ihrer Wahl spezifisch sind.

Weitere Informationen zu VPN-Profilen finden Sie unter [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### <a name="kiosk-mode"></a>Kioskmodus

Sie können ein HoloLens 2 Gerät so konfigurieren, dass es als Gerät mit festem Zweck funktioniert, das auch als Kiosk bezeichnet wird, indem Sie das Gerät so konfigurieren, dass es im Kioskmodus ausgeführt wird. Der Kioskmodus schränkt die Anwendungen (oder Benutzer) ein, die auf dem Gerät verfügbar sind. Der Kioskmodus ist ein praktisches Feature, mit dem Sie ein HoloLens 2 Gerät für Geschäfts-Apps oder das HoloLens 2 Gerät in einer App-Demo verwenden können.

Weitere Informationen zum Konfigurieren eines HoloLens 2 im Kioskmodus finden Sie unter [Einrichten von HoloLens als Kiosk.](https://docs.microsoft.com/hololens/hololens-kiosk)

## <a name="deploy"></a>Bereitstellen

### <a name="mdm-device-enrollment"></a>MDM-Geräteregistrierung

Für Unternehmensbereitstellungen wird empfohlen, Geräte nur mit Azure AD Join und automatischer MDM-Registrierung (Azure AD+MDM) bei MDM als Unternehmensgeräte zu [registrieren.](https://docs.microsoft.com/hololens/hololens-enroll-mdm) Dies erfordert Azure AD Premium und unterstützt die automatische Registrierung bei mehreren MDM-Anbietern, einschließlich Intune.

Erfahren Sie mehr über die selbstbereitstellungsbasierte Registrierungsmethode [Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot).

### <a name="application-deployment"></a>Anwendungsbereitstellung

Die Benutzerproduktivität auf mobilen Geräten wird oft durch Apps ermöglicht.

Mithilfe der Universellen Windows-Plattform (UWP) für Windows-Apps ermöglicht Windows 10 das Entwickeln von Apps, die nahtlos geräteübergreifend funktionieren.

Es gibt mehrere Möglichkeiten, Anwendungen auf HoloLens 2 Geräten bereitzustellen. Apps können direkt über MDM, die Microsoft Store für Unternehmen oder über ein Bereitstellungspaket quergeladen werden. Weitere Informationen finden Sie in der Dokumentation zur [App-Bereitstellung.](https://docs.microsoft.com/hololens/app-deploy-overview)

> [!NOTE]
> HoloLens 2 unterstützt nur die Ausführung von UWP ARM64-Apps.

## <a name="maintain"></a>Verwalten

In IT-Umgebungen von Unternehmen muss ein Ausgleich zwischen dem Wunsch, Benutzern stets die neuesten Technologien zur Verfügung zu stellen, und dem Bedarf an Sicherheit und Kostenkontrolle gefunden werden. Da Cyberangriffe zu einem alltäglichen Ereignis geworden sind, ist es wichtig, den Zustand Ihrer Windows 10 Geräte ordnungsgemäß zu verwalten. Die IT muss die Konfigurationseinstellungen steuern, deren Kompatibilität aufrechterhalten und vorschreiben, welche Geräte auf interne Anwendungen zugreifen dürfen. HoloLens 2 stellt die Verwaltungsfunktionen für mobile Vorgänge bereit, die erforderlich sind, um sicherzustellen, dass Geräte mit den Unternehmensrichtlinien konform sind.

### <a name="os-servicing-options"></a>Betriebssystemwartungsoptionen

**Ein optimierter Updateprozess**

Microsoft hat den Windows-Engineering- und -Freigabezyklus optimiert, sodass neue Features, Umgebungen und Funktionen, die auf dem Markt nachgefragt werden, schneller bereitgestellt werden können als jemals zuvor. Microsoft plant die Bereitstellung von zwei Funktionsupdates pro Jahr (12-Monats-Zeitraum). **Featureupdates** richten eine Current Branch oder CB ein und verfügen über eine zugeordnete Version.

Microsoft wird Updates aus Sicherheits- und Stabilitätsgründen auch direkt auf HoloLens 2 installieren. Diese **Qualitätsupdates,** die unter Der Kontrolle von Microsoft über Windows Update veröffentlicht werden, sind monatlich verfügbar. HoloLens 2 werden Featureupdates und Qualitätsupdates im Rahmen des gleichen Standardupdateprozesses verwendet.

Unternehmenskunden können die Updateerfahrung und den Updateprozess auf HoloLens 2s mithilfe eines MDM-Systems verwalten. In den meisten Fällen gelten die Richtlinien zum Verwalten des Updateprozesses sowohl für Funktions- als auch für Qualitätsupdates. Weitere Informationen zum [Konfigurieren von MDM für HoloLens-Updates](https://docs.microsoft.com/hololens/hololens-updates)finden Sie unter .

### <a name="managing-applications"></a>Verwalten von Anwendungen

IT-Administratoren können steuern, welche Apps auf dem HoloLens 2 installiert werden dürfen und wie sie auf dem neuesten Stand gehalten werden sollen.

HoloLens 2 unterstützt Windows Defender Application [Control (WDAC),](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)wodurch Administratoren Listen von Apps aus der Anwendung erstellen, zulassen oder Microsoft Store. Diese Funktion wird auch auf integrierte Apps erweitert. Die Möglichkeit, Apps zu erlauben oder zu verweigern, trägt dazu bei, sicherzustellen, dass Benutzer ihre Geräte für ihre vorgesehenen Zwecke verwenden. Es ist jedoch nicht immer leicht, Anforderungen und Wünschen der Mitarbeiter und Sicherheitsaspekten gleichermaßen gerecht zu werden. Das Erstellen von Listen zum Zulassen oder Nicht zulassen erfordert auch, mit der sich ändernden App-Landschaft im Microsoft Store.

Weitere Informationen finden Sie unter [Application Control CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp).

### <a name="retire"></a>Außerkraftsetzen

Die Geräteinnung ist die letzte Phase des Gerätelebenszyklus. Es&#39;wichtig, dass Geräte, die durch neuere Modelle ersetzt werden, sicher ausgemustert werden, da Sie&#39;nicht möchten, dass Unternehmensdaten auf verworfenen Geräten verbleiben, die die Vertraulichkeit Ihrer Daten gefährden könnten. Die IT erfordert auch eine Möglichkeit, Benutzer beim Zurücksetzen von gestohlenen oder verloren gegangenen Geräten angemessen zu unterstützen.

HoloLens 2 unterstützt drei Methoden zum Löschen des Geräts.

**MDM Factory-Zurücksetzung:** Setzt die HoloLens 2 mithilfe eines vom Administrator initiierten MDM-Befehls auf das Factoryimage zurück. Löscht alle gespeicherten Daten auf dem Gerät.

**Gerätezurücksetzung aus den Einstellungen:** Endbenutzer können die Einstellungen in HoloLens 2 Einstellungs-App auf dem Gerät manuell zurücksetzen. Löscht alle gespeicherten Daten auf dem Gerät.

**Advanced Recovery Companion (ARC):** Auf einem PC, auf dem das ARC-Tool ausgeführt wird, kann ein Benutzer oder Administrator eine Verbindung HoloLens 2 USB-Kabel an den PC anschließen. Löscht alle gespeicherten Daten auf dem Gerät.

> [!div class="nextstepaction"]
> [Allgemeine Bereitstellungsszenarien](common-scenarios.md)
