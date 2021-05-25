---
title: Allgemeine Bereitstellungsszenarien für die Infrastruktur
description: Erfahren Sie mehr über einige der gängigsten Bereitstellungsszenarien, die auf verschiedenen Infrastrukturbereitstellungen für Mixed Reality basieren.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
keywords: hololens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 30a35fb0fe5d5b669249df25ebff0228b552596c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397419"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>Allgemeine Bereitstellungsszenarien für die Infrastruktur – Übersicht

Die folgenden Informationen bieten eine allgemeine Übersicht über die Architektur für drei gängige Szenarien beim Bereitstellen und Verwalten von Microsoft HoloLens 2 Geräten im Unternehmen. Häufig wird die Art und Weise, wie Sie Ihre Geräte verwalten und wie Sie auf die Ressourcen Ihrer Organisation zugreifen, größtenteils von bereits festgelegten Faktoren bestimmt. Basierend auf der vorhandenen Infrastruktur laden wir Sie ein, den allgemeinen Geräteverwaltungsstil in den folgenden Szenarien zu überprüfen und unsere Leitfäden für die Bereitstellung in dem Szenario auszuprobieren, das Ihren Anforderungen entspricht.

## <a name="scenarios"></a>Szenarien

Das folgende Diagramm zeigt zwei typische verwaltete Szenarien für HoloLens 2 Bereitstellungen.
 

Es gibt auch ein drittes Szenario, das sichere Offlinebereitstellungen ermöglicht.

### <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Szenario A: Bereitstellen auf mit der Cloud verbundenen Geräten

HoloLens 2 wird für die Verwendung in erster Linie in Umgebungen außerhalb eines Unternehmensnetzwerks bereitgestellt. Auf Unternehmensressourcen wird nicht zugegriffen oder kann über VPN eingeschränkt werden. Diese Bereitstellung ähnelt verwalteten mobilen Geräten innerhalb eines Unternehmens.
 * Grundlegende allgemeine Konfigurationen
   * Wi-Fi-Netzwerke sind in der Regel vollständig für das Internet und cloudbasierte Dienste geöffnet.
   * Azure AD join with Mobile Geräteverwaltung (MDM) Auto Enrollment –MDM (Intune) Managed
   * Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)
     * Unterstützter Einzelbenutzer oder mehrere Benutzer pro Gerät
   * Verschiedene Ebenen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von Vollständig geöffnet bis Einzel-App-Kiosk.
   * Mindestens eine Anwendung wird über MDM bereitgestellt.



* Häufige Herausforderungen
   * Bestimmen der MDM-Konfigurationen, die auf die HoloLens 2 angewendet werden sollen, basierend auf den Szenarioanforderungen.

