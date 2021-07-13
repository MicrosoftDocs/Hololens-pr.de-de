---
title: Bereitstellungshandbuch – Bereitstellung HoloLens 2 cloudbasierten Bereitstellung im großen Stil mit Remote Assist – Bereitstellen
description: Erfahren Sie, wie Sie die Registrierung und Remote Assist für HoloLens über ein cloudbasiertes Netzwerk überprüfen.
keywords: HoloLens, Verwaltung, cloudgebunden, Remote Assist, AAD, Azure AD, MDM, Mobile Geräteverwaltung
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b0597806d58d7bf16fe6f6c766af3f9662fca7e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635176"
---
# <a name="deploy---cloud-connected-guide"></a>Bereitstellen – Leitfaden für cloudbasierte Bereitstellung

Nachdem Sie nun alles konfiguriert haben, sollten Sie bereit sein, Geräte zu verteilen. Jetzt sollten Sie jedoch zuerst Ihr Setup überprüfen. Zuerst sollten Azure AD Und MDM-Registrierung überprüft werden, und anschließend muss überprüft werden, ob ein Remote Assist platziert werden kann.

## <a name="enrollment-validation"></a>Registrierungsüberprüfung

Nachdem nun alles ordnungsgemäß für Azure AD und MDM-Registrierung konfiguriert ist, sollte der Rest jetzt ein Snap-Programm sein. Sie&#39;benötigen eine Wi-Fi Verbindung und das HoloLens-Gerät sowie eines der zuvor konfigurierten AAD-Benutzerkonten.

Wenn Ihr Gerät nicht&#39;sich derzeit nicht im Zustand "Factoryeinstellungen" befindet, ist jetzt ein guter Zeitpunkt, um das Gerät neu [zu bereinen.](/hololens/hololens-recovery#clean-reflash-the-device)

1. Sobald sich Ihr Gerät in oobe befindet,&#39;sie mit der Interaktion beginnen und den Aufforderungen folgen. 
1. Die kritische Eingabeaufforderung wird angezeigt, wenn Sie gefragt **werden, Wer diese Rolle HoloLens?** Wählen Sie My work or school owns it (Mein Arbeits-, Schul- oder **Schulkonto besitzt)** aus, und geben Sie Azure AD Kontoanmeldeinformationen ein.
1. Wenn die Registrierung erfolgreich ist,&#39;sie aufgefordert, eine PIN zu einrichten. Diese PIN ist für dieses Gerät für diesen Benutzer eindeutig. Sie werden auch zur Eingabe von Iris-Scans, Sprachdaten und Telemetrieeinstellungen aufgefordert, und schließlich können Sie&#39;erfahren, wie Sie das Startmenü öffnen und die OOBE abschließen.
1. Öffnen Sie nach dem Mixed Reality Start die Startmenü mithilfe der soeben **gelernten** Startgeste.
1. Wählen Sie die **Einstellungen-App** und dann **System aus.** Die erste Information, die&#39;angezeigt wird, ist Ihr Gerätename, der für Ihr HoloLens 2-Gerät HOLOLENS- gefolgt von einer sechsstelligen Zeichenfolge &quot; &quot; ist.
1. Notieren Sie sich diesen Namen.

![HoloLens 2 Einstellungen – Informationen](./images/hololens2-settings-about.jpg)

7. Sie können überprüfen, ob Ihr Gerät erfolgreich in der Azure AD in der Einstellungen registriert wurde. Wählen **Einstellungen** Konten **Auf**  ->  **Arbeits- oder Schulkonto zugreifen aus.** Auf diesem Bildschirm können Sie überprüfen, ob Sie erfolgreich registriert wurden, indem Sie &quot; Connected to _nameofAAD&#39;nameofAAD_ Azure AD. Verbunden durch _IhrenUsernamenameofAAD_ @ .onmicrosoft.com &quot; .


Um zu überprüfen, ob das Gerät Azure AD beigetreten ist, [](https://portal.azure.com/#home)können wir die Azure Active Directory im Azure-Portal Azure Active Directory Geräte alle Geräte überprüfen und den  ->    ->    ->  Gerätenamen durchsuchen. Sie&#39;sehen, dass das Gerät Teil der Azure Active Directory.


![Azure Active Directory – Gerät](./images/aad-enrollment.png)

Als Nächstes&#39;Sie sich beim Microsoft Endpoint Manager [Admin Center anmelden.](https://endpoint.microsoft.com/#home) Melden Sie sich an, **und wählen Sie Geräte** und dann Alle Geräte **aus.** Hier können Sie ihren Gerätenamen HoloLens&#39;suchen. Ihr Konto sollte in Intune HoloLens werden.

![Intune – Gerät](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Remote Assist-Aufrufüberprüfung

Nachdem Sie&#39;sichergestellt haben, dass Ihr Gerät sowohl in Ihrer AAD- als auch mdm-Anwendung registriert ist, ist es&#39;Zeit, einen Testaufruf Remote Assist zu führen. Für diese Überprüfung benötigen&#39;das HoloLens-Gerät und einen Windows 10-PC sowie ein zweites Azure AD-Benutzerkonto für den PC.

Bei diesem Überprüfungsschritt wird davon ausgegangen, dass Sie den letzten Überprüfungsschritt bereits abgeschlossen haben und Ihr Gerät registriert ist und sich Azure AD Benutzer auf dem Gerät befindet.


1. Wenn Sie noch keine Installation Microsoft Teams pc installiert haben, können Sie diese [Teams herunterladen.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Melden Sie Teams mit dem zweiten Benutzerkonto Azure AD, das derzeit bei Ihrem Konto angemeldet ist, HoloLens. Nachdem Sie sich bei Ihrem PC angemeldet haben, können Sie den Anruf empfangen.
3. Entsperren Sie HoloLens, und melden Sie sich an.
4. Öffnen Sie zum Starten Remote Assist-App das **Startmenü, und** wählen Sie **Remote Assist.** Remote Assist wird nicht nur als Posteingangs-App gebündelt, sondern auch an HoloLens 2&#39;Startmenü des Pakets angeheftet. In einem Fall wird&#39;nicht an den Startmenü angeheftet, und öffnen  Sie dann die liste Alle Apps, um danach zu suchen.
5. Sobald Remote Assist gestartet wird, sollte der Benutzer des Geräts über [SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) identifiziert und sich bei der App anmelden.
6. Wählen Sie in der App Suchen aus, **und** suchen Sie nach dem zweiten Benutzer auf dem PC. Wählen Sie den Benutzer aus, um den Aufruf zu starten.
7. Beantworten Sie auf Ihrem PC den Anruf.

Herzlichen Glückwunsch! Sie&#39;erfolgreich verbunden haben und sich in Ihrem Remoteunterstützungsaufruf befinden. Stellen Sie sicher, dass Sie bestimmte Remoteunterstützungsfeatures ausprobieren, z. B. mit:

- [Inking-Anmerkungen](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Freigeben einer Datei und Ansicht in Mixed Reality](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Hilfe in einer anderen HoloLens-App](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Nächster Schritt

> [!div class="nextstepaction"]
> [Cloud connected deployment - Maintain](hololens2-cloud-connected-maintain.md)