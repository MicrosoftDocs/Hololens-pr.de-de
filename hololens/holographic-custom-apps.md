---
title: Verwalten von benutzerdefinierten Apps für HoloLens
description: Seiten laden benutzerdefinierte apps auf HoloLens. Weitere Informationen zum Installieren und Deinstallieren von holographischen apps.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 07/01/2019
manager: v-miegge
keywords: hololens, querladen, Side Load, Side-Load, Store, UWP, APP, install
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
- HoloLens 2
ms.openlocfilehash: 12c5eedfab580be8acea48c1fc19b56c1ead08ac
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828164"
---
# Verwalten von benutzerdefinierten Apps für HoloLens

HoloLens unterstützt viele vorhandene Anwendungen aus dem Microsoft Store sowie neue apps, die speziell für HoloLens entwickelt wurden. Dieser Artikel befasst sich mit benutzerdefinierten holographischen Anwendungen.  

Weitere Informationen zu Store-Apps finden Sie unter [Verwalten von apps mit dem Store](holographic-store-apps.md).

## Installieren benutzerdefinierter apps

Sie können Ihre eigenen Anwendungen auf HoloLens installieren, indem Sie entweder das Geräte Portal verwenden oder die Apps aus Visual Studio bereitstellen.

### Installieren eines Anwendungspakets mit dem Geräte Portal

1. Herstellen einer Verbindung vom [Geräte Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) zur Ziel HoloLens
1. Navigieren Sie in der linken Navigationsleiste zur Seite " **apps** ".
1. Navigieren Sie unter **App-Paket** zu der AppX-Datei, die Ihrer Anwendung zugeordnet ist.
   > [!IMPORTANT]
   > Stellen Sie sicher, dass Sie auf alle zugehörigen Abhängigkeits-und Zertifikatdateien verweisen.

1. Wählen Sie **Gehe**zu aus.
   ![Installieren des App-Formulars im Windows Device Portal auf Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### Bereitstellen von Microsoft Visual Studio 2015

1. Öffnen Sie die Visual Studio-Projektmappe (SLN-Datei) der app.
1. Öffnen Sie die Projekt **Eigenschaften**.
1. Wählen Sie die folgende Buildkonfiguration aus: **Master/x86/Remote Computer**.
1. Wenn Sie **Remote Computer**auswählen:
   - Stellen Sie sicher, dass die Adresse auf die Wi-Fi-IP-Adresse Ihres HoloLens verweist.
   - Setzen Sie die Authentifizierung auf **universell (unverschlüsseltes Protokoll)**.
1. Erstellen Sie Ihre Lösung.
1. Wenn Sie die APP von Ihrem Entwicklungscomputer auf Ihrem HoloLens bereitstellen möchten, wählen Sie **Remote Computer**aus. Wenn Sie bereits über einen vorhandenen Build auf der HoloLens verfügen, wählen Sie **Ja** aus, um diese neuere Version zu installieren.  

   ![Bereitstellung von Remote Computern für apps zu Microsoft HoloLens in Visual Studio](images/vs2015-remotedeployment.jpg)  
1. Die Anwendung wird auf Ihrem HoloLens installiert und automatisch gestartet.

Nachdem Sie eine APP installiert haben, finden Sie Sie in der Liste **alle apps** (**Start**  >  **alle apps**starten).
