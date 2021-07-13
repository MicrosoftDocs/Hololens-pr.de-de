---
title: Verwalten benutzerdefinierter Apps für HoloLens (1. Generation)
description: Erfahren Sie, wie Sie benutzerdefinierte holografische Apps auf HoloLens-Geräten installieren, deinstallieren und seitlich laden, indem Geräteportal und Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side load, store, uwp, app, install
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
ms.openlocfilehash: a179032978e1fc062273a6754e3b0a1ad50a5211
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635907"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>Verwalten benutzerdefinierter Apps für HoloLens (1. Generation)

HoloLens unterstützt viele vorhandene Anwendungen aus dem Microsoft Store sowie neue Apps, die speziell für HoloLens. Dieser Artikel konzentriert sich auf benutzerdefinierte holografische Anwendungen.  

Weitere Informationen zu Store-Apps finden Sie unter [Verwalten von Apps mit dem Store.](holographic-store-apps.md)

> [!IMPORTANT]
> Die folgenden Informationen wurden für die HoloLens (1. Generation) erstellt, die zu diesem Zeitpunkt auch als HoloLens Developer Edition bezeichnet wurde. Daher waren das Sideloaden von Apps über das Geräteportal und das Installieren von Apps über Visual Studio dann üblich. Für Unternehmensbereitstellungen wird die Aktivierung des Entwicklermodus, der von beiden Methoden verwendet wird, nicht empfohlen. Wenn Sie an einer sicheren App-Bereitstellungsmethode interessiert sind, lesen Sie unsere [App-Verwaltung: Übersicht](app-deploy-overview.md).
>
> Wenn Sie eine der beiden Entwicklermethode für die App-Installation für HoloLens 2-Geräte suchen, lesen Sie:
>
> - [Geräteportal: Installieren einer App](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Verwenden Visual Studio zum Bereitstellen und Debuggen von Apps](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Installieren von benutzerdefinierten Apps

Sie können Ihre eigenen Anwendungen auf dem HoloLens entweder mithilfe des Geräteportal oder durch Bereitstellen der Apps aus Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Installieren eines Anwendungspakets mit Geräteportal

1. Stellen Sie eine Verbindung [zwischen Geräteportal](/windows/mixed-reality/using-the-windows-device-portal) und dem Zielcomputer HoloLens.

1. Navigieren Sie im linken Navigationsbereich zur **Seite Apps.**

1. Navigieren **Sie unter App-Paket** zu der APPX-Datei, die Ihrer Anwendung zugeordnet ist.

   > [!IMPORTANT]
   > Stellen Sie sicher, dass Sie auf alle zugeordneten Abhängigkeits- und Zertifikatdateien verweisen.

1. Klicken Sie auf **Starten**.

   > [!div class="mx-imgBorder"]
   > ![Installieren des App-Formulars in Windows Geräteportal auf Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Bereitstellung ab Microsoft Visual Studio 2015

1. Öffnen Sie die Projektmappe Visual Studio App (SLN-Datei).

1. Öffnen Sie die Eigenschaften des **Projekts.**

1. Wählen Sie die folgende Buildkonfiguration aus: **Master/x86/Remotecomputer**.

1. Wenn Sie **Remotecomputer auswählen:**
   - Stellen Sie sicher, dass die Adresse auf die Wi-Fi IP-Adresse Ihrer HoloLens.
   - Legen Sie die **Authentifizierung auf Universell (unverschlüsselte Protokoll) fest.**
   
1. Erstellen Sie Ihre Lösung.

1. Wählen Sie Remotecomputer aus, um die App von Ihrem Entwicklungs-PC HoloLens **Ihrem Computer bereitzustellen.** Wenn Sie bereits über einen vorhandenen Build auf dem HoloLens, wählen Sie **Ja aus,** um diese neuere Version zu installieren.  

   ![Remote machine deployment for apps to Microsoft HoloLens in Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. Die Anwendung wird auf Ihrem Computer installiert und automatisch HoloLens.

Nachdem Sie eine App installiert haben, finden Sie  sie in der liste Alle Apps (**Start**  >  **Alle Apps**).
