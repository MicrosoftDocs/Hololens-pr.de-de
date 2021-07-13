---
title: 'Übersicht: App-Verwaltung'
description: Verschaffen Sie sich einen Überblick über die Mixed Reality-App-Verwaltung mit Verwaltung mobiler Geräte, Microsoft Store für Unternehmen und Bereitstellungspakete.
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
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635550"
---
# <a name="app-management-overview"></a>App-Verwaltung: Übersicht

Sie können Apps auf vier verschiedenen Pfaden bereitstellen: **Mobile Geräteverwaltung (MDM),** **Microsoft Store für Unternehmen**, **Microsoft Store** oder durch Installation über **Bereitstellung**.

## <a name="mobile-device-management-mdm"></a>Mobile Geräteverwaltung (MDM)

Mit einer MDM-Lösung können IT-Entscheidungsträger und Administratoren ihre unternehmensspezifischen Apps privat automatisch installieren (pushen) oder Apps über den Store für eine Gruppe von Benutzern erwerben. HoloLens-Geräte funktionieren am besten mit Microsoft Endpoint Manager (Intune) für [die Anwendungsverwaltung.](app-deploy-intune.md) Intune bietet Benutzern auch eine feiner abgrenzende Kontrolle über IT-verwaltete Apps über die Unternehmensportal herunterladbare Benutzererfahrung.

> [!NOTE]
> Die folgenden Anweisungen gelten für Benutzer, die ihre Anwendungen mit Intune verwalten möchten. Microsoft empfiehlt die Verwendung von Intune für die Anwendungs- und Geräteverwaltung.

Mobile Geräteverwaltung (MDM) gilt für:

* MDM bereitgestellt + Unternehmensportal
* Line of Business-Apps (nicht öffentlich)
* Manuelle Installation verfügbarer Anwendungen über Unternehmensportal
* Pushen durch den Administrator durch die MDM-Richtlinie
* Automatisches Update über MDM

## <a name="microsoft-store-for-business"></a>Microsoft Store für Unternehmen

Das [Microsoft Store für Unternehmen](app-deploy-store-business.md) bietet IT-Entscheidungsträgern und Administratoren in Unternehmen das Suchen, Erwerben, Verwalten und Verteilen kostenloser und kostenpflichtiger Apps. IT-Administratoren können Microsoft Store-Apps und private Line-of-Business-Apps in einem Bestand verwalten und lizenzen nach Bedarf zuweisen und wiederverwenden. Weitere Informationen finden Sie unter [Voraussetzungen für die Verwendung der Microsoft Store für Unternehmen](/microsoft-store/prerequisites-microsoft-store-for-business).

Die Microsoft Store für Unternehmen gilt für:

* Öffentliche oder line of Business-Apps
* Automatische Installation erforderlicher Anwendungen durch MDM-Zuordnung
* Benutzer lädt Apps manuell herunter
* Automatische Aktualisierung

## <a name="microsoft-store-apps"></a>Microsoft Store-Apps

Das Microsoft Store bietet IT-Entscheidungsträgern und Administratoren in Unternehmen das Suchen, Erwerben, Verwalten und Verteilen öffentlicher Apps.

Diese Microsoft Store gilt für:

* Nur öffentliche Apps
* Benutzer lädt Apps manuell herunter
* Automatisches Update, wenn eine Internetverbindung besteht

Weitere Informationen finden Sie unter [Holographic Store Apps](/hololens/holographic-store-apps).

## <a name="install-via-provisioning-packages"></a>Installieren über Bereitstellungspakete

[Mit](app-deploy-provisioning-package.md) Bereitstellungspaketen können Sie benutzerdefinierte oder line of Business-Apps installieren, sodass IT-Profis und Administratoren Apps schnell über USB auf einem lokalen Gerät installieren können. Diese Installation kann ohne Internetverbindung und für jeden Identitätstyp erfolgen.

Die Installation über Bereitstellungspakete gilt für:

* Line of Business/Selbst entwickelte (nicht öffentliche) Apps
* Öffentliche Apps (wenn das Offlineinstallationsprogramm verfügbar ist)
* Nur USB-Seitenladevorgang
* Keine automatische Aktualisierung (manuelle Updates über Bereitstellungspaket erforderlich)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>Installieren von Apps auf HoloLens 2 über App-Installer

Mithilfe [App-Installer](app-deploy-app-installer.md) können Benutzer einfach Apps auf lokalen Geräten installieren oder eine App für andere Benutzer freigeben, die mit anderen App-Installationsmethoden auf lokalen Geräten nicht vertraut HoloLens. Dies kann erfolgen, ohne den Entwicklermodus zu aktivieren oder Geräteportal. Dies ist eine einfache Methode zum Verteilen einer vollständig erstellten App. Unabhängig davon, ob Sie Ihre App einfach für einen anderen Benutzer mit einem HoloLens demo oder ihre App bereitstellen möchten, funktioniert diese Methode problemlos.

Die Installation über App-Installer gilt für:

* Line of Business/Selbst entwickelte (nicht öffentliche) Apps
* Nur side-load
* Der Entwicklermodus oder das Geräteportal ist nicht erforderlich.
* Einfache Installation durch Endbenutzer
