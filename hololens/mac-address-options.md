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
ms.openlocfilehash: fe365248332f8e78b15ab362f169b84e48dfe594
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393839"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Enterprise-Registrierung von HoloLens-Geräten in einer auf MAC-Adressen beschränkten WLAN-Umgebung

In diesem Dokument wird ein gängiges Szenario beschrieben, das in Kundenumgebungen festgelegt wurde, in denen das WLAN-System durch MAC-Adressen eingeschränkt wird, oder Zertifikate für die Teilnahme an drahtlosen Netzwerken erforderlich sind.

## <a name="example-scenario"></a>Beispielszenario

Viele Kunden in sicheren Umgebungen haben Einschränkungen in ihren drahtlosen oder kabelgebundenen Netzwerken, sodass nur zugelassene Geräte (basierend auf MAC-Adressen) eine erfolgreiche Verbindung herstellen können. Dies kann durch MAC-Adressfilterung auf einem Wireless Access Point oder über einen DHCP-Server erzwungen werden. Darüber hinaus können einige drahtlose Netzwerke mit PEAP geschützt werden. Daher muss vor der Authentifizierung im drahtlosen Netzwerk ein Zertifikat auf das Gerät angewendet werden.

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
| Bereitstellungspaket mit Ethernet-Adapter | Verbessert die OOBE-Erfahrung und ermöglicht eine schnellere Techniker-Erfahrung. | Der HoloLens-kompatible USB-C Hub + Ethernet-Adapter und der Techniker müssen weiterhin mit dem Gerät interagieren, um die MAC-Erfassung und die OOBE-Finalisierung durchzuführen |
| Autopilot mit Intune-Registrierung über Ethernet | Dies ist eine einstufige Verbindung und Registrierung des Geräts in der Kundenumgebung. Die MAC-Erfassung kann abgeschlossen werden, ohne dass eine Interaktion mit dem Gerät erforderlich ist | Intune aktiviert für den AAD-Mandanten des Kunden und einen HoloLens-kompatiblen USB-C-Ethernet-Adapter |
| Automatisierte Berichterstattung von MAC-Adressen | Wenn Geräte beim Intune-Mandanten registriert sind, kann ein Skript die MAC-Adresse dem Techniker melden. | Intune PowerShell-Commandlets |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Bereitstellungspaket mit Ethernet-Adapter

> [!NOTE] 
> Wenn für das kabelgebundene Netzwerk auch MAC-Einschränkungen gelten, muss auch die MAC-Adresse des USB-C Hub + Ethernet-Adapters vorab genehmigt werden. Bei diesem Adapter ist Vorsicht geboten, da er den Zugriff auf das Netzwerk von anderen Geräten aus ermöglicht.

### <a name="requirements"></a>Anforderungen

- Verkabelter Netzwerk-Port mit Zugriff auf das Kundennetzwerk
- HoloLens-kompatibler USB-C-Hub mit Ethernet-Adapter – Jeder Adapter, für den keine zusätzlicher Treiber oder Anwendungsinstallationen erforderlich sind, sollte geeignet sein.
- Bereitstellungspaket enthält:
  - Informationen zum drahtlosen Netzwerk und Zertifikat
  - Informationen zur Registrierung für Azure AD der Organisation&#39;s (optional)
  - Alle anderen erforderlichen Bereitstellungseinstellungen

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

Auf diese Weise kann mit einer &quot;einzigen Berührung&quot; des Geräts das korrekte Bereitstellungspaket angewendet und die MAC-Adresse des Geräts erfasst werden. [Bereitstellungspakete können entsprechend der hier aufgeführten Anleitung erstellt werden.](https://docs.microsoft.com/hololens/hololens-provisioning)

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
1. [Aktivieren des Mandanten für die Autopilot-Vorschau](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. Erstellen der HoloLens-Richtlinien, um das Bereitstellungspaket in Intune zu ersetzen.
1. Erstellen der HoloLens-Intune-Richtlinien.
1. Zuordnen der Geräte zur richtigen Gruppe.

### <a name="process"></a>Verfahren

1. Schließen Sie das Ethernet-Kabel an den Adapter an und stecken Sie den Adapter in den USB-C-Anschluss des HoloLens 2-Geräts.
2. Schalten Sie die HoloLens ein.
3. Das Gerät sollte während der OOBE über den Ethernet-Adapter automatisch eine Verbindung zum Internet herstellen. Es sollte die Autopilot-Konfiguration erkennen und sich automatisch bei Azure AD und Intune registrieren
4. Das Gerät wendet die erforderlichen WLAN-Zertifikate und andere Konfigurationen nach Bedarf über Intune an
5. Nach Fertigstellung kann der Techniker das Intune (Endpunkt-Manager)-Portal laden und die Seite "Geräteeigenschaften" unter **Start -> Geräte -> Gerätename -> Hardware** aufrufen
6. Die WLAN-MAC-Adresse wird im Intune-Portal angezeigt

![MAC-Adresse über Intune](images/mac-address-intune.jpg)

7. Der Techniker wird diese MAC-Adresse als zulässiges Gerät hinzufügen.

### <a name="benefits"></a>Vorteile

Dies ermöglicht dem Techniker eine &quot;"Heads off"&quot;-Bereitstellungserfahrung, bei der das Gerät von der Box zum Azure AD und Intune übergehen kann, ohne dass der Techniker das Gerät tragen oder manuell mit der HoloLens-Umgebung interagieren muss.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Berichterstattung von MAC-Adressen an den Techniker

### <a name="requirements"></a>Anforderungen

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

### <a name="process"></a>Process

Nachdem die Intune-Registrierung abgeschlossen ist, wird der Techniker das obige Skript ausführen, um die MAC-Adresse abzurufen.
