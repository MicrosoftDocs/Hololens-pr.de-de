---
title: Bereitstellungshandbuch – Mit der Cloud verbundene HoloLens 2-Bereitstellung im großen Maßstab mit Remote Assist – Bereitstellen
description: Erfahren Sie, wie Sie die Registrierung und Remote Assist für HoloLens-Geräte über ein mit der Cloud verbundenes Netzwerk überprüfen.
keywords: HoloLens, Verwaltung, mit der Cloud verbunden, Remote Assist, AAD, Azure AD, MDM, Verwaltung mobiler Geräte
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11282936"
---
# Bereitstellen – Mit der Cloud verbundene Anleitung

Nachdem Sie nun alles konfiguriert haben, sollten Sie bereit sein, Geräte zu verteilen. Jetzt sollten Sie das Setup jedoch zuerst überprüfen. Zunächst sollten der Azure AD-Beitritts- und der MDM-Registrierungsprozess überprüft werden, gefolgt von der Überprüfung, ob ein Remote assist-Anruf ausgeführt werden kann.

## Registrierungsüberprüfung

Da nun alles ordnungsgemäß für Azure AD und die MDM-Registrierung konfiguriert ist, sollte der Rest jetzt ein Snap sein. Sie&#39;eine Wi-Fi und das HoloLens-Gerät sowie eines der zuvor konfigurierten AAD-Benutzerkonten benötigen.

Wenn ihr Gerät nicht&#39;sich derzeit nicht in einem Zustand der Werkseinstellungen befindet, wäre es jetzt ein guter Zeitpunkt, den Schrägstrich für [das Gerät zu ändern.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Sobald sich Ihr Gerät in der OOBE befindet,&#39;sie mit der Interaktion beginnen und den Eingabeaufforderungen folgen. 
1. Die kritische Eingabeaufforderung wird angezeigt, wenn Sie gefragt **werden, wem diese HoloLens gehören?** Wählen **Sie "Meine Arbeit oder Schule" aus, und** geben Sie Ihre Azure AD-Kontoanmeldeinformationen ein.
1. Wenn die Registrierung erfolgreich ist,&#39;zum Einrichten einer PIN aufgefordert. Diese PIN ist für dieses Gerät für diesen Benutzer eindeutig. Außerdem werden Sie zur Eingabe von Irisscans, Sprachdaten und Telemetrieeinstellungen aufgefordert, und schließlich&#39;Erfahren Sie, wie Sie das Startmenü öffnen und die OOBE abschließen.
1. Sobald Sie im Mixed Reality Home landen, öffnen Sie das Startmenü mit der **Gerade** gelernten Startgeste.
1. Wählen Sie die **App "Einstellungen"** und dann **"System" aus.** Die erste Information, die Ihnen&#39;wird, ist Ihr Gerätename, der für Ihr HoloLens 2-Gerät HOLOLENS ist, gefolgt von einer sechsstelligen &quot; &quot; Zeichenfolge.
1. Notieren Sie sich diesen Namen.

![HoloLens 2-Einstellungen – Informationen](./images/hololens2-settings-about.jpg)

7. Sie können in der App "Einstellungen" überprüfen, ob Ihr Gerät erfolgreich bei Azure AD registriert wurde. Wählen **Sie unter "Einstellungen"** **die Option "Kontenzugriff**auf  ->  **Arbeits- oder Schulkonto" aus.** Auf diesem Bildschirm können Sie überprüfen, ob Sie erfolgreich registriert sind, indem Sie "Verbunden mit &quot; _nameofAAD"_&#39;Azure AD anzeigen. Verbunden durch _ihren_ @ _NamennameofAAD_.onmicrosoft.com &quot; .


Um zu überprüfen, ob das Gerät Azure AD [](https://portal.azure.com/#home)beigetreten ist, können wir das Azure Active Directory aus dem Azure-Portal Azure Active Directory Devices All devices überprüfen und  ->  ****  ->  ****  ->  **** den Gerätenamen durchsuchen. Sie&#39;sehen, dass das Gerät Teil von Azure Active Directory ist.


![Azure Active Directory – Gerät](./images/aad-enrollment.png)

Als Nächstes&#39;müssen Sie sich beim [Microsoft Endpoint Manager Admin Center anmelden.](https://endpoint.microsoft.com/#home) Melden Sie sich an, und wählen **Sie "Geräte"** und dann **"Alle Geräte" aus.** Von hier aus können Sie Ihr HoloLens-Gerät&#39;Namen durchsuchen. Sie sollten in der Lage sein, Ihre HoloLens in Intune aufgeführt zu sehen.

![Intune – Gerät](./images/endpoint-all-devices-enrolled.png)

## Remote Assist Call Validation

Nachdem Sie&#39;, dass Ihr Gerät sowohl in AAD als auch in MDM registriert ist, ist es&#39;Zeit, einen Remote assist-Testanruf zu senden. Für diese Überprüfung benötigen&#39;das HoloLens-Gerät und einen Windows 10-PC sowie ein zweites Azure AD-Benutzerkonto für den PC.

Bei diesem Überprüfungsschritt wird davon ausgegangen, dass Sie den letzten Überprüfungsschritt bereits abgeschlossen haben und Ihr Gerät registriert ist und sich Ihr Azure AD-Benutzer auf dem Gerät befindet.


1. Wenn Sie Microsoft Teams noch nicht auf Ihrem PC installiert haben, können Sie [Teams hier herunterladen.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Melden Sie sich mit dem zweiten Azure AD-Benutzerkonto, das derzeit bei Ihrer HoloLens angemeldet ist, bei Teams an. Sobald Sie sich bei Ihrem PC angemeldet haben, können Sie den Anruf empfangen.
3. Entsperren Sie Ihre HoloLens, und melden Sie sich an.
4. Öffnen Sie zum Starten der Remote Assist-App **das Startmenü,** und wählen Sie **Remote assist aus.** Remote Assist ist nicht nur als Posteingangs-App gebündelt, sondern auch an das HoloLens 2-&#39;Startmenü angeheftet. In einem Fall,&#39;sie nicht an das Startmenü angeheftet **** wird, öffnen Sie die Liste "Alle Apps", um danach zu suchen.
5. Sobald Remote Assist gestartet wird, sollte er den Benutzer des Geräts über [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) identifizieren und sich bei der App anmelden.
6. Wählen Sie in **** der App "Suchen" aus, und suchen Sie auf dem PC nach dem zweiten Benutzer. Wählen Sie den Benutzer aus, um den Anruf zu starten.
7. Beantworten Sie den Anruf von Ihrem PC aus.

Herzlichen Glückwunsch, sie&#39;erfolgreich verbunden haben und sich an Ihrem Remote-Assist-Anruf befinden. Testen Sie bestimmte Remoteunterstützungsfeatures, z. B.:

- [Anmerkungen zur Beschriftung](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Freigeben einer Datei und Ansicht in Mixed Reality](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Hilfe in einer anderen HoloLens-App erhalten](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## Nächster Schritt

> [!div class="nextstepaction"]
> [Mit der Cloud verbundene Bereitstellung – Verwalten](hololens2-cloud-connected-maintain.md)