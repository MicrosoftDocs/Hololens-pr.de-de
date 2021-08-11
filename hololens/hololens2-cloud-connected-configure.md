---
title: Bereitstellungshandbuch – Cloud connected HoloLens 2 deployment at scale with Remote Assist – Configure
description: Erfahren Sie, wie Sie Konfigurationen einrichten, um HoloLens geräte über ein cloudbasiertes Netzwerk im großen Stil mit Remote Assist.
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
ms.openlocfilehash: 8e6999157c6f5a396812df26f748c771581b61d63709918abb2ae45063810ef8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660566"
---
# <a name="configure---cloud-connected-guide"></a>Konfigurieren – Leitfaden für cloudbasierte Verbindung

In diesem Abschnitt des Leitfadens erfahren&#39;, wie Sie die automatische Registrierung für Ihren Mandanten einrichten und Lizenzen sowohl für Intune als auch für Remote Assist.

## <a name="azure-users-and-groups"></a>Azure-Benutzer und -Gruppen

Azure und Intune mit dieser Erweiterung verwenden Benutzer und Gruppen, um Konfigurationen und Lizenzen zuzuweisen. Um diesen Bereitstellungsablauf zu überprüfen und einen Remote Assist benutzeraufrufen zu können, benötigen&#39;zwei Benutzerkonten.

Wir können eine einzelne Benutzergruppe zum Zuweisen von Lizenzen verwenden. Wir können beide Benutzer derselben Gruppe hinzufügen und eine Lizenz für Intune anwenden und Remote Assist gruppe anwenden.

Wenn Sie nicht&#39;haben, haben Sie noch keinen Zugriff auf zwei Azure AD-Konten in einer Benutzergruppe, die Sie verwenden können. Hier finden Sie die Schnellstartanleitungen für:

- [Erstellen eines Benutzers](/mem/intune/fundamentals/quickstart-create-user)
- [Erstellen einer Gruppe](/mem/intune/fundamentals/quickstart-create-group)
- [Hinzufügen von Benutzern zu einer Gruppe:](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) Hinzufügen von erstellten Benutzern zum Erstellen einer Gruppe
- [Konfigurieren Azure AD, um](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) einer Benutzergruppe das Beitreten zu Geräten zu ermöglichen: Stellen Sie sicher, dass eine neue Benutzergruppe über die Berechtigung zum Registrieren von Geräten für Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Automatische Registrierung auf HoloLens 2

Um eine reibungslose und nahtlose Umgebung zu gewährleisten, ist das Einrichten von Azure Active Directory Join (AADJ) und der automatischen Registrierung bei Intune für HoloLens 2-Geräte die erste Möglichkeit. Dadurch können Benutzer ihre Anmeldeinformationen für die Organisation während der OOBE eingeben und sich automatisch bei Azure AD registrieren und das Gerät bei MDM registrieren.

Mithilfe [von Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)können wir Dienste auswählen und zu einigen Seiten navigieren, bis wir auf Get a Premium trial (Testversion Premium können. Möglicherweise bemerken Sie, dass Azure Active Directory Premium 1 und 2 vorhanden sind, da die automatische Registrierung P1 ausreichend ist. Wir können Intune und den Benutzerbereich für die automatische Registrierung auswählen und die Gruppe auswählen, die zuvor erstellt wurde.

Ausführliche Informationen und Schritte finden Sie im Leitfaden zum Aktivieren der [automatischen Registrierung für Intune.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="application-licenses"></a>Anwendungslizenzen

Mit einer Anwendungslizenz kann ein Benutzer entweder vom Unternehmen erworbene Apps installieren oder ein Upgrade von einer kostenlosen Testversion auf die Vollversion einer App durchführen. Anwendungslizenzen können entweder auf Benutzer, Benutzergruppen oder Gerätegruppen angewendet werden. Sie&#39;Lizenzen Remote Assist benutzer in Ihrer Organisation benötigen, um diese zu Remote Assist. Für die Zwecke dieses Leitfadens weisen wir Remote Assist Benutzergruppe zu, die wir oben in [Azure-Benutzer und -Gruppen erstellt haben.](hololens2-cloud-connected-configure.md#azure-users-and-groups)

Die Anforderungen für Lizenzen können unterschiedlich sein, je nachdem, ob der Benutzer den Remote Assist von einem Gerät aus aufruft oder ein Remotemitarbeiter von Microsoft Teams. Standardmäßig sind die Remote Assist und Teams markiert. Für die Zwecke dieses Leitfadens empfehlen wir, die Standardfelder aktiviert zu lassen.

1. Erfahren Sie mehr über die verschiedenen [Lizenzierungs- und Produktanforderungen pro Rolle.](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role) Es gibt verschiedene Arten von Remote Assist, daher sollten Sie sicherstellen, dass Sie die richtigen Lizenzen für Ihre Anforderungen erhalten.
2. Sie&#39;die Lizenz [erwerben müssen.](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
3. [Wenden Sie Ihre Lizenzen](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) auf die Gruppe an.

## <a name="next-step"></a>Nächster Schritt

> [!div class="nextstepaction"]
> [Mit der Cloud verbundene Bereitstellung: Bereitstellen](hololens2-cloud-connected-deploy.md)