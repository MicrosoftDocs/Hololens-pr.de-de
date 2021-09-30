---
ms.openlocfilehash: 3d6b36124cd50dcc9f420227cb7787f0d787c013
ms.sourcegitcommit: c73cdefbdb4411f6a187cc38bb2570dadeb156bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2021
ms.locfileid: "129220951"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[Microsoft Intune-Kioskvorlage für einzelne Apps](#tab/uisak)

### <a name="microsoft-intune-single-app-kiosk-template"></a>Microsoft Intune-Kioskvorlage für einzelne Apps

1. Erstellen Sie ein Konfigurationsprofil <br>
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Wählen Sie eine Kioskvorlage aus <br>
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Wählen Sie zwischen einem Kiosk für eine einzelne oder für mehrere Apps, und wählen Sie außerdem die Art der Zielgruppenadressierung für den Kioskmodus aus <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. Wählen Sie die App aus, die im Kioskmodus ausgeführt werden soll <br>
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. Behalten Sie für die restlichen Optionen die Standardwerte bei <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Wählen Sie aus, welchen Gruppen/Geräten oder Benutzern dieses Konfigurationsprofil zugewiesen werden soll <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. Führen Sie die Überprüfung und Erstellung aus, um das Konfigurationsprofil zu speichern
8. Führen Sie die MDM-Synchronisierung entweder am Gerät oder in Intune aus, um die Konfiguration auf das Gerät anzuwenden. [Synchronisieren Sie die Geräte in Intune](/mem/intune/remote-actions/device-sync#sync-a-device) oder am Gerät über **Einstellungen > Konten > Geschäfts-, Schul- oder Unikonto >** , wählen Sie das verbundene Konto aus, dann **> Info > Synchronisieren**
9. Melden Sie sich als Zielbenutzer an, um den Kiosk zu erleben.

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[Microsoft Intune-Kioskvorlage für mehrere Apps](#tab/uimak)

### <a name="microsoft-intune-multi-app-kiosk-template"></a>Microsoft Intune-Kioskvorlage für mehrere Apps

1. Erstellen Sie ein Konfigurationsprofil <br>
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Wählen Sie eine Kioskvorlage aus <br>
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Wählen Sie zwischen einem Kiosk für eine einzelne oder für mehrere Apps, und wählen Sie außerdem die Art der Zielgruppenadressierung für den Kioskmodus aus <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. Wählen Sie die Apps aus, die im Kioskmodus ausgeführt werden sollen <br>
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. Behalten Sie für die restlichen Optionen die Standardwerte bei <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Wählen Sie aus, welchen Gruppen/Geräten oder Benutzern dieses Konfigurationsprofil zugewiesen werden soll <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. Führen Sie die Überprüfung und Erstellung aus, um das Konfigurationsprofil zu speichern
8. Führen Sie die MDM-Synchronisierung entweder am Gerät oder in Intune aus, um die Konfiguration auf das Gerät anzuwenden. [Synchronisieren Sie die Geräte in Intune](/mem/intune/remote-actions/device-sync#sync-a-device) oder am Gerät über **Einstellungen > Konten > Geschäfts-, Schul- oder Unikonto >** , wählen Sie das verbundene Konto aus, dann **> Info > Synchronisieren**
9. Melden Sie sich als Zielbenutzer an, um den Kiosk zu erleben.

# <a name="microsoft-intune-custom-template"></a>[Benutzerdefinierte Microsoft Intune-Vorlage](#tab/intunecustom)

### <a name="microsoft-intune-custom-template"></a>Benutzerdefinierte Microsoft Intune-Vorlage

1. Erstellen Sie eine XML-Konfiguration für Ihre gewünschte Kioskerfahrung. Anregungen für den Einstieg finden Sie in diesen [Beispielen](../hololens-kiosk-reference.md#kiosk-xml-code-samples).

1. Erstellen Sie ein benutzerdefiniertes Konfigurationsprofil <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. Geben Sie den Namen des benutzerdefinierten Konfigurationsprofils an, und klicken Sie im Abschnitt „Konfigurationseinstellungen“ auf „Hinzufügen“, um OMA-URI-Einstellungen hinzuzufügen. <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. Geben Sie den Namen der OMA-URI-Einstellungen an.

    1. Geben Sie im OMA-URI-Textfeld **./Device/Vendor/MSFT/AssignedAccess/Configuration** ein
    1. Legen Sie als Datentyp **Zeichenfolge** fest.
    1. Fügen Sie in das Wert-Textfeld den XML-Code für die zugewiesene Zugriffskonfiguration durch Kopieren und Einfügen ein (Beispiele auf der Grundlage Ihres Szenarios finden Sie über die Referenzlinks; nehmen Sie bei Bedarf vor dem Kopieren und Einfügen Anpassungen vor).
    1. Wählen Sie die Schaltfläche „Speichern“ aus, um Einstellungen und Konfiguration zu speichern.

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. Wählen Sie aus, welchen Gruppen/Geräten oder Benutzern dieses Konfigurationsprofil zugewiesen werden soll. <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. Führen Sie die Überprüfung und Erstellung aus, um das Konfigurationsprofil zu speichern.
1. Führen Sie die MDM-Synchronisierung entweder am Gerät oder in Intune aus, um die Konfiguration auf das Gerät anzuwenden. [Synchronisieren Sie die Geräte in Intune](/mem/intune/remote-actions/device-sync#sync-a-device) oder am Gerät über **Einstellungen > Konten > Geschäfts-, Schul- oder Unikonto >** , wählen Sie das verbundene Konto aus, dann **Info > Synchronisieren**
1. Melden Sie sich als Zielbenutzer an, um den Kiosk zu erleben.

# <a name="runtime-provisioning---multi-app"></a>[Laufzeitbereitstellung: Mehrere Apps](#tab/ppkgmak)

### <a name="runtime-provisioning---multi-app"></a>Laufzeitbereitstellung: Mehrere Apps

1. Erstellen Sie eine XML-Konfiguration für Ihre gewünschte Kioskerfahrung. Anregungen für den Einstieg finden Sie in diesen [Beispielen](../hololens-kiosk-reference.md#kiosk-xml-code-samples).

1. Öffnen Sie den [Windows-Konfigurationsdesigner](https://www.microsoft.com/store/apps/9nblggh4tx22).

1. Wählen Sie auf Startseite die Option **HoloLens-Geräte bereitstellen** aus. <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. Wählen Sie **HoloLens 2-Geräte bereitstellen** und dann „Weiter“ aus. <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. Geben Sie dem Projekt einen Namen. Geben Sie optional eine Beschreibung ein. Wählen Sie **Fertig stellen** aus, um fortzufahren.

6. Wählen Sie unten links auf dem Bildschirm **Wechseln zum erweiterten Editor** aus. Bestätigen Sie den Wechsel zum erweiterten Editor, indem Sie **Ja** auswählen. <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. Klappen Sie auf der linken Seite „Runtimeeinstellungen“ > „AssignedAccess“ auf, und wählen Sie **MultiAppAssignedAccess** aus. <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. Wählen Sie die Schaltfläche **Durchsuchen** aus, um den Datei-Explorer zu öffnen. Wählen Sie Ihre konfigurierte Kiosk-XML-Datei aus.

9. Wählen Sie **Exportieren** und dann **Bereitstellungspaket** aus.

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. Ändern Sie den Besitzertyp in **IT-Administrator**. <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. Wählen Sie dreimal **Weiter** aus. Wählen Sie anschließend **Build** aus.

12. Öffnen Sie nach dem Erstellen des Bereitstellungspakets den Ordner des Ausgabespeicherorts. Die PPKG-Datei ist Ihr Bereitstellungspaket. Optionaler Schritt: Speichern Sie Ihr Projekt.

13. Jetzt können Sie Ihr Bereitstellungspaket anwenden. Sie können entweder [ein Bereitstellungspaket beim Setup auf HoloLens anwenden](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) oder [ein Bereitstellungspaket nach dem Setup auf HoloLens anwenden](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).

14. Melden Sie sich als Zielbenutzer an, um den Kiosk zu erleben.

# <a name="runtime-provisioning---single-app"></a>[Laufzeitbereitstellung: Einzelne App](#tab/ppkgsak)

### <a name="runtime-provisioning---single-app"></a>Laufzeitbereitstellung: Einzelne App

1. Öffnen Sie den [Windows-Konfigurationsdesigner](https://www.microsoft.com/store/apps/9nblggh4tx22).

1. Wählen Sie auf Startseite die Option **HoloLens-Geräte bereitstellen** aus. <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. Wählen Sie **HoloLens 2-Geräte bereitstellen** und dann „Weiter“ aus. <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. Geben Sie dem Projekt einen Namen. Geben Sie optional eine Beschreibung ein. Wählen Sie **Fertig stellen** aus, um fortzufahren.

5. Wählen Sie unten links auf dem Bildschirm **Wechseln zum erweiterten Editor** aus. Bestätigen Sie den Wechsel zum erweiterten Editor, indem Sie **Ja** auswählen. <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. Klappen Sie auf der linken Seite „Runtimeeinstellungen“ > „AssignedAccess“ auf, und wählen Sie **AssignedAccessSettings** aus. <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. Definieren Sie Ihren Kiosk im Textfeld. Im Folgenden wird beispielsweise ein Kiosk mit einer einzelnen App für ein lokales Konto namens LocalAccount erstellt, bei der es sich um die Einstellungs-App handelt.
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. Wählen Sie **Exportieren** und dann **Bereitstellungspaket** aus. <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. Ändern Sie den Besitzertyp in **IT-Administrator**. <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. Wählen Sie dreimal **Weiter** aus. Wählen Sie anschließend **Build** aus.

11. Öffnen Sie nach dem Erstellen des Bereitstellungspakets den Ordner des Ausgabespeicherorts. Die PPKG-Datei ist Ihr Bereitstellungspaket. Optionaler Schritt: Speichern Sie Ihr Projekt.

12. Jetzt können Sie Ihr Bereitstellungspaket anwenden. Sie können entweder [ein Bereitstellungspaket beim Setup auf HoloLens anwenden](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) oder [ein Bereitstellungspaket nach dem Setup auf HoloLens anwenden](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).