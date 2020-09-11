---
title: InTune und Unternehmens Portal
description: InTune, App-Verwaltung, APP, Unternehmensportal, Portal
keywords: InTune, App-Verwaltung, APP, Unternehmensportal, Portal, hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
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
ms.openlocfilehash: 5fc369caa2e5e26c91c07f9270c3984177507dbd
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009463"
---
# Intune und Unternehmensportal

Mit der Verwaltung mobiler Geräte (Mobile Device Management, MDM) können Sie Ihre eigenen benutzerdefinierten Apps über [Microsoft Endpoint Manager (InTune)](https://docs.microsoft.com/intune/windows-holographic-for-business) verwenden, um Sie direkt auf Ihren HoloLens-Geräten bereitzustellen. Microsoft InTune ist ein Cloud-basierter Dienst, der sich auf die Verwaltung mobiler Geräte (Mobile Device Management, MDM) und die Verwaltung mobiler Anwendungen (MAM) konzentriert. InTune ist in der Microsoft[Enterprise Mobility + Security (EMS)-Suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)enthalten und ermöglicht Benutzern, produktiv zu sein und gleichzeitig ihre Organisationsdaten zu schützen. Wenn Sie mehr über InTune erfahren möchten, lesen Sie [Was ist InTune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).

## Setup

1. Laden Sie eine app in eine geschäftszeile hoch, oder laden Sie eine benutzerdefinierte app in ihren InTune-Mandanten hoch. Siehe auch: [Enterprise-App-Verwaltung](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).

2. [Weisen Sie Ihre APP einer Gruppe zu](https://docs.microsoft.com/mem/intune/apps/apps-deploy). Basierend auf dem von Ihnen ausgewählten Zuordnungstyp können Sie die APP automatisch oder verfügbar bereitstellen lassen, wenn Sie eine Auswahl von apps haben. 

> [!NOTE] 
> Achten Sie beim Erstellen Ihres AppX-Pakets darauf, dass Sie die Architektur für die Geräte berücksichtigen, auf die Sie bereitstellen. HoloLens 2 ist ARM64, und HoloLens (1st Generation) ist x86. Sie können beide in ein einzelnes AppX-Bundle einbeziehen, wenn Sie eine Umgebung mit gemischten Geräten planen.

## Zuordnungstypen

Wenn Sie möchten, dass Ihre APP nach der Registrierung automatisch auf dem Gerät installiert wird, sollten Sie für diese Gruppe (n) **erforderlich** auswählen.
Wenn Sie Ihre APP für die über das Unternehmensportal registrierten Personen herunterladen möchten, wählen Sie **für eingeschriebene Geräte verfügbar**aus.


## Endbenutzererfahrung

Nachdem Sie die Konfiguration auf InTune eingerichtet haben, sind Sie bereit, damit Endbenutzer Ihre ausgewählten apps empfangen können.

Führen Sie die folgenden Schritte aus, um Ihre APP (s) automatisch abzurufen:
1. Registrieren Sie Ihr Gerät für Ihren Mandanten. 
2. Sobald Ihr Gerät die Registrierung abgeschlossen hat, sollten Sie die APP auf Ihrem Gerät empfangen. 
3. Wenn Sie die APP nicht sofort sehen, wechseln Sie zu **Einstellungen**  >  **Firmen**  >  **Arbeit oder Schule**  >  **YourAccount** Informationen, und Scrollen Sie nach unten, um Informationen zum installierten App-Status anzuzeigen.

So gelangen Sie zu Apps über das Unternehmens Portal:
1. Öffnen Sie das **Startmenü** , und wählen Sie **Microsoft Store**aus. 
2. Suchen Sie nach **Unternehmens Portal** , und laden Sie die APP herunter.
3. Bei Ihrem Konto anmelden.
4. Wählen Sie die APP aus, die Sie erhalten möchten, und laden Sie Sie herunter.

> [!Tip]
> Weitere Informationen finden Sie [unter Automatisches Installieren des Unternehmensportals](https://docs.microsoft.com/mem/intune/apps/company-portal-app) und [bereitstellen und Verwalten von apps in InTune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).
