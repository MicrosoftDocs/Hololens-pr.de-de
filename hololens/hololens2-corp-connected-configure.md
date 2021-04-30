---
title: Bereitstellungshandbuch – Mit Dem Unternehmen verbundene HoloLens 2 mit Dynamics 365-Handbüchern – Konfigurieren
description: Erfahren Sie, wie Sie konfigurationen zum Bereitstellen von HoloLens 2 Geräten über ein verbundenes Unternehmensnetzwerk mit Dynamics 365-Handbüchern einrichten.
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
ms.openlocfilehash: 939efc28a0c3255cc9a38af3cd8dd9aa8fc2ac98
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308560"
---
# <a name="configure---corporate-connected-guide"></a>Konfigurieren – Handbuch zu verbundenen Unternehmensdaten

## <a name="azure-users-and-groups"></a>Azure-Benutzer und -Gruppen

Azure und Intune von dieser Erweiterung verwenden Benutzer und Gruppen, um Konfigurationen und Lizenzen zuzuweisen. Um diesen Bereitstellungsablauf zu überprüfen und zu überprüfen, ob Sie einen Leitfaden erstellen und betreiben können, benötigen Sie&#39;ein Benutzerkonto.

Wir können eine einzelne Benutzergruppe speziell zum Zuweisen von Lizenzen erstellen.

Wenn Sie&#39;noch keinen Zugriff auf zwei Azure AD Konten in einer Benutzergruppe haben, die Sie verwenden können. Hier sind die Schnellstartanleitungen für Folgendes:

- [Erstellen eines Benutzers](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Erstellen einer Gruppe](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Hinzufügen von Benutzern zu einer Gruppe:](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) Hinzufügen von erstellten Benutzern zum Erstellen einer Gruppe
- [Konfigurieren Azure AD, um einer Benutzergruppe das Beitreten zu Geräten zu ermöglichen:](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) Stellen Sie sicher, dass eine neue Benutzergruppe über die Berechtigung zum Registrieren von Geräten für Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Automatische Registrierung bei HoloLens 2

Um eine reibungslose und nahtlose Benutzeroberfläche zu erhalten, ist das Einrichten von Azure Active Directory Join (AADJ) und der automatischen Registrierung bei Intune für HoloLens 2 Geräte die beste Vorgehensweise. Dadurch können Benutzer ihre Anmeldeinformationen für die Organisation während der OOBE eingeben und sich automatisch bei Azure AD registrieren und das Gerät bei MDM registrieren.

Mithilfe von [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)können wir Dienste auswählen und durch einige Seiten navigieren, bis wir Premium-Testversion abrufen auswählen können. Möglicherweise stellen Sie fest, dass Azure Active Directory Premium 1 und 2 vorhanden sind. Für die automatische Registrierung ist P1 ausreichend. Wir können Intune auswählen, den Benutzerbereich für die automatische Registrierung auswählen und die gruppe auswählen, die zuvor erstellt wurde.

