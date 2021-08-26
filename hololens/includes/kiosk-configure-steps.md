---
ms.openlocfilehash: 7a7122790d3e0257c07cdd8bc8c7f658b3a0e279
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859219"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[Microsoft Intune Einer-App-Kioskvorlage](#tab/uisak)

## <a name="microsoft-intune-single-app-kiosk-template"></a>Microsoft Intune einer Kioskvorlage für eine einzelne App

1. Erstellen eines Konfigurationsprofils <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Auswählen einer Kioskvorlage <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Wählen Sie aus, ob eine einzelne App oder mehrere App-Kiosks verwendet werden soll, und wählen Sie auch die Art der Benutzeradressierung für den Kioskmodus aus. <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. Auswählen der App für die Ausführung im Kioskmodus <br> 
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. Lassen Sie die restlichen Optionen erhalten. <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Wählen Sie aus, welchen Gruppen/Geräten oder Benutzern dieses Konfigurationsprofil zugewiesen werden soll. <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. Überprüfen und Erstellen zum Speichern des Konfigurationsprofils
8. Führen Sie die MDM-Synchronisierung entweder über das Gerät oder intune aus, um die Konfiguration auf das Gerät anzuwenden. Synchronisieren von Geräten aus [Intune](/mem/intune/remote-actions/device-sync#sync-a-device) oder auf dem Gerät über **Einstellungen -> Accounts -> Work** or school ->select the connected account **-> Info -> Sync**
9. Melden Sie sich als Zielbenutzer an, um den Kiosk zu erleben.

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[Microsoft Intune Kioskvorlage für mehrere Apps](#tab/uimak)

## <a name="microsoft-intune-multi-app-kiosk-template"></a>Microsoft Intune Kioskvorlage für mehrere Apps

1. Erstellen eines Konfigurationsprofils <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Auswählen einer Kioskvorlage <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Wählen Sie aus, ob eine einzelne App oder mehrere App-Kiosks verwendet werden soll, und wählen Sie auch die Art der Benutzeradressierung für den Kioskmodus aus. <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. Auswählen der Apps, die im Kioskmodus ausgeführt werden <br> 
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. Lassen Sie die restlichen Optionen erhalten. <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Wählen Sie aus, welchen Gruppen/Geräten oder Benutzern dieses Konfigurationsprofil zugewiesen werden soll. <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. Überprüfen und Erstellen zum Speichern des Konfigurationsprofils
8. Führen Sie die MDM-Synchronisierung entweder über das Gerät oder intune aus, um die Konfiguration auf das Gerät anzuwenden. Synchronisieren von Geräten aus [Intune](/mem/intune/remote-actions/device-sync#sync-a-device) oder auf dem Gerät über **Einstellungen -> Accounts -> Work** or school ->select the connected account **-> Info -> Sync**
9. Melden Sie sich als Zielbenutzer an, um den Kiosk zu erleben.

# <a name="microsoft-intune-custom-template"></a>[Microsoft Intune benutzerdefinierte Vorlage](#tab/intunecustom)

## <a name="microsoft-intune-custom-template"></a>Microsoft Intune benutzerdefinierte Vorlage

1. Erstellen Sie eine XML-Konfiguration für Ihre gewünschte Kioskerfahrung. Sehen Sie [sich die](../hololens-kiosk-reference.md#kiosk-xml-code-samples) Beispiele hier an, um zu beginnen.

1. Erstellen eines benutzerdefinierten Konfigurationsprofils <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. Geben Sie den Namen des benutzerdefinierten Konfigurationsprofils an, und klicken Sie im Abschnitt "Konfigurationseinstellungen" auf "Hinzufügen", um OMA-URI-Einstellungen hinzuzufügen. <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. Geben Sie den Namen der OMA-URI-Einstellungen an.

    1. Geben Sie im Textfeld OMA-URI **./Device/Vendor/MSFT/AssignedAccess/Configuration ein.**
    1. Wählen Sie Datentyp als **Zeichenfolge aus.**
    1. Kopieren Sie in das Textfeld value (Wert) die xml-Datei für die zugewiesene Zugriffskonfiguration(siehe Referenzlinks für Beispiele, die auf Ihrem Szenario basieren, und aktualisieren Sie sie nach Bedarf, bevor Sie kopieren und einfügen).
    1. Wählen Sie die Schaltfläche "Speichern" aus, um die Einstellung und Konfiguration zu speichern.

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. Wählen Sie aus, welchen Gruppen/Geräten oder Benutzern dieses Konfigurationsprofil zugewiesen werden soll. <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. Überprüfen und erstellen Sie , um das Konfigurationsprofil zu speichern.
1. Führen Sie die MDM-Synchronisierung entweder über das Gerät oder intune aus, um die Konfiguration auf das Gerät anzuwenden. Synchronisieren von Geräten aus [Intune](/mem/intune/remote-actions/device-sync#sync-a-device) oder auf dem Gerät über **Einstellungen -> Accounts -> Work** or school ->select the connected account **-> Info -> Sync**
1. Melden Sie sich als Zielbenutzer an, um den Kiosk zu erleben.

# <a name="runtime-provisioning---multi-app"></a>[Laufzeitbereitstellung : Mehrere Apps](#tab/ppkgmak)

## <a name="runtime-provisioning---multi-app"></a>Laufzeitbereitstellung : Mehrere Apps

1. Erstellen Sie eine XML-Konfiguration für Ihre gewünschte Kioskerfahrung. Sehen Sie [sich die](../hololens-kiosk-reference.md#kiosk-xml-code-samples) Beispiele hier an, um zu beginnen.

1. Öffnen [sie Windows-Konfigurations-Designer.](https://www.microsoft.com/store/apps/9nblggh4tx22)

1. Wählen Sie auf der Seite Start **die Option HoloLens Geräte bereitstellen aus.** <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. Wählen **Sie HoloLens 2 Geräte bereitstellen und** dann Weiter aus. <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. Geben Sie dem Projekt einen Namen. Schreiben Sie optional eine Beschreibung. Wählen Sie **Fertig stellen aus,** um fortzufahren.

6. Wählen Sie unten links auf dem Bildschirm Switch **to advanced editor (Zum erweiterten Editor wechseln) aus.** Bestätigen Sie den Wechsel zum erweiterten Editor, indem Sie **Ja auswählen.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. Erweitern Sie auf der linken Seite Runtimeeinstellungen, AssignedAccess, und wählen **Sie MultiAppAssignedAccess aus.** <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. Wählen Sie die Schaltfläche **Durchsuchen** -Schaltfläche, um den Datei-Explorer zu öffnen. Wählen Sie die konfigurierte Kiosk-XML-Datei aus.

9. Wählen **Sie Exportieren** und dann **Bereitstellungspaket aus.**

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. Ändern Sie den Besitzertyp in **IT-Administrator.** <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. Wählen Sie dreimal **Weiter** aus. Wählen Sie dann **Erstellen aus.**

12. Öffnen Sie nach dem Erstellen des Bereitstellungspakets den Ordner Ausgabespeicherort. Die PPKG-Datei ist Ihr Bereitstellungspaket. Optionaler Schritt: Speichern Sie Ihr Projekt.

13. Jetzt können Sie Ihr Bereitstellungspaket anwenden. Sie können entweder [ein Bereitstellungspaket](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) auf HoloLens Setup anwenden oder ein [Bereitstellungspaket](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)auf HoloLens Setup anwenden.

14. Melden Sie sich als Zielbenutzer an, um den Kiosk zu erleben.

# <a name="runtime-provisioning---single-app"></a>[Laufzeitbereitstellung : Einzelne App](#tab/ppkgsak)

## <a name="runtime-provisioning---single-app"></a>Laufzeitbereitstellung : Einzelne App

1. Öffnen [sie Windows-Konfigurations-Designer.](https://www.microsoft.com/store/apps/9nblggh4tx22)

1. Wählen Sie auf der Seite Start **die Option HoloLens Geräte bereitstellen aus.** <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. Wählen **Sie HoloLens 2 Geräte bereitstellen und** dann Weiter aus. <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. Geben Sie dem Projekt einen Namen. Schreiben Sie optional eine Beschreibung. Wählen Sie **Fertig stellen aus,** um fortzufahren.

5. Wählen Sie unten links auf dem Bildschirm Switch **to advanced editor (Zum erweiterten Editor wechseln) aus.** Bestätigen Sie den Wechsel zum erweiterten Editor, indem Sie **Ja auswählen.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. Erweitern Sie auf der linken Seite Runtimeeinstellungen, AssignedAccess, und wählen **Sie AssignedAccessSettings aus.** <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. Definieren Sie Ihren Kiosk im Textfeld. Im Folgenden wird beispielsweise ein einzelner App-Kiosk für ein lokales Konto namens LocalAccount erstellt, bei dem es sich um die Einstellungs-App handelt.
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. Wählen **Sie Exportieren** und dann **Bereitstellungspaket aus.** <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. Ändern Sie den Besitzertyp in **IT-Administrator.** <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. Wählen Sie dreimal **Weiter** aus. Wählen Sie dann **Erstellen aus.**

11. Öffnen Sie nach dem Erstellen des Bereitstellungspakets den Ordner Ausgabespeicherort. Die PPKG-Datei ist Ihr Bereitstellungspaket. Optionaler Schritt: Speichern Sie Ihr Projekt.

12. Jetzt können Sie Ihr Bereitstellungspaket anwenden. Sie können entweder [ein Bereitstellungspaket](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) auf HoloLens Setup anwenden oder ein [Bereitstellungspaket](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)auf HoloLens Setup anwenden.