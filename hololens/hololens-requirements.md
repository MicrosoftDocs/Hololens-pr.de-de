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
ms.openlocfilehash: 4b8975d8eb362212eaf91966f4efa0bc22236327
ms.sourcegitcommit: 3f21b692be2f1b7f9c382f2b735b4c10339d4a78
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2021
ms.locfileid: "127934067"
---
# <a name="common-deployment-scenarios"></a>Häufige Bereitstellungsszenarien

## <a name="overview"></a>Übersicht

Es kann schwierig sein, herauszufinden, wie Sie ein neues Gerät bereitstellen, wenn Sie es zum ersten Mal ausprobieren. Hier haben wir verschiedene Möglichkeiten zum Bereitstellen und Verwalten von Microsoft HoloLens 2 Geräten innerhalb der Organisation.

Sie möchten Lösungen im großen Stil bereitgestellt haben. Wir möchten Sie dort finden. Im Folgenden werden die Schritte zum Bereitstellen von Geräten (also Hologrammen) beschrieben, um einen Mehrwert für Ihr Mixed Reality-Zielszenario zu erzielen. Unabhängig davon, ob Sie D365 Remote Assist, Leitfäden oder eine anwendung verwenden, die für den Azure Mixed Reality-Dienst aktiviert ist, die Sie erstellt haben– unsere allgemeinen Bereitstellungsszenarien sind für Sie hilfreich.

Möglicherweise sind Sie ein Entscheidungsträger im Unternehmen, IT-Experten oder Innovationsteam, das HoloLens Inbetrieb nehmen möchten. Wenn Sie vom Proof of Concept bis zu einer skalierten Bereitstellung aufbauen, sind unsere Bereitstellungsleitfäden für die HoloLens in Ihrer IT-Infrastruktur sinnvoll – unabhängig davon, wie groß oder klein sie sind. Die folgenden Bereitstellungsszenarien werden am häufigsten verwendet:

| Szenario |Verwendung | Wesentliche Punkte |
|---------|---------|---------|
| [Szenario A: Mit der Cloud verbundene Geräte](hololens2-cloud-connected-overview.md) | Wenn Sie ihre Bereitstellung zum ersten Mal starten, können Sie klein anfangen und ein einzelnes Gerät bereitstellen, das mit der Cloud verbunden ist, um den grundlegenden Prozess zu sehen. | Geräte werden mit Clouddiensten und dem öffentlichen Internet verbunden. Dies eignet sich am besten für Anwendungsfälle, Außendienstdienste und Proof of Concept.|
| [Szenario B: Netzwerk der Organisation](hololens2-corp-connected-overview.md) | Bei der Bereitstellung in der Produktionsumgebung im großen Stil müssen Sie möglicherweise in das Netzwerk Ihrer eigenen Organisation integrieren. | Geräte werden mit einem UNTERNEHMENS-WLAN-Netzwerk verbunden. Dies eignet sich am besten für interne Benutzer oder die Verwendung in der Unternehmensumgebung.|
| [Szenario C: Sichere Offlineumgebung](hololens-common-scenarios-offline-secure.md) | Einige unternehmenskritische Prozesse oder unternehmensrichtlinien erfordern möglicherweise die Verwendung von Offlineumgebungen. | Geräte werden mit einem stark restriktiven Netzwerk verbunden oder sind rein offline. Dies eignet sich am besten für hochsichere Umgebungen oder Einschränkungen der Internetkonnektivität in Remotebereichen. |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Szenario A: Bereitstellen auf mit der Cloud verbundenen Geräten

Dieses Szenario ist vergleichbar mit der Bereitstellung verwalteter mobiler Geräte in einem Unternehmen. HoloLens 2 wird hauptsächlich für die Verwendung in Umgebungen außerhalb eines Unternehmensnetzwerks bereitgestellt. Auf Unternehmensressourcen wird nicht zugegriffen oder kann über VPN eingeschränkt werden.

