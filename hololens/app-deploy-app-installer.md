---
title: Herunterladen und Installieren von apps über das HoloLens 2-App-Installationsprogramm
description: Laden und Installieren von apps über die Benutzeroberfläche
keywords: App-Verwaltung, APP, hololens, App-Installationsprogramm
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
ms.openlocfilehash: e52cc2f031c284b619c61ffa04f259f76397faf5
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253092"
---
# Installieren von apps auf HoloLens 2 über das App-Installationsprogramm

Wir **fügen eine neue Funktion (app-Installationsprogramm) hinzu, mit der Sie Anwendungen nahtlos** auf Ihren HoloLens 2-Geräten installieren können. Das Feature ist **für nicht verwaltete Geräte standardmäßig aktiviert**. Um Unterbrechungen von Unternehmen zu verhindern, steht das App-Installationsprogramm derzeit **nicht für verwaltete Geräte zur Verfügung** .  

> [!NOTE]
> Dieses Feature wurde in [Windows holographisch, Version 20H2 – Dezember 2020-Update](hololens-release-notes.md)zur Verfügung gestellt. Stellen Sie sicher, dass Ihr Gerät [aktualisiert](hololens-update-hololens.md) wurde, um dieses Feature zu verwenden.

Wir haben **eine neue Funktion (app-Installationsprogramm) hinzugefügt, mit der Sie Anwendungen nahtlos** auf Ihren HoloLens 2-Geräten installieren können. Das Feature ist **für nicht verwaltete Geräte standardmäßig aktiviert**. Um Unterbrechungen von Unternehmen zu verhindern, steht das App-Installationsprogramm derzeit **nicht für verwaltete Geräte zur Verfügung** .  

Ein Gerät gilt als "verwaltet", **Wenn eine der folgenden** Bedingungen zutrifft:

- MDM [registriert](hololens-enroll-mdm.md)
- Mit [Bereitstellungspaket](hololens-provisioning.md) konfiguriert
- Benutzer [Identität](hololens-identity.md) ist Azure AD

