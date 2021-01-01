---
title: Kommerzielle Funktionen
description: Die Microsoft HoloLens Commercial Suite umfasst Features, die es für Unternehmen einfacher machen, HoloLens-Geräte zu verwalten. HoloLens 2-Geräte sind standardmäßig mit kommerziellen Funktionen ausgestattet.
keywords: HoloLens, kommerziell, Features, MDM, Verwaltung mobiler Geräte, Kioskmodus
author: scooley
ms.author: scooley
ms.date: 08/26/2019
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 51d50f863e379baffee4e44c44e3ab467b517359
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253172"
---
# Kommerzielle Funktionen

HoloLens enthält Features, die es für Unternehmen einfacher machen, HoloLens-Geräte zu verwalten.

Für jedes HoloLens 2-Gerät stehen kommerzielle Funktionen zur Verfügung.

HoloLens (1. Generation) hat zwei Lizenzierungsoptionen, die Entwicklerlizenz und eine kommerzielle Lizenz. Um die kommerziellen Funktionen von HoloLens zu entsperren, führen Sie ein Upgrade von der Entwicklerlizenz auf eine kommerzielle Lizenz durch. Wenn Sie die Microsoft HoloLens Commercial Suite erwerben möchten, wenden Sie sich an Ihren lokalen Microsoft-Konto-Manager.

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## Wichtige kommerzielle Funktionen

- **Kioskmodus.** Sie können HoloLens in Demo-oder Showcase-Umgebungen mithilfe des Kioskmodus verwenden, um zu begrenzen, welche Apps ausgeführt werden können.

  ![Mit dem Kioskmodus startet HoloLens direkt in die App Ihrer Wahl.](images/201608-kioskmode-400px.png)

- **Geräteverwaltung für Mobilgeräte (MDM, Mobile Device Management) für HoloLens.** Ihre IT-Abteilung kann mehrere HoloLens-Geräte gleichzeitig mithilfe von Lösungen wie Microsoft InTune verwalten. Sie können Einstellungen verwalten, zu installierende Apps auswählen und Sicherheitskonfigurationen einrichten, die auf die Anforderungen Ihrer Organisation zugeschnitten sind.

  ![Die Verwaltung mobiler Geräte auf HoloLens bietet unternehmensweite Geräteverwaltung auf mehreren Geräten.](images/201608-enterprisemanagement-400px.png)

- **Windows Update for Business.** Windows Update for Business bietet kontrollierte Betriebssystemaktualisierungen für Geräte und Unterstützung für den langfristigen Servicing Channel.
- **Datensicherheit.** Die BitLocker-Datenverschlüsselung ist auf HoloLens aktiviert, um dasselbe Maß an Sicherheitsschutz wie jedes andere Windows-Gerät bereitzustellen.
- **Arbeitsplatzzugriff.** Jeder in Ihrer Organisation kann über ein virtuelles privates Netzwerk (VPN) auf einer HoloLens eine Remoteverbindung mit dem Unternehmensnetzwerk herstellen. HoloLens kann auch auf WLAN-Netzwerke zugreifen, für die Anmeldeinformationen erforderlich sind.
- **Microsoft Store für Unternehmen.** Ihre IT-Abteilung kann auch einen privaten Unternehmensspeicher einrichten, in dem nur die Apps Ihres Unternehmens für Ihre spezifische HoloLens-Nutzung enthalten sind. Verteilen Sie Ihre Unternehmenssoftware auf sichere Weise an ausgewählte Gruppen von Unternehmensbenutzern.

## Funktionsvergleich zwischen Editionen

|Features |HoloLens Development Edition |HoloLens Commercial Suite |HoloLens 2 |
|---|:---:|:---:|:---:|
|Geräteverschlüsselung (BitLocker) | |✔️ |✔️ |
|Virtuelles privates Netzwerk (VPN) | |✔️ |✔️ |
|[Kioskmodus](hololens-kiosk.md) | |✔️ |✔️ |
|**Verwaltung und Bereitstellung** | | | |
|Mobile Geräteverwaltung (MDM) | |✔️ |✔️ |
|Möglichkeit zum Blockieren der Abmeldung | |✔️ |✔️ |
|CERT-basierter Corporate WLAN-Zugriff | |✔️ |✔️ |
|Microsoft Store (Verbraucher) |Verbraucher |Filtern mithilfe der Geräteverwaltung |Filtern mithilfe der Geräteverwaltung |
|[Business Store-Portal](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**Sicherheit und Identität** | | | |
|Anmelden mit Azure Active Directory-Konto (Azure AD) |✔️ |✔️ |✔️ |
|Anmelden mit Microsoft-Konto (MSA) |✔️ |✔️ |✔️ |
|Anmeldeinformationen der nächsten Generation mit PIN-Entsperrung |✔️ |✔️ |✔️ |
|[Sicheres Starten](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**Wartung und Support** | | | |
|Automatische Systemaktualisierungen, sobald sie eintreffen |✔️ |✔️ |✔️ |
|[Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|Long-Term Servicing Channel (LTSC) | |✔️ |✔️ |

## Aktivieren von kommerziellen Features

Der IT-Administrator Ihrer Organisation kann kommerzielle Features wie Microsoft Store für Unternehmen, Kioskmodus und Enterprise-WLAN-Zugriff einrichten. In der [Microsoft HoloLens](index.yml)-Dokumentation finden Sie schrittweise Anleitungen zum Registrieren von Geräten und zum Installieren von Apps aus dem Microsoft Store für Unternehmen.

## Weitere Informationen

- [Microsoft HoloLens](index.yml)
- [Kioskmodus](hololens-kiosk.md)
- [In HoloLens-Geräten unterstützte CSPs (Kryptografiedienstanbieter)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [Microsoft Store für Unternehmen und Branchenanwendungen](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [Arbeiten mit Branchenanwendungen](/microsoft-store/working-with-line-of-business-apps)
