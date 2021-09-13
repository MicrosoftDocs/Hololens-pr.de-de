---
title: Bereitstellungshandbuch – Unternehmensverknannte HoloLens 2 mit Dynamics 365 Guides – Konfigurieren
description: Erfahren Sie, wie Sie Konfigurationen einrichten, um HoloLens 2 Geräte über ein verbundenes Unternehmensnetzwerk mit Dynamics 365 Guides bereitzustellen.
keywords: HoloLens, Verwaltung, unternehmensverbunden, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Geräteverwaltung
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9457acd2f53d0d3127d6c68d620b660f6e09866d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032725"
---
# <a name="configure---corporate-connected-guide"></a>Konfigurieren – Handbuch zu verbundenen Unternehmensdaten

## <a name="azure-users-and-groups"></a>Azure-Benutzer und -Gruppen

Azure und Intune von dieser Erweiterung verwenden Benutzer und Gruppen, um Konfigurationen und Lizenzen zuzuweisen. Um diesen Bereitstellungsablauf zu überprüfen und zu überprüfen, ob Sie einen Leitfaden erstellen und betreiben können, benötigen Sie&#39;ein Benutzerkonto.

Wir können eine einzelne Benutzergruppe speziell zum Zuweisen von Lizenzen erstellen.

Wenn Sie&#39;noch keinen Zugriff auf zwei Azure AD Konten in einer Benutzergruppe haben, die Sie verwenden können. Hier sind die Schnellstartanleitungen für Folgendes:

- [Erstellen eines Benutzers](/mem/intune/fundamentals/quickstart-create-user)
- [Erstellen einer Gruppe](/mem/intune/fundamentals/quickstart-create-group)
- [Hinzufügen von Benutzern zu einer Gruppe:](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) Hinzufügen von erstellten Benutzern zum Erstellen einer Gruppe
- [Konfigurieren Azure AD, um einer Benutzergruppe das Beitreten zu Geräten zu ermöglichen:](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) Stellen Sie sicher, dass eine neue Benutzergruppe über die Berechtigung zum Registrieren von Geräten für Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Automatische Registrierung bei HoloLens 2

Um eine reibungslose und nahtlose Benutzeroberfläche zu erhalten, ist das Einrichten von Azure Active Directory Join (AADJ) und der automatischen Registrierung bei Intune für HoloLens 2 Geräte die beste Vorgehensweise. Dadurch können Benutzer ihre Anmeldeinformationen für die Organisation während der OOBE eingeben und sich automatisch bei Azure AD registrieren und das Gerät bei MDM registrieren.

Mit [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)können wir Dienste auswählen und durch einige Seiten navigieren, bis wir get a Premium trial (Testversion abrufen) auswählen können. Möglicherweise stellen Sie fest, dass Azure Active Directory Premium 1 und 2 vorhanden sind. Für die automatische Registrierung ist P1 ausreichend. Wir können Intune auswählen, den Benutzerbereich für die automatische Registrierung auswählen und die Gruppe auswählen, die zuvor erstellt wurde.

