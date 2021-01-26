---
title: Bereitstellungshandbuch – Mit der Cloud verbundene HoloLens 2-Bereitstellung im großen Maßstab mit Remote Assist – Konfigurieren
description: Erfahren Sie, wie Sie Konfigurationen für die Registrierung von HoloLens-Geräten über ein cloudverbundenes Netzwerk im großen Maßstab mit Remote Assist einrichten.
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
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283886"
---
# Konfigurieren – Leitfaden mit Verbindung mit der Cloud

In diesem Abschnitt des Handbuchs erfahren&#39;, wie Sie die automatische Registrierung für Ihren Mandanten einrichten und wie Sie Lizenzen für Intune und Remote Assist anwenden.

## Benutzer und Gruppen in Azure

Azure und Intune durch diese Erweiterung verwenden Benutzer und Gruppen, um Konfigurationen und Lizenzen zuzuordnen. Um diesen Bereitstellungsfluss zu überprüfen und einen Remote assist-Anruf von einem Benutzer zu einem anderen zu machen, benötigen&#39;zwei Benutzerkonten.

Wir können eine einzelne Benutzergruppe zum Zuweisen von Lizenzen erstellen. Wir können beide Benutzer derselben Gruppe hinzufügen und eine Lizenz für Intune und Remote Assist auf diese Gruppe anwenden.

Wenn Sie&#39;noch nicht über Zugriff auf zwei Azure #A0 in einer Benutzergruppe verfügen, können Sie diese verwenden. Hier sind die Schnellstarthandbücher für:

- [Erstellen eines Benutzers](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Erstellen einer Gruppe](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Hinzufügen von Benutzern zu einer Gruppe –](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) Hinzufügen erstellter Benutzer zum Erstellen einer Gruppe
- [Konfigurieren von Azure AD, um](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) einer Benutzergruppe den Beitritt zu Geräten zu ermöglichen – Stellen Sie sicher, dass die neue Benutzergruppe über die Berechtigung zum Registrieren von Geräten bei Azure AD verfügt.

## Automatische Registrierung auf HoloLens 2

Um eine reibungslose und nahtlose Erfahrung zu bieten, sind das Einrichten von Azure Active Directory Join (AADJ) und die automatische Registrierung bei Intune für HoloLens 2-Geräte die erste Möglichkeit. Dadurch können Benutzer ihre Anmeldeinformationen für die Organisation während der OOBE eingeben und sich automatisch bei Azure AD registrieren und das Gerät bei MDM registrieren.

Mithilfe von [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)können wir Dienste auswählen und einige Seiten navigieren, bis wir eine Premium-Testversion auswählen können. You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient. Wir können Intune und den Benutzerbereich für die automatische Registrierung auswählen und die zuvor erstellte Gruppe auswählen.

Ausführliche Informationen und Schritte finden Sie in der Anleitung [zum Aktivieren der automatischen Registrierung für Intune.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## Anwendungslizenzen

Mit einer Anwendungslizenz kann ein Benutzer entweder vom Unternehmen erworbene Apps installieren oder ein Upgrade von einer kostenlosen Testversion auf die Vollversion einer App durchführen. Anwendungslizenzen können auf Benutzer, Benutzergruppen oder Gerätegruppen angewendet werden. Sie&#39;Remote Assist-Lizenzen für Benutzer in Ihrer Organisation benötigen, um Remote Assist verwenden zu können. Für den Zweck dieses Leitfadens weisen wir der Benutzergruppe, die wir oben in Azure Users and Groups erstellt haben, Remote [assist-Lizenzen zu.](hololens2-cloud-connected-configure.md#azure-users-and-groups)

Die Anforderungen für Lizenzen können unterschiedlich sein, je nachdem, ob der Benutzer den Remote -Assist-Anruf von einem Gerät aus macht oder ein Remotemitarbeiter von Microsoft Teams ist. Standardmäßig sind die Kontrollkästchen "Remote Assist" und "Teams" beide gekennzeichnet. Im Sinne dieses Leitfadens empfehlen wir, die Standardfelder aktiviert zu lassen.

1. Erfahren Sie mehr über die verschiedenen [Lizenzierungs- und Produktanforderungen pro Rolle.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role) Es gibt einige verschiedene Arten von Remote Assist-Lizenzen. Stellen Sie daher sicher, dass Sie die richtigen Lizenzen für Ihre Anforderungen erhalten.
2. Sie&#39;müssen die [Lizenz erwerben.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
3. [Wenden Sie Ihre Lizenzen](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) auf die Gruppe an.

## Nächster Schritt

> [!div class="nextstepaction"]
> [Mit der Cloud verbundene Bereitstellung – Bereitstellen](hololens2-cloud-connected-deploy.md)