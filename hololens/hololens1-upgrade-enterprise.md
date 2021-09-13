---
title: Effiziente Nutzung der Features von Windows Holographic for Business
description: Wenn Sie ein Upgrade auf Windows Holographic for Business, HoloLens zusätzliche Features, die für Unternehmen konzipiert sind.
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
ms.openlocfilehash: c6d1225dc6da1c039a34fc2782f23330ae40f280
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032778"
---
# <a name="unlock-windows-holographic-for-business-features"></a>Effiziente Nutzung der Features von Windows Holographic for Business

> [!IMPORTANT]
> Diese Seite gilt nur für HoloLens 1. Generation.

Microsoft HoloLens ist in der *Development Edition* verfügbar, die Windows Holographic (eine Edition von Windows 10, die für HoloLens entwickelt wurde) und in der Commercial [Suite,](hololens-commercial-features.md)die zusätzliche Funktionen für Unternehmen bietet.

Wenn Sie die Commercial Suite erwerben, erhalten Sie eine Lizenz, die ein Upgrade Windows Holographic auf Windows Holographic for Business. Sie können diese Lizenz entweder mithilfe des MDM-Anbieters [(Mobile Device Management,](#edition-upgrade-by-using-mdm) Verwaltung mobiler Geräte) der Organisation oder mit einem [Bereitstellungspaket auf das Gerät anwenden.](#edition-upgrade-by-using-a-provisioning-package)

> [!TIP]
> In Windows 10 Version 1803 können Sie überprüfen, ob der HoloLens auf die Business Edition aktualisiert wurde, indem Sie Einstellungen  >  **System auswählen.**

## <a name="edition-upgrade-by-using-mdm"></a>Editionsupgrade mithilfe von MDM

Die Enterprise-Lizenz kann von jedem MDM-Anbieter angewendet werden, der den [WindowsLicensing-Konfigurationsdienstanbieter (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) unterstützt. Die neueste Version der Microsoft-MDM-API unterstützt den WindowsLicensing CSP.

Eine Schritt-für-Schritt-Anleitung zum Aktualisieren von HoloLens mit Microsoft Intune finden Sie unter Aktualisieren von Geräten mit Windows [Holographic auf Windows Holographic for Business](/intune/holographic-upgrade).

 Im Fall anderer MDM-Anbieter können die einzelnen Schritte zum Einrichten und Bereitstellen der Richtlinie abweichen.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Editionsupgrade mithilfe eines Bereitstellungspakets

Bereitstellungspakete sind Dateien, die vom Windows-Konfigurations-Designer-Tool erstellt wurden, die eine angegebene Konfiguration auf ein Gerät anwenden.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Erstellen eines Bereitstellungspakets, das ein Upgrade der Windows Holographic Edition ausführt

1. [Erstellen Sie ein Bereitstellungspaket für HoloLens.](hololens-provisioning.md)
1. Wechseln Sie **zu Runtimeeinstellungen**  >  **EditionUpgrade,** und wählen **Sie EditionUpgradeWithLicense aus.**

    ![Upgrade der Edition mit ausgewählter Lizenzeinstellung.](images/icd1.png)

1. Suchen Sie die XML-Lizenzdatei, die beim Kauf der Commercial Suite bereitgestellt wurde.

    > [!NOTE]
    > Sie können [zusätzliche Einstellungen im Bereitstellungspaket](hololens-provisioning.md) konfigurieren.

1. Klicken Sie im Menü **File** (Datei) auf **Save** (Speichern). 

1. Lesen Sie die Warnung, dass Projektdateien möglicherweise vertrauliche Informationen enthalten, und klicken Sie auf **OK.**

    > [!IMPORTANT]
    > Wenn Sie ein Bereitstellungspaket erstellen, können Sie vertrauliche Informationen in die Projektdateien und die Bereitstellungspaketdatei (PPKG)-Datei ein. Obwohl Sie die PPKG-Datei verschlüsseln können, werden die Projektdateien nicht verschlüsselt. Sie sollten die Projektdateien an einem sicheren Speicherort speichern und die Projektdateien löschen, wenn sie nicht mehr benötigt werden.

1. Wählen Sie im Menü **Exportieren** die Option **Bereitstellungspaket** aus.

1. Ändern **Sie Besitzer** in **IT-Administrator,** wodurch die Rangfolge dieses Bereitstellungspakets höher ist als bei anderen, die aus verschiedenen Quellen auf dieses Gerät angewendet werden, und wählen Sie dann **Weiter aus.**

1. Legen Sie einen Wert für **Paketversion** fest.

    > [!TIP]
    > Sie können Änderungen an vorhandenen Paketen vornehmen und die Versionsnummer ändern, um bereits angewendete Pakete zu aktualisieren.

1. Wählen **Sie unter Sicherheitsdetails für das Bereitstellungspaket auswählen** die Option Weiter **aus.**

1. Wählen **Sie Weiter** aus, um den Ausgabespeicherort anzugeben, an den das Bereitstellungspaket gehen soll, sobald es erstellt wurde. Standardmäßig verwendet Windows ICD den Projektordner als Ausgabespeicherort.

    Optional können Sie Durchsuchen auswählen, **um** den Standardausgabespeicherort zu ändern.

1. Wählen Sie **Weiter** aus.

1. Wählen Sie **Erstellen aus,** um mit dem Erstellen des Pakets zu beginnen. Auf der Buildseite werden die Projektinformationen und auf der Statusanzeige der Buildstatus angezeigt.

1. Wenn der Build abgeschlossen ist, wählen Sie **Fertig stellen aus.**

### <a name="apply-the-provisioning-package-to-hololens"></a>Anwenden des Bereitstellungspakets auf HoloLens

1. Verbinden Sie das Gerät über das USB-Kabel mit einem PC. Starten Sie das Gerät, aber  fahren Sie nicht über die Anpassungsseite der anfänglichen Einrichtung hinaus (die erste Seite mit dem blauen Feld). Auf dem PC wird HoloLens im Datei-Explorer als Gerät angezeigt.

    > [!NOTE]
    > Wenn auf dem HoloLens-Gerät Windows 10, Version 1607 oder früher, ausgeführt wird, öffnen Sie den Datei-Explorer, indem Sie auf dem Gerät kurz darauf klicken und die Schaltflächen **Volume down** und **Power** gleichzeitig freigeben.

1. Verschieben Sie das Bereitstellungspaket (.ppkg) im Datei-Explorer per Drag & Drop zum Gerätespeicher.

1. Während HoloLens sich noch  auf der Anpassungsseite befindet, drücken Sie kurz, und lassen Sie die Schaltflächen **Volume Down** und **Power** gleichzeitig wieder frei.

1. HoloLens Sie, ob Sie dem Paket vertrauen und es anwenden möchten. Bestätigen Sie, dass Sie dem Paket vertrauen.

1. Sie können erkennen, ob das Paket erfolgreich angewendet wurde oder nicht. Wenn sie nicht erfolgreich angewendet wurde, können Sie das Paket korrigieren und es erneut versuchen. Wenn dies erfolgreich ist, fahren Sie mit der Geräteeinrichtung fort.
