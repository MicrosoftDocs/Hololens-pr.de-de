---
title: Teilen von HoloLens mit mehreren Personen
description: Sie können HoloLens so konfigurieren, dass es von mehreren Azure Active Directory-Konten oder von mehreren Benutzern, die ein einzelnes Konto verwenden, freigegeben wird.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828421"
---
# Teilen von HoloLens mit mehreren Personen

Es ist üblich, eine HoloLens für viele Personen freizugeben oder viele Personen mit einer Reihe von HoloLens-Geräten zu teilen.  In diesem Artikel werden die verschiedenen Möglichkeiten beschrieben, wie Sie ein Gerät freigeben können.

## Freigeben für mehrere Personen mit jeweils eigenem Konto

**Voraussetzung**: auf dem HoloLens-Gerät muss Windows 10, Version 1803 oder höher, ausgeführt werden.  HoloLens (1st Generation) muss ebenfalls [auf Windows holographisch for Business aktualisiert](hololens-upgrade-enterprise.md)werden.

Wenn Sie eigene Azure Active Directory-Konten (Azure AD) verwenden, können mehrere Benutzer jeweils ihre eigenen Benutzereinstellungen und Benutzerdaten auf dem Gerät behalten.

Führen Sie die folgenden Schritte aus, um sicherzustellen, dass mehrere Personen Ihre eigenen Konten auf Ihrem HoloLens verwenden können:

1. Stellen Sie sicher, dass auf dem Gerät Windows 10, Version 1803 oder höher ausgeführt wird.
   > [!IMPORTANT]
   > Wenn Sie ein HoloLens (1st Generation)-Gerät verwenden, [Aktualisieren Sie das Gerät auf Windows holographisch for Business](hololens1-upgrade-enterprise.md).
1. Wenn Sie das Gerät einrichten, wählen Sie **mein Geschäfts-oder Schul Besitzer** aus, und melden Sie sich mit einem Azure AD-Konto an.
1. Nachdem Sie das Setup abgeschlossen haben, stellen Sie sicher, dass die Kontoeinstellungen (**Einstellungs**  >  **Konten**) **andere Benutzer**umfassen.

Um HoloLens zu verwenden, führt jeder Benutzer die folgenden Schritte aus:

1. Wenn ein anderer Benutzer das Gerät verwendet hat, führen Sie eine der folgenden Aktionen aus:
   - Drücken Sie die Power-Taste einmal, um in den Standbymodus zu wechseln, und drücken Sie dann erneut die Power-Taste, um zum Sperrbildschirm zurückzukehren.
   - HoloLens 2 Benutzer können die Kachel "Benutzer" im Menü "Start" auswählen, um den aktuellen Benutzer abzumelden.

1. Verwenden Sie Ihre Azure AD-Kontoanmeldeinformationen, um sich beim Gerät anzumelden.  
    Wenn Sie das Gerät zum ersten Mal verwenden, müssen Sie HoloLens mit eigenen Augen [Kalibrieren](hololens-calibration.md) .

Wenn Sie eine Liste der Geräte Benutzer anzeigen oder einen Benutzer vom Gerät entfernen möchten, wechseln Sie zu **Einstellungen**für  >  **Accounts**  >  **andere Benutzer**.

## Freigeben für mehrere Personen, die alle dasselbe Konto verwenden

Mehrere Benutzer können auch ein HoloLens-Gerät freigeben, während Sie ein einzelnes Benutzerkonto verwenden.

Wenn ein neuer Benutzer das Gerät zum ersten Mal auf dem Kopf platziert (unter Beibehaltung desselben Kontos), fordert das Gerät den neuen Benutzer **auf HoloLens 2**auf, die Anzeigeumgebung schnell zu kalibrieren und zu personalisieren. Das Gerät kann die Kalibrierungsinformationen speichern, damit das Gerät in Zukunft automatisch die Qualität und den Komfort der Anzeige Erfahrung jedes Benutzers optimieren kann. Die Benutzer müssen das Gerät nicht erneut kalibrieren.

**Bei HoloLens (1st Gen)** müssen Benutzer, die ein Konto freigeben, die erneute Kalibrierung in der Einstellungs-APP anfordern.  Weitere Informationen finden Sie im Artikel [Kalibrieren](hololens-calibration.md).
