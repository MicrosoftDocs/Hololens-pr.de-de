---
title: Windows Defender Application Control – WDAC
description: Übersicht über die WDAC und die Verwendung zum Verwalten von HoloLens-Geräten.
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
ms.openlocfilehash: d337f9856eaeac433524d7bb8b60e9a24e264b80
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252646"
---
# Windows Defender Application Control – WDAC

WDAC ermöglicht es einem IT-Administrator, seine Geräte so zu konfigurieren, dass die Einführung von apps auf Geräten blockiert wird. Dies unterscheidet sich von den Methoden der Geräte Einschränkung wie dem Kiosk Modus, bei dem dem Benutzer eine Benutzeroberfläche angezeigt wird, auf der die apps auf dem Gerät verborgen sind, die jedoch weiterhin gestartet werden können. Während WDAC implementiert ist, sind die apps weiterhin in der Liste alle apps sichtbar, aber WDAC verhindert, dass diese apps und Prozesse vom Geräte Benutzer gestartet werden können.

Einem Gerät kann mehr als eine WDAC-Richtlinie zugewiesen werden. Wenn mehrere WDAC-Richtlinien auf einem System eingestellt sind, werden die meisten restriktiven wirksam. 

> [!NOTE]
> Wenn Endbenutzer versuchen, eine APP zu starten, die von WDAC blockiert wird, erhalten Sie auf HoloLens keine Benachrichtigung darüber, dass Sie die APP nicht starten können.

Im folgenden finden Sie eine Anleitung für Benutzer, die erfahren möchten, wie Sie [mithilfe von WDAC und Windows PowerShell apps auf HoloLens 2-Geräten mit Microsoft InTune zulassen oder blockieren](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Wenn Benutzer nach Apps suchen, die auf Ihrem Windows 10-PC mit dem ersten Beispiel Schritt installiert sind, müssen Sie möglicherweise einige Versuche Unternehmen, die Ergebnisse einzuschränken.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Wenn Sie den vollständigen Namen des Pakets nicht kennen, müssen Sie möglicherweise ein paar Mal "Get-AppxPackage-Name \ * YourBestGuess \ *" ausführen, um es zu finden. Nachdem Sie den Namen ausgeführt haben, führen Sie "$Package 1 = Get-AppxPackage-Name ist. Paketname" aus.

Wenn Sie beispielsweise Folgendes für Microsoft Edge ausführen, wird mehr als ein Ergebnis zurückgegeben, doch aus dieser Liste können Sie erkennen, dass der vollständige Name Microsoft. MicrosoftEdge ist.

```powershell
Get-AppxPackage -name *edge*
``` 

## Paket Familiennamen für apps auf HoloLens

Im obigen Leitfaden können Sie newPolicy.xml manuell bearbeiten und Regeln für Anwendungen hinzufügen, die nur auf HoloLens mit ihren Paket Familiennamen installiert sind. Manchmal gibt es apps, die Sie verwenden können, die nicht auf dem Desktop-PC vorhanden sind, den Sie der Richtlinie hinzufügen möchten.

Nachfolgend finden Sie eine Liste der häufig verwendeten und In-Box-Apps für HoloLens 2-Geräte.

| App-Name                   | Paket Familien Name                                |
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
| Fotos                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| Einstellungen                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Tipps                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- Das 1-blockierende App-Installationsprogramm blockiert nur die APP-Installer-app und keine apps, die aus anderen Quellen wie dem Microsoft Store oder aus ihrer MDM-Lösung installiert werden.

### So suchen Sie nach einem Paket Familiennamen

Wenn eine APP nicht in dieser Liste enthalten ist, kann ein Benutzer das Geräte Portal verwenden, das mit einem HoloLens 2 verbunden ist, das die APP, die blockiert werden soll, installiert hat, um die PackageRelativeID zu ermitteln, und dann den PackageFamilyName.

1. Installieren Sie die APP auf Ihrem HoloLens 2-Gerät. 
1. Öffnen Sie Einstellungen – > Updates & Security-> für Entwickler, und aktivieren Sie den **Entwicklermodus** und dann **Device Portal**. 
    1. Weitere Informationen hierzu finden Sie hier unter Weitere Informationen zum [Einrichten und Verwenden des Device Portals](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).
1. Wenn Device Portal verbunden ist, navigieren Sie zu **Ansichten** und dann zu **apps**. 
1. Verwenden Sie im Bereich installierte Apps die Dropdownliste, um die installierte App auszuwählen. 
1. Suchen Sie nach dem PackageRelativeID. 
1. Kopieren Sie App-Zeichen vor dem!, diese Zeichen sind Ihre PackageFamilyName.


