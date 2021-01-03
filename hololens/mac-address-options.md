---
title: Enterprise-Registrierung von HoloLens-Geräten in einer auf MAC-Adressen beschränkten WLAN-Umgebung
description: 'So wird es gemacht: MAC-Adresse für Netzwerk auf HoloLens 2-Geräten'
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 3e06540dd7dca8892cd69abaf9a318d46ca0f3f2
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253142"
---
# Enterprise-Registrierung von HoloLens-Geräten in einer auf MAC-Adressen beschränkten WLAN-Umgebung

In diesem Dokument wird ein gängiges Szenario beschrieben, das in Kundenumgebungen festgelegt wurde, in denen das WLAN-System durch MAC-Adressen eingeschränkt wird, oder Zertifikate für die Teilnahme an drahtlosen Netzwerken erforderlich sind.

## Beispielszenario

Viele Kunden in sicheren Umgebungen haben Beschränkungen in Ihren drahtlosen oder verkabelten Netzwerken, die nur genehmigten Geräten (basierend auf MAC-Adressen) das erfolgreiche Herstellen einer Verbindung ermöglichen (entweder mit der MAC-Adressfilterung auf einem Zugriffspunkt oder auf einem DHCP-Server). Außerdem können einige drahtlose Netzwerke mit PEAP geschützt werden, was erfordert, dass ein Zertifikat auf das Gerät angewendet ist, bevor das drahtlose Netzwerk erfolgreich authentifiziert werden kann.

Bei HoloLens-Geräten können zwei wichtige Probleme auftreten, die zu Verzögerungen und manueller Arbeit beim Verbinden der HoloLens-Geräte mit dem Netzwerk führen können.

- Das drahtlose PEAP-Zertifikat muss auf das Gerät angewendet werden, bevor das Gerät erfolgreich mit dem drahtlosen Netzwerk verbunden wird.
- Die MAC-Adresse des HoloLens-WLAN-Adapters muss registriert werden.

Die wichtigsten Herausforderungen hierfür sind:

1. Die MAC-Adresse kann derzeit nur anhand der Einstellungs-App auf dem Gerät oder aus Intune nach einer erfolgreichen Intune-Registrierung bestimmt werden.
2. Ohne die MAC-Adresse kann das Gerät nicht mit dem WLAN-Netzwerk verbunden werden, um die Registrierung zu starten.
3. Manuelle Lösungen für diese Herausforderungen erfordern den Einsatz von Technikern an den Geräten.

## Lösungen

Es gibt viele Möglichkeiten, diese Situation zu verbessern, abhängig von der in der Umgebung verfügbaren Infrastruktur.

| Lösung | Vorteile | Anforderungen |
| --- | --- | --- |
| Bereitstellungspaket mit Ethernet-Adapter | Verbessert die OOBE-Erfahrung und ermöglicht eine schnellere Techniker-Erfahrung. | HoloLens kompatibler USB-C-Hub. Der Techniker muss für die MAC-Erfassung und OOBE-Fertigstellung noch mit dem Gerät interagieren |
| Autopilot mit Intune-Registrierung über Ethernet | Einstufige Verbindung und Registrierung des Geräts an die Kundenumgebung. Die MAC-Erfassung kann ohne Interaktion mit dem Gerät durchgeführt werden | Intune für den Kunden aktiviert. Azure AD TenantHoloLens kompatibler USB-C-Netzwerkadapter |
| Automatisierte Berichterstattung von MAC-Adressen | Wenn Geräte innerhalb des Intune-Mandanten registriert wurden, skripten Sie die Berichterstattung der MAC-Adresse an den Techniker. | Intune PowerShell-Commandlets |

## Bereitstellungspaket mit Ethernet-Adapter

> [!NOTE] 
> Wenn das verkabelte Netzwerk auch MAC-Beschränkungen unterliegt, muss die MAC-Adresse des USB-C-Ethernet-Adapters/-Hubs vorab genehmigt werden. Bei diesem Hub sollten Sie darauf achten, dass der Zugriff auf das Netzwerk von anderen Geräten aus ermöglicht wird.

### Anforderungen

- Verkabelter Netzwerk-Port mit Zugriff auf das Kundennetzwerk
- HoloLens kompatibler USB-C-Hub mit einem Ethernet-Adapter – Jeder Hub, der keine zusätzlichen Treiber oder Anwendungsinstallationen erfordert, sollte geeignet sein.
- Bereitstellungspaket enthält:
  - Informationen zum drahtlosen Netzwerk und Zertifikat
  - Informationen zur Registrierung für Azure AD der Organisation&#39;s (optional)
  - Alle anderen erforderlichen Bereitstellungseinstellungen

### Process

