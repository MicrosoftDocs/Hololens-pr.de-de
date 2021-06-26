---
title: Planen HoloLens 2 Bereitstellung in einer kommerziellen Umgebung
description: Erfahren Sie mehr über das Bereitstellen und Verwalten von HoloLens in Unternehmensumgebungen, einschließlich Infrastruktur, Azure Active Directory und Verwaltung mobiler Geräte.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 2a0933bb754043934621a22ffa7764c9c88d93da
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924603"
---
# <a name="common-deployment-scenarios"></a>Häufige Bereitstellungsszenarien

## <a name="overview"></a>Übersicht

Diese Seite bietet eine allgemeine Übersicht über die Architektur für drei gängige Szenarien bei der Bereitstellung und Verwaltung von Microsoft HoloLens 2 Geräten im Unternehmen.

Häufig wird die Art und Weise, wie Sie Ihre Geräte verwalten und auf die Ressourcen Ihrer Organisation zugreifen, größtenteils durch bereits eingerichtete Faktoren bestimmt. Basierend auf Ihrer vorhandenen Infrastruktur laden wir Sie ein, den allgemeinen Geräteverwaltungsstil (Common Device Management Style, MDM) in den folgenden Szenarien zu überprüfen. Lesen Sie anschließend [Planning HoloLens 2 deployments in a commercial environment (Planen HoloLens 2 Bereitstellungen in einer kommerziellen Umgebung),](hololens-core-components.md) um zu ermitteln, welches Szenario Ihren Anforderungen entspricht. Es sind auch drei entsprechende Leitfäden für die Verwendung während der Bereitstellung verfügbar.


 1. [Bereitstellungshandbuch für cloudbasierte Umgebung](hololens2-cloud-connected-overview.md)
     1. [Bereitstellungshandbuch für cloudbasierte Umgebung (externe Clients)](hololens2-deployment-guide.md)
 1. [Bereitstellungshandbuch für Unternehmensnetzwerke](hololens2-corp-connected-overview.md)
 1. [Bereitstellungshandbuch für sichere Offlineumgebung](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Szenario A: Bereitstellen auf mit der Cloud verbundenen Geräten

Dieses Szenario ist vergleichbar mit der Bereitstellung verwalteter mobiler Geräte innerhalb eines Unternehmens. HoloLens 2 wird in erster Linie in Umgebungen außerhalb eines Unternehmensnetzwerks bereitgestellt. Auf Unternehmensressourcen wird nicht zugegriffen oder kann über VPN eingeschränkt werden. 
 * Grundlegende allgemeine Konfigurationen
   * Wi-Fi Netzwerke sind in der Regel vollständig für internet- und cloudbasierte Dienste geöffnet.
   * Azure AD Mit mobiler Geräteverwaltung (MDM) automatischer Registrierung beitreten – MDM (Intune) verwaltet
   * Benutzer melden sich mit ihrem eigenen Unternehmenskonto (Azure AD) an.
     * Einzelne oder mehrere Benutzer pro Unterstütztes Gerät
   * Unterschiedliche Ebenen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von Vollständig geöffnet bis zu Kiosk mit einzelner App.
   * Eine oder mehrere Anwendungen werden über MDM bereitgestellt.

* Häufige Herausforderungen
   * Bestimmen der MDM-Konfigurationen, die auf die HoloLens 2 angewendet werden sollen, basierend auf den Szenarioanforderungen.

[![Szenario: Diagramm ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

Im entsprechenden Leitfaden für cloudfähige Verbindungen wird erläutert, wie Sie HoloLens 2 bei Ihrer Geräteverwaltung registrieren, Lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer Remote Assist sofort bei der Geräteeinrichtung verwenden können. Verwenden Sie den Leitfaden für externe Clients, um Geräte zur kurzfristigen oder langfristigen externen Verwendung an einem Remotestandort bereitzustellen.

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch für cloudbasierte Umgebung](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch für cloudbasierte Umgebung (externe Clients)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Szenario B: Bereitstellen innerhalb des Netzwerks Ihrer Organisation

Dieses Szenario ist mit einer klassischen Bereitstellung für die meisten Windows 10 PCs identisch. HoloLens 2 wird für die Verwendung in erster Linie im Unternehmensnetzwerk mit Zugriff auf interne Unternehmensressourcen bereitgestellt. Internet- und Clouddienste können eingeschränkt sein. 

 * Grundlegende allgemeine Konfigurationen
   * Wi-Fi Netzwerk ist ein internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen und eingeschränktem Zugriff auf das Internet oder Clouddienste.
   * Azure AD Beitreten zur automatischen MDM-Registrierung
   * MDM (Intune) Verwaltet
   * Benutzer melden sich mit ihrem eigenen Unternehmenskonto (Azure AD) an.
     * Einzelne oder mehrere Benutzer pro Unterstütztes Gerät
   * Unterschiedliche Ebenen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von Vollständig geöffnet bis zu Kiosk mit einzelner App.
   * Eine oder mehrere Anwendungen werden über MDM bereitgestellt.

 * Häufige Herausforderungen
   * HoloLens 2 unterstützt keine lokale AD-Verknüpfung oder SCCM. Nur Azure AD mit MDM beitreten. Viele Unternehmen stellen in diesem Szenario noch immer Windows 10 PCs als lokale, in AD eingebundene Geräte bereit, die von System Center Konfigurations-Manager (SCCM) verwaltet werden und die Infrastruktur möglicherweise nicht für die Verwaltung interner Windows 10 Geräte über cloudbasierte MDM-Lösungen bereitgestellt/konfiguriert ist.
   * Da es sich bei HoloLens 2 um ein cloudbasiertes Gerät handelt, basiert es in hohem Maße auf Mit dem Internet und mit der Cloud verbundenen Diensten für Benutzerauthentifizierung, Betriebssystemupdates, MDM-Verwaltung usw. Beim Herstellen einer Verbindung mit einem Unternehmensnetzwerk müssen wahrscheinlich Proxy-/Firewallregeln angepasst werden, um den Zugriff für HoloLens 2 und die darauf ausgeführten Anwendungen zu ermöglichen.
   * Unternehmens-Wi-Fi Konnektivität erfordert in der Regel Zertifikate, um das Gerät oder den Benutzer beim Netzwerk zu authentifizieren. Die erforderliche Infrastruktur oder die erforderlichen Einstellungen zum Bereitstellen von Zertifikaten auf Windows 10 Geräten über MDM können schwierig zu konfigurieren sein.

[![Szenario B1-Diagramm ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Szenario B2-Diagramm ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

Im entsprechenden Unternehmensnetzwerkleitfaden erfahren Sie, wie Sie HoloLens 2 bei Ihrer vorhandenen Geräteverwaltung registrieren, Lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer nach der Geräteeinrichtung einen Dynamics 365-Leitfaden betreiben und benutzerdefinierte Branchen-Apps verwenden können.

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch für Unternehmensnetzwerke](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Szenario C: Bereitstellen in einer sicheren Offlineumgebung

Dies ist eine typische Bereitstellung für äußerst sichere oder vertrauliche Speicherorte. HoloLens 2 wird für die Verwendung in erster Linie offline ohne Netzwerk- oder Internetzugriff bereitgestellt. 
 * Grundlegende allgemeine Konfigurationen
   * Wi-Fi Konnektivität ist deaktiviert. Ethernet über USB kann bei Bedarf für LAN-Konnektivität aktiviert werden.
   * Nicht verwaltet.
   * Lokales Benutzerkonto für die Geräteanmeldung.
     * HoloLens 2 unterstützt nur ein lokales Konto.
   * Unterschiedliche Ebenen von Gerätesperrungskonfigurationen werden über Bereitstellungspakete basierend auf bestimmten Anwendungsfällen angewendet. Diese Konfigurationen sind in der Regel aufgrund sicherer Umgebungsanforderungen eingeschränkt.
   * Eine oder mehrere Anwendungen werden über das Bereitstellungspaket bereitgestellt.

 * Häufige Herausforderungen
   * Über Bereitstellungspakete steht nur ein begrenzter Satz von Konfigurationen zur Verfügung.
   * Clouddienste können nicht verwendet werden, wodurch die HoloLens 2 Funktionen eingeschränkt werden.
   * Höherer Verwaltungsaufwand, da diese Geräte manuell eingerichtet, konfiguriert und aktualisiert werden müssen.

[![Sicheres Offlinediagramm 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

Der entsprechende sichere Offlineleitfaden enthält Anweisungen zum Anwenden eines Beispielbereitstellungspakets, das eine HoloLens 2 für die Verwendung in sicheren Umgebungen sperrt.

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch für sichere Offlineumgebung](hololens-common-scenarios-offline-secure.md)


