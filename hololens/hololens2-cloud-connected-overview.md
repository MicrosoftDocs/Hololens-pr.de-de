---
title: Bereitstellungshandbuch – Cloud Connected HoloLens 2 mit Remote Assist – Übersicht
description: Registrieren von HoloLens-Geräten über ein in der Cloud verbundenes Netzwerk
keywords: HoloLens, Verwaltung, Cloud Connected, Remote Assist, AAD, Azure AD, MDM, Verwaltung mobiler Geräte
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
ms.openlocfilehash: 7d954347c7c274b844d436c0d6fc96e8bbc59f10
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253182"
---
# Bereitstellungshandbuch – Cloud Connected HoloLens 2 mit Remote Assist – Übersicht

Dieser Leitfaden unterstützt IT-Experten beim Planen und Bereitstellen von Microsoft HoloLens 2-Geräten für Ihre Organisation mit dem Gesamtziel, dass diese Geräte mit Ihrer Organisation in Verbindung mit der Dynamics 365-Remote Unterstützung einsatzbereit sind. Beachten Sie, dass dies als Modell für Machbarkeits orientierte Bereitstellungen für Ihre Organisation in einer Vielzahl von HoloLens 2-Anwendungsfällen dienen kann.

Während des Leitfadens wird erläutert, wie Sie Ihre Geräte in der Geräteverwaltung registrieren, Lizenzen nach Bedarf anwenden und überprüfen können, ob Ihre Endbenutzer die Remote Unterstützung unmittelbar nach der Einrichtung des Geräts verwenden können. Zu diesem Zweck gehen wir auf die wichtigen Infrastrukturkomponenten ein, die für die Einrichtung und Ausführung erforderlich sind, um die Bereitstellung im Maßstab mit HoloLens 2 zu erreichen.

## In diesem Leitfaden

Dieser Leitfaden hat das spezifische Ziel, den Remote-Support in Ihrer Organisation auf Ihren HoloLens-Geräten einzurichten. Wir werden die Notwendigkeiten decken, die erforderlich sind, um dieses Ziel zu erreichen. Um die Fokussierung auf dieses Ziel zu gewährleisten, sind bestimmte Vorbereitungen und Konfigurationen bereits ausgewählt, um für diese Bereitstellung zu optimieren oder die für die Konfiguration erforderlichen Elemente zu reduzieren. Sie werden über diese Auswahlmöglichkeiten informiert und können Ihre Bereitstellung auf der Grundlage ihrer geschäftlichen Anforderungen anpassen.

Hierbei handelt es sich um eine Einrichtung, die mit [Szenario a vergleichbar ist: Bereitstellen auf Cloud Connect-Geräten](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), was eine gute Option für viele Konzepte zur Machbarkeitsstudie ist, einschließlich:

- Wi-Fi Netzwerke sind in der Regel vollständig für das Internet und die Cloud-Dienste geöffnet.
- Azure AD Join with MDM Auto Enrollment--MDM (InTune) verwaltet
- Benutzer anmelden mit einem eigenen Unternehmenskonto (Azure AD)
  - Einzelne oder mehrere Benutzer pro Gerät unterstützt
- Unterschiedliche Ebenen der Geräte Sperrungs Konfigurationen werden basierend auf bestimmten Anwendungsfällen angewendet, vom vollständigen öffnen zum einzelnen App-Kiosk

![Szenario mit Cloud-Verbindung](./images/cloud-connected-deployment-chart.png)

In diesem Leitfaden werden keine weiteren Geräteeinschränkungen oder-Konfigurationen angewendet, wir empfehlen Ihnen jedoch, diese Optionen nach Abschluss zu untersuchen.

## Informationen zu Remote Unterstützung

Der Remote-Assistent ermöglicht die gemeinsame Wartung und Reparatur, die Remote Inspektion sowie den Austausch von Wissen und Schulungen. Durch die Verbindung von Personen mit unterschiedlichen Rollen und Speicherorten kann ein Techniker mit Remoteunterstützung eine Verbindung mit einem Remotemitarbeiter in Microsoft Teams herstellen. Sie können Video, Screenshots und Anmerkungen kombinieren, um Probleme in Echtzeit zu lösen, auch wenn Sie nicht am selben Ort&#39;t sind. Remote-Mitarbeiter können Referenzbilder, schematische und andere hilfreiche Informationen einfügen, um den physikalischen Platz des Technikers&#39;, damit Sie sich auf die Schaltplan Funktion beziehen können, während Sie Heads-up und freihändig auf HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## In diesem Leitfaden finden Sie folgende Informationen:

Vorbereiten

> [!div class="checklist"]
> - [Erfahren Sie mehr über die Infrastruktur-Grundlagen für HoloLens 2-Geräte.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Weitere Informationen zu Azure AD und Einrichten einer, wenn Sie&#39;t haben.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Erfahren Sie mehr über die Identitätsverwaltung und die optimale Einrichtung von Azure Ad-Konten.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Weitere Informationen zu MDM und zum Einrichten von InTune, wenn Sie&#39;t bereits eine bereit haben.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Informieren Sie sich über die Netzwerkanforderungen der Remote Unterstützung.](hololens2-cloud-connected-prepare.md#network)
> - [Optional: VPN zum Herstellen einer Verbindung mit organisatorischen Ressourcen](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Konfigurieren

> [!div class="checklist"]
> - [Erstellen von Benutzern und Gruppen](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Einrichten der automatischen Registrierung in Azure AD](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [So weisen Sie Ihre Anwendungslizenzen zu.](hololens2-cloud-connected-configure.md#application-licenses)

Bereitstellen

> [!div class="checklist"]
> - [Richten Sie Ihre HoloLens 2 ein, und überprüfen Sie die Registrierung.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Überprüfen Sie können einen Remote Unterstützungs Anruf führen.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Pflegen

> [!div class="checklist"]
> - [Aktualisieren von Remote Unterstützung mithilfe der Microsoft Store-App](hololens2-cloud-connected-maintain.md#updates)
> - [Erstellen eines Support Plans](hololens2-cloud-connected-maintain.md#support-plan)
> - [Entwicklungsplan.](hololens2-cloud-connected-maintain.md#development-plan)

## Nächster Schritt

> [!div class="nextstepaction"]
> [Cloud Connected-Bereitstellung – vorbereiten](hololens2-cloud-connected-prepare.md)

