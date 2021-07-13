---
title: Windows Defender Application Control – WDAC
description: Übersicht darüber, was Windows Defender Application Control ist und wie sie zum Verwalten HoloLens Mixed Reality-Geräten verwendet wird.
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
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639929"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Application Control – WDAC

Mit WDAC kann ein IT-Administrator seine Geräte so konfigurieren, dass der Start von Apps auf Geräten blockiert wird. Dies unterscheidet sich von Methoden der Geräteeinschränkung wie dem Kioskmodus, in dem dem Benutzer eine Benutzeroberfläche angezeigt wird, die die Apps auf dem Gerät ausblendet, aber trotzdem gestartet werden kann. Während WDAC implementiert ist, sind die Apps weiterhin in der Liste Alle Apps sichtbar, aber WDAC verhindert, dass diese Apps und Prozesse vom Gerätebenutzer gestartet werden können.

Einem Gerät können mehrere WDAC-Richtlinien zugewiesen werden. Wenn mehrere WDAC-Richtlinien auf einem System festgelegt sind, werden die restriktivsten Richtlinien wirksam. 

> [!NOTE]
> Wenn Endbenutzer versuchen, eine Von WDAC blockierte App zu starten, erhalten sie auf HoloLens keine Benachrichtigung darüber, dass sie diese App nicht starten kann.

Im Folgenden erfahren Benutzer, wie Sie [WDAC und Windows PowerShell verwenden, um Apps auf HoloLens 2 Geräten mit Microsoft Intune zuzulassen oder zu blockieren.](/mem/intune/configuration/custom-profile-hololens)

Wenn Benutzer im ersten Beispielschritt auf ihrem Windows 10 PC nach installierten Apps suchen, müssen sie möglicherweise einige Versuche unternehmen, um die Ergebnisse einzugrenzen.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Wenn Sie den vollständigen Namen des Pakets nicht kennen, müssen Sie möglicherweise mehrmals "Get-AppxPackage -name \* YourBestGuess" \* ausführen, um es zu finden. Sobald Sie den Namen haben, führen Sie "$package 1 = Get-AppxPackage -name Actual.PackageName" aus.

Wenn Sie z. B. folgendes für Microsoft Edge ausführen, werden mehrere Ergebnisse zurückgegeben. Aus dieser Liste können Sie jedoch erkennen, dass der vollständige Name, den Sie benötigen, Microsoft.MicrosoftEdge lautet.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Paketfamiliennamen für Apps auf HoloLens

In der oben verlinkten Anleitung können Sie newPolicy.xml manuell bearbeiten und Regeln für Anwendungen hinzufügen, die nur auf HoloLens mit ihren Paketfamiliennamen installiert sind. Manchmal gibt es Apps, die Sie verwenden können, die sich nicht auf Ihrem Desktop-PC befinden, die Sie der Richtlinie hinzufügen möchten.

Hier finden Sie eine Liste der häufig verwendeten und In-Box Apps für HoloLens 2 Geräte.

| App-Name                   | Paketfamilienname                                |
|----------------------------|----------------------------------------------------|
| 3D-Viewer                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| App-Installer              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Calendar                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
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

- 1– Durch blockierende App-Installer wird nur die App-Installer-App blockiert, nicht die Apps, die aus anderen Quellen wie dem Microsoft Store oder aus Ihrer MDM-Lösung installiert wurden.

### <a name="how-to-find-a-package-family-name"></a>Suchen eines Paketfamiliennamens

Wenn eine App nicht in dieser Liste enthalten ist, kann ein Benutzer Geräteportal verwenden, der mit einem HoloLens 2 verbunden ist, der die App installiert hat, die blockiert werden soll, um die PackageRelativeID zu bestimmen und von dort den PackageFamilyName abzurufen.

1. Installieren Sie die App auf Ihrem HoloLens 2 Gerät. 
1. Öffnen Sie Einstellungen -> Updates & Security -> Für Entwickler, aktivieren Sie den **Entwicklermodus** und dann das **Geräteportal.** 
    1. Ausführlichere Anweisungen zum [Einrichten und Verwenden des Geräteportals finden Sie hier.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Sobald Geräteportal verbunden ist, navigieren Sie zu **Ansichten** und dann **zu Apps.** 
1. Wählen Sie im Bereich Installierte Apps die Dropdownliste aus, um die installierte App auszuwählen. 
1. Suchen Sie packageRelativeID. 
1. Kopieren Sie App-Zeichen vor !. Diese Zeichen sind Ihr PackageFamilyName.


