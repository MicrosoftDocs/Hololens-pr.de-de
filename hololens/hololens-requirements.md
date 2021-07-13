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
ms.openlocfilehash: ccccdcc7d3188919d02eb5855131137415c12d16
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639827"
---
# <a name="common-deployment-scenarios"></a>Häufige Bereitstellungsszenarien

## <a name="overview"></a>Überblick

Diese Seite bietet eine allgemeine Übersicht über die Architektur für drei gängige Szenarien beim Bereitstellen und Verwalten Microsoft HoloLens 2 Geräten innerhalb des Unternehmens.

Häufig wird die Art und Weise, wie Sie Ihre Geräte verwalten und auf die Ressourcen Ihrer Organisation zugreifen, größtenteils von bereits festgelegten Faktoren bestimmt. Basierend auf Ihrer vorhandenen Infrastruktur laden wir Sie ein, den allgemeinen Geräteverwaltungsstil (Device Management Style, MDM) in den folgenden Szenarien zu überprüfen und dann Planning [HoloLens 2 deployments in a commercial environment](hololens-core-components.md) (Planen von HoloLens 2-Bereitstellungen in einer kommerziellen Umgebung) zu lesen, um zu ermitteln, welches Szenario Ihren Anforderungen entspricht. Es gibt auch drei entsprechende Leitfäden, die während der Bereitstellung verwendet werden können.


 1. [Bereitstellungshandbuch für cloudbasierte Umgebung](hololens2-cloud-connected-overview.md)
     1. [Bereitstellungshandbuch für cloudbasierte Umgebung (externe Clients)](hololens2-deployment-guide.md)
 1. [Bereitstellungshandbuch für Unternehmensnetzwerke](hololens2-corp-connected-overview.md)
 1. [Bereitstellungshandbuch für sichere Offlineumgebung](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Szenario A: Bereitstellen auf mit der Cloud verbundenen Geräten

Dieses Szenario ist vergleichbar mit der Bereitstellung verwalteter mobiler Geräte in einem Unternehmen. HoloLens 2 wird für die Verwendung in erster Linie in Umgebungen außerhalb eines Unternehmensnetzwerks bereitgestellt. Auf Unternehmensressourcen wird nicht zugegriffen oder kann über VPN eingeschränkt werden. 
 * Grundlegende allgemeine Konfigurationen
   * Wi-Fi-Netzwerke sind in der Regel vollständig für das Internet und cloudbasierte Dienste geöffnet.
   * Azure AD join with Mobile Geräteverwaltung (MDM) Auto Enrollment –MDM (Intune) Managed
   * Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)
     * Unterstützter Einzelbenutzer oder mehrere Benutzer pro Gerät
   * Verschiedene Ebenen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von Vollständig geöffnet bis Einzel-App-Kiosk.
   * Mindestens eine Anwendung wird über MDM bereitgestellt.

* Häufige Herausforderungen
   * Bestimmen, welche MDM-Konfigurationen auf die Anwendung HoloLens 2 Szenarioanforderungen angewendet werden.

