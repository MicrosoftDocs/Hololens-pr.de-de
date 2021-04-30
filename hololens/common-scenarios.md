---
title: Allgemeine Szenarien für die Infrastrukturbereitstellung
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
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308785"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>Allgemeine Szenarien für die Infrastrukturbereitstellung – Übersicht

Die folgenden Informationen bieten eine allgemeine Übersicht über die Architektur für drei gängige Szenarien bei der Bereitstellung und Verwaltung von Microsoft HoloLens 2-Geräten im Unternehmen. Häufig wird die Art und Weise, wie Sie Ihre Geräte verwalten und auf die Ressourcen Ihrer Organisation zugreifen, größtenteils durch bereits eingerichtete Faktoren bestimmt. Basierend auf der vorhandenen Infrastruktur laden wir Sie ein, den allgemeinen Geräteverwaltungsstil in den folgenden Szenarien zu überprüfen und unsere Leitfäden für die Bereitstellung in dem Szenario auszuprobieren, das Ihren Anforderungen entspricht.

## <a name="scenarios"></a>Szenarien

Das folgende Diagramm stellt drei typische Szenarien für HoloLens 2 Bereitstellungen dar.
![Szenariodiagramm](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a>Szenario A: Bereitstellen auf Cloudverbindungsgeräten

HoloLens 2 wird in erster Linie in Umgebungen außerhalb eines Unternehmensnetzwerks bereitgestellt. Auf Unternehmensressourcen wird nicht zugegriffen oder kann über VPN eingeschränkt werden. Diese Bereitstellung ähnelt verwalteten mobilen Geräten innerhalb eines Unternehmens.
 * Grundlegende allgemeine Konfigurationen
   * Wi-Fi Netzwerke sind in der Regel vollständig für internet- und cloudbasierte Dienste geöffnet.
   * Azure AD Mit mobiler Geräteverwaltung (MDM) automatischer Registrierung beitreten – MDM (Intune) verwaltet
   * Benutzer melden sich mit ihrem eigenen Unternehmenskonto (Azure AD) an.
     * Einzelne oder mehrere Benutzer pro Gerät unterstützt
   * Unterschiedliche Ebenen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von Vollständig geöffnet bis zu Kiosk mit einzelner App.
   * Eine oder mehrere Anwendungen werden über MDM bereitgestellt.

* Häufige Herausforderungen
   * Bestimmen, welche MDM-Konfigurationen auf die Anwendung HoloLens 2 Szenarioanforderungen angewendet werden.

Ein Bereitstellungshandbuch, das dem Szenario ähnelt, finden Sie in unserem Leitfaden für cloudbasierte HoloLens 2 [mit Remote Assist.](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch – Cloud verbundene HoloLens 2 mit Remote Assist](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>Szenario B: Bereitstellen im Netzwerk Ihrer Organisation

HoloLens 2 wird hauptsächlich für die Verwendung im Unternehmensnetzwerk mit Zugriff auf interne Unternehmensressourcen bereitgestellt. Internet- und Clouddienste sind möglicherweise eingeschränkt. Diese Bereitstellung ist eine typische Bereitstellung für die Windows 10 PCs.

 * Grundlegende allgemeine Konfigurationen
   * Wi-Fi Netzwerk ist ein internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen und eingeschränktem Zugriff auf das Internet oder Clouddienste.
   * Azure AD der automatischen MDM-Registrierung
   * MDM (Intune) Verwaltet
   * Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)
     * Unterstützter Einzelbenutzer oder mehrere Benutzer pro Gerät
   * Verschiedene Ebenen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von Vollständig geöffnet bis Einzel-App-Kiosk.
   * Mindestens eine Anwendung wird über MDM bereitgestellt.

 * Häufige Herausforderungen
   * HoloLens 2 unterstützt keine lokale AD-Verknüpfung oder SCCM. Nur Azure AD mit MDM beitreten. Viele Unternehmen stellen in diesem Szenario weiterhin Windows 10-PCs als lokale, in AD verbundene Geräte bereit, die von System Center Konfigurations-Manager (SCCM) verwaltet werden. Möglicherweise ist die Infrastruktur für die Verwaltung interner Windows 10-Geräte über cloudbasierte MDM-Lösungen nicht bereitgestellt/konfiguriert.
   * Da es sich bei HoloLens 2 um ein cloudbasiertes Gerät handelt, basiert es in hohem Maße auf Mit dem Internet und mit der Cloud verbundenen Diensten für Benutzerauthentifizierung, Betriebssystemupdates, MDM-Verwaltung usw. Beim Herstellen einer Verbindung mit einem Unternehmensnetzwerk müssen wahrscheinlich Proxy-/Firewallregeln angepasst werden, um den Zugriff für HoloLens 2 und die darauf ausgeführten Anwendungen zu ermöglichen.
   * Unternehmens-Wi-Fi Konnektivität erfordert in der Regel Zertifikate, um das Gerät oder den Benutzer beim Netzwerk zu authentifizieren. Die erforderliche Infrastruktur oder die erforderlichen Einstellungen zum Bereitstellen von Zertifikaten auf Windows 10 Geräten über MDM können schwierig zu konfigurieren sein.

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch – Mit Dem Unternehmen verbundene HoloLens 2 mit Dynamics 365-Handbüchern](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>Szenario C: Bereitstellen in einer sicheren Offlineumgebung

HoloLens 2 wird für die Verwendung in erster Linie offline ohne Netzwerk- oder Internetzugriff bereitgestellt. Dies ist eine typische Bereitstellung für äußerst sichere oder vertrauliche Speicherorte.
 * Grundlegende allgemeine Konfigurationen
   * Wi-Fi Konnektivität ist deaktiviert. Ethernet über USB kann bei Bedarf für LAN-Konnektivität aktiviert werden.
   * Nicht verwaltet.
   * Lokales Benutzerkonto für die Geräteanmeldung.
     * HoloLens 2 unterstützt nur ein lokales Konto.
   * Unterschiedliche Ebenen von Gerätesperrungskonfigurationen werden über Bereitstellungspakete basierend auf bestimmten Anwendungsfällen angewendet. Diese Konfigurationen sind in der Regel aufgrund sicherer Umgebungsanforderungen eingeschränkt.
   * Eine oder mehrere Anwendungen werden über das Bereitstellungspaket bereitgestellt.

 * Häufige Herausforderungen
   * Über Bereitstellungspakete steht nur eine begrenzte Anzahl von Konfigurationen zur Verfügung.
   * Clouddienste können nicht verwendet werden, wodurch die HoloLens 2 Funktionen eingeschränkt werden.
   * Höherer Verwaltungsaufwand, da diese Geräte manuell eingerichtet, konfiguriert und aktualisiert werden müssen.

Eine Bereitstellungsanleitung, die diesem Szenario ähnelt, finden Sie im [Offline-Handbuch zur sicheren Bereitstellung.](hololens-common-scenarios-offline-secure.md)

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch – Sichere Offline HoloLens 2](hololens-common-scenarios-offline-secure.md)
