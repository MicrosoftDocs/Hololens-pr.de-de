---
title: HoloLens BitLocker-Verschlüsselung
description: Erfahren Sie, wie Sie die BitLocker-Geräteverschlüsselung aktivieren, um Dateien zu schützen, die auf Ihren HoloLens Mixed Reality-Geräten gespeichert sind.
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
ms.openlocfilehash: 37efab3ef3d68a9641320e144619008612f6efa2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635244"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>BitLocker-Verschlüsselung von HoloLens (1. Generation)

HoloLens (1. Generation) und HoloLens 2 unterstützen beide die Geräteverschlüsselung mit BitLocker. BitLocker ist jedoch immer auf HoloLens 2 aktiviert.

Dieser Artikel unterstützt Sie beim Aktivieren und Verwalten von BitLocker auf HoloLens (1. Generation).

Auf HoloLens (1. Generation) können Sie die BitLocker-Geräteverschlüsselung manuell oder mithilfe der Verwaltung mobiler Geräte (Mobile Device Management, MDM) aktivieren. Befolgen Sie diese Anweisungen, um die [BitLocker-Geräteverschlüsselung](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) zum Schützen von Dateien und Informationen zu aktivieren, die auf dem HoloLens gespeichert sind. Die Geräteverschlüsselung trägt zum Schutz Ihrer Daten mithilfe der AES-CBC 128-Verschlüsselungsmethode bei, die der [EncryptionMethodByDriveType-Methode 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) im BitLocker-Konfigurationsdienstanbieter (CSP) entspricht. Mitarbeiter, die über den richtigen Verschlüsselungsschlüssel (z. B. ein Kennwort) verfügen, können ihn entschlüsseln oder eine Datenwiederherstellung durchführen.

## <a name="enable-device-encryption-using-mdm"></a>Aktivieren der Geräteverschlüsselung mit MDM

Sie können Ihren Mdm-Anbieter (Mobile Geräteverwaltung) verwenden, um eine Richtlinie anzuwenden, die geräteverschlüsselung erfordert. Die zu verwendende Richtlinie ist die [Einstellung Security/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) im Richtlinien-CSP.

