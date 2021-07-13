---
title: Bereitstellungshandbuch – Unternehmens verbundene HoloLens 2 mit Dynamics 365 Guides – Bereitstellen
description: Erfahren Sie, wie Sie Bereitstellungen von HoloLens 2 über ein verbundenes Unternehmensnetzwerk mit Dynamics 365 Guides.
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
ms.openlocfilehash: 6407517bca9efd02fdaf45a78cba7a215ec05670
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637063"
---
# <a name="deploy---corporate-connected-guide"></a>Bereitstellen – Leitfaden für verbundene Unternehmen

Ein wichtiger Teil jeder Bereitstellung besteht in der Sicherstellung, dass Ihre Bereitstellung ordnungsgemäß eingerichtet ist, bevor Sie sie selbst testen, um eine reibungslose Benutzererfahrung zu gewährleisten.

Da wir das Wi-Fi-Zertifikat über MDM bereitstellen, müssen wir zunächst HoloLens einrichten und Geräte in einem offenen Wi-Fi-Netzwerk oder einem Netzwerk registrieren, für das das Zertifikat nicht erforderlich ist. Nachdem die HoloLens oobe und enrolled abgeschlossen haben, erhält das Gerät das Netzwerkzertifikat und die zuvor konfigurierte LOB, und wir können überprüfen, ob beide vom Gerät empfangen wurden.

Anschließend können Sie bestätigen, dass Sie einen Testleitfaden erstellen und betreiben können.

## <a name="enrollment-validation"></a>Registrierungsüberprüfung

Nachdem nun alles ordnungsgemäß für Azure AD und MDM-Registrierung konfiguriert ist, sollte der Rest jetzt ein Snap-Programm sein. Sie benötigen eine Wi-Fi Verbindung und das HoloLens-Gerät sowie eines der zuvor konfigurierten Azure AD Benutzerkonten.

