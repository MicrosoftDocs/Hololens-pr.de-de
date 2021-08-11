---
title: Bereitstellungshandbuch – Unternehmens verbundene HoloLens 2 mit Dynamics 365 Guides – Konfigurieren
description: Erfahren Sie, wie Sie Konfigurationen zum Bereitstellen HoloLens 2 Geräten über ein verbundenes Unternehmensnetzwerk mit Dynamics 365 Guides.
keywords: HoloLens, Verwaltung, unternehmens verbunden, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Geräteverwaltung
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
ms.openlocfilehash: 2b855f5891dfa4ca695e4ae3b2a2e82510c5b626f08b434643169be239b48291
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660193"
---
# <a name="configure---corporate-connected-guide"></a>Konfigurieren – Leitfaden für verbundene Unternehmen

## <a name="azure-users-and-groups"></a>Azure-Benutzer und -Gruppen

Azure und Intune mit dieser Erweiterung verwenden Benutzer und Gruppen, um Konfigurationen und Lizenzen zuzuweisen. Um diesen Bereitstellungsablauf zu überprüfen und zu überprüfen, ob Sie einen Leitfaden erstellen und betreiben können, benötigen Sie&#39;Benutzerkonto.

Wir können eine einzelne Benutzergruppe speziell zum Zuweisen von Lizenzen verwenden.

Wenn Sie nicht&#39;haben, haben Sie noch keinen Zugriff auf zwei Azure AD-Konten in einer Benutzergruppe, die Sie verwenden können. Hier finden Sie die Schnellstartanleitungen für:

- [Erstellen eines Benutzers](/mem/intune/fundamentals/quickstart-create-user)
- [Erstellen einer Gruppe](/mem/intune/fundamentals/quickstart-create-group)
- [Hinzufügen von Benutzern zu einer Gruppe:](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) Hinzufügen von erstellten Benutzern zum Erstellen einer Gruppe
- [Konfigurieren Azure AD, um](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) einer Benutzergruppe das Beitreten zu Geräten zu ermöglichen: Stellen Sie sicher, dass eine neue Benutzergruppe über die Berechtigung zum Registrieren von Geräten für Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Automatische Registrierung auf HoloLens 2

Um eine reibungslose und nahtlose Umgebung zu gewährleisten, ist das Einrichten von Azure Active Directory Join (AADJ) und der automatischen Registrierung bei Intune für HoloLens 2-Geräte die erste Möglichkeit. Dadurch können Benutzer ihre Anmeldeinformationen für die Organisation während der OOBE eingeben und sich automatisch bei Azure AD registrieren und das Gerät bei MDM registrieren.

