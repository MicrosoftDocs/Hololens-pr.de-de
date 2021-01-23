---
title: HoloLens-BitLocker-Verschlüsselung
description: Erfahren Sie, wie Sie die Bitlocker-Geräteverschlüsselung aktivieren, um Dateien zu schützen, die auf Ihren Mixed -Reality-HoloLens-Geräten gespeichert sind.
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
ms.openlocfilehash: 268c3650b85e7e7f102618ccc5a94c25de54dcfe
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284026"
---
# BitLocker-Verschlüsselung von HoloLens (1. Gen.) 

HoloLens (1. Generation) und HoloLens 2 unterstützen beide die Geräteverschlüsselung mit BitLocker, BitLocker ist jedoch immer auf HoloLens 2 aktiviert.

Dieser Artikel hilft Ihnen, BitLocker auf HoloLens (1. Generation) zu aktivieren und zu verwalten.

Auf HoloLens (1. Generation) können Sie die BitLocker-Geräteverschlüsselung manuell oder mithilfe der Mobile Device Management (MDM) aktivieren. Befolgen Sie diese Anweisungen, um die [BitLocker-Geräteverschlüsselung](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) zu aktivieren, um dateien und Informationen zu schützen, die auf holoLens gespeichert sind. Die Geräteverschlüsselung schützt Ihre Daten mithilfe der AES-CBC 128-Verschlüsselungsmethode, die der [EncryptionMethodByDriveType-Methode 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) im #A0 (CSP) entspricht. Mitarbeiter, die über den richtigen Verschlüsselungsschlüssel (z. B. ein Kennwort) verfügen, können ihn entschlüsseln oder eine Datenwiederherstellung durchführen.

## Geräteverschlüsselung mithilfe von MDM aktivieren

Sie können Ihren Anbieter für die mobile Geräteverwaltung (Mobile Device Management, MDM) verwenden, um eine Richtlinie anzuwenden, die Geräteverschlüsselung erfordert. Die zu verwendende Richtlinie ist die [Einstellung "Sicherheit/RequireDeviceEncryption"](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) im Richtlinien-CSP.

[Weitere Informationen zum Aktivieren der Geräteverschlüsselung mit Microsoft Intune finden Sie in den Anweisungen.](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

Weitere MDM-Tools finden Sie in der Dokumentation Ihres MDM-Anbieters. Wenn Ihr MDM-Anbieter einen benutzerdefinierten URI für die Geräteverschlüsselung benötigt, verwenden Sie die folgende Konfiguration:

- **Namen**: ein Name Ihrer Wahl
- **Beschreibung**: optional
- **OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Datentyp:**: ganze Zahl
- **Wert**: `1`

## Aktivieren der Geräteverschlüsselung mithilfe eines Bereitstellungspakets

Bereitstellungspakete sind Dateien, die vom Windows-Designer für die Konfiguration erstellt werden und eine spezifische Konfiguration auf ein Gerät anwenden. 

### Erstellen eines Bereitstellungspakets, das ein Upgrade der Windows Holographic Edition und die Verschlüsselung ermöglicht

1. [Erstellen Sie ein Bereitstellungspaket für HoloLens.](hololens-provisioning.md)
1. Wechseln Sie zu **Laufzeiteinstellungen** > **Richtlinien** > **Sicherheit** und wählen Sie **RequireDeviceEncryption** aus.

    ![Konfigurieren der Geräteverschlüsselungseinstellung auf „Ja”](images/device-encryption.png)

1. Suchen Sie die XML-Lizenzdatei, die beim Kauf der Commercial Suite bereitgestellt wurde.

1. Navigieren Sie zu der XML-Lizenzdatei, die beim Kauf der Commercial Suite bereitgestellt wurde, und wählen Sie diese aus.
    > [!NOTE]
    > Sie können [zusätzliche Einstellungen im Bereitstellungspaket](hololens-provisioning.md) konfigurieren.

1. Klicken Sie im Menü **Datei** auf **Speichern**. 

1. Lesen Sie die Warnung, dass Projektdateien möglicherweise vertrauliche Informationen enthalten, und klicken Sie auf **"OK".**

    > [!IMPORTANT]
    > Wenn Sie ein Bereitstellungspaket erstellen, können Sie vertrauliche Informationen in die Projektdateien und die Bereitstellungspaketdatei (.ppkg) verwenden. Obwohl Sie die PPKG-Datei verschlüsseln können, werden die Projektdateien nicht verschlüsselt. Sie sollten die Projektdateien an einem sicheren Speicherort speichern und die Projektdateien löschen, wenn sie nicht mehr benötigt werden.

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

- Wechseln Sie auf HoloLens zu **Einstellungen** > **System** > **Info**. **BitLocker** ist **aktiviert,** wenn das Gerät verschlüsselt ist. 

    ![Informationen zum Bildschirm, auf dem BitLocker aktiviert ist](images/about-encryption.png)