Ausführliche Informationen und Schritte finden Sie im Leitfaden zum Aktivieren der [automatischen Registrierung für Intune.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>Wi-Fi Konnektivität für Unternehmen

Unternehmensverbindungen Wi-Fi erfordern in der Regel zertifikatbasierte Authentifizierung für Kunden, die HoloLens 2 verwenden. Sie müssen solche Zertifikate mithilfe einer in Ihre MDM-Lösung integrierten zertifikatbasierten Simple Certificate Enrollment-Protokoll (SCEP) oder PKCS-Zertifikatinfrastruktur (Public Key Cryptography Standard) bereitstellen. Die Verwendung von Intune zum Bereitstellen von Wi-Fi Profilen, Zertifikaten und Proxyeinstellungen sorgt für eine nahtlose Benutzererfahrung.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Bereitstellen von Zertifikaten und Wi-Fi Profilen

Führen Sie die folgenden Schritte aus, um Zertifikate und Profile über Microsoft Endpoint Manager bereitzustellen:

1. Erstellen Sie ein Profil für jedes Stamm- und Zwischenzertifikat (siehe [Erstellen von vertrauenswürdigen Zertifikatprofilen).](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Jedes dieser Profile muss über eine Beschreibung verfügen, die ein Ablaufdatum im Format DD/MM/YYYY enthält.

    > [!CAUTION]
    > **Zertifikatprofile ohne Ablaufdatum werden nicht bereitgestellt.**

2. Erstellen Sie ein Profil für jedes SCEP- oder PKCS-Zertifikat (siehe [Erstellen eines SCEP-Zertifikatprofils oder Erstellen eines PKCS-Zertifikatprofils](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)). Jedes dieser Profile muss eine Beschreibung aufweisen, die ein Ablaufdatum im Format TT/MM/YYYY enthält.

    > [!CAUTION]
    > **Zertifikatprofile ohne Ablaufdatum werden nicht bereitgestellt.**

    > [!Note]
    > Da die HoloLens 2 für viele als freigegebenes Gerät betrachtet wird, d. h. mehrere Benutzer pro Gerät, wird empfohlen, Gerätezertifikate anstelle von Benutzerzertifikaten für Wi-Fi Authentifizierung bereitzustellen, wenn dies möglich ist.

3. Erstellen Sie ein Profil für Ihr Unternehmens-Wi-Fi-Netzwerk (weitere Informationen finden Sie unter [WLAN-Einstellungen für Windows 10 und höhere Geräte).](/intune/wi-fi-settings-windows) In Ihrem Wi-Fi-Profil können Sie auswählen, ob Sie die Proxyeinstellungen in Ihrer Organisation verwenden möchten.

    Folgende Optionen sind verfügbar:
    - **Keine**: Es sind keine Proxyeinstellungen konfiguriert.
    - **Manuell konfigurieren:** Geben Sie die **IP-Adresse des Proxyservers** und die zugehörige **Portnummer** ein.
    - **Automatisch konfigurieren:** Geben Sie die URL ein, die auf ein PAC-Skript (Proxy Auto-Configuration, automatische Proxykonfiguration) zeigt. Geben Sie z.B. *http://proxy.contoso.com/proxy.pac* ein.

    Weitere Informationen zu PAC-Dateien finden Sie unter [Proxy Auto-Configuration (PAC) file (Datei für die automatische Proxykonfiguration)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (öffnet eine Drittanbieterwebsite).
 
    > [!Note]
    > Es empfiehlt sich, WLAN-Profile möglichst Gerätegruppen statt Benutzergruppen zuzuweisen.
     
    > [!Tip]
    > Sie können auch ein funktionierendes WLAN-Profil von einem Windows 10-PC in Ihrem Unternehmensnetzwerk exportieren. Mit diesem Export wird eine XML-Datei mit allen aktuellen Einstellungen erstellt. Importieren Sie dann diese Datei in Intune, und verwenden Sie sie als WLAN-Profil für Ihre HoloLens 2-Geräte. Weitere Informationen finden Sie unter [Exportieren und Importieren von WLAN-Einstellungen für Windows-Geräte](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Weisen Sie](/mem/intune/configuration/device-profile-assign) die Geräteprofile der HoloLens Gerätegruppe zu.

2.  [Überwachen Sie](/mem/intune/configuration/device-profile-monitor) die Geräteprofile in Intune.

Wenn Probleme mit Wi-Fi Profilen auftreten, finden Sie unter [Problembehandlung Wi-Fi Gerätekonfigurationsprofile in Intune](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)weitere Informationen.

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Problembehandlung bei externem Internetzugriff bei Unternehmensverbindung
Wenn Dienste versuchen, keinen festgelegten Proxy zu durchlaufen, versuchen sie möglicherweise, eine Verbindung über die Firewall herzustellen. Sie können Ihren Firewallregeln eine Liste mit Endpunkten hinzufügen, um diese Probleme zu beheben.

Wenn Sie an Firewallports blockiert sind, aktivieren Sie einige allgemeine [Endpunkte](/hololens/hololens-offline) für HoloLens.

Sie können auch die spezifischen Ports für Handbücher aktivieren: UrLs, auf die über das [Internet zugegriffen werden kann, die für die Konnektivität mit Microsoft Dynamics CRM Online erforderlich sind.](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)

## <a name="app-deployment"></a>App-Bereitstellung

Die Bereitstellung einer branchenweiten App über MDM ist eine Methode, die einfach skalierbar ist und bei der Registrierung in einer erstellten Gruppe automatisch auf Ihren Geräten bereitgestellt werden kann.

Wenn Sie Ihre Apps noch entwickeln oder noch keine haben, können Sie eine Beispiel-App des MRTK-Beispielhubs verwenden. Diese Beispiel-App ist einsatzbereit und erfordert weder Unity noch Visual Studio. [Laden Sie die MRTK-Beispiel-App herunter.](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)

Wenn Sie ihre eigene App verwenden möchten oder an der App-Entwicklung für Mixed Reality interessiert sind, können Sie sich unsere [Mixed Reality Entwicklerdokumentation](/windows/mixed-reality/design/design)ansehen.

> [!NOTE]
> Die Systemanforderungen für HoloLens-Geräte basieren auf der Architektur des App-Builds. HoloLens 2 Geräte verwenden die ARM-Architektur. Stellen Sie beim Erstellen Ihrer Apps in Visual Studio sicher, dass Sie die richtige Architektur für das Gerät ausgewählt haben und alle erforderlichen Abhängigkeiten einschließen.

> [!IMPORTANT]
> Beim Bereitstellen von Branchen-Apps ist es wichtig, das Zertifikat auch in Intune hochzuladen und es derselben Gruppe zuzuweisen, die die App verwenden soll, oder es wird nicht ordnungsgemäß installiert.

### <a name="upload-and-assign-the-app"></a>Hochladen und Zuweisen der App

1. Navigieren Sie zum [MEM Admin Center.](https://endpoint.microsoft.com/#home)

2. Wählen Sie **Apps**  ->  **Alle Apps** und dann die Schaltfläche **+ Hinzufügen** aus.

3. Wählen Sie unter Andere die Option **Branchenspezifische App** aus. Klicken Sie auf **auswählen.**

4. Wählen Sie die App-Paketdatei aus, dies ist Ihre APPXBUNDLE-Datei, oder in unserem Fall ist die App _MRTK Examples Hub \_ 2.4.2.0 \_ arm \_ Master.appxbundle_.

5. Sie werden über fehlende Abhängigkeiten benachrichtigt. In diesem Fall müssen wir _Microsoft.VCLibs.ARM.14.00.appx_ hochladen. Suchen Sie unter **Datei auswählen** danach.

6. Wählen Sie „OK“ aus.

7. Auf dem nächsten Bildschirm werden die erforderlichen Felder automatisch ausgefüllt. Wählen Sie **Weiter** aus.

8. Fügen Sie unter Erforderlich die zuvor erstellte Gruppe hinzu, damit diese App für die Gruppe erforderlich ist. Dies führt dazu, dass die App automatisch auf registrierte Geräte in der Gruppe heruntergeladen wird. Klicken Sie auf **Weiter**.

9. Wählen Sie **Erstellen** aus.

Weitere Informationen: [Zuweisen von Apps zu Gruppen in Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Setuphandbücher: Anwendungslizenzen, Dataverse und Erstellung

Um Dynamics 365 Guides verwenden zu können, müssen Sie einige Vorbereitungen durchführen. Es gibt drei Bereiche, in denen wir uns vorbereiten müssen: Benutzer, Dataverse und die Handbücher selbst.

### <a name="users-and-application-licenses"></a>Benutzer und Anwendungslizenzen

Damit jemand Handbücher verwenden kann, muss er ein Azure AD Konto verwenden, das wir zuvor in diesem Leitfaden eingerichtet haben.

Außerdem müssen Sie dem erstellten Benutzer Dynamics 365 Guides Lizenz zuweisen. Dies geschieht über die [Microsoft 365 Admin Center](https://admin.microsoft.com/AdminPortal/Home). Weisen Sie die Lizenz auch Ihrem primären Azure-Konto zu.

Befolgen Sie [diese kurze Anleitung](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) mit Bildern, um schrittweise Anweisungen zum Anwenden von Anwendungslizenzen zu erhalten.

### <a name="set-up-the-dataverse"></a>Einrichten der Dataverse

Um [eine Produktionsumgebung einzurichten,](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) müssen Sie zwei Voraussetzungen erfüllen. Sie benötigen die [**Systemadministratorrolle**](/power-platform/admin/database-security) **und** eine [**Power Apps Lizenz**](/power-platform/admin/signup-question-and-answer) (oder eine Dynamics 365 Guides [**Lizenz,**](/dynamics365/mixed-reality/guides/setup-step-one) die eine Power Apps Lizenz enthält). Wenn Sie diese Anleitung befolgen, haben Sie die Azure AD erstellt, dann erfüllen Sie die Rollenanforderungen für Systemadministrator. Im vorherigen Schritt haben wir auch eine Lizenz für Handbücher zugewiesen.

In diesem Leitfaden zum [Erstellen einer Microsoft Dataverse-Umgebung:](/dynamics365/mixed-reality/guides/setup-step-two)

1. Verwenden Sie zunächst die [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/environments) und erstellen Sie eine neue Umgebung.
2. Wenn Sie die **neue Umgebung** erstellen, wählen Sie für den **Typ,** den Sie&#39;, die Option **Produktion** aus.
3. Es ist wichtig, dass Sie Datenbank **für diese Umgebung erstellen umschalten?**  -Option auf **Ja.**
4. Legen  **Sie**  im Dialogfeld Datenbank hinzufügen die Option  **Dynamics 365-Apps aktivieren**  auf  **Ja fest.**

Sie möchten die maximale Dateigröße von Elementen in Ihrem Dataverse erhöhen. Wenn Sie die maximale Dateigröße erhöhen, können Sie größere 3D-Modelle oder Videodateien hochladen, die Sie später in Ihren Handbüchern verwenden werden. Befolgen Sie eine kurze [Anleitung, um die maximale Uploaddateigröße zu ändern.](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Schließlich müssen Sie die [Projektmappe installieren und konfigurieren.](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution) Wählen Sie im [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/environments)die Option **Ressourcen** \& gt;  **Dynamics 365-Apps,** wählen Sie **Dynamics 365 Guides** in der Liste und dann **Installieren** aus.  

Sie müssen [eine Sicherheitsrolle "Handbücher" hinzufügen,](/dynamics365/mixed-reality/guides/assign-role) bevor Sie die Apps verwenden können.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Erstellen eines Testleitfadens auf Ihrem PC per Erstellung

Beim Erstellen von Handbüchern starten Sie immer auf Ihrem PC. Erstellen der Schritte, Auswählen von Modellen und Verankern des Leitfadens. Danach werden Inhalte für Ihren Leitfaden später im Erstellungsmodus auf Ihrem HoloLens Gerät platziert. Für die Zwecke dieses Leitfadens wird empfohlen, eine kurze Testanleitung mit minimalen Schritten und Modellen zu erstellen.

Wenn Sie sich mit der Erstellung von Handbüchern informieren möchten, beginnen Sie hier mit der Übersicht über die [Erstellung.](/dynamics365/mixed-reality/guides/authoring-overview) Alternativ können Sie sich dieses kurze Video ansehen, um sich einen schnellen Überblick zu verschaffen.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Optional: Kioskmodus

Der Kioskmodus ist ein Modus, in dem ein IT-Administrator die Benutzeroberfläche des Startmenüs so konfiguriert, dass nur eine einzelne App oder eine Auswahl von Apps angezeigt wird. Ein Kiosk kann auch auf bestimmte Benutzer, Gruppen oder auf Geräteebene angewendet werden. und in einigen Fällen bestimmte Benutzer vom Kiosk ausschließen, sodass sie weiterhin Zugriff auf das reguläre Startmenü haben.

Der Kioskmodus verfügt über viele verschiedene Variablen, sowohl im Bereich als auch in den Konfigurationen, die festgelegt werden können, sowie Methoden zum Bereitstellen des Kiosks im HoloLens. Aufgrund all dieser Variablen bleibt der Kioskmodus für diese Anleitung _optional_ und wird nicht erneut überprüft. Wenn Sie der Meinung sind, dass Sie ein Unternehmen benötigen, um verfügbare Apps auf Benutzer zu beschränken, oder weitere Informationen erhalten möchten, können Sie sich darüber informieren, wie [Sie HoloLens als Kiosk einrichten.](/hololens/hololens-kiosk)

## <a name="optional-wdac"></a>Optional: WDAC

Mit WDAC kann ein IT-Administrator seine Geräte so konfigurieren, dass der Start von Apps auf Geräten blockiert wird. Dies unterscheidet sich von Methoden der Geräteeinschränkung, z. B. dem Kioskmodus, in dem dem Benutzer eine Benutzeroberfläche angezeigt wird, die die Apps auf dem Gerät ausblendet, aber trotzdem gestartet werden kann. Während WDAC implementiert ist, sind die Apps weiterhin in der Liste Alle Apps sichtbar, aber WDAC verhindert, dass diese Apps und Prozesse vom Gerätebenutzer gestartet werden können.

Weitere Informationen zum Zulassen oder Blockieren von [Apps auf HoloLens 2 Geräten mithilfe von WDAC und Windows PowerShell mit Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).

[Windows Defender Application Control – WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Nächster Schritt 
> [!div class="nextstepaction"]
> [Unternehmensverbundene Bereitstellung – Bereitstellen](hololens2-corp-connected-deploy.md)