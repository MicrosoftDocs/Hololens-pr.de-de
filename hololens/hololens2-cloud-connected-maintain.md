---
title: 'Bereitstellungshandbuch : Bereitstellung mit Cloudverbindung HoloLens 2 im großen Stil mit Remote Assist – Verwalten'
description: Bleiben Sie mit unseren Tipps zur Wartung und Unterstützung von HoloLens Geräten über ein mit der Cloud verbundenes Netzwerk auf dem laufenden.
keywords: HoloLens, Verwaltung, cloudverbunden, Remote Assist, AAD, Azure AD, MDM, Mobile Geräteverwaltung
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
ms.openlocfilehash: 879f89d84bbae5b4cc187bc8b1fca627036269145b1c2dd82787e3789fef259d
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660376"
---
# <a name="maintain---cloud-connected-guide"></a>Verwalten – Leitfaden für cloudverknannte Verbindungen

## <a name="updates"></a>Aktualisierungen

Microsoft hat Windows Update for Business entwickelt, um IT-Administratoren weitere Verwaltungsfunktionen rund um Windows Update bereitzustellen, wie beispielsweise die Möglichkeit, Updates für Gruppen von Geräten bereitzustellen oder Wartungszeitfenster für die Installation von Updates festzulegen.

Erfahren Sie, wie Sie [HoloLens Updates verwalten,](/hololens/hololens-updates) einschließlich geplanter Tage, geplanter Zeit und Festlegen der aktiven Stunden auf dem Gerät, damit es außerhalb der Arbeitszeit aktualisiert wird.

Remote Assist ist eine In-Box-App und kann über die Microsoft Store-App aktualisiert werden. Für alle Apps, die über die Microsoft Store heruntergeladen werden, können sie [manuell über die Microsoft Store](/hololens/holographic-store-apps#update-apps) App selbst aktualisiert werden.

## <a name="support-plan"></a>Supportplan

Ein Supportplan ist eine hervorragende Möglichkeit. Es ist hilfreich, jemanden oder eine Gruppe mit der Problembehandlung des Registrierungsprozesses auf HoloLens Geräten und der allgemeinen Verwendung des HoloLens Geräts in Ihrer Organisation zu trainieren. Damit Ihre Benutzer ihre Probleme schneller lösen können, wird empfohlen, dass Ihr Eskalationsprozess in ähnlicher Weise wie die folgende Reihenfolge behandelt wird:

1. Ihr Support-Desk.
2. Ihr HoloLens Expert-Team
3. [HoloLens-Dokumentation](/hololens/)  /  [HoloLens-Dokumentation zur Problembehandlung](/hololens/hololens-troubleshooting)
4. [Wenden Sie sich an den Support.](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Entwicklungsplan

Nachdem Ihr Gerät erfolgreich registriert wurde, können Sie branchenspezifische Apps (LOB-Apps) auf Ihren Geräten bereitstellen. Dies sind benutzerdefinierte Apps, die für Ihre Organisation&#39;Anforderungen erstellt wurden.

Wenn Sie bereits über eine Branchen-App verfügen,&#39;Sie bereit sein, [Ihre App über MDM bereitzustellen.](/hololens/app-deploy-intune) Wenn Sie eine andere Methode bevorzugen&#39;, lesen Sie die Übersicht über die [Anwendungsbereitstellung für HoloLens 2,](/hololens/app-deploy-overview) um weitere Methoden zum Bereitstellen Ihrer BRANCHEN-App auf Ihren Geräten zu erfahren.

Wenn Sie&#39;ihre eigene BRANCHEN-App noch nicht erstellt haben oder sich noch in der Erstellung befinden, lesen Sie unsere Mixed Reality-Entwicklungsdokumente, um mit dem Entwerfen und Erstellen von Prototypen zu [beginnen,](/windows/mixed-reality/design/design) oder lernen Sie die grundlegenden Konzepte für den Einstieg in die [Mixed Reality-Entwicklung kennen.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>-Geräteverwaltung 

In diesem Leitfaden wurde zwar das Einrichten von Mobile Geräteverwaltung (MDM) erläutert, es wurde jedoch nicht verwendet, um Geräteeinschränkungen anzuwenden, oder Richtlinien wurden auf Geräte angewendet. Die Geräteverwaltung kann verwendet werden, um den Zugriff durch Pushen von Zertifikaten zuzulassen oder den Zugriff mit einer Vielzahl von Geräteeinschränkungen einzuschränken. 

In vielen Fällen können Geräte Konnektivitätseinschränkungen aufweisen, z. B. Bluetooth, VPN, USB oder sogar den Zugriff auf die Kamera oder das Mikrofon deaktivieren. Wenn Sie eines dieser Interessen haben, empfehlen wir Ihnen, unsere Seite mit [allgemeinen Geräteeinschränkungen](hololens-common-device-restrictions.md)zu lesen.

Es gibt weitere komplexere Geräteeinschränkungen, die Sie verwenden können. Also beispielsweise:

- Einschränken der Seiten, die in der Einstellungen-App angezeigt werden können, indem [SettingsPageVisibility](settings-uri-list.md)verwendet wird, sodass Benutzer nur auf die Einstellungen zugreifen können, die sie anpassen müssen, z. B. das Ändern ihrer Wi-Fi Verbindung.
- Verwenden Sie den [Kioskmodus,](hololens-kiosk.md) um die Benutzeroberfläche einzuschränken, die Benutzern auf einem Gerät angezeigt wird. Sie können Kiosks so festlegen, dass eine einzelne App oder mehrere Apps mit einer benutzerdefinierten Startseite angezeigt werden. Kiosks können verschiedenen Benutzern auch unterschiedliche Benutzererlebnisse bieten.  
- [Windows Anwendungssteuerung (Application Control, WDAC),](windows-defender-application-control-wdac.md) damit bestimmte Apps oder Prozesse nicht vollständig gestartet werden.

Wenn Sie mehr über verschiedene Methoden der Geräteverwaltung oder Geräteeinschränkungen erfahren möchten, fahren Sie mit dem nächsten Schritt fort, und lesen Sie unsere Geräteverwaltung Übersicht.

## <a name="next-step"></a>Nächster Schritt

> [!div class="nextstepaction"]
> [Lesen Sie die CSPs und Geräteverwaltung Overview (Übersicht über CSPs und Geräteverwaltung).](hololens-csp-policy-overview.md)