---
title: Bereitstellungshandbuch – Unternehmens verbundene HoloLens 2 mit Dynamics 365 Guides – Übersicht
description: Erfahren Sie, wie Sie HoloLens 2 Geräte mit Dynamics 365 Guides über ein verbundenes Unternehmensnetzwerk registrieren.
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
ms.openlocfilehash: 541c1080d7f5fe9491d6cb11179ea98b160f687c
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032690"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Bereitstellungshandbuch – Unternehmens verbundene HoloLens 2 mit Dynamics 365 Guides – Übersicht

Dieser Leitfaden hilft IT-Experten bei der Planung und Bereitstellung Microsoft HoloLens 2-Geräte mit Dynamics 365 Guides (Leitfäden) in ihrer Organisation. Dieser Leitfaden ist ideal für Pilot- und Produktionsbereitstellungen und ähnelt dem Leitfaden Szenario [B: Bereitstellen](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) innerhalb des Netzwerkleitfadens Ihrer Organisation. Nachdem Sie Ihren Proof of Concept getestet haben, verwenden Sie diesen Leitfaden, um die Integration HoloLens in Ihre Organisation voranzutreiben.

In diesem Leitfaden erfahren Sie, wie Sie Ihre Geräte bei Ihrer vorhandenen Geräteverwaltung registrieren, Lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer ein Dynamics 365-Handbuch betreiben und nach der Einrichtung des Geräts benutzerdefinierte Line-of-Business-Apps verwenden können. 

## <a name="prerequisites"></a>Voraussetzungen

Die folgende Infrastruktur sollte bereits vorhanden sein:
- WLAN
    - Internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen und eingeschränktem Zugriff auf das Internet oder Clouddienste
    - Gerätebasierte Zertifikatauthentifizierung.
- Azure Active Directory (Azure AD) Join mit automatischer MDM-Registrierung ([Azure AD P1-Abonnement](/azure/active-directory/fundamentals/active-directory-whatis) erforderlich)
- MDM (Intune) Verwaltet
    - Mindestens eine Anwendung wird über MDM bereitgestellt.
- Netzwerk 
    - Zertifikate (SCEP oder PKCS)
    - Proxykonfiguration
- Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)
    - Einzelne oder mehrere Benutzer pro Gerät werden unterstützt.
- Verschiedene Ebenen von Gerätesperrungskonfigurationen, die basierend auf bestimmten Anwendungsfällen angewendet werden, von Vollständig geöffnet bis Kiosk für einzelne Apps.

## <a name="guides-licensing-and-requirements"></a>[Anleitungen für Lizenzierung und Anforderungen](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- Azure AD-Konto
- Dynamics 365 Guides-PC und -HoloLens
- Dynamics 365 Guides-Abonnement
    - Microsoft Dataverse (enthalten)
    - Power Apps (enthalten)
- Power BI Desktop
- Netzwerkverbindung

[![Diagramm des verbundenen Unternehmensnetzwerks, Phase 1. ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagramm des verbundenen Unternehmensnetzwerks, Phase 2. ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>In dieser Anleitung lernen Sie Folgendes:
### <a name="prepare"></a>Vorbereiten
> [!div class="checklist"]
>- [Erfahren Sie mehr über die Infrastruktur essentials für HoloLens 2 Geräte.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Erfahren Sie mehr über Azure AD und richten Sie eins ein, wenn Sie es nicht haben.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Erfahren Sie mehr über die Identitätsverwaltung und die optimale Einrichtung Azure AD Konten.](hololens2-corp-connected-prepare.md#identity-management)
>- [Erfahren Sie mehr über MDM, und richten Sie Intune ein, wenn Sie noch keines haben.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Machen Sie sich mit zertifikatbasiertem WLAN vertraut.](hololens2-corp-connected-prepare.md#certificates)
>- [Machen Sie sich mit Proxy vertraut.](hololens2-corp-connected-prepare.md#proxy)
>- [Erfahren Sie, wie Sie Line of Business-Apps verwenden können.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [Erfahren Sie mehr über die Verwendung von Leitfäden für Ihre Organisation.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Konfigurieren
> [!div class="checklist"]
>- [Erstellen von Benutzern und Gruppen.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Einrichten der automatischen Registrierung.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Hier erfahren Sie, wie Sie Wi-Fi Zertifikate und Profile für die Konnektivität Wi-Fi Unternehmensnetzwerks einrichten.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Hochladen und Zuweisen von Lob-App-Paketen (Line of Business).](hololens2-corp-connected-configure.md#app-deployment)
>- [Setup Dynamics 365 Guides.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Konfigurieren des Kioskmodus (optional).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [Konfigurieren von WDAC (optional).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Bereitstellen
> [!div class="checklist"]
>-  [Überprüfen Sie die Registrierung über das Gerät und MDM.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Überprüfen Wi-Fi Zertifikate.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Überprüfen Sie die Installation der BRANCHEN-App.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Überprüfen Sie Leitfäden über Erstellung und Betrieb.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Verwalten
> [!div class="checklist"]
>- [Aktualisieren HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Aktualisieren von Leitfäden (Store-Apps)](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [Aktualisieren von BRANCHEN-Apps.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Entwicklungsplan.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Erstellen eines Supportplans.](hololens2-corp-connected-maintain.md#support-plan)
>- [Geräteverwaltungsoptionen.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Nächster Schritt 
> [!div class="nextstepaction"]
> [Bereitstellung im verbundenen Unternehmen – Vorbereiten](hololens2-corp-connected-prepare.md)
