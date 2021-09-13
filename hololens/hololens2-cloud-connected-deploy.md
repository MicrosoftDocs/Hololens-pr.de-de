---
title: 'Bereitstellungshandbuch : Bereitstellung mit cloudbasierter HoloLens 2 im großen Stil mit Remote Assist – Bereitstellen'
description: Erfahren Sie, wie Sie die Registrierung und Remote Assist für HoloLens Geräte über ein mit der Cloud verbundenes Netzwerk überprüfen.
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
ms.openlocfilehash: 519770badab9f260316fe4cfff4bf453a7c971a7
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032741"
---
# <a name="deploy---cloud-connected-guide"></a>Bereitstellen – Leitfaden für cloudverknannte Anwendungen

Nachdem Sie nun alles konfiguriert haben, sollten Sie bereit sein, Geräte zu verteilen. Nun sollten Sie das Setup jedoch zunächst überprüfen. Zuerst sollte der Azure AD Join- und MDM-Registrierungsprozess überprüft werden, gefolgt von der Überprüfung, ob ein Remote Assist Aufruf erfolgen kann.

## <a name="enrollment-validation"></a>Überprüfung der Registrierung

Da nun alles ordnungsgemäß für Azure AD und MDM-Registrierung konfiguriert ist, sollte der Rest nun ein Snap sein. Sie&#39;eine Wi-Fi Verbindung und das HoloLens Gerät sowie eines der zuvor konfigurierten AAD-Benutzerkonten benötigen.

Wenn Ihr Gerät&#39;derzeit nicht im Zustand der Werkseinstellungen ist, wäre jetzt ein guter Zeitpunkt, [um den Schrägstrich des Geräts zu ändern.](/hololens/hololens-recovery#clean-reflash-the-device)

1. Sobald sich Ihr Gerät in OOBE befindet, müssen Sie&#39;mit der Interaktion beginnen und den Eingabeaufforderungen folgen. 
1. Die kritische Eingabeaufforderung wird angezeigt, wenn Sie gefragt **werden Wer diese HoloLens besitzt?** Wählen Sie **My work or school owns it (Meine Arbeit oder Schule besitzt es)** aus, und geben Sie die Anmeldeinformationen Ihres Azure AD-Kontos ein.
1. Wenn die Registrierung erfolgreich ist, werden Sie&#39;aufgefordert, eine PIN einzurichten. Diese PIN ist für diesen Benutzer auf diesem Gerät eindeutig. Sie werden auch zur Eingabe von Iris-Scans, Sprachdaten und Telemetrieeinstellungen aufgefordert. Schließlich können Sie&#39;erfahren, wie Sie das Startmenü öffnen und oobe abschließen.
1. Sobald Sie im Mixed Reality Home landen, öffnen Sie die Startmenü mithilfe der **soeben erlernten Startgeste.**
1. Wählen Sie die **Einstellungen-App** und dann **System aus.** Die erste Information, die Sie&#39;sehen, ist Ihr Gerätename, der für Ihr HoloLens 2 Gerät &quot; HOLOLENS lautet, &quot; gefolgt von einer sechsstelligen Zeichenfolge.
1. Notieren Sie sich diesen Namen.

![HoloLens 2 Einstellungen: Informationen.](./images/hololens2-settings-about.jpg)

7. Sie können überprüfen, ob Ihr Gerät erfolgreich im Azure AD innerhalb der Einstellungen-App registriert wurde. Wählen **Sie Einstellungen** **Konten** Auf  ->  **Arbeits- oder Schulkonto zugreifen** aus. Auf diesem Bildschirm können Sie überprüfen, ob Sie erfolgreich registriert wurden, indem Sie &quot; Connected to _nameofAAD_&#39;s Azure AD (Mit Name verbunden)&#39;sehen. Verbunden durch _Name IhresUsernamensofAAD_ @ .onmicrosoft.com &quot; .


Um zu überprüfen, ob das Gerät Azure AD eingebunden wurde, können wir die Azure Active Directory aus der [Azure-Portal](https://portal.azure.com/#home)Azure Active Directory Geräte Alle Geräte überprüfen  ->    ->    ->  und den Gerätenamen durchsuchen. Sie&#39;sehen können, dass das Gerät Teil der Azure Active Directory ist.


![Azure Active Directory: Gerät.](./images/aad-enrollment.png)

Als Nächstes müssen Sie sich&#39;beim [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home)anmelden. Melden Sie sich an, und wählen Sie **Geräte** und dann **Alle Geräte aus.** Hier können Sie den Namen Ihres HoloLens Geräts&#39;suchen. Ihre HoloLens sollten in Intune aufgeführt sein.

![Intune: Gerät.](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Remote Assist-Aufrufüberprüfung

Nachdem Sie&#39;überprüft haben, ob Ihr Gerät sowohl bei AAD als auch bei MDM registriert ist,&#39;es an der Zeit, einen Test Remote Assist-Aufrufs zu platzieren. Für diese Überprüfung benötigen Sie&#39;das HoloLens Gerät und einen Windows 10 PC sowie ein zweites Azure AD Benutzerkonto für den PC.

Bei diesem Überprüfungsschritt wird davon ausgegangen, dass Sie zuvor den letzten Überprüfungsschritt abgeschlossen haben und Ihr Gerät registriert ist und sich Ihr Azure AD Benutzer auf dem Gerät befindet.


1. Wenn Sie noch nicht Microsoft Teams auf Ihrem PC installiert haben, können Sie [Teams hier herunterladen.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Melden Sie sich mithilfe des zweiten Azure AD Benutzerkontos als das derzeit bei Ihrem HoloLens angemeldete Benutzerkonto bei Teams an. Nach der Anmeldung auf Ihrem PC können Sie den Anruf empfangen.
3. Entsperren Sie Ihre HoloLens, und melden Sie sich an.
4. Um die Remote Assist-App zu starten, öffnen Sie das **Startmenü,** und wählen Sie **Remote Assist** aus. Remote Assist wird nicht nur als Posteingangs-App gebündelt, sondern auch an das Startmenü der HoloLens 2&#39;angeheftet. Falls sie&#39;nicht an die Startmenü angeheftet ist, öffnen Sie dann die **liste Alle Apps,** um danach zu suchen.
5. Sobald Remote Assist gestartet wurde, sollte er den Benutzer des Geräts über [SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) identifizieren und sich bei der App anmelden.
6. Wählen Sie in der App **Suchen** aus, und suchen Sie auf dem PC nach dem zweiten Benutzer. Wählen Sie den Benutzer aus, um den Aufruf zu starten.
7. Beantworten Sie den Anruf von Ihrem PC aus.

Herzlichen Glückwunsch! Sie&#39;erfolgreich eine Verbindung hergestellt haben und sich in Ihrem Remoteassistentenanruf befinden. Stellen Sie sicher, dass Sie bestimmte Remoteunterstützungsfeatures ausprobieren, z. B. mit:

- [Freihandanmerkungen](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Freigeben einer Datei und einer Ansicht in Mixed Reality](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Hilfe in einer anderen HoloLens-App](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Nächster Schritt

> [!div class="nextstepaction"]
> [Bereitstellung mit Cloudverbindung : Verwalten](hololens2-cloud-connected-maintain.md)