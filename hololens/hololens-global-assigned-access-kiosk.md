---
title: Global zugewiesener Zugriff
description: Leitfaden für die Verwendung von Oma-URI für global zugewiesene Zugriff-Kioske
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: HoloLens, HoloLens 2, zugewiesener Zugriff, Kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f91b77be846b585de8d89c17e516923f97304d57
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253202"
---
# Global zugewiesener Zugriff – Kiosk

Dieses Feature konfiguriert das HoloLens 2-Gerät für den Multi-App-Kioskmodus, der auf Systemebene anwendbar ist, keine Affinität zu einer anderen Identität des Systems hat und für jeden gilt, der sich auf dem Gerät anmeldet.

> [!NOTE]
> Dieses Feature ist derzeit nur in Windows-Insider-Builds verfügbar. Wenn Sie dieses Feature ausprobieren möchten, bevor es in HoloLens-Versionen allgemein verfügbar sein wird, lesen Sie weitere Informationen zu [Windows-Insider-](hololens-insider.md)-Builds.

## Zur Verwendung des Globalen zugewiesenen Zugriffs in Intune.

> [!NOTE]
> Bitte beachten Sie die mit "<!-" markierten Bereiche. In diesen Bereichen müssen Sie Änderungen vornehmen, die Ihren Voreinstellungen entsprechen.

1. Erstellen Sie wie folgt ein benutzerdefiniertes OMA URI-Gerätekonfigurationsprofil und wenden Sie es auf die HoloLens-Gerätegruppe an:

    URI-Wert: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Globaler zugewiesener Zugriff OMA-URI in Intune](images/global-assigned-access-omauri.png)

2. Für Wert, aktualisieren und einfügen des folgenden Inhalts:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## Zur Verwendung des Einrichten des Globalen zugewiesenen Zugriffs im Windows-Konfigurations-Designer.

1. Aktualisieren und speichern Sie den oben erwähnten XML-BLOB als XML-Datei. 

2. Führen Sie die Schritte in [Verwenden eines Bereitstellungspakets aus, um einen Single-App- oder Multi-App-Kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)einzurichten, insbesondere den Abschnitt Prov. Paket, Schritt 2 – Fügen Sie die Kiosk-Konfigurations-XML-Datei zu einem Bereitstellungspaket hinzu und verweisen Sie auf die XML-Datei, die im vorherigen Schritt gespeichert wurde.

## Kann ich eine Konfiguration erstellen, bei der eine globale Konfiguration für alle und eine separate Konfiguration für 1 Azure AD-Konto oder eine Azure AD-Gruppe gilt? 

Ja, weitere Informationen dazu finden Sie im folgenden Beispiel-XML-BLOB. Das global zugewiesene Zugriff-Profil wird auf HoloLens angewendet, wenn ein bestimmtes Profil für den angemeldeten Benutzer nicht gefunden wird. Daher ist dies die Standardkonfiguration für den Kioskmodus für angemeldete Benutzer.
Hier ist ein Beispiel für die Verwendung von XML-BLOB:

> [!NOTE]
> Bitte beachten Sie die mit `<!-` gekennzeichneten Bereiche. In diesen Bereichen müssen Sie Änderungen vornehmen, die Ihren Voreinstellungen entsprechen.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## Ausschließen von DeviceOwners aus dem globalen zugewiesenen Access-Profil

Diese Funktion ermöglicht es einem Benutzer, der auf HoloLens als "[Gerätebesitzer](security-adminless-os.md)" betrachtet wird, von dem globalen zugewiesenen Zugriff auszuschließen. Um dieses Feature nutzen zu können, stellen Sie sicher, dass in der XML-BLOB-Konfiguration für mehrere-App-Kiosks hervorgehobene Zeilen hinzugefügt werden:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## Zusätzliche Beispiele für globalen Zugriff

Dies ist ein Beispiel für einen globalen zugewiesenen Zugriffskiosk. Wenn sich ein Benutzer dort anmeldet, steht ihm ein Multi-App-Kiosk mit der Einstellungen-App, Feedback-Hub und Microsoft Edge zur Verfügung.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Bei diesem Beispiel handelt es sich um einen global zugewiesenen Zugriffskiosk, der den Gerätebesitzer ausschließt. Wenn sich ein anderer Azure AD-Benutzer dort anmeldet, steht ihm ein Multi-App-Kiosk mit der Einstellungen-App, Feedback-Hub und Microsoft Edge zur Verfügung. Dieser Kiosk enthält auch eine sekundäre Kiosk-Konfiguration für ein Besucherkonto, bei dem sich alle Benutzer auf dem Sperrbildschirm anmelden können. Wenn sich ein Benutzer beim Besucherkonto anmeldet, steht ihm ein Multi-App-Kiosk zur Verfügung, der nur die Feedback-Hub-App enthält.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
