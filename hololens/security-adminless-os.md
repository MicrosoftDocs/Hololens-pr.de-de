---
title: Sicheres Betriebssystem ohne Administrator
description: Betriebssystem ohne Administrator und HoloLens-Sicherheit
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
ms.openlocfilehash: ea35012e63f4c0d8868f9604809c1552c3212e72
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016639"
---
# Betriebssystem ohne Administrator

HoloLens 2 minimiert die Angriffsfläche für eine Rechteausweitung, indem der Support für die Administratorengruppe deaktiviert und alle UWP-Anwendungscodes von Drittanbietern so eingeschränkt werden, dass sie nur im AppContainer Sandbox als Standardbenutzer ausgeführt werden. Der Zugriff auf diesen Code wird nur für Ressourcen gestattet, deren Funktionen explizit in der Anwendung für einen nicht autorisierten Benutzer genannt werden, sowie für Ressourcen, auf die alle AppContainer Zugriff haben.
Auf diese Anwendungsfunktionen wird weiterhin über das dreistufige Klassifizierungsmodell zugegriffen:
  * Allgemein
  * Restricted (Eingeschränkter Zugriff)
  * Windows

Windows-Komponenten können auch den AppContainer Sandbox über System-UWPs nutzen. Weitere Informationen zu Apps für die Universelle Windows-Plattform (UWP) finden Sie in der [UWP-Dokumentation](https://docs.microsoft.com/windows/uwp/). Außerdem wird für Windows-Komponenten, für die eine stärkere Einschränkung der Zugriffsrechte erforderlich ist (z. B. Browser-Inhaltsseiten, Parser) die Sandbox Less Privileged AppContainer (LPAC) verwendet. Diese beschränkt den Zugriff auf die Reihe von Ressourcen, die für alle AppContainer verfügbar sind.

Zu guter Letzt wird die Ausführung spezifischer geräteweiter Vorgänge (z. B. Anschluss des Geräts an einen Mandanten oder die Benutzerverwaltung) nur „Gerätebesitzern“ gestattet. Diese Gruppe wird von Benutzern auf dem Gerät durch einen der folgenden Schritte ausgefüllt:
  * Der erste Nutzer auf dem Gerät wird immer als Besitzer festgelegt. 
    * Die Ausnahme von dieser Regel kommt zum Tragen, wenn das Gerät in AAD eingebunden ist. Dann wird der Benutzer, der die Einbindung vorgenommen hat, zum Gerätebesitzer. Dies gilt beispielsweise, wenn ein Gerät über Autopilot in AAD eingebunden wurde. In diesem Fall hat der erste Benutzer, der sich auf dem Gerät angemeldet, die Einbindung des Geräts nicht vorgenommen und wird daher kein Gerätebesitzer. Weitere Informationen darüber, wer der Gerätebesitzer auf einem in AAD eingebundenen Gerät wird, finden Sie in der[Dokumentation „Lokalen Administrator zuweisen“](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) („Lokaler Administrator“ meint hier allerdings „Gerätebesitzer“, da es auf HoloLens keine Administratoren gibt).
  * Heraufstufung eines Benutzers zum Besitzer über die UX „Einstellungen“ durch einen anderen Benutzer auf dem Gerät.
  * Wenn der Gerätebesitzer nicht mehr verfügbar ist (weil er z. B. das Unternehmen verlassen hat), und das Gerät in AAD eingebunden ist, kann der Mandantenadministrator im Azure Portal einen neuen Benutzer als Gerätebesitzer festlegen.
Globale Administratoren eines Azure AD-Mandanten werden implizit als Besitzer auf dem Gerät festgelegt, ohne dass sie einen der vorstehenden Schritte ausführen müssen. 

IT-Administratoren können verwalten, auf welche Apps über die [Datenschutz](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy)-Richtlinien zugegriffen werden kann. 
