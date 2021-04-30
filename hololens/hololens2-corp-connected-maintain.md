---
title: Bereitstellungshandbuch – Unternehmens verbundene HoloLens 2 mit Dynamics 365-Handbüchern – Verwalten
description: Erfahren Sie, wie Sie HoloLens 2 über ein verbundenes Unternehmensnetzwerk mit Dynamics 365-Leitfäden verwalten.
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
ms.openlocfilehash: f231e65e17ab053e34e7174e1ed7ff6e7a0a56b8
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308802"
---
# <a name="maintain---corporate-connected-guide"></a>Verwalten – Leitfaden für verbundene Unternehmen

## <a name="update-hololens"></a>Aktualisieren von HoloLens

Microsoft hat Windows Update for Business entwickelt, um IT-Administratoren weitere Verwaltungsfunktionen rund um Windows Update bereitzustellen, wie beispielsweise die Möglichkeit, Updates für Gruppen von Geräten bereitzustellen oder Wartungszeitfenster für die Installation von Updates festzulegen.

Eine beliebte Methode zum Verwalten von Updates besteht in einer Feature-Verzögerung von 30 Tagen. Auf diese Weise können Administratoren neue Features aktualisieren und eine Vorschau anzeigen. So können sie aus erster Hand Wissen sammeln und Ihren Supportdesk über neue Änderungen informieren.

