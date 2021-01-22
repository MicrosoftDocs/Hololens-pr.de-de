---
title: Übersicht – App-Verwaltung
description: Erste Schritte mit einer Übersicht über mixed Reality-App-Verwaltung mit Verwaltung mobiler Geräte, Microsoft Store für Unternehmen und Bereitstellungspaketen.
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
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283706"
---
# App-Verwaltung: Übersicht

Sie können Apps auf vier verschiedenen Pfaden bereitstellen: **Mobile Device Management (MDM),** **Microsoft Store für Unternehmen**, **Microsoft Store**oder durch Installation über **Bereitstellung.**

## Mobile Geräteverwaltung (MDM)

Eine MDM-Lösung ermöglicht es IT-Entscheidungsträgern und Administratoren, ihre eigenen ,Line-of-Business-Apps privat zu installieren (pushen) oder Apps über den Store für eine Gruppe von Benutzern zu erwerben. HoloLens-Geräte funktionieren am besten mit Microsoft Endpoint Manager (Intune) für [die Anwendungsverwaltung.](app-deploy-intune.md) Intune bietet Benutzern auch eine feinkörnige Kontrolle über IT-verwaltete Apps über das Unternehmensportal, das heruntergeladen werden kann.

> [!NOTE]
> Die folgenden Anweisungen sind für Benutzer, die ihre Anwendungen mit Intune verwalten möchten. Microsoft empfiehlt die Verwendung von Intune für die Anwendungs- und Geräteverwaltung.

Die Verwaltung mobiler Geräte (Mobile Device Management, MDM) gilt für:

* MDM bereitgestellt + Unternehmensportal
* (nicht öffentliche) Line-of-Business-Apps
* Manuelle Installation verfügbarer Anwendungen über das Unternehmensportal
* Administrator-Push über die MDM-Richtlinie
* Automatisches Update über MDM

## Microsoft Store für Unternehmen

Der [Microsoft Store für Unternehmen](app-deploy-store-business.md) bietet IT-Entscheidungsträgern und Administratoren in Unternehmen die Suche, den Erwerb, die Verwaltung und den Vertrieb kostenloser und kostenpflichtiger Apps. It administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed. Weitere Informationen finden Sie unter ["Voraussetzungen für die Verwendung des Microsoft Store für Unternehmen".](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)

Der Microsoft Store für Unternehmen gilt für:

* Öffentliche Apps oder Line-of-Business-Apps
* Automatische Installation erforderlicher Anwendungen über die MDM-Zuordnung
* Benutzer lädt Apps manuell herunter
* Automatisches Update

## Microsoft Store-Apps

Der Microsoft Store bietet IT-Entscheidungsträgern und Administratoren in Unternehmen die Suche, den Erwerb, die Verwaltung und den Vertrieb öffentlicher Apps.

Dieser Microsoft Store gilt für:

* Nur öffentliche Apps
* Benutzer lädt Apps manuell herunter
* Automatisches Update, wenn eine Verbindung mit dem Internet besteht

Weitere Informationen finden Sie unter [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).

## Installieren über Bereitstellungspakete

[Mit Bereitstellungspaketen](app-deploy-provisioning-package.md) können Sie benutzerdefinierte Apps oder Line-of-Business-Apps installieren, sodass IT-Profis und Administratoren Apps schnell über USB auf einem oder mehreren lokalen Geräten installieren können. Diese Installation kann ohne Internetverbindung und für jeden Identitätstyp durchgeführt werden.

Die Installation über Bereitstellungspakete gilt für:

* Geschäftsbereich/selbst entwickelte (nicht öffentliche) Apps
* Öffentliche Apps (wenn ein Offlineinstallationsprogramm verfügbar ist)
* Nur side-loading von USB
* Kein automatisches Update (erfordert manuelle Updates über das Bereitstellungspaket)

## Installieren von Apps auf HoloLens 2 über den App-Installer

Die Verwendung des [App-Installers](app-deploy-app-installer.md) kann für Benutzer einfach sein, um Apps auf lokalen Geräten zu installieren oder eine App für eine andere Person zu teilen, die mit anderen Methoden zur Installation von Apps auf HoloLens nicht vertraut ist. Dies ist möglich, ohne den Entwicklermodus aktivieren oder das Geräteportal verwenden zu müssen. Dies ist eine einfache Methode zum Verteilen einer vollständig erstellten App. Unabhängig davon, ob Sie Ihre App einfach für einen anderen Benutzer mit einer HoloLens demon möchten oder Wenn Sie Ihre App bereitstellen möchten, funktioniert diese Methode problemlos.

Die Installation über den App Installer gilt für:

* Geschäftsbereich/selbst entwickelte (nicht öffentliche) Apps
* Nur Sideloading
* Erfordert weder den Entwicklermodus noch das Geräteportal
* Einfache Installation für Endbenutzer