Ausführliche Informationen und Schritte finden Sie im Leitfaden zum Aktivieren der [automatischen Registrierung für Intune.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>UnternehmensWi-Fi Konnektivität

UnternehmensWi-Fi verbindungen erfordern in der Regel eine zertifikatbasierte Authentifizierung für Kunden, die HoloLens 2. Sie müssen solche Zertifikate bereitstellen, indem Sie eine Simple Certificate Enrollment-Protokoll-Zertifikatinfrastruktur (SCEP) oder eine PUBLIC KEY Cryptography Standard-Zertifikatinfrastruktur (Public Key Cryptography Standard, PKCS) verwenden, die in Ihre MDM-Lösung integriert ist. Die Verwendung von Intune Wi-Fi Bereitstellung von Profilen, Zertifikaten und Proxyeinstellungen sorgt für eine nahtlose Benutzererfahrung.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Bereitstellen von Zertifikaten und Wi-Fi Profilen

Um Zertifikate und Profile über Microsoft Endpoint Manager bereitzustellen, führen Sie die folgenden Schritte aus:

1. Erstellen Sie ein Profil für jedes Stamm- und Zwischenzertifikat (siehe [Erstellen vertrauenswürdiger Zertifikatprofile).](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles) Jedes dieser Profile muss eine Beschreibung aufweisen, die ein Ablaufdatum im Format TT/MM/YYYY enthält. 

    > [!CAUTION]
    > **Zertifikatprofile ohne Ablaufdatum werden nicht bereitgestellt.**

2.  Erstellen Sie ein Profil für jedes SCEP- oder PKCS-Zertifikat (siehe Erstellen eines [SCEP-Zertifikatprofils](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)oder Erstellen eines PKCS-Zertifikatprofils). Jedes dieser Profile muss eine Beschreibung aufweisen, die ein Ablaufdatum im Format TT/MM/YYYY enthält. 

    > [!CAUTION]
    > **Zertifikatprofile ohne Ablaufdatum werden nicht bereitgestellt.**

    > [!Note]
    > Da die HoloLens 2 für viele als gemeinsam genutztes Gerät betrachtet wird, d. h. mehrere Benutzer pro Gerät, wird empfohlen, gerätezertifikate anstelle von Benutzerzertifikaten für die Wi-Fi-Authentifizierung bereitzustellen.

3.  Erstellen Sie ein Profil für Ihr Unternehmensnetzwerk Wi-Fi (siehe [WLAN-Einstellungen für](https://docs.microsoft.com/intune/wi-fi-settings-windows)Windows 10 und höher). In Ihrem Wi-Fi können Sie die Proxyeinstellungen in Ihrer Organisation verwenden.
 
    Folgende Optionen sind verfügbar:
    - **Keine**: Es sind keine Proxyeinstellungen konfiguriert.
    - **Manuell konfigurieren:** Geben Sie die **IP-Adresse des Proxyservers** und die zugehörige **Portnummer** ein.
    - **Automatisch konfigurieren:** Geben Sie die URL ein, die auf ein PAC-Skript (Proxy Auto-Configuration, automatische Proxykonfiguration) zeigt. Geben Sie z.B. *http://proxy.contoso.com/proxy.pac* ein.

    Weitere Informationen zu PAC-Dateien finden Sie unter [Proxy Auto-Configuration (PAC) file (Datei für die automatische Proxykonfiguration)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (öffnet eine Drittanbieterwebsite).
 
    > [!Note]
    > Es wird empfohlen, Wi-Fi Gerätegruppen anstelle von Benutzergruppen zu zuweisen.
     
    > [!Tip]
    > Sie können auch ein arbeitsorientiertes profil Wi-Fi von einem Windows 10 PC in Ihrem Unternehmensnetzwerk exportieren. Dieser Export erstellt eine XML-Datei mit allen aktuellen Einstellungen. Importieren Sie diese Datei dann in Intune, und verwenden Sie sie als Wi-Fi Profil für Ihre HoloLens 2 Geräte. Weitere Informationen finden Sie unter [Exportieren und Importieren von WLAN-Einstellungen für Windows-Geräte](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Weisen Sie](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) die Geräteprofile der HoloLens-Gerätegruppe zu.

2.  [Überwachen Sie](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) die Geräteprofile in Intune.

Wenn Probleme mit Wi-Fi Profilen auftreten, finden Sie weitere Informationen unter [Problembehandlung Wi-Fi Gerätekonfigurationsprofile in Intune.](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Problembehandlung bei externem Internetzugriff bei Unternehmensverbindung
Wenn Dienste versuchen, keinen festgelegten Proxy zu durchlaufen, versuchen sie möglicherweise, eine Verbindung über die Firewall herzustellen. Sie können Ihren Firewallregeln eine Liste mit Endpunkten hinzufügen, um diese Probleme zu beheben.

Wenn Sie an Firewallports blockiert sind, aktivieren Sie einige gängige [Endpunkte](https://docs.microsoft.com/hololens/hololens-offline) für HoloLens.

Sie können auch die spezifischen Ports für Handbücher aktivieren: UrLs, auf die über das [Internet zugegriffen werden kann, die für die Konnektivität mit Microsoft Dynamics CRM Online erforderlich sind.](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)

## <a name="app-deployment"></a>App-Bereitstellung

Die Bereitstellung einer branchenweiten App über MDM ist eine Methode, die einfach skalierbar ist und bei der Registrierung in einer erstellten Gruppe automatisch auf Ihren Geräten bereitgestellt werden kann.

Wenn Sie Ihre Apps noch entwickeln oder noch keine haben, können Sie eine Beispiel-App des MRTK-Beispielhubs verwenden. Diese Beispiel-App ist einsatzbereit und erfordert weder Unity noch Visual Studio. [Laden Sie die MRTK-Beispiel-App herunter.](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)

Wenn Sie ihre eigene App verwenden möchten oder an der App-Entwicklung für Mixed Reality interessiert sind, können Sie sich unsere [Mixed Reality Entwicklerdokumentation](https://docs.microsoft.com/windows/mixed-reality/design/design)ansehen.

> [!NOTE]
> Die Systemanforderungen für HoloLens-Geräte basieren auf der Architektur des App-Builds. HoloLens 2 Geräte verwenden die ARM-Architektur. Stellen Sie beim Erstellen Ihrer Apps in Visual Studio sicher, dass Sie die richtige Architektur für das Gerät ausgewählt haben und alle erforderlichen Abhängigkeiten einschließen.

> [!IMPORTANT]
> Beim Bereitstellen von Branchen-Apps ist es wichtig, das Zertifikat auch in Intune hochzuladen und es derselben Gruppe zuzuweisen, die die App verwenden soll, oder es wird nicht ordnungsgemäß installiert.

### <a name="upload-and-assign-the-app"></a>Hochladen und Zuweisen der App

1. Navigieren Sie zum [MEM Admin Center.](https://endpoint.microsoft.com/#home)

2. Wählen Sie **Apps**  ->  **Alle Apps** und dann die Schaltfläche **+ Hinzufügen** aus.

3. Wählen Sie unter Sonstige die **Option Line-of-Business-App aus.** Klicken Sie **auf auswählen.**

4. Wählen Sie die App-Paketdatei aus. Dies ist Ihre APPXBUNDLE-Datei, oder in diesem Beispiel ist die App _MRTK Examples Hub \_ 2.4.2.0 \_ arm \_ Master.appxbundle._

5. Sie werden über fehlende Abhängigkeiten benachrichtigt. In diesem Fall müssen wir _Microsoft.VCLibs.ARM.14.00.appx hochladen._ Suchen Sie unter Datei **auswählen nach der Datei**.

6. Wählen Sie „OK“ aus.

7. Im nächsten Bildschirm werden die erforderlichen Felder automatisch ausgefüllt. Wählen Sie **Weiter** aus.

8. Fügen Sie unter Erforderlich die zuvor erstellte Gruppe hinzu, damit diese App für die Gruppe erforderlich ist. Dies führt dazu, dass die App automatisch auf registrierte Geräte in der Gruppe heruntergeladen wird. Wählen Sie **Weiter** aus.

9. Klicken Sie auf **Erstellen**.

Weitere Informationen: [Zuweisen von Apps zu Gruppen in Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Einrichtungshandbücher: Anwendungslizenzen, Datenverse und Erstellung

Um Dynamics 365-Handbücher verwenden zu können, müssen Sie einige Vorbereitungen unternehmen. Es gibt drei Bereiche, in denen wir uns vorbereiten müssen: Benutzer, Datenverse und die Leitfäden selbst.

### <a name="users-and-application-licenses"></a>Benutzer und Anwendungslizenzen

Damit jemand Leitfäden verwenden kann, muss er ein Azure AD verwenden, das wir zuvor in diesem Leitfaden eingerichtet haben.

Außerdem müssen Sie dem erstellten Benutzer die Dynamics 365 Guides-Lizenz zuweisen. Hierzu verwenden Sie die [Microsoft 365 Admin Center](https://admin.microsoft.com/AdminPortal/Home). Weisen Sie die Lizenz auch Ihrem primären Azure-Konto zu.

Befolgen [Sie diese kurze Anleitung](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) mit Bildern, um schritt-für-Schritt-Anweisungen zum Anwenden von Anwendungslizenzen zu erhalten.

### <a name="set-up-the-dataverse"></a>Einrichten der Datenverse

Um [eine Produktionsumgebung einzurichten,](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) müssen Sie zwei Voraussetzungen erfüllen. Sie benötigen die [**Systemadministratorrolle**](https://docs.microsoft.com/power-platform/admin/database-security)  **und**  eine [**Power Apps Lizenz**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer) (oder eine Dynamics [**365 Guides-Lizenz,**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one) die eine Power Apps-Lizenz enthält). Wenn Sie diese Anleitung befolgen, haben Sie die Azure AD erstellt, dann erfüllen Sie die Rollenanforderungen für Systemadministrator. Im vorherigen Schritt haben wir auch eine Lizenz für Handbücher zugewiesen.

In diesem Leitfaden zum [Erstellen einer Microsoft Dataverse-Umgebung:](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two)

1. Verwenden Sie zunächst die [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/environments) und erstellen Sie eine neue Umgebung.
2. Wenn Sie die **neue Umgebung** erstellen, wählen Sie für den **Typ,** den Sie&#39;, die Option **Produktion** aus.
3. Es ist wichtig, dass Sie Datenbank **für diese Umgebung erstellen umschalten?**  -Option auf **Ja.**
4. Legen  **Sie**  im Dialogfeld Datenbank hinzufügen die Option  **Dynamics 365-Apps aktivieren**  auf  **Ja fest.**

Sie möchten die maximale Dateigröße von Elementen in Ihrem Dataverse erhöhen. Wenn Sie die maximale Dateigröße erhöhen, können Sie größere 3D-Modelle oder Videodateien hochladen, die Sie später in Ihren Handbüchern verwenden werden. Befolgen Sie eine kurze [Anleitung, um die maximale Uploaddateigröße zu ändern.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Schließlich müssen Sie die [Projektmappe installieren und konfigurieren.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution) Wählen Sie im [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/environments) **die** Option Ressourcen \& gt;  **Dynamics 365-Apps,** wählen Sie **Dynamics 365 Guides** in der Liste und dann **Installieren** aus.  

Sie müssen [eine Sicherheitsrolle "Handbücher" hinzufügen,](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) bevor Sie die Apps verwenden können.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Erstellen eines Testleitfadens auf Ihrem PC per Erstellung

Beim Erstellen von Handbüchern starten Sie immer auf Ihrem PC. Erstellen der Schritte, Auswählen von Modellen und Verankern des Leitfadens. Danach werden Inhalte für Ihren Leitfaden später im Erstellungsmodus auf Ihrem HoloLens-Gerät platziert. Für die Zwecke dieses Leitfadens empfehlen wir, einen kurzen Testleitfaden mit minimalen Schritten und Modellen zu erstellen.

Wenn Sie mit dem Erstellen von Leitfäden beginnen möchten, beginnen Sie hier mit der [Übersicht über die Erstellung.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview) Oder sehen Sie sich dieses kurze Video an, um sich einen Schnellen Überblick zu verschaffen.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Optional: Kioskmodus

Der Kioskmodus ist ein Modus, in dem ein IT-Administrator die Benutzeroberfläche des Startmenüs so konfigurieren kann, dass nur eine einzelne App oder eine Auswahl von Apps angezeigt wird. Ein Kiosk kann auch auf bestimmte Benutzer, Gruppen oder auf Geräteebene angewendet werden. und in einigen Fällen bestimmte Benutzer aus dem Kiosk ausschließen, sodass sie weiterhin Zugriff auf das reguläre Startmenü haben.

Der Kioskmodus verfügt über viele verschiedene Variablen, sowohl im Bereich als auch in den Konfigurationen, die festgelegt werden können, sowie methoden zum Bereitstellen des Kiosks auf der HoloLens. Aufgrund all dieser Variablen bleibt der Kioskmodus für diesen Leitfaden _optional_ und wird nicht erneut verwendet. Wenn Sie der Meinung sind, dass Sie eine geschäftliche Notwendigkeit haben, verfügbare Apps auf Benutzer zu beschränken, oder mehr erfahren möchten, können Sie sich darüber informieren, wie [Sie HoloLens](https://docs.microsoft.com/hololens/hololens-kiosk)als Kiosk einrichten.

## <a name="optional-wdac"></a>Optional: WDAC

WDAC ermöglicht einem IT-Administrator, seine Geräte so zu konfigurieren, dass das Starten von Apps auf Geräten blockiert wird. Dies ist anders als die Methoden der Geräteeinschränkung, z. B. kioskmodus, in dem dem Benutzer eine Benutzeroberfläche angezeigt wird, die die Apps auf dem Gerät ausblendet, aber trotzdem gestartet werden kann. Während WDAC implementiert ist, sind die Apps weiterhin in der Liste Alle Apps sichtbar, aber WDAC verhindert, dass diese Apps und Prozesse vom Gerätebenutzer gestartet werden können.

Weitere Informationen finden Sie unter [Use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

[Windows Defender Anwendungssteuerung – WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Nächster Schritt 
> [!div class="nextstepaction"]
> [Bereitstellung im verbundenen Unternehmen – Bereitstellen](hololens2-corp-connected-deploy.md)