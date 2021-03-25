---
title: Bereitstellungshandbuch – Unternehmensverknte HoloLens 2 mit Dynamics 365-Anleitungen – Übersicht
description: Erfahren Sie, wie Sie HoloLens 2-Geräte mit Dynamics 365-Anleitungen über ein verbundenes Unternehmensnetzwerk registrieren.
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
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448557"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Bereitstellungshandbuch – Unternehmensverknnnte HoloLens 2 mit Dynamics 365-Anleitungen – Übersicht

Dieses Handbuch hilft IT-Experten bei der Planung und Bereitstellung von Microsoft HoloLens 2-Geräten mit Dynamics 365 Guides (Guides) in ihrer Organisation. Dieses Handbuch ist ideal für Piloten und Produktionsbereitstellungen und ähnelt dem [Szenario B: Bereitstellen](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) innerhalb des Netzwerkhandbuchs Ihrer Organisation. Nach dem Testen Ihres Proof-of-Concept verwenden Sie dieses Handbuch, um mit der Integration von HoloLens in Ihre Organisation voran zu gehen.

In diesem Handbuch wird beschrieben, wie Sie Ihre Geräte bei Ihrer vorhandenen Geräteverwaltung registrieren, Lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer in der Lage sind, einen Dynamics 365-Leitfaden zu betreiben, sowie benutzerdefinierte Unternehmens-Apps nach der Geräteeinrichtung zu verwenden. 

## <a name="prerequisites"></a>Voraussetzungen

Die folgende Infrastruktur sollte bereits vorhanden sein:
- WLAN
    - Internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen und eingeschränktem Zugriff auf das Internet oder Clouddienste
    - Gerätebasierte Zertifikatauthentifizierung.
- Azure Active Directory (Azure AD)-Beitritt mit automatischer MDM-Registrierung ([Azure AD P1-Abonnement](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) erforderlich)
- Verwaltetes MDM (Intune)
    - Mindestens eine Anwendung wird über MDM bereitgestellt.
- Network 
    - Zertifikate (SCEP oder PKCS)
    - Proxykonfiguration
- Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)
    - Einzelne oder mehrere Benutzer pro Gerät werden unterstützt.
- Unterschiedliche Stufen von Gerätesperrungskonfigurationen, die basierend auf bestimmten Anwendungsfällen angewendet werden, von Fully Open bis Single App Kiosk.

## [<a name="guides-licensing-and-requirements"></a>Anleitungen für Lizenzierung und Anforderungen](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- Azure AD-Konto
- Dynamics 365 Führt Anwendungen PC und HoloLens
- Dynamics 365 Guides-Abonnement
    - Microsoft Dataverse (enthalten)
    - Power Apps (im Lieferumfang enthalten)
- Power BI Desktop
- Netzwerkkonnektivität

![Verbundenes Netzwerkdiagramm der Corp](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a>Phasen der Bereitstellung
### <a name="prepare"></a>Vorbereiten
> [!div class="checklist"]
>- [Erfahren Sie mehr über die grundlegenden Infrastruktur für HoloLens 2-Geräte.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Erfahren Sie mehr über Azure AD, und richten Sie eins ein, wenn Sie es nicht haben.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Erfahren Sie mehr über die Identitätsverwaltung und die optimale Einrichtung von Azure AD-Konten.](hololens2-corp-connected-prepare.md#identity-management)
>- [Erfahren Sie mehr über MDM und richten Sie intune ein, wenn Sie noch nicht bereit sind.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Machen Sie sich mit zertifikatbasiertem WLAN vertraut.](hololens2-corp-connected-prepare.md#certificates)
>- [Machen Sie sich mit Proxy vertraut.](hololens2-corp-connected-prepare.md#proxy)
>- [Erfahren Sie, wie Sie Line of Business Apps verwenden können.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [Erfahren Sie mehr über die Verwendung von Handbüchern für Ihre Organisation.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Konfigurieren
> [!div class="checklist"]
>- [Erstellen von Benutzern und Gruppen.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Einrichten der automatischen Registrierung.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Einrichten von Zertifikaten Wi-Fi Profilen für unternehmensWi-Fi Konnektivität.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Hochladen und Zuweisen von Branchen-App-Paketen.](hololens2-corp-connected-configure.md#app-deployment)
>- [Setup Dynamics 365 Guides.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Konfigurieren des Kioskmodus (optional).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [Konfigurieren von WDAC (optional).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Bereitstellen
> [!div class="checklist"]
>-  [Überprüfen der Registrierung über Gerät und MDM.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Überprüfen Wi-Fi Zertifikate.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Überprüfen der Branchen-App-Installation.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Überprüfen von Handbüchern über Die Erstellung und den Betrieb.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Warten
> [!div class="checklist"]
>- [Aktualisieren Sie HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Aktualisieren von Handbüchern (Store-Apps).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [Aktualisieren von Branchen-Apps.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Entwicklungsplan.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Erstellen eines Supportplans](hololens2-corp-connected-maintain.md#support-plan)
>- [Geräteverwaltungsoptionen.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Nächster Schritt 
> [!div class="nextstepaction"]
> [Unternehmensverkn nnte Bereitstellung – Vorbereiten](hololens2-corp-connected-prepare.md)