[Weitere Informationen finden Sie in den Anweisungen zum Aktivieren der Geräteverschlüsselung mithilfe von Microsoft Intune.](/intune/compliance-policy-create-windows#windows-holographic-for-business)

Anweisungen für andere MDM-Tools finden Sie in der Dokumentation Ihres MDM-Anbieters. Wenn Ihr MDM-Anbieter einen benutzerdefinierten URI für die Geräteverschlüsselung erfordert, verwenden Sie die folgende Konfiguration:

- **Name:** Ein Name Ihrer Wahl.
- **Beschreibung:** optional
- **OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Datentyp:** integer
- **Wert**: `1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>Aktivieren der Geräteverschlüsselung mithilfe eines Bereitstellungspakets

Bereitstellungspakete sind Dateien, die vom Windows-Konfigurations-Designer-Tool erstellt werden und eine angegebene Konfiguration auf ein Gerät anwenden. 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>Erstellen eines Bereitstellungspakets, mit dem die Windows Holographic Edition aktualisiert und die Verschlüsselung aktiviert wird

1. [Erstellen Sie ein Bereitstellungspaket für HoloLens.](hololens-provisioning.md)
1. Wechseln Sie zu **Laufzeiteinstellungen**  >    >  **Richtliniensicherheit,** und wählen **Sie RequireDeviceEncryption** aus.

    ![Geräteverschlüsselungseinstellung erforderlich, die auf Ja konfiguriert ist](images/device-encryption.png)

1. Suchen Sie die XML-Lizenzdatei, die beim Erwerb der Commercial Suite bereitgestellt wurde.

1. Navigieren Sie zu der XML-Lizenzdatei, die beim Kauf der Commercial Suite bereitgestellt wurde, und wählen Sie diese aus.
    > [!NOTE]
    > Sie können [zusätzliche Einstellungen im Bereitstellungspaket](hololens-provisioning.md) konfigurieren.

1. Klicken Sie im Menü **Datei** auf **Speichern**. 

1. Lesen Sie die Warnung, in der erläutert wird, dass Projektdateien vertrauliche Informationen enthalten können, und klicken Sie auf **OK.**

    > [!IMPORTANT]
    > Wenn Sie ein Bereitstellungspaket erstellen, können Sie vertrauliche Informationen in die Projektdateien und die Bereitstellungspaketdatei (PPKG) einschließen. Obwohl Sie die PPKG-Datei verschlüsseln können, werden die Projektdateien nicht verschlüsselt. Sie sollten die Projektdateien an einem sicheren Speicherort speichern und die Projektdateien löschen, wenn sie nicht mehr benötigt werden.

1. Klicken Sie im Menü **Exportieren** auf **Bereitstellungspaket**.
1. Ändern Sie **Besitzer** in **IT-Administrator,** wodurch die Rangfolge dieses Bereitstellungspakets höher ist als das Bereitstellen von Paketen, die auf dieses Gerät aus anderen Quellen angewendet werden, und wählen Sie dann **Weiter** aus.
1. Legen Sie einen Wert für **Paketversion** fest.

    > [!TIP]
    > Sie können Änderungen an vorhandenen Paketen vornehmen und die Versionsnummer ändern, um bereits angewendete Pakete zu aktualisieren.

1. Klicken Sie unter **Sicherheitsdetails für das Bereitstellungspaket auswählen** auf **Weiter**.
1. Klicken Sie auf **Weiter**, um den Ausgabespeicherort anzugeben, an dem das Bereitstellungspaket nach dem Erstellen gespeichert werden soll. Standardmäßig verwendet Windows ICD den Projektordner als Ausgabespeicherort.

    Klicken Sie optional auf Durchsuchen , um den Standardausgabespeicherort zu ändern.

1. Klicken Sie auf **Weiter**.
1. Klicken Sie auf **Erstellen** , um mit der Paketerstellung zu beginnen. Die Projektinformationen werden auf der Buildseite angezeigt, und die Statusanzeige gibt den Buildstatus an.
1. Wenn der Build abgeschlossen ist, klicken Sie auf **Fertig stellen**.

### <a name="apply-the-provisioning-package-to-hololens"></a>Anwenden des Bereitstellungspakets auf HoloLens

1. Verbinden das Gerät über USB an einen PC, und starten Sie das Gerät, aber fahren Sie nicht über die **Anpassungsseite** der anfänglichen Einrichtung hinaus (die erste Seite mit dem blauen Feld).
1. Drücken Sie die Tasten **Leiser** und **Ein/Aus** kurz gleichzeitig, und geben Sie sie anschließend wieder frei.
1. HoloLens wird im Datei-Explorer auf dem PC als Gerät angezeigt.
1. Verschieben Sie das Bereitstellungspaket (.ppkg) im Datei-Explorer per Drag & Drop zum Gerätespeicher.
1. Drücken Sie erneut die Tasten **Leiser** und **Ein/Aus** kurz gleichzeitig, während Sie sich auf der Seite **Anpassen** befinden, und geben Sie sie anschließend wieder frei.
1. Das Gerät wird Sie fragen, ob Sie dem Paket vertrauen und es anwenden möchten. Bestätigen Sie, dass Sie dem Paket vertrauen.
1. Sie können erkennen, ob das Paket erfolgreich angewendet wurde oder nicht. Wenn das Paket nicht erfolgreich angewendet wurde, können Sie es korrigieren und den Vorgang wiederholen. Wenn dies erfolgreich war, fahren Sie mit der Geräteeinrichtung fort.

> [!NOTE]
> Wenn das Gerät vor August 2016 erworben wurde, müssen Sie sich mit einem Microsoft-Konto beim Gerät anmelden, das neueste Betriebssystemupdate abrufen und dann das Betriebssystem zurücksetzen, um das Bereitstellungspaket anzuwenden.

## <a name="verify-device-encryption"></a>Überprüfen der Geräteverschlüsselung

Die Verschlüsselung erfolgt bei HoloLens im Hintergrund. So überprüfen Sie den Geräteverschlüsselungsstatus:

- Wechseln Sie auf HoloLens zu **Einstellungen**  >  **System**  >  **about**. **BitLocker** ist **aktiviert,** wenn das Gerät verschlüsselt ist. 

    ![Bildschirm "Informationen" mit aktivierter BitLocker-Funktion](images/about-encryption.png)
