---
title: Effiziente Nutzung der Features von Windows Holographic for Business
description: Wenn Sie ein Upgrade auf Windows holographisch for Business durchführen, bietet HoloLens zusätzliche Features, die für Unternehmen entwickelt wurden.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829339"
---
# Effiziente Nutzung der Features von Windows Holographic for Business

> [!IMPORTANT]
> Diese Seite gilt nur für HoloLens 1st Gen.

Microsoft HoloLens steht in der *Development Edition*zur Verfügung, die Windows holographisch (eine Edition von Windows 10, die für HoloLens entwickelt wurde) und in der [kommerziellen Suite](hololens-commercial-features.md), die zusätzliche Features bietet, die für Unternehmen entwickelt wurden, ausführt.

Wenn Sie die Commercial Suite erwerben, erhalten Sie eine Lizenz, mit der Sie ein Upgrade von Windows Holographic auf Windows Holographic for Business ausführen können. Sie können diese Lizenz auf das Gerät anwenden, indem Sie entweder den [MDM-Anbieter (Mobile Device Management)](#edition-upgrade-by-using-mdm) der Organisation oder ein [Bereitstellungspaket](#edition-upgrade-by-using-a-provisioning-package)verwenden.

> [!TIP]
> In Windows 10, Version 1803, können Sie überprüfen, ob die HoloLens auf die Business Edition aktualisiert wurde, indem Sie **Einstellungen**  >  **System**auswählen.

## Editionsupgrade mithilfe von MDM

Die Enterprise-Lizenz kann von jedem MDM-Anbieter angewendet werden, der den [WindowsLicensing-Konfigurationsdienstanbieter (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) unterstützt. Die neueste Version der Microsoft-MDM-API unterstützt den WindowsLicensing CSP.

Eine Schritt-für-Schritt-Anleitung zum Upgrade von HoloLens mithilfe von Microsoft InTune finden Sie unter [Aktualisieren von Geräten, auf denen Windows holographisch auf Windows holographisch für Unternehmen ausgeführt wird](https://docs.microsoft.com/intune/holographic-upgrade).

 Im Fall anderer MDM-Anbieter können die einzelnen Schritte zum Einrichten und Bereitstellen der Richtlinie abweichen.

## Editionsupgrade mithilfe eines Bereitstellungspakets

Bereitstellungspakete sind Dateien, die vom Windows-Designer für die Konfiguration erstellt werden und eine spezifische Konfiguration auf ein Gerät anwenden.

### Erstellen eines Bereitstellungspakets, das ein Upgrade der Windows Holographic Edition ausführt

1. [Erstellen Sie ein Bereitstellungspaket für HoloLens.](hololens-provisioning.md)
1. Navigieren Sie zu **Laufzeiteinstellungen** > **EditionUpgrade**, und wählen Sie **EditionUpgradeWithLicense** aus.

    ![Editionsupgrade mit ausgewählter Lizenzeinstellung](images/icd1.png)

1. Suchen Sie die XML-Lizenzdatei, die beim Kauf der kommerziellen Suite zur Verfügung gestellt wurde.

    > [!NOTE]
    > Sie können [zusätzliche Einstellungen im Bereitstellungspaket](hololens-provisioning.md) konfigurieren.

1. Wählen Sie im Menü **Datei** die Option **Speichern**aus. 

1. Lesen Sie die Warnung, dass Projektdateien vertrauliche Informationen enthalten können, und klicken Sie auf **OK**.

    > [!IMPORTANT]
    > Wenn Sie ein Bereitstellungspaket erstellen, können Sie vertrauliche Informationen in die Datei "Projektdateien und Bereitstellungspaket" (ppkg) einbeziehen. Obwohl Sie die PPKG-Datei verschlüsseln können, werden die Projektdateien nicht verschlüsselt. Speichern Sie die Projektdateien an einem sicheren Speicherort, und löschen Sie die Projektdateien, wenn Sie nicht mehr benötigt werden.

1. Wählen Sie im Menü **Exportieren** die Option **Bereitstellungspaket**aus.

1. Ändern Sie den **Besitzer** in den **IT-Administrator**, wodurch die Rangfolge dieses Bereitstellungspakets höher ist als bei anderen Benutzern, die auf dieses Gerät aus unterschiedlichen Quellen angewendet wurden, und wählen Sie dann **weiter**aus.

1. Legen Sie einen Wert für **Paketversion**fest.

    > [!TIP]
    > Sie können Änderungen an vorhandenen Paketen vornehmen und die Versionsnummer ändern, um bereits angewendete Pakete zu aktualisieren.

1. Wählen Sie unter **Sicherheitsdetails für das Bereitstellungspaket auswählen die**Option **weiter**aus.

1. Wählen Sie **weiter** aus, um den Ausgabespeicherort anzugeben, an dem das Bereitstellungspaket nach dem Aufbau ablaufen soll. Standardmäßig verwendet Windows ICD den Projektordner als Ausgabespeicherort.

    Optional können Sie **Durchsuchen** auswählen, um den Standardausgabe Speicherort zu ändern.

1. Wählen Sie **Weiter** aus.

1. Wählen Sie **Erstellen** aus, um mit dem Erstellen des Pakets zu beginnen. Auf der Seite "erstellen" werden die Projektinformationen angezeigt, und die Statusleiste zeigt den Buildstatus an.

1. Wenn der Build abgeschlossen ist, wählen Sie **Fertig stellen**aus.

### Anwenden des Bereitstellungspakets auf HoloLens

1. Schließen Sie das Gerät über das USB-Kabel an einen PC an. Starten Sie das Gerät, aber gehen Sie nicht über die Seite " **Anpassen** " der anfänglichen Setup-Umgebung (die erste Seite mit dem blauen Feld) hinaus. Auf dem PC wird HoloLens im Datei-Explorer als Gerät angezeigt.

    > [!NOTE]
    > Wenn auf dem HoloLens-Gerät Windows 10, Version 1607 oder früher ausgeführt wird, öffnen Sie den Datei-Explorer, indem Sie die **Lautstärke** Taste und die **Power** -Taste gleichzeitig auf dem Gerät freigeben.

1. Verschieben Sie das Bereitstellungspaket (.ppkg) im Datei-Explorer per Drag & Drop zum Gerätespeicher.

1. Während sich HoloLens noch auf der Seite " **Anpassen** " befindet, drücken Sie kurz die **Lautstärke** Taste und die **Power** -Taste gleichzeitig wieder.

1. HoloLens fragt Sie, ob Sie dem Paket Vertrauen und es anwenden möchten. Bestätigen Sie, dass Sie dem Paket vertrauen.

1. Sie können erkennen, ob das Paket erfolgreich angewendet wurde oder nicht. Wenn Sie nicht erfolgreich angewendet wurde, können Sie das Paket beheben und es erneut versuchen. Wenn Sie erfolgreich sind, fahren Sie mit der Einrichtung des Geräts fort.
