---
title: Bereitstellungshandbuch – Cloud Connected HoloLens 2-Bereitstellung im Maßstab mit Remote Unterstützung – bereitstellen
description: Überprüfen der Registrierung und Remote Unterstützung für HoloLens-Geräte über ein in der Cloud verbundenes Netzwerk
keywords: HoloLens, Verwaltung, Cloud Connected, Remote Assist, AAD, Azure AD, MDM, Verwaltung mobiler Geräte
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
ms.openlocfilehash: 2b38f4a76ee088d4f892c86de07d8f5a10d2a3bf
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253192"
---
# Bereitstellen-Cloud Connected Guide

Nachdem Sie nun alles konfiguriert haben, sollten Sie bereit sein, Geräte zu verteilen. Jetzt sollten Sie jedoch zunächst Ihr Setup überprüfen. Zunächst sollte der Azure AD Join-und der MDM-Registrierungsprozess überprüft werden, gefolgt von der Überprüfung, ob ein Remote Unterstützungs Anruf getätigt werden kann.

## Registrierungsüberprüfung

Nachdem alles für die Azure AD-und MDM-Registrierung ordnungsgemäß konfiguriert wurde, sollte der andere jetzt ein Kinderspiel sein. Sie&#39;ll benötigen eine Wi-Fi-Verbindung und das HoloLens-Gerät sowie eines der zuvor konfigurierten Aad-Benutzerkonten.

Wenn Ihr Gerät zurzeit nicht in einem Zustand der factoryeinstellungen sitzt&#39;, wäre es jetzt ein guter Zeitpunkt, um [das Gerät erneut zu blinken](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).

1. Sobald sich das Gerät in OOBE befindet, müssen Sie&#39;mit der Interaktion beginnen und die Eingabeaufforderungen befolgen. 
1. Die kritische Aufforderung wird angezeigt, wenn Sie gefragt werden **, wer der Besitzer dieses HoloLens ist.** Wählen Sie mein Geschäfts- **oder Schul Besitzer** aus, und geben Sie Ihre Azure AD-Kontoanmeldeinformationen ein.
1. Wenn die Registrierung erfolgreich ist, werden Sie aufgefordert, eine PIN einzurichten.&#39; Diese PIN ist auf diesem Gerät für diesen Benutzer eindeutig. Darüber hinaus werden Sie zur Eingabe von Iris-Scans, Sprach Daten und Telemetrie-Einstellungen aufgefordert, und schließlich&#39;Sie erfahren, wie Sie das Startmenü öffnen und oobe komplettieren können.
1. Sobald Sie in der Mixed Reality-Startseite landen, öffnen Sie das Startmenü mit der soeben gelernten **anfangs Geste** .
1. Wählen Sie die APP **Einstellungen** aus, und wählen Sie **System aus.** Der erste Teil der Informationen, die Sie&#39;ll sehen, ist Ihr Gerätename, der für Ihr HoloLens 2 &quot; -Gerät &quot; mit einer sechsstelligen Zeichenfolge HoloLens wird.
1. Notieren Sie sich diesen Namen.

![HoloLens 2-Einstellungen-Info](./images/hololens2-settings-about.jpg)

7. Sie können überprüfen, ob Ihr Gerät erfolgreich in der Azure AD-App in der Einstellungs-APP registriert wurde. Wählen Sie unter **Einstellungen** die Option **Konten**  ->  **Zugriff auf Arbeit oder Schule**aus. Auf diesem Bildschirm können Sie überprüfen, ob Sie erfolgreich registriert sind, indem Sie mit &quot; _nameofAAD_&#39;s Azure AD verbunden sehen. Verbunden durch _yourusername_ @ _nameofAAD_. onmicrosoft.com &quot; .


So überprüfen Sie, ob das Gerät Azure AD beigetreten ist wir können das Azure Active Directory über das Azure- [Portal](https://portal.azure.com/#home)  ->  **Azure Active Directory**-  ->  **Geräte**  ->  **alle Geräte**überprüfen und den Gerätenamen durchsuchen. Sie&#39;ll sehen können, dass das Gerät Teil des Azure Active Directory ist.


![Azure Active Directory-Gerät](./images/aad-enrollment.png)

Als nächstes müssen Sie&#39;sich beim [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home)anmelden. Melden **Sie sich** an, und wählen Sie dann **alle Geräte**aus. Hier können Sie Ihr HoloLens-Gerät&#39;s-Namen durchsuchen. Sie sollten ihre HoloLens-Liste auf InTune sehen können.

![InTune-Gerät](./images/endpoint-all-devices-enrolled.png)

## Überprüfung des Remote Unterstützungs Anrufs

Nachdem Sie&#39;ve überprüft haben, ob Ihr Gerät sowohl in Ihrem Aad als auch in MDM registriert ist,&#39;es Zeit, einen Test-Remote Unterstützungs Anruf zu tätigen. Für diese Überprüfung benötigen Sie&#39;das HoloLens-Gerät und einen Windows 10-PC sowie ein zweites Azure AD-Benutzerkonto für den PC.

Bei diesem Überprüfungsschritt wird davon ausgegangen, dass Sie zuvor den letzten Validierungsschritt abgeschlossen haben und Ihr Gerät registriert ist und Ihr Azure AD-Benutzer auf dem Gerät installiert ist.


1. Wenn Microsoft Teams noch nicht auf Ihrem PC installiert ist, können Sie [Teams hier herunterladen](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).
2. Melden Sie sich bei Teams mit dem zweiten Azure AD-Benutzerkonto an, das derzeit bei Ihrem HoloLens angemeldet ist. Nachdem Sie sich bei Ihrem PC angemeldet haben, können Sie den Anruf entgegennehmen.
3. Entsperren Sie Ihr HoloLens, und registrieren Sie sich.
4. Um die Remote Assist-APP zu starten, öffnen Sie das **Startmenü** , und wählen Sie **Remote-Assistent**aus. Der Remote-Assistent ist nicht nur als Posteingangs-App gebündelt, sondern auch an das HoloLens 2&#39;s-Startmenü angeheftet. In einem Ereignis, das Sie nicht an das Startmenü angeheftet&#39;, öffnen Sie die Liste **alle apps** , um danach zu suchen.
5. Sobald der Remote-Assistent gestartet wurde, sollte er den Benutzer des Geräts über [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) identifizieren und sich bei der App anmelden.
6. Wählen Sie in der APP **Suchen** aus, und suchen Sie nach dem zweiten Benutzer auf dem PC. Wählen Sie den Benutzer aus, um den Anruf zu starten.
7. Nehmen Sie auf Ihrem PC den Anruf entgegen.

Herzlichen Glückwunsch, Sie&#39;ve erfolgreich verbunden und sind auf Ihrem Remote Assist-Anruf. Stellen Sie sicher, dass Sie bestimmte Remote Unterstützungsfunktionen testen, beispielsweise:

- [Freihand-Anmerkungen](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Freigeben einer Datei und einer Ansicht in gemischter Realität](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Abrufen von Hilfe in einer anderen HoloLens-App](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## Nächster Schritt

> [!div class="nextstepaction"]
> [Cloud Connected-Bereitstellung – verwalten](hololens2-cloud-connected-maintain.md)