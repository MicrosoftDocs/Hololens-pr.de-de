---
title: Betriebssystemsicherheit ohne Administratoren
description: Erfahren Sie mehr über Betriebssysteme ohne Administratoren, Gerätebesitzer und Sicherheit auf HoloLens Mixed Reality-Geräten.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: Sicherheit, hololens, ohne Administratoren, keine Administratoren, Betriebssystem, Betriebssystem ohne Administratoren, Administrator-Betriebssystem, administratorloses Betriebssystem, hololens 2, hololens2 Sicherheit,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 972bbc689505d42993cf47d82351ceeb79a0606b
ms.sourcegitcommit: 257720deb27f3bbc301175ce2a4afa79001862d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2021
ms.locfileid: "11440336"
---
# <a name="admin-less-operating-system"></a>Betriebssystem ohne Administrator

HoloLens 2 minimiert die Angriffsfläche für eine Rechteausweitung, indem der Support für die Administratorengruppe deaktiviert und alle UWP-Anwendungscodes von Drittanbietern so eingeschränkt werden, dass sie nur im AppContainer Sandbox als Standardbenutzer ausgeführt werden. Der Zugriff auf diesen Code wird nur für Ressourcen gestattet, deren Funktionen explizit in der Anwendung für einen nicht autorisierten Benutzer genannt werden, sowie für Ressourcen, auf die alle AppContainer Zugriff haben.
Auf diese Anwendungsfunktionen wird weiterhin über das dreistufige Klassifizierungsmodell zugegriffen:
  * Allgemein
  * Restricted (Eingeschränkter Zugriff)
  * Windows

Windows-Komponenten können auch den AppContainer Sandbox über System-UWPs nutzen. Weitere Informationen zu Apps für die Universelle Windows-Plattform (UWP) finden Sie in der [UWP-Dokumentation](https://docs.microsoft.com/windows/uwp/). Außerdem wird für Windows-Komponenten, für die eine stärkere Einschränkung der Zugriffsrechte erforderlich ist (wie Browser-Inhaltsseiten oder Parser) die Sandbox Less Privileged AppContainer (LPAC) verwendet. Diese beschränkt den Zugriff auf die Reihe von Ressourcen, die für alle AppContainer verfügbar sind.

## <a name="device-owner"></a>Gerätebesitzer

Zu guter Letzt wird die Ausführung spezifischer geräteweiter Vorgänge (z. B. Anschluss des Geräts an einen Mandanten oder die Benutzerverwaltung) nur „Gerätebesitzern“ gestattet. Diese Gruppe wird von Benutzern auf dem Gerät durch einen der folgenden Schritte ausgefüllt:
  * Der erste Nutzer auf dem Gerät wird immer als Besitzer festgelegt. 
> [!IMPORTANT]
>Für Azure AD-Benutzer besteht die Ausnahme von dieser Regel darin, dass das Gerät Azure AD ist, das über Autopilot oder eine Massenregistrierung von Azure AD verbunden ist, bei der ein nicht realer Benutzer verwendet wird. In diesem Fall wird der erste AAD-Benutzer, der sich beim Gerät anmeldet, möglicherweise nicht automatisch zum Gerätebesitzer ernannt, es sei denn, diesem Benutzer ist im Azure-Portal die Rolle "globaler Administrator" oder "Geräteadministrator" zugewiesen. Weitere Informationen finden Sie im Hinweis unten.  

  * Wenn ein Benutzer von einem anderen Besitzer auf dem Gerät aus den Einstellungen UX zum Besitzer gemacht wird.
  * Wenn der Gerätebesitzer nicht mehr verfügbar ist (das Unternehmen verlässt) und dem Gerät Azure AD beigetreten ist, kann der Mandantenadministrator den Gerätebesitzer im Azure-Portal zu einem neuen Benutzer ändern. Globale Administratoren und Geräteadministratoren eines Azure AD-Mandanten sind implizit als Besitzer auf dem Gerät angemeldet, ohne dass einer der vorherigen Schritte erforderlich ist.  

 IT-Administratoren können verwalten, auf welche Apps über die [Datenschutz](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy)-Richtlinien zugegriffen werden kann. 

> [!NOTE]
> Weitere Informationen darüber, wer der Gerätebesitzer auf einem in Azure AD eingebundenen Gerät wird, finden Sie in der[Dokumentation „Lokalen Administrator zuweisen“](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) („Lokaler Administrator“ meint hier allerdings „Gerätebesitzer“, da es auf HoloLens keine Administratoren gibt).