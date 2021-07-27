---
title: Häufige Bereitstellungsszenarien
description: Erfahren Sie mehr über das Bereitstellen und Verwalten von HoloLens in Unternehmensumgebungen, einschließlich Infrastruktur, Azure Active Directory und Verwaltung mobiler Geräte.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 529dde590c30d4a51fa8ae61e9d37d22170dc271
ms.sourcegitcommit: 5130823947caffd2a444e9d8fb15cd24cbb6414c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2021
ms.locfileid: "114659062"
---
# <a name="common-deployment-scenarios"></a>Häufige Bereitstellungsszenarien

## <a name="overview"></a>Überblick

Es kann schwierig sein, herauszufinden, wie ein neues Gerät bereitgestellt wird, wenn Sie es zum ersten Mal ausprobieren. Hier werden verschiedene Möglichkeiten zum Bereitstellen und Verwalten von Microsoft HoloLens 2-Geräten innerhalb der Organisation gemeinsam verwendet.

Sie möchten, dass Lösungen in großem Umfang bereitgestellt werden. Wir möchten Sie dorthin bringen. Zunächst werden die Schritte zum Bereitstellen von Geräten (also Hologrammen) beschrieben, um einen Mehrwert für Ihr Mixed Reality-Zielszenario zu erzielen, unabhängig davon, ob Sie D365 Remote Assist, Handbücher oder eine azure mixed reality-dienstfähige Anwendung verwenden, die Sie erstellt haben.

Möglicherweise sind Sie ein Geschäftlicher Entscheidungsträger, IT-Experten oder ein Innovationsteam, das HoloLens in Ihrer Organisation übernehmen möchte. Wenn Sie vom Proof of Concept bis hin zu einer skalierten Bereitstellung entwickeln, sind unsere Bereitstellungsleitfäden für HoloLens innerhalb Ihrer IT-Infrastruktur sinnvoll – unabhängig davon, wie groß oder klein sie sind. Die folgenden Bereitstellungsszenarien sind die gängigsten:

| Szenario |Verbrauch | Wesentliche Punkte |
|---------|---------|---------|
| [Szenario A: Mit der Cloud verbundene Geräte](hololens2-cloud-connected-overview.md) | Wenn Sie ihre Bereitstellung zum ersten Mal starten, können Sie klein anfangen und ein einzelnes Gerät bereitstellen, das mit der Cloud verbunden ist, um den grundlegenden Prozess anzuzeigen. | Geräte werden mit Clouddiensten und dem öffentlichen Internet verbunden. Dies eignet sich am besten für Anwendungsfälle von Kunden, Außendienst und Proof of Concept.|
| [Szenario B: Netzwerk der Organisation](hololens2-corp-connected-overview.md) | Wenn Sie die Bereitstellung in der Produktionsumgebung im großen Stil durchführen, müssen Sie möglicherweise in das Netzwerk Ihrer eigenen Organisation integriert werden. | Geräte werden mit einem UNTERNEHMENS-WLAN-Netzwerk verbunden. Dies eignet sich am besten für interne Benutzer oder die Verwendung innerhalb der Unternehmensumgebung.|
| [Szenario C: Sichere Offlineumgebung](hololens-common-scenarios-offline-secure.md) | Einige unternehmenskritische Prozesse oder einige Unternehmensrichtlinien erfordern möglicherweise die Verwendung von Offlineumgebungen. | Geräte werden mit einem stark restriktiven Netzwerk verbunden oder sind ausschließlich Offlinegeräte. Dies eignet sich am besten für äußerst sichere Umgebungen oder Internetkonnektivitätseinschränkungen in Remotebereichen. |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Szenario A: Bereitstellen auf mit der Cloud verbundenen Geräten

Dieses Szenario ist vergleichbar mit der Bereitstellung verwalteter mobiler Geräte innerhalb eines Unternehmens. HoloLens 2 wird in erster Linie in Umgebungen außerhalb eines Unternehmensnetzwerks bereitgestellt. Auf Unternehmensressourcen wird nicht zugegriffen oder kann über VPN eingeschränkt werden.