Wenn sich Ihr Gerät derzeit nicht im Zustand "Factoryeinstellungen" befindet, ist jetzt ein guter Zeitpunkt, um das Gerät neu [zu bereinen.](/hololens/hololens-recovery#clean-reflash-the-device)

1. Sobald sich Ihr Gerät in oobe befindet, müssen Sie mit der Interaktion beginnen und den Anweisungen folgen.

2. Verbinden in ein offenes Wi-Fi netzwerk, für das keine Zertifikate erforderlich sind, um dem WLAN beitreten zu können. Auf diese Weise kann das Gerät das Zertifikat herunterladen, das nach der erst eingerichteten Einrichtung auf dem Wi-Fi der Organisation verwendet werden soll.

3. Die kritische Eingabeaufforderung wird angezeigt, wenn Sie gefragt **werden, Wer diese Rolle HoloLens?** Wählen Sie My work or school owns it (Mein Arbeits-, Schul- oder **Schulkonto besitzt)** aus, und geben Sie Azure AD Kontoanmeldeinformationen ein.

4. Wenn die Registrierung erfolgreich ist, werden Sie aufgefordert, eine PIN zu einrichten. Diese PIN ist für dieses Gerät für diesen Benutzer eindeutig. Außerdem werden Sie zur Eingabe von Iris-Scans, Sprachdaten und Telemetrieeinstellungen aufgefordert, und schließlich erfahren Sie, wie Sie das Startmenü öffnen und die OOBE abschließen.

5. Öffnen Sie nach dem Öffnen Mixed Reality Start die Startmenü mithilfe der soeben **gelernten** Startgeste.

6. Wählen Sie die **Einstellungen-App** und dann **System aus.** Die erste Information, die Sie sehen, ist Ihr Gerätename, der für Ihr HoloLens 2-Gerät HOLOLENS- gefolgt von einer sechsstelligen &quot; &quot; Zeichenfolge ist.

7. Notieren Sie sich diesen Namen.

    ![HoloLens 2 Einstellungen-Bildschirm](./images/hololens2-settings-about.jpg)

8. Vergewissern Sie sich, dass Ihr Gerät erfolgreich mit dem Azure AD. Es gibt zwei Möglichkeiten:

    1.  Die Einstellungen-App. Wählen **Einstellungen** Konten **Auf**  ->  **Arbeits- oder Schulkonto zugreifen aus.** Auf diesem Bildschirm können Sie überprüfen, ob Sie erfolgreich registriert sind, indem Sie &quot; Connected to nameofAAD&#39;nameofAAD Azure AD. Verbunden mit *yourusername@nameofAAD.onmicrosoft.com* . Dadurch wird überprüft, ob Ihr Gerät in Ihre Organisation&#39;und Azure AD.

    1. [Azure-Portal](https://portal.azure.com/#home) Wechseln Sie **zu Azure Active Directory**  ->  **Geräte**  ->  **Alle Geräte,** und suchen Sie den Gerätenamen. Unter Jointyp wird als "Azure AD Join" (Verbunden) gezeigt.
        ![Überprüfen des Jointyps in Azure AD](./images/hololens2-devices-all-devices.png)

9. Vergewissern Sie sich, dass Ihr Gerät bei MDM registriert ist. Es gibt zwei Möglichkeiten:

    1. Wählen **Einstellungen** **kontenZugriff auf**  ->  **Arbeits- oder Schulkonto aus.** Auf diesem Bildschirm können Sie überprüfen, ob Sie erfolgreich registriert sind, indem Sie &quot; Connected to nameofAAD&#39;nameofAAD Azure AD. Verbunden mit *yourusername@nameofAAD.onmicrosoft.com* . Wählen Sie in diesem Konto auf Arbeits- oder Schulkonto zugreifen aus, indem Sie mit nameofAAD verbunden&#39;&quot; die Azure AD. Verbunden über yourusername@nameofAAD.onmicrosoft.com &quot; , und wählen Sie die **Schaltfläche Info** aus.

    1. [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home). Melden Sie sich an, **und wählen Sie Geräte** und dann Alle Geräte **aus.** Von hier aus können Sie Den Namen HoloLens Geräts&#39;durchsuchen. Ihr Konto sollte in Intune HoloLens werden.

        ![Überprüfen der Verwaltung durch Intune in Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi Zertifikatüberprüfung

Das Gerät sollte nun das Zertifikat Wi-Fi erhalten haben. Die einfachste Überprüfung, die Sie durchführen können, ist der Versuch, eine Verbindung mit der Wi-Fi-Verbindung herzustellen, für&#39;sie das Zertifikat erhalten haben. Öffnen Sie  die Einstellungen-App, navigieren Sie zu **&amp; Netzwerk-Internet-WLAN,** und  ->   wählen Sie die WLAN-Verbindung aus. Öffnen Sie nach der Verbindung die Microsoft Edge-App, und vergewissern Sie sich, dass Sie zu einer Website navigieren können.

Um zu bestätigen, dass Sie das Zertifikat auf dem Gerät erhalten haben, können Sie den [Zertifikat-Manager verwenden.](/hololens/certificate-manager)

## <a name="validate-lob-app-install"></a>Überprüfen der Lob-App-Installation

Um den Installationsfortschritt einer verwalteten App zu sehen, sehen Sie entweder, ob die App installiert ist, oder überprüfen Einstellungen. Wenn Sie eine BRANCHEN-App als erforderliche Installation für unsere Gruppe konfigurieren, wird die App nach der Registrierung der HoloLens bei einem Benutzer in der zugewiesenen Gruppe automatisch in die HoloLens.

Öffnen Sie die Startmenü, und wählen Sie **Alle Apps.** Abhängig von der Anzahl der Apps, über die Sie verfügen, müssen Sie möglicherweise die Schaltflächen "Seite **nach oben"** oder **"Nach unten"** verwenden.

Um die Installation der App auf dem Gerät zu überprüfen, können Sie dies über **Einstellungen-KontenZugriff** auf Geschäfts-, Schul- oder Schulkonto durchführen. Wählen Sie das Konto und dann die Schaltfläche Info aus, und scrollen Sie nach unten, um verschiedene Konfigurationen und Apps zu sehen, die von MDM auf das Gerät angewendet  ->    ->  werden. 

Um die Installation von Intune zu überprüfen, navigieren Sie zur [Seite](https://endpoint.microsoft.com/#home)  ->  **Mem-Portal-Apps** -> Alle Apps   -> *TheNameOfYourApp* Device install status page (Installationsstatusseite des  ->   Mem-Portals).

Weitere Informationen finden Sie [unter Intune App Deployment for HoloLens](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Überprüfen Dynamics 365 Guides

Es gibt Modi für die Guides-App HoloLens, Erstellung und Betrieb. Sie müssen die Erstellung eines Leitfadens beenden, bevor Sie ihn benötigen.

### <a name="authoring-the-guide"></a>Erstellen des Leitfadens

Für diese schnelle Überprüfung ist nicht viel erforderlich. Wählen Sie einfach den Leitfaden aus, den Sie auf Ihrem PC vorbereitet haben. Sie müssen die Anleitung [verankern.](/dynamics365/mixed-reality/guides/hololens-app-anchor)Für eine schnelle Überprüfung können Sie einen holografischen Anker verwenden. Anschließend sollten Sie Ihre [Schritte und Modelle platzieren.](/dynamics365/mixed-reality/guides/hololens-app-orientation)

>[!NOTE]
> Sie benötigen die **Rolle Erstellung,** um sich am PC anzumelden und auf dem Computer HoloLens. Die Rolle Operator ist schreibgeschützt und hat keinen Zugriff auf die PC-App.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Betrieb des Leitfadens

Sobald Ihre Hologramme installiert sind, können Sie den Betrieb Ihres Leitfadens testen. 
- Operatormodus **auswählen**
- Klicken Sie sich durch die Schritte Ihres Leitfadens.

Eine detailliertere Anleitung zum Betrieb eines Leitfadens finden Sie in den folgenden Ressourcen:

[Übersicht über den Betrieb eines Leitfadens in Dynamics 365 Guides](/dynamics365/mixed-reality/guides/operator-overview)

[Orientieren Sie sich mit der Karte Schritt als Operator in Dynamics 365 Guides](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Nächster Schritt 
> [!div class="nextstepaction"]
> [Bereitstellung im verbundenen Unternehmen – Verwalten](hololens2-corp-connected-maintain.md)