Mithilfe [von Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)können wir Dienste auswählen und zu einigen Seiten navigieren, bis wir auf Get a Premium trial (Testversion Premium können. Möglicherweise werden Sie feststellen, dass Azure Active Directory Premium 1 und 2 vorhanden sind. Für die automatische Registrierung ist P1 ausreichend. Wir können Intune auswählen und den Benutzerbereich für die automatische Registrierung auswählen und die Gruppe auswählen, die zuvor erstellt wurde.

Ausführliche Informationen und Schritte finden Sie im Leitfaden zum Aktivieren der [automatischen Registrierung für Intune.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>UnternehmensWi-Fi Konnektivität

UnternehmensWi-Fi verbindungen erfordern in der Regel eine zertifikatbasierte Authentifizierung für Kunden, die HoloLens 2. Sie müssen solche Zertifikate bereitstellen, indem Sie eine Simple Certificate Enrollment-Protokoll-Zertifikatinfrastruktur (SCEP) oder eine PUBLIC KEY Cryptography Standard-Zertifikatinfrastruktur (PUBLIC Key Cryptography Standard, PKCS) verwenden, die in Ihre MDM-Lösung integriert ist. Die Verwendung von Intune Wi-Fi Bereitstellung von Profilen, Zertifikaten und Proxyeinstellungen sorgt für eine nahtlose Benutzererfahrung.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Bereitstellen von Zertifikaten und Wi-Fi Profilen

Führen Sie zum Bereitstellen von Zertifikaten und Profilen Microsoft Endpoint Manager folgenden Schritte aus:

1. Erstellen Sie ein Profil für jedes Stamm- und Zwischenzertifikat (siehe [Erstellen vertrauenswürdiger Zertifikatprofile).](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Jedes dieser Profile muss eine Beschreibung aufweisen, die ein Ablaufdatum im Format TT/MM/YYYY enthält.

    > [!CAUTION]
    > **Zertifikatprofile ohne Ablaufdatum werden nicht bereitgestellt.**

2. Erstellen Sie ein Profil für jedes SCEP- oder PKCS-Zertifikat (siehe [Erstellen eines SCEP-Zertifikatprofils oder Erstellen eines PKCS-Zertifikatprofils](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)). Jedes dieser Profile muss eine Beschreibung aufweisen, die ein Ablaufdatum im Format TT/MM/YYYY enthält.

    > [!CAUTION]
    > **Zertifikatprofile ohne Ablaufdatum werden nicht bereitgestellt.**

    > [!Note]
    > Da die HoloLens 2 für viele als gemeinsam genutztes Gerät betrachtet wird, d. h. mehrere Benutzer pro Gerät, wird empfohlen, gerätezertifikate anstelle von Benutzerzertifikaten für die Wi-Fi-Authentifizierung bereitzustellen.

3. Erstellen Sie ein Profil für Ihr Unternehmensnetzwerk Wi-Fi (siehe [WLAN-Einstellungen für](/intune/wi-fi-settings-windows)Windows 10 und höher). In Ihrem Wi-Fi können Sie auswählen, ob Sie die Proxyeinstellungen in Ihrer Organisation verwenden möchten.

    Folgende Optionen sind verfügbar:
    - **Keine**: Es sind keine Proxyeinstellungen konfiguriert.
    - **Manuell konfigurieren:** Geben Sie die **IP-Adresse des Proxyservers** und die zugehörige **Portnummer** ein.
    - **Automatisch konfigurieren:** Geben Sie die URL ein, die auf ein PAC-Skript (Proxy Auto-Configuration, automatische Proxykonfiguration) zeigt. Geben Sie z.B. *http://proxy.contoso.com/proxy.pac* ein.

    Weitere Informationen zu PAC-Dateien finden Sie unter [Proxy Auto-Configuration (PAC) file (Datei für die automatische Proxykonfiguration)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (öffnet eine Drittanbieterwebsite).
 
    > [!Note]
    > Es empfiehlt sich, WLAN-Profile möglichst Gerätegruppen statt Benutzergruppen zuzuweisen.
     
    > [!Tip]
    > Sie können auch ein funktionierendes WLAN-Profil von einem Windows 10-PC in Ihrem Unternehmensnetzwerk exportieren. Mit diesem Export wird eine XML-Datei mit allen aktuellen Einstellungen erstellt. Importieren Sie dann diese Datei in Intune, und verwenden Sie sie als WLAN-Profil für Ihre HoloLens 2-Geräte. Weitere Informationen finden Sie unter [Exportieren und Importieren von WLAN-Einstellungen für Windows-Geräte](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Weisen](/mem/intune/configuration/device-profile-assign) Sie die Geräteprofile der HoloLens zu.

2.  [Überwachen](/mem/intune/configuration/device-profile-monitor) Sie die Geräteprofile in Intune.

Wenn Probleme mit Wi-Fi-Profilen Wi-Fi Problembehandlung [bei Gerätekonfigurationsprofilen in Intune.](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Problembehandlung beim externen Internetzugriff bei verbundener Corp.
Wenn Dienste versuchen, keinen festgelegten Proxy zu passieren, versuchen sie möglicherweise, eine Verbindung über die Firewall herzustellen. Sie können Ihren Firewallregeln eine Liste mit Endpunktspezifischen Informationen hinzufügen, um diese Probleme zu beheben.

Wenn Sie an Firewallports blockiert sind, aktivieren Sie einige allgemeine [Endpunkte](/hololens/hololens-offline) für HoloLens.

Sie können auch die leitfädenspezifischen Ports aktivieren: [URLs,](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)die über das Internet zugänglich sind, die für die Konnektivität mit Microsoft Dynamics CRM Online.

## <a name="app-deployment"></a>App-Bereitstellung

Die Bereitstellung einer BRANCHEN-App über MDM ist eine methode, die leicht skalierbar ist und bei der Registrierung in einer erstellten Gruppe automatisch auf Ihren Geräten bereitgestellt werden kann.

Wenn Sie Ihre Apps noch entwickeln oder noch keines haben, können Sie eine Beispiel-App des MRTK-Beispielhubs verwenden. Diese Beispiel-App ist einsatzbereit und erfordert weder Unity noch Visual Studio. [Laden Sie die MRTK-Beispiel-Beispiel-App herunter.](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)

Wenn Sie lieber Ihre eigene App verwenden möchten oder an der App-Entwicklung für Mixed Reality interessiert sind, können Sie sich unsere Dokumentation für [Mixed Reality-Entwickler durchsischen.](/windows/mixed-reality/design/design)

> [!NOTE]
> Die Systemanforderungen für HoloLens-Geräte basieren auf der Architektur des App-Builds. HoloLens 2-Geräte verwenden die ARM-Architektur. Wenn Sie Ihre Apps in Visual Studio, stellen Sie sicher, dass Sie die richtige Architektur für das Gerät ausgewählt haben und alle erforderlichen Abhängigkeiten enthalten.

> [!IMPORTANT]
> Bei der Bereitstellung von BRANCHEN-Apps ist es wichtig, das Zertifikat auch in Intune hochzuladen und es derselben Gruppe zu zuweisen, die die App verwenden soll, da sie nicht ordnungsgemäß installiert wird.

### <a name="upload-and-assign-the-app"></a>Hochladen und Zuweisen der App

1. Navigieren Sie zum [MEM Admin Center.](https://endpoint.microsoft.com/#home)

2. Wählen **Sie Apps**  ->  **Alle Apps** und dann die Schaltfläche + **Hinzufügen** aus.

3. Wählen Sie unter Sonstige die **Option Line-of-Business-App aus.** Klicken Sie **auf auswählen.**

4. Wählen Sie die App-Paketdatei aus. Dies ist Ihre APPXBUNDLE-Datei, oder in diesem Beispiel ist die App _MRTK Examples Hub \_ 2.4.2.0 \_ arm \_ Master.appxbundle._

5. Sie werden über fehlende Abhängigkeiten benachrichtigt. In diesem Fall müssen wir _Microsoft.VCLibs.ARM.14.00.appx hochladen._ Suchen Sie unter Datei **auswählen nach der Datei**.

6. Wählen Sie „OK“ aus.

7. Im nächsten Bildschirm werden die erforderlichen Felder automatisch ausgefüllt. Wählen Sie **Weiter** aus.

8. Fügen Sie unter Erforderlich die zuvor erstellte Gruppe hinzu, damit diese App für die Gruppe erforderlich ist. Dies führt dazu, dass die App automatisch auf registrierte Geräte in der Gruppe heruntergeladen wird. Wählen Sie **Weiter** aus.

9. Klicken Sie auf **Erstellen**.

Weitere Informationen: [Zuweisen von Apps zu Gruppen in Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Einrichtungshandbücher: Anwendungslizenzen, Datenverse und Erstellung

Um die Dynamics 365 Guides verwenden zu können, müssen Sie einige Vorbereitungen unternehmen. Es gibt drei Bereiche, in denen wir uns vorbereiten müssen: Benutzer, Datenverse und die Leitfäden selbst.

### <a name="users-and-application-licenses"></a>Benutzer und Anwendungslizenzen

Damit jemand Leitfäden verwenden kann, muss er ein Azure AD verwenden, das wir zuvor in diesem Leitfaden eingerichtet haben.

Außerdem müssen Sie dem benutzer Dynamics 365 Guides, den Sie erstellt haben, eine Lizenz zuweisen. Hierzu verwenden Sie die [Microsoft 365 Admin Center](https://admin.microsoft.com/AdminPortal/Home). Weisen Sie die Lizenz auch Ihrem primären Azure-Konto zu.

Befolgen [Sie diese kurze Anleitung](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) mit Bildern, um eine Schritt-für-Schritt-Anleitung zum Anwenden von Anwendungslizenzen zu erhalten.

### <a name="set-up-the-dataverse"></a>Einrichten der Datenverse

Um eine [Produktionsumgebung einrichten zu können,](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) müssen Sie zwei Voraussetzungen erfüllen. Sie müssen über die [**Rolle Systemadministrator**](/power-platform/admin/database-security) **verfügen,** und Sie [](/dynamics365/mixed-reality/guides/setup-step-one) müssen über eine Power Apps-Lizenz [**(oder**](/power-platform/admin/signup-question-and-answer) eine Dynamics 365 Guides-Lizenz verfügen, die eine Power Apps enthält). Wenn Sie die Schritte in diesem Leitfaden Azure AD, erfüllen Sie die Rollenanforderungen für den Systemadministrator. Außerdem haben wir im vorherigen Schritt eine Guides-Lizenz zugewiesen.

In diesem Leitfaden zum [Erstellen einer Microsoft Dataverse-Umgebung:](/dynamics365/mixed-reality/guides/setup-step-two)

1. Verwenden Sie zunächst [die](https://admin.powerplatform.microsoft.com/environments) Power Platform Admin Center und erstellen Sie eine neue Umgebung.
2. Wenn Sie die **neue Umgebung erstellen,** wählen Sie als Typ **&#39;** **Produktionsumgebung aus.**
3. Es ist wichtig, dass Sie Datenbank **für diese Umgebung erstellen umschalten?**  Option auf **Ja.**
4. Legen Sie  **im Dialogfeld Datenbank**  hinzufügen die Option Dynamics  **365-Apps aktivieren**  auf Ja  **fest.**

Sie möchten die maximale Dateigröße von Elementen in Ihrem Dataverse erhöhen. Wenn Sie die maximale Dateigröße erhöhen, können Sie größere 3D-Modelle oder Videodateien hochladen, die Sie später in Ihren Handbüchern verwenden werden. Befolgen Sie eine kurze [Anleitung, um die maximale Uploaddateigröße zu ändern.](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Schließlich müssen Sie die [Projektmappe installieren und konfigurieren.](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution) Wählen Sie im [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/environments)die Option **Ressourcen** \& gt;  **Dynamics 365-Apps,** wählen Sie **Dynamics 365 Guides** in der Liste und dann **Installieren** aus.  

Sie müssen [eine Sicherheitsrolle "Handbücher" hinzufügen,](/dynamics365/mixed-reality/guides/assign-role) bevor Sie die Apps verwenden können.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Erstellen eines Testleitfadens auf Ihrem PC per Erstellung

Beim Erstellen von Handbüchern starten Sie immer auf Ihrem PC. Erstellen der Schritte, Auswählen von Modellen und Verankern des Leitfadens. Danach werden Inhalte für Ihren Leitfaden später im Erstellungsmodus auf Ihrem HoloLens Gerät platziert. Für die Zwecke dieses Leitfadens wird empfohlen, einen kurzen Testleitfaden mit minimalen Schritten und Modellen zu erstellen.

Wenn Sie sich mit der Erstellung von Handbüchern informieren möchten, beginnen Sie hier mit der Übersicht über die [Erstellung.](/dynamics365/mixed-reality/guides/authoring-overview) Alternativ können Sie sich dieses kurze Video ansehen, um sich einen schnellen Überblick zu verschaffen.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Optional: Kioskmodus

Der Kioskmodus ist ein Modus, in dem ein IT-Administrator die Benutzeroberfläche des Startmenüs so konfiguriert, dass nur eine einzelne App oder eine Auswahl von Apps angezeigt wird. Ein Kiosk kann auch auf bestimmte Benutzer, Gruppen oder auf Geräteebene angewendet werden. und in einigen Fällen bestimmte Benutzer vom Kiosk ausschließen, sodass sie weiterhin Zugriff auf das reguläre Startmenü haben.

Der Kioskmodus verfügt über viele verschiedene Variablen, sowohl im Bereich als auch in den Konfigurationen, die festgelegt werden können, sowie Methoden zum Bereitstellen des Kiosks im HoloLens. Aufgrund all dieser Variablen bleibt der Kioskmodus für diese Anleitung _optional_ und wird nicht erneut überprüft. Wenn Sie der Meinung sind, dass Sie ein Unternehmen benötigen, um verfügbare Apps auf Benutzer zu beschränken, oder weitere Informationen erhalten möchten, können Sie sich darüber informieren, wie [Sie HoloLens als Kiosk einrichten.](/hololens/hololens-kiosk)

## <a name="optional-wdac"></a>Optional: WDAC

Mit WDAC kann ein IT-Administrator seine Geräte so konfigurieren, dass der Start von Apps auf Geräten blockiert wird. Dies unterscheidet sich von Methoden der Geräteeinschränkung, z. B. dem Kioskmodus, in dem dem Benutzer eine Benutzeroberfläche angezeigt wird, die die Apps auf dem Gerät ausblendet, aber trotzdem gestartet werden kann. Während WDAC implementiert ist, sind die Apps weiterhin in der Liste Alle Apps sichtbar, aber WDAC verhindert, dass diese Apps und Prozesse vom Gerätebenutzer gestartet werden können.

Weitere Informationen hierzu können Sie unter [Verwenden von WDAC und Windows PowerShell zum Zulassen oder Blockieren](/mem/intune/configuration/custom-profile-hololens)von Apps auf HoloLens 2 Geräten mit Microsoft Intune .

[Windows Defender Application Control – WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Nächster Schritt 
> [!div class="nextstepaction"]
> [Unternehmensverbundene Bereitstellung – Bereitstellen](hololens2-corp-connected-deploy.md)