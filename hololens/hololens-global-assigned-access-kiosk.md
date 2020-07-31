---
title: Global zugewiesener Zugriff
description: Leitfaden für die Verwendung von Oma-URI für global zugewiesene Zugriff-Kioske
author: evmill
ms.author: v-evmill
ms.date: 7/13/2020
ms.topic: article
keywords: HoloLens, HoloLens 2, zugewiesener Zugriff, Kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 1a0a3eb8ef3d21b34e13711bcc890af57e5ae2c2
ms.sourcegitcommit: 7c16570839893f4a4432286b13ae6d84c665d376
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "10902300"
---
# Global zugewiesener Zugriff – Kiosk

Dieses Feature konfiguriert das Hololens 2-Gerät für den Multi-App-Kioskmodus, der auf Systemebene anwendbar ist, keine Affinität zu einer anderen Identität des Systems hat und für jeden gilt, der sich auf dem Gerät anmeldet. 

> [!NOTE]
> Dieses Feature ist derzeit nur in Windows-Insider-Builds verfügbar. Wenn Sie dieses Feature ausprobieren möchten, bevor es in HoloLens-Versionen allgemein verfügbar sein wird, lesen Sie weitere Informationen zu [Windows Insider-](hololens-insider.md)-Builds.
 
## Wie verwende ich dies in InTune? 

> [!NOTE]
> Bitte beachten Sie die mit "<!-" markierten Bereiche. In diesen Bereichen müssen Sie Änderungen vornehmen, die Ihren Voreinstellungen entsprechen. 

1.  Erstellen Sie ein benutzerdefiniertes Konfigurationsprofil für OMA-URI-Geräte wie folgt, und wenden Sie es auf die HoloLens-Gerätegruppe an: ![Global zugewiesene Zugriff Oma-URI in InTune](images/global-assigned-access-omauri.png)

2.  Für Wert, aktualisieren und einfügen des folgenden Inhalts: 

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## Wie verwende ich das im Windows Konfigurations-Designer? 
 
1.  Aktualisieren und speichern Sie den oben erwähnten XML-BLOB als XML-Datei. 

2.  Führen Sie die Schritte in [Verwenden eines Bereitstellungspakets aus, um einen Single-App- oder Multi-App-Kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)einzurichten, insbesondere den Abschnitt Prov. Paket, Schritt 2 – Fügen Sie die Kiosk-Konfigurations-XML-Datei zu einem Bereitstellungspaket hinzu und verweisen Sie auf die XML-Datei, die im vorherigen Schritt gespeichert wurde. 

## Kann ich eine Konfiguration erstellen, bei der Global für alle Personen mit Ausnahme des 1 AAD-Kontos oder der AAD-Gruppe gilt? 

Ja, weitere Informationen dazu finden Sie im folgenden Beispiel-XML-BLOB. Das global zugewiesene Zugriff-Profil wird auf HoloLens angewendet, wenn ein bestimmtes Profil für den angemeldeten Benutzer nicht gefunden wird. Daher ist dies die Standardkonfiguration für den Kioskmodus für angemeldete Benutzer. Hier ist ein Beispiel für die Verwendung von XML-BLOB: 

> [!NOTE]
> Bitte beachten Sie die mit <! markierten Bereiche. In diesen Bereichen müssen Sie Änderungen vornehmen, die Ihren Einstellungen entsprechen. 

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## Ausschließen von DeviceOwners aus dem globalen zugewiesenen Access-Profil

Diese Funktion ermöglicht es einem Benutzer, der als "[Gerätebesitzer](security-adminless-os.md)" betrachtet wird, auf Hololens, von dem globalen zugewiesenen Zugriff auszuschließen. Um dieses Feature nutzen zu können, stellen Sie sicher, dass in der XML-BLOB-Konfiguration für mehrere-App-Kiosks hervorgehobene Zeilen hinzugefügt werden: 

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::
 
