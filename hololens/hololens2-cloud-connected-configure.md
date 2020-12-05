---
title: Bereitstellungshandbuch – Cloud Connected HoloLens 2-Bereitstellung im Maßstab mit Remote Unterstützung – konfigurieren
description: Einrichten von Konfigurationen für die Registrierung von HoloLens-Geräten über ein in der Cloud verbundenes Netzwerk
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
ms.openlocfilehash: 43b9db96a2c29d1e3a798d0c695ab6edaa8199ac
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196309"
---
# Konfigurieren-Cloud Connected-Leitfaden

In diesem Abschnitt des Leitfadens&#39;wir, wie Sie die automatische Registrierung für Ihren Mandanten einrichten und wie Sie Lizenzen für InTune und Remote Assist anwenden.

## Azure-Benutzer und-Gruppen

Azure und InTune von dieser Erweiterung verwenden Benutzer und Gruppen, um die Zuweisung von Konfigurationen und Lizenzen zu unterstützen. Um diesen Bereitstellungs Fluss zu überprüfen und einen Remote Unterstützungs Anruf von einem Benutzer zu einem anderen durchführen zu können, benötigen Sie&#39;2 Benutzerkonten.

Wir können eine einzelne Benutzergruppe zum Zweck der Zuweisung von Lizenzen erstellen. Wir können beiden Benutzern dieselbe Gruppe hinzufügen und eine Lizenz für InTune und Remote Unterstützung für diese Gruppe anwenden.

Wenn Sie Don&#39;t bereits Zugriff auf zwei Aad-Konten in einer Benutzergruppe haben, die Sie verwenden können; Im folgenden finden Sie die Schnellstart Handbücher für:

- [Erstellen eines Benutzers](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Erstellen einer Gruppe](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Hinzufügen von Benutzern zu einer Gruppe](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Hinzufügen von erstellten Benutzern zum Erstellen einer Gruppe
- [Konfigurieren von Aad, um einer Benutzergruppe die Teilnahme an Geräten zu ermöglichen](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – stellen Sie sicher, dass die neue Benutzergruppe die Berechtigung zum Registrieren von Geräten für Aad hat.

## Automatische Registrierung auf HoloLens 2

Um eine reibungslose und nahtlose Benutzeroberfläche zu haben, ist das Einrichten von Azure Active Directory Join (AADJ) und der automatischen Registrierung für InTune für HoloLens 2-Geräte die richtige Lösung. Dadurch können Benutzer ihre Anmeldeinformationen für Ihre Organisation einfach während OOBE eingeben und sich automatisch bei Aad registrieren und das Gerät in MDM registrieren.

Mithilfe von [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home) können wir Dienste auswählen und auf einigen Seiten navigieren, bis wir eine Premium-Testversion auswählen können. Sie werden feststellen, dass es Azure Active Directory Premium 1 und 2 gibt, für die automatische Registrierung P1 genügt. Wir können InTune auswählen und den Benutzerbereich für die automatische Registrierung auswählen und die zuvor erstellte Gruppe auswählen.

Ausführliche Informationen und Schritte finden Sie im Leitfaden zum [Aktivieren der automatischen Registrierung für InTune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).

## Anwendungslizenzen

Eine Anwendungslizenz ermöglicht es einem Benutzer, entweder von Unternehmen erworbene apps zu installieren oder von einer kostenlosen Testversion auf die Vollversion einer APP zu aktualisieren. Anwendungslizenzen können entweder auf Benutzer, Benutzergruppen oder Gerätegruppen angewendet werden. Sie&#39;ll benötigen Remote Assist-Lizenzen für Benutzer in Ihrer Organisation, um die Remoteunterstützung verwenden zu können. In diesem Leitfaden weisen wir der Benutzergruppe, die wir oben in [Azure-Benutzern und-Gruppen](hololens2-cloud-connected-configure.md#azure-users-and-groups)erstellt haben, Remote Unterstützungs Lizenzen zu.

Die Anforderungen für Lizenzen können unterschiedlich sein, je nachdem, ob der Benutzer den Remote Unterstützungs Anruf von einem Gerät aus durchführt oder ein Remotemitarbeiter von Microsoft Teams ist. Standardmäßig sind die Kontrollkästchen "Remote Assist" und "Teams" beide markiert. Für die Zwecke dieses Leitfadens empfehlen wir, die Standardfelder aktiviert zu lassen.

1. Weitere Informationen zu den unterschiedlichen [Lizenzierungs-und Produktanforderungen pro Rolle](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role). Es gibt ein paar verschiedene Arten von Lizenzen für Remote-Unterstützung, um sicherzustellen, dass Sie die richtigen für Ihre Anforderungen erhalten.
2. Sie müssen&#39;[die Lizenz erwerben](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).
3. [Wenden Sie Ihre Lizenzen](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) auf die Gruppe an.

## Nächster Schritt

> [!div class="nextstepaction"]
> [Cloud Connected-Bereitstellung – bereitstellen](hololens2-cloud-connected-deploy.md)