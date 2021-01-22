---
title: Szenarien für die Bereitstellung einer gemeinsamen Infrastruktur
description: Erfahren Sie mehr über einige der gängigsten Bereitstellungsszenarien, die auf unterschiedlichen Infrastrukturbereitstellungen für Mixed Reality basieren.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 11/04/2020
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
ms.openlocfilehash: 6f398327ba82e15a15da21c2b3f90222178d257a
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283626"
---
# Übersicht über allgemeine Infrastrukturbereitstellungsszenarien

Die folgenden Informationen bieten eine allgemeine Architekturübersicht für drei gängige Szenarien beim Bereitstellen und Verwalten von Microsoft HoloLens 2-Geräten innerhalb des Unternehmens. Wie Sie Ihre Geräte verwalten und wie Sie auf die Ressourcen Ihrer Organisation zugreifen, hängt häufig von faktoren ab, die bereits vorhanden sind. Basierend auf der vorhandenen Infrastruktur laden wir Sie ein, den gemeinsamen Geräteverwaltungsstil in den folgenden Szenarien zu überprüfen und unsere Anleitungen für die Bereitstellung in dem Szenario zu testen, das Ihren Anforderungen entspricht.

## Szenarien

Das folgende Diagramm stellt drei typische Szenarien für HoloLens 2-Bereitstellungen dar.
![Szenariodiagramm](images/scenarios.jpg)

### Szenario A: Bereitstellen auf Cloud -Connect-Geräten

HoloLens 2 wird für die Verwendung in erster Linie in Umgebungen außerhalb eines Unternehmensnetzwerks bereitgestellt. Auf Unternehmensressourcen wird nicht zugegriffen oder kann über VPN eingeschränkt werden. Diese Bereitstellung ähnelt verwalteten mobilen Geräten in einem Unternehmen.
 * Grundlegende allgemeine Konfigurationen
   * Wi-Fi sind in der Regel vollständig für internet- und cloudbasierte Dienste geöffnet.
   * Azure AD Join with Mobile Device Management (MDM) Auto Enrollment --MDM (Intune) Managed
   * Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)
     * Einzelne oder mehrere Benutzer pro Gerät unterstützt
   * Unterschiedliche Ebenen von Gerätesperrmoduskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von "Vollständig geöffnet" bis "Single App Kiosk".
   * Eine oder mehrere Anwendungen werden über MDM bereitgestellt

* Häufige Herausforderungen
   * Bestimmen der MDM-Konfigurationen, die auf HoloLens 2 angewendet werden, basierend auf den Szenarioanforderungen.

Ein Bereitstellungshandbuch, das Szenario ähnelt. Lesen Sie unser Handbuch für mit der Cloud verbundene [HoloLens 2 mit Remote Assist.](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch – Mit der Cloud verbundene HoloLens 2 mit Remote Assist](hololens2-cloud-connected-overview.md)

### Szenario B: Bereitstellen innerhalb des Netzwerks Ihrer Organisation

HoloLens 2 wird für die Verwendung in erster Linie im Unternehmensnetzwerk mit Zugriff auf interne Unternehmensressourcen bereitgestellt. Internet- und Clouddienste können eingeschränkt sein. Diese Bereitstellung ist eine typische Bereitstellung für die meisten Windows 10-PCs.

 * Grundlegende allgemeine Konfigurationen
   * Wi-Fi ist ein internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen und eingeschränktem Zugriff auf das Internet oder Clouddienste.
   * Azure AD Join mit automatischer MDM-Registrierung
   * MDM (Intune) Managed
   * Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)
     * Einzelne oder mehrere Benutzer pro Gerät unterstützt
   * Unterschiedliche Ebenen von Gerätesperrmoduskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von "Vollständig geöffnet" bis "Single App Kiosk".
   * Eine oder mehrere Anwendungen werden über MDM bereitgestellt

 * Häufige Herausforderungen
   * HoloLens 2 unterstützt keine lokale AD-Verknüpfung oder SCCM. Nur Azure AD wird mit MDM beitreten. Viele Unternehmen stellen in diesem Szenario weiterhin Windows 10-PCs als lokale AD-beigetretene Geräte zur Verfügung, die von System Center Configuration Manager (SCCM) verwaltet werden und möglicherweise nicht die Infrastruktur für die Verwaltung interner Windows 10-Geräte über cloudbasierte MDM-Lösungen bereitgestellt/konfiguriert haben.
   * Da HoloLens 2 ein erstes Cloudgerät ist, ist es in hohem Maße auf Internet- und Clouddienste für benutzerbasierte Authentifizierung, Betriebssystemupdates, die Verwaltung von MDM und vieles mehr angewiesen. Beim Herstellen einer Verbindung mit einem Unternehmensnetzwerk müssen Proxy-/Firewallregeln höchstwahrscheinlich angepasst werden, um den Zugriff für HoloLens 2 und die Darauf ausgeführten Anwendungen zu ermöglichen.
   * Die Wi-Fi Unternehmensnetzwerk erfordert in der Regel Zertifikate, um das Gerät oder den Benutzer beim Netzwerk zu authentifizieren. Die erforderliche Infrastruktur oder einstellungen für die Bereitstellung von Zertifikaten auf Windows 10-Geräten über MDM kann eine Herausforderung darstellen.

### Szenario C: Bereitstellen in einer sicheren Offlineumgebung

HoloLens 2 wird für die Verwendung in erster Linie offline ohne Netzwerk- oder Internetzugriff bereitgestellt. Dies ist eine typische Bereitstellung für hochgradig sichere oder vertrauliche Speicherorte.
 * Grundlegende allgemeine Konfigurationen
   * Wi-Fi Konnektivität ist deaktiviert. Ethernet über USB kann bei Bedarf für die LAN-Konnektivität aktiviert werden.
   * Nicht verwaltet.
   * Lokales Benutzerkonto für die Geräte-Anmeldung.
     * HoloLens 2 unterstützt nur ein lokales Konto.
   * Unterschiedliche Ebenen von Gerätesperrmoduskonfigurationen werden über Bereitstellungspakete basierend auf bestimmten Verwendungsfällen angewendet. Diese Konfigurationen sind in der Regel aufgrund sicherer Umgebungsanforderungen eingeschränkt.
   * Mindestens eine Anwendung wird über das Bereitstellungspaket bereitgestellt

 * Häufige Herausforderungen
   * Es gibt eine begrenzte Anzahl von Konfigurationen, die über Bereitstellungspakete verfügbar sind.
   * Clouddienste können nicht verwendet werden, wodurch die HoloLens 2-Funktionen eingeschränkt werden.
   * Höherer Verwaltungsaufwand, da diese Geräte manuell eingerichtet, konfiguriert und aktualisiert werden müssen.

Ein Bereitstellungshandbuch, das diesem Szenario ähnelt, finden Sie im [Handbuch zur sicheren Offlinebereitstellung.](hololens-common-scenarios-offline-secure.md)

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch – Offline Secure HoloLens 2](hololens-common-scenarios-offline-secure.md)
