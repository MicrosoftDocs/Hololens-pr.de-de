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
ms.openlocfilehash: a577eace62040e2d48de5d3e4cc99ef108bd006c
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407620"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Enterprise-Registrierung von HoloLens-Geräten in einer auf MAC-Adressen beschränkten WLAN-Umgebung

In diesem Dokument wird ein gängiges Szenario beschrieben, das in Kundenumgebungen festgelegt wurde, in denen das WLAN-System durch MAC-Adressen eingeschränkt wird, oder Zertifikate für die Teilnahme an drahtlosen Netzwerken erforderlich sind.

## <a name="example-scenario"></a>Beispielszenario

Viele Kunden in sicheren Umgebungen haben Einschränkungen für ihre Drahtlos- oder Kabelnetzwerke, die nur genehmigten Geräten (basierend auf MAC-Adressen) erlauben, eine erfolgreiche Verbindung herzustellen. Dies kann durch MAC-Adressfilterung auf einem drahtlosen Zugriffspunkt oder über einen DHCP-Server erzwungen werden. Darüber hinaus können einige drahtlose Netzwerke mit PEAP geschützt werden. Daher muss vor der Authentifizierung im drahtlosen Netzwerk ein Zertifikat auf das Gerät angewendet werden.

In diesem Szenario können zwei Hauptanforderungen zu Verzögerungen führen oder manuelle Eingriffe erfordern, wenn HoloLens-Geräte mit dem Netzwerk verbunden werden:

- Das drahtlose PEAP-Zertifikat muss auf das Gerät angewendet werden, bevor das Gerät erfolgreich mit dem drahtlosen Netzwerk verbunden wird.
- Die MAC-Adresse des HoloLens-WLAN-Adapters muss registriert werden.

Die Kernherausforderungen mit den oben genannten Anforderungen sind:

1. Die MAC-Adresse kann derzeit nur über die Einstellungen-App auf dem Gerät oder über Intune nach erfolgreicher Registrierung identifiziert werden.

2. Ohne die MAC-Adresse kann das Gerät nicht mit dem WLAN-Netzwerk verbunden werden, um die Registrierung zu starten.

3. Manuelle Problemumgehungen für diese Herausforderungen erfordern, dass ein Techniker mit dem Gerät interagiert.

## <a name="solutions"></a>Lösungen

Es gibt viele Möglichkeiten, diese Situation zu verbessern, abhängig von der in der Umgebung verfügbaren Infrastruktur.

| Lösung | Vorteile | Anforderungen |
| --- | --- | --- |
| Bereitstellungspaket mit Ethernet-Adapter | Verbessert die OOBE und ermöglicht eine schnellere Techniker-Erfahrung. | HoloLens kompatibler USB-C-Hub + Ethernet-Adapter, und Techniker müssen weiterhin für die MAC-Erfassung und die OOBE-Fertigstellung mit dem Gerät interagieren. |
| Autopilot mit Intune-Registrierung über Ethernet | Dies ist eine Ein-Schritt-Verbindung und -Registrierung des Geräts in der Kundenumgebung. Die MAC-Erfassung kann abgeschlossen werden, ohne dass eine Interaktion mit dem Gerät erforderlich ist | Intune aktiviert für den AAD-Mandanten des Kunden und einen HoloLens-kompatiblen USB-C-Ethernet-Adapter |
| Automatisierte Berichterstattung von MAC-Adressen | Wenn Geräte beim Intune-Mandanten registriert sind, kann ein Skript die MAC-Adresse dem Techniker melden. | Intune PowerShell-Cmdlets |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Bereitstellungspaket mit Ethernet-Adapter

> [!NOTE] 
> Wenn für das kabelgebundene Netzwerk auch MAC-Einschränkungen gelten, muss auch die MAC-Adresse des USB-C Hub + Ethernet-Adapters vorab genehmigt werden. Bei diesem Adapter ist Vorsicht geboten, da er den Zugriff auf das Netzwerk von anderen Geräten aus ermöglicht.

### <a name="requirements"></a>Anforderungen

- Verkabelter Netzwerk-Port mit Zugriff auf das Kundennetzwerk
- HoloLens Kompatibler USB-C-Hub mit Ethernet-Adapter – Jeder Adapter, für den keine zusätzlichen Treiber oder Anwendungsinstallationen erforderlich sind, sollte geeignet sein.
- Bereitstellungspaket enthält:
  - Beinhaltet Drahtlosnetzwerk-Informationen und -Zertifikat
  - Beinhaltet optional Registrierungsinformationen für Azure AD der Organisation
  - Beinhaltet alle anderen erforderlichen Bereitstellungseinstellungen

### <a name="process"></a>Process

