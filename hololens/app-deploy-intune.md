---
title: Intune und Unternehmensportal
description: Erfahren Sie, wie Sie eine komfortable Benutzeroberfläche mit Intune, der Verwaltung mobiler Geräte und dem Unternehmensportal einrichten, zuweisen und erstellen.
keywords: Intune, App-Verwaltung, App, Unternehmensportal, Portal, HoloLens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309728"
---
# <a name="intune--company-portal"></a>Intune & Unternehmensportal

Mit Mobile Geräteverwaltung (MDM) können Sie Ihre eigenen benutzerdefinierten Apps über [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) verwenden, um sie direkt auf Ihren HoloLens-Geräten bereitzustellen. Microsoft Intune ist ein cloudbasierter Dienst, der sich auf die Verwaltung mobiler Geräte (MDM, Mobile Device Management) und mobiler Anwendungen (MAM, Mobile Application Management) konzentriert. Intune ist in der [EMS-Suite (Enterprise Mobility + Security)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) von Microsoft enthalten und ermöglicht Ihren Benutzern, produktiv zu sein, während die Daten ihrer Organisation geschützt bleiben. Weitere Informationen zu Intune finden Sie unter [Was ist Intune?.](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

## <a name="setup"></a>Setup

1. Laden Sie eine App in einen Line of Business-Dienst hoch, oder laden Sie eine benutzerdefinierte App in Ihren Intune-Mandanten hoch. Siehe auch: [Unternehmens-App-Verwaltung](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).

2. [Weisen Sie Ihre App einer Gruppe zu.](https://docs.microsoft.com/mem/intune/apps/apps-deploy) Basierend auf dem von Ihnen ausgewählten Zuweisungstyp kann die App automatisch übermittelt werden oder verfügbar sein, damit sie sofort heruntergefahren werden kann, wenn Sie über eine Auswahl von Apps verfügen.

> [!NOTE]
> Achten Sie beim Erstellen Ihres AppX-Pakets darauf, dass Sie die Architektur für die Geräte, auf denen Sie bereitstellen, berücksichtigen. HoloLens 2 arm64 und HoloLens (1. Generation) ist x86. Sie können beides in ein einzelnes AppX-Paket einbetten, wenn Sie eine Umgebung für gemischte Geräte planen.

## <a name="assignment-types"></a>Zuweisungstypen

Damit Ihre App nach der Registrierung automatisch auf dem Gerät installiert wird, sollten Sie **Für** diese Gruppe(n) erforderlich auswählen.
Wählen Sie Verfügbar für registrierte Geräte aus, um Ihre App für Geräte verfügbar zu machen, die über das Unternehmensportal **registriert sind.**

## <a name="end-user-experience"></a>Endbenutzererfahrung

Nachdem Sie die Konfiguration in Intune eingerichtet haben, können Endbenutzer Ihre ausgewählten Apps erhalten.

Führen Sie die folgenden Schritte aus, um Ihre Apps automatisch zu erhalten:

1. Registrieren Sie Ihr Gerät bei Ihrem Mandanten.
2. Nachdem die Registrierung Ihres Geräts abgeschlossen ist, sollten Sie die App auf Ihrem Gerät erhalten.
3. Wenn Sie Ihre App nicht sofort sehen, wechseln Sie zu Einstellungen Konten Arbeits- oder SchulkontoInformationen, und scrollen Sie nach unten, um Informationen zum Status der  >    >    >   installierten App anzuzeigen.

So gelangen Sie über die Unternehmensportal zu Apps:

1. Öffnen Sie das **Startmenü,** und wählen Sie **Microsoft Store** aus.
2. Suchen Sie **nach Unternehmensportal,** und laden Sie die App herunter.
3. Melden Sie sich bei Ihrem Konto an.
4. Wählen Sie die App aus, die Sie erhalten möchten, und laden Sie sie herunter.

> [!Tip]
> Erfahren Sie mehr über [die automatische Installation der Unternehmensportal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) und das Bereitstellen und Verwalten von Apps in [Intune.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
