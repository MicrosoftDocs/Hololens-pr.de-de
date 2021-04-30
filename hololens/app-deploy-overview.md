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
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308644"
---
# <a name="app-management-overview"></a>App-Verwaltung: Übersicht

Sie können Apps auf vier verschiedenen Pfaden bereitstellen: **Mobile Geräteverwaltung (MDM),** **Microsoft Store für Unternehmen**, **Microsoft Store** oder , indem Sie sie über Die **Bereitstellung installieren.**

## <a name="mobile-device-management-mdm"></a>Mobile Geräteverwaltung (MDM)

Mit einer MDM-Lösung können IT-Entscheidungsträger und Administratoren ihre unternehmensspezifischen Apps privat automatisch installieren (pushen) oder Apps über den Store für eine Gruppe von Benutzern erwerben. HoloLens-Geräte funktionieren am besten mit Microsoft Endpoint Manager (Intune) für die [Anwendungsverwaltung.](app-deploy-intune.md) Intune bietet Benutzern auch eine feiner abgrenzende Kontrolle über IT-verwaltete Apps über die Unternehmensportal herunterladbare Benutzererfahrung.

> [!NOTE]
> Die folgenden Anweisungen gelten für Benutzer, die ihre Anwendungen mit Intune verwalten möchten. Microsoft empfiehlt die Verwendung von Intune für die Anwendungs- und Geräteverwaltung.

Mobile Geräteverwaltung (MDM) gilt für:

* MDM bereitgestellt + Unternehmensportal
* Line of Business-Apps (nicht öffentlich)
* Manuelle Installation verfügbarer Anwendungen über Unternehmensportal
* Pushen durch den Administrator durch die MDM-Richtlinie
* Automatisches Update über MDM

## <a name="microsoft-store-for-business"></a>Microsoft Store für Unternehmen

Das [Microsoft Store für Unternehmen](app-deploy-store-business.md) bietet IT-Entscheidungsträgern und Administratoren in Unternehmen das Suchen, Erwerben, Verwalten und Verteilen kostenloser und kostenpflichtiger Apps. IT-Administratoren können Microsoft Store-Apps und private Line-of-Business-Apps in einem Bestand verwalten und lizenzen nach Bedarf zuweisen und wiederverwenden. Weitere Informationen finden Sie unter [Voraussetzungen für die Verwendung der Microsoft Store für Unternehmen](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).

Die Microsoft Store für Unternehmen gilt für:

* Öffentliche apps oder Line of Business-Apps
* Automatische Installation erforderlicher Anwendungen über MDM-Zuordnung
* Benutzer lädt Apps manuell herunter
* Automatische Aktualisierung

## <a name="microsoft-store-apps"></a>Microsoft Store-Apps

Die Microsoft Store bietet IT-Entscheidungsträgern und Administratoren in Unternehmen die Möglichkeit, öffentliche Apps zu finden, zu erwerben, zu verwalten und zu verteilen.

Diese Microsoft Store gilt für:

* Nur öffentliche Apps
* Benutzer lädt Apps manuell herunter
* Automatisches Update, wenn eine Verbindung mit dem Internet besteht

Weitere Informationen finden Sie unter [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).

## <a name="install-via-provisioning-packages"></a>Installieren über Bereitstellungspakete

[Mit Bereitstellungspaketen](app-deploy-provisioning-package.md) können Sie benutzerdefinierte oder branchenspezifische Apps installieren, sodass IT-Spezialisten und Administratoren Apps schnell über USB auf einem lokalen Gerät installieren können. Diese Installation kann ohne Internetverbindung und für jeden Identitätstyp erfolgen.

Die Installation über Bereitstellungspakete gilt für:

* Branchenspezifische/selbst entwickelte (nicht öffentliche) Apps
* Öffentliche Apps (wenn ein Offlineinstaller verfügbar ist)
* Nur USB-Querladen
* Kein automatisches Update (erfordert manuelle Updates über das Bereitstellungspaket)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>Installieren von Apps auf HoloLens 2 über App-Installer

Mithilfe der [App-Installer](app-deploy-app-installer.md) können Benutzer über eine einfache Benutzeroberfläche verfügen, um Apps auf lokalen Geräten zu installieren oder eine App für eine andere Person zu teilen, die mit anderen App-Installationsmethoden auf HoloLens nicht vertraut ist. Dies kann erfolgen, ohne den Entwicklermodus zu aktivieren oder Geräteportal zu verwenden. Dies ist eine einfache Methode zum Verteilen einer vollständig erstellten App. Unabhängig davon, ob Sie Ihre App einfach für einen anderen Benutzer mit einer HoloLens demo oder ihre App bereitstellen möchten, funktioniert diese Methode problemlos.

Die Installation über App-Installer gilt für:

* Line of Business/Selbst entwickelte (nicht öffentliche) Apps
* Nur side-load
* Der Entwicklermodus oder das Geräteportal ist nicht erforderlich.
* Einfache Installation durch Endbenutzer
