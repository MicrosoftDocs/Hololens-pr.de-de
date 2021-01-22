---
title: Intune und Unternehmensportal
description: Informationen zum Einrichten, Zuweisen und Erstellen einer komfortablen Benutzeroberfläche mit Intune, der Verwaltung mobiler Geräte und dem Unternehmensportal.
keywords: Intune, App-Verwaltung, App, Unternehmensportal, Portal, HoloLens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283716"
---
# Intune und Unternehmensportal

Mit der Mobile Device Management (MDM) können Sie Ihre eigenen benutzerdefinierten Apps über [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) verwenden, um sie direkt auf Ihren HoloLens-Geräten bereitzustellen. Microsoft Intune ist ein cloudbasierter Dienst, der sich auf mobile Geräteverwaltung (Mobile Device Management, MDM) und mobile Anwendungsverwaltung (Mobile Application Management, MAM) konzentriert. Intune ist in der [Enterprise Mobility + Security (EMS)-Suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)von Microsoft enthalten und ermöglicht Benutzern, produktiv zu sein und gleichzeitig ihre Unternehmensdaten zu schützen. Weitere Informationen zu Intune finden Sie unter ["Was ist Intune".](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

## Setup

1. Laden Sie eine App in eine Geschäftsbereich hoch, oder laden Sie eine benutzerdefinierte App in Ihren Intune-Mandanten hoch. Siehe auch: [Enterprise-App-Verwaltung](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).

2. [Weisen Sie Ihre App einer Gruppe zu.](https://docs.microsoft.com/mem/intune/apps/apps-deploy) Basierend auf dem von Ihnen verwendeten Zuweisungstyp kann die App automatisch zugestellt oder verfügbar sein, um problemlos nach unten gezogen zu werden, wenn Sie über eine Auswahl von Apps verfügen.

> [!NOTE]
> Achten Sie beim Erstellen Ihres Appx-Bundles darauf, die Architektur für die Geräte, auf denen Sie bereitstellen, zu berücksichtigen. HoloLens 2 ist ARM64 und HoloLens (1. Generation) x86. Sie können beides in ein einzelnes Appx-Bundle mit einplanen, wenn Sie eine Umgebung mit gemischten Geräten planen.

## Zuweisungstypen

Damit Ihre App nach der Registrierung automatisch auf dem **** Gerät installiert wird, sollten Sie "Erforderlich" für diese Gruppe(en) auswählen.
Um Ihre App für den Download auf Geräten verfügbar zu machen, die über das Unternehmensportal registriert sind, wählen Sie **"Verfügbar"** für registrierte Geräte aus.

## End-User A0

Nachdem Sie die Konfiguration in Intune eingerichtet haben, können Endbenutzer Ihre ausgewählten Apps empfangen.

Führen Sie die folgenden Schritte aus, um Ihre App(en) automatisch zu erhalten:

1. Registrieren Sie Ihr Gerät bei Ihrem Mandanten.
2. Sobald Ihr Gerät die Registrierung abgeschlossen hat, sollten Sie die App auf Ihrem Gerät erhalten.
3. Wenn Die App nicht sofort angezeigt **** wird, wechseln Sie zu Kontoinformationen zu "Einstellungskonten " Arbeit" oder "Schule", und scrollen Sie nach unten, um Informationen zum Status der  >  ****  >  ****  >  ** installierten App zu erhalten.

So wechseln Sie über das Unternehmensportal zu Apps:

1. Öffnen Sie **das Startmenü,** und wählen **Sie Microsoft Store aus.**
2. Suchen Sie nach **dem Unternehmensportal,** und laden Sie die App herunter.
3. Melden Sie sich bei Ihrem Konto an.
4. Wählen Sie die App aus, die Sie empfangen möchten, und laden Sie sie herunter.

> [!Tip]
> Erfahren Sie mehr [über die automatische Installation des Unternehmensportals](https://docs.microsoft.com/mem/intune/apps/company-portal-app) und das Bereitstellen und Verwalten von Apps in [Intune.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
