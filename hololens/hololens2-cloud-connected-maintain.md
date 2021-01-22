---
title: Bereitstellungshandbuch – Mit der Cloud verbundene HoloLens 2-Bereitstellung im großen Maßstab mit Remote Assist – Wartung
description: Halten Sie sich mit unseren Tipps zur Wartung und Unterstützung von HoloLens-Geräten über ein cloudverbundenes Netzwerk auf dem Laufenden.
keywords: HoloLens, Verwaltung, mit der Cloud verbunden, Remote Assist, AAD, Azure AD, MDM, Verwaltung mobiler Geräte
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283896"
---
# Verwalten – Leitfaden mit Verbindung mit der Cloud

## Updates

Microsoft hat Windows Update for Business entwickelt, um IT-Administratoren weitere Verwaltungsfunktionen rund um Windows Update bereitzustellen, wie beispielsweise die Möglichkeit, Updates für Gruppen von Geräten bereitzustellen oder Wartungszeitfenster für die Installation von Updates festzulegen.

Erfahren Sie, wie [Sie HoloLens-Updates](https://docs.microsoft.com/hololens/hololens-updates) verwalten, einschließlich geplanter Tage, geplanter Zeit und Festlegen der Aktiven Stunden auf dem Gerät, damit sie außerhalb der Arbeitszeiten aktualisiert werden.

Remote Assist ist eine In-Box App und kann über die Microsoft Store-App aktualisiert werden. Für alle Apps, die über den Microsoft Store heruntergeladen werden, können sie manuell über [die Microsoft](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) Store-App selbst aktualisiert werden.

## Supportplan

Ein Supportplan ist eine hervorragende Sache. Es ist hilfreich, jemanden oder eine Gruppe in der Problembehandlung für den Registrierungsprozess auf HoloLens-Geräten und die allgemeine Verwendung des Geräts HoloLens in Ihrer Organisation zu trainieren. Damit Ihre Benutzer ihre Probleme schneller beheben können, empfehlen wir, dass Ihr Eskalationsprozess in ähnlicher Weise wie in dieser Reihenfolge behandelt wird:

1. Ihr Supportdesk.
2. Ihr HoloLens -Expertenteam
3. [HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [Dokumentation zur Problembehandlung bei HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Hilfe und Support zu Windows](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## Entwicklungsplan

Nachdem Ihr Gerät erfolgreich registriert wurde, sind Sie nun bereit, Branchen-Apps (Line of Business Apps) auf Ihren Geräten bereitstellen. Dabei handelt es sich um benutzerdefinierte Apps, die für ihre&#39;erstellt wurden.

Wenn Sie bereits über eine Line-of-Business-App verfügen, können&#39;Über [MDM bereitstellen.](https://docs.microsoft.com/hololens/app-deploy-intune) Wenn Sie&#39;eine andere Methode bevorzugen, lesen Sie die Übersicht über die Anwendungsbereitstellung für [HoloLens 2,](https://docs.microsoft.com/hololens/app-deploy-overview) um weitere Methoden zum Bereitstellen Ihrer Branchen-App auf Ihren Geräten zu erhalten.

Wenn Sie&#39;ihre eigene Branchen-App noch nicht erstellt haben oder sich noch im Erstellungsprozess [](https://docs.microsoft.com/windows/mixed-reality/design/design) befinden, lesen Sie unsere Mixed Reality-Entwicklungs-Dokumente, um mit dem Entwerfen und Erstellen von Prototypen zu beginnen oder die Kernkonzepte für die ersten Schritte bei der [Mixed -Reality-Entwicklung](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr) zu erlernen.

## -Geräteverwaltung 

In diesem Handbuch wurde zwar von der Einrichtung der Mobile Device Management (MDM) gesprochen, es wurde jedoch nicht zum Anwenden von Geräteeinschränkungen oder Richtlinien auf Geräte verwendet. Die Geräteverwaltung kann verwendet werden, um den Zugriff durch Pushen von Zertifikaten zu ermöglichen oder den Zugriff mit einer Vielzahl von Geräteeinschränkungen einzuschränken. 

In vielen Fällen können Geräte Konnektivitätseinschränkungen haben, z. B. Bluetooth, VPN, USB oder sogar das Deaktivieren des Zugriffs auf die Kamera oder das Mikrofon. Wenn Sie eines dieser Interessen haben, empfehlen wir Ihnen, unsere Seite mit den allgemeinen [Geräteeinschränkungen zu lesen.](hololens-common-device-restrictions.md)

Es gibt weitere komplexere Geräteeinschränkungen, die Sie verwenden können. Beispiel:

- Beschränken der Seiten, die in der App "Einstellungen" angezeigt werden können, mithilfe von [SettingsPageVisibility,](settings-uri-list.md)sodass Benutzer nur auf die Einstellungen zugreifen können, die sie anpassen müssen, z. B. ändern Wi-Fi Verbindung.
- Verwenden [Sie den Kioskmodus,](hololens-kiosk.md) um die Benutzeroberfläche für Benutzer auf einem Gerät zu beschränken. Sie können kiosks so festlegen, dass eine einzelne App oder mehrere Apps mit einer benutzerdefinierten Startseite angezeigt werden. Kioske können auch verschiedenen Benutzern unterschiedliche Erfahrungen bieten.  
- [Windows-Anwendungssteuerung (Windows Application Control, WDAC),](windows-defender-application-control-wdac.md) damit bestimmte Apps oder Prozesse nicht vollständig gestartet werden.

Wenn Sie mehr über die verschiedenen Methoden der Geräteverwaltung oder Geräteeinschränkungen erfahren möchten, gehen Sie wie im nächsten Schritt vor, und lesen Sie die Übersicht über die Geräteverwaltung.

## Nächster Schritt

> [!div class="nextstepaction"]
> [CsPs und Geräteverwaltung (Übersicht) lesen](hololens-csp-policy-overview.md)