Sie können jetzt apps installieren, ohne den Entwicklermodus oder die Verwendung des Geräte Portals aktivieren zu müssen.  Laden Sie (über USB oder über Microsoft Edge) das AppX-Paket auf Ihr Gerät herunter, und navigieren Sie im Datei-Explorer zum AppX-Paket, um aufgefordert zu werden, die Installation zu starten.  Alternativ können Sie [eine Installation von einer Webseite aus initiieren](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Genau wie apps, die Sie über den Microsoft Store oder querladen mit der Dienst Bereitstellungsfunktion der Branchen-App für die Branchenanwendung von MDM installieren, müssen apps mit dem [Signatur Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) digital signiert werden, und das [zum Signieren verwendete Zertifikat muss](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) vom HoloLens-Gerät als vertrauenswürdig eingestuft werden, bevor die APP bereitgestellt werden kann.

## Anforderungen

### Für Ihre Geräte:

 Das Feature steht derzeit in Windows holographischen 20H2-Builds für HoloLens 2-Geräte zur Verfügung. Stellen Sie sicher, dass alle Geräte, die diese Methode verwenden, [aktualisiert](hololens-update-hololens.md)werden.

### Für Ihre apps: 
Die Projektmappenkonfiguration der APP muss entweder **Master** oder **Release** sein, da vom APP-Installationsprogramm Abhängigkeiten aus dem Store verwendet werden. Weitere Informationen finden Sie unter [Erstellen von App-Paketen](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).

Apps, die über diese Methode installiert werden, müssen digital signiert sein. Sie müssen ein Zertifikat zum Signieren der App verwenden. Sie können entweder ein Zertifikat aus der [Liste der vertrauenswürdigen MS-Zertifizierungsstelle](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)anfordern, in diesem Fall müssen Sie keine weiteren Schritte Unternehmen. Oder Sie können ein eigenes Zertifikat signieren, das Zertifikat muss jedoch auf das Gerät übertragen werden.

- Signieren [von apps mit dem Signatur Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Zertifikatoptionen:**

- [Liste der vertrauenswürdigen MS-Zertifizierungsstelle](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Entscheiden Sie sich für eine Zertifikat Bereitstellungsmethode.**

- [Bereitstellungspakete](hololens-provisioning.md) können auf lokale Geräte angewendet werden.
- MDM kann verwendet werden, um [Zertifikate mit Gerätekonfigurationen anzuwenden](https://docs.microsoft.com/mem/intune/protect/certificates-configure).
- Verwenden Sie den [Zertifikat-Manager](certificate-manager.md)für Geräte.

## Installationsmethode

1. Überprüfen Sie, ob Ihr Gerät als verwaltet angesehen wird.
1. Vergewissern Sie sich, dass Ihr HoloLens 2-Gerät eingeschaltet ist und Sie angemeldet sind.
1. Navigieren Sie auf Ihrem PC zu Ihrer benutzerdefinierten APP, und kopieren Sie yourapp. appxbundle nach yourdevicename\Internal Storage\Downloads.
    Nachdem Sie das Kopieren der Datei abgeschlossen haben, können Sie Ihr Gerät trennen und die Installation später abschließen.
1. Öffnen Sie auf Ihrem HoloLens 2-Gerät das **Startmenü**, wählen Sie **alle apps** aus, und starten Sie die **Datei-Explorer** -app.
1. Navigieren Sie zum Ordner Downloads. Möglicherweise müssen Sie auf der linken Seite der APP zuerst **dieses Gerät** auswählen und dann zu Downloads navigieren.
1. Wählen Sie die Datei "yourapp. appxbundle" aus.
1. Das App-Installationsprogramm wird gestartet. Wählen Sie die Schaltfläche **Installieren** aus, um Ihre APP zu installieren.

Die installierte APP wird nach Abschluss der Installation automatisch gestartet.

![Installieren von MRTK-Beispielen über das App-Installationsprogramm](images/hololens-app-installer-picture.jpg)

### Problembehandlung bei Installationen

Wenn Ihre APP nicht installiert werden konnte, prüfen Sie die folgenden Schritte zur Problembehandlung:

- Ihre APP ist entweder ein Master-oder Release-Build.
- Ihr Gerät wird auf einen Build aktualisiert, auf dem dieses Feature verfügbar ist.
- Sie sind [mit dem Internet verbunden](hololens-network.md).
- Ihre [Endpunkte für den Microsoft Store](hololens-offline.md) sind ordnungsgemäß konfiguriert.  

## Web Installer

Benutzer können eine APP direkt von einem Webserver installieren. Dieser Flow nutzt das App-Installationsprogramm kombiniert mit einer einfachen Download-und Installations Verteilungsmethode.

### Einrichten der Web-Installation:

1. Stellen Sie sicher, dass Ihre APP für die Installation richtig konfiguriert ist.
1. Führen Sie die folgenden [Schritte aus, um die Installation von einer Webseite aus zu aktivieren](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).

### Benutzerfreundlichkeit:

1. Der Benutzer empfängt und installiert das Zertifikat auf dem Gerät mithilfe einer zuvor ausgewählten Methode.
1. Der Benutzer besucht die URL, die aus dem obigen Schritt erstellt wurde.

Die APP wird nun auf dem Gerät installiert. Um die APP zu finden, öffnen Sie das **Startmenü** , und wählen Sie die Schaltfläche **alle apps** aus, um Ihre APP zu finden.

- Weitere Hilfe zur Problembehandlung der Installationsmethode des App-Installationsprogramms finden Sie unter [Behandeln von Problemen](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)mit dem App-Installationsprogramm.

> [!NOTE]
> Die Benutzeroberfläche wird während des Aktualisierungsvorgangs nicht unterstützt. Daher werden die ShowPrompt-Option auf [dieser Seite](https://docs.microsoft.com/windows/msix/app-installer/update-settings) und die zugehörigen Optionen nicht unterstützt.

## Beispiel-apps

Wenn Sie das App-Installationsprogramm mit einigen Beispiel-Apps testen möchten, schauen Sie sich einige der verfügbaren Beispiele an:

- [MRTK examples Hub](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [Flächen](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [UWP-Beispiel-apps, die für Tests verwendet werden können](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
