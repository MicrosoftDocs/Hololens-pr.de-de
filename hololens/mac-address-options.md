---
title: Enterprise-Registrierung von HoloLens-Geräten in einer auf MAC-Adressen beschränkten WLAN-Umgebung
description: 'So wird‘s gemacht: MAC-Adresse für das Netzwerk auf HoloLens 2-Geräten'
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
ms.openlocfilehash: d21a63aae94f5ea5269f61fe319a9036626de1b4
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189527"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Enterprise-Registrierung von HoloLens-Geräten in einer auf MAC-Adressen beschränkten WLAN-Umgebung

In diesem Dokument wird ein gängiges Szenario beschrieben, das wir in Kundenumgebungen gefunden haben, in denen das WLAN-System durch MAC-Adressen eingeschränkt ist oder Zertifikate für die Teilnahme an drahtlosen Netzwerken erforderlich sind.

## <a name="example-scenario"></a>Beispielszenario

Viele Kunden in sicheren Umgebungen haben Einschränkungen für ihre Drahtlos- oder Kabelnetzwerke, die es nur genehmigten Geräten (basierend auf MAC-Adressen) erlauben, erfolgreich eine Verbindung herzustellen. Dies kann durch MAC-Adressfilterung auf einem drahtlosen Zugriffspunkt oder über einen DHCP-Server erzwungen werden. Darüber hinaus können einige drahtlose Netzwerke mit PEAP geschützt werden. Dafür muss vor der Authentifizierung im drahtlosen Netzwerk ein Zertifikat auf das Gerät angewendet werden.

In diesem Szenario können zwei Hauptanforderungen zu Verzögerungen führen oder manuelle Eingriffe erfordern, wenn HoloLens-Geräte mit dem Netzwerk verbunden werden:

- Das drahtlose PEAP-Zertifikat muss auf das Gerät angewendet werden, bevor das Gerät erfolgreich mit dem drahtlosen Netzwerk verbunden wird.
- Die MAC-Adresse des HoloLens-WLAN-Adapters muss registriert werden.

Dies sind die Kernherausforderungen bei den oben genannten Anforderungen:

1. Die MAC-Adresse kann derzeit nur über die Einstellungen-App auf dem Gerät oder nach erfolgreicher Registrierung über Intune bestimmt werden.

2. Ohne die MAC-Adresse kann das Gerät nicht mit dem WLAN-Netzwerk verbunden werden, um die Registrierung zu starten.

3. Manuelle Problemumgehungen für diese Herausforderungen machen es erforderlich, dass ein Techniker mit dem Gerät interagiert.

## <a name="solutions"></a>Lösungen

Es gibt viele Möglichkeiten, diese Situation zu verbessern, abhängig von der in der Umgebung verfügbaren Infrastruktur.

| Lösung | Vorteile | Requirements (Anforderungen) |
| --- | --- | --- |
| Bereitstellungspaket mit Ethernet-Adapter | Verbessert die Ersteinrichtungserfahrung und bietet eine schnellere Umgebung für Techniker. | Mit HoloLens kompatibler USB-C-Hub + Ethernet-Adapter, und trotzdem muss ein Techniker für die MAC-Erfassung und die OOBE-Fertigstellung mit dem Gerät interagieren |
| Autopilot mit Intune-Registrierung über Ethernet | Dies ist eine Verbindung und Registrierung des Geräts in der Kundenumgebung in einem Schritt. Die MAC-Erfassung kann abgeschlossen werden, ohne dass eine Interaktion mit dem Gerät erforderlich ist | Für den AAD-Mandanten des Kunden aktiviertes Intune und ein HoloLens-kompatibler USB-C-Ethernet-Adapter |
| Automatisierte Meldung von MAC-Adressen | Wenn Geräte beim Intune-Mandanten registriert sind, kann ein Skript dem Techniker die MAC-Adresse melden. | Intune PowerShell-Cmdlets |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Bereitstellungspaket mit Ethernet-Adapter

> [!NOTE] 
> Wenn für das kabelgebundene Netzwerk ebenfalls MAC-Einschränkungen gelten, muss auch die MAC-Adresse des USB-C Hub + Ethernet-Adapters vorab genehmigt werden. Bei diesem Adapter ist Vorsicht geboten, da er den Zugriff auf das Netzwerk von anderen Geräten aus ermöglicht.

### <a name="requirements"></a>Requirements (Anforderungen)

- Kabelgebundener Netzwerkport mit Zugriff auf das Kundennetzwerk
- Mit HoloLens kompatibler USB-C-Hub mit Ethernet-Adapter: Jeder Adapter, für den keine Installation zusätzlicher Treiber oder Anwendungen erforderlich ist, sollte geeignet sein.
- Bereitstellungspaket mit diesem Inhalt:
  - Enthaltene Informationen und Zertifikat für das Drahtlosnetzwerk
  - Optional enthaltene Registrierungsinformationen für das Azure AD der Organisation
  - Alle anderen erforderlichen Bereitstellungseinstellungen

### <a name="process"></a>Prozess

