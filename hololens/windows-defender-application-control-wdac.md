---
title: Windows Defender Application Control – WDAC
description: Übersicht darüber, was Windows Defender A0 ist und wie sie zum Verwalten von Mixed -Reality-HoloLens-Geräten verwendet wird.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284136"
---
# Windows Defender Application Control – WDAC

WDAC ermöglicht einem IT-Administrator, seine Geräte so zu konfigurieren, dass das Starten von Apps auf Geräten blockiert wird. Dies ist anders als Methoden zur Geräteeinschränkung wie z. B. der Kioskmodus, bei dem dem Benutzer eine Benutzeroberfläche angezeigt wird, die die Apps auf dem Gerät ausblendet, aber dennoch gestartet werden kann. Während WDAC implementiert ist, sind die Apps weiterhin in der Liste "Alle Apps" sichtbar, aber WDAC verhindert, dass diese Apps und Prozesse vom Gerätebenutzer gestartet werden können.

Einem Gerät können mehrere WDAC-Richtlinien zugewiesen werden. Wenn mehrere WDAC-Richtlinien auf einem System festgelegt sind, werden die restriktivsten wirksam. 

> [!NOTE]
> Wenn Endbenutzer versuchen, eine von WDAC blockierte App zu starten, erhalten sie auf HoloLens keine Benachrichtigung darüber, dass sie diese App nicht starten können.

Im folgenden Leitfaden erfahren Benutzer, wie Sie WDAC und Windows PowerShell verwenden, um Apps auf [HoloLens 2-Geräten](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)mit Microsoft Intune zu erlauben oder zu blockieren.

Wenn Benutzer mithilfe des ersten Beispielschritts nach Apps suchen, die auf ihrem Windows 10-PC installiert sind, müssen sie möglicherweise einige Versuche zur Einschr nkung der Ergebnisse machen.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Wenn Sie den vollständigen Namen des Pakets nicht kennen, müssen Sie möglicherweise mehrmals "Get-AppxPackage -name \*YourBestGuess\*" ausführen, um es zu finden. Führen Sie dann nach dem Namen "$package 1 = Get-AppxPackage -name Actual.PackageName" aus.

Wenn Sie z. B. den folgenden Namen für Microsoft Edge ausführen, werden mehr als ein Ergebnis zurückgeben, aber aus dieser Liste können Sie erkennen, dass der vollständige Name, den Sie benötigen, "Microsoft.MicrosoftEdge" ist.

```powershell
Get-AppxPackage -name *edge*
``` 

## Paketfamiliennamen für Apps auf HoloLens

In dem oben verknüpften Handbuch können Sie die newPolicy.xml manuell bearbeiten und Regeln für Anwendungen hinzufügen, die nur auf HoloLens mit ihren Paketfamiliennamen installiert sind. Manchmal gibt es Apps, die Sie möglicherweise verwenden, die sich nicht auf Ihrem Desktop-PC befinden, die Sie der Richtlinie hinzufügen möchten.

Hier ist eine Liste der häufig verwendeten und In-Box für HoloLens 2-Geräte.

| App-Name                   | Paketfamilienname                                |
|----------------------------|----------------------------------------------------|
| 3D-Viewer                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| App-Installer              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</sup>         |
| Calendar                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Kamera                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Feedback-Hub               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Datei-Explorer              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Filme & TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Fotos                     | Microsoft.Windows.Fotos_8wekyb3d8bbwe             |
| Einstellungen                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Tipps                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 – Durch das Blockieren des App-Installers wird nur die App-Installer-App blockiert, und keine Apps, die aus anderen Quellen wie dem Microsoft Store oder aus Ihrer MDM-Lösung installiert wurden.

### So finden Sie einen Paketfamiliennamen

Wenn eine App nicht in dieser Liste enthalten ist, kann ein Benutzer das Geräteportal verwenden, das mit einer HoloLens 2 verbunden ist, die die App installiert hat, die blockiert werden soll, um die PackageRelativeID zu ermitteln und von dort den PackageFamilyName zu erhalten.

1. Installieren Sie die App auf Ihrem HoloLens 2-Gerät. 
1. Öffnen Sie "Einstellungen -> Updates & Sicherheit -> Für Entwickler, **** aktivieren Sie den Entwicklermodus und dann **das Geräteportal.** 
    1. Weitere Informationen zur Einrichtung und Verwendung des Geräteportals finden Sie [hier.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Sobald das Geräteportal verbunden ist, navigieren Sie zu **"Ansichten"** und dann zu **"Apps".** 
1. Wählen Sie im Bereich "Installierte Apps" in der Dropdownliste die installierte App aus. 
1. Suchen Sie die PackageRelativeID. 
1. Kopieren Sie die Zeichen der App vor !, diese Zeichen sind Ihr PackageFamilyName.


