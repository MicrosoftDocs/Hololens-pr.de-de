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
ms.date: 03/10/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: da783756c271c589f67efca0c229ad0f777857e2
ms.sourcegitcommit: ccdd628cdbb5b89741f5dbc971143cb2fd2e451b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2020
ms.locfileid: "10990909"
---
# Konfigurieren von HoloLens mithilfe eines Bereitstellungspakets

Die [Windows-Bereitstellung](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) macht es IT-Administratoren einfach, endbenutzergeräte ohne Imaging zu konfigurieren. Der Windows-Konfigurations-Designer ist ein Tool zum Konfigurieren von Bildern und Laufzeiteinstellungen, die dann in Bereitstellungspakete integriert sind.

Einige der HoloLens-Konfigurationen, die Sie in einem Bereitstellungspaket anwenden können, umfassen Folgendes:

- Upgrade auf Windows holographisch für Unternehmen [hier](hololens1-upgrade-enterprise.md)
- Einrichten eines lokalen Kontos
- Einrichten einer WLAN-Verbindung
- Anwenden von Zertifikaten auf das Gerät
- Aktivieren des Entwicklermodus
- Konfigurieren des Kioskmodus (detaillierte Anweisungen zum Konfigurieren des Kioskmodus finden Sie [hier](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk).

## Bereitstellungspaket-HoloLens-Assistent

Der HoloLens-Assistent unterstützt Sie bei der Konfiguration der folgenden Einstellungen in einem Bereitstellungspaket:

- Upgrade auf Enterprise Edition

    > [!NOTE]
    > Dies sollte nur für HoloLens 1st-Gen-Geräte verwendet werden. Einstellungen in einem Bereitstellungspaket werden nur angewendet, wenn das Bereitstellungspaket eine Edition-Upgrade-Lizenz für Windows holographische for Business enthält oder wenn [das Gerät bereits auf Windows holographische for Business aktualisiert](hololens1-upgrade-enterprise.md)wurde.

- Konfigurieren der HoloLens First Experience (OOBE)
- Konfigurieren des Wi-Fi-Netzwerks
- Registrieren des Geräts in Azure Active Directory oder Erstellen eines lokalen Kontos
- Hinzufügen von Zertifikaten
- Aktivieren des Entwicklermodus
- Konfigurieren des Kioskmodus (Detaillierte Anweisungen zum Konfigurieren des Kiosk-Modus finden Sie [hier](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)).

> [!WARNING]
> Sie müssen Windows-Konfigurations-Designer unter Windows10 ausführen, um die Azure Active Directory-Registrierung mit einem beliebigen Assistenten zu konfigurieren.

Bereitstellungspakete können Verwaltungsanweisungen und-Richtlinien, benutzerdefinierte Netzwerkverbindungen und Richtlinien und vieles mehr umfassen.

> [!TIP]
> Verwenden Sie den Desktop-Assistenten, um ein Paket mit allgemeinen Einstellungen zu erstellen, und wechseln Sie dann zum erweiterten Editor, um weitere Einstellungen, Apps, Richtlinien usw. hinzuzufügen.

## Schritte zum Erstellen von Bereitstellungspaketen

1. **Option 1:** [aus dem Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22). Dazu gehören die Funktionen von HoloLens 2.
2. **Option 2:** [aus dem Windows Assessment and Deployment Kit (ADK) für Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit). Wenn Sie den Windows-Konfigurations-Designer aus dem Windows ADK installieren, wählen Sie im Dialogfeld **Wählen Sie die zu installierenden Features** aus den Eintrag **Configuration Designer** aus. Diese Option umfasst nicht die Funktionen von HoloLens 2.

> [!NOTE]
> Wenn Sie wissen, dass Sie einen Offline-PC verwenden werden, der Zugriff auf den Windows-Konfigurations-Designer benötigt, folgen Sie der Offline-App-Installation [hier](https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) für Advanced Recovery Companion, aber machen Sie stattdessen die Windows Confiugration-Desinger-Auswahl. 

### 2. Erstellen des Bereitstellungspakets

Erstellen Sie ein Bereitstellungspaket mit Windows-Konfigurations-Designer.

1. Öffnen Sie Windows-Konfigurations-Designer (standardmäßig unter „%windir%\Programme (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe“).

2. Wählen Sie **HoloLens-Geräte bereit**stellen aus.

   ![ICD-Startoptionen](images/icd-create-options-1703.png)

3. Benennen Sie Ihr Projekt, und wählen Sie **Fertig stellen**aus.

4. Lesen Sie die Anweisungen auf der Seite **Erste Schritte** , und wählen Sie **weiter**aus. Die Seiten für die Desktopbereitstellung führen Sie durch die folgenden Schritte.
  
> [!IMPORTANT]
> Wenn Sie ein Bereitstellungspaket erstellen, können Sie vertrauliche Informationen in die Projektdateien und die Bereitstellungspaketdatei (PPKG-Datei) aufnehmen. Obwohl Sie die PPKG-Datei verschlüsseln können, werden die Projektdateien nicht verschlüsselt. Sie sollten die Projektdateien an einem sicheren Ort speichern und sie löschen, wenn sie nicht mehr benötigt werden.

### Konfigurieren von Einstellungen

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>Navigieren Sie zu der Enterprise-Lizenzdatei, und wählen Sie Sie aus, um die HoloLens Edition zu aktualisieren.</br></br>Sie können auch <strong> Ja </strong> oder Nein umschalten <strong> </strong> , um Teile der ersten Darstellung auszublenden.</br></br>Wenn Sie das Gerät einrichten möchten, ohne eine Verbindung mit einem WLAN-Netzwerk herstellen zu müssen, schalten Sie <strong> WLAN-Setup überspringen auf ein </strong> <strong> </strong> .</br></br>Wählen Sie eine Region und Zeitzone aus, in der das Gerät verwendet wird. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>In diesem Abschnitt können Sie die Details des WLAN-WLAN-Netzwerks eingeben, mit dem das Gerät automatisch eine Verbindung herstellen soll. Wählen Sie dazu ein aus <strong> </strong> , geben Sie die SSID, den Netzwerktyp ( <strong> offen </strong> oder <strong> WPA2-Persönlich </strong> ) und (falls <strong> WPA2-Persönlich </strong> ) das Kennwort für das drahtlose Netzwerk ein.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Sie können das Gerät in Azure Active Directory registrieren oder ein lokales Konto auf dem Gerät erstellen.</br></br>Bevor Sie einen Assistenten in Windows-Konfigurations-Designer verwenden, um die Azure AD-Massenregistrierung zu konfigurieren, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">richten Sie die Azure AD-Verknüpfung in Ihrer Organisation ein</a>. Die Einstellung <strong>Maximale Anzahl von Geräten pro Benutzer</strong> in Ihrem Azure AD-Mandanten bestimmt, wie oft das Massen-Token im Assistenten verwendet werden kann. Um das Gerät in Azure AD zu registrieren, wählen Sie diese Option aus, und geben Sie einen aussagekräftigen Namen für das Massen-Token ein, das Sie vom Assistenten erhalten. Legen Sie ein Ablaufdatum für das Token fest. (Das Maximum liegt bei 30Tagen ab Erhalt des Tokens.) Wählen Sie <strong> Bulk-Token abrufen aus </strong> . <strong>Geben Sie im Fenster&#39;, dass Sie angemeldet </strong> sind, ein Konto ein, das über die Berechtigung zum teilnehmen an einem Gerät mit Azure AD und dann über das Kennwort verfügt. Wählen Sie <strong> annehmen aus </strong> , um dem Windows-Konfigurations-Designer die erforderlichen Berechtigungen zuzuweisen. </br></br>Wenn Sie ein lokales Konto erstellen möchten, wählen Sie diese Option aus, und geben Sie einen Benutzernamen und ein Kennwort ein. </br></br><strong>Wichtig:</strong> <br />(Nur für Windows 10, Version 1607) Wenn Sie im Bereitstellungspaket ein lokales Konto erstellen, müssen Sie das Kennwort <strong> Alle 42 Tage mithilfe der Einstellungs- </strong> App ändern. Wenn das Kennwort innerhalb dieses Zeitraums nicht geändert wird, wird das Konto möglicherweise gesperrt, und eine Anmeldung ist nicht möglich.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Um dem Gerät ein Zertifikat bereitzustellen, klicken Sie auf <strong>Add a certificate</strong>. Geben Sie einen Namen für das Zertifikat ein, navigieren Sie zum Zertifikat, das verwendet werden soll, und wählen Sie es aus.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br><strong>Aktivieren Sie "Ja" </strong> oder " <strong> Nein </strong> ", um den Entwicklermodus auf der HoloLens zu aktivieren. <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Weitere Informationen zum Entwicklermodus</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finish"/></br></br>Setzen Sie kein Kennwort, um Ihr Bereitstellungspaket zu schützen. Wenn das Bereitstellungspaket durch ein Kennwort geschützt ist, schlägt die Bereitstellung des HoloLens-Geräts fehl.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Wenn Sie fertig sind, wählen Sie **Erstellen**aus. Es dauert nur wenige Sekunden. Wenn das Paket erstellt wurde, wird der Speicherort des Pakets als Hyperlink am unteren Rand der Seite angezeigt.

### 3. Erstellen eines Bereitstellungspakets für HoloLens mithilfe der erweiterten Bereitstellung

> [!NOTE]
> Ein Bereitstellungspaket, das Sie in der **erweiterten Bereitstellung** erstellen, muss keine Editionsupgrade-Lizenz für Windows holographische for Business enthalten, damit es erfolgreich auf eine HoloLens (1st Gen) angewendet werden kann. [Weitere Informationen finden Sie unter Windows holographisch for Business für HoloLens (1st Gen)](hololens1-upgrade-enterprise.md).

1. Wählen Sie auf der Startseite des Windows-Konfigurations-Designers **Erweiterte Bereitstellung**.
2. Geben Sie im Fenster **Projektdetails eingeben** den Namen und den Speicherort für Ihr Projekt an. Optional können Sie eine kurze Beschreibung zu Ihrem Projekt eingeben.

3. Wählen Sie **Weiter** aus.

4. Wählen Sie im Fenster **Wählen Sie die Einstellungen aus, die Sie anzeigen und konfigurieren möchten** , **Windows 10 holographisch**aus, und wählen Sie dann **weiter**aus.

5. Wählen Sie **Fertig stellen**aus.

6. Erweitern Sie die **Laufzeiteinstellungen** , und passen Sie das Paket mithilfe der Einstellungen an, die [weiter unten in diesem Artikel beschrieben](#what-you-can-configure)werden.

    > [!IMPORTANT]
    > (Nur für Windows 10, Version 1607) Wenn Sie im Bereitstellungspaket ein lokales Konto erstellen, müssen Sie das Kennwort alle 42 Tage mithilfe der **Einstellungs** -App ändern. Wenn das Kennwort innerhalb dieses Zeitraums nicht geändert wird, wird das Konto möglicherweise gesperrt, und eine Anmeldung ist nicht möglich. Wenn das Benutzerkonto gesperrt wird, müssen Sie [eine vollständige Gerätewiederherstellung](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery) ausführen.

7. Wählen Sie **Datei**  >  **Speichern**aus.

8. Lesen Sie die Warnung, dass Projektdateien vertrauliche Informationen enthalten können, und wählen Sie **OK**aus.

    > [!IMPORTANT]
    > Wenn Sie ein Bereitstellungspaket erstellen, können Sie vertrauliche Informationen in die Projektdateien und die Bereitstellungspaketdatei (PPKG-Datei) aufnehmen. Obwohl Sie die PPKG-Datei verschlüsseln können, werden die Projektdateien nicht verschlüsselt. Sie sollten die Projektdateien an einem sicheren Ort speichern und löschen, wenn sie nicht mehr benötigt werden.
    
9. Wählen **Export**Sie  >  **Bereitstellungspaket**exportieren aus.

10. Ändern Sie den **Besitzer** in den **IT-Administrator**. Dadurch wird die Rangfolge dieses Bereitstellungspakets höher als Bereitstellungspakete, die auf dieses Gerät aus anderen Quellen angewendet werden. Wählen Sie **Weiter** aus.

11. Legen Sie einen Wert für **Paketversion**fest.

    > [!TIP]
    > Sie können Änderungen an vorhandenen Paketen vornehmen und die Versionsnummer ändern, um bereits angewendete Pakete zu aktualisieren.

12. Wählen Sie im **Paket Sicherheitsdetails für die Bereitstellung auswählen**die Option **weiter**aus.

    > [!WARNING]
    > Wenn Sie das Bereitstellungspaket verschlüsseln, ist die Bereitstellung des HoloLens-Geräts nicht möglich.  

13. Wählen Sie **weiter** aus, um den Ausgabespeicherort anzugeben, an dem das Bereitstellungspaket nach dem Aufbau ablaufen soll. Standardmäßig verwendet der Windows-Konfigurations-Designer den Projektordner als Ausgabespeicherort.

    Optional können Sie **Durchsuchen** auswählen, um den Standardausgabe Speicherort zu ändern.

14. Wählen Sie **Weiter** aus.

15. Wählen Sie **Erstellen** aus, um mit dem Erstellen des Pakets zu beginnen. Die Projektinformationen werden auf der Buildseite angezeigt, und die Statusanzeige gibt den Buildstatus an.

16. Wenn der Build abgeschlossen ist, wählen Sie **Fertig stellen**aus.

<span id="apply" />

## Anwenden eines Bereitstellungspakets auf HoloLens während des Setups

HoloLens 2-Geräte auf Build [19041,1103](hololens-release-notes.md#windows-holographic-version-2004) oder höher verwenden möglicherweise ein USB-Laufwerk, um ein Bereitstellungspaket anzuwenden. Kopieren Sie einfach die ppkg-Datei in das Stammverzeichnis des USB-Laufwerks. Bereitstellungspakete werden nur angewendet, wenn Sie sich im Stammverzeichnis des USB-Laufwerks befinden. Das vorhanden sein mehrerer Bereitstellungspakete wird sequenziell angewendet.

1. Verwenden Sie das USB-Kabel, um das Gerät mit einem PC (oder einem USB-Laufwerk für HoloLens 2 wie oben beschrieben) zu verbinden, und starten Sie dann das Gerät. Gehen Sie nicht über die **erste interagierende Moment** Seite von OOBE hinaus.   
    - Auf HoloLens (1st Gen) enthält diese Seite ein blaues Feld. 
    - Auf HoloLens 2 enthält diese Seite den Kolibri.

2. Drücken Sie die Tasten **Leiser** und **Ein/Aus** kurz gleichzeitig, und geben Sie sie anschließend wieder frei. 

3. HoloLens wird im Datei-Explorer auf dem PC als Gerät angezeigt.

4. Verschieben Sie das Bereitstellungspaket (.ppkg) im Datei-Explorer per Drag & Drop zum Gerätespeicher.

5. Drücken Sie kurz die **Lautstärke** Taste und die **Power** -Taste gleichzeitig wieder, während Sie sich auf der **ersten interagierenden Moment** Seite von OOBE befinden.

6. Das Gerät fragt Sie, ob Sie dem Paket Vertrauen und es anwenden möchten. Bestätigen Sie, dass Sie dem Paket vertrauen.

7. Sie können erkennen, ob das Paket erfolgreich angewendet wurde oder nicht. Wenn das Paket nicht erfolgreich angewendet wurde, können Sie es korrigieren und den Vorgang wiederholen. Wenn das Paket erfolgreich angewendet wurde, fahren Sie mit der Windows-Willkommensseite fort.

> [!NOTE]
> Wenn das Gerät vor August 2016 gekauft wurde, müssen Sie sich mit einem Microsoft-Konto bei dem Gerät anmelden, das neueste Betriebssystemupdate abrufen und dann das Betriebssystem zurücksetzen, um das Bereitstellungspaket anzuwenden.

## Anwenden eines Bereitstellungspakets auf HoloLens nach dem Setup

> [!NOTE]
> Diese Schritte gelten nur für Windows 10, Version 1809.

Führen Sie auf Ihrem PC die folgenden Schritte aus:
1. Erstellen Sie ein Bereitstellungspaket, wie unter [Erstellen eines Bereitstellungspakets für HoloLens mithilfe des HoloLens-Assistenten](hololens-provisioning.md)beschrieben.
2. Schließen Sie das HoloLens-Gerät mit einem USB-Kabel an einen PC an. HoloLens wird im Datei-Explorer auf dem PC als Gerät angezeigt.
3. Ziehen Sie das Bereitstellungspaket, und legen Sie es in den Ordner "Dokumente" auf der HoloLens.

Führen Sie auf Ihrem HoloLens die folgenden Schritte aus:
1. Wechseln Sie zu **Einstellungen**  >  **Konten**  >  **Zugriff auf Arbeit oder Schule**. 
2. Wählen Sie unter **Verwandte Einstellungen** **die Option hinzufügen oder Entfernen eines Bereitstellungspakets**aus.
3. Wählen Sie auf der nächsten Seite **Paket hinzufügen** aus, um die Dateiauswahl zu starten, und wählen Sie Ihr Bereitstellungspaket aus. Wenn der Ordner leer ist, stellen Sie sicher, dass Sie **dieses Gerät** auswählen und **Dokumente**auswählen.

Nachdem das Paket angewendet wurde, wird es in der Liste der **installierten Pakete**angezeigt. Wenn Sie die Paketdetails anzeigen oder das Paket vom Gerät entfernen möchten, wählen Sie das aufgelistete Paket aus.

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

Apps können über Bereitstellungspakete auf HoloLens 2-Geräten installiert werden. Dies ermöglicht ein einfach wiederverwendbares Paket, mit dem Sie Ihre apps verteilen können. Lesen Sie die vollständigen Anweisungen zum [Bereitstellen von apps über Bereitstellungspakete](app-deploy-provisioning-package.md).  

> [!NOTE]
> HoloLens (1st Generation) unterstützt die Installation von apps (**UniversalAppInstall**) nicht mithilfe eines Bereitstellungspakets.
