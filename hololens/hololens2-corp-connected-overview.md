---
title: Bereitstellungshandbuch – Unternehmensverknannte HoloLens 2 mit Dynamics 365 Guides – Übersicht
description: Erfahren Sie, wie Sie HoloLens 2 Geräte mit Dynamics 365 Guides über ein verbundenes Unternehmensnetzwerk registrieren.
keywords: HoloLens, Verwaltung, unternehmensverbunden, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Geräteverwaltung
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
ms.openlocfilehash: f2f7e1425a208e1f466d995f66118b7e68984242
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637012"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Bereitstellungshandbuch – Unternehmensverknannte HoloLens 2 mit Dynamics 365 Guides – Übersicht

Dieser Leitfaden unterstützt IT-Experten bei der Planung und Bereitstellung von Microsoft HoloLens 2-Geräten mit Dynamics 365 Guides (Handbüchern) für ihre Organisation. Dieser Leitfaden eignet sich hervorragend für Pilot- und Produktionsbereitstellungen und ähnelt dem [Leitfaden Szenario B: Bereitstellen innerhalb des Netzwerks Ihrer Organisation.](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) Nachdem Sie Ihren Proof of Concept getestet haben, verwenden Sie diesen Leitfaden, um mit der Integration von HoloLens in Ihre Organisation fortzugehen.

In diesem Leitfaden erfahren Sie, wie Sie Ihre Geräte bei Ihrer vorhandenen Geräteverwaltung registrieren, Lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer nach der Geräteeinrichtung einen Dynamics 365-Leitfaden betreiben und benutzerdefinierte Branchen-Apps verwenden können. 

## <a name="prerequisites"></a>Voraussetzungen

Die folgende Infrastruktur sollte bereits vorhanden sein:
- WLAN
    - Internes Unternehmensnetzwerk mit Zugriff auf interne Ressourcen und eingeschränktem Zugriff auf das Internet oder Clouddienste
    - Gerätebasierte Zertifikatauthentifizierung.
- Azure Active Directory (Azure AD) Beitreten zur automatischen MDM-Registrierung[(Azure AD P1-Abonnement](/azure/active-directory/fundamentals/active-directory-whatis) erforderlich)
- MDM (Intune) Verwaltet
    - Eine oder mehrere Anwendungen werden über MDM bereitgestellt.
- Netzwerk 
    - Zertifikate (SCEP oder PKCS)
    - Proxykonfiguration
- Benutzer melden sich mit ihrem eigenen Unternehmenskonto (Azure AD) an.
    - Einzelne oder mehrere Benutzer pro Gerät werden unterstützt.
- Unterschiedliche Ebenen von Gerätesperrungskonfigurationen, die basierend auf bestimmten Anwendungsfällen angewendet werden, von Vollständig geöffnet bis Kiosk mit einzelner App.

## <a name="guides-licensing-and-requirements"></a>[Handbücher – Lizenzierung und Anforderungen](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- Azure AD-Konto
- pc und HoloLens Dynamics 365 Guides Anwendungen
- Dynamics 365 Guides-Abonnement
    - Microsoft Dataverse (enthalten)
    - Power Apps (enthalten)
- Power BI Desktop
- Netzwerkverbindung

[![Diagramm des verbundenen Unternehmensnetzwerks, Phase 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagramm des verbundenen Unternehmensnetzwerks, Phase 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>In dieser Anleitung lernen Sie Folgendes:
### <a name="prepare"></a>Vorbereiten
> [!div class="checklist"]
>- [Erfahren Sie mehr über die Grundlegendes zur Infrastruktur für HoloLens 2 Geräte.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Erfahren Sie mehr über Azure AD, und richten Sie eine ein, wenn Sie sie nicht haben.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Erfahren Sie mehr über die Identitätsverwaltung und die optimale Einrichtung Azure AD Konten.](hololens2-corp-connected-prepare.md#identity-management)
>- [Erfahren Sie mehr über MDM, und richten Sie intune ein, wenn Sie noch keine bereit haben.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Machen Sie sich mit zertifikatbasiertem WLAN vertraut.](hololens2-corp-connected-prepare.md#certificates)
>- [Machen Sie sich mit proxy vertraut.](hololens2-corp-connected-prepare.md#proxy)
>- [Erfahren Sie, wie Sie Branchen-Apps verwenden können.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [Erfahren Sie mehr über die Verwendung von Handbüchern für Ihre Organisation.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Konfigurieren
> [!div class="checklist"]
>- [Erstellen von Benutzern und Gruppen](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Einrichten der automatischen Registrierung.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Einrichten von Wi-Fi Zertifikaten und Profilen für unternehmensinterne Wi-Fi Konnektivität.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Hochladen und Zuweisen von LOB-App-Paketen (Line of Business).](hololens2-corp-connected-configure.md#app-deployment)
>- [Richten Sie Dynamics 365 Guides ein.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Konfigurieren des Kioskmodus (optional)](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [Konfigurieren von WDAC (optional).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Bereitstellen
> [!div class="checklist"]
>-  [Überprüfen Sie die Registrierung per Gerät und MDM.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Überprüfen Sie Wi-Fi Zertifikate.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Überprüfen sie die Installation einer branchenspezifische App.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Überprüfen Von Handbüchern über Erstellung und Betrieb.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Verwalten
> [!div class="checklist"]
>- [Aktualisieren Sie HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Aktualisieren von Handbüchern (Store-Apps).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [Aktualisieren branchenspezifische Apps.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Entwicklungsplan:](hololens2-corp-connected-maintain.md#development-plan) 
>- [Erstellen eines Supportplans.](hololens2-corp-connected-maintain.md#support-plan)
>- [Optionen für die Geräteverwaltung.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Nächster Schritt 
> [!div class="nextstepaction"]
> [Unternehmensverbundene Bereitstellung – Vorbereiten](hololens2-corp-connected-prepare.md)
