---
title: Global zugewiesener Zugriff
description: Beginnen Sie mit unserem Leitfaden zur Verwendung von OMA-URI für Kioske mit global zugewiesenem Zugriff mit Intune und Windows Configuration Designer.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: HoloLens, HoloLens 2, zugewiesener Zugriff, Kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d89c630da76060fe6c2a049e5fa162e88779bb99
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640422"
---
# <a name="global-assigned-access--kiosk"></a>Global zugewiesener Zugriff: Kiosk

Dieses Feature konfiguriert das HoloLens 2-Gerät für den Multi-App-Kioskmodus, der auf Systemebene anwendbar ist, keine Affinität zu einer Identität des Systems hat und für jeden gilt, der sich auf dem Gerät anmeldet.

> [!NOTE]
> Dieses Feature ist derzeit nur in Windows-Insider-Builds verfügbar. Wenn Sie dieses Feature vor seiner allgemeinen Verfügbarkeit in HoloLens-Versionen ausprobieren möchten, lesen Sie weitere Informationen zu [Windows-Insider](hololens-insider.md)-Builds.

## <a name="how-to-use-global-assigned-access-in-intune"></a>Zur Verwendung des global zugewiesenen Zugriffs in Intune.

> [!NOTE]
> Bitte beachten Sie die mit „<!-“ markierten Bereiche. In diesen Bereichen müssen Sie Änderungen vornehmen, die Ihren Voreinstellungen entsprechen.

1. Erstellen Sie wie folgt ein benutzerdefiniertes OMA URI-Gerätekonfigurationsprofil, und wenden Sie es auf die HoloLens-Gerätegruppe an:

    URI-Wert: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Global zugewiesener Zugriff OMA-URI in Intune](images/global-assigned-access-omauri.png)

2. Aktualisieren Sie für den Wert den folgenden Inhalt, und fügen Sie ihn ein:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Wie verwende ich den global zugewiesenen Zugriff in Windows Configuration Designer?

1. Aktualisieren und speichern Sie den oben erwähnten XML-BLOB als XML-Datei. 

2. Führen Sie die Schritte unter [Verwenden eines Bereitstellungspakets zum Einrichten eines Single-App oder Multi-App-Kiosks](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) mit aus, insbesondere im Abschnitt „Bereitstellungspaket Schritt 2: Hinzufügen der Kiosk-Konfigurations-XML-Datei zu einem Bereitstellungspaket“, und verweisen Sie auf die XML-Datei, die im vorherigen Schritt gespeichert wurde.

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>Kann ich eine Konfiguration erstellen, bei der eine globale Konfiguration für alle und eine separate Konfiguration für 1 Azure AD-Konto oder eine Azure AD-Gruppe gilt? 

Ja, Informationen dazu finden Sie im folgenden Beispiel-XML-BLOB. Das global zugewiesene Zugriffsprofil wird auf HoloLens angewendet, wenn kein bestimmtes Profil für den angemeldeten Benutzer gefunden wird. Dies ist also die Standardkonfiguration für den Kioskmodus für angemeldete Benutzer.
Hier ist ein Beispiel für die Verwendung von XML-BLOB:

> [!NOTE]
> Beachten Sie die hervorgehobenen Bereiche, die mit `<!-` gekennzeichnet sind. In diesen Bereichen müssen Sie Änderungen vornehmen, die Ihren Voreinstellungen entsprechen.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>Ausschließen von DeviceOwners aus dem globalen zugewiesenen Zugriffsprofil

Diese Funktion macht es möglich, einen Benutzer, der auf HoloLens als „[Gerätebesitzer](security-adminless-os.md)“ angesehen wird, vom global zugewiesenen Zugriff auszuschließen. Stellen Sie zum Nutzen dieser Funktion sicher, dass in der XML-BLOB-Konfiguration für den Multi-App-Kiosk die hervorgehobenen Zeilen hinzugefügt werden:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>Weitere Beispiele für den global zugewiesenen Zugriff

Dies ist ein Beispiel für einen Kiosk mit global zugewiesenem Zugriff. Wenn sich ein Benutzer dort anmeldet, steht ihm ein Multi-App-Kiosk mit der Einstellungen-App, dem Feedback-Hub und Microsoft Edge zur Verfügung.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Bei diesem Beispiel handelt es sich um einen Kiosk mit global zugewiesenem Zugriff, der den Gerätebesitzer ausschließt. Wenn sich ein anderer Azure AD-Benutzer dort anmeldet, steht ihm ein Multi-App-Kiosk mit der Einstellungen-App, dem Feedback-Hub und Microsoft Edge zur Verfügung. Dieser Kiosk enthält außerdem eine sekundäre Kiosk-Konfiguration für ein Besucherkonto, bei dem sich alle Benutzer auf dem Sperrbildschirm anmelden können. Wenn sich ein Benutzer beim Besucherkonto anmeldet, steht ihm ein Multi-App-Kiosk zur Verfügung, der nur die Feedback-Hub-App enthält.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
