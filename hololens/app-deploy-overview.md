---
title: Übersicht – App-Verwaltung
description: APP, Verwaltung, App-Verwaltung
keywords: HoloLens, Benutzer, Konto, APP, Anwendungsverwaltung,
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
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
ms.openlocfilehash: e73a56e5a2fcef14e85f5f552e264dd8d796cc8f
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009453"
---
# App-Verwaltung: Übersicht

Sie können apps auf vier verschiedenen Pfaden bereitstellen: **Mobile Device Management (MDM)**, **Microsoft Store für Unternehmen**, **Microsoft Store**oder durch die Installation über die bereit **Stellung**. 

## Mobile Geräteverwaltung (MDM)

Mit einer MDM-Lösung können IT-Entscheider und Administratoren ihre in-House-, Branchen-apps privat automatisch installieren (pushen) oder Apps über den Store für eine Gruppe von Benutzern kaufen. HoloLens-Geräte funktionieren am besten mit Microsoft Endpoint Manager (InTune) für die [Anwendungsverwaltung](app-deploy-intune.md). Darüber hinaus bietet InTune Benutzern eine feinere Steuerung von IT-verwalteten Apps über die herunterladbare Funktionalität des Unternehmensportals.

> [!NOTE] 
> Die folgenden Anweisungen gelten für Benutzer, die Ihre Anwendungen mit InTune verwalten möchten. Microsoft empfiehlt die Verwendung von InTune für die Anwendungs-und Geräteverwaltung.
    
Mobile Device Management (MDM) gilt für: 
* MDM bereitgestellt + Unternehmens Portal 
* Geschäftszeile (nicht öffentliche) apps
* Manuelle Installation verfügbarer Anwendungen über das Unternehmens Portal
* Administrator-Push-Through-MDM-Richtlinie
* Automatische Aktualisierung über MDM

## Microsoft Store für Unternehmen

Der [Microsoft Store für Unternehmen](app-deploy-store-business.md) bietet IT-Entscheidern und Administratoren in Unternehmen die Suche, den Erwerb, die Verwaltung und die Verteilung von kostenlosen und kostenpflichtigen apps. IT-Administratoren können Microsoft Store-Apps und private Branchenapps in einem Inventar verwalten, sowie Lizenzen je nach Bedarf zuweisen und wiederverwenden. Weitere Informationen finden Sie unter [Voraussetzungen für die Verwendung des Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).
    
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

[Bereitstellungspakete](app-deploy-provisioning-package.md) ermöglichen es Ihnen, benutzerdefinierte oder branchenspezifische apps zu installieren, sodass IT-Experten und Administratoren apps schnell auf einem lokalen Gerät (n) über USB installieren können. Dies kann ohne Internetverbindung und für beliebige Identitätstypen erfolgen.
    
Die Installation über Bereitstellungspakete gilt für: 
* Geschäftszeile (nicht öffentliche) apps
* Öffentliche Apps (wenn das offlineinstallationsprogramm verfügbar ist)
* Nur USB-Seite laden
* Keine automatische Aktualisierung (erfordert manuelle Updates über Bereitstellungspaket)
