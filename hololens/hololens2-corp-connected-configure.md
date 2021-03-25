---
title: Bereitstellungshandbuch – Unternehmensverknte HoloLens 2 mit Dynamics 365-Anleitungen – Konfigurieren
description: Erfahren Sie, wie Sie Konfigurationen für die Bereitstellung von HoloLens 2-Geräten über ein verbundenes Unternehmensnetzwerk mit Dynamics 365-Anleitungen einrichten.
keywords: HoloLens, Verwaltung, unternehmensgebunden, Dynamics 365-Anleitungen, AAD, Azure AD, MDM, Verwaltung mobiler Geräte
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
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448558"
---
# <a name="configure---corporate-connected-guide"></a>Configure – Corporate Connected Guide

## <a name="azure-users-and-groups"></a>Azure-Benutzer und -Gruppen

Azure und Intune mit dieser Erweiterung verwenden Benutzer und Gruppen, um Konfigurationen und Lizenzen zuzuordnen. Um diesen Bereitstellungsfluss zu überprüfen und zu überprüfen, ob Sie einen Leitfaden erstellen und betreiben können, benötigen Sie&#39;Benutzerkonto.

Wir können eine einzelne Benutzergruppe speziell zum Zuweisen von Lizenzen erstellen.

Wenn Sie&#39;nicht bereits Zugriff auf zwei Azure #A0 in einer Benutzergruppe haben, die Sie verwenden können; Hier sind die Schnellstartanleitungen für:

