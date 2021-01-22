---
title: Übersicht über mit der Cloud verbundene HoloLens 2 mit Remote Assist
description: Erfahren Sie, wie Sie HoloLens 2-Geräte über ein cloudverbundenes Netzwerk mit Dynamics 365 Remote Assist registrieren.
keywords: HoloLens, Verwaltung, mit der Cloud verbunden, Remote Assist, AAD, Azure AD, MDM, Verwaltung mobiler Geräte
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
ms.openlocfilehash: 835b4be101b665d2b86c2170a65c04697686e403
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283076"
---
# Bereitstellungshandbuch – Mit der Cloud verbundene HoloLens 2 mit Remote Assist – Übersicht

Dieses Handbuch hilft IT-Experten bei der Planung und Bereitstellung von Microsoft HoloLens 2-Geräten in ihrer Organisation mit dem allgemeinen Ziel, dass diese Geräte cloudgebunden mit Ihrer Organisation mit Dynamics 365 Remote Assist betriebsbereit sind. Beachten Sie, dass dies als Modell für die Bereitstellung von Proof-of-Concept-Bereitstellungen für Ihre Organisation in einer Vielzahl von HoloLens 2-Verwendungsfällen dient.

In diesem Leitfaden wird beschrieben, wie Sie Ihre Geräte bei der Geräteverwaltung registrieren, Lizenzen nach Bedarf anwenden und überprüfen, ob Ihre Endbenutzer remote Assist sofort beim Einrichten des Geräts verwenden können. Dazu werden wir die wichtigen Infrastrukturteile durchgehen, die für die Einrichtung und Ausführung erforderlich sind – die Bereitstellung mit HoloLens 2 wird im großen Maßstab erreicht.

## In diesem Leitfaden

Dieses Handbuch hat das spezifische Ziel, Remote Assist in Ihrer Organisation auf Ihren HoloLens-Geräten einrichten. Wir werden die Notwendigkeiten zur Erreichung dieses Ziels abdecken. Um den Fokus auf diesem Ziel zu behalten, werden bestimmte Vorbereitungen und Konfigurationen vorab ausgewählt, um die Bereitstellung zu optimieren oder die zu konfigurierenden Elemente zu reduzieren. Sie werden über diese Auswahlmöglichkeiten informiert und können Ihre Bereitstellung an Ihre Geschäftlichen Anforderungen anpassen.

Diese Einrichtung ähnelt Szenario [A: Bereitstellen](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)auf Cloud Connect-Geräten. Dies ist eine gute Option für viele Proof of Concept-Bereitstellungen, die Folgendes umfassen:

- Wi-Fi Netzwerke sind in der Regel vollständig für internet- und cloudbasierte Dienste geöffnet
- Azure AD Join mit automatischer MDM-Registrierung – MDM (Intune) Managed
- Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)
  - Einzelne oder mehrere Benutzer pro Gerät unterstützt
- Unterschiedliche Stufen von Gerätesperrmoduskonfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, von "Vollständig geöffnet" bis "Single App Kiosk".

![Mit der Cloud verbundenes Szenario](./images/cloud-connected-guide-diagram.png)

In diesem Leitfaden werden keine weiteren Geräteeinschränkungen oder -konfigurationen angewendet. Wir empfehlen Ihnen jedoch, diese Optionen nach abschluss zu erkunden.

## Erfahren Sie mehr über Remote Assist

Remote Assist ermöglicht gemeinsame Wartung und Reparatur, Remoteinspektion sowie Wissensfreigabe und Schulung. Durch das Verbinden von Personen an unterschiedlichen Rollen und Standorten kann ein Techniker mit Remote Assist eine Verbindung mit einem Remotemitarbeiter in Microsoft Teams herstellen. Sie können Videos, Screenshots und Anmerkungen kombinieren, um Probleme in Echtzeit zu lösen, auch wenn&#39;sich nicht am selben Speicherort befinden. Remotemitarbeiter können Referenzbilder, Schemata und andere hilfreiche Informationen einfügen, die der Techniker&#39;den physischen Raum eingibt, damit sie auf das Schema beim Arbeiten mit Kopf und Freisprechen auf HoloLens verweisen können.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## In diesem Leitfaden werden Sie:

Bereiten Sie dies vor:

> [!div class="checklist"]
> - [Erfahren Sie mehr über die grundlegenden Infrastruktur für HoloLens 2-Geräte.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Erfahren Sie mehr über Azure AD, und richten Sie eins ein,&#39;nicht verfügen.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Erfahren Sie mehr über die Identitätsverwaltung und die beste Einrichtung von Azure AD-Konten.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Erfahren Sie mehr über MDM, und richten Sie Intune ein,&#39;sie noch nicht bereit sind.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Erfahren Sie mehr über die Netzwerkanforderungen von Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Optional: VPN zum Herstellen einer Verbindung mit Organisationsressourcen](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Konfigurieren Sie:

> [!div class="checklist"]
> - [Erstellen von Benutzern und Gruppen.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Einrichten der automatischen Registrierung in Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Zuweisen von Anwendungslizenzen.](hololens2-cloud-connected-configure.md#application-licenses)

Bereitstellen:

> [!div class="checklist"]
> - [Richten Sie HoloLens 2 ein, und überprüfen Sie die Registrierung.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Überprüfen Sie, ob Sie einen Remote assist-Anruf machen können.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Warten Sie:

> [!div class="checklist"]
> - [So aktualisieren Sie Remote Assist mithilfe der Microsoft Store-App.](hololens2-cloud-connected-maintain.md#updates)
> - [Erstellen eines Supportplans.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Entwicklungsplan.](hololens2-cloud-connected-maintain.md#development-plan)

## Nächster Schritt

> [!div class="nextstepaction"]
> [Mit der Cloud verbundene Bereitstellung – Vorbereiten](hololens2-cloud-connected-prepare.md)

