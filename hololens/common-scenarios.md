---
title: Szenarien für die Bereitstellung einer gemeinsamen Infrastruktur
description: Einige häufige Bereitstellungsszenarien auf Grundlage unterschiedlicher allgemeiner Infrastrukturen
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
ms.openlocfilehash: e9e91535bb49b5076547e8b9934bdc86808d41fc
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195568"
---
# Übersicht über die allgemeinen Infrastruktur Bereitstellungsszenarien

Diese folgenden Informationen bieten eine allgemeine Architektur Übersicht für drei häufige Szenarien beim Bereitstellen und Verwalten von Microsoft HoloLens 2-Geräten innerhalb des Unternehmens. Häufig wird die Art und Weise, wie Sie Ihre Geräte verwalten, und wie der Zugriff auf die Ressourcen Ihrer Organisation überwiegend durch bereits vorhandene Faktoren bestimmt wird. Basierend auf der vorhandenen Infrastruktur laden wir Sie ein, den allgemeinen Geräte Verwaltungsstil in den folgenden Szenarien zu überprüfen und unsere Leitfäden für die Bereitstellung in dem Szenario zu testen, das Ihren Anforderungen entspricht.

## Szenarien

Das folgende Diagramm stellt drei typische Szenarien für HoloLens 2-Bereitstellungen dar.
![Szenarien-Diagramm](images/scenarios.jpg)

### Szenario A: Bereitstellen auf Cloud Connect-Geräten

HoloLens 2 wird für die Verwendung in erster Linie in Umgebungen außerhalb eines Unternehmensnetzwerks bereitgestellt. Auf Unternehmensressourcen wird nicht zugegriffen, oder es ist möglich, dass Sie über VPN limitiert sind. Hierbei handelt es sich um eine Bereitstellung, die mit verwalteten mobilen Geräten in einem Unternehmen vergleichbar ist.
 * Allgemeine Standardkonfigurationen
   * Wi-Fi Netzwerke sind in der Regel vollständig für das Internet und die Cloud-Dienste geöffnet.
   * Azure AD Join with MDM Auto Enrollment--MDM (InTune) verwaltet
   * Benutzer anmelden mit einem eigenen Unternehmenskonto (AAD)
     * Einzelne oder mehrere Benutzer pro Gerät unterstützt
   * Unterschiedliche Ebenen der Geräte Sperrungs Konfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, vom vollständig geöffneten zum einzelnen App-Kiosk.
   * Eine oder mehrere Anwendungen werden über MDM bereitgestellt.

* Häufige Herausforderungen
   * Ermitteln, welche MDM-Konfigurationen auf das HoloLens 2 basierend auf den Szenarien erforderlich sind.

Ein Bereitstellungshandbuch, das diesem Szenario ähnelt, finden Sie in unserem Leitfaden für [Cloud Connected HoloLens 2 mit Remote Unterstützung](hololens2-cloud-connected-overview.md).

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch – Cloud Connected HoloLens 2 mit Remote Unterstützung](hololens2-cloud-connected-overview.md)

### Szenario B: Bereitstellen im Netzwerk Ihrer Organisation

HoloLens 2 wird für die Verwendung in erster Linie im Unternehmensnetzwerk mit Zugriff auf interne Unternehmensressourcen bereitgestellt. Internet-und Cloud-Services sind möglicherweise limitiert. Dies ist eine typische Bereitstellung für die meisten Windows 10-PCs.
 * Allgemeine Standardkonfigurationen
   * Wi-Fi Netzwerk ist ein internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen sowie begrenztem Zugriff auf das Internet oder Cloud-Dienste.
   * Azure AD-Join mit automatischer MDM-Registrierung
   * MDM (InTune) verwaltet
   * Benutzer anmelden mit einem eigenen Unternehmenskonto (AAD)
     * Einzelne oder mehrere Benutzer pro Gerät unterstützt
   * Unterschiedliche Ebenen der Geräte Sperrungs Konfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, vom vollständig geöffneten zum einzelnen App-Kiosk.
   * Eine oder mehrere Anwendungen werden über MDM bereitgestellt.

 * Häufige Herausforderungen
   * HoloLens 2 unterstützt keine lokale Ad Join-oder SCCM-Funktion. Nur Azure AD-Join mit MDM. Viele Unternehmen stellen heute weiterhin Windows 10-PCs in diesem Szenario bereit, wie auf lokalen AD-Join-Geräten, die von System Center Configuration Manager (SCCM) verwaltet werden und möglicherweise nicht über die Infrastruktur bereitgestellt/konfiguriert sind, um interne Windows 10-Geräte über Cloud-basierte MDM-Lösungen zu verwalten.
   * Da es sich bei HoloLens 2 um ein Cloud-First-Device handelt, basiert es stark auf Internet-und Cloud-verbundenen Diensten für Benutzerauthentifizierung, Betriebssystemupdates, MDM-Verwaltung usw. Beim Herstellen einer Verbindung mit einem Unternehmensnetzwerk müssen Proxy/Firewall-Regeln höchstwahrscheinlich angepasst werden, um den Zugriff auf HoloLens 2 und die darauf ausgeführten Anwendungen zu ermöglichen.
   * Für Unternehmens Wi-Fi Verbindungen sind in der Regel Zertifikate erforderlich, um das Gerät oder den Benutzer im Netzwerk zu authentifizieren. Die erforderliche Infrastruktur oder Einstellungen zum Bereitstellen von Zertifikaten auf Windows 10-Geräten über MDM können eine Herausforderung für die Konfiguration darstellen.

### Szenario C: Bereitstellen in einer sicheren Offlineumgebung

HoloLens 2 wird für die Verwendung in erster Linie offline ohne Netzwerk-oder Internetzugriff bereitgestellt. Hierbei handelt es sich um eine typische Bereitstellung für hochsichere oder vertrauliche Speicherorte.
 * Allgemeine Standardkonfigurationen
   * Wi-Fi Konnektivität ist deaktiviert. Ethernet über USB kann bei Bedarf für LAN-Konnektivität aktiviert werden.
   * Nicht verwaltet.
   * Lokales Benutzerkonto für Geräte Anmeldung.
     * HoloLens 2 unterstützt nur 1 lokales Konto.
   * Unterschiedliche Ebenen der Geräte Sperrungs Konfigurationen werden über Bereitstellungspakete basierend auf bestimmten Anwendungsfällen angewendet. Diese Konfigurationen sind in der Regel aufgrund sicherer Umgebungsanforderungen sehr eingeschränkt.
   * Eine oder mehrere Anwendungen werden über das Bereitstellungspaket bereitgestellt.

 * Häufige Herausforderungen
   * Es gibt eine begrenzte Anzahl von Konfigurationen, die über Bereitstellungspakete zur Verfügung stehen.
   * Cloud-Dienste sind nicht in der Lage, Leveraged zu nutzen, wodurch die HoloLens 2-Funktionen eingeschränkt werden.
   * Höherer Verwaltungsaufwand, da diese Geräte manuell eingerichtet, konfiguriert und aktualisiert werden müssen.

Ein Bereitstellungshandbuch, das mit diesem Szenario vergleichbar ist, finden Sie in unserem [Leitfaden zur sicheren Bereitstellung in der Offline Bereitstellung](hololens-common-scenarios-offline-secure.md).

> [!div class="nextstepaction"]
> [Bereitstellungshandbuch – Offline Secure HoloLens 2](hololens-common-scenarios-offline-secure.md)
