---
title: Bereitstellungshandbuch – Mit Dem Unternehmen verbundene HoloLens 2 mit Dynamics 365-Handbüchern – Bereitstellen
description: Erfahren Sie, wie Sie bereitstellungen von HoloLens 2 Geräten über ein verbundenes Unternehmensnetzwerk mit Dynamics 365-Handbüchern einrichten.
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
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308682"
---
# <a name="deploy---corporate-connected-guide"></a>Bereitstellen – Leitfaden für unternehmensbezogene Verbindungen

Ein wichtiger Bestandteil jeder Bereitstellung ist die Sicherstellung, dass Ihre Bereitstellung ordnungsgemäß eingerichtet ist, bevor Sie sie selbst testen, um eine reibungslose Benutzererfahrung sicherzustellen.

Da wir das Wi-Fi Zertifikat über MDM bereitstellen, müssen wir zunächst HoloLens einrichten und Geräte in einem offenen Wi-Fi Netzwerk oder in einem Netzwerk registrieren, für das das Zertifikat nicht erforderlich ist. Sobald die HoloLens oobe und enrolled abgeschlossen hat, empfängt das Gerät das zuvor konfigurierte Netzwerkzertifikat und lob, und wir können überprüfen, ob beide vom Gerät empfangen wurden.

Anschließend können Sie bestätigen, dass Sie einen Testleitfaden erstellen und betreiben können.

## <a name="enrollment-validation"></a>Überprüfung der Registrierung

Da nun alles ordnungsgemäß für Azure AD und MDM-Registrierung konfiguriert ist, sollte der Rest nun ein Snap sein. Sie benötigen eine Wi-Fi-Verbindung und das HoloLens-Gerät sowie eines der zuvor konfigurierten Azure AD Benutzerkonten.

