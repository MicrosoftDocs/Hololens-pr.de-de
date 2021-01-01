---
title: Übersicht – App-Verwaltung
description: APP, Verwaltung, App-Verwaltung
keywords: HoloLens, Benutzer, Konto, APP, Anwendungsverwaltung,
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
ms.openlocfilehash: 2ca0b05b6ed61ddce327a44fedbbcf280b33a106
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252666"
---
# App-Verwaltung: Übersicht

Sie können apps auf vier verschiedenen Pfaden bereitstellen: **Mobile Device Management (MDM)**, **Microsoft Store für Unternehmen**, **Microsoft Store**oder durch die Installation über die bereit **Stellung**.

## Mobile Geräteverwaltung (MDM)

Mit einer MDM-Lösung können IT-Entscheider und Administratoren ihre in-House-, Branchen-apps privat automatisch installieren (pushen) oder Apps über den Store für eine Gruppe von Benutzern kaufen. HoloLens-Geräte funktionieren am besten mit Microsoft Endpoint Manager (InTune) für die [Anwendungsverwaltung](app-deploy-intune.md). Darüber hinaus bietet InTune Benutzern eine feinere Steuerung von IT-verwalteten Apps über die herunterladbare Funktionalität des Unternehmensportals.

> [!NOTE]
> Die folgenden Anweisungen gelten für Benutzer, die Ihre Anwendungen mit InTune verwalten möchten. Microsoft empfiehlt die Verwendung von InTune für die Anwendungs-und Geräteverwaltung.

Mobile Device Management (MDM) gilt für:

* MDM bereitgestellt + Unternehmens Portal
* Branchen-Apps (nicht öffentlich)
* Manuelle Installation verfügbarer Anwendungen über das Unternehmens Portal
* Administrator-Push-Through-MDM-Richtlinie
* Automatische Aktualisierung über MDM

## Microsoft Store für Unternehmen

Der [Microsoft Store für Unternehmen](app-deploy-store-business.md) bietet IT-Entscheidern und Administratoren in Unternehmen die Suche, den Erwerb, die Verwaltung und die Verteilung von kostenlosen und kostenpflichtigen apps. IT-Administratoren können Microsoft Store-Apps und private Branchen-apps in einem einzigen Inventar verwalten sowie Lizenzen nach Bedarf zuweisen und wieder verwenden. Weitere Informationen finden Sie unter [Voraussetzungen für die Verwendung des Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).

Der Microsoft Store für Unternehmen gilt für:

* Öffentliche oder Branchen-apps
* Automatische Installation erforderlicher Anwendungen über die MDM-Zuordnung
* Benutzer lädt apps manuell herunter
* Automatische Aktualisierung

## Microsoft Store-Apps

Der Microsoft Store bietet IT-Entscheidern und Administratoren in Unternehmen die Suche, den Erwerb, die Verwaltung und die Verteilung öffentlicher apps.

Dieser Microsoft Store gilt für:

* Nur öffentliche apps
* Benutzer lädt apps manuell herunter
* Automatische Aktualisierung, wenn eine Verbindung mit dem Internet besteht

Weitere Informationen finden Sie unter [holographische Store-Apps](https://docs.microsoft.com/hololens/holographic-store-apps).

## Installieren über Bereitstellungspakete

[Bereitstellungspakete](app-deploy-provisioning-package.md) ermöglichen es Ihnen, benutzerdefinierte oder branchenspezifische apps zu installieren, sodass IT-Experten und Administratoren apps schnell auf einem lokalen Gerät (n) über USB installieren können. Diese Installation kann ohne Internetverbindung und für beliebige Identitätstypen erfolgen.

Die Installation über Bereitstellungspakete gilt für:

* Branchen-/selbst entwickelte (nicht öffentliche) apps
* Öffentliche Apps (wenn das offlineinstallationsprogramm verfügbar ist)
* Nur USB-Seiten laden
* Keine automatische Aktualisierung (erfordert manuelle Updates über Bereitstellungspaket)

## Installieren von apps auf HoloLens 2 über das App-Installationsprogramm

Die Verwendung der [App-Installationsprogramm](app-deploy-app-installer.md) Benutzer kann eine einfache Erfahrung für die Installation von apps auf lokalen Geräten oder das Freigeben einer APP für eine andere Person aufweisen, die mit anderen APP-Installationsmethoden auf HoloLens nicht vertraut ist. Dies kann erfolgen, ohne dass Sie den Entwicklermodus aktivieren oder Device Portal verwenden müssen. Dies ist eine einfache Methode, um eine vollständig erstellte APP zu verteilen. Unabhängig davon, ob Sie Ihre APP einfach einem anderen Benutzer mit einem HoloLens-Demo senden möchten, oder wenn Sie Ihre APP bereitstellen möchten, funktioniert diese Methode problemlos.

Die Installation über das App-Installationsprogramm gilt für:

* Branchen-/selbst entwickelte (nicht öffentliche) apps
* Nur Seite laden
* Erfordert keinen Entwicklermodus oder Geräte Portal
* Einfache Installation für Endbenutzer
