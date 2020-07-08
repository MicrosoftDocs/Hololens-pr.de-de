---
title: Allgemeine Szenarien für die Infrastrukturbereitstellung
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 6/30/2020
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
ms.openlocfilehash: f8d69fc988afabad5f4ae1cce9003381ceb8e68c
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857890"
---
# Allgemeine Szenarien für die Infrastrukturbereitstellung
Diese folgenden Informationen bieten eine allgemeine Architektur Übersicht für drei häufige Szenarien beim Bereitstellen und Verwalten von Microsoft HoloLens 2-Geräten innerhalb des Unternehmens.

## Szenarien

Das folgende Diagramm stellt drei typische Szenarien für HoloLens 2-Bereitstellungen dar. 
![Szenarien](images/scenarios.jpg)

### Szenario A

HoloLens 2 wird für die Verwendung in erster Linie in Umgebungen außerhalb eines Unternehmensnetzwerks bereitgestellt. Auf Unternehmensressourcen wird nicht zugegriffen, oder es ist möglich, dass Sie über VPN limitiert sind. Hierbei handelt es sich um eine Bereitstellung, die mit verwalteten mobilen Geräten in einem Unternehmen vergleichbar ist.
 * Allgemeine Standardkonfigurationen
   * WLAN-Netzwerke sind in der Regel vollständig für das Internet und die Cloud-Dienste geöffnet.
   * Azure AD Join with MDM Auto Enrollment--MDM (InTune) verwaltet
   * Benutzer anmelden mit einem eigenen Unternehmenskonto (AAD) 
     * Einzelne oder mehrere Benutzer pro Gerät unterstützt
   * Unterschiedliche Ebenen der Geräte Sperrungs Konfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, vom vollständig geöffneten zum einzelnen App-Kiosk.
   * Eine oder mehrere Anwendungen werden über MDM bereitgestellt.

* Häufige Herausforderungen
   * Ermitteln, welche MDM-Konfigurationen auf das HoloLens 2 basierend auf den Szenarien erforderlich sind.

### Szenario B

HoloLens 2 wird für die Verwendung in erster Linie im Unternehmensnetzwerk mit Zugriff auf interne Unternehmensressourcen bereitgestellt. Internet-und Cloud-Services sind möglicherweise limitiert. Dies ist eine typische Bereitstellung für die meisten Windows 10-PCs.
 * Allgemeine Standardkonfigurationen
   * Das Wi-Fi-Netzwerk ist ein internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen und begrenztem Zugriff auf das Internet oder Cloud-Dienste.
   * Azure AD-Join mit automatischer MDM-Registrierung 
   * MDM (InTune) verwaltet
   * Benutzer anmelden mit einem eigenen Unternehmenskonto (AAD)
     * Einzelne oder mehrere Benutzer pro Gerät unterstützt
   * Unterschiedliche Ebenen der Geräte Sperrungs Konfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, vom vollständig geöffneten zum einzelnen App-Kiosk.
   * Eine oder mehrere Anwendungen werden über MDM bereitgestellt.

 * Häufige Herausforderungen
   * HoloLens 2 unterstützt keine lokale Ad Join-oder SCCM-Funktion. Nur Azure AD-Join mit MDM. Viele Unternehmen stellen heute weiterhin Windows 10-PCs in diesem Szenario bereit, wie auf lokalen AD-Join-Geräten, die von System Center Configuration Manager (SCCM) verwaltet werden und möglicherweise nicht über die Infrastruktur bereitgestellt/konfiguriert sind, um interne Windows 10-Geräte über Cloud-basierte MDM-Lösungen zu verwalten.
   * Da es sich bei HoloLens 2 um ein Cloud-First-Device handelt, basiert es stark auf Internet-und Cloud-verbundenen Diensten für Benutzerauthentifizierung, Betriebssystemupdates, MDM-Verwaltung usw. Beim Herstellen einer Verbindung mit einem Unternehmensnetzwerk müssen Proxy/Firewall-Regeln höchstwahrscheinlich angepasst werden, um den Zugriff auf HoloLens 2 und die darauf ausgeführten Anwendungen zu ermöglichen. 
   * Für die Wi-Fi-Verbindung in Unternehmen sind in der Regel Zertifikate erforderlich, um das Gerät oder den Benutzer im Netzwerk zu authentifizieren. Die erforderliche Infrastruktur oder Einstellungen zum Bereitstellen von Zertifikaten auf Windows 10-Geräten über MDM können eine Herausforderung für die Konfiguration darstellen.

### Szenario C

HoloLens 2 wird für die Verwendung in erster Linie offline ohne Netzwerk-oder Internetzugriff bereitgestellt. Hierbei handelt es sich um eine typische Bereitstellung für hochsichere oder vertrauliche Speicherorte.
 * Allgemeine Standardkonfigurationen
   * Wi-Fi-Konnektivität ist deaktiviert. Ethernet über USB kann bei Bedarf für LAN-Konnektivität aktiviert werden.
   * Nicht verwaltet.
   * Lokales Benutzerkonto für Geräte Anmeldung.
     * HoloLens 2 unterstützt nur 1 lokales Konto.
   * Unterschiedliche Ebenen der Geräte Sperrungs Konfigurationen werden über Bereitstellungspakete basierend auf bestimmten Anwendungsfällen angewendet. Diese Konfigurationen sind in der Regel aufgrund sicherer Umgebungsanforderungen sehr eingeschränkt.
   * Eine oder mehrere Anwendungen werden über das Bereitstellungspaket bereitgestellt.

 * Häufige Herausforderungen
   * Es gibt eine begrenzte Anzahl von Konfigurationen, die über Bereitstellungspakete zur Verfügung stehen.
   * Cloud-Dienste sind nicht in der Lage, Leveraged zu nutzen, wodurch die HoloLens 2-Funktionen eingeschränkt werden.
   * Höherer Verwaltungsaufwand, da diese Geräte manuell eingerichtet, konfiguriert und aktualisiert werden müssen.
