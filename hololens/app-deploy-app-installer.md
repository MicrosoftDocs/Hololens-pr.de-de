---
title: Querladen und Installieren von Apps über HoloLens 2 App-Installer
description: Erfahren Sie, wie Sie Apps mit dem App-Installationsprogramm installieren und Probleme beheben und Apps über die Benutzeroberfläche querladen und installieren.
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
ms.openlocfilehash: 071dfb3b211928c561fc84754dd7ed4d64886f61
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032490"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>Installieren von Apps auf HoloLens 2 über App-Installer

> [!NOTE]
> Dieses Feature wurde in [Windows Holographic, Version 20H2 – Dezember 2020 Update](hololens-release-notes.md)verfügbar gemacht. Stellen Sie sicher, dass Ihr Gerät [aktualisiert](hololens-update-hololens.md) wurde, um dieses Feature zu verwenden.

Wir haben **eine neue Funktion (App-Installer) hinzugefügt, mit** der Sie Anwendungen nahtloser auf Ihren HoloLens 2 Geräten installieren können. Das Feature ist **für nicht verwaltete Geräte standardmäßig aktiviert.** Um Unterbrechungen für Unternehmen zu verhindern, ist das App-Installationsprogramm **derzeit nicht für verwaltete Geräte verfügbar.**  

Ein Gerät gilt als "verwaltet", wenn **eine** der folgenden Punkte zutrifft:

- MDM [registriert](hololens-enroll-mdm.md)
- Konfiguriert mit [dem Bereitstellungspaket](hololens-provisioning.md)
- Die [Benutzeridentität](hololens-identity.md) ist Azure AD

Sie können apps jetzt installieren, ohne den Entwicklermodus aktivieren oder Geräteportal verwenden zu müssen.  Laden Sie (über USB oder über Microsoft Edge) das Appx-Paket auf Ihr Gerät herunter, und navigieren Sie im Datei-Explorer zum Appx-Paket, um aufgefordert zu werden, die Installation zu starten.  Alternativ können Sie [eine Installation über eine Webseite initiieren.](/windows/msix/app-installer/installing-windows10-apps-web) Genau wie Apps, die Sie über die Microsoft Store installieren oder mithilfe der BEREITSTELLUNGsfunktion für branchenspezifische Apps von MDM querladen, müssen Apps mit dem [Signierungstool](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) digital signiert werden, und das zum Signieren verwendete Zertifikat muss vom HoloLens Gerät [vertrauenswürdig sein,](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) bevor die App bereitgestellt werden kann.

## <a name="requirements"></a>Requirements (Anforderungen)

### <a name="for-your-devices"></a>Für Ihre Geräte:

Dieses Feature ist derzeit in Windows Holographic 20H2-Builds für HoloLens 2 Geräte verfügbar. Stellen Sie sicher, dass alle Geräte, die diese Methode verwenden, [aktualisiert](hololens-update-hololens.md)werden.

### <a name="for-your-apps"></a>Für Ihre Apps:

Die Projektmappenkonfiguration Ihrer App muss entweder **Master** oder **Release** sein, da der App-Installer Abhängigkeiten aus dem Speicher verwendet. Weitere Informationen finden Sie unter [Erstellen von App-Paketen.](/windows/msix/app-installer/create-appinstallerfile-vs)

Apps, die über diese Methode installiert werden, müssen digital signiert sein. Sie müssen ein Zertifikat verwenden, um die App zu signieren. Sie können entweder ein Zertifikat aus der Liste der [vertrauenswürdigen](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)MS-Zertifizierungsstellen abrufen. In diesem Fall müssen Sie keine zusätzlichen Maßnahmen ergreifen. Sie können auch Ihr eigenes Zertifikat signieren, aber dieses Zertifikat muss per Push auf das Gerät übertragen werden.

