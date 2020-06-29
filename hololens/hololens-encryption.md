---
title: Aktivieren der BitLocker-Verschlüsselung für HoloLens (HoloLens)
description: Aktivieren der BitLocker-Geräteverschlüsselung zum Schutz von Dateien auf HoloLens
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 29b9ce346456019dad8e9bc6fd02b104ed4a821d
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828093"
---
# Aktivieren der Verschlüsselung für HoloLens

HoloLens (1st Generation) und HoloLens 2 unterstützen die Geräteverschlüsselung mithilfe von BitLocker, allerdings ist BitLocker in HoloLens 2 immer aktiviert.

In diesem Artikel wird das Aktivieren und Verwalten von BitLocker auf HoloLens (1st Generation) unterstützt.

Auf HoloLens (1st Generation) können Sie die BitLocker-Geräteverschlüsselung manuell oder mithilfe der Mobile Device Management (MDM) aktivieren. Befolgen Sie diese Anweisungen, um die [BitLocker-Geräteverschlüsselung](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) zu aktivieren, um Dateien und auf der HoloLens gespeicherte Informationen zu schützen. Die Geräteverschlüsselung schützt Ihre Daten mithilfe der AES-CBC 128-Verschlüsselungsmethode, die mit der [EncryptionMethodByDriveType-Methode 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) im BitLocker-Konfigurationsdienst Anbieter (CSP) vergleichbar ist. Mitarbeiter, die über den richtigen Verschlüsselungsschlüssel (wie ein Kennwort) verfügen, können ihn entschlüsseln oder eine Datenwiederherstellung durchführen.

## Geräteverschlüsselung mithilfe von MDM aktivieren

Sie können Ihren MDM-Anbieter (Mobile Device Management) verwenden, um eine Richtlinie anzuwenden, die Geräteverschlüsselung erfordert. Die zu verwendende Richtlinie ist die [Einstellung Sicherheit/RequireDeviceEncryption](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) im Richtlinien-CSP.

