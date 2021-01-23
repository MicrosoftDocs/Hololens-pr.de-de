---
title: So laden und installieren Sie Apps über das HoloLens 2-App-Installationsprogramm
description: Erfahren Sie, wie Sie Apps mit dem App-Installer installieren und über die Benutzeroberfläche laden und installieren.
keywords: App-Verwaltung, App, HoloLens, App-Installer
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9e413963dbf34dd071fc9603487590065b967ee7
ms.sourcegitcommit: af4e222a4f83ab82466a383099897986ddf6b8c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297290"
---
# Installieren von Apps auf HoloLens 2 über das App-Installationsprogramm

> [!NOTE]
> Dieses Feature wurde in [Windows Holographic, Version 20H2 – Dezember 2020 Update, verfügbar gemacht.](hololens-release-notes.md) Stellen Sie sicher, dass Ihr [Gerät für](hololens-update-hololens.md) die Verwendung dieses Features aktualisiert ist.

Wir haben **eine neue Funktion (App-Installer)** hinzugefügt, mit der Sie Anwendungen nahtloser auf Ihren HoloLens 2-Geräten installieren können. Das Feature ist **für nicht verwaltete Geräte standardmäßig aktiviert.** Um Unterbrechungen für Unternehmen zu verhindern, steht das App-Installationsprogramm derzeit nicht für **verwaltete** Geräte zur Verfügung.  

Ein Gerät wird als "verwaltet" betrachtet, **wenn** eine der folgenden Bedingungen zutrifft:

- MdM [Enrolled](hololens-enroll-mdm.md)
- Mit [Bereitstellungspaket konfiguriert](hololens-provisioning.md)
- [Benutzeridentität](hololens-identity.md) ist Azure AD

Sie können jetzt Apps installieren, ohne den Entwicklermodus aktivieren oder das Geräteportal verwenden zu müssen.  Laden Sie (über USB oder Microsoft Edge) das Appx Bundle auf Ihr Gerät herunter, und navigieren Sie zum Appx Bundle im Datei-Explorer, um aufgefordert zu werden, die Installation zu starten.  Alternativ können [Sie eine Installation über eine Webseite initiieren.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)  Genau wie Apps, die Sie aus dem Microsoft Store installieren oder mithilfe der BRANCHEN-App-Bereitstellungsfunktion [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) von MDM querladen, müssen Apps digital mit dem Signierungstool signiert werden, und das zum Signieren verwendete Zertifikat muss vom HoloLens-Gerät als vertrauenswürdig eingestuft werden, bevor die App bereitgestellt werden kann. [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

## Anforderungen

### Für Ihre Geräte:

Dieses Feature ist derzeit in Windows Holographic 20H2-Builds für HoloLens 2-Geräte verfügbar. Stellen Sie sicher, dass alle Geräte, die diese Methode verwenden, [aktualisiert werden.](hololens-update-hololens.md)

### Für Ihre Apps:

Die Lösungskonfiguration Ihrer App muss entweder **Master** oder **Release** sein, da der App Installer Abhängigkeiten aus dem Store verwendet. Weitere Informationen zum Erstellen [von App-Paketen.](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)

Apps, die über diese Methode installiert werden, müssen digital signiert sein. Sie müssen ein Zertifikat zum Signieren der App verwenden. Sie können entweder ein Zertifikat aus der [Liste](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)der vertrauenswürdigen MS-Zertifizierungsstellen erhalten. In diesem Fall müssen Sie keine zusätzlichen Maßnahmen ergreifen. Oder Sie können Ihr eigenes Zertifikat signieren, das Zertifikat muss jedoch auf das Gerät übertragen werden.

- So signieren Sie Apps [mit dem Signieren-Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Zertifikatoptionen:**

- [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Wählen Sie eine Zertifikatbereitstellungsmethode aus.**

- [Bereitstellungspakete können](hololens-provisioning.md) auf lokale Geräte angewendet werden.
- MDM kann verwendet werden, [um Zertifikate mit Gerätekonfigurationen anzuwenden.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)
- Verwenden Sie den [Zertifikat-Manager auf dem Gerät.](certificate-manager.md)

## Installationsmethode

1. Stellen Sie sicher, dass Ihr Gerät nicht als verwaltet betrachtet wird.
1. Überprüfen Sie, ob Ihr HoloLens 2-Gerät eingeschaltet ist und Sie angemeldet sind.
1. Navigieren Sie auf Ihrem PC zu Ihrer benutzerdefinierten App, und kopieren Sie "yourapp.appxbundle" in "yourdevicename\Internal Storage\Downloads".
    Nachdem Sie das Kopieren der Datei abgeschlossen haben, können Sie das Gerät trennen und die Installation später beenden.
1. Öffnen Sie auf Ihrem HoloLens 2-Gerät das **Startmenü,** wählen Sie **alle Apps aus,** und starten Sie die **Datei-Explorer-App.**
1. Navigieren Sie zum Ordner "Downloads". You may need to on the left panel of the app select **This device** first, then navigate to Downloads.
1. Wählen Sie die Datei "yourapp.appxbundle" aus.
1. Das App-Installationsprogramm wird gestartet. Wählen Sie die **Schaltfläche "Installieren"** aus, um Ihre App zu installieren.

Die installierte App wird nach Abschluss der Installation automatisch gestartet.

![Installieren von MRTK-Beispielen über das App-Installationsprogramm](images/hololens-app-installer-picture.jpg)

### Problembehandlung bei Installationen

Wenn ihre App nicht installiert werden konnte, überprüfen Sie folgendes, um eine Problembehandlung zu beheben:

- Ihre App ist entweder ein Master- oder Release-Build.
- Ihr Gerät wird auf einen Build aktualisiert, auf dem dieses Feature verfügbar ist.
- Sie sind [mit dem Internet verbunden.](hololens-network.md)
- Ihre [Endpunkte für den Microsoft Store](hololens-offline.md) sind ordnungsgemäß konfiguriert.  

## Web Installer

Benutzer können eine App direkt von einem Webserver installieren. Dieser Fluss verwendet das App-Installationsprogramm in Kombination mit einer einfachen Download- und Installationsmethode.

### So richten Sie die Webinstallation ein:

1. Stellen Sie sicher, dass Ihre App ordnungsgemäß für die Installation konfiguriert ist.
1. Führen Sie die [folgenden Schritte aus, um die Installation über eine Webseite zu aktivieren.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)

### Endbenutzererfahrung:

1. Der Benutzer empfängt und installiert das Zertifikat auf dem Gerät mithilfe einer zuvor gewählten Methode.
1. Der Benutzer besucht die URL, die aus dem obigen Schritt erstellt wurde.

Die App wird nun auf dem Gerät installiert. Um die App zu finden, öffnen Sie das **Startmenü,** und wählen Sie die Schaltfläche **"Alle Apps"** aus, um Ihre App zu finden.

- Weitere Hilfe zur Problembehandlung bei der Installationsmethode des App-Installers finden Sie unter [Behandeln von Problemen mit dem App-Installer.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> Die Benutzeroberfläche während des Updateprozesses wird nicht unterstützt. Daher werden die Option "ShowPrompt" auf [dieser Seite und](https://docs.microsoft.com/windows/msix/app-installer/update-settings) verwandte Optionen nicht unterstützt.

## Beispiel-Apps

Wenn Sie den App Installer mit einigen Beispiel-Apps testen möchten, sehen Sie sich einige unserer verfügbaren Beispiele an:

- [HUB für MRTK-Beispiele](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [Oberflächen](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [UWP-Beispiel-Apps, die zum Testen verwendet werden können](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
