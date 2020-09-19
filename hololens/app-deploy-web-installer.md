---
title: Installieren von apps über das Web Installer
description: Installieren von apps über das Web Installer für das App-Installationsprogramm
keywords: App-Verwaltung, APP, hololens, App-Installationsprogramm, Webinstallation
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 186cbefb2822455dcf922804ea09533b833b8663
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027469"
---
# Installieren von apps von einer Webseite

Benutzer können eine APP direkt von einem Webserver installieren. Dadurch wird das App-Installationsprogramm in Kombination mit einer einfachen Download-und Installations Verteilungsmethode verwendet. 

> [!IMPORTANT]
> Dieses Feature ist derzeit nur avalible in Windows Insider-Builds 19041.1366 +. [Weitere Informationen zum Registrieren von Windows Insider-Builds](hololens-insider.md).

## So richten Sie das ein:
1.  Stellen Sie sicher, dass Ihre APP für die Installation richtig konfiguriert ist.
1.  Führen Sie die folgenden [Schritte aus, um diese auf einer Webseite zu aktivieren](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage). 
1.  Entscheiden Sie sich für eine Zertifikat Bereitstellungsmethode. 
    1.  [Bereitstellungspakete](hololens-provisioning.md) können auf lokale Geräte angewendet werden.
    1.  MDM kann verwendet werden, um [Zertifikate mit Gerätekonfigurationen anzuwenden](https://docs.microsoft.com/mem/intune/protect/certificates-configure).
    1.  Verwenden Sie den [Zertifikat-Manager](hololens-insider.md#certificate-manager)für Geräte. 

## Benutzerfreundlichkeit:
1.  Der Benutzer empfängt und installiert das Zertifikat auf dem Gerät mithilfe einer zuvor ausgewählten Methode. 
1.  Der Benutzer besucht die URL, die aus dem obigen Schritt erstellt wurde.

Die APP wird nun auf dem Gerät installiert. Um die APP zu finden, öffnen Sie das **Startmenü** , und wählen Sie die Schaltfläche **alle apps** aus, um Ihre APP zu finden. 

-   Hilfe zur Problembehandlung dieser Installationsmethode finden Sie unter [Problembehandlung von Problemen mit dem App-Installationsprogramm](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues). 

> [!NOTE]
> Die Benutzeroberfläche wird während des Aktualisierungsvorgangs nicht unterstützt. Daher werden die ShowPrompt-Option auf [dieser Seite](https://docs.microsoft.com/windows/msix/app-installer/update-settings) und die zugehörigen Optionen nicht unterstützt.
