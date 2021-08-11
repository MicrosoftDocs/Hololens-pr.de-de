---
title: Bereitstellungshandbuch – Unternehmens verbundene HoloLens 2 mit Dynamics 365 Guides – Verwalten
description: Erfahren Sie, wie Sie HoloLens 2 geräte über ein verbundenes Unternehmensnetzwerk mit Dynamics 365 Guides.
keywords: HoloLens, Verwaltung, unternehmens verbunden, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Geräteverwaltung
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
ms.openlocfilehash: 2649e370e98747562591c031b8ae262674c831e071f4ef228557dda66d2dc768
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660272"
---
# <a name="maintain---corporate-connected-guide"></a>Verwalten – Leitfaden für verbundene Unternehmen

## <a name="update-hololens"></a>Aktualisieren von HoloLens

Microsoft hat Windows Update for Business entwickelt, um IT-Administratoren weitere Verwaltungsfunktionen rund um Windows Update bereitzustellen, wie beispielsweise die Möglichkeit, Updates für Gruppen von Geräten bereitzustellen oder Wartungszeitfenster für die Installation von Updates festzulegen.

Eine beliebte Methode zum Verwalten von Updates besteht in einer Feature-Verzögerung von 30 Tagen. Auf diese Weise können Administratoren neue Features aktualisieren und eine Vorschau anzeigen. So können sie aus erster Hand Wissen sammeln und Ihren Supportdesk über neue Änderungen informieren.

Erfahren Sie, [wie Sie](/hololens/hololens-updates)HoloLens Verwalten von Updates verwalten, einschließlich geplanter Tage, geplanter Zeit und Festlegen der aktiven Stunden auf dem Gerät, damit es außerhalb der Arbeitszeit aktualisiert wird.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Aktualisieren von Dynamics 365 Guides (und anderen Store-Apps)