Der Vorgang kann je nach Softwareebene des Geräts variieren. Wenn auf dem Gerät das [Mai 2004 Update](hololens-release-notes.md#windows-holographic-version-2004) vorhanden ist, führen Sie die folgenden Schritte aus.

1. Platzieren Sie das Bereitstellungspaket auf dem Stamm eines USB-Sticks und schließen Sie es an den Hub an.
2. Verbinden Sie das Ethernet-Kabel mit dem Hub.
3. Verbinden Sie den USB-C-Hub mit dem HoloLens-Gerät.
4. Schalten Sie das HoloLens-Gerät ein, und tragen Sie das Gerät.
5. Drücken Sie die **Lautstärke-nach-unten-Taste**, um das Bereitstellungspaket anzuwenden.
6. Der Techniker kann nun die OOBE verfolgen und nach Fertigstellung die Einstellungs-App öffnen und die MAC-Adresse des Geräts abrufen.

Wenn auf dem Gerät ein Betriebssystem-Build vor dem [Mai 2004 Update](hololens-release-notes.md#windows-holographic-version-2004) vorhanden ist, führen Sie die folgenden Schritte aus.

1. Schalten Sie das HoloLens-Gerät ein und schließen Sie das Gerät an einen PC an.
2. Das Gerät sollte auf dem PC als Datei-Speichervorrichtung angezeigt werden.
3. Kopieren Sie das Bereitstellungspaket auf dem Gerät
4. Verbinden Sie das Ethernet-Kabel mit dem Hub.
5. Verbinden Sie den USB-C-Hub mit dem HoloLens-Gerät.
6. Tragen Sie das Gerät.
7. Drücken Sie die **Lautstärke-nach-unten-Taste**, um das Bereitstellungspaket anzuwenden.
8. Der Techniker kann nun die OOBE verfolgen und nach Fertigstellung die Einstellungs-App öffnen und die MAC-Adresse des Geräts abrufen.

### Vorteile

Auf diese Weise kann mit einer &quot;einzigen Berührung&quot; des Geräts das korrekte Bereitstellungspaket angewendet und die MAC-Adresse des Geräts erfasst werden. [Bereitstellungspakete können entsprechend der hier aufgeführten Anleitung erstellt werden.](https://docs.microsoft.com/hololens/hololens-provisioning)

## Autopilot mit Intune-Registrierung

### Anforderungen

- Verkabelter Netzwerk-Port mit Zugriff auf das Kundennetzwerk
- HoloLens-Geräte unter Windows holographisch 2004
- HoloLens kompatibler USB-C-Hub
- Intune eingerichtet und für den Kundenmandanten aktiviert
- Für Autopilot registriertes und in den Kundenmandanten importiertes Gerät
- Für das Gerät definierte Intune-Richtlinien:
   - Informationen zum drahtlosen Netzwerk und Zertifikat
   - Alle anderen erforderlichen Bereitstellungseinstellungen

Auf diese Weise kann ein Kunde mit fortgeschrittenen Netzwerkanforderungen die Geräte in einem praktischen, skalierbaren Ansatz registrieren.

Weitere Voraussetzungen sind wie unten aufgeführt erforderlich:
1. [Aktivieren des Mandanten für die Autopilot-Vorschau](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. Erstellen der HoloLens-Richtlinien, um das Bereitstellungspaket in Intune zu ersetzen.
1. Erstellen der HoloLens-Intune-Richtlinien.
1. Zuordnen der Geräte zur richtigen Gruppe.

### Process

1. Schließen Sie den USB-C-Hub und das Ethernet-Kabel an das HoloLens 2-Gerät an.
2. Schalten Sie HoloLens 2 ein.
3. Das Gerät sollte sich bei der OOBE über den Ethernet-Adapter automatisch mit dem Internet verbinden, die Autopilot-Konfiguration erkennen und sich automatisch bei Azure AD und Intune registrieren
4. Das Gerät wendet die erforderlichen WLAN-Zertifikate und andere Konfigurationen nach Bedarf über Intune an
5. Nach Fertigstellung kann der Techniker das Intune (Endpunkt-Manager)-Portal laden und die Seite "Geräteeigenschaften" unter **Start -> Geräte -> Gerätename -> Hardware** aufrufen
6. Die WLAN-MAC-Adresse wird im Intune-Portal angezeigt

![MAC-Adresse über Intune](images/mac-address-intune.jpg)

7. Der Techniker wird diese MAC-Adresse als zulässiges Gerät hinzufügen.

### Vorteile

Dies ermöglicht dem Techniker eine &quot;"Heads off"&quot;-Bereitstellungserfahrung, bei der das Gerät von der Box zum Azure AD und Intune übergehen kann, ohne dass der Techniker das Gerät tragen oder manuell mit der HoloLens-Umgebung interagieren muss.

## Berichterstattung von MAC-Adressen an den Techniker

### Anforderungen

- Autorisierung der &quot;Intune Graph-PowerShell&quot; gegenüber dem Kundenmandanten
- Installation der Intune Graph-PowerShell auf dem Computer des Technikers.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Lesezugriff auf die Elemente &quot;Verwaltete Geräte&quot; von Intune. (Helpdesk-Operator oder höher oder eine benutzerdefinierte Rolle)

Derzeit gibt es keine &quot;einfache&quot; Möglichkeit, einen Automatisierungsbefehl basierend auf der Registrierung eines neuen Geräts in Intune auszulösen. Daher bietet dieser Befehl dem Techniker eine einfache Möglichkeit, die MAC-Adresse abzurufen, ohne dass er sich am Portal anmelden und sie manuell abrufen muss.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Dadurch werden der Name und die MAC-Adresse aller HoloLens-Geräte zurückgegeben, die in den letzten 30 Tagen registriert wurden.

![Mac-Adresse über PowerShell](images/mac-address-powershell.jpg)

### Process

Nachdem die Intune-Registrierung abgeschlossen ist, wird der Techniker das obige Skript ausführen, um die MAC-Adresse abzurufen.
