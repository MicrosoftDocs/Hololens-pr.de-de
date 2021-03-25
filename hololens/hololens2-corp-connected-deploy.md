---
title: Bereitstellungshandbuch – Unternehmensverknte HoloLens 2 mit Dynamics 365-Anleitungen – Bereitstellen
description: Erfahren Sie, wie Sie Bereitstellungen von HoloLens 2-Geräten über ein verbundenes Unternehmensnetzwerk mit Dynamics 365-Anleitungen einrichten.
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
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448559"
---
# <a name="deploy---corporate-connected-guide"></a>Bereitstellen – Unternehmensverknnungshandbuch

Ein wichtiger Teil jeder Bereitstellung ist die Sicherstellung, dass Ihre Bereitstellung ordnungsgemäß eingerichtet ist, bevor Sie sie selbst testen, um eine reibungslose Benutzererfahrung für den Endbenutzer zu gewährleisten.

Da wir das Wi-Fi-Zertifikat über MDM bereitstellen, müssen wir zunächst HoloLens einrichten und Geräte in einem offenen Wi-Fi-Netzwerk oder einem Netzwerk registrieren, für das das Zertifikat nicht erforderlich ist. Sobald holoLens OOBE und Enrolled abgeschlossen hat, erhält das Gerät das Netzwerkzertifikat und die zuvor konfigurierte BRANCHEN, und wir können überprüfen, ob beide vom Gerät empfangen wurden.

Anschließend können Sie bestätigen, dass Sie eine Testanleitung erstellen und betreiben können.

## <a name="enrollment-validation"></a>Registrierungsüberprüfung

Nachdem nun alles ordnungsgemäß für Azure AD- und MDM-Registrierung konfiguriert ist, sollte der Rest jetzt ein Snap sein. Sie benötigen eine Wi-Fi Verbindung und das HoloLens-Gerät sowie eines der zuvor konfigurierten Azure AD-Benutzerkonten.