[![Szenario: Diagramm ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

Ein Bereitstellungshandbuch, das diesem Szenario ähnelt, ist in unserem Leitfaden für die [Bereitstellung der cloudfähigen Umgebung zu lesen.](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch für eine mit der Cloud verbundene Umgebung](hololens2-cloud-connected-overview.md)
> [!div class="nextstepaction"]
> [Bereitstellungshandbuch für eine cloudverbundene Umgebung (externe Clients)](hololens2-deployment-guide.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>Szenario B: Bereitstellen innerhalb des Netzwerks Ihrer Organisation

HoloLens 2 wird für die Verwendung in erster Linie im Unternehmensnetzwerk mit Zugriff auf interne Unternehmensressourcen bereitgestellt. Internet- und Clouddienste können eingeschränkt sein. Diese Bereitstellung ist eine typische Bereitstellung für die meisten Windows 10 PCs.

 * Grundlegende allgemeine Konfigurationen
   * Wi-Fi Netzwerk ist ein internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen und eingeschränktem Zugriff auf das Internet oder Clouddienste.
   * Azure AD Beitreten zur automatischen MDM-Registrierung
   * MDM (Intune) Verwaltet
   * Benutzer melden sich mit ihrem eigenen Unternehmenskonto (Azure AD) an.
     * Einzelne oder mehrere Benutzer pro Gerät unterstützt
   * Unterschiedliche Ebenen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von Vollständig geöffnet bis zu Kiosk mit einzelner App.
   * Eine oder mehrere Anwendungen werden über MDM bereitgestellt.

 * Häufige Herausforderungen
   * HoloLens 2 unterstützt keine lokale AD-Verknüpfung oder SCCM. Nur Azure AD mit MDM beitreten. Viele Unternehmen stellen in diesem Szenario weiterhin Windows 10-PCs als lokale, in AD verbundene Geräte bereit, die von System Center Konfigurations-Manager (SCCM) verwaltet werden. Möglicherweise ist die Infrastruktur für die Verwaltung interner Windows 10-Geräte über cloudbasierte MDM-Lösungen nicht bereitgestellt/konfiguriert.
   * Da HoloLens 2 ein cloudbasiertes Gerät ist, ist es stark von mit dem Internet und der Cloud verbundenen Diensten für Benutzerauthentifizierung, Betriebssystemupdates, MDM-Verwaltung und so weiter abhängig. Beim Herstellen einer Verbindung mit einem Unternehmensnetzwerk müssen wahrscheinlich Proxy-/Firewallregeln angepasst werden, um den Zugriff für HoloLens 2 anwendungen zu ermöglichen, die darauf ausgeführt werden.
   * UnternehmensWi-Fi verbindung erfordert in der Regel Zertifikate, um das Gerät oder den Benutzer beim Netzwerk zu authentifizieren. Die erforderliche Infrastruktur oder Einstellungen zum Bereitstellen von Zertifikaten auf Windows 10 Geräten über MDM kann eine Herausforderung darstellen.

[![Diagramm zu Szenario B1 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagramm zu Szenario B2 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

Ein Bereitstellungshandbuch, das diesem Szenario ähnelt, finden Sie in unserem Leitfaden für die [Bereitstellung von Unternehmensnetzwerken.](hololens2-corp-connected-overview.md)

> [!div class="nextstepaction"]
> [Handbuch zur Bereitstellung von Unternehmensnetzwerken](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>Szenario C: Bereitstellen in einer sicheren Offlineumgebung

HoloLens 2 wird für die Verwendung in erster Linie offline ohne Netzwerk- oder Internetzugriff bereitgestellt. Dies ist eine typische Bereitstellung für äußerst sichere oder vertrauliche Standorte.
 * Grundlegende allgemeine Konfigurationen
   * Wi-Fi Die Konnektivität ist deaktiviert. Ethernet über USB kann bei Bedarf für LAN-Verbindungen aktiviert werden.
   * Nicht verwaltet.
   * Lokales Benutzerkonto für die Geräte-Anmeldung.
     * HoloLens 2 unterstützt nur ein lokales Konto.
   * Unterschiedliche Ebenen von Gerätesperrungskonfigurationen werden über Bereitstellungspakete basierend auf bestimmten Anwendungsfällen angewendet. Diese Konfigurationen sind in der Regel aufgrund sicherer Umgebungsanforderungen eingeschränkt.
   * Eine oder mehrere Anwendungen werden über das Bereitstellungspaket bereitgestellt.

 * Häufige Herausforderungen
   * Über Bereitstellungspakete steht nur ein begrenzter Satz von Konfigurationen zur Verfügung.
   * Clouddienste können nicht verwendet werden, wodurch die HoloLens 2 Funktionen eingeschränkt werden.
   * Höherer Verwaltungsaufwand, da diese Geräte manuell eingerichtet, konfiguriert und aktualisiert werden müssen.

[![Sicheres Offlinediagramm 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

Ein Bereitstellungshandbuch, das diesem Szenario ähnelt, ist im [Bereitstellungshandbuch für die sichere Offlineumgebung zu lesen.](hololens-common-scenarios-offline-secure.md)

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch für eine sichere Offlineumgebung](hololens-common-scenarios-offline-secure.md)
