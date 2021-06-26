---
title: Übersicht über cloudbasierte HoloLens 2 mit Remote Assist
description: Erfahren Sie, wie Sie HoloLens 2 über ein mit der Cloud verbundenes Netzwerk registrieren, indem Sie Dynamics 365 Remote Assist.
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
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923532"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Bereitstellungshandbuch – Cloud connected HoloLens 2 with Remote Assist – Overview

Dieser Leitfaden hilft IT-Experten bei der Planung und Bereitstellung Microsoft HoloLens 2-Geräten mit Remote Assist in ihrer Organisation. Dies dient als Modell für Proof of Concept-Bereitstellungen für Ihre Organisation in einer Vielzahl HoloLens 2 Anwendungsfällen. Das Setup ähnelt Szenario [A: Bereitstellen auf Cloud connect-Geräten.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a) 

Im Rahmen dieses Leitfadens erfahren Sie, wie Sie Ihre Geräte bei Ihrer Geräteverwaltung registrieren, lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer die Geräte bei der Geräteeinrichtung Remote Assist sofort verwenden können. Hierzu gehen wir auf die wichtigen Infrastrukturteile ein, die erforderlich sind, um eingerichtet und ausgeführt zu werden– um eine Bedarfsbereitstellung mit HoloLens 2. In diesem Leitfaden werden keine anderen Geräteeinschränkungen oder Konfigurationen angewendet. Wir empfehlen Ihnen jedoch, diese Optionen nach Abschluss des Handbuchs zu untersuchen.

## <a name="prerequisites"></a>Voraussetzungen

Die folgende Infrastruktur sollte zum Bereitstellen der -HoloLens 2. Wenn dies nicht der Fall ist, ist das Einrichten von Azure und Intune in diesem Leitfaden enthalten:

- WLAN
    - Netzwerke sind in der Regel für die Internet- und Clouddienste geöffnet.
- Azure Active Directory (Azure AD) Join mit automatischer MDM-Registrierung ([Azure AD P1-Abonnement](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) erforderlich)
- MDM (Intune) Verwaltet
    - Mindestens eine Anwendung wird über MDM bereitgestellt.
- Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)
    - Einzelne oder mehrere Benutzer pro Gerät werden unterstützt.

:::image type="content" alt-text="Cloud verbundenes Szenario" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Weitere Informationen Remote Assist

Remote Assist ermöglicht gemeinsame Wartung und Reparatur, Remoteüberprüfung sowie Wissensfreigabe und Schulungen. Durch Verbinden von Personen in verschiedenen Rollen und Standorten kann ein Techniker Remote Assist mit einem Remotemitarbeiter in Microsoft Teams eine Verbindung herstellen. Sie können Videos, Screenshots und Anmerkungen kombinieren, um Probleme auch dann in Echtzeit zu lösen, wenn&#39;sich nicht am gleichen Ort befinden. Remotemitarbeiter können Referenzbilder, Schemata und andere hilfreiche Informationen einfügen, die der Techniker&#39;physischem Raum enthält, damit sie auf das Schema verweisen können, während sie auf HoloLens kopf- und händefrei arbeiten.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Remote Assist Lizenzierung und Anforderungen

- Azure AD -Konto (erforderlich für den Erwerb des Abonnements und das Zuweisen von Lizenzen)
- [Remote Assist -Abonnement](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (oder [Remote Assist-Testversion)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist Benutzer

- Remote Assist Lizenz
- Netzwerkverbindung

#### <a name="microsoft-teams-user"></a>Microsoft Teams-Benutzer

- Microsoft Teams oder [Teams Freemium](https://products.office.com/microsoft-teams/free).
- Netzwerkkonnektivität

Wenn Sie dieses mandantenübergreifende [Szenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)implementieren möchten, benötigen Sie möglicherweise eine Lizenz für Informationsbarrieren. In [diesem Artikel erfahren](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) Sie, ob eine Information Barrier License erforderlich ist.

## <a name="in-this-guide-you-will"></a>In dieser Anleitung lernen Sie Folgendes:

Vorbereiten:

> [!div class="checklist"]
> - [Erfahren Sie mehr über die Infrastruktur essentials für HoloLens 2 Geräte.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Erfahren Sie mehr über Azure AD und richten Sie eine ein, wenn Sie&#39;nicht haben.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Erfahren Sie mehr über die Identitätsverwaltung und die optimale Einrichtung Azure AD Konten.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Erfahren Sie mehr über MDM, und richten Sie Intune ein,&#39;sie noch nicht bereit sind.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Erfahren Sie mehr über die Netzwerkanforderungen Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Optional: VPN zum Herstellen einer Verbindung mit Organisationsressourcen](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Konfiguration von:

> [!div class="checklist"]
> - [Erstellen von Benutzern und Gruppen.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Einrichten der automatischen Registrierung in Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Zuweisen von Anwendungslizenzen](hololens2-cloud-connected-configure.md#application-licenses)

Bereitstellen:

> [!div class="checklist"]
> - [Richten Sie Ihre HoloLens 2 ein, und überprüfen Sie die Registrierung.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Überprüfen Sie, ob Sie einen Remote Assist können.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Warten:

> [!div class="checklist"]
> - [Aktualisieren von Remote Assist mithilfe der Microsoft Store-App.](hololens2-cloud-connected-maintain.md#updates)
> - [Erstellen eines Supportplans.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Entwicklungsplan.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Nächster Schritt

> [!div class="nextstepaction"]
> [Mit der Cloud verbundene Bereitstellung: Vorbereiten](hololens2-cloud-connected-prepare.md)

