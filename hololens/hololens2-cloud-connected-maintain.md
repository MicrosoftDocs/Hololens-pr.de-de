---
title: Bereitstellungshandbuch – Cloud connected HoloLens 2 deployment at scale with Remote Assist – Maintain
description: Bleiben Sie mit unseren Tipps zum Warten und Unterstützen von HoloLens-Geräten über ein cloudbasiertes Netzwerk auf dem laufenden.
keywords: HoloLens, Verwaltung, cloudgebunden, Remote Assist, AAD, Azure AD, MDM, Mobile Geräteverwaltung
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309787"
---
# <a name="maintain---cloud-connected-guide"></a>Verwalten – Leitfaden für cloudverknete Clouds

## <a name="updates"></a>Aktualisierungen

Microsoft hat Windows Update for Business entwickelt, um IT-Administratoren weitere Verwaltungsfunktionen rund um Windows Update bereitzustellen, wie beispielsweise die Möglichkeit, Updates für Gruppen von Geräten bereitzustellen oder Wartungszeitfenster für die Installation von Updates festzulegen.

Erfahren Sie, wie [Sie HoloLens-Updates](https://docs.microsoft.com/hololens/hololens-updates) verwalten, einschließlich geplanter Tage, geplanter Zeit und Festlegen der aktiven Stunden auf dem Gerät, damit es außerhalb der Arbeitszeit aktualisiert wird.

Remote Assist ist eine In-Box-App und kann über die Microsoft Store werden. Für alle Apps, die über den Microsoft Store heruntergeladen werden, können sie manuell über die Microsoft Store [App](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) selbst aktualisiert werden.

## <a name="support-plan"></a>Supportplan

Ein Supportplan ist eine hervorragende Möglichkeit. Es ist nützlich, dass jemand oder eine Gruppe sich mit der Problembehandlung des Registrierungsprozesses auf HoloLens-Geräten und auch mit der allgemeinen Verwendung des HoloLens-Geräts in Ihrer Organisation austrainiert hat. Damit Ihre Benutzer ihre Probleme schneller lösen können, empfehlen wir, dass Ihr Eskalationsprozess in ähnlicher Weise wie in dieser Reihenfolge behandelt wird:

1. Ihr Supportdesk.
2. Ihr HoloLens Expert-Team
3. [HoloLens-Dokumentation](https://docs.microsoft.com/hololens/)  /  [HoloLens-Dokumentation zur Problembehandlung](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Wenden Sie sich an den Support.](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Entwicklungsplan

Nachdem Ihr Gerät erfolgreich registriert wurde, sind Sie jetzt darauf vorbereitet, Branchen-Apps (LOB-Apps) auf Ihren Geräten bereitzustellen. Hierbei handelt es sich um benutzerdefinierte Apps, die für ihre Organisation&#39;anforderungen erstellt wurden.

Wenn Sie bereits über eine Line-of-Business-App verfügen,&#39;bereit, Ihre App über [MDM bereitzustellen.](https://docs.microsoft.com/hololens/app-deploy-intune) Wenn Sie&#39;eine andere Methode bevorzugen, [](https://docs.microsoft.com/hololens/app-deploy-overview) lesen Sie die Übersicht über die Anwendungsbereitstellung für HoloLens 2, um weitere Methoden zum Bereitstellen Ihrer BRANCHEN-App auf Ihren Geräten zu erfahren.

Wenn Sie&#39;ihre eigene BRANCHEN-App erstellt haben oder sich noch in der Erstellung befinden, [](https://docs.microsoft.com/windows/mixed-reality/design/design) lesen Sie unsere Dokumentation zur Mixed Reality-Entwicklung, um mit dem Entwerfen und Erstellen von Prototypen zu beginnen oder sich mit den grundlegenden Konzepten für den Einstieg in die Mixed Reality-Entwicklung zu [informieren.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>-Geräteverwaltung 

In diesem Leitfaden wurde zwar das Einrichten von Mobile Geräteverwaltung (MDM) erläutert, es wurde jedoch nicht verwendet, um Geräteeinschränkungen anzuwenden, oder Richtlinien wurden auf Geräte angewendet. Die Geräteverwaltung kann verwendet werden, um den Zugriff durch Pushen von Zertifikaten zuzulassen oder den Zugriff mit einer Vielzahl von Geräteeinschränkungen einzuschränken. 

In vielen Fällen können für Geräte Konnektivitätseinschränkungen wie Bluetooth, VPN, USB oder sogar das Ausschalten des Zugriffs auf die Kamera oder das Mikrofon gelten. Wenn Sie eines dieser Interessen haben, empfehlen wir Ihnen, unsere Seite mit [allgemeinen Geräteeinschränkungen](hololens-common-device-restrictions.md)zu lesen.

Es gibt weitere komplexere Geräteeinschränkungen, die Sie verwenden können. Also beispielsweise:

- Einschränken der Seiten, die in der Einstellungs-App mithilfe von [SettingsPageVisibility](settings-uri-list.md)angezeigt werden können, sodass Benutzer nur auf die Einstellungen zugreifen können, die sie anpassen müssen, z. B. das Ändern ihrer Wi-Fi Verbindung.
- Verwenden Sie den [Kioskmodus,](hololens-kiosk.md) um die Benutzeroberfläche einzuschränken, die Benutzern auf einem Gerät angezeigt wird. Sie können Kiosks so festlegen, dass eine einzelne App oder mehrere Apps mit einer benutzerdefinierten Startseite angezeigt werden. Kiosks können verschiedenen Benutzern auch unterschiedliche Benutzererlebnisse bieten.  
- [Windows-Anwendungssteuerung (Windows Application Control, WDAC),](windows-defender-application-control-wdac.md) damit bestimmte Apps oder Prozesse nicht vollständig gestartet werden.

Wenn Sie mehr über verschiedene Methoden der Geräteverwaltung oder Geräteeinschränkungen erfahren möchten, fahren Sie mit dem nächsten Schritt fort, und lesen Sie unsere Geräteverwaltung Übersicht.

## <a name="next-step"></a>Nächster Schritt

> [!div class="nextstepaction"]
> [Lesen Sie die CSPs und Geräteverwaltung Overview (Übersicht über CSPs und Geräteverwaltung).](hololens-csp-policy-overview.md)