Der Vorgang kann je nach Softwareebene des Geräts variieren. Wenn das Gerät über das [Update 2004 vom Mai verfügt](hololens-release-notes.md#windows-holographic-version-2004), führen Sie die folgenden Schritte aus.

1. Platzieren Sie das Bereitstellungspaket im Stamm eines USB-Sticks, und schließen Sie es an den Hub an.
2. Schließen Sie das Ethernetkabel an den Hub + Ethernet-Adapter an.
3. Schließen Sie den USB-C-Hub an das HoloLens-Gerät an.
4. Schalten Sie die HoloLens und das Gerät ein.
5. Drücken Sie die Schaltflächen **„Leiser“ und „Ein/Aus“** , um das Bereitstellungspaket anzuwenden.
6. Der Techniker kann nun der Ersteinrichtung folgen und nach Abschluss die Einstellungen-App öffnen, um die MAC-Adresse des Geräts abzurufen.

Wenn auf dem Gerät ein Betriebssystem-Build vor dem [Update 2004 vom Mai](hololens-release-notes.md#windows-holographic-version-2004) vorhanden ist, führen Sie die folgenden Schritte aus.

1. Schalten Sie die HoloLens ein, und schließen Sie das Gerät an einen PC an.
2. Das Gerät sollte auf dem PC als Dateispeichergerät angezeigt werden.
3. Kopieren Sie das Bereitstellungspaket auf das Gerät
4. Verbinden Sie das Ethernet-Kabel mit dem Hub.
5. Schließen Sie den USB-C-Hub an das HoloLens-Gerät an.
6. Setzen Sie die HoloLens auf
7. Drücken Sie die Schaltflächen **„Leiser“ und „Ein/Aus“** , um das Bereitstellungspaket anzuwenden.
8. Der Techniker kann nun der Ersteinrichtung folgen und nach Abschluss die Einstellungen-App öffnen, um die MAC-Adresse des Geräts abzurufen.

### <a name="benefits"></a>Vorteile

Dadurch wird eine „Einzeltoucheingabe“ des Geräts ermöglicht, um das richtige Bereitstellungspaket anzuwenden und die MAC-Adresse des Geräts zu erfassen. [Bereitstellungspakete können entsprechend der hier aufgeführten Anleitung erstellt werden](hololens-provisioning.md).

## <a name="autopilot-with-intune-enrollment"></a>Autopilot mit Intune-Registrierung

### <a name="requirements"></a>Requirements (Anforderungen)

- Kabelgebundener Netzwerkport mit Zugriff auf das Kundennetzwerk
- HoloLens-Geräte unter Windows Holographic 2004
- HoloLens-kompatibler USB-C-Ethernet-Adapter
- Eingerichtetes und für den Kundenmandanten aktiviertes Intune
- Für Autopilot registriertes und in den Kundenmandanten importiertes Gerät
- Für das Gerät definierte Intune-Richtlinien:
   - Enthaltene Informationen und Zertifikat für das Drahtlosnetzwerk
   - Alle anderen erforderlichen Bereitstellungseinstellungen

Auf diese Weise kann ein Kunde mit fortgeschrittenen Netzwerkanforderungen die Geräte in einem skalierbaren Ansatz ohne Benutzereingriff registrieren

Weitere Voraussetzungen sind wie unten aufgeführt erforderlich:
1. [Aktivieren des Mandanten für die Autopilot-Vorschau](hololens2-autopilot.md).
1. Erstellen Sie die HoloLens-Richtlinien, um das Bereitstellungspaket in Intune zu ersetzen.
1. Erstellen Sie die HoloLens-Intune-Richtlinien.
1. Weisen Sie die Geräte der richtigen Gruppe zu.

### <a name="process"></a>Prozess

1. Verbinden Sie das Ethernet-Kabel mit dem Adapter, und stecken Sie den Adapter in den USB-C-Anschluss des HoloLens 2-Geräts.

2. Schalten Sie die HoloLens ein.

3. Das Gerät sollte während der Ersteinrichtung automatisch eine Internetverbindung über den Ethernet-Adapter herstellen. Es sollte die Autopilot-Konfiguration erkennen und sich automatisch bei Azure AD und Intune registrieren.

4. Das Gerät wendet die erforderlichen WLAN-Zertifikate und die sonstige Konfiguration nach Bedarf über Intune an.

5. Nach Abschluss des Vorgangs kann der Techniker das Intune (Endpunkt-Manager)-Portal laden und unter **Start > Geräte > Gerätename > Hardware** bis zu den Geräteeigenschaften herunter gelangen.

6. Die WLAN-MAC-Adresse wird im Intune-Portal angezeigt.

   ![MAC-Adresse über Intune.](images/mac-address-intune.jpg)

7. Der Techniker fügt diese MAC-Adresse als zulässiges Gerät hinzu.

### <a name="benefits"></a>Vorteile

Dies ermöglicht dem Techniker eine „blinde“ Bereitstellung, bei der das Gerät direkt aus der Verpackung zur Registrierung in Azure AD und Intune gelangt, ohne dass der Techniker das Gerät tragen oder manuell mit der HoloLens-Umgebung interagieren muss.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Meldung von MAC-Adressen an den Techniker

### <a name="requirements"></a>Requirements (Anforderungen)

- Autorisierung der „Intune Graph-PowerShell“ beim Kunden-Mandanten
- Installation der Intune Graph-PowerShell auf dem Computer des Technikers.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Lesezugriff auf die „Verwaltete Geräte“-Elemente von Intune. (Helpdesk-Operator oder höher oder eine benutzerdefinierte Rolle)

Derzeit gibt es keine „einfache“ Möglichkeit, einen Automatisierungsbefehl basierend auf der Registrierung eines neuen Geräts in Intune auszulösen. Daher bietet dieser Befehl dem Techniker eine einfache Möglichkeit, die MAC-Adresse zu erhalten, ohne dass er sich beim Portal anmelden und sie manuell abrufen muss.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Dadurch werden die Namen und MAC-Adressen aller HoloLens-Geräte zurückgegeben, die in den letzten 30 Tagen registriert wurden.

![MAC-Adresse über PowerShell.](images/mac-address-powershell.jpg)

### <a name="process"></a>Prozess

Nach Abschluss der Intune-Registrierung führt der Techniker das obige Skript aus, um die MAC-Adresse abzurufen.
