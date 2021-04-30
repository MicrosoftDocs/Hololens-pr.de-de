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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309858"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>Konfigurieren von HoloLens mithilfe eines Bereitstellungspakets

[Die Windows-Bereitstellung](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) erleichtert IT-Administratoren das Konfigurieren von Endbenutzergeräten ohne Imageerstellung. Der Windows-Konfigurations-Designer ist ein Tool zum Konfigurieren von Images und Laufzeiteinstellungen, die dann in Bereitstellungspakete integriert werden.

Einige der HoloLens-Konfigurationen, die Sie in einem Bereitstellungspaket anwenden können, sind:

- Upgrade auf [Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- Einrichten eines lokalen Kontos
- Einrichten einer WLAN-Verbindung
- Anwenden von Zertifikaten auf das Gerät
- Aktivieren des Entwicklermodus
- Konfigurieren Sie den Kioskmodus, indem Sie unsere [ausführlichen Anweisungen](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)befolgen.

## <a name="provisioning-package-hololens-wizard"></a>HoloLens-Assistent für Bereitstellungspakete

Mit dem HoloLens-Assistenten können Sie die folgenden Einstellungen in einem Bereitstellungspaket konfigurieren:

- Upgrade auf die Enterprise Edition

    > [!NOTE]
    > Dies sollte nur für HoloLens-Geräte der ersten Generation verwendet werden. Einstellungen in einem Bereitstellungspaket werden nur angewendet, wenn das Bereitstellungspaket eine Editionsupgradelizenz für Windows Holographic for Business enthält oder [wenn das Gerät bereits auf Windows Holographic for Business aktualisiert wurde.](hololens1-upgrade-enterprise.md)

- Konfigurieren der ersten HoloLens-Benutzeroberfläche (OOBE)
- Konfigurieren des Wi-Fi Netzwerks
- Registrieren Sie das Gerät bei Azure Active Directory, oder erstellen Sie ein lokales Konto.
- Hinzufügen von Zertifikaten
- Aktivieren des Entwicklermodus
- Konfigurieren Sie den Kioskmodus, indem Sie [die ausführlichen Anweisungen](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)befolgen.

> [!WARNING]
> Sie müssen den Windows-Konfigurations-Designer auf Windows 10 ausführen, um Azure Active Directory Registrierung mit einem der Assistenten zu konfigurieren.

Bereitstellungspakete können Verwaltungsanweisungen und -richtlinien, benutzerdefinierte Netzwerkverbindungen und -richtlinien und vieles mehr enthalten.

> [!TIP]
> Verwenden Sie den Desktop-Assistenten, um ein Paket mit den allgemeinen Einstellungen zu erstellen, und wechseln Sie dann zum erweiterten Editor, um weitere Einstellungen, Apps, Richtlinien usw. hinzuzufügen.

## <a name="steps-for-creating-provisioning-packages"></a>Schritte zum Erstellen von Bereitstellungspaketen

1. **Option 1: Aus** [Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22). Dies umfasst HoloLens 2 Funktionen.
2. **Option 2: Aus** [dem Windows Assessment and Deployment Kit (ADK) für Windows 10.](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit) Wenn Sie den Windows-Konfigurations-Designer über  das Windows ADK installieren, wählen Sie im Dialogfeld Features auswählen, die Sie installieren möchten die Option **Konfigurations-Designer** aus. Diese Option umfasst keine HoloLens 2 Funktionen.

> [!NOTE]
> Wenn Sie wissen, dass Sie einen Offline-PC verwenden, der Zugriff auf den Windows-Konfigurations-Designer benötigt, befolgen Sie die Anweisungen unter [Offline-App-Installation( für https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) Advanced Recovery Companion). Machen Sie Windows-Konfigurations-Designer zu Ihrer Auswahl. 

### <a name="2-create-the-provisioning-package"></a>2. Erstellen des Bereitstellungspakets

Verwenden Sie das Windows-Konfigurations-Designer-Tool, um ein Bereitstellungspaket zu erstellen.

1. Öffnen Sie den Windows-Konfigurations-Designer (standardmäßig %windir%\Programme (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).

2. Wählen Sie **HoloLens-Geräte bereitstellen aus.**

   ![ICD-Startoptionen](images/icd-create-options-1703.png)

3. Nennen Sie Ihr Projekt, und wählen Sie **Fertig stellen aus.**

4. Lesen Sie die Anweisungen auf der **Seite Erste Schritte,** und wählen Sie **Weiter aus.** Auf den Seiten für die Desktopbereitstellung werden die folgenden Schritte beschrieben.
  
> [!IMPORTANT]
> Wenn Sie ein Bereitstellungspaket erstellen, können Sie vertrauliche Informationen in die Projektdateien und das Bereitstellungspaket (PPKG-Datei) aufnehmen. Obwohl Sie die PPKG-Datei verschlüsseln können, werden die Projektdateien nicht verschlüsselt. Sie sollten die Projektdateien an einem sicheren Ort speichern und löschen, wenn sie nicht mehr benötigt werden.

### <a name="configure-settings"></a>Konfigurieren von Einstellungen

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>Navigieren Sie zur Enterprise-Lizenzdatei, und wählen Sie sie aus, um ein Upgrade der HoloLens-Edition durchführen zu können.</br></br>Sie können auch <strong></strong> Ja oder Nein <strong>umschalten,</strong> um Teile der ersten Erfahrung auszublenden.</br></br>Wenn Sie das Gerät einrichten möchten, ohne eine Verbindung mit einem Wi-Fi herstellen zu müssen, legen Sie Wi-Fi <strong>Ein</strong> <strong>fest.</strong></br></br>Wählen Sie eine Region und zeitzone aus, in der das Gerät verwendet wird. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>In diesem Abschnitt können Sie die Details des Wi-Fi drahtlosnetzwerks eingeben, mit dem das Gerät automatisch eine Verbindung herstellen soll. Wählen Sie hierzu <strong>Ein</strong>aus, geben Sie die SSID, den Netzwerktyp<strong>(Open</strong> oder <strong>WPA2-Personal)</strong>und (bei <strong>WPA2-Personal)</strong>das Kennwort für das Drahtlosnetzwerk ein.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Sie können das Gerät bei Azure Active Directory registrieren oder ein lokales Konto auf dem Gerät erstellen.</br></br>Bevor Sie einen Windows-Konfigurations-Designer-Assistenten zum Konfigurieren der Massenregistrierung Azure AD verwenden, richten Sie <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">Azure AD in Ihrer Organisation ein.</a> Die <strong>maximale Anzahl von Geräten pro Benutzereinstellung</strong> in Ihrem Azure AD Mandanten bestimmt, wie oft das Massentoken verwendet werden kann, das Sie im Assistenten erhalten. Um das Gerät bei Azure AD zu registrieren, wählen Sie diese Option aus, und geben Sie einen Anzeigenamen für das Massentoken ein, das Sie mit dem Assistenten erhalten. Legen Sie ein Ablaufdatum für das Token fest (maximal 30 Tage ab dem Datum, an dem Sie das Token erhalten). Wählen <strong>Sie Massentoken abrufen</strong>aus. Geben Sie im Fenster Let&#39;s get you signed in (&#39;anmelden) ein Konto ein, das über Berechtigungen zum Beitreten eines <strong>Geräts</strong> zu Azure AD verfügt, und geben Sie dann das Kennwort ein. Wählen Sie <strong>Akzeptieren</strong> aus, um dem Windows-Konfigurations-Designer die erforderlichen Berechtigungen zu erteilen. </br></br>Um ein lokales Konto zu erstellen, wählen Sie diese Option aus, und geben Sie einen Benutzernamen und ein Kennwort ein. </br></br><strong>Wichtig:</strong> <br />(Nur für Windows 10 Version 1607) Wenn Sie ein lokales Konto im Bereitstellungspaket erstellen, müssen Sie das Kennwort alle 42 Tage mithilfe der <strong>App Einstellungen</strong> ändern. Wenn das Kennwort innerhalb dieses Zeitraums nicht geändert wird, wird das Konto möglicherweise gesperrt, und eine Anmeldung ist nicht möglich.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Klicken Sie zum Bereitstellen des Geräts mit einem Zertifikat auf <strong>Zertifikat hinzufügen.</strong> Geben Sie einen Namen für das Zertifikat ein, navigieren Sie zu dem zu verwendenden Zertifikat, und wählen Sie es aus.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>Schalten Sie <strong>Ja</strong> oder <strong>Nein</strong> ein, um den Entwicklermodus auf der HoloLens zu aktivieren. <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Weitere Informationen zum Entwicklermodus</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>Legen Sie kein Kennwort fest, um Ihr Bereitstellungspaket zu schützen. Wenn das Bereitstellungspaket durch ein Kennwort geschützt ist, schlägt die Bereitstellung des HoloLens-Geräts fehl.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Wählen Sie **Erstellen** aus, wenn Sie fertig sind. Es dauert nur wenige Sekunden. Wenn das Paket erstellt wird, wird der Speicherort des Pakets als Link am unteren Rand der Seite angezeigt.

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3. Erstellen eines Bereitstellungspakets für HoloLens mithilfe der erweiterten Bereitstellung

> [!NOTE]
> Ein Bereitstellungspaket, das Sie **in** Der erweiterten Bereitstellung erstellen, muss keine Editionsupgradelizenz für Windows Holographic for Business enthalten, um erfolgreich auf eine HoloLens (1. Generation) angewendet zu werden. [Weitere Informationen finden Windows Holographic for Business für HoloLens (1. Generation).](hololens1-upgrade-enterprise.md)

1. Wählen Sie auf der Startseite des Windows-Konfigurations-Designers die Option **Erweiterte Bereitstellung aus.**
2. Geben Sie im Fenster **Projektdetails eingeben** den Namen und den Speicherort für Ihr Projekt an. Optional können Sie eine kurze Beschreibung zu Ihrem Projekt eingeben.

3. Wählen Sie **Weiter** aus.

4. Wählen Sie **im Fenster Wählen Sie aus,** welche Einstellungen angezeigt und konfiguriert werden, Windows 10 Holographic **aus,** und klicken Sie dann auf **Weiter.**

5. Wählen Sie **Fertig stellen** aus.

6. Erweitern **Sie Laufzeiteinstellungen,** und passen Sie das Paket mithilfe einer der weiter unten [in diesem Artikel beschriebenen Einstellungen an.](#what-you-can-configure)

    > [!IMPORTANT]
    > (Nur Windows 10 Version 1607) Wenn Sie im Bereitstellungspaket ein lokales Konto erstellen,  müssen Sie das Kennwort mithilfe der App Einstellungen alle 42 Tage ändern. Wenn das Kennwort innerhalb dieses Zeitraums nicht geändert wird, wird das Konto möglicherweise gesperrt, und eine Anmeldung ist nicht möglich. Wenn das Benutzerkonto gesperrt wird, müssen Sie [eine vollständige Gerätewiederherstellung](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery) ausführen.

7. Wählen Sie **Datei** > **Speichern** aus.

8. Lesen Sie die Warnung, dass Projektdateien möglicherweise vertrauliche Informationen enthalten, und wählen Sie **OK aus.**

    > [!IMPORTANT]
    > Wenn Sie ein Bereitstellungspaket erstellen, können Sie vertrauliche Informationen in die Projektdateien und das Bereitstellungspaket (PPKG-Datei) aufnehmen. Obwohl Sie die PPKG-Datei verschlüsseln können, werden die Projektdateien nicht verschlüsselt. Sie sollten die Projektdateien an einem sicheren Ort speichern und löschen, wenn sie nicht mehr benötigt werden.
    
9. Wählen Sie  >  **Bereitstellungspaket exportieren aus.**

10. Ändern **Sie Besitzer** in **IT-Administrator.** Dadurch wird die Rangfolge dieses Bereitstellungspakets höher als das Bereitstellen von Paketen, die auf dieses Gerät aus anderen Quellen angewendet werden. Wählen Sie **Weiter** aus.

11. Legen Sie einen Wert für **Paketversion** fest.

    > [!TIP]
    > Sie können Änderungen an vorhandenen Paketen vornehmen und die Versionsnummer ändern, um bereits angewendete Pakete zu aktualisieren.

12. Wählen Sie **unter Sicherheitsdetails für das Bereitstellungspaket auswählen** die Option **Weiter aus.**

    > [!WARNING]
    > Wenn Sie das Bereitstellungspaket verschlüsseln, kann das HoloLens-Gerät nicht bereitgestellt werden.  

13. Wählen **Sie Weiter** aus, um den Ausgabespeicherort anzugeben, an den das Bereitstellungspaket gehen soll, nachdem es erstellt wurde. Standardmäßig verwendet der Windows-Konfigurations-Designer den Projektordner als Ausgabespeicherort.

    Optional können Sie Durchsuchen auswählen, **um** den Standardausgabespeicherort zu ändern.

14. Wählen Sie **Weiter** aus.

15. Wählen Sie **Erstellen aus,** um mit dem Erstellen des Pakets zu beginnen. Die Projektinformationen werden auf der Buildseite angezeigt, und die Statusanzeige gibt den Buildstatus an.

16. Wenn der Build abgeschlossen ist, wählen Sie **Fertig stellen aus.**

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>Anwenden eines Bereitstellungspakets auf HoloLens während des Setups

HoloLens 2 Windows Holographic, Version 2004 oder Build [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) oder höher, können ein USB-Laufwerk verwenden, um ein Bereitstellungspaket anzuwenden. Kopieren Sie einfach die PPKG-Datei in das Stammverzeichnis des USB-Laufwerks. Bereitstellungspakete werden nur angewendet, wenn sie sich im Stammverzeichnis des USB-Laufwerks befindet. Mehrere bereitgestellte Pakete werden sequenziell angewendet.

HoloLens 2 Geräte unter [Windows Holographic Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) oder höher verfügen über neuere Features, um diesen Prozess zu optimieren und zu vereinfachen, sodass er automatisch erfolgt. Lesen Sie die folgenden Abschnitte:

- [Automatisches Starten der Bereitstellung über USB](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [Automatische Bestätigung von Bereitstellungspaketen in OOBE](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Automatische Bereitstellung ohne Benutzeroberfläche](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. Verwenden Sie das USB-Kabel, um das Gerät mit einem PC (oder einem USB-Laufwerk für HoloLens 2 wie oben erwähnt) zu verbinden, und starten Sie dann das Gerät. Fahren Sie nicht über die Seite **First interactable moment (Erster interaktiver Moment)** von OOBE fort.   
    - Auf HoloLens (1. Generation) enthält diese Seite ein blaues Feld. 
    - Auf HoloLens 2 enthält diese Seite das -Blatt.

2. Drücken Sie die Tasten **Leiser** und **Ein/Aus** kurz gleichzeitig, und geben Sie sie anschließend wieder frei. 

3. HoloLens wird im Datei-Explorer auf dem PC als Gerät angezeigt.

4. Verschieben Sie das Bereitstellungspaket (.ppkg) im Datei-Explorer per Drag & Drop zum Gerätespeicher.

5. Drücken Und loslassen Sie die Schaltflächen **"Volume Down"** und **"Power"** gleichzeitig, während Sie sich auf der Seite **First interactable moment (Erster interaktionsfähiger Moment)** von OOBE befinden.

6. Das Gerät fragt Sie, ob Sie dem Paket vertrauen und es anwenden möchten. Bestätigen Sie, dass Sie dem Paket vertrauen.

7. Sie können erkennen, ob das Paket erfolgreich angewendet wurde oder nicht. Wenn das Paket nicht erfolgreich angewendet wurde, können Sie es korrigieren und den Vorgang wiederholen. Wenn das Paket erfolgreich angewendet wurde, fahren Sie mit der Windows-Willkommensseite fort.

> [!NOTE]
> Wenn das Gerät vor August 2016 erworben wurde, müssen Sie sich mit einem Microsoft-Konto beim Gerät anmelden, das neueste Betriebssystemupdate abrufen und dann das Betriebssystem zurücksetzen, um das Bereitstellungspaket anzuwenden.

### <a name="auto-launch-provisioning-from-usb"></a>Automatisches Starten der Bereitstellung über USB

- Automatisierte Prozesse, die eine geringere Benutzerinteraktion ermöglichen, wenn USB-Laufwerke mit Bereitstellungspaketen während der OoBE verwendet werden.

Vor diesem Release mussten Benutzer den Bereitstellungsbildschirm während der OOBE manuell starten, um die Bereitstellung mithilfe einer Schaltflächenkombination zu ermöglichen. Jetzt können Benutzer die Schaltflächenkombination überspringen, indem sie ein Bereitstellungspaket auf einem USB-Speicherlaufwerk verwenden. 

1. Schließen Sie das USB-Laufwerk mit dem Bereitstellungspaket während des ersten interaktionsfähigen OoBE-Moments an.
1. Wenn das Gerät bereit für die Bereitstellung ist, wird automatisch die Eingabeaufforderung mit der Bereitstellungsseite geöffnet. 

Hinweis: Wenn ein USB-Laufwerk angeschlossen bleibt, während das Gerät gestartet wird, werden vorhandene USB-Speichergeräte von OOBE enumeriert, und es wird darauf achten, dass zusätzliche USB-Speichergeräte angeschlossen werden.

Lesen Sie die Informationen [zum Anwenden von Bereitstellungspaketen während der OOBE.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Automatisches Bestätigen von Bereitstellungspaketen in OOBE
- Automatisierter Prozess, der weniger Benutzerinteraktion ermöglicht, wenn die Seite Bereitstellungspaket angezeigt wird, werden automatisch alle aufgelisteten Pakete angewendet.

Wenn der Hauptbildschirm für die Bereitstellung angezeigt wird, wird oobe 10 Sekunden heruntergezählt, bevor automatisch mit dem Anwenden aller Bereitstellungspakete gestartet wird. Benutzer können die Pakete innerhalb dieser 10 Sekunden bestätigen oder abbrechen, nachdem sie die erwarteten Pakete überprüft haben.

### <a name="automatic-provisioning-without-using-ui"></a>Automatische Bereitstellung ohne Benutzeroberfläche
- Kombinierte automatische Prozesse für reduzierte Geräteinteraktionen für die Bereitstellung. 

Durch die Kombination des automatischen Starts der Bereitstellung von USB-Geräten und der automatischen Bestätigung der Bereitstellung von Paketen kann ein Benutzer HoloLens 2-Geräte automatisch bereitstellen, ohne die Benutzeroberfläche des Geräts zu verwenden oder das Gerät sogar zu verwenden. Sie können weiterhin dasselbe USB-Laufwerk und bereitstellungspaket für mehrere Geräte verwenden. Dies ist nützlich, um mehrere Geräte gleichzeitig in demselben Bereich bereitzustellen. 

1. [Erstellen Sie mithilfe des Windows-Konfigurations-Designers](hololens-provisioning.md) ein [Bereitstellungspaket.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Kopieren Sie das Paket auf ein USB-Speicherlaufwerk.
1. [Flashen HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) [19041.1361 oder neueren Build.](https://aka.ms/hololens2previewdownload) 
1. Wenn [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) das Flashen Ihres Geräts abgeschlossen hat, trennen Sie das USB-C-Kabel. 
1. Schließen Sie Ihr USB-Laufwerk an das Gerät an.
1. Wenn das HoloLens 2 in oobe startet, erkennt es automatisch das Bereitstellungspaket auf dem USB-Laufwerk und startet die Bereitstellungsseite.
1. Nach 10 Sekunden wird das Bereitstellungspaket automatisch vom Gerät angewendet. 

Ihr Gerät ist jetzt konfiguriert und zeigt den Bildschirm Bereitstellung erfolgreich an.

## <a name="apply-a-provisioning-package-to-hololens-after-setup"></a>Anwenden eines Bereitstellungspakets auf HoloLens nach dem Setup

> [!NOTE]
> Diese Schritte gelten nur für Windows 10, Version 1809.

Führen Sie auf Ihrem PC die folgenden Schritte aus:
1. Erstellen Sie ein Bereitstellungspaket, wie unter [Erstellen eines Bereitstellungspakets für HoloLens mithilfe des HoloLens-Assistenten](hololens-provisioning.md)beschrieben.
2. Verbinden Sie das HoloLens-Gerät mithilfe eines USB-Kabels mit einem PC. HoloLens wird im Datei-Explorer auf dem PC als Gerät angezeigt.
3. Ziehen Sie das Bereitstellungspaket per Drag &amp; Drop in den Ordner Dokumente auf der HoloLens.

Führen Sie auf Ihrer HoloLens die folgenden Schritte aus:
1. Navigieren Sie zu **Einstellungen** > **Konten** > **Access work or school** (Zugriff auf Geschäfts-, Schul- oder Unikonto). 
2. Wählen Sie **unter Verwandte Einstellungen** die Option **Bereitstellungspaket hinzufügen oder entfernen** aus.
3. Wählen Sie auf der nächsten Seite **Paket hinzufügen** aus, um die Dateiauswahl zu starten, und wählen Sie Ihr Bereitstellungspaket aus. Wenn der Ordner leer ist, stellen Sie sicher, dass Sie **Dieses Gerät** und **dann Dokumente** auswählen.

Nachdem Das Paket angewendet wurde, wird es in der Liste **installierter Pakete angezeigt.** Um die Paketdetails anzuzeigen oder das Paket vom Gerät zu entfernen, wählen Sie das aufgeführte Paket aus.

## <a name="what-you-can-configure"></a>Konfigurierbare Elemente

Bereitstellungspakete nutzen Konfigurationsdienstanbieter (Configuration Service Providers, CSPs). Wenn Sie mit CSPs nicht vertraut sind, lesen Sie den Abschnitt [Einführung in Konfigurationsdienstanbieter (Configuration Service Providers, CSPs) für IT-Experten](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).

Wenn Sie im Windows-Konfigurations-Designer ein Bereitstellungspaket für Windows Holographic erstellen, basieren die Einstellungen unter **Verfügbare Anpassungen** auf [CSPs, die in Windows Holographic unterstützt werden.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) Die folgende Tabelle zeigt die Einstellungen, die Sie möglicherweise für HoloLens konfigurieren sollten.

![Allgemeine Laufzeiteinstellungen für HoloLens](images/icd-settings.png)

| Einstellung | BESCHREIBUNG |
| --- | --- |
| **Zertifikate** | Stellen Sie ein Zertifikat für HoloLens bereit.  |
| **ConnectivityProfiles** | Stellen Sie ein WLAN-Profil für HoloLens bereit.   |
| **EditionUpgrade** | [Führen Sie ein Upgrade auf Windows Holographic for Business durch.](hololens1-upgrade-enterprise.md)  |
| **Richtlinien** | Lassen Sie den Entwicklermodus auf HoloLens zu, oder sperren Sie ihn. [Von Windows Holographic for Business unterstützte Richtlinien](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>App-Installation über Bereitstellungspaket

Apps können über Bereitstellungspakete auf HoloLens 2 Geräten installiert werden. Dies ermöglicht ein leicht wiederverwendebares Paket, mit dem Sie Ihre Apps verteilen können. Lesen Sie die vollständige Anleitung zum [Bereitstellen von Apps über Bereitstellungspakete.](app-deploy-provisioning-package.md)  

> [!NOTE]
> HoloLens (1. Generation) bietet eingeschränkte Unterstützung für die Installation von Apps (**UniversalAppInstall**) mithilfe eines Bereitstellungspakets. HoloLens-Geräte (1. Generation) unterstützen nur die Installation einer App über PPKG nur während oobe und nur mit Benutzerkontext-Installationen.
