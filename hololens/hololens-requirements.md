---
title: Einrichten von HoloLens in einer geschäftlichen Umgebung
description: Weitere Informationen finden Sie unter Bereitstellen und Verwalten von HoloLens in Enterprise-Umgebungen.
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
ms.openlocfilehash: 5f24d62193f083f96144b7e8c3518dc97c14be68
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195588"
---
# HoloLens 2 Enterprise-Bereitstellung und-Verwaltung

Diese Übersicht soll IT-Experten dabei helfen, Überlegungen zur Bereitstellung und Verwaltung von Microsoft HoloLens 2-Geräten innerhalb des Unternehmens zu verstehen.

HoloLens 2 läuft unter Windows 10 holographisch, das Unternehmen mit robusten, flexiblen, integrierten mobilen Geräten und App-Verwaltungstechnologien ausgestattet ist. Windows 10 holographische unterstützt das End-to-End-Device Lifecycle Management, um Unternehmen die Kontrolle über Ihre Geräte, Daten und apps zu ermöglichen. Die HoloLens 2 kann problemlos in Standard-Lebenszyklusmethoden integriert werden, von der Geräteregistrierung,-Konfiguration und-Anwendungsverwaltung über die Wartung und den Ruhestand mithilfe einer umfassenden Lösung für die Verwaltung mobiler Geräte.

## Vorbereiten

Während Sie die Bereitstellung von HoloLens 2 für Ihre Unternehmensumgebung vorbereiten, sollten verschiedene Aspekte überprüft und verstanden werden, wenn Sie mit der Planung von Skalierungs Bereitstellungen von HoloLens 2 beginnen.

### Infrastruktur-Grundlagen

Für HoloLens 2 in einem Unternehmensbereitstellungsszenario sind bestimmte wesentliche Infrastrukturdienste erforderlich, um den vollständigen Satz von Funktionen zu unterstützen. HoloLens 2 wurde mit [modernen mobilen Geräte Verwaltungen](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) für die Bereitstellung und Verwaltung konzipiert. Mit Azure AD Join + MDM als wichtigstes Mittel, um dies in einer ständig steigenden Zahl von mobilen Mitarbeitern zu erreichen. Die folgenden Themen enthalten einen kurzen Überblick über jede Infrastrukturkomponente, die in Ihrer Bereitstellungsplanung für HoloLens 2 berücksichtigt werden sollte.

