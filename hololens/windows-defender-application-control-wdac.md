---
title: Windows Defender Application Control (WDAC)
description: Übersicht darüber, was Windows Defender Application Control ist und wie sie zum Verwalten HoloLens Mixed Reality-Geräten verwendet wird.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b5c3b55273346f330580b07e5294e7e8e65ea12d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032927"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Application Control – WDAC

## <a name="overview"></a>Übersicht

Mit WDAC können Sie HoloLens konfigurieren, um den Start von Apps zu blockieren. Dies unterscheidet sich vom Kioskmodus, in dem die Benutzeroberfläche die Apps ausblendet, aber trotzdem gestartet werden kann. Mit WDAC können Sie die Apps anzeigen, aber sie können nicht gestartet werden.

> [!NOTE]
> Wenn Endbenutzer versuchen, eine App zu starten, die von WDAC auf HoloLens blockiert wird, werden sie nicht benachrichtigt, wenn sie die App nicht starten können.

Einem Gerät können mehrere WDAC-Richtlinien zugewiesen werden. Wenn mehrere WDAC-Richtlinien auf einem System festgelegt sind, werden die restriktivsten Richtlinien wirksam. 

Im Folgenden erfahren Benutzer, wie Sie [WDAC und Windows PowerShell verwenden, um Apps auf HoloLens 2 Geräten mit Microsoft Intune zuzulassen oder zu blockieren.](/mem/intune/configuration/custom-profile-hololens)

Wenn Benutzer im ersten Beispielschritt nach Apps suchen, die auf ihrem Windows 10 PC installiert sind, müssen sie möglicherweise einige Versuche unternehmen, um die Ergebnisse einzugrenzen.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Wenn Sie den vollständigen Namen des Pakets nicht kennen, müssen Sie möglicherweise mehrmals "Get-AppxPackage -name \* YourBestGuess" \* ausführen, um es zu finden. Sobald Sie den Namen haben, führen Sie "$package 1 = Get-AppxPackage -name Actual.PackageName" aus.

Wenn Sie z. B. den folgenden Code für Microsoft Edge ausführen, werden mehrere Ergebnisse zurückgegeben. Aus dieser Liste können Sie jedoch erkennen, dass der vollständige Name, den Sie benötigen, Microsoft.MicrosoftEdge lautet.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Paketfamiliennamen für Apps auf HoloLens

In der oben verlinkten Anleitung können Sie newPolicy.xml manuell bearbeiten und Regeln für Anwendungen hinzufügen, die nur auf HoloLens mit ihren Paketfamiliennamen installiert sind. Manchmal gibt es Apps, die Sie verwenden können, die sich nicht auf Ihrem Desktop-PC befinden, die Sie der Richtlinie hinzufügen möchten.

Hier finden Sie eine Liste der häufig verwendeten und In-Box Apps für HoloLens 2 Geräte.

| App-Name                   | Paketfamilienname                                |
|----------------------------|----------------------------------------------------|
| 3D-Betrachter                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| App-Installer              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Kalender                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Kamera                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365-Leitfäden        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Feedback-Hub               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Datei-Explorer              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| E-Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Filme & TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Fotos                     | Microsoft. Windows. Photos_8wekyb3d8bbwe             |
| Einstellungen                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Tipps                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1– Durch blockierende App-Installer wird nur die App-Installer-App blockiert, nicht die Apps, die aus anderen Quellen wie dem Microsoft Store oder ihrer MDM-Lösung installiert wurden.

### <a name="how-to-find-a-package-family-name"></a>Suchen eines Paketfamiliennamens

Wenn eine App nicht in dieser Liste enthalten ist, kann ein Benutzer Geräteportal verwenden, der mit einem HoloLens 2 verbunden ist, der die App installiert hat, die blockiert werden soll, um die PackageRelativeID zu bestimmen und von dort den PackageFamilyName abzurufen.

1. Installieren Sie die App auf Ihrem HoloLens 2 Gerät. 
1. Öffnen Sie Einstellungen -> Updates & Security -> Für Entwickler, aktivieren Sie den **Entwicklermodus** und dann das **Geräteportal.** 
    1. Ausführlichere Anweisungen zum [Einrichten und Verwenden des Geräteportals finden Sie hier.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Sobald Geräteportal verbunden ist, navigieren Sie zu **Ansichten** und dann **zu Apps.** 
1. Wählen Sie im Bereich Installierte Apps die Dropdownliste aus, um die installierte App auszuwählen. 
1. Suchen Sie nach PackageRelativeID. 
1. Kopieren Sie App-Zeichen vor `!` , diese Zeichen sind Ihr PackageFamilyName.

