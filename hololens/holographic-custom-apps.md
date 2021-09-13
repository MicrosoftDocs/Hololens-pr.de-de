---
title: Verwalten von benutzerdefinierten Apps für HoloLens (1. Generation)
description: Erfahren Sie, wie Sie benutzerdefinierte holografische Apps mithilfe der Geräteportal und Visual Studio auf HoloLens Geräten installieren, deinstallieren und querladen.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side-load, store, uwp, app, install
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
ms.openlocfilehash: b6769c36f821ee3619ac9b62efd637ac561192bb
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032506"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>Verwalten von benutzerdefinierten Apps für HoloLens (1. Generation)

HoloLens unterstützt viele vorhandene Anwendungen aus dem Microsoft Store sowie neue Apps, die speziell für HoloLens erstellt wurden. Dieser Artikel konzentriert sich auf benutzerdefinierte holografische Anwendungen.  

Weitere Informationen zu Store-Apps finden Sie unter [Verwalten von Apps mit dem Store.](holographic-store-apps.md)

> [!IMPORTANT]
> Die folgenden Informationen wurden für die HoloLens (1. Generation) erstellt, die zu diesem Zeitpunkt auch als HoloLens Developer Edition bezeichnet wurde. Daher war das Querladen von Apps über das Geräteportal und das Installieren von Apps über Visual Studio dann üblich. Für Unternehmensbereitstellungen wird nicht empfohlen, den Entwicklermodus zu aktivieren, der von beiden Methoden verwendet wird. Wenn Sie an einer sicheren App-Bereitstellungsmethode interessiert sind, lesen Sie unsere [App-Verwaltung: Übersicht](app-deploy-overview.md).
>
> Wenn Sie nach einer der Entwicklermethoden für die App-Installation für HoloLens 2 Geräte suchen, finden Sie weitere Informationen unter:
>
> - [Geräteportal: Installieren einer App](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Verwenden von Visual Studio zum Bereitstellen und Debuggen von Apps](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Installieren von benutzerdefinierten Apps

Sie können Ihre eigenen Anwendungen auf HoloLens installieren, indem Sie entweder die Geräteportal verwenden oder die Apps über Visual Studio bereitstellen.

### <a name="installing-an-application-package-with-the-device-portal"></a>Installieren eines Anwendungspakets mit dem Geräteportal

1. Stellen Sie eine Verbindung zwischen [Geräteportal und](/windows/mixed-reality/using-the-windows-device-portal) dem Ziel-HoloLens her.

1. Navigieren Sie im linken Navigationsbereich zur Seite **Apps.**

1. Navigieren Sie unter **App-Paket** zur APPX-Datei, die Ihrer Anwendung zugeordnet ist.

   > [!IMPORTANT]
   > Stellen Sie sicher, dass Sie auf alle zugeordneten Abhängigkeits- und Zertifikatdateien verweisen.

1. Klicken Sie auf **Starten**.

   > [!div class="mx-imgBorder"]
   > ![Installieren Sie das App-Formular in Windows Geräteportal auf Microsoft HoloLens.](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Bereitstellen ab Microsoft Visual Studio 2015

1. Öffnen Sie die Visual Studio Projektmappe Ihrer App (SLN-Datei).

1. Öffnen Sie die **Eigenschaften** des Projekts.

1. Wählen Sie die folgende Buildkonfiguration aus: **Master/x86/Remotecomputer**.

1. Wenn Sie **Remotecomputer** auswählen:
   - Stellen Sie sicher, dass die Adresse auf die Wi-Fi IP-Adresse Ihrer HoloLens verweist.
   - Legen Sie die Authentifizierung auf **Universal (Unverschlüsseltes Protokoll)** fest.
   
1. Erstellen Sie Ihre Lösung.

1. Wählen Sie **Remotecomputer** aus, um die App von Ihrem Entwicklungs-PC auf Ihrem HoloLens bereitzustellen. Wenn Sie bereits über einen Build auf dem HoloLens verfügen, wählen Sie **Ja** aus, um diese neuere Version zu installieren.  

   ![Remotecomputerbereitstellung für Apps, die in Visual Studio Microsoft HoloLens.](images/vs2015-remotedeployment.jpg)  
   
1. Die Anwendung wird auf Ihrem HoloLens installiert und automatisch gestartet.

Nachdem Sie eine App installiert haben, finden Sie sie in der **liste Alle Apps** (**Start**  >  **Alle Apps**).
