---
title: Übersicht über cloudgebundene HoloLens 2 mit Remote Assist
description: Erfahren Sie, wie Sie HoloLens 2 Geräte über ein mit der Cloud verbundenes Netzwerk mithilfe von Dynamics 365 Remote Assist registrieren.
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
ms.openlocfilehash: 66e543dd699edbd54ab41474f3ea86fa313bf6ba
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032733"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Bereitstellungshandbuch – Cloud-verbundene HoloLens 2 mit Remote Assist – Übersicht

Dieser Leitfaden unterstützt IT-Experten bei der Planung und Bereitstellung von Microsoft HoloLens 2-Geräten mit Remote Assist in ihrer Organisation. Dies dient als Modell für Proof-of-Concept-Bereitstellungen in Ihrer Organisation in verschiedenen HoloLens 2 Anwendungsfällen. Das Setup ähnelt [Szenario A: Bereitstellen auf Cloudverbindungsgeräten.](common-scenarios.md#scenario-a) 

Während des Leitfadens erfahren Sie, wie Sie Ihre Geräte bei der Geräteverwaltung registrieren, Lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer Remote Assist sofort bei der Geräteeinrichtung verwenden können. Zu diesem Zeitpunkt werden die wichtigen Infrastrukturteile behandelt, die für die Einrichtung und Ausführung erforderlich sind, um eine bedarfsorientierte Bereitstellung mit HoloLens 2 zu erreichen. In diesem Leitfaden werden keine anderen Geräteeinschränkungen oder Konfigurationen angewendet. Wir empfehlen Ihnen jedoch, diese Optionen nach Abschluss des Handbuchs zu untersuchen.

## <a name="prerequisites"></a>Voraussetzungen

Die folgende Infrastruktur sollte vorhanden sein, um die HoloLens 2 bereitzustellen. Andernfalls ist das Einrichten von Azure und Intune in diesem Leitfaden enthalten:

Dies ist ein Setup ähnlich dem [Szenario A: Bereitstellen auf Cloudverbindungsgeräten.](/hololens/common-scenarios#scenario-a)Dies ist eine gute Option für viele Proof of Concept-Bereitstellungen, die Folgendes umfassen:

- Wi-Fi Netzwerke sind in der Regel vollständig für das Internet und cloudbasierte Dienste geöffnet.
- Azure AD Beitreten zur automatischen MDM-Registrierung – MDM-verwaltet (Intune)
- Benutzer melden sich mit ihrem eigenen Unternehmenskonto (Azure AD) an.
    - Einzelne oder mehrere Benutzer pro Gerät werden unterstützt.

:::image type="content" alt-text="Szenario mit Cloudverbindung." source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Informationen zu Remote Assist

Remote Assist ermöglicht die zusammenarbeitsgesteuerte Wartung und Reparatur, Remoteuntersuchung sowie Wissensaustausch und Schulungen. Durch das Verbinden von Personen an unterschiedlichen Rollen und Standorten kann sich ein Techniker, der Remote Assist verwendet, mit einem Remotemitarbeiter auf Microsoft Teams verbinden. Sie können Videos, Screenshots und Anmerkungen kombinieren, um Probleme in Echtzeit zu lösen, auch wenn sie sich nicht am selben Ort befinden. Remotemitarbeiter können Referenzbilder, Schemata und andere hilfreiche Informationen in den physischen Raum des Technikers einfügen, damit sie beim Arbeiten mit kopf- und freihändigen HoloLens auf das Schema verweisen können.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Remote Assist Lizenzierung und Anforderungen

- Azure AD-Konto (erforderlich für den Erwerb des Abonnements und die Zuweisung von Lizenzen)
- [Remote Assist-Abonnement](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (oder [Remote Assist-Testversion](/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist-Benutzer

- Remote Assist-Lizenz
- Netzwerkverbindung

#### <a name="microsoft-teams-user"></a>Microsoft Teams-Benutzer

- Microsoft Teams oder [Teams Freemium](https://products.office.com/microsoft-teams/free).
- Netzwerkverbindungen

Wenn Sie dieses [mandantenübergreifende Szenario](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants) implementieren möchten, benötigen Sie möglicherweise eine Lizenz für Informationsbarrieren. Informationen dazu, ob eine Information Barrier-Lizenz erforderlich ist, finden Sie unter [Anbieter und Kunden verwenden vollständige Dynamics 365 Remote Assist Funktionen.](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation)

## <a name="in-this-guide-you-will"></a>In dieser Anleitung lernen Sie Folgendes:

Vorbereiten:

> [!div class="checklist"]
> - [Erfahren Sie mehr über die Grundlegendes zur Infrastruktur für HoloLens 2 Geräte.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Erfahren Sie mehr über Azure AD, und richten Sie eine ein, wenn Sie sie nicht&#39;haben.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Erfahren Sie mehr über die Identitätsverwaltung und die optimale Einrichtung Azure AD Konten.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Erfahren Sie mehr über MDM, und richten Sie intune ein, wenn Sie&#39;noch nicht bereit sind.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Erfahren Sie mehr über die Netzwerkanforderungen von Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Optional: VPN zum Herstellen einer Verbindung mit Organisationsressourcen](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Konfiguration von:

> [!div class="checklist"]
> - [Erstellen von Benutzern und Gruppen](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Einrichten der automatischen Registrierung in Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Zuweisen Ihrer Anwendungslizenzen.](hololens2-cloud-connected-configure.md#application-licenses)

Bereitstellen:

> [!div class="checklist"]
> - [Richten Sie Ihre HoloLens 2 ein, und überprüfen Sie die Registrierung.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Überprüfen Sie, ob Sie einen Remote Assist Aufrufen vornehmen können.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Warten:

> [!div class="checklist"]
> - [Aktualisieren Remote Assist mithilfe der Microsoft Store-App](hololens2-cloud-connected-maintain.md#updates)
> - [Erstellen eines Supportplans.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Entwicklungsplan:](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Nächster Schritt

> [!div class="nextstepaction"]
> [Bereitstellung mit Cloudverbindung – Vorbereiten](hololens2-cloud-connected-prepare.md)

