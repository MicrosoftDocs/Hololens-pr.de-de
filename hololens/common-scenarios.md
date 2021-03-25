---
title: Szenarien für die Bereitstellung einer gemeinsamen Infrastruktur
description: Erfahren Sie mehr über einige der gängigsten Bereitstellungsszenarien, die auf unterschiedlichen Infrastrukturbereitstellungen für Mixed Reality basieren.
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
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448493"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>Übersicht über allgemeine Infrastrukturbereitstellungsszenarien

Diese folgenden Informationen bieten eine allgemeine Architekturübersicht für drei gängige Szenarien beim Bereitstellen und Verwalten von Microsoft HoloLens 2-Geräten innerhalb des Unternehmens. Häufig wird die Verwaltung Ihrer Geräte und der Zugriff auf die Ressourcen Ihrer Organisation weitgehend von bereits vorhandenen Faktoren bestimmt. Basierend auf der vorhandenen Infrastruktur laden wir Sie ein, den allgemeinen Geräteverwaltungsstil in den folgenden Szenarien zu überprüfen und unsere Anleitungen für die Bereitstellung in dem Szenario zu testen, das Ihren Anforderungen entspricht.

## <a name="scenarios"></a>Szenarien

Das folgende Diagramm stellt drei typische Szenarien für HoloLens 2-Bereitstellungen dar.
![Szenariodiagramm](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a>Szenario A: Bereitstellen auf Cloud-Connect-Geräten

HoloLens 2 wird für die Verwendung in erster Linie in Umgebungen außerhalb eines Unternehmensnetzwerks bereitgestellt. Auf Unternehmensressourcen wird nicht zugegriffen oder kann über VPN eingeschränkt werden. Diese Bereitstellung ähnelt verwalteten mobilen Geräten in einem Unternehmen.
 * Grundlegende allgemeine Konfigurationen
   * Wi-Fi sind in der Regel vollständig für das Internet und die Clouddienste geöffnet.
   * Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed
   * Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)
     * Einzelne oder mehrere Benutzer pro unterstützten Gerät
   * Unterschiedliche Stufen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von Fully Open bis Single App Kiosk.
   * Eine oder mehrere Anwendungen werden über MDM bereitgestellt

* Allgemeine Herausforderungen
   * Bestimmen, welche MDM-Konfigurationen auf holoLens 2 basierend auf den Szenarioanforderungen angewendet werden.

Eine Bereitstellungsanleitung, die dem Szenario ähnelt, finden Sie in unserem Leitfaden für [cloudintehte HoloLens 2 mit Remote assist](hololens2-cloud-connected-overview.md).

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch – Cloud-verbundenes HoloLens 2 mit Remoteunterstützung](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>Szenario B: Bereitstellen im Netzwerk Ihrer Organisation

HoloLens 2 wird für die Verwendung hauptsächlich im Unternehmensnetzwerk mit Zugriff auf interne Unternehmensressourcen bereitgestellt. Internet- und Clouddienste können eingeschränkt sein. Diese Bereitstellung ist eine typische Bereitstellung für die meisten Windows 10-PCs.

 * Grundlegende allgemeine Konfigurationen
   * Wi-Fi ist ein internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen und eingeschränktem Zugriff auf das Internet oder Clouddienste.
   * Azure AD Join with MDM Auto Enrollment
   * Verwaltetes MDM (Intune)
   * Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)
     * Einzelne oder mehrere Benutzer pro unterstützten Gerät
   * Unterschiedliche Stufen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von Fully Open bis Single App Kiosk.
   * Eine oder mehrere Anwendungen werden über MDM bereitgestellt

 * Allgemeine Herausforderungen
   * HoloLens 2 unterstützt keine lokale AD-Verknüpfung oder SCCM. Nur Azure AD tritt mit MDM bei. Viele Unternehmen stellen in diesem Szenario weiterhin Windows 10-PCs als lokale AD-beigetretene Geräte zur Verfügung, die von System Center Configuration Manager (SCCM) verwaltet werden und möglicherweise nicht die Infrastruktur für die Verwaltung interner Windows 10-Geräte über cloudbasierte MDM-Lösungen bereitgestellt/konfiguriert haben.
   * Da HoloLens 2 ein erstes Cloudgerät ist, basiert es in hohem Maße auf internet- und cloudgebundenen Diensten für die Benutzerauthentifizierung, Betriebssystemupdates, MDM-Verwaltung und so weiter. Beim Herstellen einer Verbindung mit einem Unternehmensnetzwerk müssen Proxy-/Firewallregeln höchstwahrscheinlich angepasst werden, um den Zugriff für HoloLens 2 und die darauf ausgeführten Anwendungen zu ermöglichen.
   * Für Wi-Fi Unternehmensverbindung sind in der Regel Zertifikate erforderlich, um das Gerät oder den Benutzer beim Netzwerk zu authentifizieren. Die erforderliche Infrastruktur oder Einstellungen zum Bereitstellen von Zertifikaten auf Windows 10-Geräten über MDM kann schwierig zu konfigurieren sein.

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch – Unternehmensintegte HoloLens 2 mit Dynamics 365-Anleitungen](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>Szenario C: Bereitstellen in sicherer Offlineumgebung

HoloLens 2 wird für die Verwendung hauptsächlich offline ohne Netzwerk- oder Internetzugriff bereitgestellt. Dies ist eine typische Bereitstellung für besonders sichere oder vertrauliche Standorte.
 * Grundlegende allgemeine Konfigurationen
   * Wi-Fi Konnektivität ist deaktiviert. Ethernet über USB kann bei Bedarf für die LAN-Verbindung aktiviert werden.
   * Nicht verwaltet.
   * Lokales Benutzerkonto für die Geräte-Anmeldung.
     * HoloLens 2 unterstützt nur ein lokales Konto.
   * Unterschiedliche Stufen von Gerätesperrungskonfigurationen werden über Bereitstellungspakete basierend auf bestimmten Verwendungsfällen angewendet. Diese Konfigurationen sind in der Regel aufgrund der Anforderungen an eine sichere Umgebung eingeschränkt.
   * Mindestens eine Anwendung wird über das Bereitstellungspaket bereitgestellt.

 * Allgemeine Herausforderungen
   * Es gibt eine begrenzte Anzahl von Konfigurationen, die über Bereitstellungspakete verfügbar sind
   * Clouddienste können nicht verwendet werden, was die HoloLens 2-Funktionen einschränkt.
   * Höherer Verwaltungsaufwand, da diese Geräte manuell eingerichtet, konfiguriert und aktualisiert werden müssen.

Eine Bereitstellungsanleitung, die diesem Szenario ähnelt, finden Sie in [unserem Leitfaden für die sichere Offlinebereitstellung.](hololens-common-scenarios-offline-secure.md)

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch – Offline Secure HoloLens 2](hololens-common-scenarios-offline-secure.md)