Erfahren Sie, [wie Sie HoloLens-Updates](https://docs.microsoft.com/hololens/hololens-updates)verwalten, einschließlich geplanter Tage, geplanter Zeit und Festlegen der aktiven Stunden auf dem Gerät, damit es außerhalb der Arbeitszeit aktualisiert wird.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Aktualisieren von Dynamics 365-Handbüchern (und anderen Store-Apps)

Dynamics 365 Guides ist eine In-Box-App und kann über die app Microsoft Store werden. Für alle Apps, die über die Microsoft Store heruntergeladen werden, können sie manuell über die Microsoft Store [App](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) selbst aktualisiert werden.

## <a name="how-to-update-lob-apps"></a>Aktualisieren von BRANCHEN-Apps

Branchenanwendungen können auf die gleiche Weise aktualisiert werden, wie sie intune hinzugefügt wurden. Apps können in Intune aktualisiert werden, indem die neue App mit einer höheren Versionsnummer in die vorhandene App-Konfiguration hochgeladen wird. Wenn das Gerät mit Intune synchronisiert wird, wird beobachtet, dass es eine neuere App-Version gibt, und die neuere App wird heruntergeladen und ersetzt die alte App.

1. Um die neuere App hochzuladen, navigieren Sie zum [](https://endpoint.microsoft.com/#home)  ->  **MEM-Portal Apps** -> Alle Apps   ->  *TheNameOfYourApp-Eigenschaften.*  ->  
2. Wählen Sie neben App-Informationen die Option **Bearbeiten aus.**
3. Wählen Sie für den Wert &quot; Select file to update (Zu aktualisierende Datei &quot; auswählen) Ihre Datei aus.
4. Verwenden Sie hier das Kontextmenü, um Ihren Datei-Explorer zu öffnen und die neuere Version der LOB-App hochzuladen. Stellen Sie sicher, dass Abhängigkeiten nach Bedarf enthalten sind.

Weitere Informationen finden Sie unter [Intune-App-Bereitstellung für HoloLens.](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="development-plan"></a>Entwicklungsplan

Nachdem Ihr Gerät erfolgreich registriert wurde, sind Sie nun darauf vorbereitet, weitere BRANCHEN-Apps auf Ihren Geräten bereitzustellen. Für die Dauer dieses Leitfadens verwenden wir eine Beispiel-App, aber es ist wahrscheinlicher, dass Sie benutzerdefinierte Apps verwenden möchten, die für die Anforderungen Ihrer Organisation erstellt wurden.

Wenn Sie bereits über eine branchenspezifische App verfügen, können Sie [Ihre App über MDM bereitstellen.](https://docs.microsoft.com/hololens/app-deploy-intune) Wenn Sie eine andere Methode bevorzugen, lesen Sie die Übersicht über die [Anwendungsbereitstellung für HoloLens 2,](https://docs.microsoft.com/hololens/app-deploy-overview) um weitere Methoden zum Bereitstellen Ihrer BRANCHEN-App auf Ihren Geräten zu erfahren.

Wenn Sie noch keine eigene BRANCHEN-App erstellen müssen oder sich noch in der Erstellung befinden, lesen Sie unsere Mixed Reality-Entwicklungsdokumente, um mit dem Entwerfen und Erstellen von Prototypen zu [beginnen,](https://docs.microsoft.com/windows/mixed-reality/design/design) oder lernen Sie die grundlegenden Konzepte für den Einstieg in die [Mixed Reality-Entwicklung kennen.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Supportplan

Ein Supportplan ist eine hervorragende Möglichkeit. Es ist hilfreich, jemanden oder eine Gruppe mit der Problembehandlung des Registrierungsprozesses auf HoloLens-Geräten und der allgemeinen Verwendung des HoloLens-Geräts in Ihrer Organisation zu trainieren. Damit Ihre Benutzer ihre Probleme schneller lösen können, wird empfohlen, dass Ihr Eskalationsprozess in ähnlicher Weise wie die folgende Reihenfolge behandelt wird:

1. Ihr Support-Desk.
2. Ihr HoloLens Expert-Team
3. [HoloLens-Dokumentation](https://docs.microsoft.com/hololens/)  /  [HoloLens-Dokumentation zur Problembehandlung](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Wenden Sie sich an den Support.](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>-Geräteverwaltung

In diesem Leitfaden wurde das Einrichten von Mobile Geräteverwaltung (MDM) erläutert, und es wurden einige Gerätekonfigurationen eingerichtet und Einstellungen angewendet, um den Zugriff in Bezug auf Wi-Fi Zertifikate und Proxys zuzulassen. Mdm kann jedoch auch verwendet werden, um Geräteeinschränkungen über CSPs und Richtlinien anzuwenden.

In vielen Fällen können Für Geräte Konnektivitätseinschränkungen gelten, z. B. Bluetooth, VPN, USB oder sogar das Ausschalten des Zugriffs auf die Kamera oder das Mikrofon. Wenn Sie eines dieser Interessen haben, empfehlen wir Ihnen, unsere [Seite mit allgemeinen Geräteeinschränkungen](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)zu lesen.

Es gibt weitere komplexere Geräteeinschränkungen, die Sie verwenden können. Also beispielsweise:

- Einschränken der Seiten, die in der App Einstellungen angezeigt werden können, mithilfe von [SettingsPageVisibility,](https://docs.microsoft.com/hololens/settings-uri-list)sodass Benutzer nur auf die Einstellungen zugreifen können, die sie anpassen müssen, z. B. das Ändern Wi-Fi Verbindung.
- Verwenden [Sie den Kioskmodus,](https://docs.microsoft.com/hololens/hololens-kiosk) um die Benutzeroberfläche zu beschränken, die Benutzern auf einem Gerät angezeigt wird. Sie können Kiosks so festlegen, dass eine einzelne App oder mehrere Apps mit einer benutzerdefinierten Startseite angezeigt werden. Kioske können verschiedenen Benutzern auch unterschiedliche Erfahrungen bieten.
- [Windows-Anwendungssteuerung (Windows Application Control, WDAC),](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) damit bestimmte Apps oder Prozesse nicht vollständig gestartet werden können.

Wenn Sie mehr über zusätzliche Methoden der Geräteverwaltung oder Geräteeinschränkungen erfahren möchten, führen Sie den nächsten Schritt aus, und lesen Sie unsere Geräteverwaltung [Übersicht.](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)