### Azure Active Directory
AzureAD ist ein cloudbasierter Verzeichnisdienst zur Identitäts- und Zugriffsverwaltung. Dank der Möglichkeit zur Integration in bereits vorhandene lokale Verzeichnisse lässt sich eine Hybrid-Identitätslösung realisieren. Organisationen, die Microsoft Office 365 oder InTune verwenden, verwenden bereits Azure AD mit drei Editionen: Free, Premium P1 und Premium P2 (siehe [Azure Active Directory-Editionen](https://azure.microsoft.com/documentation/articles/active-directory-editions/)). Alle Editionen unterstützen die Azure AD-Geräteregistrierung, aber Premium P1 ist erforderlich, um die MDM-automatische Registrierung zu aktivieren. HoloLens 2 erfordert Azure Active Directory Join, um die meisten Features und Funktionen auf Unternehmensebene zu ermöglichen.

> [!NOTE]
> Active Directory-Join wird in HoloLens 2 nicht unterstützt.

### Verwaltung mobiler Geräte
HoloLens 2 wurde speziell für die Verwaltung von Mobile Device Management (MDM)-Systemen in einer Unternehmensumgebung entwickelt. Microsoft [InTune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune), ein Bestandteil des Enterprise Mobility + Security, ist ein Cloud-basiertes MDM-System, das Geräte im Unternehmen verwaltet. Wie in Office 365 verwendet InTune Azure AD für die Identitätsverwaltung, damit Mitarbeiter dieselben Anmeldeinformationen für die Registrierung von Geräten in InTune verwenden, die Sie für die Anmeldung bei Office 365 verwenden. Mehrere MDM-Systeme unterstützen Windows10, und die meisten unterstützen Bereitstellungsszenarien für persönliche und unternehmenseigene Geräte. MDM-Systeme können auch Anwendungsbereitstellungen und-Updates für das HoloLens 2 verwalten. Andere MDM-Anbieter, die HoloLens 2 unterstützen, sind derzeit: Watch, MobileIron und andere. Alle MDM-Systemanbieter haben gleichen Zugriff auf Windows 10-Konfigurationsdienstanbieter (Device Management Configuration Service Providers, CSP), sodass IT-Abteilungen die Freiheit haben, das für Ihre Verwaltungsanforderungen am besten geeignete System auszuwählen, ob Microsoft InTune oder ein MDM-Produkt eines Drittanbieters.

> [!NOTE]
> Herkömmliche PC-Verwaltungssysteme wie System Center Configuration Manager werden in HoloLens 2 nicht unterstützt.

### Windows Update for Business
Microsoft hat Windows Update for Business entwickelt, um IT-Administratoren weitere Verwaltungsfunktionen rund um Windows Update bereitzustellen, wie beispielsweise die Möglichkeit, Updates für Gruppen von Geräten bereitzustellen oder Wartungszeitfenster für die Installation von Updates festzulegen. Details zum Verwalten von HoloLens 2-Updates finden Sie [hier](https://docs.microsoft.com/hololens/hololens-updates).

### Zertifikate
HoloLens 2 unterstützt die Bereitstellung von Zertifikaten über MDM, wenn Ihre Umgebung Zertifikate für die Corp Wi-Fi-Netzwerkauthentifizierung oder den Zugriff auf andere Ressourcen erfordert. Möglicherweise sind einige MDM-Infrastrukturkonfigurationen erforderlich, um Zertifikat Bereitstellungen auf HoloLens 2 zu aktivieren. Hier erfahren Sie, wie Sie [Zertifikate und Netzwerkprofile für HoloLens 2 vorbereiten](https://docs.microsoft.com/hololens/hololens-certificates-network). Informationen zu InTune finden Sie [hier](https://docs.microsoft.com/mem/intune/protect/certificates-configure).

## Konfigurieren

MDM-Administratoren können Richtlinieneinstellungen auf allen Unternehmensgeräten definieren und implementieren, die in einem MDM-System registriert sind. Welche Konfigurationseinstellungen Sie verwenden, hängt vom Bereitstellungsszenario ab. In Windows 10 sind Configuration Service Providers (CSP) eine Schnittstelle zum Lesen, festlegen, ändern oder Löschen von Konfigurationseinstellungen auf dem Gerät. Diese Einstellungen sind mit Registrierungsschlüsseln oder Dateien verknüpft. Weitere Informationen zu Windows 10 Device Management LSP für HoloLens 2 finden Sie in der vollständigen Liste der [in HoloLens-Geräten unterstützten Kryptografiedienstanbieter](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

HoloLens 2 unterstützt auch das Festlegen eines eingeschränkten Satzes von CSP-Konfigurationen über benutzerdefinierte Bereitstellungspakete. Bereitstellungspakete werden in der Regel für nicht-MDM-verwaltete Geräte genutzt und müssen manuell auf jedes Gerät angewendet werden. Weitere Informationen zum Erstellen benutzerdefinierter Bereitstellungspakete finden Sie [hier](https://docs.microsoft.com/hololens/hololens-provisioning).

> [!NOTE]
> HoloLens 2 unterstützt [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)und bietet einen einfachen und einfachen Prozess für die Verwaltung Ihrer Windows 10-Gerätekonfigurationen in Unternehmen.

### Identitätsverwaltung

Mitarbeiter können nur ein Konto verwenden, um ein Gerät zu initialisieren, damit es&#39;wichtig ist, dass Ihre Organisation steuert, welches Konto zuerst aktiviert wird. Die Wahl des Kontos bestimmt, wer das Gerät kontrolliert und welche Verwaltungsfunktionen Ihnen zur Verfügung stehen. HoloLens 2 unterstützt drei Kontotypen: lokales Benutzerkonto, persönliches Microsoft-Konto und Azure Active Directory-Konten. Es wird dringend empfohlen, Azure Active Directory für Ihre Enterprise Identity Management-Lösung zu nutzen, da dadurch die vollständigen Funktionen auf Ihren HoloLens 2-Geräten aktiviert werden. Weitere Informationen zu den Identitäten auf HoloLens 2 finden Sie [hier](https://docs.microsoft.com/hololens/hololens-identity).

### Netzwerk und Konnektivität

Da es sich bei HoloLens 2 um ein Cloud First Device handelt, ist der Netzwerkzugriff auf Online Ressourcen erforderlich, damit alle Funktionen und Funktionen zur Verfügung gestellt werden können. Wenn Sie HoloLens 2-Geräte mit Konnektivität zum Intranet Ihres Unternehmens bereitstellen, müssen Sie möglicherweise Ihre Proxy/Firewall-Regeln aktualisieren, um den Zugriff auf HoloLens 2-Cloud-Dienste zu ermöglichen. Eine Liste der allgemeinen Endpunkte, die für das Betriebssystem HoloLens 2 benötigt werden, finden Sie [hier](https://docs.microsoft.com/hololens/hololens-offline). Möglicherweise ist der Zugriff auf zusätzliche Endpunkte erforderlich, damit Anwendungen oder andere Cloud-Dienste erfolgreich auf HoloLens 2 ausgeführt werden können.

Einige häufige HoloLens 2-Dienste, die zusätzlichen Endpunkt Zugriff erfordern, sind wie folgt:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365-Leitfäden](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365-Remote Unterstützung (Office 365 Teams-Infrastruktur)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### Zertifikatbereitstellung

Wenn Zertifikate für den Zugriff auf Unternehmens Wi-Fi Netzwerke oder andere Dienste in Ihrer Organisation erforderlich sind, unterstützt HoloLens 2 die Bereitstellung von Benutzer-und Geräte Zertifikaten über MDM. Hinweis: Ihre MDM-Lösung erfordert möglicherweise zusätzliche Infrastruktur Konfiguration zum Bereitstellen von Zertifikaten auf Windows 10-Geräten.

### Sicherheitsüberprüfung

In den meisten IT-Abteilungen des Unternehmens müssen die neuen Geräte, die in einem Unternehmensnetzwerk bereitgestellt werden, bewertet und überprüft werden. Wenn in Ihrer Organisation eine Sicherheitsüberprüfung von HoloLens 2 erforderlich ist, [finden Sie hier weitere Informationen, die Ihnen beim Abrufen von Sicherheitsgenehmigungen behilflich sein](https://docs.microsoft.com/hololens/security-overview)können.

### Allgemeine HoloLens 2-Geräteeinstellungen

Wenn Sie HoloLens 2-Geräte in einer Unternehmensumgebung bereitstellen, gibt es eine Reihe allgemeiner Gerätekonfigurationen, die bei der Planung der Bereitstellung von HoloLens 2 berücksichtigt werden können. In dieser Liste werden Konfigurationen und Einstellungen hervorgehoben, die sich als recht häufig erweisen und keine vollständige Liste der verfügbaren Optionen enthalten:

| Geräteeinstellung | Kurzbeschreibung.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Hardwareeinschränkungen](hololens-requirements.md#hardware-restrictions)               | Hardware Einschränkungen reduzieren die Konnektivität und unterstützen den Datenschutz.                        |
| [WLAN-Profile](hololens-requirements.md#wi-fi-profiles)               | Konfigurieren Sie Wi-Fi profile ohne Benutzereingriff oder Interaktion.                              |
| [Zertifikate](hololens-requirements.md#certificates-1)               | Bereitstellen von Konto-und/oder Wi-Fi Authentifizierung, VPN-Verschlüsselung und SSL-Verschlüsselung von Webinhalten |
| [Proxy](hololens-requirements.md#proxy)              | Verwalten Sie den internen Datenverkehr.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Steuern des Zugriffs auf apps und Ressourcen im Intranet Ihres Unternehmens                               |
| [Kioskmodus](hololens-requirements.md#kiosk-mode) | Schränkt die Anwendungen ein, die Benutzern über die Benutzeroberfläche angezeigt werden. |

#### Hardwareeinschränkungen

HoloLens 2 verwendet modernste Technologie, die gängige Hardware Features wie Kameras, Mikrofone, Lautsprecher, USB-Schnittstellen, Bluetooth-Schnittstellen und WLAN umfasst. Die Verfügbarkeit dieser Features kann mit Hardwareeinschränkungen gesteuert werden.

Im folgenden sind die am häufigsten verwendeten MDM-Einstellungen aufgeführt, die von HoloLens 2 zum Konfigurieren von Hardwareeinschränkungen unterstützt werden. Einige diese Hardwareeinschränkungen sorgen für Konnektivität und tragen zum Datenschutz bei.

- [**WiFi zulassen:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Ob Benutzer das Wi-Fi Radio auf Ihren Geräten aktivieren und verwenden können
- [**USB-Verbindung zulassen:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Ob die USB-Verbindung aktiviert ist (does&#39;t beeinflussen USB-Ladevorgang)
- [**Bluetooth zulassen:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Ob Benutzer das Bluetooth-Radio auf Ihren Geräten aktivieren und verwenden können

Weitere Informationen zu anderen [allgemeinen Geräteeinschränkungen](https://docs.microsoft.com/hololens/hololens-common-device-restrictions) finden Sie hier.

#### WLAN-Profile

Die meisten WLAN-Netzwerke von Unternehmen erfordern Zertifikate und andere komplexe Informationen, um den Zugriff einzuschränken und zu schützen. Diese erweiterten Wi-Fi Informationen sind für typische Benutzer schwierig zu konfigurieren, doch MDM-Systeme können diese Wi-Fi profile ohne Benutzereingriff vollständig konfigurieren. Sie können mehrere WLAN-Profile in Ihrem MDM-System erstellen.

Weitere Informationen zu den Wi-Fi Einstellungen für Windows 10 finden Sie unter [Enterprise-Profil WLAN-Einstellungen](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile).

#### Zertifikate

Zertifikate helfen, die Sicherheit zu verbessern, indem Sie Kontoauthentifizierung, Wi-Fi Authentifizierung, VPN-Verschlüsselung und SSL-Verschlüsselung von Webinhalten bereitstellen. Obwohl Administratoren Zertifikate auf Geräten manuell über Bereitstellungspakete verwalten können, ist es&#39;bewährte Methode, das MDM-System für die Verwaltung dieser Zertifikate während des gesamten Lebenszyklus zu verwenden – von der Registrierung bis zur Verlängerung und Sperrung. Ihr MDM-System kann diese Zertifikate nach der Registrierung des Geräts automatisch auf den Geräten&#39; Zertifikatspeicher bereitstellen (sofern das MDM-System das Simple Certificate Enrollment Protocol (SCEP) oder Public Key Cryptography Standards #12 (PKCS # 12) unterstützt). MDM kann auch angemeldete Clientzertifikate Abfragen und löschen oder eine neue Registrierungsanforderung auslösen, bevor das aktuelle Zertifikat abgelaufen ist.

Weitere Informationen finden Sie unter [Vorbereiten von Zertifikaten und Netzwerkprofilen für HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### Proxy

Die meisten Intranet-Netzwerke des Unternehmens nutzen einen Proxy, um internen Datenverkehr zu verwalten. Mit HoloLens 2 können Sie einen Proxy Server für Ethernet-und Wi-Fi-Verbindungen konfigurieren. Diese Einstellungen gelten nicht für VPN-Verbindungen.

Weitere Informationen zu Proxyeinstellungen für Windows 10 finden Sie unter [Netzwerkproxy-CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

#### VPN

Organisationen verwenden häufig ein VPN zum Steuern des Zugriffs auf apps und Ressourcen im Intranet Ihres Unternehmens&#39;s. HoloLens 2 unterstützt SSL-VPN-Verbindungen, die ein herunterladbares Plugin aus dem Microsoft Store erfordern und für den VPN-Anbieter Ihrer Wahl spezifisch sind.

Weitere Informationen zu VPN-Profilen finden Sie unter [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### Kioskmodus

Sie können ein HoloLens 2-Gerät so konfigurieren, dass es als festes Gerät (auch Kiosk genannt) funktioniert, indem Sie das Gerät so konfigurieren, dass es im Kioskmodus ausgeführt wird. Der Kiosk Modus schränkt die auf dem Gerät verfügbaren Anwendungen (oder Benutzer) ein. Der Kiosk Modus ist eine nützliche Funktion, mit der Sie ein HoloLens 2-Gerät für Geschäfts-Apps verwenden oder das HoloLens 2-Gerät in einer APP-Demo verwenden können.

Weitere Informationen zum Konfigurieren einer HoloLens 2 im Kioskmodus finden Sie unter [Einrichten von HoloLens als Kiosk](https://docs.microsoft.com/hololens/hololens-kiosk)

## Bereitstellen

### MDM-Geräteregistrierung

Bei Unternehmensbereitstellungen empfiehlt es sich, Geräte nur mit Azure AD Join und automatischer MDM-Registrierung (AAD + MDM) als unternehmensgeräte in MDM zu [registrieren](https://docs.microsoft.com/hololens/hololens-enroll-mdm) . Dies erfordert Azure AD Premium und unterstützt die automatische Registrierung für mehrere MDM-Anbieter, einschließlich InTune.

Weitere Informationen zur Self-Deploying-Registrierungsmethode [Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot).

### Anwendungsbereitstellung

Die Benutzerproduktivität auf mobilen Geräten wird oft durch Apps ermöglicht.

Mithilfe der Universellen Windows-Plattform (UWP) für Windows-Apps ermöglicht Windows10 das Entwickeln von Apps, die nahtlos geräteübergreifend funktionieren.

Es gibt mehrere Möglichkeiten zum Bereitstellen von Anwendungen auf HoloLens 2-Geräten. Apps können über ein Bereitstellungspaket direkt über MDM, den Microsoft Store for Business oder quer geladene bereitgestellt werden. Weitere [Informationen zur APP-Bereitstellung](https://docs.microsoft.com/hololens/app-deploy-overview)finden Sie hier.

> [!NOTE]
> HoloLens 2 unterstützt die Ausführung von UWP ARM64-apps.

## Warten

In IT-Umgebungen von Unternehmen muss ein Ausgleich zwischen dem Wunsch, Benutzern stets die neuesten Technologien zur Verfügung zu stellen, und dem Bedarf an Sicherheit und Kostenkontrolle gefunden werden. Da Cyberattacken zu einem alltäglichen Ereignis geworden sind, ist es wichtig, den Zustand Ihrer Windows 10-Geräte ordnungsgemäß zu verwalten. Die IT muss die Konfigurationseinstellungen steuern, deren Kompatibilität aufrechterhalten und vorschreiben, welche Geräte auf interne Anwendungen zugreifen dürfen. HoloLens 2 bietet die mobilen Betriebs Verwaltungsfunktionen, die erforderlich sind, um sicherzustellen, dass Geräte mit den Unternehmensrichtlinien kompatibel sind.

### Betriebssystem-Wartungsoptionen

**Ein optimierter Updateprozess**

Microsoft hat den Windows-Engineering- und -Freigabezyklus optimiert, sodass neue Features, Umgebungen und Funktionen, die auf dem Markt nachgefragt werden, schneller bereitgestellt werden können als jemals zuvor. Microsoft plant die Bereitstellung von zwei Funktionsupdates pro Jahr (12-Monats-Zeitraum). **Feature-Updates** stellen eine aktuelle Verzweigung oder CB her und weisen eine zugehörige Version auf.

Microsoft wird auch Updates für Sicherheit und Stabilität direkt auf HoloLens 2-Geräten bereitstellen und installieren. Diese **Qualitäts Updates** , die unter Microsoft Control über Windows Update veröffentlicht wurden, sind monatlich verfügbar. HoloLens 2 nutzt Funktionsupdates und Qualitäts Updates im Rahmen desselben Standard Aktualisierungsprozesses.

Unternehmenskunden können das Update in HoloLens 2S mithilfe eines MDM-Systems verwalten. In den meisten Fällen gelten die Richtlinien zum Verwalten des Updateprozesses sowohl für Funktions- als auch für Qualitätsupdates. Weitere Informationen finden Sie unter [Konfigurieren von MDM für HoloLens-Updates](https://docs.microsoft.com/hololens/hololens-updates).

### Verwalten von Anwendungen

IT-Administratoren können steuern, welche apps auf dem HoloLens 2 installiert werden dürfen und wie Sie auf dem neuesten Stand gehalten werden sollen.

HoloLens 2 unterstützt [Windows Defender Application Control (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac), mit dem Administratoren Listen von Apps aus dem Microsoft Store erstellen, zulassen oder verweigern können. Diese Funktion erstreckt sich auch auf integrierte apps. Die Möglichkeit, Apps zuzulassen oder zu verweigern, hilft, sicherzustellen, dass Personen Ihre Geräte für ihre beabsichtigten Zwecke verwenden. Es ist jedoch nicht immer leicht, Anforderungen und Wünschen der Mitarbeiter und Sicherheitsaspekten gleichermaßen gerecht zu werden. Beim Erstellen von Positiv- oder Negativlisten muss außerdem die sich ändernde App-Landschaft des Microsoft Store berücksichtigt werden.

Weitere Informationen finden Sie unter [Application Control CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp).

### Ausmustern

Der Geräte Ruhestand ist die letzte Phase des Gerätelebenszyklus. Es&#39;wichtig, dass Geräte, die durch neuere Modelle ersetzt werden, sicher zurückgezogen werden, da&#39;Sie nicht möchten, dass Unternehmensdaten auf verworfenen Geräten verbleiben, die die Vertraulichkeit Ihrer Daten gefährden könnten. Die IT erfordert auch eine Möglichkeit, Benutzer beim Zurücksetzen von gestohlenen oder verloren gegangenen Geräten angemessen zu unterstützen.

HoloLens 2 unterstützt 3 Methoden zum Abwischen des Geräts

**MDM Factory Wipe:** Setzt das HoloLens 2 zurück auf das Factory-Image über vom Administrator initiierten MDM-Befehl. Löscht alle gespeicherten Daten auf dem Gerät.

**Geräte-Reset in den Einstellungen:** Endbenutzer können das HoloLens 2 innerhalb der Einstellungs-APP auf dem Gerät manuell zurücksetzen. Löscht alle gespeicherten Daten auf dem Gerät.

**Advanced Recovery Companion (ARC):** Von einem PC, auf dem das Arc-Tool ausgeführt wird, kann ein Benutzer oder Administrator eine HoloLens 2-Verbindung mit dem PC über ein USB-Kabel aufblinken lassen. Löscht alle gespeicherten Daten auf dem Gerät.

> [!div class="nextstepaction"]
> [Allgemeine Bereitstellungsszenarien](common-scenarios.md)