Dynamics 365 Guides ist eine In-Box-App und kann über die Microsoft Store werden. Für alle Apps, die über die Microsoft Store heruntergeladen werden, können sie manuell über die Microsoft Store [App](/hololens/holographic-store-apps#update-apps) selbst aktualisiert werden.

## <a name="how-to-update-lob-apps"></a>Aktualisieren von BRANCHEN-Apps

BRANCHEN-Apps können auf die gleiche Weise aktualisiert werden, wie sie intune hinzugefügt wurden. Apps können in Intune aktualisiert werden, indem die neue App mit einer höheren Versionsnummer in die vorhandene App-Konfiguration hochgeladen wird. Wenn das Gerät mit Intune synchronisiert wird, wird beobachtet, dass es eine neuere App-Version gibt, und die neuere App wird heruntergeladen und ersetzt die alte App.

1. Um die neuere App hochzuladen, navigieren Sie zum [](https://endpoint.microsoft.com/#home)  ->  **MEM-Portal Apps** -> Alle Apps   ->  *TheNameOfYourApp-Eigenschaften.*  ->  
2. Wählen Sie neben App-Informationen die Option **Bearbeiten aus.**
3. Wählen Sie für den Wert &quot; Select file to update (Zu aktualisierende Datei &quot; auswählen) Ihre Datei aus.
4. Verwenden Sie hier das Kontextmenü, um Ihren Datei-Explorer zu öffnen und die neuere Version der LOB-App hochzuladen. Stellen Sie sicher, dass Abhängigkeiten nach Bedarf enthalten sind.

Weitere Informationen finden Sie [unter Intune App Deployment for HoloLens](/hololens/app-deploy-intune)

## <a name="development-plan"></a>Entwicklungsplan

Nachdem Ihr Gerät erfolgreich registriert wurde, sind Sie jetzt darauf vorbereitet, weitere BRANCHEN-Apps auf Ihren Geräten bereitzustellen. Für die Dauer dieses Leitfadens verwenden wir eine Beispiel-App, aber es ist wahrscheinlicher, dass Sie benutzerdefinierte Apps verwenden möchten, die für die Anforderungen Ihrer Organisation erstellt wurden.

Wenn Sie bereits über eine BRANCHEN-App verfügen, können Sie Ihre App über [MDM bereitstellen.](/hololens/app-deploy-intune) Wenn Sie eine andere Methode bevorzugen, [](/hololens/app-deploy-overview) lesen Sie die Übersicht über die Anwendungsbereitstellung für HoloLens 2, um weitere Methoden zum Bereitstellen Ihrer LOB-App auf Ihren Geräten zu erfahren.

Wenn Sie noch keine eigene BRANCHEN-App erstellen müssen oder sich noch im Erstellungsprozess befinden, lesen Sie unsere Dokumentation zur Mixed Reality-Entwicklung, um mit dem Entwerfen und Erstellen von Prototypen zu beginnen oder sich mit den grundlegenden Konzepten für den Einstieg in die Mixed Reality-Entwicklung zu [informieren.](/windows/mixed-reality/discover/get-started-with-mr) [](/windows/mixed-reality/design/design)

## <a name="support-plan"></a>Supportplan

Ein Supportplan ist eine hervorragende Möglichkeit. Es ist hilfreich, wenn sie sich mit der Problembehandlung des Registrierungsprozesses auf HoloLens-Geräten und der allgemeinen Verwendung des HoloLens-Geräts in Ihrer Organisation austrainiert haben. Damit Ihre Benutzer ihre Probleme schneller lösen können, empfehlen wir, dass Ihr Eskalationsprozess in ähnlicher Weise wie in dieser Reihenfolge behandelt wird:

1. Ihr Supportdesk.
2. Ihr HoloLens Expert-Team
3. [HoloLens-Dokumentation](/hololens/)  /  [HoloLens Problembehandlung](/hololens/hololens-troubleshooting)
4. [Wenden Sie sich an den Support.](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>-Geräteverwaltung

In diesem Leitfaden wurde die Einrichtung von Mobile Geräteverwaltung (MDM) und deren Verwendung zum Einrichten einiger Gerätekonfigurationen und Zum Anwenden von Einstellungen verwendet, um den Zugriff auf Wi-Fi Zertifikate und Proxys zu ermöglichen. Mdm kann jedoch auch verwendet werden, um Geräteeinschränkungen über CSPs und Richtlinien anzuwenden.

In vielen Fällen können Für Geräte Konnektivitätseinschränkungen gelten, z. B. Bluetooth, VPN, USB oder sogar das Deaktivieren des Zugriffs auf die Kamera oder das Mikrofon. Wenn Sie eines dieser Interessen haben, empfehlen wir Ihnen, unsere allgemeine Seite mit [Geräteeinschränkungen zu lesen.](/hololens/hololens-common-device-restrictions)

Es gibt weitere komplexere Geräteeinschränkungen, die Sie verwenden können. Also beispielsweise:

- Einschränken der Seiten, die in der Einstellungen-App angezeigt werden können, mit [settingsPageVisibility,](/hololens/settings-uri-list)sodass Benutzer nur auf die Einstellungen zugreifen können, die sie anpassen müssen, z. B. das Ändern Wi-Fi Verbindung.
- Verwenden [Sie den Kioskmodus,](/hololens/hololens-kiosk) um die Benutzeroberfläche zu beschränken, die Benutzern auf einem Gerät angezeigt wird. Sie können Kiosks so festlegen, dass eine einzelne App oder mehrere Apps mit einer benutzerdefinierten Startseite angezeigt werden. Kioske können verschiedenen Benutzern auch unterschiedliche Erfahrungen bieten.
- [Windows Application Control (WDAC),](/hololens/windows-defender-application-control-wdac) um zu ermöglichen, dass bestimmte Apps oder Prozesse nicht vollständig gestartet werden.

Wenn Sie mehr über zusätzliche Methoden der Geräteverwaltung oder Geräteeinschränkungen erfahren möchten, führen Sie den nächsten Schritt aus, und lesen Sie unsere Geräteverwaltung [Übersicht.](/hololens/hololens-csp-policy-overview)