[Lesen Sie dazu die Anweisungen zum Aktivieren der Geräteverschlüsselung mit Microsoft InTune.](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

Weitere MDM-Tools finden Sie in der Dokumentation Ihres MDM-Anbieters. Wenn Ihr MDM-Anbieter benutzerdefinierten URI für die Geräteverschlüsselung erfordert, verwenden Sie die folgende Konfiguration:

- **Namen**: ein Name Ihrer Wahl
- **Beschreibung**: optional
- **OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Datentyp:**: ganze Zahl
- **Wert**: `1`

## Aktivieren der Geräteverschlüsselung mithilfe eines Bereitstellungspakets

Bereitstellungspakete sind Dateien, die vom Windows-Designer für die Konfiguration erstellt werden und eine spezifische Konfiguration auf ein Gerät anwenden. 

### Erstellen eines Bereitstellungspakets, das die Windows holographische Edition aktualisiert und die Verschlüsselung ermöglicht

1. [Erstellen Sie ein Bereitstellungspaket für HoloLens.](hololens-provisioning.md)
1. Wechseln Sie zu **Laufzeiteinstellungen** > **Richtlinien** > **Sicherheit** und wählen Sie **RequireDeviceEncryption** aus.

    ![Konfigurieren der Geräteverschlüsselungseinstellung auf „Ja”](images/device-encryption.png)

1. Suchen Sie die XML-Lizenzdatei, die beim Kauf der kommerziellen Suite zur Verfügung gestellt wurde.

1. Navigieren Sie zu der XML-Lizenzdatei, die beim Kauf der Commercial Suite bereitgestellt wurde, und wählen Sie diese aus.
    > [!NOTE]
    > Sie können [zusätzliche Einstellungen im Bereitstellungspaket](hololens-provisioning.md) konfigurieren.

1. Klicken Sie im Menü **Datei** auf **Speichern**. 

1. Lesen Sie die Warnung erläutern, dass Projektdateien vertrauliche Informationen enthalten können, und klicken Sie auf **OK**.

    > [!IMPORTANT]
    > Wenn Sie ein Bereitstellungspaket erstellen, können Sie vertrauliche Informationen in die Datei "Projektdateien und Bereitstellungspaket" (ppkg) einbeziehen. Obwohl Sie die PPKG-Datei verschlüsseln können, werden die Projektdateien nicht verschlüsselt. Speichern Sie die Projektdateien an einem sicheren Speicherort, und löschen Sie die Projektdateien, wenn Sie nicht mehr benötigt werden.

1. Klicken Sie im Menü **Exportieren** auf **Bereitstellungspaket**.
1. Ändern Sie **Owner** in **IT Admin**. Dadurch erhält dieses Bereitstellungspaket Vorrang gegenüber Bereitstellungspaketen, die aus anderen Quellen auf dieses Gerät angewendet werden. Wählen Sie anschließend **Weiter** aus.
1. Legen Sie einen Wert für **Paketversion**fest.

    > [!TIP]
    > Sie können Änderungen an vorhandenen Paketen vornehmen und die Versionsnummer ändern, um bereits angewendete Pakete zu aktualisieren.

1. Klicken Sie unter **Sicherheitsdetails für das Bereitstellungspaket auswählen** auf **Weiter**.
1. Klicken Sie auf **Weiter**, um den Ausgabespeicherort anzugeben, an dem das Bereitstellungspaket nach dem Erstellen gespeichert werden soll. Standardmäßig verwendet Windows ICD den Projektordner als Ausgabespeicherort.

    Klicken Sie optional auf Durchsuchen , um den Standardausgabespeicherort zu ändern.

1. Klicken Sie auf **Weiter**.
1. Klicken Sie auf **Erstellen** , um mit der Paketerstellung zu beginnen. Die Projektinformationen werden auf der Buildseite angezeigt, und die Statusanzeige gibt den Buildstatus an.
1. Wenn der Build abgeschlossen ist, klicken Sie auf **Fertig stellen**.

### Anwenden des Bereitstellungspakets auf HoloLens

1. Schließen Sie das Gerät über USB an einen PC an, und starten Sie das Gerät. Führen Sie den Vorgang jedoch nur bis zur Seite **Anpassen** der Ersteinrichtung (der ersten Seite mit dem blauen Feld) aus.
1. Drücken Sie die Tasten **Leiser** und **Ein/Aus** kurz gleichzeitig, und geben Sie sie anschließend wieder frei.
1. HoloLens wird im Datei-Explorer auf dem PC als Gerät angezeigt.
1. Verschieben Sie das Bereitstellungspaket (.ppkg) im Datei-Explorer per Drag & Drop zum Gerätespeicher.
1. Drücken Sie erneut die Tasten **Leiser** und **Ein/Aus** kurz gleichzeitig, während Sie sich auf der Seite **Anpassen** befinden, und geben Sie sie anschließend wieder frei.
1. Das Gerät wird Sie fragen, ob Sie dem Paket vertrauen und es anwenden möchten. Bestätigen Sie, dass Sie dem Paket vertrauen.
1. Sie können erkennen, ob das Paket erfolgreich angewendet wurde oder nicht. Wenn das Paket nicht erfolgreich angewendet wurde, können Sie es korrigieren und den Vorgang wiederholen. Wenn das Paket erfolgreich angewendet wurde, fahren Sie mit der Einrichtung des Geräts fort.

> [!NOTE]
> Wenn das Gerät vor dem August2016 erworben wurde, müssen Sie sich mit einem Microsoft-Konto am Gerät anmelden, das neueste Betriebssystemupdate abrufen und anschließend das Betriebssystem zurücksetzen, um das Bereitstellungspaket anzuwenden.

## Geräteverschlüsselung überprüfen

Verschlüsselung erfolgt im Hintergrund für HoloLens. So überprüfen Sie den Verschlüsselungsstatus des Geräts:

- Wechseln Sie auf HoloLens zu **Einstellungen** > **System** > **Info**. **BitLocker** ist **aktiviert** , wenn das Gerät verschlüsselt ist. 

    ![Bildschirm ' Info ' mit aktiviertem BitLocker](images/about-encryption.png)
