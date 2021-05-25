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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397651"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Bereitstellungshandbuch – Cloud-verbundene HoloLens 2 mit Remote Assist – Übersicht

Dieser Leitfaden unterstützt IT-Experten bei der Planung und Bereitstellung von Microsoft HoloLens 2 Geräten in ihrer Organisation mit dem allgemeinen Ziel, dass diese Geräte mit Ihrer Organisation verbunden sind und Dynamics 365 Remote Assist einsatzbereit sind. Beachten Sie, dass dies als Modell für Proof of Concept-Bereitstellungen in Ihrer Organisation in einer Vielzahl von HoloLens 2 Anwendungsfällen dient.

In diesem Leitfaden wird erläutert, wie Sie Ihre Geräte bei der Geräteverwaltung registrieren, Lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer Remote Assist sofort bei der Geräteeinrichtung verwenden können. Zu diesem Zeitpunkt werden die wichtigen Teile der Infrastruktur behandelt, die für die Einrichtung und Ausführung erforderlich sind, um eine bedarfsorientierte Bereitstellung mit HoloLens 2 zu erreichen.

[Szenario mit ![ ](./images/deployment-guides-revised-scenario-a.png) Cloudverbindung ](./images/deployment-guides-revised-scenario-a.png#lightbox)
## <a name="in-this-guide"></a>In diesem Handbuch

Dieser Leitfaden hat das spezifische Ziel, Remote Assist in Ihrer Organisation auf Ihren HoloLens-Geräten einzurichten. Wir werden die Notwendigkeiten abdecken, die erforderlich sind, um dieses Ziel zu erreichen. Um den Fokus auf dieses Ziel zu behalten, werden bestimmte Vorbereitungen und Konfigurationen vorab ausgewählt, um für diese Bereitstellung zu optimieren oder die für die Konfiguration erforderlichen Elemente zu reduzieren. Sie werden über diese Optionen informiert und können Ihre Bereitstellung an Ihre geschäftlichen Anforderungen anpassen.

Dies ist eine Einrichtung, die dem [Szenario A: Bereitstellen auf Cloudverbindungsgeräten](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)ähnelt. Dies ist eine gute Option für viele Proof of Concept-Bereitstellungen, die Folgendes umfassen:

- Wi-Fi Netzwerke sind in der Regel vollständig für internet- und cloudbasierte Dienste geöffnet.
- Azure AD Mit automatischer MDM-Registrierung beitreten – MDM (Intune) verwaltet
- Benutzer melden sich mit ihrem eigenen Unternehmenskonto (Azure AD) an.
  - Einzelne oder mehrere Benutzer pro Gerät unterstützt
- Verschiedene Ebenen von Gerätesperrungskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von "Vollständig geöffnet" bis "Kiosk für einzelne Apps".



In diesem Leitfaden werden keine anderen Geräteeinschränkungen oder Konfigurationen angewendet. Wir empfehlen Ihnen jedoch, diese Optionen nach Abschluss des Handbuchs zu untersuchen.

## <a name="learn-about-remote-assist"></a>Weitere Informationen Remote Assist

Remote Assist ermöglicht gemeinsame Wartung und Reparatur, Remoteüberprüfung sowie Wissensfreigabe und Schulungen. Durch Verbinden von Personen in verschiedenen Rollen und Standorten kann ein Techniker Remote Assist mit einem Remotemitarbeiter in Microsoft Teams eine Verbindung herstellen. Sie können Videos, Screenshots und Anmerkungen kombinieren, um Probleme auch dann in Echtzeit zu lösen, wenn&#39;sich nicht am gleichen Ort befinden. Remotemitarbeiter können Referenzbilder, Schemata und andere hilfreiche Informationen einfügen, die der Techniker&#39;physischem Raum enthält, damit sie auf das Schema verweisen können, während sie auf HoloLens kopf- und händefrei arbeiten.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a>In dieser Anleitung lernen Sie Folgendes:

Vorbereiten:

> [!div class="checklist"]
> - [Erfahren Sie mehr über die Infrastruktur essentials für HoloLens 2 Geräte.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Erfahren Sie mehr über Azure AD und richten Sie eine ein, wenn Sie&#39;nicht haben.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Erfahren Sie mehr über die Identitätsverwaltung und die optimale Einrichtung Azure AD Konten.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Erfahren Sie mehr über MDM, und richten Sie Intune ein,&#39;sie noch nicht bereit sind.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Erfahren Sie mehr über die Netzwerkanforderungen Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Optional: VPN zum Herstellen einer Verbindung mit Organisationsressourcen](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

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
> - [Entwicklungsplan:](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Nächster Schritt

> [!div class="nextstepaction"]
> [Bereitstellung mit Cloudverbindung – Vorbereiten](hololens2-cloud-connected-prepare.md)