Wenn Sich Ihr Gerät derzeit nicht im Zustand der Werkseinstellungen befindet, ist es jetzt ein guter Zeitpunkt, [um den Schrägstrich des Geräts zu ändern.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Sobald sich Ihr Gerät in OOBE befindet, müssen Sie mit der Interaktion beginnen und den Eingabeaufforderungen folgen.

2. Stellen Sie eine Verbindung mit einem offenen Wi-Fi-Netzwerk her, für das keine Zertifikate erforderlich sind, um dem WLAN beizutreten. Dadurch kann das Gerät das Zertifikat herunterladen, das nach der ersten Einrichtung auf der Wi-Fi der Organisation verwendet werden soll.

3. Die kritische Eingabeaufforderung wird angezeigt, wenn Sie gefragt **werden, wer diese HoloLens besitzt?** Wählen Sie **My work or school owns it (Meine Arbeit oder Schule besitzt es)** aus, und geben Sie Die Anmeldeinformationen Ihres Azure AD-Kontos ein.

4. Wenn die Registrierung erfolgreich ist, werden Sie aufgefordert, eine PIN einzurichten. Diese PIN ist für diesen Benutzer auf diesem Gerät eindeutig. Außerdem werden Sie zur Eingabe von Iris-Scans, Sprachdaten und Telemetrieeinstellungen aufgefordert, und schließlich erfahren Sie, wie Sie das Startmenü öffnen und die OOBE abschließen.

5. Öffnen Sie nach dem Start Mixed Reality start die Startmenü mithilfe der soeben **gelernten** Startgeste.

6. Wählen Sie die **App Einstellungen** und dann **System aus.** Die erste Information, die Sie sehen, ist Ihr Gerätename, der für Ihr HoloLens 2-Gerät HOLOLENS- gefolgt von einer sechsstelligen &quot; &quot; Zeichenfolge ist.

7. Notieren Sie sich diesen Namen.

    ![HoloLens 2 Der Bildschirm "Einstellungen"](./images/hololens2-settings-about.jpg)

8. Vergewissern Sie sich, dass Ihr Gerät erfolgreich mit dem Azure AD. Es gibt zwei Möglichkeiten:

    1.  Die Einstellungs-App. Wählen **Sie unter** Einstellungen die Option Konten **Auf**  ->  **Arbeits- oder Schulkonto zugreifen aus.** Auf diesem Bildschirm können Sie überprüfen, ob Sie erfolgreich registriert sind, indem Sie &quot; Connected to nameofAAD&#39;nameofAAD Azure AD. Verbunden mit *yourusername@nameofAAD.onmicrosoft.com* . Dadurch wird überprüft, ob Ihr Gerät in Ihre Organisation&#39;und Azure AD.

    1. [Azure-Portal](https://portal.azure.com/#home) Wechseln Sie **zu Azure Active Directory**  ->    ->  **Geräte Alle Geräte,** und suchen Sie den Gerätenamen. Unter Jointyp wird als "Azure AD Join" (Verbunden) gezeigt.
        ![Überprüfen des Jointyps in Azure AD](./images/hololens2-devices-all-devices.png)

9. Vergewissern Sie sich, dass Ihr Gerät bei MDM registriert ist. Es gibt zwei Möglichkeiten:

    1. Wählen **Sie unter** Einstellungen die Option Konten **Auf**  ->  **Arbeits- oder Schulkonto zugreifen aus.** Auf diesem Bildschirm können Sie überprüfen, ob Sie erfolgreich registriert sind, indem Sie &quot; Connected to nameofAAD&#39;nameofAAD Azure AD. Verbunden durch *yourusername@nameofAAD.onmicrosoft.com* . Wählen Sie in diesem Access work or school account (Auf Arbeits- oder Schulkonto zugreifen) die Option &quot; Connected to nameofAAD&#39;s Azure AD aus. Verbunden durch yourusername@nameofAAD.onmicrosoft.com &quot; , und wählen Sie die Schaltfläche **Info** aus.

    1. [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home). Melden Sie sich an, und wählen Sie **Geräte** und dann **Alle Geräte aus.** Hier können Sie den Namen Ihres HoloLens-Geräts&#39;suchen. Ihre HoloLens sollte in Intune aufgeführt sein.

        ![Überprüfen der Verwaltung durch Intune in Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi der Zertifikatüberprüfung

Mittlerweile sollte das Gerät das Wi-Fi Zertifikat erhalten haben. Die einfachste Überprüfung, die Sie durchführen können, besteht darin, eine Verbindung mit der Wi-Fi Verbindung herzustellen, für die Sie das Zertifikat empfangen&#39;. Öffnen Sie die **App Einstellungen,** navigieren Sie zu **&amp; Netzwerk-Internet-WLAN,**  ->   und wählen Sie die WLAN-Verbindung aus. Öffnen Sie nach der Verbindung die Microsoft Edge-App, und bestätigen Sie, dass Sie zu einer Website navigieren können.

Um zu bestätigen, dass Sie das Zertifikat auf dem Gerät erhalten haben, können Sie den [Zertifikat-Manager](https://docs.microsoft.com/hololens/certificate-manager)verwenden.

## <a name="validate-lob-app-install"></a>Überprüfen der Lob-App-Installation

Um den Installationsfortschritt einer verwalteten App anzuzeigen, sehen Sie entweder, ob die App installiert ist, oder überprüfen Sie Einstellungen. Indem Sie eine branchenspezifische App als erforderliche Installation für unsere Gruppe konfigurieren, wird die App nach der Registrierung der HoloLens mit einem Benutzer in der zugewiesenen Gruppe automatisch auf die HoloLens heruntergeladen.

Öffnen Sie die Startmenü, und wählen Sie **Alle Apps** aus. Abhängig von der Anzahl der Apps, über die Sie verfügen, müssen Sie möglicherweise die Schaltflächen nach **oben** oder **nach unten** verwenden.

Um die Installation der App auf dem Gerät zu überprüfen, können Sie dies über  ->  **Einstellungskonten**  ->  **Auf Arbeits- oder Schulkonto zugreifen.** Wählen Sie das Konto und dann die Schaltfläche **Info** aus, und scrollen Sie nach unten, um verschiedene Konfigurationen und Apps anzuzeigen, die von MDM auf das Gerät angewendet werden.

Um die Installation von Intune zu überprüfen, navigieren Sie zur [Seite](https://endpoint.microsoft.com/#home)  ->  **Mem-Portal-Apps** -> Alle Apps   -> *TheNameOfYourApp* Device install status page (Installationsstatusseite des  ->   Mem-Portals).

Weitere Informationen finden Sie [unter Intune App Deployment for HoloLens (Intune-App-Bereitstellung für HoloLens).](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Überprüfen von Dynamics 365-Handbüchern

Es gibt Modi für die Guides-App auf HoloLens, Erstellung und Betrieb. Sie müssen die Erstellung eines Leitfadens beenden, bevor Sie ihn benötigen.

### <a name="authoring-the-guide"></a>Erstellen des Leitfadens

Für diese schnelle Überprüfung ist nicht viel erforderlich. Wählen Sie einfach den Leitfaden aus, den Sie auf Ihrem PC vorbereitet haben. Sie müssen die Anleitung [verankern.](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)Für eine schnelle Überprüfung können Sie einen holografischen Anker verwenden. Anschließend sollten Sie Ihre [Schritte und Modelle platzieren.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation)

>[!NOTE]
> Sie benötigen die **Rolle Erstellung,** um sich am PC anzumelden und auf der HoloLens zu erstellen. Die Rolle Operator ist schreibgeschützt und hat keinen Zugriff auf die PC-App.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Betrieb des Leitfadens

Sobald Ihre Hologramme installiert sind, können Sie den Betrieb Ihres Leitfadens testen. 
- Operatormodus **auswählen**
- Klicken Sie sich durch die Schritte Ihres Leitfadens.

Eine detailliertere Anleitung zum Betrieb eines Leitfadens finden Sie in den folgenden Ressourcen:

[Übersicht über den Betrieb eines Leitfadens in Dynamics 365-Handbüchern](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[Orientieren Sie sich mit der Karte Schritt als Operator in Dynamics 365-Handbüchern.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Nächster Schritt 
> [!div class="nextstepaction"]
> [Bereitstellung im verbundenen Unternehmen – Verwalten](hololens2-corp-connected-maintain.md)