Der Vorgang kann je nach Softwareebene des Geräts variieren. Wenn auf dem Gerät das [Mai 2004 Update](hololens-release-notes.md#windows-holographic-version-2004) vorhanden ist, führen Sie die folgenden Schritte aus.

1. Platzieren Sie das Bereitstellungspaket auf dem Stamm eines USB-Sticks und schließen Sie es an den Hub an.
2. Schließen Sie das Ethernet-Kabel an den Hub + Ethernet-Adapter an.
3. Schließen Sie den USB-C-Hub an das HoloLens-Gerät an.
4. Schalten Sie die HoloLens ein und setzen Sie das Gerät auf.
5. Drücken Sie die **Lautstärke-nach-unten-Taste**, um das Bereitstellungspaket anzuwenden.
6. Der Techniker kann nun OOBE folgen und nach Abschluss die Einstellungen-App öffnen, um die MAC-Adresse des Geräts abzurufen.

Wenn auf dem Gerät ein Betriebssystem-Build vor dem [Mai 2004 Update](hololens-release-notes.md#windows-holographic-version-2004) vorhanden ist, führen Sie die folgenden Schritte aus.

1. Schalten Sie die HoloLens ein und schließen Sie das Gerät an einen PC an.
2. Das Gerät sollte auf dem PC als Datei-Speichervorrichtung angezeigt werden.
3. Kopieren Sie das Bereitstellungspaket auf dem Gerät
4. Verbinden Sie das Ethernet-Kabel mit dem Hub.
5. Schließen Sie den USB-C-Hub an das HoloLens-Gerät an.
6. Setzen Sie die HoloLens auf
7. Drücken Sie die **Lautstärke-nach-unten-Taste**, um das Bereitstellungspaket anzuwenden.
8. Der Techniker kann nun OOBE folgen und nach Abschluss die Einstellungen-App öffnen, um die MAC-Adresse des Geräts abzurufen.

### <a name="benefits"></a>Vorteile

Dadurch wird eine „Einzeltoucheingabe“ des Geräts ermöglicht, um das richtige Bereitstellungspaket anzuwenden und die MAC-Adresse des Geräts zu erfassen. [Bereitstellungspakete können entsprechend der hier aufgeführten Anleitung erstellt werden.](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a>Autopilot mit Intune-Registrierung

### <a name="requirements"></a>Anforderungen

- Verkabelter Netzwerk-Port mit Zugriff auf das Kundennetzwerk
- HoloLens-Geräte unter Windows holographisch 2004
- HoloLens-kompatibler USB-C-Ethernet-Adapter
- Intune eingerichtet und für den Kundenmandanten aktiviert
- Für Autopilot registriertes und in den Kundenmandanten importiertes Gerät
- Für das Gerät definierte Intune-Richtlinien:
   - Informationen zum drahtlosen Netzwerk und Zertifikat
   - Alle anderen erforderlichen Bereitstellungseinstellungen

Auf diese Weise kann ein Kunde mit fortgeschrittenen Netzwerkanforderungen die Geräte in einem praktischen, skalierbaren Ansatz registrieren.

Weitere Voraussetzungen sind wie unten aufgeführt erforderlich:
1. [Aktivieren Sie den Mandanten für die Autopilot-Vorschau](https://docs.microsoft.com/hololens/hololens2-autopilot).
1. Erstellen Sie die HoloLens-Richtlinien, um das Bereitstellungspaket in Intune zu ersetzen.
1. Erstellen der HoloLens-Intune-Richtlinien.
1. Zuordnen der Geräte zur richtigen Gruppe.

### <a name="process"></a>Verfahren

1. Schließen Sie das Ethernet-Kabel an den Adapter an und stecken Sie den Adapter in den USB-C-Anschluss des HoloLens 2-Geräts.

2. Schalten Sie die HoloLens ein.

3. Das Gerät sollte während der OOBE über den Ethernet-Adapter automatisch eine Verbindung zum Internet herstellen. Es sollte die Autopilot-Konfiguration erkennen und sich automatisch bei Azure AD und Intune registrieren.

4. Das Gerät wird die erforderlichen WLAN-Zertifikate und andere Konfigurationen nach Bedarf über Intune anwenden.

5. Nach Abschluss des Vorgangs kann der Techniker das Intune (Endpoint Manager)-Portal laden und auf die Seite der Geräteeigenschaften heruntergehen unter **Startseite -> Geräte -> Gerätename -> Hardware**.

6. Die WLAN-MAC-Adresse wird im Intune-Portal angezeigt.

   ![MAC-Adresse über Intune](images/mac-address-intune.jpg)

7. Der Techniker wird diese MAC-Adresse als zulässiges Gerät hinzufügen.

### <a name="benefits"></a>Vorteile

Dies ermöglicht dem Techniker eine „Heads off“-Bereitstellung, bei der das Gerät aus der Schachtel zur Registrierung in Azure AD und Intune wechseln kann, ohne dass der Techniker das Gerät bewegen oder manuell mit der HoloLens-Umgebung interagieren muss.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Berichterstattung von MAC-Adressen an den Techniker

### <a name="requirements"></a>Anforderungen

- Autorisierung der „Intune Graph PowerShell“ gegen den Kunden-Mandanten
- Installation der Intune Graph-PowerShell auf dem Computer des Technikers.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Lesezugriff auf die Elemente „Verwaltete Geräte“ von Intune. (Helpdesk-Operator oder höher, oder eine benutzerdefinierte Rolle)

Derzeit gibt es keine „einfache“ Möglichkeit, einen Automatisierungsbefehl basierend auf der Registrierung eines neuen Geräts in Intune auszulösen. Daher bietet dieser Befehl dem Techniker eine einfache Möglichkeit, die MAC-Adresse abzurufen, ohne dass er sich am Portal anmelden und sie manuell abrufen muss.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Dies wird die Namen und MAC-Adressen aller HoloLens-Geräte zurückgegeben, die in den letzten 30 Tagen registriert wurden.

![MAC-Adresse über PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a>Verfahren

Nach Abschluss der Intune-Registrierung würde der Techniker das obige Skript ausführen, um die MAC-Adresse abzurufen.
