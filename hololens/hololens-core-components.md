---
title: Planen einer HoloLens 2-Bereitstellung in einer kommerziellen Umgebung
description: Erfahren Sie mehr über die Hauptanforderungen für die Bereitstellung und Verwaltung von HoloLens in Unternehmensumgebungen, einschließlich Infrastruktur, Azure Active Directory und Verwaltung mobiler Geräte.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 2fb58345f623a0b70c1fda10b9fb550de70f4c6d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635788"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>Planen einer HoloLens 2-Bereitstellung in einer kommerziellen Umgebung

## <a name="overview"></a>Überblick
> [!NOTE]
> Diese Übersicht soll IT-Experten dabei helfen, Überlegungen zur Bereitstellung und Verwaltung von Microsoft HoloLens 2-Geräten innerhalb einer Organisation zu verstehen. Informationen für Geräteendbenutzer finden Sie unter [HoloLens 2 für den Einstieg.](hololens2-setup.md)

HoloLens 2 auf einem Windows 10 Holographic, das Organisationen stabile, flexible, integrierte Technologien für die Verwaltung mobiler Geräte und Apps bietet. Windows 10 Holographic unterstützt die End-to-End-Verwaltung des Gerätelebenszyklus, um Unternehmen die Kontrolle über ihre Geräte, Daten und Apps zu geben. Die HoloLens 2 können mithilfe einer umfassenden Lösung für die Verwaltung mobiler Geräte problemlos in Standardmethoden für den Lebenszyklus integriert werden– von der Geräteregistrierung, Konfiguration und Anwendungsverwaltung bis zur Wartung und Ablösung.

Die folgenden Schritte und das Video helfen Ihnen bei der Einführung HoloLens 2 in Ihrer Organisation.

| | |
|--|--|
| ![Schritt 1](images/1green.png)| <br/> **[Allgemeine Bereitstellungsszenarien:](hololens-requirements.md)** Machen Sie sich mit Bereitstellungsszenarien und den Kernkomponenten für die Bereitstellung HoloLens 2 geräte. |
| ![Schritt 2](images/2green.png)| <br/> **[Vorbereiten:](#prepare)** Machen Sie sich mit den Infrastruktur-Essentials vertraut, die für die HoloLens 2. |
| ![Schritt 3](images/3green.png) | <br/> **[Konfigurieren:](#configure)** Erfahren Sie, wie Sie Ihre wesentlichen Komponenten für eine cloudbasierte Bereitstellung konfigurieren. |
| ![Schritt 4](images/4green.png) | <br/> **[Bereitstellen:](#deploy)** Erfahren Sie, wie Sie Ihre Geräte bereitstellen und Ihre Anwendungen sicher und effizient verteilen. |
| ![Schritt 5](images/5green.png) | <br/> **[Verwalten:](#maintain)** Finden Sie heraus, was erforderlich ist, um den Zustand Ihrer HoloLens 2 ordnungsgemäß zu verwalten und die Einhaltung der Unternehmensrichtlinie sicherzustellen. |

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>Vorbereiten

Erfahren Sie mehr über wichtige Infrastrukturdienste, die erforderlich sind, um den vollständigen Satz von HoloLens 2 unterstützen. 

| Komponente | Beschreibung |
|-----------|------------|
| [Azure AD](hololens-identity.md) | Bietet Identitäts- und Zugriffsverwaltung für die HoloLens 2  |
| [Mobile Geräteverwaltung](hololens-mdm-configure.md)| Verwaltet HoloLens 2 Mit Ihrem Mandanten verbundenen Geräte  |
| [WLAN-Netzwerk](hololens-commercial-infrastructure.md)| Wi-Fi ist verfügbar, und Geräte können mit dem Internet verbunden werden.  |

## <a name="configure"></a>Konfigurieren

Verwenden Sie Intune und Autopilot als Low-Touch-Lösungen zum Registrieren und Konfigurieren von HoloLens 2 für den Azure AD mandanten und MDM Ihrer Organisation.

| Komponente | Beschreibung |
|-----------|------------|
| [Automatische Registrierung](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | Nach der ersten Anmeldung registrieren sich Geräte automatisch bei Azure AD und registrieren sich bei MDM.  |
| [Anwendungslizenzen](hololens2-cloud-connected-configure.md#application-licenses)| Kann entweder auf Benutzer, Benutzergruppen oder Gerätegruppen angewendet werden.  |
| [Azure-Benutzer und -Gruppen](hololens2-cloud-connected-configure.md#azure-users-and-groups) | Hilft beim Zuweisen von Konfigurationen und Lizenzen für HoloLens 2  |

## <a name="deploy"></a>Bereitstellen

Verteilen Sie Ihre HoloLens 2 Geräte, und überprüfen Sie deren Konfiguration. 

| Komponente | Beschreibung |
|-----------|------------|
| [Registrierungsüberprüfung](hololens2-corp-connected-deploy.md#enrollment-validation) | Überprüfen, ob das Gerät über Azure AD oder das Azure-Portal Einstellungen wurde |
| [Zertifikatüberprüfung](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Überprüfen Sie die Einstellungen, und überprüfen Sie, ob sie ordnungsgemäß verteilt wurden. |
| [Überprüfen von App-Installationen](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Vergewissern Sie sich, dass die App vorhanden ist und an Ihrem HoloLens 2 |

## <a name="maintain"></a>Verwalten

Verwenden Windows Update for Business zusammen mit Ihrem MDM-System oder dem Microsoft Store, um Ihre HoloLens 2 und Apps auf dem neuesten Stand zu halten.

| Komponente | Beschreibung |
|-----------|------------|
| [Update HoloLens 2](hololens-updates.md) | Konfigurieren Von Updates nach Bedarf über Windows Updates for Business |
| [Aktualisieren von Apps](app-deploy-overview.md) | Konfigurieren sie über Ihr MDM-System oder Microsoft Store
