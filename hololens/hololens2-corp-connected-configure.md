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
ms.openlocfilehash: 9457acd2f53d0d3127d6c68d620b660f6e09866d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637080"
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

Um eine reibungslose und nahtlose Benutzererfahrung zu gewährleisten, ist das Einrichten von Azure Active Directory Join (AADJ) und der automatischen Registrierung bei Intune für HoloLens 2-Geräte die erste Möglichkeit. Dadurch können Benutzer ihre Anmeldeinformationen für die Organisation während der OOBE eingeben und sich automatisch bei Azure AD registrieren und das Gerät bei MDM registrieren.

Mithilfe [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)können wir Dienste auswählen und in einigen Seiten navigieren, bis wir auf Get a Premium trial (Testversion Premium können. Möglicherweise werden Sie feststellen, dass Azure Active Directory Premium 1 und 2 vorhanden sind. Für die automatische Registrierung ist P1 ausreichend. Wir können Intune auswählen und den Benutzerbereich für die automatische Registrierung auswählen und die Gruppe auswählen, die zuvor erstellt wurde.

Ausführliche Informationen und Schritte finden Sie im Leitfaden zum Aktivieren der [automatischen Registrierung für Intune.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>UnternehmensWi-Fi Konnektivität

UnternehmensWi-Fi verbindungen erfordern in der Regel eine zertifikatbasierte Authentifizierung für Kunden, die HoloLens 2. Sie müssen solche Zertifikate bereitstellen, indem Sie eine Simple Certificate Enrollment-Protokoll-Zertifikatinfrastruktur (SCEP) oder eine PUBLIC KEY Cryptography Standard-Zertifikatinfrastruktur (Public Key Cryptography Standard, PKCS) verwenden, die in Ihre MDM-Lösung integriert ist. Die Verwendung von Intune Wi-Fi Bereitstellung von Profilen, Zertifikaten und Proxyeinstellungen sorgt für eine nahtlose Benutzererfahrung.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Bereitstellen von Zertifikaten und Wi-Fi Profilen

Führen Sie zum Bereitstellen von Zertifikaten und Profilen Microsoft Endpoint Manager folgenden Schritte aus:

1. Erstellen Sie ein Profil für jedes Stamm- und Zwischenzertifikat (siehe [Erstellen vertrauenswürdiger Zertifikatprofile).](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Jedes dieser Profile muss eine Beschreibung aufweisen, die ein Ablaufdatum im Format TT/MM/YYYY enthält.

    > [!CAUTION]
    > **Zertifikatprofile ohne Ablaufdatum werden nicht bereitgestellt.**

2. Erstellen Sie ein Profil für jedes SCEP- oder PKCS-Zertifikat (siehe Erstellen eines [SCEP-Zertifikatprofils](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)oder Erstellen eines PKCS-Zertifikatprofils). Jedes dieser Profile muss eine Beschreibung aufweisen, die ein Ablaufdatum im Format TT/MM/YYYY enthält.

    > [!CAUTION]
    > **Zertifikatprofile ohne Ablaufdatum werden nicht bereitgestellt.**

    > [!Note]
    > Da die HoloLens 2 für viele als gemeinsam genutztes Gerät betrachtet wird, d. h. mehrere Benutzer pro Gerät, wird empfohlen, gerätezertifikate anstelle von Benutzerzertifikaten für die Wi-Fi-Authentifizierung bereitzustellen, wenn dies möglich ist.

3. Erstellen Sie ein Profil für Ihr Unternehmensnetzwerk Wi-Fi (siehe [WLAN-Einstellungen für](/intune/wi-fi-settings-windows)Windows 10 und höher). In Ihrem Wi-Fi können Sie die Proxyeinstellungen in Ihrer Organisation verwenden.

    Folgende Optionen sind verfügbar:
    - **Keine**: Es sind keine Proxyeinstellungen konfiguriert.
    - **Manuell konfigurieren:** Geben Sie die **IP-Adresse des Proxyservers** und die zugehörige **Portnummer** ein.
    - **Automatisch konfigurieren:** Geben Sie die URL ein, die auf ein PAC-Skript (Proxy Auto-Configuration, automatische Proxykonfiguration) zeigt. Geben Sie z.B. *http://proxy.contoso.com/proxy.pac* ein.

    Weitere Informationen zu PAC-Dateien finden Sie unter [Proxy Auto-Configuration (PAC) file (Datei für die automatische Proxykonfiguration)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (öffnet eine Drittanbieterwebsite).
 
    > [!Note]
    > Es wird empfohlen, Wi-Fi Gerätegruppen anstelle von Benutzergruppen zu zuweisen.
     
    > [!Tip]
    > Sie können auch ein Arbeitsprofil Wi-Fi von einem Windows 10 PC in Ihrem Unternehmensnetzwerk exportieren. Dieser Export erstellt eine XML-Datei mit allen aktuellen Einstellungen. Importieren Sie diese Datei dann in Intune, und verwenden Sie sie als Wi-Fi Profil für Ihre HoloLens 2 Geräte. Weitere Informationen finden Sie unter [Exportieren und Importieren von WLAN-Einstellungen für Windows-Geräte](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Weisen](/mem/intune/configuration/device-profile-assign) Sie die Geräteprofile der HoloLens zu.

2.  [Überwachen](/mem/intune/configuration/device-profile-monitor) Sie die Geräteprofile in Intune.

Wenn Probleme mit Wi-Fi-Profilen Wi-Fi Problembehandlung [bei Gerätekonfigurationsprofilen in Intune.](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Problembehandlung beim externen Internetzugriff bei verbundener Corp.
Wenn Dienste versuchen, keinen festgelegten Proxy zu passieren, versuchen sie möglicherweise, eine Verbindung über die Firewall herzustellen. Sie können Ihren Firewallregeln eine Liste von Endpunktspezifisch hinzufügen, um diese Probleme zu beheben.

Wenn Sie an Firewallports blockiert sind, aktivieren Sie einige allgemeine [Endpunkte](/hololens/hololens-offline) für HoloLens.

Sie können auch die leitfädenspezifischen Ports aktivieren: [URLs,](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)die über das Internet zugänglich sind, die für die Konnektivität mit Microsoft Dynamics CRM Online.

## <a name="app-deployment"></a>App-Bereitstellung

Die Bereitstellung einer BRANCHEN-App über MDM ist eine methode, die leicht skalierbar ist und bei der Registrierung in einer erstellten Gruppe automatisch auf Ihren Geräten bereitgestellt werden kann.

Wenn Sie Ihre Apps noch entwickeln oder noch keines haben, können Sie eine Beispiel-App des MRTK-Beispielhubs verwenden. Diese Beispiel-App ist einsatzbereit und erfordert weder Unity noch Visual Studio. [Laden Sie die MRTK-Beispiel-Beispiel-App herunter.](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)

Wenn Sie lieber Ihre eigene App verwenden möchten oder an der App-Entwicklung für Mixed Reality interessiert sind, können Sie sich unsere Dokumentation für [Mixed Reality-Entwickler durchsischen.](/windows/mixed-reality/design/design)

> [!NOTE]
> Die Systemanforderungen für HoloLens basieren auf der Architektur des App-Build. HoloLens 2-Geräte verwenden die ARM-Architektur. Wenn Sie Ihre Apps in Visual Studio, stellen Sie sicher, dass Sie die richtige Architektur für das Gerät ausgewählt haben und alle erforderlichen Abhängigkeiten enthalten.

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

9. Wählen Sie **Erstellen** aus.

Weitere Informationen: [Zuweisen von Apps zu Gruppen in Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Einrichtungshandbücher: Anwendungslizenzen, Datenverse und Erstellung

Um die Dynamics 365 Guides verwenden zu können, müssen Sie einige Vorbereitungen unternehmen. Es gibt drei Bereiche, in denen wir uns vorbereiten müssen: Benutzer, Datenverse und die Leitfäden selbst.

### <a name="users-and-application-licenses"></a>Benutzer und Anwendungslizenzen

Damit jemand Leitfäden verwenden kann, muss er ein Azure AD verwenden, das wir zuvor in diesem Leitfaden eingerichtet haben.

Außerdem müssen Sie dem benutzer Dynamics 365 Guides, den Sie erstellt haben, eine Lizenz zuweisen. Dies wird über die [Microsoft 365 Admin Center.](https://admin.microsoft.com/AdminPortal/Home) Weisen Sie die Lizenz auch Ihrem primären Azure-Konto zu.

Befolgen [Sie diese kurze Anleitung](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) mit Bildern, um schritt-für-Schritt-Anweisungen zum Anwenden von Anwendungslizenzen zu erhalten.

### <a name="set-up-the-dataverse"></a>Einrichten der Datenverse

Um eine [Produktionsumgebung einrichten zu können,](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) müssen Sie zwei Voraussetzungen erfüllen. Sie müssen über die [**Rolle Systemadministrator**](/power-platform/admin/database-security) **verfügen,** und Sie [](/dynamics365/mixed-reality/guides/setup-step-one) müssen über eine Power Apps-Lizenz [**(oder**](/power-platform/admin/signup-question-and-answer) eine Dynamics 365 Guides-Lizenz verfügen, die eine Power Apps enthält). Wenn Sie die Schritte in diesem Leitfaden Azure AD, erfüllen Sie die Rollenanforderungen für den Systemadministrator. Außerdem haben wir im vorherigen Schritt eine Guides-Lizenz zugewiesen.

In diesem Leitfaden zum [Erstellen einer Microsoft Dataverse-Umgebung:](/dynamics365/mixed-reality/guides/setup-step-two)

1. Verwenden Sie zunächst [die](https://admin.powerplatform.microsoft.com/environments) Power Platform Admin Center und erstellen Sie eine neue Umgebung.
2. Wenn Sie die **neue Umgebung erstellen,** wählen Sie als Typ **&#39;** **Produktionsumgebung aus.**
3. Es ist wichtig, dass Sie Datenbank **für diese Umgebung erstellen umschalten?**  Option auf **Ja.**
4. Legen Sie  **im Dialogfeld Datenbank**  hinzufügen die Option Dynamics  **365-Apps aktivieren**  auf Ja  **fest.**

Sie sollten die maximale Dateigröße von Elementen in Ihrem Datenverse erhöhen. Wenn Sie die maximale Dateigröße erhöhen, können Sie größere 3D-Modelle oder Videodateien hochladen, die Sie später in Ihren Leitfäden verwenden werden. Befolgen Sie eine kurze [Anleitung, um die maximale Uploaddateigröße zu ändern.](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Schließlich müssen Sie die Lösung [installieren und konfigurieren.](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution) Wählen Sie [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/environments)ressourcen  \& gt; aus.  **Dynamics 365-Apps**, wählen **Dynamics 365 Guides** in der Liste und dann **Installieren aus.**  

Sie müssen [eine Sicherheitsrolle Leitfäden hinzufügen,](/dynamics365/mixed-reality/guides/assign-role) bevor Sie die Apps verwenden können.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Erstellen eines Testhandbuchs auf Ihrem PC über die Erstellung

Beim Erstellen von Leitfäden starten Sie immer auf Ihrem PC. Erstellen der Schritte, Auswählen von Modellen und Verankern des Leitfadens Danach platzieren Sie Inhalte für Ihren Leitfaden später im Erstellungsmodus auf Ihrem HoloLens Gerät. Für die Zwecke dieses Leitfadens empfehlen wir, einen kurzen Testleitfaden mit minimalen Schritten und Modellen zu erstellen.

Wenn Sie mit dem Erstellen von Leitfäden beginnen möchten, beginnen Sie hier mit der [Übersicht über die Erstellung.](/dynamics365/mixed-reality/guides/authoring-overview) Oder sehen Sie sich dieses kurze Video an, um sich einen Schnellen Überblick zu verschaffen.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Optional: Kioskmodus

Der Kioskmodus ist ein Modus, in dem ein IT-Administrator die Benutzeroberfläche des Startmenüs so konfigurieren kann, dass nur eine einzelne App oder eine Auswahl von Apps angezeigt wird. Ein Kiosk kann auch auf bestimmte Benutzer, Gruppen oder auf Geräteebene angewendet werden. und in einigen Fällen bestimmte Benutzer aus dem Kiosk ausschließen, sodass sie weiterhin Zugriff auf das reguläre Startmenü haben.

Der Kioskmodus verfügt über viele verschiedene Variablen, sowohl im Bereich als auch in den Konfigurationen, die festgelegt werden können, sowie methoden zum Bereitstellen des Kiosks für HoloLens. Aufgrund all dieser Variablen bleibt der Kioskmodus für diesen Leitfaden _optional_ und wird nicht erneut verwendet. Wenn Sie der Meinung sind, dass Sie eine geschäftliche Notwendigkeit haben, verfügbare Apps auf Benutzer zu beschränken, oder mehr erfahren möchten, können Sie sich darüber informieren, wie Sie HoloLens als Kiosk [einrichten.](/hololens/hololens-kiosk)

## <a name="optional-wdac"></a>Optional: WDAC

WDAC ermöglicht einem IT-Administrator, seine Geräte so zu konfigurieren, dass das Starten von Apps auf Geräten blockiert wird. Dies ist anders als die Methoden der Geräteeinschränkung, z. B. kioskmodus, in dem dem Benutzer eine Benutzeroberfläche angezeigt wird, die die Apps auf dem Gerät ausblendet, aber trotzdem gestartet werden kann. Während WDAC implementiert ist, sind die Apps weiterhin in der Liste Alle Apps sichtbar, aber WDAC verhindert, dass diese Apps und Prozesse vom Gerätebenutzer gestartet werden können.

Weitere Informationen finden Sie unter [Use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).

[Windows Defender Application Control – WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Nächster Schritt 
> [!div class="nextstepaction"]
> [Bereitstellung im verbundenen Unternehmen – Bereitstellen](hololens2-corp-connected-deploy.md)