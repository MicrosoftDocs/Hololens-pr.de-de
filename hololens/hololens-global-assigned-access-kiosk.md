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
ms.openlocfilehash: 8777c64b4d4ca08bf3b103d7d92bbb99d6978bdc
ms.sourcegitcommit: 4e168380c23e8463438aa8a1388baf8d5ac1a1ab
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2020
ms.locfileid: "11154196"
---
# Global zugewiesener Zugriff – Kiosk

Dieses Feature konfiguriert das Hololens 2-Gerät für den Multi-App-Kioskmodus, der auf Systemebene anwendbar ist, keine Affinität zu einer anderen Identität des Systems hat und für jeden gilt, der sich auf dem Gerät anmeldet. 

> [!NOTE]
> Dieses Feature ist derzeit nur in Windows-Insider-Builds verfügbar. Wenn Sie dieses Feature ausprobieren möchten, bevor es in HoloLens-Versionen allgemein verfügbar sein wird, lesen Sie weitere Informationen zu [Windows Insider-](hololens-insider.md)-Builds.
 
## Wie verwende ich dies in InTune? 

> [!NOTE]
> Bitte beachten Sie die mit "<!-" markierten Bereiche. In diesen Bereichen müssen Sie Änderungen vornehmen, die Ihren Voreinstellungen entsprechen. 

1.  Erstellen Sie wie folgt ein benutzerdefiniertes OMA URI-Gerätekonfigurationsprofil und wenden Sie es auf die HoloLens-Gerätegruppe an: 

    URI-Wert: ./Device/Vendor/MSFT/AssignedAccess/Configuration
   
    > [!div class="mx-imgBorder"]
    > ![Globaler zugewiesener Zugriff OMA-URI in Intune](images/global-assigned-access-omauri.png)

2.  Für Wert, aktualisieren und einfügen des folgenden Inhalts: 

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## Wie verwende ich das im Windows Konfigurations-Designer? 
 
1.  Aktualisieren und speichern Sie den oben erwähnten XML-BLOB als XML-Datei. 

2.  Führen Sie die Schritte in [Verwenden eines Bereitstellungspakets aus, um einen Single-App- oder Multi-App-Kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)einzurichten, insbesondere den Abschnitt Prov. Paket, Schritt 2 – Fügen Sie die Kiosk-Konfigurations-XML-Datei zu einem Bereitstellungspaket hinzu und verweisen Sie auf die XML-Datei, die im vorherigen Schritt gespeichert wurde. 

## Kann ich eine Konfiguration erstellen, bei der eine globale Konfiguration für alle und eine separate Konfiguration für 1 AAD-Konto oder eine AAD-Gruppe gilt? 

Ja, weitere Informationen dazu finden Sie im folgenden Beispiel-XML-BLOB. Das global zugewiesene Zugriff-Profil wird auf HoloLens angewendet, wenn ein bestimmtes Profil für den angemeldeten Benutzer nicht gefunden wird. Daher ist dies die Standardkonfiguration für den Kioskmodus für angemeldete Benutzer. Hier ist ein Beispiel für die Verwendung von XML-BLOB: 

> [!NOTE]
> Bitte beachten Sie die mit `<!-` gekennzeichneten Bereiche. In diesen Bereichen müssen Sie Änderungen vornehmen, die Ihren Voreinstellungen entsprechen. 

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## Ausschließen von DeviceOwners aus dem globalen zugewiesenen Access-Profil

Diese Funktion ermöglicht es einem Benutzer, der als "[Gerätebesitzer](security-adminless-os.md)" betrachtet wird, auf Hololens, von dem globalen zugewiesenen Zugriff auszuschließen. Um dieses Feature nutzen zu können, stellen Sie sicher, dass in der XML-BLOB-Konfiguration für mehrere-App-Kiosks hervorgehobene Zeilen hinzugefügt werden: 

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::
 
## Zusätzliche Beispiele für globalen Zugriff

Dies ist ein global zugewiesener Zugriffkiosk. Wenn sich ein Benutzer dort anmeldet, steht ihm ein Multi-App-Kiosk mit der Einstellungen-App, Feedback-Hub und Edge zur Verfügung.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Dies ist ein global zugewiesener Zugriffkiosk, der den Gerätebesitzer ausschließt. Wenn sich ein anderer AAD-Benutzer dort anmeldet, steht ihm ein Multi-App-Kiosk mit der Einstellungen-App, Feedback-Hub und Edge zur Verfügung. Dieser Kiosk enthält auch eine sekundäre Kiosk-Konfiguration für ein Besucherkonto, bei dem sich alle Benutzer auf dem Sperrbildschirm anmelden können. Wenn sich ein Benutzer beim Besucherkonto anmeldet, steht ihm ein Multi-App-Kiosk zur Verfügung, der nur die Feedback-Hub-App enthält.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::