[![Szenario: Diagramm ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

Im entsprechenden Cloud connected guide (Cloud verbundenes Handbuch) erfahren Sie, wie Sie HoloLens 2 bei Ihrer Geräteverwaltung registrieren, Lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer die Geräte bei der Geräteeinrichtung Remote Assist sofort verwenden können. Verwenden Sie den Leitfaden externe Clients, um Geräte für die kurzfristige oder langfristige externe Verwendung an einem Remotestandort bereitzustellen.

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch für cloudbasierte Umgebung](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch für cloudbasierte Umgebung (externe Clients)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Szenario B: Bereitstellen im Netzwerk Ihrer Organisation

Dieses Szenario ist identisch mit einer klassischen Bereitstellung für die Windows 10 PCs. HoloLens 2 wird hauptsächlich für die Verwendung im Unternehmensnetzwerk mit Zugriff auf interne Unternehmensressourcen bereitgestellt. Internet- und Clouddienste sind möglicherweise eingeschränkt. 

 * Grundlegende allgemeine Konfigurationen
   * Wi-Fi Netzwerk ist ein internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen und eingeschränktem Zugriff auf das Internet oder Clouddienste.
   * Azure AD der automatischen MDM-Registrierung
   * MDM (Intune) Verwaltet
   * Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)
     * Unterstützter Einzelbenutzer oder mehrere Benutzer pro Gerät
   * Verschiedene Ebenen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von Vollständig geöffnet bis Einzel-App-Kiosk.
   * Mindestens eine Anwendung wird über MDM bereitgestellt.

 * Häufige Herausforderungen
   * HoloLens 2 unterstützt keine lokale AD-Verknüpfung oder SCCM. Nur Azure AD mit MDM beitreten. Viele Unternehmen stellen heute noch Windows 10-PCs in diesem Szenario als lokale, in AD verbundene Geräte bereit, die von System Center Configuration Manager (SCCM) verwaltet werden und möglicherweise nicht die Infrastruktur für die Verwaltung interner Windows 10-Geräte über cloudbasierte MDM-Lösungen bereitgestellt/konfiguriert haben.
   * Da HoloLens 2 ein cloudbasiertes Gerät ist, ist es stark von mit dem Internet und der Cloud verbundenen Diensten für Benutzerauthentifizierung, Betriebssystemupdates, MDM-Verwaltung und so weiter abhängig. Beim Herstellen einer Verbindung mit einem Unternehmensnetzwerk müssen wahrscheinlich Proxy-/Firewallregeln angepasst werden, um den Zugriff für HoloLens 2 anwendungen zu ermöglichen, die darauf ausgeführt werden.
   * UnternehmensWi-Fi verbindung erfordert in der Regel Zertifikate, um das Gerät oder den Benutzer beim Netzwerk zu authentifizieren. Die erforderliche Infrastruktur oder Einstellungen zum Bereitstellen von Zertifikaten auf Windows 10 Geräten über MDM kann eine Herausforderung darstellen.

[![Diagramm zu Szenario B1 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagramm zu Szenario B2 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

Im entsprechenden Unternehmensnetzwerkleitfaden erfahren Sie, wie Sie HoloLens 2 bei Ihrer vorhandenen Geräteverwaltung registrieren, Lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer ein Dynamics 365-Handbuch betreiben und benutzerdefinierte Line-of-Business-Apps verwenden können, nachdem das Gerät eingerichtet wurde.

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch für Unternehmensnetzwerke](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Szenario C: Bereitstellen in einer sicheren Offlineumgebung

Dies ist eine typische Bereitstellung für äußerst sichere oder vertrauliche Standorte. HoloLens 2 wird für die Verwendung in erster Linie offline ohne Netzwerk- oder Internetzugriff bereitgestellt. 
 * Grundlegende allgemeine Konfigurationen
   * Wi-Fi Die Konnektivität ist deaktiviert. Ethernet über USB kann bei Bedarf für LAN-Verbindungen aktiviert werden.
   * Nicht verwaltet.
   * Lokales Benutzerkonto für die Geräte-Anmeldung.
     * HoloLens 2 unterstützt nur ein lokales Konto.
   * Unterschiedliche Ebenen von Gerätesperrungskonfigurationen werden über Bereitstellungspakete basierend auf bestimmten Anwendungsfällen angewendet. Diese Konfigurationen sind in der Regel aufgrund sicherer Umgebungsanforderungen eingeschränkt.
   * Mindestens eine Anwendung wird über das Bereitstellungspaket bereitgestellt.

 * Häufige Herausforderungen
   * Es gibt eine begrenzte Anzahl von Konfigurationen, die über Bereitstellungspakete verfügbar sind.
   * Clouddienste können nicht verwendet werden, wodurch die HoloLens 2 eingeschränkt wird.
   * Höherer Verwaltungsaufwand, da diese Geräte manuell eingerichtet, konfiguriert und aktualisiert werden müssen.

[![Sicheres Offlinediagramm 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

Der entsprechende Sichere Offlineleitfaden enthält Anweisungen zum Anwenden eines Beispielbereitstellungspakets, das eine HoloLens 2 für die Verwendung in sicheren Umgebungen sperrt.

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch für sichere Offlineumgebung](hololens-common-scenarios-offline-secure.md)