[![Szenario: Diagramm](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>Verwendung

Betrachten Sie dieses Bereitstellungsmodell für:

* Bereitstellen von Proof of Concept, Pilotprojekten und Außendienstdiensten
* Bereitstellen von [Remote Assist](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>Grundlegende allgemeine Konfigurationen

* Wi-Fi Netzwerke sind in der Regel vollständig für das Internet und Clouddienste geöffnet.
* Azure AD Mit mobiler Geräteverwaltung (MDM) automatisch registrieren – MDM (Intune) verwaltet
* Benutzer melden sich mit ihrem eigenen Unternehmenskonto (Azure AD) an.
  * Einzelne oder mehrere Benutzer pro Unterstütztes Gerät
* Unterschiedliche Ebenen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von Vollständig geöffnet bis zu Kiosk mit einzelner App.
* Eine oder mehrere Anwendungen werden über MDM bereitgestellt.

### <a name="common-challenges"></a>Häufige Herausforderungen

* Bestimmen der MDM-Konfigurationen, die auf die HoloLens 2 angewendet werden sollen, basierend auf den Szenarioanforderungen

Im entsprechenden Leitfaden für cloudfähige Verbindungen wird erläutert, wie Sie HoloLens 2 bei Ihrer Geräteverwaltung registrieren, Lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer Remote Assist sofort bei der Geräteeinrichtung verwenden können.

> [!div class="nextstepaction"]
> [Leitfaden zur Bereitstellung mit Cloudverbindung](hololens2-cloud-connected-overview.md)

Verwenden Sie den Leitfaden für externe Clients, um Geräte zur kurzfristigen oder langfristigen externen Verwendung an einem Remotestandort bereitzustellen.

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch für cloudverbundene (externe Clients)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Szenario B: Bereitstellen innerhalb des Netzwerks Ihrer Organisation

Dieses Szenario ist mit einer klassischen Bereitstellung für die meisten Windows 10 PCs identisch. HoloLens 2 wird für die Verwendung in erster Linie im Unternehmensnetzwerk mit Zugriff auf interne Unternehmensressourcen bereitgestellt. Internet- und Clouddienste können eingeschränkt sein. 

[![Szenario B1-Diagramm](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Szenario B2-Diagramm](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>Verwendung

Betrachten Sie dieses Bereitstellungsmodell für:

* Interne Benutzer
* Bereitstellung im großen Stil (Pilot und Produktion) in der Unternehmensumgebung

### <a name="basic-common-configurations"></a>Grundlegende allgemeine Konfigurationen

* Wi-Fi Netzwerk ist ein internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen und eingeschränktem Zugriff auf das Internet oder Clouddienste.
* Azure AD Beitreten zur automatischen MDM-Registrierung
* MDM (Intune) Verwaltet
* Benutzer melden sich mit ihrem eigenen Unternehmenskonto (Azure AD) an.
  * Einzelne oder mehrere Benutzer pro Unterstütztes Gerät
* Unterschiedliche Ebenen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von Vollständig geöffnet bis zu Kiosk mit einzelner App.
* Eine oder mehrere Anwendungen werden über MDM bereitgestellt.

### <a name="common-challenges"></a>Häufige Herausforderungen

* HoloLens 2 unterstützt keine lokale AD-Verknüpfung oder System Center Configuration Manager (SCCM). Nur Azure AD mit MDM beitreten. Viele Unternehmen stellen in diesem Szenario noch immer Windows 10 PCs als lokale ad eingebundene Geräte bereit, die von SCCM verwaltet werden und möglicherweise nicht über die Infrastruktur verfügen, die für die Verwaltung interner Windows 10 Geräte über cloudbasierte MDM-Lösungen bereitgestellt/konfiguriert ist.
* Da es sich bei HoloLens 2 um ein cloudbasiertes Gerät handelt, werden für die Benutzerauthentifizierung, Betriebssystemupdates, MDM-Verwaltung usw. in hohem Maße Internet- und Clouddienste verwendet. Beim Herstellen einer Verbindung mit einem Unternehmensnetzwerk müssen wahrscheinlich Proxy-/Firewallregeln angepasst werden, um den Zugriff für HoloLens 2 und die darauf ausgeführten Anwendungen zu ermöglichen.
* Unternehmens-Wi-Fi Konnektivität erfordert in der Regel Zertifikate, um das Gerät oder den Benutzer beim Netzwerk zu authentifizieren. Die erforderliche Infrastruktur oder Die erforderlichen Einstellungen zum Bereitstellen von Zertifikaten auf Windows 10 Geräten über MDM können schwierig zu konfigurieren sein.

Im entsprechenden Leitfaden für unternehmensinterne Verbindungen wird erläutert, wie Sie HoloLens 2 bei Ihrer vorhandenen Geräteverwaltung registrieren, Lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer nach der Geräteeinrichtung einen Dynamics 365-Leitfaden betreiben und benutzerdefinierte Branchen-Apps verwenden können.

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch für unternehmenseingegeschaltete Verbindungen](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Szenario C: Bereitstellen in einer sicheren Offlineumgebung

Dies ist eine typische Bereitstellung für äußerst sichere oder vertrauliche Standorte. HoloLens 2 wird für die Verwendung in erster Linie offline ohne Netzwerk- oder Internetzugriff bereitgestellt.

[![Sicheres Offlinediagramm 1](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>Verwendung

Betrachten Sie dieses Bereitstellungsmodell für:

* Hochsichere Umgebungen, in denen Daten im Haus aufbewahrt werden müssen
* "Erfahrungen", in denen die Öffentlichkeit die Geräte verwendet
* Internetkonnektivitätsproblem im Remotebereich

### <a name="basic-common-configurations"></a>Grundlegende allgemeine Konfigurationen

* Wi-Fi Konnektivität ist deaktiviert. Ethernet über USB kann bei Bedarf für LAN-Konnektivität aktiviert werden.
* Nicht verwaltet
* Lokales Benutzerkonto für die Geräteanmeldung
  * HoloLens 2 unterstützt nur ein lokales Konto.
* Unterschiedliche Ebenen von Gerätesperrungskonfigurationen werden über Bereitstellungspakete basierend auf bestimmten Anwendungsfällen angewendet. Diese Konfigurationen sind in der Regel aufgrund sicherer Umgebungsanforderungen eingeschränkt.
* Eine oder mehrere Anwendungen werden über das Bereitstellungspaket bereitgestellt.

### <a name="common-challenges"></a>Häufige Herausforderungen

* Es gibt eine begrenzte Anzahl von Konfigurationen, die über Bereitstellungspakete verfügbar sind.
* Clouddienste können nicht verwendet werden, wodurch die HoloLens 2 Funktionen eingeschränkt werden.
* Höherer Verwaltungsaufwand, da diese Geräte manuell eingerichtet, konfiguriert und aktualisiert werden müssen.

Der entsprechende sichere Offlineleitfaden enthält Anweisungen zum Anwenden eines Beispielbereitstellungspakets, das eine HoloLens 2 für die Verwendung in sicheren Umgebungen sperrt.

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch für sichere Offlineumgebung](hololens-common-scenarios-offline-secure.md)
