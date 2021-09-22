---
title: Windows Defender Application Control (WDAC)
description: Übersicht darüber, was Windows Defender Anwendungssteuerung ist und wie Sie sie zum Verwalten HoloLens Mixed Reality-Geräten verwenden.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/21/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: efdc57b5e045c1669587ffc46dbe2132b6de6600
ms.sourcegitcommit: 52ed453cace3851fbec0cfcc228fa2a79f1a2fec
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2021
ms.locfileid: "128075384"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Application Control – WDAC

## <a name="overview"></a>Übersicht

Mit WDAC können Sie HoloLens, um den Start von Apps zu blockieren. Dies ist anders als im Kioskmodus, in dem die Benutzeroberfläche die Apps ausblendet, aber trotzdem gestartet werden kann. Mit WDAC können Sie die Apps sehen, aber nicht gestartet werden.

> [!NOTE]
> Wenn Endbenutzer versuchen, eine App zu starten, die von WDAC auf HoloLens wird, werden sie nicht darüber benachrichtigt, dass sie die App nicht starten können.

Einem Gerät können mehrere WDAC-Richtlinien zugewiesen werden. Wenn mehrere WDAC-Richtlinien auf einem System festgelegt sind, werden die restriktivsten wirksam.

Im folgenden Leitfaden erfahren Benutzer, wie [Sie WDAC](/mem/intune/configuration/custom-profile-hololens)und Windows PowerShell zum Zulassen oder Blockieren von Apps auf HoloLens 2-Geräten mit Microsoft Intune.

Wenn Benutzer mithilfe des ersten Beispielschritts nach Apps suchen, die auf ihrem Windows 10-PC installiert sind, müssen sie möglicherweise einige Versuche unternehmen, die Ergebnisse ein wenig zu engen.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
```

Wenn Sie den vollständigen Namen des Pakets nicht kennen, müssen Sie möglicherweise mehrmals "Get-AppxPackage -name YourBestGuess" ausführen, um es \* \* zu finden. Sobald Sie den Namen haben, führen Sie "$package 1 = Get-AppxPackage -name Actual.PackageName" aus.

Wenn Sie beispielsweise den folgenden Code für Microsoft Edge ausführen, werden mehrere Ergebnisse angezeigt. Aus dieser Liste können Sie jedoch erkennen, dass der vollständige Name, den Sie benötigen, Microsoft.MicrosoftEdge ist.

```powershell
Get-AppxPackage -name *edge*
```

## <a name="package-family-names-for-apps-on-hololens"></a>Paketfamiliennamen für Apps auf HoloLens

In der oben verlinkten Anleitung können Sie newPolicy.xml manuell bearbeiten und Regeln für Anwendungen hinzufügen, die nur auf HoloLens mit ihren Paketfamiliennamen installiert sind. Manchmal gibt es Apps, die Sie verwenden können, die sich nicht auf Ihrem Desktop-PC befinden und der Richtlinie hinzugefügt werden sollen.

Im Folgenden finden Sie eine Liste der häufig verwendeten und In-Box-Apps für HoloLens 2 Geräte.

| App-Name                   | Paketfamilienname                                |
|----------------------------|----------------------------------------------------|
| 3D-Betrachter                  | `Microsoft.Microsoft3DViewer_8wekyb3d8bbwe`          |
| App-Installer              | `Microsoft.DesktopAppInstaller_8wekyb3d8bbwe` <sup>1</sup>         |
| Kalender                   | `microsoft.windowscommunicationsapps_8wekyb3d8bbwe`  |
| Kamera                     | `HoloCamera_cw5n1h2txyewy`                          |
| Cortana                    | `Microsoft.549981C3F5F10_8wekyb3d8bbwe`              |
| Dynamics 365-Leitfäden        | `Microsoft.Dynamics365.Guides_8wekyb3d8bbwe`         |
| Dynamics 365 Remote Assist | `Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe`      |
| Feedback-Hub               | `Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe`         |
| Datei-Explorer              | `c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy` |
| E-Mail                       | `microsoft.windowscommunicationsapps_8wekyb3d8bbwe`  |
| Microsoft Store            | `Microsoft.WindowsStore_8wekyb3d8bbwe`               |
| Filme & TV                | `Microsoft.ZuneVideo_8wekyb3d8bbwe`                  |
| OneDrive                   | `microsoft.microsoftskydrive_8wekyb3d8bbwe`          |
| Fotos                     | `Microsoft.Windows.Photos_8wekyb3d8bbwe`             |
| Einstellungen                   | `HolographicSystemSettings_cw5n1h2txyewy`            |
| Tipps                       | `Microsoft.HoloLensTips_8wekyb3d8bbwe`               |

- 1 – App-Installer blockieren, wird nur die App-Installer-App blockiert, nicht die Apps, die aus anderen Quellen wie dem Microsoft Store oder aus Ihrer MDM-Lösung installiert wurden.

### <a name="using-wdac-to-block-new-microsoft-edge"></a>Blockieren des neuen Microsoft Edge mit WDAC

It-Administratoren, die ihre [WDAC-Richtlinie](windows-defender-application-control-wdac.md) aktualisieren möchten, um die neue Microsoft Edge-App zu [blockieren,](hololens-new-edge.md)müssen Ihrer Richtlinie Folgendes hinzufügen.

```xml
<Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" />
```

### <a name="how-to-find-a-package-family-name"></a>Suchen eines Paketfamiliennamens

Wenn eine App nicht in dieser Liste enthalten ist, kann ein Benutzer Geräteportal verwenden, das mit einem HoloLens 2 verbunden ist, auf dem die App installiert wurde, die blockiert werden soll, um packageRelativeID zu bestimmen und von dort den PackageFamilyName zu erhalten.

1. Installieren Sie die App auf Ihrem HoloLens 2 Gerät.

1. Öffnen Einstellungen -> Updates & Security -> Für Entwickler, und aktivieren Sie den **Entwicklermodus** und dann **das Geräteportal.**

   Weitere Informationen und Anweisungen finden Sie unter [Einrichten und Verwenden des Geräteportals hier.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

1. Sobald Geräteportal verbunden ist, navigieren Sie **zu Ansichten** und dann **zu Apps.**

1. Wählen Sie im Bereich Installierte Apps die Dropdownliste aus, um die installierte App auszuwählen.

1. Suchen Sie die PackageRelativeID.

1. Kopieren Sie App-Zeichen vor `!` . Diese Zeichen sind Ihr PackageFamilyName.
