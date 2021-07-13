---
title: Intune und Unternehmensportal
description: Erfahren Sie, wie Sie mit Intune, der Verwaltung mobiler Geräte und dem Unternehmensportal eine komfortable Benutzeroberfläche einrichten, zuweisen und erstellen.
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
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635499"
---
# <a name="intune--company-portal"></a>Intune- und Unternehmensportal

Mit Mobile Geräteverwaltung (MDM) können Sie Ihre eigenen benutzerdefinierten Apps über [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) verwenden, um sie direkt auf Ihren HoloLens Geräten bereitzustellen. Microsoft Intune ist ein cloudbasierter Dienst, der sich auf die Verwaltung mobiler Geräte (MDM, Mobile Device Management) und mobiler Anwendungen (MAM, Mobile Application Management) konzentriert. Intune ist in der [EMS-Suite (Enterprise Mobility + Security)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) von Microsoft enthalten und ermöglicht Ihren Benutzern, produktiv zu sein, während die Daten ihrer Organisation geschützt bleiben. Weitere Informationen zu Intune finden Sie unter [Was ist Intune?.](/mem/intune/fundamentals/what-is-intune)

## <a name="setup"></a>Einrichten

1. Hochladen eine App in eine Branchenanwendung, oder laden Sie eine benutzerdefinierte App in Ihren Intune-Mandanten hoch. Siehe auch: [Enterprise App-Verwaltung.](/windows/client-management/mdm/enterprise-app-management)

2. [Weisen Sie Ihre App einer Gruppe zu.](/mem/intune/apps/apps-deploy) Basierend auf dem von Ihnen ausgewählten Zuweisungstyp kann die App automatisch oder verfügbar bereitgestellt werden, damit sie sofort abgerufen werden kann, wenn Sie über eine Auswahl von Apps verfügen.

> [!NOTE]
> Achten Sie beim Erstellen Ihres AppX-Pakets darauf, dass Sie die Architektur für die Geräte berücksichtigen, auf denen Sie die Bereitstellung durchführen. HoloLens 2 ist ARM64, und HoloLens (1. Generation) ist x86. Sie können beides in ein einzelnes AppX-Paket einschließen, wenn Sie eine Umgebung mit gemischten Geräten planen.

## <a name="assignment-types"></a>Zuweisungstypen

Damit Ihre App nach der Registrierung automatisch auf dem Gerät installiert wird, sollten Sie für diese Gruppe(en) **Erforderlich** auswählen.
Um Ihre App für Geräte, die über das Unternehmensportal registriert sind, zum Download zur Verfügung zu stellen, wählen Sie **Für registrierte Geräte verfügbar** aus.

## <a name="end-user-experience"></a>Endbenutzererfahrung

Nachdem Sie die Konfiguration in Intune eingerichtet haben, können Endbenutzer Ihre ausgewählten Apps empfangen.

Führen Sie die folgenden Schritte aus, um Ihre Apps automatisch abzurufen:

1. Registrieren Sie Ihr Gerät bei Ihrem Mandanten.
2. Nachdem Ihr Gerät die Registrierung abgeschlossen hat, sollten Sie die App auf Ihrem Gerät erhalten.
3. Wenn Ihre App nicht sofort angezeigt wird, wechseln Sie zu **Einstellungen**  >  **Konten**  >  **Arbeits- oder**  >  *Schulkontoinformationen,* und scrollen Sie nach unten, um Informationen zum Status der installierten App anzuzeigen.

So gelangen Sie über die Unternehmensportal zu Apps:

1. Öffnen Sie das **Startmenü,** und wählen Sie **Microsoft Store** aus.
2. Suchen Sie **nach Unternehmensportal,** und laden Sie die App herunter.
3. Melden Sie sich bei Ihrem Konto an.
4. Wählen Sie die App aus, die Sie erhalten möchten, und laden Sie sie herunter.

> [!Tip]
> Erfahren Sie mehr über [die automatische Installation der Unternehmensportal](/mem/intune/apps/company-portal-app) und das Bereitstellen und Verwalten von Apps in [Intune.](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
