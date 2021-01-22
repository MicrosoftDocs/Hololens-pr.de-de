---
title: Verwalten von benutzerdefinierten Apps für HoloLens (1. Generation)
description: Erfahren Sie, wie Sie benutzerdefinierte holografische Apps auf HoloLens-Geräten mithilfe des Geräteportals und der Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: HoloLens, Querladen, Querladen, Querladen, Store, UWP, App, installieren
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: 4c6d982bee72195bef955532738711f2b00ac8be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "11296988"
---
# Verwalten von benutzerdefinierten Apps für HoloLens (1. Generation)

HoloLens unterstützt viele vorhandene Anwendungen aus dem Microsoft-Shop sowie neue Apps, die speziell für HoloLens erstellt wurden. Dieser Artikel befasst sich mit benutzerdefinierten holografischen Anwendungen.  

Weitere Informationen zu Store-Apps finden Sie unter ["Verwalten von Apps mit dem Store".](holographic-store-apps.md)

> [!IMPORTANT]
> Die folgenden Informationen wurden für HoloLens (1. Generation) erstellt, die zu diesem Zeitpunkt auch als HoloLens Developer Edition bezeichnet wurde. Das Querladen von Apps über das Geräteportal und das Installieren von Apps über Visual Studio waren dann üblich. Für Unternehmensbereitstellungen wird die Aktivierung des Entwicklermodus, der von beiden Methoden verwendet wird, nicht empfohlen. Wenn Sie an einer sicheren Bereitstellungsmethode für Apps interessiert sind, lesen Sie unsere [App-Verwaltung: Übersicht](app-deploy-overview.md).
>
> Wenn Sie nach einer der Entwicklerverfahren für die Installation von Apps für HoloLens 2-Geräte suchen, lesen Sie bitte:
> - [Geräteportal: Installieren einer App](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Verwenden Visual Studio zum Bereitstellen und Debuggen von Apps](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## Installieren benutzerdefinierter Apps

Sie können Ihre eigenen Anwendungen auf HoloLens entweder über das Geräteportal oder durch Bereitstellen der Apps von Visual Studio.

### Installieren eines Anwendungspakets mit dem Geräteportal

1. Stellen Sie eine Verbindung vom [Geräteportal mit](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) der HoloLens-Zielwebsite fest.

1. Navigieren Sie im linken Navigationsbereich zur **Seite "Apps".**

1. Navigieren **Sie unter "App-Paket"** zu der APPX-Datei, die Ihrer Anwendung zugeordnet ist.

   > [!IMPORTANT]
   > Verweisen Sie unbedingt auf alle zugeordneten Abhängigkeits- und Zertifikatdateien.

1. Select **Go**.

   > [!div class="mx-imgBorder"]
   > ![Installieren des App-Formulars im Windows Device Portal auf Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### Bereitstellen von Microsoft Visual Studio 2015

1. Öffnen Sie die Visual Studio Ihrer App (SLN-Datei).

1. Öffnen Sie die Eigenschaften des **Projekts.**

1. Wählen Sie die folgende Buildkonfiguration aus: **Master/x86/Remote Machine**.

1. Wenn Sie **Remotecomputer auswählen:**
   - Stellen Sie sicher, dass die Adresse auf die Wi-Fi Ihrer HoloLens verweist.
   - Legen Sie die **Authentifizierung auf "Universal (Unencrypted Protocol)" (unverschlüsseltes Protokoll) festgelegt.**
   
1. Erstellen Sie Ihre Lösung.

1. Um die App von Ihrem Entwicklungs-PC auf Ihrer HoloLens bereitstellen möchten, wählen Sie **Remotecomputer aus.** If you already have an existing build on the HoloLens, select **Yes** to install this newer version.  

   ![Remotecomputerbereitstellung für Apps für Microsoft HoloLens in Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. Die Anwendung wird auf Ihrer HoloLens installiert und automatisch gestartet.

Nachdem Sie eine App installiert haben, finden Sie sie in der Liste **"Alle Apps"** **(Alle**  >  **Apps starten).**
