---
title: Herunterladen und Installieren von apps über das HoloLens 2-App-Installationsprogramm
description: Laden und Installieren von apps über die Benutzeroberfläche
keywords: App-Verwaltung, APP, hololens, App-Installationsprogramm
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 10/26/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4e2256f1086c92cdf0e788ba9dddf5b74a733116
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135526"
---
# Installieren von apps auf HoloLens 2 über das App-Installationsprogramm

In unserer Windows-Insider-Version **fügen wir eine neue Funktion (app-Installationsprogramm) hinzu, mit der Sie Anwendungen nahtlos** auf Ihren HoloLens 2-Geräten installieren können.  Sie können jetzt apps installieren, ohne den Entwicklermodus oder die Verwendung des Geräte Portals aktivieren zu müssen.  Laden Sie einfach (über USB oder durch Edge) das AppX-Paket auf Ihr Gerät herunter, und navigieren Sie im Datei-Explorer zum AppX-Paket, um aufgefordert zu werden, die Installation zu starten.  Alternativ können Sie [eine Installation von einer Webseite aus initiieren](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Genau wie apps, die Sie über den Microsoft Store oder querladen mit der Dienst Bereitstellungsfunktion der Branchen-App für die Branchenanwendung von MDM installieren, müssen apps mit dem [Signatur Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) digital signiert werden, und das [zum Signieren verwendete Zertifikat muss](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) vom HoloLens-Gerät als vertrauenswürdig eingestuft werden, bevor die APP bereitgestellt werden kann.   

Dieses Update richtet sich an den Desktop, [auf dem Sideloading standardmäßig aktiviert ist](https://blogs.windows.com/windows-insider/2019/08/07/announcing-windows-10-insider-preview-build-18956/) .

> [!IMPORTANT]
> Dieses Feature ist derzeit nur avalible in Windows Insider-Builds 19041.1377 +. [Weitere Informationen zum Registrieren von Windows Insider-Builds](hololens-insider.md).

> [!NOTE]
> Für IT-Administratoren, die diese Funktion deaktivieren möchten, verwenden Sie den folgenden Paket Familiennamen als Teil ihrer [WDAC-Richtlinie](windows-defender-application-control-wdac.md). Dadurch wird nur die APP-Installationsprogramm-APP und keine apps blockiert, die aus anderen Quellen wie dem Microsoft Store oder aus ihrer MDM-Lösung installiert wurden.
```
Microsoft.DesktopAppInstaller_8wekyb3d8bbwe
```
> [!NOTE]
> Es wird empfohlen, die [WDAC-Richtlinie](windows-defender-application-control-wdac.md) zum Steuern von apps zu verwenden, wenn Sie jedoch nur Microsoft Store-Apps zulassen möchten, die für die [ApplicationManagement/AllowAllTrustedApps-](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) Richtlinie explizit auf "nicht zulassen" konfiguriert sind, können Apps nur aus dem Microsoft Store installiert werden. 

## Anforderungen

### Für Ihre Geräte: 
> [!NOTE]
> Dieses Feature ist derzeit nur avalible in Windows Insider-Builds 19041.1377 +. [Weitere Informationen zum Registrieren von Windows Insider-Builds](hololens-insider.md).

### Für Ihre apps: 
Die Projektmappenkonfiguration der APP muss entweder **Master** oder **Release** sein, da vom APP-Installationsprogramm Abhängigkeiten aus dem Store verwendet werden. Weitere Informationen finden Sie unter [Erstellen von App-Paketen](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).

Apps, die über diese Methode installiert werden, müssen digital signiert sein. Sie müssen ein Zertifikat zum Signieren der App verwenden. Sie können entweder ein Zertifikat aus der [Liste der vertrauenswürdigen MS-Zertifizierungsstelle](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)anfordern, in diesem Fall müssen Sie keine weiteren Schritte Unternehmen. Oder Sie können ein eigenes Zertifikat signieren, das Zertifikat muss jedoch auf das Gerät übertragen werden. 
- Signieren [von apps mit dem Signatur Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Zertifikatoptionen:** 
- [Liste der vertrauenswürdigen MS-Zertifizierungsstelle](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Entscheiden Sie sich für eine Zertifikat Bereitstellungsmethode.** 
- [Bereitstellungspakete](hololens-provisioning.md) können auf lokale Geräte angewendet werden.
- MDM kann verwendet werden, um [Zertifikate mit Gerätekonfigurationen anzuwenden](https://docs.microsoft.com/mem/intune/protect/certificates-configure).
- Verwenden Sie den [Zertifikat-Manager](hololens-insider.md#certificate-manager)für Geräte. 

## Installationsmethode

1.  Stellen Sie sicher, dass Ihr HoloLens 2-Gerät eingeschaltet ist und Sie angemeldet sind.
1.  Navigieren Sie auf Ihrem PC zu Ihrer benutzerdefinierten APP, und kopieren Sie yourapp. appxbundle nach yourdevicename\Internal Storage\Downloads. 
    Nachdem Sie Ihre Datei fertig kopiert haben, können Sie Ihr Gerät trennen und die Installation später abschließen.
1.  Öffnen Sie auf Ihrem HoloLens 2-Gerät das **Startmenü**, wählen Sie **alle apps** aus, und starten Sie die **Datei-Explorer** -app.
1.  Navigieren Sie zum Ordner Downloads. Möglicherweise müssen Sie auf der linken Seite der APP zuerst **dieses Gerät** auswählen und dann zu Downloads navigieren.
1.  Wählen Sie die Datei "yourapp. appxbundle" aus. 
1.  Das App-Installationsprogramm wird gestartet. Wählen Sie die Schaltfläche **Installieren** aus, um Ihre APP zu installieren. 

Die installierte APP wird nach Abschluss der Installation automatisch gestartet. 

![Installieren von MRTK-Beispielen über das App-Installationsprogramm](images/hololens-app-installer-picture.jpg)

### Problembehandlung bei Installationen
Wenn Ihre APP nicht installiert werden konnte, prüfen Sie Folgendes:
-   Ihre APP ist entweder ein Master-oder Release-Build.
- Ihr Gerät wird auf einen Build aktualisiert, auf dem dieses Feature verfügbar ist. 
-   Sie sind [mit dem Internet verbunden](hololens-network.md).
-   Ihre [Endpunkte für den Microsoft Store](hololens-offline.md) sind ordnungsgemäß konfiguriert.  

## Web Installer

Benutzer können eine APP direkt von einem Webserver installieren. Dadurch wird das App-Installationsprogramm in Kombination mit einer einfachen Download-und Installations Verteilungsmethode verwendet. 

### Einrichten der Web-Installation:
1.  Stellen Sie sicher, dass Ihre APP für die Installation richtig konfiguriert ist.
1.  Führen Sie die folgenden [Schritte aus, um diese auf einer Webseite zu aktivieren](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage). 

### Benutzerfreundlichkeit:
1. Der Benutzer empfängt und installiert das Zertifikat auf dem Gerät mithilfe einer zuvor ausgewählten Methode. 
1. Der Benutzer besucht die URL, die aus dem obigen Schritt erstellt wurde.

Die APP wird nun auf dem Gerät installiert. Um die APP zu finden, öffnen Sie das **Startmenü** , und wählen Sie die Schaltfläche **alle apps** aus, um Ihre APP zu finden. 

-   Hilfe zur Problembehandlung dieser Installationsmethode finden Sie unter [Problembehandlung von Problemen mit dem App-Installationsprogramm](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues). 

> [!NOTE]
> Die Benutzeroberfläche wird während des Aktualisierungsvorgangs nicht unterstützt. Daher werden die ShowPrompt-Option auf [dieser Seite](https://docs.microsoft.com/windows/msix/app-installer/update-settings) und die zugehörigen Optionen nicht unterstützt.

## Beispiel-apps

Wenn Sie dies mit einigen Beispiel-apps ausprobieren möchten, schauen Sie sich einige unserer verfügbaren Beispiele an:
- [MRTK examples Hub](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [Flächen](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [UWP-Beispiel-apps, die für Tests verwendet werden können](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