- Signieren von Apps [mit dem Signieren-Tool](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Zertifikatoptionen:**

- [Liste vertrauenswürdiger MS-Zertifizierungsstellen](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Wählen Sie eine Zertifikatbereitstellungsmethode aus.**

- [Bereitstellungspakete](hololens-provisioning.md) können auf lokale Geräte angewendet werden.
- MDM kann verwendet werden, um [Zertifikate mit Gerätekonfigurationen anzuwenden.](/mem/intune/protect/certificates-configure)
- Verwenden Sie den auf dem Gerät [Zertifikat-Manager](certificate-manager.md).

## <a name="installation-method"></a>Installationsmethode

1. Vergewissern Sie sich, dass Ihr Gerät nicht als verwaltet angesehen wird.
1. Überprüfen Sie, ob Ihr HoloLens 2 Gerät eingeschaltet ist und Sie angemeldet sind.
1. Navigieren Sie auf Ihrem PC zu Ihrer benutzerdefinierten App, und kopieren Sie "app.appxbundle" in "IhrGerätename\Interne Storage\Downloads".
    Nachdem Sie das Kopieren der Datei abgeschlossen haben, können Sie ihr Gerät trennen und die Installation später beenden.
1. Wählen Sie auf Ihrem HoloLens 2 Gerät Das **Startmenü** öffnen aus, wählen Sie **Alle Apps** aus, und starten Sie die **Datei-Explorer-App.**
1. Navigieren Sie zum Ordner Downloads. Möglicherweise müssen Sie im linken Bereich der App zuerst **Dieses Gerät** auswählen und dann zu Downloads navigieren.
1. Wählen Sie die Datei yourapp.appxbundle aus.
1. Die App-Installer wird gestartet. Wählen Sie die Schaltfläche **Installieren** aus, um Ihre App zu installieren.

Die installierte App wird nach Abschluss der Installation automatisch gestartet.

![Installieren von MRTK-Beispielen über App-Installer.](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>Problembehandlung bei Installationen

Wenn ihre App nicht installiert werden konnte, überprüfen Sie Folgendes, um Probleme zu beheben:

- Ihre App ist entweder ein Master- oder Releasebuild.
- Ihr Gerät wird auf einen Build aktualisiert, auf dem dieses Feature verfügbar ist.
- Sie sind [mit dem Internet verbunden.](hololens-network.md)
- Ihre [Endpunkte für die Microsoft Store](hololens-offline.md) sind ordnungsgemäß konfiguriert.  

## <a name="web-installer"></a>Webinstaller

Benutzer können eine App direkt von einem Webserver installieren. Für diesen Flow wird die App-Installer in Kombination mit einer einfachen Verteilungsmethode zum Herunterladen und Installieren verwendet.

### <a name="how-to-set-up-web-install"></a>Einrichten der Webinstallation:

1. Stellen Sie sicher, dass Ihre App ordnungsgemäß für die Installation konfiguriert ist.
1. Führen Sie die folgenden [Schritte aus, um die Installation über eine Webseite zu aktivieren.](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)

### <a name="end-user-experience"></a>Endbenutzererfahrung:

1. Der Benutzer empfängt und installiert das Zertifikat auf dem Gerät mithilfe einer zuvor ausgewählten Methode.
1. Der Benutzer besucht die URL, die aus dem obigen Schritt erstellt wurde.

Die App wird nun auf dem Gerät installiert. Um die App zu finden, öffnen Sie die **Startmenü,** und wählen Sie die Schaltfläche **Alle Apps** aus, um Ihre App zu finden.

- Weitere Hilfe zur Problembehandlung bei der Installationsmethode des App-Installers finden Sie unter Beheben von Problemen mit dem [App-Installationsprogramm.](/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> Die Benutzeroberfläche während des Updateprozesses wird nicht unterstützt. Daher werden die Option ShowPrompt auf [dieser Seite](/windows/msix/app-installer/update-settings) und verwandte Optionen nicht unterstützt.

## <a name="sample-apps"></a>Beispiel-Apps

Probieren Sie die App-Installer mit einer unserer verfügbaren Beispiel-Apps aus. 
> [!div class="nextstepaction"]
> [Beispiel-Apps](/windows/mixed-reality/develop/features-and-samples)
