---
title: Kommerzielle Features
description: Hier erfahren Sie mehr über Microsoft HoloLens Commercial Suite-Funktionen, die es für Unternehmen einfacher machen, HoloLens-Geräte zu verwalten.
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
keywords: HoloLens, kommerziell, Funktionen, MDM, Verwaltung mobiler Geräte, Kioskmodus
ms.openlocfilehash: 3682a2633477d68f61dba8a674846857947a3d15
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397861"
---
# <a name="commercial-features"></a>Kommerzielle Features

HoloLens enthält Funktionen, die es für Unternehmen einfacher machen, HoloLens-Geräte zu verwalten.

Für jedes HoloLens 2-Gerät stehen kommerzielle Funktionen zur Verfügung.

HoloLens (1. Generation) hat zwei Lizenzierungsoptionen, die Entwicklerlizenz und eine kommerzielle Lizenz. Um die kommerziellen Funktionen von HoloLens zu entsperren, führen Sie ein Upgrade von der Entwicklerlizenz auf eine kommerzielle Lizenz durch. Wenn Sie die Microsoft HoloLens Commercial Suite erwerben möchten, wenden Sie sich an Ihren lokalen Microsoft-Konto-Manager.

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## <a name="key-commercial-features"></a>Wichtige kommerzielle Funktionen

- **Kioskmodus** Sie können HoloLens in Demo-oder Showcase-Umgebungen mithilfe des Kioskmodus verwenden, um zu begrenzen, welche Apps ausgeführt werden können.

  ![Mit dem Kioskmodus startet HoloLens direkt in die App Ihrer Wahl.](images/201608-kioskmode-400px.png)

- **Verwaltung mobiler Geräte (MDM, Mobile Device Management) für HoloLens.** Ihre IT-Abteilung kann mehrere HoloLens-Geräte gleichzeitig mithilfe von Lösungen wie Microsoft Intune verwalten. Sie können Einstellungen verwalten, zu installierende Apps auswählen und Sicherheitskonfigurationen einrichten, die auf die Anforderungen Ihrer Organisation zugeschnitten sind.

  ![Die Verwaltung mobiler Geräte auf HoloLens bietet unternehmensweite Geräteverwaltung auf mehreren Geräten.](images/201608-enterprisemanagement-400px.png)

- **Windows Update für Unternehmen.** Windows Update für Unternehmen bietet kontrollierte Betriebssystemaktualisierungen für Geräte und Unterstützung für den langfristigen Servicing Channel.
- **Datensicherheit**. Die BitLocker-Datenverschlüsselung ist auf HoloLens aktiviert, um dasselbe Maß an Sicherheitsschutz wie jedes andere Windows-Gerät bereitzustellen.
- **Arbeitsplatzzugriff.** Jeder in Ihrem Unternehmen kann über ein virtuelles privates Netzwerk (VPN) auf einer HoloLens eine Remoteverbindung mit dem Unternehmensnetzwerk herstellen. HoloLens kann auch auf WLAN-Netzwerke zugreifen, die Anmeldeinformationen erfordern.
- **Microsoft Store für Unternehmen.** Ihre IT-Abteilung kann auch einen privaten Unternehmensspeicher einrichten, in dem nur die Apps Ihres Unternehmens für Ihre spezifische HoloLens-Nutzung enthalten sind. Verteilen Sie Ihre Unternehmenssoftware auf sichere Weise an ausgewählte Gruppen von Unternehmensbenutzern.

## <a name="feature-comparison-between-editions"></a>Funktionsvergleich zwischen den Editionen

|Features |HoloLens (1. Generation) Development Edition |HoloLens (1. Generation) Commercial Suite |HoloLens 2 |
|---|:---:|:---:|:---:|
|Geräteverschlüsselung (BitLocker) | |✔️ |✔️ |
|Virtuelles privates Netzwerk (VPN): | |✔️ |✔️ |
|[Kioskmodus](hololens-kiosk.md) | |✔️ |✔️ |
|**Verwaltung und Bereitstellung** | | | |
|Mobile Geräteverwaltung (MDM) | |✔️ |✔️ |
|Möglichkeit zum Blockieren der Registrierungsaufhebung | |✔️ |✔️ |
|CERT-basierter Corporate WLAN-Zugriff | |✔️ |✔️ |
|Microsoft Store (Verbraucher) |Consumer |Filtern mithilfe der MDM |Filtern mithilfe der MDM |
|[Business Store-Portal](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**Sicherheit und Identität** | | | |
|Anmelden mit dem Azure Active Directory-Konto (Azure AD) |✔️ |✔️ |✔️ |
|Anmelden mit dem Microsoft-Konto (MSA) |✔️ |✔️ |✔️ |
|Anmeldeinformationen der nächsten Generation mit PIN-Entsperrung |✔️ |✔️ |✔️ |
|[Sicherer Start](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**Wartung und Support** | | | |
|Automatische Systemaktualisierungen, sobald sie eintreffen |✔️ |✔️ |✔️ |
|[Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|Long-Term Servicing Channel (LTSC) | |✔️ |✔️ |

## <a name="enabling-commercial-features"></a>Aktivieren von kommerziellen Funktionen

Der IT-Administrator Ihres Unternehmens kann kommerzielle Funktionen wie Microsoft Store für Unternehmen, Kioskmodus und Enterprise-WLAN-Zugriff einrichten. In der [Microsoft HoloLens](index.yml) Dokumentation finden Sie schrittweise Anleitungen zum Registrieren von Geräten und zum Installieren von Apps aus dem Microsoft Store für Unternehmen.

## <a name="see-also"></a>Siehe auch

- [Microsoft HoloLens](index.yml)
- [Kioskmodus](hololens-kiosk.md)
- [In HoloLens-Geräten unterstützte CSPs](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [Microsoft Store für Unternehmen und Branchenanwendungen](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [Arbeiten mit Branchen-Apps](/microsoft-store/working-with-line-of-business-apps)
