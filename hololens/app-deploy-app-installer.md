---
title: Side load and Install Apps via HoloLens 2 App-Installer
description: Erfahren Sie, wie Sie Apps mit dem App-Installationsprogramm installieren und Probleme beheben und Apps über die Benutzeroberfläche laden und installieren.
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
ms.openlocfilehash: 8f236ee27903069b65d3ded8eb7a1f37c65f535e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635584"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>Installieren von Apps auf HoloLens 2 über App-Installer

> [!NOTE]
> Dieses Feature wurde in [holografischer Windows Version 20H2 – Update vom Dezember 2020 zur Verfügung gestellt.](hololens-release-notes.md) Stellen Sie sicher, dass Ihr [Gerät aktualisiert wurde,](hololens-update-hololens.md) um dieses Feature zu verwenden.

Wir haben **eine neue Funktion (App-Installer)** hinzugefügt, mit der Sie Anwendungen nahtloser auf Ihren HoloLens 2 installieren können. Das Feature ist standardmäßig **für nicht verwaltete Geräte aktiviert.** Um Unterbrechungen für Unternehmen zu verhindern, ist das App-Installationsprogramm derzeit nicht für **verwaltete** Geräte verfügbar.  

Ein Gerät gilt als "verwaltet", **wenn** eine der folgenden Bedingungen zutrifft:

- MDM [registriert](hololens-enroll-mdm.md)
- Mit [Bereitstellungspaket konfiguriert](hololens-provisioning.md)
- Die [Benutzeridentität](hololens-identity.md) ist Azure AD

