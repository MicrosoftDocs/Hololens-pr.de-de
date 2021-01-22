---
title: Konfigurieren von HoloLens mithilfe eines Bereitstellungspakets (HoloLens)
description: Die Windows-Bereitstellung vereinfacht die Konfiguration von Endbenutzergeräten für IT-Administratoren, ohne dass diese ein Image erstellen müssen.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.custom:
- CI 115190
- CSSTroubleshooting
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b22baa62488bbdf6d2a8a43b6487bbe5ec3277cb
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284156"
---
# Konfigurieren von HoloLens mithilfe eines Bereitstellungspakets

[Die Bereitstellung von Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) erleichtert IT-Administratoren das Konfigurieren von Endbenutzergeräten ohne Imageerstellung. Windows-Konfigurations-Designer ist ein Tool zum Konfigurieren von Images und Laufzeiteinstellungen, die dann in Bereitstellungspakete integrierte werden.

Zu den HoloLens-Konfigurationen, die Sie in einem Bereitstellungspaket anwenden können, gehören die folgenden:

- Upgrade auf [Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- Einrichten eines lokalen Kontos
- Einrichten einer WLAN-Verbindung
- Anwenden von Zertifikaten auf das Gerät
- Aktivieren des Entwicklermodus
- Konfigurieren Sie den Kioskmodus, indem Sie unsere [detaillierten Anweisungen befolgen.](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

## Assistent für das Bereitstellungspaket für HoloLens

Der Assistent für HoloLens unterstützt Sie beim Konfigurieren der folgenden Einstellungen in einem Bereitstellungspaket:

- Upgrade auf die Enterprise Edition

    > [!NOTE]
    > Dies sollte nur für HoloLens 1st Gen-Geräte verwendet werden. Einstellungen in einem Bereitstellungspaket werden nur angewendet, wenn das Bereitstellungspaket eine Edition-Upgradelizenz auf Windows Holographic for Business enthält oder wenn das Gerät bereits auf [Windows Holographic for Business](hololens1-upgrade-enterprise.md)aktualisiert wurde.

- Konfigurieren der ersten HoloLens-Erfahrung (OOBE)
- Konfigurieren des Wi-Fi A0
- Registrieren des Geräts in Azure Active Directory oder Erstellen eines lokalen Kontos
- Hinzufügen von Zertifikaten
- Aktivieren des Entwicklermodus
- Konfigurieren Sie den Kioskmodus, indem Sie detaillierte [Anweisungen befolgen).](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

> [!WARNING]
> Sie müssen Windows-Konfigurations-Designer unter Windows10 ausführen, um die Azure Active Directory-Registrierung mit einem beliebigen Assistenten zu konfigurieren.

Bereitstellungspakete können Verwaltungsanweisungen und -richtlinien, benutzerdefinierte Netzwerkverbindungen und -richtlinien und vieles mehr enthalten.

> [!TIP]
> Verwenden Sie den Desktop-Assistenten, um ein Paket mit allgemeinen Einstellungen zu erstellen, und wechseln Sie dann zum erweiterten Editor, um weitere Einstellungen, Apps, Richtlinien usw. hinzuzufügen.

## Schritte zum Erstellen von Bereitstellungspaketen

1. **Option 1: Aus** [dem Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22). Dies umfasst HoloLens 2-Funktionen.
2. **Option 2:** [Aus dem Windows Assessment and Deployment Kit (ADK) für Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit). Wenn Sie Windows-Konfigurations-Designer aus dem Windows ADK installieren, wählen Sie im Dialogfeld "Features auswählen, die **Sie** installieren möchten" den **Konfigurations-Designer** aus. Diese Option enthält keine HoloLens 2-Funktionen.

> [!NOTE]
> Wenn Sie wissen, dass Sie einen Offline-PC verwenden, der Zugriff auf Den Windows-Konfigurations-Designer benötigt, befolgen Sie die [Offline-App-Installation( Anweisungen https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) für Advanced Recovery Companion). Treffen Sie die Auswahl für Windows-Konfigurations-Designer. 

### 2. Erstellen des Bereitstellungspakets

Erstellen Sie ein Bereitstellungspaket mit Windows-Konfigurations-Designer.

1. Öffnen Sie Windows-Konfigurations-Designer (standardmäßig unter „%windir%\Programme (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe“).

2. Wählen **Sie "HoloLens-Geräte bereitstellen" aus.**

   ![ICD-Startoptionen](images/icd-create-options-1703.png)

3. Benennen Sie Ihr Projekt, und wählen Sie **"Fertig stellen" aus.**

4. Lesen Sie die Anweisungen auf der Seite **"Erste Schritte",** und wählen Sie **"Weiter" aus.** Auf den Seiten für die Desktopbereitstellung werden Die folgenden Schritte ausgeführt.
  
> [!IMPORTANT]
> Wenn Sie ein Bereitstellungspaket erstellen, können Sie vertrauliche Informationen in die Projektdateien und die Bereitstellungspaketdatei (PPKG-Datei) aufnehmen. Obwohl Sie die PPKG-Datei verschlüsseln können, werden die Projektdateien nicht verschlüsselt. Sie sollten die Projektdateien an einem sicheren Ort speichern und sie löschen, wenn sie nicht mehr benötigt werden.

### Konfigurieren von Einstellungen

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>Navigieren Sie zu der Enterprise-Lizenzdatei, und wählen Sie sie aus, um die HoloLens Edition zu aktualisieren.</br></br>Sie können auch "Ja" oder "Nein" umschalten, um <strong> Teile der ersten Erfahrung </strong> <strong> </strong> auszublenden.</br></br>Wenn Sie das Gerät einrichten möchten, ohne eine Verbindung mit einem Wi-Fi herstellen zu müssen, setzen Sie den Wi-Fi <strong> auf </strong> <strong> "Ein". </strong></br></br>Wählen Sie eine Region und Zeitzone aus, in der das Gerät verwendet wird. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>In diesem Abschnitt können Sie die Details des Wi-Fi, mit dem das Gerät automatisch eine Verbindung herstellen soll. Wählen Sie dazu "Ein" aus, geben Sie die SSID, den Netzwerktyp <strong> </strong> ( Open oder <strong> </strong> <strong> WPA2-Personal ) und </strong> (bei <strong> WPA2-Personal) </strong> das Kennwort für das Drahtlosnetzwerk ein.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Sie können das Gerät in Azure Active Directory registrieren oder ein lokales Konto auf dem Gerät erstellen.</br></br>Bevor Sie einen Assistenten in Windows-Konfigurations-Designer verwenden, um die Azure AD-Massenregistrierung zu konfigurieren, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">richten Sie die Azure AD-Verknüpfung in Ihrer Organisation ein</a>. Die Einstellung <strong>Maximale Anzahl von Geräten pro Benutzer</strong> in Ihrem Azure AD-Mandanten bestimmt, wie oft das Massen-Token im Assistenten verwendet werden kann. Um das Gerät in Azure AD zu registrieren, wählen Sie diese Option aus, und geben Sie einen aussagekräftigen Namen für das Massen-Token ein, das Sie vom Assistenten erhalten. Legen Sie ein Ablaufdatum für das Token fest. (Das Maximum liegt bei 30Tagen ab Erhalt des Tokens.) Select <strong> Get bulk token </strong> . Geben Sie im&#39;A0 ein Konto ein, das über Berechtigungen zum Verbinden eines Geräts mit Azure AD verfügt, und geben Sie dann <strong> </strong> das Kennwort ein. Wählen <strong> Sie </strong> "Akzeptieren" aus, um Windows-Konfigurations-Designer die erforderlichen Berechtigungen zu erteilen. </br></br>Um ein lokales Konto zu erstellen, wählen Sie diese Option aus, und geben Sie einen Benutzernamen und ein Kennwort ein. </br></br><strong>Wichtig:</strong> <br />(Nur für Windows 10, Version 1607) Wenn Sie ein lokales Konto im Bereitstellungspaket erstellen, müssen Sie das Kennwort alle 42 Tage mithilfe der App <strong> </strong> "Einstellungen" ändern. Wenn das Kennwort innerhalb dieses Zeitraums nicht geändert wird, wird das Konto möglicherweise gesperrt, und eine Anmeldung ist nicht möglich.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Um dem Gerät ein Zertifikat bereitzustellen, klicken Sie auf <strong>Add a certificate</strong>. Geben Sie einen Namen für das Zertifikat ein, navigieren Sie zum Zertifikat, das verwendet werden soll, und wählen Sie es aus.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br><strong>Umschalten Sie </strong> "Ja" oder <strong> </strong> "Nein", um den Entwicklermodus auf der HoloLens zu aktivieren. <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Weitere Informationen zum Entwicklermodus</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>Legen Sie kein Kennwort zum Schutz Des Bereitstellungspakets. Wenn das Bereitstellungspaket durch ein Kennwort geschützt ist, kann das HoloLens-Gerät nicht bereitgestellt werden.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Nachdem Sie fertig sind, wählen Sie **"Erstellen" aus.** Es dauert nur wenige Sekunden. Wenn das Paket erstellt wurde, wird der Speicherort des Pakets als Hyperlink am unteren Rand der Seite angezeigt.

### 3. Erstellen eines Bereitstellungspakets für HoloLens mithilfe der erweiterten Bereitstellung

> [!NOTE]
> Ein Bereitstellungspaket, das Sie **in** der erweiterten Bereitstellung erstellen, muss keine Lizenz für ein Editionupgrade auf Windows Holographic for Business enthalten, um erfolgreich auf eine HoloLens (1. Generation) angewendet zu werden. [Weitere Informationen finden Sie unter Windows Holographic for Business für HoloLens (1. Generation).](hololens1-upgrade-enterprise.md)

1. Wählen Sie auf der Startseite des Windows-Konfigurations-Designers **Erweiterte Bereitstellung**.
2. Geben Sie im Fenster **Projektdetails eingeben** den Namen und den Speicherort für Ihr Projekt an. Optional können Sie eine kurze Beschreibung zu Ihrem Projekt eingeben.

3. Wählen Sie **Weiter** aus.

4. Wählen Sie **im Fenster auswählen, welche** Einstellungen angezeigt und konfiguriert werden soll, Windows **10 Holographic**aus, und wählen Sie dann **"Weiter" aus.**

5. Select **Finish**.

6. Erweitern **Sie die Laufzeiteinstellungen,** und passen Sie das Paket mithilfe einer der weiter [unten in diesem Artikel beschriebenen Einstellungen an.](#what-you-can-configure)

    > [!IMPORTANT]
    > (Nur für Windows 10, Version 1607) Wenn Sie ein lokales Konto im Bereitstellungspaket erstellen, **** müssen Sie das Kennwort alle 42 Tage mithilfe der App "Einstellungen" ändern. Wenn das Kennwort innerhalb dieses Zeitraums nicht geändert wird, wird das Konto möglicherweise gesperrt, und eine Anmeldung ist nicht möglich. Wenn das Benutzerkonto gesperrt wird, müssen Sie [eine vollständige Gerätewiederherstellung](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery) ausführen.

7. Wählen Sie **"Datei**  >  **speichern" aus.**

8. Lesen Sie die Warnung, dass Projektdateien möglicherweise vertrauliche Informationen enthalten, und wählen Sie **OK aus.**

    > [!IMPORTANT]
    > Wenn Sie ein Bereitstellungspaket erstellen, können Sie vertrauliche Informationen in die Projektdateien und die Bereitstellungspaketdatei (PPKG-Datei) aufnehmen. Obwohl Sie die PPKG-Datei verschlüsseln können, werden die Projektdateien nicht verschlüsselt. Sie sollten die Projektdateien an einem sicheren Ort speichern und löschen, wenn sie nicht mehr benötigt werden.
    
9. Wählen **Sie "Bereitstellungspaket**  >  **exportieren" aus.**

10. Ändern **Sie den Besitzer** in den **IT-Administrator.** Dadurch wird die Rangfolge dieses Bereitstellungspakets höher als die von anderen Quellen auf dieses Gerät angewendeten Bereitstellungspakete. Wählen Sie **Weiter** aus.

11. Legen Sie einen Wert für **Paketversion**fest.

    > [!TIP]
    > Sie können Änderungen an vorhandenen Paketen vornehmen und die Versionsnummer ändern, um bereits angewendete Pakete zu aktualisieren.

12. Wählen Sie **unter "Sicherheitsdetails für das Bereitstellungspaket auswählen"** die Option **"Weiter" aus.**

    > [!WARNING]
    > Wenn Sie das Bereitstellungspaket verschlüsseln, ist die Bereitstellung des HoloLens-Geräts nicht möglich.  

13. Wählen **Sie "Weiter"** aus, um den Ausgabespeicherort anzugeben, an dem das Bereitstellungspaket nach dem Erstellen erstellt werden soll. Standardmäßig verwendet der Windows-Konfigurations-Designer den Projektordner als Ausgabespeicherort.

    Optional können Sie **"Durchsuchen"** auswählen, um den Standardausgabespeicherort zu ändern.

14. Wählen Sie **Weiter** aus.

15. Wählen **Sie Build** aus, um mit dem Erstellen des Pakets zu beginnen. Die Projektinformationen werden auf der Buildseite angezeigt, und die Statusanzeige gibt den Buildstatus an.

16. Wenn der Build abgeschlossen ist, wählen Sie **"Fertig stellen" aus.**

<span id="apply" />

## Anwenden eines Bereitstellungspakets auf HoloLens während des Setups

HoloLens 2-Geräte unter Windows Holographic, Version 2004 oder Build [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) oder höher, verwenden möglicherweise ein USB-Laufwerk, um ein Bereitstellungspaket anzuwenden. Kopieren Sie einfach die PPKG-Datei in das Stammverzeichnis des USB-Laufwerks. Bereitstellungspakete werden nur angewendet, wenn sie sich im Stammverzeichnis des USB-Laufwerks finden. Mehrere bereitstellungspaket vorhandenen wird sequenziell angewendet werden.

HoloLens 2-Geräte unter [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) oder höher, verfügen über neuere Features, um diesen Prozess zu optimieren und zu vereinfachen und so automatisch zu machen. Lesen Sie die folgenden Abschnitte:

- [Automatisches Starten der Bereitstellung über USB](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [Automatisches Bestätigen von Bereitstellungspaketen in der OOBE](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Automatische Bereitstellung ohne Verwendung der Benutzeroberfläche](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. Verwenden Sie das USB-Kabel, um das Gerät mit einem PC (oder usb-Laufwerk für HoloLens 2 wie oben erwähnt) zu verbinden, und starten Sie dann das Gerät. Fahren Sie nicht nach der **Ersten interagierbaren Momentseite** der OOBE fort.   
    - Auf HoloLens (1. Generation) enthält diese Seite ein blaues Feld. 
    - Auf HoloLens 2 enthält diese Seite den Hummingbird.

2. Drücken Sie die Tasten **Leiser** und **Ein/Aus** kurz gleichzeitig, und geben Sie sie anschließend wieder frei. 

3. HoloLens wird im Datei-Explorer auf dem PC als Gerät angezeigt.

4. Verschieben Sie das Bereitstellungspaket (.ppkg) im Datei-Explorer per Drag & Drop zum Gerätespeicher.

5. Drücken Und lassen Sie die **Tasten "Lautstärke** nach **** unten" und **"Ein/Aus"** auf der Seite "Erster interagierbarer Moment" der OOBE kurz gleichzeitig los.

6. Das Gerät fragt Sie, ob Sie dem Paket vertrauen und es anwenden möchten. Bestätigen Sie, dass Sie dem Paket vertrauen.

7. Sie können erkennen, ob das Paket erfolgreich angewendet wurde oder nicht. Wenn das Paket nicht erfolgreich angewendet wurde, können Sie es korrigieren und den Vorgang wiederholen. Wenn das Paket erfolgreich angewendet wurde, fahren Sie mit der Windows-Willkommensseite fort.

> [!NOTE]
> If the device was purchased before August 2016, you will need to sign in to the device by using a Microsoft account, get the latest operating system update, and then reset the operating system in order to apply the provisioning package.

### Automatisches Starten der Bereitstellung über USB

- Automatisierte Prozesse, die eine geringere Benutzerinteraktion ermöglichen, wenn usb-Laufwerke mit Bereitstellungspaketen während der OOBE verwendet werden.

Vor dieser Version mussten Benutzer den Bereitstellungsbildschirm während der OOBE manuell starten, um die Bereitstellung mithilfe einer Tastenkombination zu ermöglichen. Jetzt können Benutzer die Tastenkombination überspringen, indem sie ein Bereitstellungspaket auf einem USB-Speicherlaufwerk verwenden. 

1. Schließen Sie das USB-Laufwerk während des ersten interagierbaren Moments der OOBE mit dem Bereitstellungspaket an.
1. Wenn das Gerät bereit für die Bereitstellung ist, wird die Eingabeaufforderung automatisch mit der Bereitstellungsseite geöffnet. 

Hinweis: Wenn ein USB-Laufwerk beim Starten des Geräts angeschlossen bleibt, enumeriert die OOBE vorhandenes USB-Speichergerät und watch for additional ones being plugged in.

Informationen zum Anwenden [von Bereitstellungspaketen während der OOBE](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

### Automatisches Bestätigen von Bereitstellungspaketen in der OOBE
- Wenn die Seite "Bereitstellungspaket" angezeigt wird, werden automatisch alle aufgelisteten Pakete angewendet.

Wenn der Hauptbildschirm der Bereitstellung angezeigt wird, zählt die OOBE 10 Sekunden nach unten, bevor automatisch mit der Anwendung aller Bereitstellungspakete begonnen wird. Benutzer können dies nach der Überprüfung der erwarteten Pakete innerhalb von 10 Sekunden weiterhin bestätigen oder abbrechen.

### Automatische Bereitstellung ohne Verwendung der Benutzeroberfläche
- Kombinierte automatische Prozesse für reduzierte Geräteinteraktionen für die Bereitstellung. 

Durch kombinieren der automatischen Start der Bereitstellung über USB-Geräte und der automatischen Bestätigung von Bereitstellungspaketen kann ein Benutzer HoloLens 2-Geräte automatisch bereitstellen, ohne die Benutzeroberfläche des Geräts zu verwenden oder sogar das Gerät zu tragen. Sie können weiterhin das gleiche USB-Laufwerk und das gleiche Bereitstellungspaket für mehrere Geräte verwenden. Dies ist hilfreich, um mehrere Geräte gleichzeitig im selben Bereich bereitstellen zu können. 

1. [Erstellen Sie ein Bereitstellungspaket mit](hololens-provisioning.md) [dem Windows-Konfigurations-Designer.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Kopieren Sie das Paket auf ein USB-Speicherlaufwerk.
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build](https://aka.ms/hololens2previewdownload). 
1. Wenn [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) das Blinken des Geräts abgeschlossen hat, ziehen Sie das USB-C-Kabel ab. 
1. Schließen Sie Das USB-Laufwerk an das Gerät an.
1. Wenn das HoloLens 2-Gerät in die OOBE startet, erkennt es automatisch das Bereitstellungspaket auf dem USB-Laufwerk und startet die Bereitstellungsseite.
1. Nach 10 Sekunden wird das Bereitstellungspaket automatisch vom Gerät angewendet. 

Ihr Gerät ist jetzt konfiguriert und zeigt den Bildschirm "Bereitstellung erfolgreich" an.

## Anwenden eines Bereitstellungspakets auf HoloLens nach dem Setup

> [!NOTE]
> Diese Schritte gelten nur für Windows 10, Version 1809.

Führen Sie auf Ihrem PC die folgenden Schritte aus:
1. Erstellen Sie ein Bereitstellungspaket, wie unter ["Erstellen eines Bereitstellungspakets für HoloLens mit dem HoloLens-Assistenten" beschrieben.](hololens-provisioning.md)
2. Schließen Sie das HoloLens-Gerät mithilfe eines USB-Kabels an einen PC an. HoloLens wird im Datei-Explorer auf dem PC als Gerät angezeigt.
3. Drag and drop the provisioning package to the Documents folder on the HoloLens.

Führen Sie auf Ihrer HoloLens die folgenden Schritte aus:
1. Wechseln **** Sie zu  >  **"Einstellungskonten**  >  **" Auf Arbeits- oder Schulkonto zugreifen".** 
2. Wählen **Sie unter "Verwandte Einstellungen"** die **Option "Bereitstellungspaket hinzufügen oder entfernen" aus.**
3. Wählen Sie auf der nächsten Seite **"Paket hinzufügen"** aus, um die Dateiauswahl zu starten, und wählen Sie Das Bereitstellungspaket aus. Wenn der Ordner leer ist, stellen Sie sicher, dass Sie **"Dieses Gerät"** und **"Dokumente" auswählen.**

Nachdem Das Paket angewendet wurde, wird es in der Liste der **installierten Pakete angezeigt.** Um die Paketdetails anzuzeigen oder das Paket vom Gerät zu entfernen, wählen Sie das aufgelistete Paket aus.

## Konfigurationsmöglichkeiten

Bereitstellungspakete nutzen Konfigurationsdienstanbieter (Configuration Service Providers, CSPs). Wenn Sie mit CSPs nicht vertraut sind, lesen Sie den Abschnitt [Einführung in Konfigurationsdienstanbieter (Configuration Service Providers, CSPs) für IT-Experten](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).

Wenn Sie ein Bereitstellungspaket für Windows Holographic im Windows-Konfigurations-Designer erstellen, basieren die Einstellungen in **Verfügbare Anpassungen** auf [CSPs, die in Windows Holographic unterstützt werden](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices). Die folgende Tabelle zeigt die Einstellungen, die Sie möglicherweise für HoloLens konfigurieren sollten.

![Allgemeine Laufzeiteinstellungen für HoloLens](images/icd-settings.png)

| Einstellung | Beschreibung |
| --- | --- |
| **Zertifikate** | Stellen Sie ein Zertifikat für HoloLens bereit.  |
| **ConnectivityProfiles** | Stellen Sie ein WLAN-Profil für HoloLens bereit.   |
| **EditionUpgrade** | [Upgrade auf Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **Richtlinien** | Lassen Sie den Entwicklermodus auf HoloLens zu, oder sperren Sie ihn. [Richtlinien, die von Windows Holographic for Business unterstützt werden](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## App-Installation über Bereitstellungspaket

Apps können über Bereitstellungspakete auf HoloLens 2-Geräten installiert werden. Dies ermöglicht ein leicht wiederverlegbares Paket, mit dem Sie Ihre Apps verteilen können. Lesen Sie die vollständigen Anweisungen [zum Bereitstellen von Apps über Bereitstellungspakete.](app-deploy-provisioning-package.md)  

> [!NOTE]
> HoloLens (1. Generation) bietet eingeschränkte Unterstützung für die Installation von Apps (**UniversalAppInstall**) mithilfe eines Bereitstellungspakets. HoloLens (1. Generation)-Geräte unterstützen nur die Installation einer App über PPKG nur während der OOBE und nur bei Installationen des Benutzerkontexts.
