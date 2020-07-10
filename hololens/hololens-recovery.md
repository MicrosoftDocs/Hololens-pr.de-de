---
title: HoloLens neu starten, zurücksetzen oder wiederherstellen
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
description: Verwenden von Advanced Recovery Companion (ARC), um einen Flashs eines Images in HoloLens 2 auszuführen.
keywords: Hilfe & Anleitung, Neustart, zurücksetzen, wiederherstellen, Kaltstart, Warmstart, Energiezyklus, HoloLens, Herunterfahren, ARC, Advanced Recovery Companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
ms.openlocfilehash: 2c7fa9b8c86900c89bbced1a10f3e9e2bc69bcd0
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857763"
---
# HoloLens neu starten, zurücksetzen oder wiederherstellen

## Aufladen des Geräts

Bevor Sie eine Problembehandlung starten, vergewissern Sie sich, dass Ihr Gerät nach Möglichkeit mindestens zu 20% bis 40% aufgeladen ist.

Stellen Sie sicher, dass Sie das Ladegerät und das USB-Typ-C-Kabel verwenden, die mit dem HoloLens2-Gerät geliefert wurden. Falls diese nicht verfügbar sind, stellen Sie sicher, dass das verfügbare Ladegerät mindestens 15W Leistung erbringen kann.

> [!NOTE]
> Verwenden Sie nach Möglichkeit keinen PC, um das Gerät über USB aufzuladen, da dies eine sehr langsame Aufladung zur Folge hat.

Wenn das Gerät korrekt hochgefahren ist und ausgeführt wird, gibt es drei verschiedene Möglichkeiten, den Ladezustand des Akkus zu überprüfen.

1. Über das Hauptmenü der Benutzeroberfläche des HoloLens-Geräts.
2. Verwenden Sie die LED in der Nähe des Einschaltknopfs (bei 40% sollten mindestens zwei LEDs ununterbrochen leuchten).
3. Öffnen Sie auf Ihrem Host-PC das Fenster des Datei-Explorers, und suchen Sie Ihr HoloLens 2-Gerät auf der linken Seite unter "Dieser PC".
    
      a. Klicken Sie mit der rechten Maustaste auf den Namen des Geräts, und wählen Sie "Eigenschaften" aus. Es wird ein Dialogfeld mit dem Akkustand für Ihr Gerät angezeigt.

![HoloLens 2 ResetRecovery](images/ResetRecovery2.png)