- [Erstellen eines Benutzers](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Erstellen einer Gruppe](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Hinzufügen von Benutzern zu einer Gruppe](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Hinzufügen erstellter Benutzer zum Erstellen einer Gruppe
- [Konfigurieren von Azure AD, um einer Benutzergruppe](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) den Beitritt zu Geräten zu ermöglichen – Sicherstellen, dass neue Benutzergruppe über die Berechtigung zum Registrieren von Geräten bei Azure AD verfügt

## <a name="auto-enrollment-on-hololens-2"></a>Automatische Registrierung auf HoloLens 2

Um eine reibungslose und nahtlose Oberfläche zu bieten, ist das Einrichten von Azure Active Directory Join (AADJ) und der automatischen Registrierung bei Intune für HoloLens 2-Geräte der weg. Auf diese Weise können Benutzer ihre Anmeldeinformationen für die Organisation während der OOBE eingeben und sich automatisch bei Azure AD registrieren und das Gerät bei MDM registrieren.

Mithilfe von [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)können wir Dienste auswählen und einige Seiten navigieren, bis wir eine Premium-Testversion erhalten auswählen können. Möglicherweise ist Azure Active Directory Premium 1 und 2 vorhanden – für die automatische Registrierung ist P1 ausreichend. Wir können Intune auswählen und den Benutzerbereich für die automatische Registrierung auswählen und die zuvor erstellte Gruppe auswählen.

Ausführliche Informationen und Schritte finden Sie in der Anleitung zum [Aktivieren der automatischen Registrierung für Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).

## <a name="corporate-wi-fi-connectivity"></a>Konnektivität Wi-Fi Unternehmens

UnternehmensWi-Fi Verbindungen erfordern in der Regel eine zertifikatbasierte Authentifizierung für Kunden, die HoloLens 2 verwenden. Sie müssen diese Zertifikate mithilfe einer #A0 (Simple Certificate Enrollment Protocol) oder einer #A1 (Public Key Cryptography Standard) bereitstellen, die in Ihre #A1 integriert ist. Die Verwendung von Intune zum Wi-Fi von Profilen, Zertifikaten und Proxyeinstellungen sorgt für eine nahtlose Benutzererfahrung.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Bereitstellen von Zertifikaten und Wi-Fi Profilen

Führen Sie zum Bereitstellen von Zertifikaten und Profilen über Microsoft Endpoint Manager die folgenden Schritte aus:

1. Erstellen Sie ein Profil für jedes Stamm- und Zwischenzertifikat (siehe [Erstellen von vertrauenswürdigen Zertifikatprofilen](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)). Jedes dieser Profile muss eine Beschreibung enthalten, die ein Ablaufdatum im DD/MM/JJJJ-Format enthält. 

    > [!CAUTION]
    > **Zertifikatprofile ohne Ablaufdatum werden nicht bereitgestellt.**

2.  Erstellen Sie ein Profil für jedes SCEP- oder PKCS-Zertifikat (siehe [Erstellen eines SCEP-Zertifikatprofils oder eines PKCS-Zertifikatprofils](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)). Jedes dieser Profile muss eine Beschreibung mit einem Ablaufdatum im Format TT/MM/JJJJ aufweisen. 

    > [!CAUTION]
    > **Zertifikatprofile ohne Ablaufdatum werden nicht bereitgestellt.**

    > [!Note]
    > Da HoloLens 2 für viele als freigegebenes Gerät betrachtet wird, d. h. mehrere Benutzer pro Gerät, wird empfohlen, Gerätezertifikate anstelle von Benutzerzertifikaten für die Wi-Fi bereitstellen.

3.  Erstellen Sie ein Profil für Wi-Fi Netzwerk (siehe [WLAN-Einstellungen für Windows 10 und höher).](https://docs.microsoft.com/intune/wi-fi-settings-windows) In Ihrem Wi-Fi können Sie die Proxyeinstellungen in Ihrer Organisation verwenden.
 
    Ihre Optionen:
    - **Keine**: Es sind keine Proxyeinstellungen konfiguriert.
    - **Manuell konfigurieren:** Geben Sie die **Proxyserver-IP-Adresse und** die **Portnummer ein.**
    - **Automatisch konfigurieren**: Geben Sie die URL ein, die auf ein Pac-Skript (Proxy Auto Configuration) verweist. Geben Sie z. B. *http://proxy.contoso.com/proxy.pac* ein.

    Weitere Informationen zu PAC-Dateien finden Sie unter [Proxy Auto-Configuration (PAC)-Datei](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (öffnet eine Nicht-Microsoft-Website).
 
    > [!Note]
    > Es empfiehlt sich, das WLAN-Profil möglichst Gerätegruppen statt Benutzergruppen zuzuweisen.
     
    > [!Tip]
    > Sie können auch ein funktionierendes WLAN-Profil von einem Windows 10-PC in Ihrem Unternehmensnetzwerk exportieren. Mit diesem Export wird eine XML-Datei mit allen aktuellen Einstellungen erstellt. Importieren Sie dann diese Datei in Intune, und verwenden Sie sie als WLAN-Profil für Ihre HoloLens 2-Geräte. Weitere Informationen finden Sie unter Export [and import Wi-Fi settings for Windows devices](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Weisen](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) Sie die Geräteprofile der HoloLens-Gerätegruppe zu.

2.  [Überwachen](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) Sie die Geräteprofile in Intune.

Wenn Probleme mit den Wi-Fi auftreten, verweisen Sie auf [Problembehandlung Wi-Fi Gerätekonfigurationsprofile in Intune](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles).

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Problembehandlung bei externem Internetzugriff, wenn Corp verbunden ist
Wenn Dienste versuchen, keinen festgelegten Proxy zu verwenden, versuchen sie möglicherweise, eine Verbindung über die Firewall herzustellen. Sie können ihren Firewallregeln eine Liste von Endpunktspezifischen hinzufügen, um diese Probleme zu beheben.

Wenn Sie an Firewallports blockiert sind, aktivieren Sie einige allgemeine [Endpunkte](https://docs.microsoft.com/hololens/hololens-offline) für HoloLens.

Sie können auch die Handbücher für bestimmte Ports aktivieren: URLs mit [Internetzugriff,](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)die für die Verbindung mit Microsoft Dynamics CRM Online.

## <a name="app-deployment"></a>App-Bereitstellung

Das Bereitstellen einer Branchen-App über MDM ist eine leicht skalierbare Methode, die bei der Registrierung in einer erstellten Gruppe automatisch auf Ihren Geräten bereitgestellt werden kann.

Wenn Sie Ihre Apps noch entwickeln oder noch keine haben, können Sie eine Beispiel-App des MRTK-Beispielhubs verwenden. Diese Beispiel-App ist einsatzbereit und erfordert weder Unity noch Visual Studio. [Laden Sie die BEISPIEL-App MRTK-Beispiele herunter.](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)

Wenn Sie ihre eigene App verwenden möchten oder an der App-Entwicklung für Mixed Reality interessiert sind, lesen Sie unsere [Mixed Reality-Entwicklerdokumentation](https://docs.microsoft.com/windows/mixed-reality/design/design).

> [!NOTE]
> Die Systemanforderungen für HoloLens-Geräte basieren auf der Architektur des App-Builds. HoloLens 2-Geräte verwenden ARM Architektur. Stellen Sie beim Erstellen ihrer Visual Studio sicher, dass Sie die richtige Architektur für das Gerät ausgewählt haben und alle erforderlichen Abhängigkeiten enthalten.

> [!IMPORTANT]
> Bei der Bereitstellung von Branchen-Apps ist es wichtig, das Zertifikat auch in Intune hochzuladen und es derselben Gruppe zuzuordnen, die die App verwenden soll, oder es wird nicht ordnungsgemäß installiert.

### <a name="upload-and-assign-the-app"></a>Hochladen und Zuweisen der App

1. Navigieren Sie zum [MEM Admin Center](https://endpoint.microsoft.com/#home).

2. Wählen **Sie Apps**Alle Apps  ->  **aus,** und wählen Sie die Schaltfläche + **Hinzufügen** aus.

3. Wählen Sie unter Other die **Option Line-of-Business-App aus.** Klicken Sie **auf Auswählen**.

4. Wählen Sie die App-Paketdatei aus, dies ist Ihre APPXBUNDLE-Datei, oder in unserem Fall ist die App _MRTK Examples Hub\_2.4.2.0\_arm\_Master.appxbundle_.

5. Sie werden über fehlende Abhängigkeiten benachrichtigt. In diesem Fall müssen wir _Microsoft.VCLibs.ARM.14.00.appx hochladen._ Suchen Sie unter **Wählen Sie eine Datei.**

6. Wählen Sie OK aus.

7. Im nächsten Bildschirm werden die erforderlichen Felder automatisch ausgefüllt. Wählen Sie **Weiter** aus.

8. Fügen Sie unter Erforderlich unsere zuvor erstellte Gruppe hinzu, um diese App für die Gruppe erforderlich zu machen. Dadurch wird die App automatisch auf registrierte Geräte in der Gruppe heruntergeladen. Wählen Sie **Weiter** aus.

9. Wählen Sie **Erstellen** aus.

Weitere Informationen: [Zuweisen von Apps zu Gruppen in Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Setupanleitungen: Anwendungslizenzen, Dataverse und Erstellung

Um Dynamics 365-Anleitungen verwenden zu können, müssen Sie einige Vorbereitungen machen. Es gibt drei Bereiche, in denen wir uns vorbereiten müssen. benutzer, dataverse und die Führungslinien selbst.

### <a name="users-and-application-licenses"></a>Benutzer und Anwendungslizenzen

Damit jemand Guides verwenden kann, muss er ein Azure AD-Konto verwenden, das wir zuvor in diesem Handbuch eingerichtet haben.

Sie müssen dem benutzer, den Sie erstellt haben, auch die Dynamics 365-Anleitungslizenz zuweisen. Sie können dies über das [Microsoft 365 Admin Center tun.](https://admin.microsoft.com/AdminPortal/Home) Weisen Sie die Lizenz auch Ihrem primären Azure-Konto zu.

Befolgen [Sie diese kurze Anleitung](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) mit Bildern, um schrittweise Anweisungen zum Anwenden von Anwendungslizenzen zu erhalten.

### <a name="set-up-the-dataverse"></a>Einrichten der Dataverse

Um eine [Produktionsumgebung einrichten zu](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) können, müssen Sie zwei Voraussetzungen erfüllen. Sie müssen über die [**Systemadministratorrolle**](https://docs.microsoft.com/power-platform/admin/database-security) verfügen  **und**  über eine [**Power Apps-Lizenz**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer) (oder eine [**Dynamics 365**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one) Guides-Lizenz, die eine Power Apps-Lizenz enthält) verfügen. Wenn Sie diesem Leitfaden folgen, haben Sie Azure AD erstellt, dann erfüllen Sie die Rollenanforderungen für Systemadministratoren. Außerdem haben wir im vorherigen Schritt eine Guides-Lizenz zugewiesen.

In diesem Handbuch zum [Erstellen einer Microsoft Dataverse-Umgebung:](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two)

1. Verwenden Sie zunächst [das Power Platform Admin Center,](https://admin.powerplatform.microsoft.com/environments) und erstellen Sie eine neue Umgebung.
2. Beim Erstellen der **neuen Umgebung**wählen Sie für den **Typ,** den Sie&#39;Produktion **aus.**
3. Es ist wichtig, dass Sie eine Datenbank für diese Umgebung erstellen **umschalten?**  -Option auf  **Ja**.
4. Legen Sie  **im Dialogfeld**  Datenbank hinzufügen die Option  **Dynamics 365-Apps aktivieren**  auf  **Ja.**

Sie möchten die maximale Dateigröße von Elementen in Ihrem dataverse erhöhen. Wenn Sie die maximale Dateigröße erhöhen, können Sie größere 3D-Modelle oder Videodateien hochladen, die Sie später in Ihren Anleitungen verwenden. Befolgen Sie eine kurze [Anleitung, um die maximale Größe der Uploaddatei zu ändern.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Abschließend müssen Sie die Lösung installieren [und konfigurieren.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution) Wählen Sie [im Power Platform Admin Center](https://admin.powerplatform.microsoft.com/environments)Ressourcen Dynamics ****   \ &gt; **365-Apps**aus, wählen Sie in der Liste **Dynamics 365-Handbücher** aus, und wählen Sie dann Installieren **aus.**  

Sie müssen [eine Sicherheitsrolle Guides hinzufügen,](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) bevor Sie die Apps verwenden können.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Erstellen eines Testhandbuchs auf Ihrem PC über die Erstellung

Beim Erstellen von Anleitungen starten Sie immer auf Ihrem PC. Erstellen der Schritte, Auswählen von Modellen und Verankern der Anleitung. Anschließend werden Inhalte für Ihr Handbuch später im Erstellungsmodus auf Ihrem HoloLens-Gerät platziert. Für die Zwecke dieses Handbuchs empfehlen wir, eine kurze Testanleitung mit minimalen Schritten und Modellen zu erstellen.

Wenn Sie mit der Erstellung von Anleitungen beginnen möchten, beginnen Sie hier mit der [Erstellungsübersicht](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview). Oder schauen Sie sich dieses kurze Video an, um eine Übersicht über die schnelle Nachverfolgung zu erhalten.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Optional: Kioskmodus

Der Kioskmodus ist ein Modus, in dem ein IT-Administrator die Benutzeroberfläche des Startmenüs so konfiguriert, dass nur eine einzelne App oder eine Auswahl von Apps angezeigt wird. Ein Kiosk kann auch auf bestimmte Benutzer, Gruppen oder auf Geräteebene angewendet werden. und in einigen Fällen bestimmte Benutzer aus dem Kiosk ausschließen, die ihnen weiterhin Zugriff auf das reguläre Startmenü ermöglichen.

Der Kioskmodus verfügt über viele verschiedene Variablen, sowohl in Bereich und Konfigurationen, die festgelegt werden können, als auch Methoden zum Bereitstellen des Kiosks in holoLens. Aufgrund all dieser Variablen bleibt der __ Kioskmodus für diese Anleitung optional und wird nicht erneut durchdacht. Wenn Sie glauben, dass Sie ein Unternehmen haben, das verfügbare Apps auf Benutzer beschränken muss oder mehr erfahren möchten, können Sie die Einrichtung von [HoloLens](https://docs.microsoft.com/hololens/hololens-kiosk)als Kiosk erlernen.

## <a name="optional-wdac"></a>Optional: WDAC

WDAC ermöglicht einem IT-Administrator, seine Geräte so zu konfigurieren, dass das Starten von Apps auf Geräten blockiert wird. Dies ist anders als Methoden zur Geräteeinschränkung, z. B. im Kioskmodus, in dem dem Benutzer eine Benutzeroberfläche angezeigt wird, die die Apps auf dem Gerät ausblendet, aber trotzdem gestartet werden kann. Während WDAC implementiert ist, sind die Apps weiterhin in der Liste Alle Apps sichtbar, aber WDAC verhindert, dass diese Apps und Prozesse vom Gerätebenutzer gestartet werden können.

Weitere Informationen finden Sie unter Verwenden von WDAC und Windows PowerShell, um Apps auf [HoloLens 2-Geräten](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)mit Microsoft Intune zu erlauben oder zu blockieren.

[Windows Defender Application Control – WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Nächster Schritt 
> [!div class="nextstepaction"]
> [Unternehmensverkn nnte Bereitstellung – Bereitstellen](hololens2-corp-connected-deploy.md)