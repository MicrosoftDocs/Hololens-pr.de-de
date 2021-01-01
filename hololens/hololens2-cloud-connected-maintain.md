---
title: Bereitstellungshandbuch – Cloud Connected HoloLens 2-Bereitstellung im Maßstab mit Remote Unterstützung – verwalten
description: Tipps zum Verwalten von HoloLens-Geräten über ein mit der Cloud verbundenes Netzwerk
keywords: HoloLens, Verwaltung, Cloud Connected, Remote Assist, AAD, Azure AD, MDM, Verwaltung mobiler Geräte
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
ms.openlocfilehash: 8117c73516d2775ec67f37bad524bcf377ece2e5
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252696"
---
# Verwalten-Cloud Connected-Leitfaden

## Updates

Microsoft hat Windows Update for Business entwickelt, um IT-Administratoren weitere Verwaltungsfunktionen rund um Windows Update bereitzustellen, wie beispielsweise die Möglichkeit, Updates für Gruppen von Geräten bereitzustellen oder Wartungszeitfenster für die Installation von Updates festzulegen.

Hier erfahren Sie, wie Sie [HoloLens-Updates verwalten](https://docs.microsoft.com/hololens/hololens-updates) , einschließlich geplanter Tage, geplanter Zeit und festlegen aktiver Stunden auf dem Gerät, damit es außerhalb der Arbeitszeiten aktualisiert wird.

Bei der Remote Unterstützung handelt es sich um eine In-Box-APP, die über die Microsoft Store-APP aktualisiert werden kann. Für alle apps, die über den Microsoft Store heruntergeladen werden, können Sie [über die Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) -APP selbst manuell aktualisiert werden.

## Supportplan

Ein Support Plan eignet sich hervorragend für den richtigen Ort. Wenn Sie eine Person oder eine Gruppe haben, die bei der Problembehandlung des Registrierungsvorgangs auf HoloLens-Geräten geschult wurde, und auch die allgemeine Verwendung des HoloLens-Geräts in Ihrer Organisation ist hilfreich. Damit Ihre Benutzer eine schnellere Lösung ihrer Probleme erhalten können, empfehlen wir, dass Ihr Eskalationsprozess auf ähnliche Weise wie in dieser Reihenfolge gehandhabt wird:

1. Ihr Support-Desk.
2. Ihr HoloLens-Expertenteam
3. [HoloLens-Dokumente](https://docs.microsoft.com/hololens/)  /  [HoloLens-Problembehandlungsdokumentation](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Hilfe und Support zu Windows](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## Entwicklungs Plan

Nachdem Sie Ihr Gerät erfolgreich registriert haben, sind Sie nun bereit, Geschäftsbereichs-Apps (Lob-Apps) auf Ihren Geräten bereitzustellen. Hierbei handelt es sich um benutzerdefinierte apps, die für Ihre Organisation&#39;Anforderungen entwickelt wurden.

Wenn Sie bereits über eine Branchen-App verfügen,&#39;Sie bereit, [Ihre APP über MDM bereitzustellen](https://docs.microsoft.com/hololens/app-deploy-intune). Wenn Sie eine andere Methode&#39;d bevorzugen, lesen Sie die [Übersicht zur Anwendungsbereitstellung für HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) , um weitere Methoden zum Bereitstellen Ihrer Lob-App auf Ihren Geräten zu erfahren.

Wenn Sie noch keine eigene Lob-app erstellen oder sich noch im Prozess der Erstellung befinden&#39;, überprüfen Sie unsere Dokumentation zur Mixed-Reality-Entwicklung, um mit dem [Entwerfen und Prototypen zu beginnen](https://docs.microsoft.com/windows/mixed-reality/design/design) oder die grundlegenden Konzepte für den Einstieg in die [Mixed-Reality-Entwicklung kennenzulernen.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## -Geräteverwaltung 

Während dieses Leitfadens zum Einrichten der Verwaltung mobiler Geräte (MDM) gesprochen wurde, wurde es nicht verwendet, um Geräteeinschränkungen anzuwenden oder Richtlinien auf Geräte anzuwenden. Die Geräteverwaltung kann sowohl dazu verwendet werden, um den Zugriff zu ermöglichen, indem Sie Zertifikate drücken, als auch den Zugriff mit einer Reihe von Geräteeinschränkungen einschränken. 

In vielen Fällen können Geräte Verbindungseinschränkungen wie Bluetooth, VPN, USB oder sogar das Ausschalten des Zugriffs auf die Kamera oder das Mikrofon aufweisen. Wenn Ihnen eine dieser Interessen zusteht, empfehlen wir Ihnen, unsere [Seite mit den allgemeinen Geräteeinschränkungen](hololens-common-device-restrictions.md)zu lesen.

Es gibt weitere komplexere Geräteeinschränkungen, die Sie verwenden können. Wie:

- Einschränken der Seiten, die mithilfe von [SettingsPageVisibility](settings-uri-list.md)in der Einstellungs-APP angezeigt werden können, sodass Benutzer nur auf die Einstellungen zugreifen können, die Sie anpassen müssen, beispielsweise das Ändern der Wi-Fi Verbindung.
- Verwenden Sie den [Kiosk Modus](hololens-kiosk.md) , um die Benutzeroberfläche zu begrenzen, die Benutzern auf einem Gerät angezeigt wird. Sie können Kioske so einstellen, dass eine einzelne APP oder mehrere apps mit einer benutzerdefinierten Startseite angezeigt werden. Kioske können auch verschiedenen Benutzern unterschiedliche Erfahrungen präsentieren.  
- [Windows-Anwendungssteuerung (WDAC)](windows-defender-application-control-wdac.md) , damit bestimmte Apps oder Prozesse nicht vollständig gestartet werden können.

Wenn Sie mehr über die unterschiedlichen Methoden der Geräteverwaltung oder Geräteeinschränkungen erfahren möchten, führen Sie den nächsten Schritt aus, und lesen Sie unsere Übersicht zur Geräteverwaltung.

## Nächster Schritt

> [!div class="nextstepaction"]
> [Lesen der Übersicht über LSP und Geräteverwaltung](hololens-csp-policy-overview.md)