Wenn das Gerät nicht über das Startmenü gestartet werden kann, beachten Sie bitte die LEDs und die Aufzählung auf dem Host-PC und befolgen Sie die Anleitung zur Fehlerbehebung (https://docs.microsoft.com/hololens/hololens-troubleshooting). Falls der Status des Geräts nicht in einen der im Handbuch zur Fehlerbehebung aufgeführten Zustände fällt, führen Sie den **Hard-Reset-Vorgang** aus, ohne das Gerät erneut an Ihren Host-PC anzuschließen, sondern schließen Sie es stattdessen an das Netzteil an. Warten Sie mindestens eine Stunde, bis das Gerät aufgeladen ist.

## Setzen Sie das Gerät zurück

Unter bestimmten Umständen muss der Kunde das Gerät möglicherweise manuell zurücksetzen, ohne die SW-Benutzeroberfläche zu verwenden. 

### Standardvorgehensweise
1. Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel ausstecken.

2. Halten Sie den **Einschaltknopf** 15 Sekunden lang gedrückt. Alle LEDs sollten aus sein.

3. Warten Sie 2-3 Sekunden und drücken Sie kurz den **Einschaltknopf**. Die LEDs in der Nähe des Netzschalters leuchten auf und das Gerät startet. 

4. Schließen Sie das Gerät an den Host-PC an, öffnen Sie den Geräte-Manager (drücken Sie für Windows 10 die **„Windows-Taste“** und dann die **„x-Taste“** und klicken Sie auf „Geräte-Manager“) und stellen Sie sicher, dass das Gerät korrekt als Microsoft HoloLens aufgeführt ist siehe Bilder unten:

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### Hard-Reset-Verfahren

Wenn das Standard-Reset-Verfahren nicht funktioniert, können Sie das Hard-Reset-Verfahren verwenden.

1. Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel ausstecken.

2. Halten Sie den **Leiser-Knopf + den Einschaltknopf** 15 Sekunden lang gedrückt.

3. Das Gerät wird automatisch neu gestartet. 

4. Schließen Sie das Gerät an den Host-PC an, öffnen Sie den Geräte-Manager (drücken Sie für Windows 10 die **„Windows-Taste“** und dann die **„x-Taste“** und klicken Sie auf „Geräte-Manager“) und stellen Sie sicher, dass das Gerät korrekt als Microsoft HoloLens aufgeführt ist siehe Bilder unten.

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## Clean-Reflash des Geräts

In außergewöhnlichen Situationen müssen Sie das Gerät möglicherweise clean flashen. Es gibt zwei Möglichkeiten, ein HoloLens2-Gerät reflashen. Für alle Reflashing-Verfahren müssen Sie die [Advanced Recovery Companion-Anwendung aus dem Windows Store installieren](https://www.microsoft.com/store/productId/9P74Z35SFRS8). Wenn Sie Ihr Gerät zurücksetzen, werden alle Ihre persönlichen Daten, Apps und Einstellungen gelöscht, einschließlich der TPM-Zurücksetzung.

Advanced Recovery Companion ist derzeit so eingestellt, dass das Feature Release für [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004) heruntergeladen wird. Wenn Sie die neueste HoloLens 2 FFU herunterladen möchten, um Ihr Gerät über Advanced Recovery Companion zu flashen, können Sie sie [hier](https://aka.ms/hololens2download) herunterladen. Dies wird auf dem neuesten Stand gehalten und entspricht dem neuesten allgemein verfügbaren Build. 

Stellen Sie vor dem Starten des Flashens sicher, dass die Anwendung auf Ihrem Windows 10-PC installiert ist und ausgeführt wird und bereit ist, das Gerät zu erkennen.

![HoloLens 2 Clean Reflash](images/ARC1.png)

### Normales Verfahren

1. Während das HoloLens-Gerät ausgeführt wird, verbinden Sie es mit Ihrem Windows 10-PC, auf dem Sie zuvor die Advanced Recovery Companion-Anwendung gestartet haben.

2. Das Gerät wird automatisch erkannt und die Benutzeroberfläche der Advanced Recovery Companion-Anwendung wird wie folgt aktualisiert:

![HoloLens 2 Clean Reflash](images/ARC2.png)

3. Wählen Sie das HoloLens2-Gerät in der Benutzeroberfläche der Advanced Recovery Companion-Anwendung aus und befolgen Sie die Anweisungen, um das Flashen abzuschließen.

### Manuelle Vorgehensweise

Wenn das Gerät nicht richtig startet, müssen Sie das HoloLens 2-Gerät möglicherweise in den Wiederherstellungsmodus versetzen.

1. Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel ausstecken. 

2. Halten Sie den **Einschaltknopf** 15 Sekunden lang gedrückt. Alle LEDs sollten erlöschen. 

3. Halten Sie den **Einschaltknopf** gedrückt, während Sie die **Lauter-Taste** drücken, um das Gerät zu starten. Warten Sie 15 Sekunden, bevor Sie die Lauter-Taste loslassen. Von den 5 LEDs am Gerät leuchtet nur die mittlere LED auf.

4. Schließen Sie das Gerät an den Host-PC an, öffnen Sie den Geräte-Manager (drücken Sie für Windows 10 die **„Windows-Taste“** und dann die **„x-Taste“** und klicken Sie auf „Geräte-Manager“) und stellen Sie sicher, dass das Gerät korrekt als Microsoft HoloLens aufgeführt ist siehe Bild unten.

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

5. Das Gerät wird automatisch erkannt und die Benutzeroberfläche der Advanced Recovery Companion-Anwendung wird wie folgt aktualisiert:

![HoloLens 2 Clean Reflash](images/ARC2.png)

6. Wählen Sie das HoloLens 2-Gerät in der Benutzeroberfläche der Advanced Recovery Companion-Anwendung aus und befolgen Sie die Anweisungen, um das Flashen abzuschließen.

## Herunterladen von ARC ohne Verwendung des App Store

Wenn eine IT-Umgebung die Verwendung der Windows Store-App verhindert oder den Zugriff auf das Einzelhandelsgeschäft einschränkt, können IT-Administratoren diese Anwendung über andere "Offline"-Bereitstellungspfade verfügbar machen. 

- Dieser Vorgang kann auch für andere Anwendungen verwendet werden (siehe Schritt 2). Dieses Handbuch konzentriert sich auf Advanced Recovery Companion, kann jedoch für andere Offline-Anwendung geändert werden.  

Dieser Bereitstellungspfad kann mit den folgenden Schritten aktiviert werden:
1.  Rufen Sie die [Store For Business-Website](https://businessstore.microsoft.com) auf und melden Sie sich mit einer Azure AD-Identität an.
1.  Gehen Sie zu **Verwalten – Einstellungen** und aktivieren Sie **Offline-Anwendungen anzeigen** unter **Einkaufserfahrung**, wie unter https://businessstore.microsoft.com/manage/settings/shop beschrieben 
1.  Gehen Sie zu **Einkaufen für meine Gruppe** und suchen Sie nach der [Advanced Recovery Companion-Anwendung](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).
1.  Ändern Sie das **Feld Lizenztyp** in Offline und klicken Sie auf **Verwalten**.
1.  Klicken Sie unter Paket für Offline-Verwendung herunterladen auf die zweite blaue Schaltfläche **"Herunterladen"**. Stellen Sie sicher, dass die Dateierweiterung .appxbundle ist.
1.  Wenn der Desktop-PC zu diesem Zeitpunkt über einen Internetzugang verfügt, doppelklicken Sie einfach und installieren Sie ihn. 
1.  Der IT-Administrator kann diese Anwendung auch über System Center Configuration Manager (SCCM) oder Intune verteilen.
1.  Wenn der Ziel-PC keine Internetverbindung hat, sind einige zusätzliche Schritte erforderlich: 
    1.  Wählen Sie die nicht codierte Lizenz aus und klicken Sie auf **"Lizenz generieren"**. Klicken Sie unter **"Erforderliche Frameworks"** auf **"Herunterladen"**. 
    1.  PCs ohne Internetzugang müssen DISM verwenden, um das Paket mit der Abhängigkeit und Lizenz anzuwenden. Geben Sie an einer Administrator-Eingabeaufforderung Folgendes ein:

      ```console
      C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
      ```
> [!NOTE]
> Die Versionsnummer in diesem Codebeispiel stimmt möglicherweise nicht mit der aktuell verfügbaren Version überein. Möglicherweise haben Sie auch einen anderen Download-Speicherort als im angegebenen Beispiel ausgewählt. Bitte stellen Sie sicher, dass Sie die erforderlichen Änderungen vornehmen.

> [!TIP]
> Wenn Sie Advanced Recovery Companion verwenden möchten, um eine ffu offline zu installieren, kann es hilfreich sein, Ihr Flash-Image herunterzuladen, um verfügbar zu sein. Hier ist das [aktuelle Image für HoloLens 2](https://aka.ms/hololens2download). 

Andere Ressourcen
- https://docs.microsoft.com/microsoft-store/distribute-offline-apps 
- https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options


