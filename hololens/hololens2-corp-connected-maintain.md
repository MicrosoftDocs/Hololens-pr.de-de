---
title: Bereitstellungshandbuch – Unternehmensverknte HoloLens 2 mit Dynamics 365-Anleitungen – Maintain
description: Erfahren Sie, wie Sie HoloLens 2-Geräte über ein verbundenes Unternehmensnetzwerk mit Dynamics 365-Anleitungen verwalten.
keywords: HoloLens, Verwaltung, unternehmensgebunden, Dynamics 365-Anleitungen, AAD, Azure AD, MDM, Verwaltung mobiler Geräte
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f231e65e17ab053e34e7174e1ed7ff6e7a0a56b8
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448556"
---
# <a name="maintain---corporate-connected-guide"></a>Maintain – Corporate Connected Guide

## <a name="update-hololens"></a>Aktualisieren von HoloLens

Microsoft hat Windows Update for Business entwickelt, um IT-Administratoren weitere Verwaltungsfunktionen rund um Windows Update bereitzustellen, wie beispielsweise die Möglichkeit, Updates für Gruppen von Geräten bereitzustellen oder Wartungszeitfenster für die Installation von Updates festzulegen.

Eine beliebte Methode zum Verwalten von Updates ist die Feature-Verschiebung um 30 Tage. Auf diese Weise können Administratoren neue Features aktualisieren und in der Vorschau anzeigen, wissen aus erster Hand und Ihren Support über neue Änderungen informieren.

Erfahren Sie, wie [Sie HoloLens-Updates](https://docs.microsoft.com/hololens/hololens-updates)verwalten, einschließlich geplanter Tage, geplanter Uhrzeiten und Festlegen der Aktiven Stunden auf dem Gerät, sodass sie außerhalb der Arbeitszeiten aktualisiert werden.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Aktualisieren von Dynamics 365-Anleitungen (und anderen Store-Apps)

Dynamics 365 Guides ist eine In-Box App und kann über die Microsoft Store-App aktualisiert werden. Für alle Apps, die über den Microsoft Store heruntergeladen werden, können sie manuell über die [Microsoft Store-App](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) selbst aktualisiert werden.

## <a name="how-to-update-lob-apps"></a>Aktualisieren von Branchen-Apps

Branchen-Apps können auf die gleiche Weise aktualisiert werden, wie sie Intune hinzugefügt wurden. Apps können in Intune aktualisiert werden, indem die neue App mit einer höheren Versionsnummer in die vorhandene App-Konfiguration hochgeladen wird. Wenn das Gerät mit Intune synchronisiert wird, wird beobachtet, dass es eine neuere App-Version gibt, und die neuere App wird heruntergeladen und ersetzt die alte App.

1. Navigieren Sie zum Hochladen der neueren App zum [MEM-Portal](https://endpoint.microsoft.com/#home)  ->  **Apps** -> Alle Apps ****  ->  *TheNameOfYourApp-Eigenschaften.*  ->  ****
2. Wählen Sie neben App-Informationen die Option **Bearbeiten aus.**
3. Wählen Sie ihre Datei aus, um den Wert der &quot; zu aktualisierende &quot; Datei auswählen.
4. Verwenden Sie hier das Kontextmenü, um den Datei-Explorer zu öffnen und die neuere Version der BRANCHEN-App hochzuladen. Stellen Sie sicher, dass Abhängigkeiten bei Bedarf enthalten sind.

Weitere Informationen: [Intune App Deployment for HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="development-plan"></a>Entwicklungsplan

Nachdem Ihr Gerät erfolgreich registriert wurde, können Sie nun weitere Branchen-Apps auf Ihren Geräten bereitstellen. Für die Dauer dieses Handbuchs verwenden wir eine Beispiel-App, aber es ist wahrscheinlicher, dass Sie benutzerdefinierte Apps verwenden möchten, die für die Anforderungen Ihrer Organisation erstellt wurden.

Wenn Sie bereits über eine BRANCHEN-App verfügen, können Sie Ihre App [über MDM bereitstellen.](https://docs.microsoft.com/hololens/app-deploy-intune) Wenn Sie eine andere Methode bevorzugen, lesen Sie die Übersicht über die Anwendungsbereitstellung für [HoloLens 2,](https://docs.microsoft.com/hololens/app-deploy-overview) um weitere Methoden zum Bereitstellen Ihrer Branchen-App auf Ihren Geräten zu erfahren.

Wenn Sie noch ihre eigene Branchen-App erstellen müssen oder sich noch im Erstellungsprozess befinden, lesen Sie unsere Mixed Reality-Entwicklungs-Dokumente, um mit dem Entwerfen und Prototyping zu beginnen oder die Kernkonzepte für die ersten Schritte mit der Mixed Reality-Entwicklung zu [erlernen.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr) [](https://docs.microsoft.com/windows/mixed-reality/design/design)

## <a name="support-plan"></a>Supportplan

Ein Supportplan ist eine hervorragende Sache. Es ist hilfreich, dass eine Person oder eine Gruppe sich für die Problembehandlung beim Registrierungsprozess auf HoloLens-Geräten und die allgemeine Verwendung des HoloLens-Geräts in Ihrer Organisation ausübte. Um Ihren Benutzern die schnellere Lösung ihrer Probleme zu ermöglichen, empfehlen wir, dass Ihr Eskalationsprozess in ähnlicher Weise wie in dieser Reihenfolge behandelt wird:

1. Ihr Supportdesk.
2. Ihr HoloLens-Expertenteam
3. [HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Hilfe und Support zu Windows](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>-Geräteverwaltung

In diesem Handbuch wurde über das Einrichten von Mobile Device Management (MDM) gesprochen und zum Einrichten einiger Gerätekonfigurationen und Anwenden von Einstellungen verwendet, um den Zugriff in Bezug auf Wi-Fi Zertifikate und Proxy zu ermöglichen. MDM kann jedoch auch verwendet werden, um Geräteeinschränkungen über CSPs und Richtlinien anzuwenden.

In vielen Fällen können Geräte Konnektivitätseinschränkungen haben, z. B. Bluetooth, VPN, USB oder sogar das Deaktivieren des Zugriffs auf die Kamera oder das Mikrofon. Wenn Sie eines dieser Interessen haben, empfehlen wir Ihnen, unsere Seite mit den allgemeinen [Geräteeinschränkungen zu lesen.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

Es gibt weitere komplexere Geräteeinschränkungen, die Sie verwenden können. Beispiel:

- Einschränken der Seiten, die in der Einstellungs-App mithilfe von [SettingsPageVisibility](https://docs.microsoft.com/hololens/settings-uri-list)angezeigt werden können, sodass Benutzer nur auf die Einstellungen zugreifen können, die sie anpassen müssen, z. B. ändern Wi-Fi Verbindung.
- Verwenden [Sie den Kioskmodus,](https://docs.microsoft.com/hololens/hololens-kiosk) um die Benutzeroberfläche für Benutzer auf einem Gerät zu beschränken. Sie können kiosks so festlegen, dass eine einzelne App oder mehrere Apps mit einer benutzerdefinierten Startseite angezeigt werden. Kioske können auch verschiedene Benutzererfahrungen präsentieren.
- [Windows Application Control (WDAC),](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) damit bestimmte Apps oder Prozesse nicht vollständig gestartet werden.

Wenn Sie mehr über zusätzliche Methoden der Geräteverwaltung oder Geräteeinschränkungen erfahren möchten, gehen Sie zum nächsten Schritt und lesen Sie unsere Übersicht über [die Geräteverwaltung](https://docs.microsoft.com/hololens/hololens-csp-policy-overview).