[![Szenario Ein Diagramm.](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>Verwendung

Betrachten Sie dieses Bereitstellungsmodell für Folgendes:

* Bereitstellen von Proof of Concept, Pilotversuchen und Außendienstdiensten
* Bereitstellen [Remote Assist](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>Grundlegende allgemeine Konfigurationen

* Wi-Fi-Netzwerke sind in der Regel vollständig für das Internet und Clouddienste geöffnet.
* Azure AD join with Mobile Geräteverwaltung (MDM) Auto Enrollment –MDM (Intune) Managed
* Benutzer melden sich mit ihrem eigenen Unternehmenskonto (Azure AD) an.
  * Unterstützter Einzelbenutzer oder mehrere Benutzer pro Gerät
* Verschiedene Ebenen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von Vollständig geöffnet bis Einzel-App-Kiosk.
* Mindestens eine Anwendung wird über MDM bereitgestellt.

### <a name="common-challenges"></a>Häufige Herausforderungen

* Bestimmen der MDM-Konfigurationen, die auf die HoloLens 2 basierend auf den Szenarioanforderungen angewendet werden

Im entsprechenden Cloud Connected-Leitfaden erfahren Sie, wie Sie HoloLens 2 bei Ihrer Geräteverwaltung registrieren, Bei Bedarf Lizenzen anwenden und überprüfen, ob Ihre Endbenutzer die Geräte bei der Geräteeinrichtung Remote Assist sofort verwenden können.

> [!div class="nextstepaction"]
> [Leitfaden für die Cloud Connected-Bereitstellung](hololens2-cloud-connected-overview.md)

Verwenden Sie den Leitfaden externe Clients, um Geräte für die kurzfristige oder langfristige externe Verwendung an einem Remotestandort bereitzustellen.

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch für cloud verbundene (externe Clients)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Szenario B: Bereitstellen im Netzwerk Ihrer Organisation

Dieses Szenario ist identisch mit einer klassischen Bereitstellung für die Windows 10 PCs. HoloLens 2 wird hauptsächlich für die Verwendung im Unternehmensnetzwerk mit Zugriff auf interne Unternehmensressourcen bereitgestellt. Internet- und Clouddienste sind möglicherweise eingeschränkt. 

[![Diagramm zu Szenario B1.](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Szenario B2-Diagramm.](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>Verwendung

Betrachten Sie dieses Bereitstellungsmodell für Folgendes:

* Interne Benutzer
* Bereitstellung im großen Stil (Pilot und Produktion) innerhalb der Unternehmensumgebung

### <a name="basic-common-configurations"></a>Grundlegende allgemeine Konfigurationen

* Wi-Fi Netzwerk ist ein internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen und eingeschränktem Zugriff auf das Internet oder Clouddienste.
* Azure AD Join mit automatischer MDM-Registrierung
* MDM (Intune) Verwaltet
* Benutzer melden sich mit ihrem eigenen Unternehmenskonto (Azure AD) an.
  * Unterstützter Einzelbenutzer oder mehrere Benutzer pro Gerät
* Verschiedene Ebenen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von Vollständig geöffnet bis Einzel-App-Kiosk.
* Mindestens eine Anwendung wird über MDM bereitgestellt.

### <a name="common-challenges"></a>Häufige Herausforderungen

* HoloLens 2 unterstützt keine lokale AD-Verknüpfung oder -System Center Configuration Manager (SCCM). Nur Azure AD mit MDM beitreten. Viele Unternehmen stellen in diesem Szenario weiterhin Windows 10-PCs als lokale AD-geräte bereit, die von SCCM verwaltet werden und möglicherweise nicht über die Infrastruktur verfügen, die für die Verwaltung interner Windows 10-Geräte über cloudbasierte MDM-Lösungen bereitgestellt/konfiguriert ist.
* Da HoloLens 2 ein Cloud-First-Gerät ist, ist es für die Benutzerauthentifizierung, Betriebssystemupdates, MDM-Verwaltung und so weiter stark von mit dem Internet und der Cloud verbundenen Diensten abhängig. Beim Herstellen einer Verbindung mit einem Unternehmensnetzwerk müssen wahrscheinlich Proxy-/Firewallregeln angepasst werden, um den Zugriff für HoloLens 2 anwendungen zu ermöglichen, die darauf ausgeführt werden.
* UnternehmensWi-Fi verbindung erfordert in der Regel Zertifikate, um das Gerät oder den Benutzer beim Netzwerk zu authentifizieren. Die erforderliche Infrastruktur oder Einstellungen zum Bereitstellen von Zertifikaten auf Windows 10 Geräten über MDM kann eine Herausforderung darstellen.

Im entsprechenden Leitfaden für verbundene Unternehmen erfahren Sie, wie Sie HoloLens 2 bei Ihrer vorhandenen Geräteverwaltung registrieren, Bei Bedarf Lizenzen anwenden und überprüfen, ob Ihre Endbenutzer ein Dynamics 365-Handbuch betreiben und benutzerdefinierte Line-of-Business-Apps verwenden können, nachdem das Gerät eingerichtet wurde.

> [!div class="nextstepaction"]
> [Leitfaden für die Bereitstellung von verbundenen Unternehmen](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Szenario C: Bereitstellen in einer sicheren Offlineumgebung

Dies ist eine typische Bereitstellung für äußerst sichere oder vertrauliche Standorte. HoloLens 2 wird für die Verwendung in erster Linie offline ohne Netzwerk- oder Internetzugriff bereitgestellt.

[![Offline: Sicheres Diagramm 1.](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>Verwendung

Betrachten Sie dieses Bereitstellungsmodell für Folgendes:

* Äußerst sichere Umgebungen, in denen Daten im Haus aufbewahrt werden müssen
* "Erfahrungen", bei denen die Öffentlichkeit die Geräte verwendet
* Internetkonnektivitätsproblem im Remotebereich

### <a name="basic-common-configurations"></a>Grundlegende allgemeine Konfigurationen

* Wi-Fi Die Konnektivität ist deaktiviert. Ethernet über USB kann bei Bedarf für LAN-Konnektivität aktiviert sein.
* Nicht verwaltet
* Lokales Benutzerkonto für die Geräte anmeldung
  * HoloLens 2 unterstützt nur ein lokales Konto.
* Unterschiedliche Ebenen von Gerätesperrungskonfigurationen werden über Bereitstellungspakete basierend auf bestimmten Anwendungsfällen angewendet. Diese Konfigurationen sind in der Regel aufgrund sicherer Umgebungsanforderungen eingeschränkt.
* Mindestens eine Anwendung wird über das Bereitstellungspaket bereitgestellt.

### <a name="common-challenges"></a>Häufige Herausforderungen

* Es gibt eine begrenzte Anzahl von Konfigurationen, die über Bereitstellungspakete verfügbar sind.
* Clouddienste können nicht verwendet werden, wodurch die HoloLens 2 eingeschränkt wird.
* Höherer Verwaltungsaufwand, da diese Geräte manuell eingerichtet, konfiguriert und aktualisiert werden müssen.

Der entsprechende sichere Offlineleitfaden enthält Anweisungen zum Anwenden eines Beispielbereitstellungspakets, das eine HoloLens 2 für die Verwendung in sicheren Umgebungen sperrt.

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch für sichere Offlineumgebung](hololens-common-scenarios-offline-secure.md)