Sie können Apps jetzt installieren, ohne den Entwicklermodus zu aktivieren oder Geräteportal.  Laden Sie (über USB oder über Microsoft Edge) das Appx Bundle auf Ihr Gerät herunter, und navigieren Sie im Datei-Explorer zum Appx Bundle, um zum Starten der Installation aufgefordert zu werden.  Alternativ können Sie [eine Installation über eine Webseite initiieren.](/windows/msix/app-installer/installing-windows10-apps-web) Genau wie Apps, die Sie über die Microsoft Store installieren oder mithilfe der BEREITSTELLUNGsfunktion für branchenseitige Apps [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) von MDM sideload verwenden, müssen Apps digital mit dem Signierungstool signiert werden, und das zertifikat, das zum Signieren verwendet wird, muss vom HoloLens-Gerät als vertrauenswürdig eingestuft werden, bevor die App bereitgestellt werden kann. [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

## <a name="requirements"></a>Anforderungen

### <a name="for-your-devices"></a>Für Ihre Geräte:

Dieses Feature ist derzeit in Windows Holographic 20H2-Builds für HoloLens 2 verfügbar. Stellen Sie sicher, dass alle Geräte, die diese Methode verwenden, [aktualisiert werden.](hololens-update-hololens.md)

### <a name="for-your-apps"></a>Für Ihre Apps:

Die Projektmappenkonfiguration Ihrer App muss entweder **"Master"** oder **"Release"** sein, da die App-Installer Abhängigkeiten aus dem Speicher verwendet. Weitere Informationen zum Erstellen [von App-Paketen finden Sie hier.](/windows/msix/app-installer/create-appinstallerfile-vs)

Apps, die über diese Methode installiert werden, müssen digital signiert werden. Sie müssen ein Zertifikat verwenden, um die App zu signieren. Sie können entweder ein Zertifikat aus der Liste der [vertrauenswürdigen](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)MS-Zertifizierungsstellen erhalten. In diesem Fall müssen Sie keine zusätzlichen Maßnahmen ergreifen. Oder Sie können Ihr eigenes Zertifikat signieren, aber dieses Zertifikat muss auf das Gerät übertragen werden.

- Signieren von Apps [mit dem Signieren-Tool](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Zertifikatoptionen:**

- [Liste der vertrauenswürdigen MS-Zertifizierungsstellen](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Wählen Sie eine Zertifikatbereitstellungsmethode aus.**

- [Bereitstellungspakete](hololens-provisioning.md) können auf lokale Geräte angewendet werden.
- MDM kann verwendet werden, [um Zertifikate mit Gerätekonfigurationen anzuwenden.](/mem/intune/protect/certificates-configure)
- Verwenden Sie den [Zertifikat-Manager auf dem Gerät.](certificate-manager.md)

## <a name="installation-method"></a>Installationsmethode

1. Überprüfen Sie, ob Ihr Gerät nicht als verwaltet gilt.
1. Überprüfen Sie, HoloLens 2 gerät eingeschaltet ist und Sie angemeldet sind.
1. Navigieren Sie auf Ihrem PC zu Ihrer benutzerdefinierten App, und kopieren Sie Yourapp.appxbundle in "IhrGerätename\Interner Storage\Downloads".
    Nachdem Sie die Datei kopiert haben, können Sie das Gerät trennen und die Installation später beenden.
1. Öffnen Sie HoloLens 2-Gerät das **Startmenü,** wählen Sie Alle Apps **aus,** und starten Sie die **Datei-Explorer-App.**
1. Navigieren Sie zum Ordner Downloads. Möglicherweise müssen Sie im linken Bereich  der App zuerst Dieses Gerät auswählen und dann zu Downloads navigieren.
1. Wählen Sie die Datei yourapp.appxbundle aus.
1. Die App-Installer wird gestartet. Wählen Sie die **Schaltfläche Installieren** aus, um Ihre App zu installieren.

Die installierte App wird nach Abschluss der Installation automatisch gestartet.

![Installieren von MRTK-Beispielen über App-Installer](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>Problembehandlung bei Installationen

Wenn ihre App nicht installiert werden konnte, überprüfen Sie Folgendes, um probleme zu beheben:

- Ihre App ist entweder ein Master- oder Release-Build.
- Ihr Gerät wird auf einen Build aktualisiert, auf dem dieses Feature verfügbar ist.
- Sie sind [mit dem Internet verbunden.](hololens-network.md)
- Ihre [Endpunkte für die Microsoft Store](hololens-offline.md) sind ordnungsgemäß konfiguriert.  

## <a name="web-installer"></a>Webinstaller

Benutzer können eine App direkt von einem Webserver installieren. Dieser Flow nutzt die -App-Installer in Kombination mit einer einfachen Download- und Installationsverteilungsmethode.

### <a name="how-to-set-up-web-install"></a>Einrichten der Web-Installation:

1. Stellen Sie sicher, dass Ihre App ordnungsgemäß für die Installation konfiguriert ist.
1. Führen Sie die [folgenden Schritte aus, um die Installation über eine Webseite zu aktivieren.](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)

### <a name="end-user-experience"></a>Endbenutzererfahrung:

1. Der Benutzer empfängt und installiert das Zertifikat auf dem Gerät mithilfe einer zuvor ausgewählten Methode.
1. Der Benutzer besucht die URL, die im obigen Schritt erstellt wurde.

Die App wird jetzt auf dem Gerät installiert. Um die App zu finden, öffnen Sie das **Startmenü,** und wählen Sie die Schaltfläche **Alle Apps,** um Ihre App zu suchen.

- Weitere Hilfe zur Problembehandlung bei der Installationsmethode des App-Installationsprogramms finden Sie unter [Beheben von Problemen mit dem App-Installationsprogramm.](/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> Die Benutzeroberfläche während des Updatevorgangs wird nicht unterstützt. Daher werden die Option ShowPrompt auf [dieser Seite und](/windows/msix/app-installer/update-settings) zugehörige Optionen nicht unterstützt.

## <a name="sample-apps"></a>Beispiel-Apps

Testen Sie die App-Installer mit einer unserer verfügbaren Beispiel-Apps. 
> [!div class="nextstepaction"]
> [Beispiel-Apps](/windows/mixed-reality/develop/features-and-samples)
