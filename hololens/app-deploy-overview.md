---
title: 'Übersicht : App-Verwaltung'
description: Beginnen Sie mit einer Übersicht über die Mixed Reality-App-Verwaltung mit der Verwaltung mobiler Geräte, microsoft store for business und Bereitstellungspaketen.
keywords: HoloLens, Benutzer, Konto, App, Anwendungsverwaltung,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032485"
---
# <a name="app-management-overview"></a>App-Verwaltung: Übersicht

Sie können Apps auf vier verschiedenen Pfaden bereitstellen: **Mobile Geräteverwaltung (MDM),** **Microsoft Store für Unternehmen**, **Microsoft Store** oder durch Installation über **die Bereitstellung.**

## <a name="mobile-device-management-mdm"></a>Mobile Geräteverwaltung (MDM)

Eine MDM-Lösung ermöglicht IT-Entscheidungsträgern und Administratoren die private automatische Installation (Push) ihrer unternehmensinternen, branchenbezogenen Apps oder den Kauf von Apps über den Store für eine Gruppe von Benutzern. HoloLens Geräte funktionieren am besten mit Microsoft Endpoint Manager (Intune) für die [Anwendungsverwaltung.](app-deploy-intune.md) Intune bietet Benutzern auch eine differenziertere Kontrolle über IT-verwaltete Apps über die Unternehmensportal herunterladbare Benutzeroberfläche.

> [!NOTE]
> Die folgenden Anweisungen gelten für Benutzer, die ihre Anwendungen mit Intune verwalten möchten. Microsoft empfiehlt die Verwendung von Intune für die Anwendungs- und Geräteverwaltung.

Mobile Geräteverwaltung (MDM) gilt für:

* MDM bereitgestellt + Unternehmensportal
* Branchenspezifische (nicht öffentliche) Apps
* Manuelle Installation verfügbarer Anwendungen über Unternehmensportal
* Administrator pusht MDM-Richtlinie
* Automatisches Update über MDM

## <a name="microsoft-store-for-business"></a>Microsoft Store für Unternehmen

Die [Microsoft Store für Unternehmen](app-deploy-store-business.md) bietet IT-Entscheidungsträgern und Administratoren in Unternehmen die Möglichkeit, kostenlose und kostenpflichtige Apps zu finden, zu erwerben, zu verwalten und zu verteilen. IT-Administratoren können Microsoft Store-Apps und private Branchen-Apps in einem Bestand verwalten sowie Lizenzen nach Bedarf zuweisen und wiederverwenden. Weitere Informationen finden Sie unter [Voraussetzungen für die Verwendung des Microsoft Store für Unternehmen](/microsoft-store/prerequisites-microsoft-store-for-business).

Die Microsoft Store für Unternehmen gilt für:

* Öffentliche oder Branchen-Apps
* Automatische Installation erforderlicher Anwendungen über MDM-Zuordnung
* Benutzer lädt Apps manuell herunter
* Automatische Aktualisierung

## <a name="microsoft-store-apps"></a>Microsoft Store-Apps

Die Microsoft Store bietet IT-Entscheidungsträgern und Administratoren in Unternehmen die Möglichkeit, öffentliche Apps zu finden, zu erwerben, zu verwalten und zu verteilen.

Diese Microsoft Store gilt für:

* Nur öffentliche Apps
* Benutzer lädt Apps manuell herunter
* Automatisches Update, wenn eine Verbindung mit dem Internet besteht

Weitere Informationen finden Sie unter [Holographic Store Apps](/hololens/holographic-store-apps).

## <a name="install-via-provisioning-packages"></a>Installieren über Bereitstellungspakete

[Mit Bereitstellungspaketen](app-deploy-provisioning-package.md) können Sie benutzerdefinierte oder branchenspezifische Apps installieren, sodass IT-Spezialisten und Administratoren Apps schnell über USB auf einem lokalen Gerät installieren können. Diese Installation kann ohne Internetverbindung und für jeden Identitätstyp erfolgen.

Die Installation über Bereitstellungspakete gilt für:

* Branchenspezifische/selbst entwickelte (nicht öffentliche) Apps
* Öffentliche Apps (wenn ein Offlineinstaller verfügbar ist)
* Nur USB-Querladen
* Kein automatisches Update (erfordert manuelle Updates über das Bereitstellungspaket)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>Installieren von Apps auf HoloLens 2 über App-Installer

Mithilfe der [App-Installer](app-deploy-app-installer.md) können Benutzer über eine einfache Benutzeroberfläche verfügen, um Apps auf lokalen Geräten zu installieren oder eine App für eine andere Person zu teilen, die mit anderen App-Installationsmethoden auf HoloLens nicht vertraut ist. Dies kann erfolgen, ohne den Entwicklermodus aktivieren oder Geräteportal verwenden zu müssen. Dies ist eine einfache Methode zum Verteilen einer vollständig erstellten App. Unabhängig davon, ob Sie Ihre App einfach einem anderen Benutzer mit einem HoloLens vordemonst oder Ihre App bereitstellen möchten, funktioniert diese Methode problemlos.

Die Installation über App-Installer gilt für:

* Branchenspezifische/selbst entwickelte (nicht öffentliche) Apps
* Nur Seitenladevorgang
* Der Entwicklermodus oder das Geräteportal sind nicht erforderlich.
* Einfache Installation durch Endbenutzer