Wenn Sich Ihr Gerät derzeit nicht im Zustand der Werkseinstellungen befindet, wäre es jetzt ein guter Zeitpunkt, das Gerät neu [zu ändern.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Sobald Sich Ihr Gerät in OOBE befindet, müssen Sie mit der Interaktion beginnen und den Eingabeaufforderungen folgen.

2. Stellen Sie eine Verbindung mit einem Wi-Fi, für das keine Zertifikate zum Beitreten zum WLAN erforderlich sind. Dadurch kann das Gerät das Zertifikat herunterladen, das nach der erst eingerichteten Wi-Fi verwendet werden kann.

3. Die kritische Eingabeaufforderung wird sein, wenn Sie gefragt **werden, wem diese HoloLens gehören?** Wählen Sie Meine Arbeit oder Schule **besitzt, und** geben Sie Ihre Azure AD-Kontoanmeldeinformationen ein.

4. Wenn die Registrierung erfolgreich ist, werden Sie aufgefordert, eine PIN zu erstellen. Diese PIN ist für dieses Gerät für diesen Benutzer eindeutig. Außerdem werden Sie zur Eingabe von Irisscans, Sprachdaten und Telemetrieeinstellungen aufgefordert, und schließlich erfahren Sie, wie Sie das Startmenü öffnen und OOBE abschließen.

5. Sobald Sie im Mixed Reality Home landen, öffnen Sie das Startmenü mit der **Gerade** gelernten Startgeste.

6. Wählen Sie die **Einstellungs-App** aus, und wählen Sie **System aus.** Die erste Information, die Sie sehen werden, ist Ihr Gerätename, der für Ihr HoloLens 2-Gerät HOLOLENS sein wird- gefolgt von einer &quot; &quot; sechsstelligen Zeichenfolge.

7. Notieren Sie sich diesen Namen.

    ![Bildschirm "HoloLens 2-Einstellungen"](./images/hololens2-settings-about.jpg)

8. Stellen Sie sicher, dass Ihr Gerät erfolgreich mit Azure AD verbunden ist. Es gibt zwei Möglichkeiten:

    1.  Die Einstellungs-App. Wählen **Sie unter Einstellungen** die Option ****  ->  **KontenZugriff auf Arbeit oder Schule aus.** Auf diesem Bildschirm können Sie überprüfen, ob Sie erfolgreich registriert sind, indem Sie Verbunden mit &quot; nameofAAD&#39;Azure AD sehen. Verbunden durch *yourusername@nameofAAD.onmicrosoft.com*. Dadurch wird sichergestellt, dass Ihr Gerät ihrer Organisation beigetreten&#39;Azure AD.

    1. Das [Azure-Portal](https://portal.azure.com/#home). Wechseln Sie **zu Azure Active Directory**  ->  **Devices**  ->  **Alle Geräte,** und suchen Sie den Gerätenamen. Unter Join Type wird als "Azure AD Joined" angezeigt.
        ![Überprüfen des Teilnahmetyps in Azure AD](./images/hololens2-devices-all-devices.png)

9. Vergewissern Sie sich, dass Ihr Gerät bei MDM registriert ist. Es gibt zwei Möglichkeiten:

    1. Wählen **Sie unter Einstellungen**die Option ****  ->  **Kontenzugriff auf Arbeit oder Schule aus.** Auf diesem Bildschirm können Sie überprüfen, ob Sie erfolgreich registriert sind, indem Sie Verbunden mit &quot; nameofAAD&#39;Azure AD sehen. Verbunden durch *yourusername@nameofAAD.onmicrosoft.com*. Wählen Sie in diesem Access-Arbeits- oder Schulkonto die Option &quot; Verbunden mit nameofAAD&#39;Azure AD aus. Verbunden durch &quot; yourusername@nameofAAD.onmicrosoft.com, und wählen Sie die **Schaltfläche Info** aus.

    1. [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home). Melden Sie sich an, und wählen Sie **Geräte** und **dann Alle Geräte aus.** Von hier aus können Sie Ihr HoloLens-Gerät nach&#39;Namen durchsuchen. Sie sollten in der Lage sein, Ihre HoloLens auf Intune aufgeführt zu sehen.

        ![Überprüfen der Verwaltung durch Intune in Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi Zertifikatüberprüfung

Bis jetzt sollte das Gerät das Zertifikat Wi-Fi haben. Die einfachste Überprüfung ist der Versuch, eine Verbindung mit der Wi-Fi herzustellen, für die Sie&#39;Zertifikat erhalten haben. Öffnen Sie die **Einstellungs-App,** und navigieren Sie zu WLAN im ** &amp; Netzwerk,**  ->  **** und wählen Sie die WLAN-Verbindung aus. Öffnen Sie nach der Verbindung die Microsoft Edge-App, und bestätigen Sie, dass Sie zu einer Website navigieren können.

Um zu bestätigen, dass Sie das Zertifikat auf dem Gerät erhalten haben, können Sie den [Zertifikat-Manager verwenden.](https://docs.microsoft.com/hololens/certificate-manager)

## <a name="validate-lob-app-install"></a>Überprüfen der Branchen-App-Installation

Um den Installationsfortschritt einer verwalteten App zu sehen, sehen Sie entweder, ob die App installiert ist, oder überprüfen Sie Einstellungen. Durch Konfigurieren einer BRANCHEN-App als erforderliche Installation für unsere Gruppe wird die App nach der Registrierung der HoloLens bei einem Benutzer in der zugewiesenen Gruppe automatisch in die HoloLens heruntergeladen.

Öffnen Sie das Menü Start, und wählen Sie **Alle Apps aus.** Je nach Anzahl der Apps müssen Sie möglicherweise **** die Schaltflächen nach oben oder **unten** verwenden.

Um die Installation der App auf dem Gerät **** zu überprüfen, können Sie dies über Einstellungen Konten Access-Arbeit oder Schule tun. Wählen Sie das Konto und dann die Schaltfläche Info aus, und scrollen Sie nach unten, um verschiedene Konfigurationen und Apps zu sehen, die von MDM auf das Gerät angewendet  ->  ****  ->  **** wurden. ****

Um die Installation von Intune zu überprüfen, navigieren Sie zur Installationsstatusseite des [MEM-Portals](https://endpoint.microsoft.com/#home)  ->  **Apps** -> All **apps**  -> *TheNameOfYourApp*  ->  **Device install.**

Weitere Informationen: [Intune App Deployment for HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Überprüfen von Dynamics 365-Anleitungen

Es gibt Modi für die Guides-App auf HoloLens, Erstellung und Betrieb. Sie müssen die Erstellung eines Leitfadens vor dem Betrieb beenden.

### <a name="authoring-the-guide"></a>Erstellen des Leitfadens

Wir müssen nicht viel für diese schnelle Überprüfung tun. Wählen Sie einfach die Anleitung aus, die Sie auf Ihrem PC vorbereitet haben. Sie müssen die Anleitung [verankern,](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)für eine schnelle Überprüfung können Sie einen holografischen Anker verwenden. Anschließend sollten Sie [ihre Schritte und Modelle platzieren.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation)

>[!NOTE]
> Sie benötigen die Rolle **"Authoring",** um sich auf dem PC und beim Autor auf der HoloLens anzumelden. Die Operatorrolle ist schreibgeschützt und hat keinen Zugriff auf die PC-App.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Bedienung des Leitfadens

Sobald Ihre Hologramme installiert sind, können Sie ihre Anleitung testen. 
- Operatormodus **auswählen**
- Klicken Sie durch die Schritte Ihres Handbuchs.

Ausführliche Anleitungen zum Betrieb eines Leitfadens finden Sie in den folgenden Ressourcen:

[Übersicht über die Bedienung eines Handbuchs in Dynamics 365-Anleitungen](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[Orientieren Sie sich an der Step-Karte als Operator in Dynamics 365-Anleitungen](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Nächster Schritt 
> [!div class="nextstepaction"]
> [Unternehmensverkn nnte Bereitstellung – Verwalten](hololens2-corp-connected-maintain.md)
