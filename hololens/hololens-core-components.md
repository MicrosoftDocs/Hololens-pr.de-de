---
title: Planen einer HoloLens 2-Bereitstellung in einer kommerziellen Umgebung
description: Erfahren Sie mehr über die grundlegenden Anforderungen für die Bereitstellung und Verwaltung von HoloLens in Unternehmensumgebungen, einschließlich Infrastruktur, Azure Active Directory und Verwaltung mobiler Geräte.
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
ms.openlocfilehash: 8605d1a889fb9facdab0e9585a43a61880155952
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "123188898"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>Planen einer HoloLens 2-Bereitstellung in einer kommerziellen Umgebung

## <a name="overview"></a>Übersicht

> [!NOTE]
> Diese Übersicht soll IT-Experten dabei helfen, Überlegungen zum Bereitstellen und Verwalten von Microsoft HoloLens 2-Geräten in einer Organisation zu verstehen. Informationen zu Geräteendbenutzern finden Sie unter Vorbereiten ihrer HoloLens 2 für den [Einstieg.](hololens2-setup.md)

HoloLens 2 wird auf Windows 10 Holographic ausgeführt, der Organisationen stabile, flexible, integrierte Technologien für die Verwaltung mobiler Geräte und Apps bietet. Windows 10 Holographic unterstützt die End-to-End-Verwaltung des Gerätelebenszyklus, um Unternehmen die Kontrolle über ihre Geräte, Daten und Apps zu geben. Die HoloLens 2 lassen sich problemlos in Standardlebenszyklusmethoden integrieren, von der Geräteregistrierung, Konfiguration und Anwendungsverwaltung bis hin zu Wartung und Außerbetriebsetzung mithilfe einer umfassenden Lösung für die Verwaltung mobiler Geräte.

Die folgenden Schritte und videos können Sie durch den Prozess der HoloLens 2 Einführung in Ihrer Organisation führen.

| &nbsp; | &nbsp; |
|--|--|
| ![Schritt 1:](images/1green.png)| <br/> **[Allgemeine Bereitstellungsszenarien:](hololens-requirements.md)** Grundlegendes zu Bereitstellungsszenarien und Untersuchen der Kernkomponenten, die zum Bereitstellen HoloLens 2 Geräten erforderlich sind. |
| ![Schritt 2:](images/2green.png)| <br/> **[Vorbereiten:](#prepare)** Machen Sie sich mit den infrastrukturellen Grundlagen vertraut, die für HoloLens 2 erforderlich sind. |
| ![Schritt 3:](images/3green.png) | <br/> **[Konfigurieren:](#configure)** Erfahren Sie, wie Sie Ihre wesentlichen Komponenten für eine cloudbasierte Bereitstellung konfigurieren. |
| ![Schritt 4.](images/4green.png) | <br/> **[Bereitstellen:](#deploy)** Erfahren Sie, wie Sie Ihre Geräte bereitstellen und Ihre Anwendungen sicher und effizient verteilen. |
| ![Schritt 5:](images/5green.png) | <br/> **[Verwalten:](#maintain)** Ermitteln Sie, was erforderlich ist, um den Zustand Ihrer HoloLens 2 Geräte ordnungsgemäß zu verwalten und die Einhaltung der Unternehmensrichtlinie sicherzustellen. |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>Aufbereitung

Erfahren Sie mehr über wichtige Infrastrukturdienste, die erforderlich sind, um den vollständigen Satz von HoloLens 2 Funktionen zu unterstützen.

| Komponente | BESCHREIBUNG |
|-----------|------------|
| [Azure AD](hololens-identity.md) | Stellt die Identitäts- und Zugriffsverwaltung für die HoloLens 2  |
| [Mobile Geräteverwaltung](hololens-mdm-configure.md)| Verwaltet HoloLens 2 Geräte, die mit Ihrem Mandanten verbunden sind.  |
| [WLAN-Netzwerk](hololens-commercial-infrastructure.md)| Wi-Fi verfügbar ist und Geräte mit dem Internet verbunden werden können  |

## <a name="configure"></a>Konfigurieren

Verwenden Sie Intune und Autopilot als Low-Touch-Lösungen zum Registrieren und Konfigurieren von HoloLens 2 für den Azure AD Mandanten und mdm Ihrer Organisation.

| Komponente | BESCHREIBUNG |
|-----------|------------|
| [Automatische Registrierung](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | Nach der ersten Anmeldung registrieren sich Geräte automatisch bei Azure AD und registrieren sich bei MDM.  |
| [Anwendungslizenzen](hololens2-cloud-connected-configure.md#application-licenses)| Kann auf Benutzer, Benutzergruppen oder Gerätegruppen angewendet werden.  |
| [Azure-Benutzer und -Gruppen](hololens2-cloud-connected-configure.md#azure-users-and-groups) | Hilft beim Zuweisen von Konfigurationen und Lizenzen für die HoloLens 2  |

## <a name="deploy"></a>Bereitstellen

Verteilen Sie Ihre HoloLens 2 Geräte, und überprüfen Sie deren Konfiguration. 

| Komponente | BESCHREIBUNG |
|-----------|------------|
| [Überprüfung der Registrierung](hololens2-corp-connected-deploy.md#enrollment-validation) | Vergewissern Sie sich, dass das Gerät über Einstellungen oder das Azure-Portal Azure AD eingebunden wurde. |
| [Zertifikatüberprüfung](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Überprüfen sie die Einstellungen, und überprüfen Sie, ob sie ordnungsgemäß verteilt wurden. |
| [Überprüfen von App-Installationen](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Vergewissern Sie sich, dass die App vorhanden ist und an Ihrem HoloLens 2 |

## <a name="maintain"></a>Verwalten

Verwenden Sie Windows Update for Business zusammen mit Ihrem MDM-System oder der Microsoft Store, um Ihre HoloLens 2 und Apps auf dem neuesten Stand zu halten.

| Komponente | BESCHREIBUNG |
|-----------|------------|
| [Aktualisieren HoloLens 2](hololens-updates.md) | Konfigurieren von Updates nach Bedarf über Windows Updates for Business |
| [Aktualisieren von Apps](app-deploy-overview.md) | Konfigurieren über Ihr MDM-System oder die Microsoft Store
