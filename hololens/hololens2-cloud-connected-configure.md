---
title: 'Bereitstellungshandbuch : Bereitstellung mit cloudbasierter HoloLens 2 im großen Stil mit Remote Assist – Konfigurieren'
description: Erfahren Sie, wie Sie Konfigurationen einrichten, um HoloLens Geräte über ein mit der Cloud verbundenes Netzwerk im großen Stil mit Remote Assist zu registrieren.
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635142"
---
# <a name="configure---cloud-connected-guide"></a>Konfigurieren – Leitfaden für cloudverknannte Verbindungen

In diesem Abschnitt des Leitfadens&#39;wir erfahren, wie Sie die automatische Registrierung für Ihren Mandanten einrichten und Lizenzen sowohl für Intune als auch für Remote Assist anwenden.

## <a name="azure-users-and-groups"></a>Azure-Benutzer und -Gruppen

Azure und Intune von dieser Erweiterung verwenden Benutzer und Gruppen, um Konfigurationen und Lizenzen zuzuweisen. Um diesen Bereitstellungsablauf zu überprüfen und einen Remote Assist Aufruf von einem Benutzer an einen anderen durchführen zu können, benötigen Sie&#39;zwei Benutzerkonten.

Wir können eine einzelne Benutzergruppe erstellen, um Lizenzen zuzuweisen. Wir können beide Benutzer derselben Gruppe beitreten und eine Lizenz für Intune und Remote Assist auf diese Gruppe anwenden.

Wenn Sie&#39;noch keinen Zugriff auf zwei Azure AD Konten in einer Benutzergruppe haben, die Sie verwenden können. Hier sind die Schnellstarthandbücher für Folgendes:

- [Erstellen eines Benutzers](/mem/intune/fundamentals/quickstart-create-user)
- [Erstellen einer Gruppe](/mem/intune/fundamentals/quickstart-create-group)
- [Hinzufügen von Benutzern zu einer Gruppe–](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) Hinzufügen von erstellten Benutzern zum Erstellen einer Gruppe
- [Konfigurieren Azure AD, um einer Benutzergruppe das Beitreten zu Geräten zu ermöglichen:](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) Stellen Sie sicher, dass eine neue Benutzergruppe über die Berechtigung zum Registrieren von Geräten für Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Automatische Registrierung bei HoloLens 2

Um eine reibungslose und nahtlose Benutzeroberfläche zu erhalten, ist das Einrichten von Azure Active Directory Join (AADJ) und der automatischen Registrierung bei Intune für HoloLens 2 Geräte die beste Vorgehensweise. Dadurch können Benutzer ihre Anmeldeinformationen für die Organisation während der OOBE eingeben und sich automatisch bei Azure AD registrieren und das Gerät bei MDM registrieren.

Mit [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)können wir Dienste auswählen und durch einige Seiten navigieren, bis wir Premium Testversion abrufen auswählen können. Möglicherweise stellen Sie fest, dass Azure Active Directory Premium 1 und 2 vorhanden sind, da die automatische Registrierung P1 ausreichend ist. Wir können Intune auswählen, den Benutzerbereich für die automatische Registrierung auswählen und die Gruppe auswählen, die zuvor erstellt wurde.

Ausführliche Informationen und Schritte finden Sie im Leitfaden zum Aktivieren der [automatischen Registrierung für Intune.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="application-licenses"></a>Anwendungslizenzen

Mit einer Anwendungslizenz kann ein Benutzer entweder vom Unternehmen erworbene Apps installieren oder ein Upgrade von einer kostenlosen Testversion auf die Vollversion einer App durchführen. Anwendungslizenzen können entweder auf Benutzer, Benutzergruppen oder Gerätegruppen angewendet werden. Sie&#39;Remote Assist Lizenzen benötigen, damit Benutzer in Ihrer Organisation Remote Assist verwenden können. Für diese Anleitung weisen wir Remote Assist Lizenzen der Benutzergruppe zu, die wir oben in [Azure-Benutzer und -Gruppen](hololens2-cloud-connected-configure.md#azure-users-and-groups)erstellt haben.

Die Anforderungen für Lizenzen können unterschiedlich sein, je nachdem, ob der Benutzer die Remote Assist von einem Gerät aus aufruft oder ein Remotemitarbeiter von Microsoft Teams ist. Standardmäßig sind die Kontrollkästchen Remote Assist und Teams markiert. Für die Zwecke dieses Leitfadens wird empfohlen, die Standardfelder aktiviert zu lassen.

1. Erfahren Sie mehr über die verschiedenen [Lizenzierungs- und Produktanforderungen pro Rolle.](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role) Es gibt einige verschiedene Arten von Remote Assist Lizenzen. Achten Sie daher darauf, die richtigen Lizenzen für Ihre Anforderungen zu erhalten.
2. Sie&#39;die Lizenz [erwerben](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)müssen.
3. [Wenden Sie Ihre Lizenzen](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) auf die Gruppe an.

## <a name="next-step"></a>Nächster Schritt

> [!div class="nextstepaction"]
> [Bereitstellung mit Cloudverbindung – Bereitstellen](hololens2-cloud-connected-deploy.md)