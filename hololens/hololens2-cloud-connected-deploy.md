---
title: 'Bereitstellungshandbuch: Bereitstellung mit cloudbasierter HoloLens 2 im großen Stil mit Remote Assist – Bereitstellen'
description: Erfahren Sie, wie Sie die Registrierung und Remote Assist für HoloLens-Geräte über ein mit der Cloud verbundenes Netzwerk überprüfen.
keywords: HoloLens, Verwaltung, cloudverbunden, Remote Assist, AAD, Azure AD, MDM, Mobile Geräteverwaltung
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
ms.openlocfilehash: 4183bde30673f5147683e16b4d625f73b063c529
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309797"
---
# <a name="deploy---cloud-connected-guide"></a>Bereitstellen – Leitfaden für cloudverknannte Anwendungen

Nachdem Sie nun alles konfiguriert haben, sollten Sie bereit sein, Geräte zu verteilen. Nun sollten Sie das Setup jedoch zunächst überprüfen. Zuerst sollte der Azure AD Join- und MDM-Registrierungsprozess überprüft werden, gefolgt von der Überprüfung, ob ein Remote Assist Aufruf platziert werden kann.

## <a name="enrollment-validation"></a>Überprüfung der Registrierung

Da nun alles ordnungsgemäß für Azure AD und MDM-Registrierung konfiguriert ist, sollte der Rest nun ein Snap sein. Sie&#39;eine Wi-Fi Verbindung und das HoloLens-Gerät sowie eines der zuvor konfigurierten AAD-Benutzerkonten benötigen.

Wenn Ihr Gerät nicht&#39;derzeit nicht im Zustand der Werkseinstellungen ist, ist es jetzt ein guter Zeitpunkt, [um den Schrägstrich des Geräts zu ändern.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Sobald sich Ihr Gerät in OOBE befindet, müssen Sie&#39;mit der Interaktion beginnen und den Eingabeaufforderungen folgen. 
1. Die kritische Eingabeaufforderung wird angezeigt, wenn Sie gefragt **werden, wer diese HoloLens besitzt?** Wählen Sie **Meine Arbeit oder Schule besitzt es** aus, und geben Sie Die Anmeldeinformationen Ihres Azure AD Kontos ein.
1. Wenn die Registrierung erfolgreich ist, werden Sie&#39;aufgefordert, eine PIN einzurichten. Diese PIN ist für diesen Benutzer für dieses Gerät eindeutig. Sie werden auch zur Eingabe von Iris-Scans, Sprachdaten und Telemetrieeinstellungen aufgefordert. Schließlich können Sie&#39;erfahren, wie Sie das Startmenü öffnen und oobe abschließen.
1. Sobald Sie im Mixed Reality Home landen, öffnen Sie die Startmenü mit der **soeben erlernten Startgeste.**
1. Wählen Sie die App **Einstellungen** und dann **System aus.** Die erste Information, die Sie&#39;sehen, ist Ihr Gerätename, der für Ihr HoloLens 2 Gerät &quot; HOLOLENS und &quot; dann eine sechsstellige Zeichenfolge lautet.
1. Notieren Sie sich diesen Namen.

![HoloLens 2 Einstellungen – Informationen](./images/hololens2-settings-about.jpg)

7. Sie können überprüfen, ob Ihr Gerät erfolgreich in der App Azure AD Einstellungen registriert wurde. Wählen **Sie unter** Einstellungen die Option Konten **Auf**  ->  **Arbeits- oder Schulkonto zugreifen aus.** Auf diesem Bildschirm können Sie überprüfen, ob Sie erfolgreich registriert wurden, indem Sie &quot; Connected to _nameofAAD&#39;nameofAAD_ Azure AD. Verbunden durch _IhrenUsernamenameofAAD_ @ .onmicrosoft.com &quot; .


Um zu überprüfen, ob das Gerät Azure AD beigetreten ist, [](https://portal.azure.com/#home)können wir die Azure Active Directory im Azure-Portal Azure Active Directory Geräte alle Geräte überprüfen und den  ->    ->    ->  Gerätenamen durchsuchen. Sie&#39;sehen, dass das Gerät Teil der Azure Active Directory.


![Azure Active Directory – Gerät](./images/aad-enrollment.png)

Als Nächstes&#39;Sie sich beim [Microsoft Endpoint Manager Admin Center anmelden.](https://endpoint.microsoft.com/#home) Melden Sie sich an, **und wählen Sie Geräte** und dann Alle Geräte **aus.** Hier können Sie Ihr HoloLens-Gerät nach&#39;suchen. Sie sollten Ihre HoloLens in Intune sehen können.

![Intune – Gerät](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Remote Assist-Aufrufüberprüfung

Nachdem Sie&#39;sichergestellt haben, dass Ihr Gerät sowohl in Ihrer AAD- als auch mdm-Anwendung registriert ist, ist es&#39;Zeit, einen Testaufruf Remote Assist zu führen. Für diese Überprüfung benötigen&#39;HoloLens-Gerät und einen Windows 10-PC sowie ein zweites Azure AD-Benutzerkonto für den PC.

Bei diesem Überprüfungsschritt wird davon ausgegangen, dass Sie den letzten Überprüfungsschritt bereits abgeschlossen haben und Ihr Gerät registriert ist und sich Azure AD Benutzer auf dem Gerät befindet.


1. Wenn Sie Microsoft Teams noch nicht auf Ihrem PC installiert haben, können Sie [Teams hier herunterladen.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Melden Sie sich bei Teams mit dem Azure AD Benutzerkonto an, das derzeit bei Ihrer HoloLens angemeldet ist. Sobald Sie sich bei Ihrem PC angemeldet haben, können Sie den Anruf empfangen.
3. Entsperren Sie Ihre HoloLens, und melden Sie sich an.
4. Um die Remote Assist-App zu starten, öffnen Sie das **Startmenü,** und wählen Sie **Remote Assist** aus. Remote Assist wird nicht nur als Posteingangs-App gebündelt, sondern auch an das Startmenü der HoloLens 2&#39;angeheftet. Falls sie&#39;nicht an die Startmenü angeheftet ist, öffnen Sie die **liste Alle Apps,** um danach zu suchen.
5. Sobald Remote Assist gestartet wurde, sollte er den Benutzer des Geräts über [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) identifizieren und sich bei der App anmelden.
6. Wählen Sie in der App **Suchen** aus, und suchen Sie auf dem PC nach dem zweiten Benutzer. Wählen Sie den Benutzer aus, um den Aufruf zu starten.
7. Beantworten Sie den Anruf von Ihrem PC aus.

Herzlichen Glückwunsch! Sie&#39;erfolgreich eine Verbindung hergestellt haben und sich bei Ihrem Remote-Hilfeanruf befinden. Stellen Sie sicher, dass Sie bestimmte Remoteunterstützungsfeatures ausprobieren, z. B. mit:

- [Freihandanmerkungen](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Freigeben einer Datei und einer Ansicht in Mixed Reality](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Hilfe in einer anderen HoloLens-App erhalten](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Nächster Schritt

> [!div class="nextstepaction"]
> [Bereitstellung mit Cloudverbindung : Verwalten](hololens2-cloud-connected-maintain.md)