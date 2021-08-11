---
title: Betriebssystemsicherheit ohne Administratoren
description: Erfahren Sie mehr über Betriebssysteme ohne Administratoren, Gerätebesitzer und Sicherheit auf HoloLens Mixed Reality-Geräten.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: Sicherheit, Hololens, ohne Administratoren, keine Administratoren, Betriebssystem, Betriebssystem ohne Administratoren, Administrator-Betriebssystem, administratorloses Betriebssystem, Hololens 2, Hololens2 Sicherheit,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f4fc79b7f51933418cdda8368c6b4b070e854dd0978754647ce864075c772cfd
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665538"
---
# <a name="admin-less-operating-system"></a>Betriebssystem ohne Administrator

HoloLens 2 minimiert die Angriffsfläche für eine Rechteausweitung, indem der Support für die Administratorengruppe deaktiviert wird und der gesamte UWP-Anwendungscode von Drittanbietern so eingeschränkt wird, dass er nur in der AppContainer-Sandbox als Standardbenutzer ausgeführt wird. Der Zugriff auf diesen Code wird nur Ressourcen gestattet, deren Funktionen explizit in der Anwendung für einen Benutzer ohne erhöhte Rechte genannt werden, sowie für Ressourcen, auf die alle AppContainer Zugriff haben.
Auf diese Anwendungsfunktionen wird weiterhin über das dreistufige Klassifizierungsmodell zugegriffen:
  * Allgemein
  * Eingeschränkt
  * Windows

Windows-Komponenten können ebenfalls die AppContainer-Sandbox über System-UWPs nutzen. Weitere Informationen zur universellen Windows-Plattform (UWP) finden Sie in der [UWP-Dokumentation](/windows/uwp/). Außerdem wird für Windows-Komponenten, für die eine stärkere Einschränkung der Zugriffsrechte erforderlich ist (wie Browser-Inhaltsseiten oder Parser) die LPAC-Sandbox (Less Privileged AppContainer) verwendet. Diese beschränkt den Zugriff auf die Sammlung von Ressourcen, die für alle AppContainer verfügbar sind.

## <a name="device-owner"></a>Geräteeigentümer

Zu guter Letzt wird die Ausführung spezifischer geräteweiter Vorgänge (z. B. Anschluss des Geräts an einen Mandanten oder Benutzerverwaltung) nur „Gerätebesitzern“ gestattet. Diese Gruppe wird von Benutzern auf dem Gerät durch einen der folgenden Schritte gefüllt:
  * Der erste Benutzer auf dem Gerät wird immer als Besitzer festgelegt. 
> [!IMPORTANT]
>Für Azure AD-Benutzer gilt die Ausnahme von dieser Regel, wenn das Gerät über Autopilot oder Bulk Azure AD Enrollment mit Azure AD verbunden ist, wozu ein nicht realer Benutzer verwendet wird. In diesem Fall wird der erste AAD-Benutzer, der sich beim Gerät anmeldet, möglicherweise nicht automatisch zum Gerätebesitzer ernannt, es sei denn, diesem Benutzer ist im Azure-Portal die Rolle „globaler Administrator“ oder „Geräteadministrator“ zugewiesen. Weitere Informationen finden Sie im Hinweis unten.  

  * Wenn ein Benutzer von einem anderen Besitzer auf dem Gerät in der Einstellungen-Benutzeroberfläche zum Besitzer gemacht wird.
  * Wenn der Gerätebesitzer nicht mehr verfügbar ist (das Unternehmen verlässt) und das Gerät Azure AD-Mitglied ist, kann der Mandantenadministrator den Gerätebesitzer im Azure-Portal in einen neuen Benutzer ändern. Globale Administratoren und Geräteadministratoren eines Azure AD-Mandanten sind implizit als Besitzer auf dem Gerät angemeldet, ohne dass einer der vorherigen Schritte erforderlich ist.  

 IT-Administratoren können mithilfe der [Datenschutzrichtlinien](/windows/client-management/mdm/policy-csp-privacy) verwalten, auf welche Apps zugegriffen werden kann. 

> [!NOTE]
> Weitere Informationen darüber, wer auf einem in Azure AD eingebundenen Gerät zum Gerätebesitzer ernannt wird, finden Sie in der Dokumentation [Zuweisen eines lokalen Administrators](/azure/active-directory/devices/assign-local-admin) („Lokaler Administrator“ bedeutet hier allerdings „Gerätebesitzer“, da es auf HoloLens keine Administratoren gibt).