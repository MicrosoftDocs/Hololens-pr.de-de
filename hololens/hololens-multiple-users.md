---
title: Freigeben Ihrer HoloLens für mehrere Personen
description: Sie können HoloLens so konfigurieren, dass sie von mehreren Azure Active Directory oder von mehreren Benutzern gemeinsam genutzt wird, die ein einzelnes Konto verwenden.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308838"
---
# <a name="share-your-hololens-with-multiple-people"></a>Freigeben Ihrer HoloLens für mehrere Personen

Es ist üblich, eine HoloLens für viele Personen zu teilen oder eine Reihe von HoloLens-Geräten gemeinsam zu nutzen.  In diesem Artikel werden die verschiedenen Möglichkeiten beschrieben, wie Sie ein Gerät freigeben können.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Freigeben für mehrere Personen, die jeweils ihr eigenes Konto verwenden

**Voraussetzung:** Auf dem HoloLens-Gerät muss Windows 10 Version 1803 oder höher ausgeführt werden.  HoloLens (1. Generation) muss ebenfalls auf [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

Wenn sie ihre eigenen Azure Active Directory-Konten (Azure AD) verwenden, können mehrere Benutzer jeweils ihre eigenen Benutzereinstellungen und Benutzerdaten auf dem Gerät behalten.

Um sicherzustellen, dass mehrere Personen ihre eigenen Konten auf Ihrer HoloLens verwenden können, führen Sie die folgenden Schritte aus, um sie zu konfigurieren:

1. Stellen Sie sicher, dass auf dem Gerät Windows 10 Version 1803 oder höher ausgeführt wird.
   > [!IMPORTANT]
   > Wenn Sie ein HoloLens-Gerät (1. Generation) verwenden, aktualisieren Sie das Gerät [auf Windows Holographic for Business.](hololens1-upgrade-enterprise.md)
1. Wenn Sie das Gerät eingerichtet haben, wählen Sie **Mein Unternehmen** oder Meine Schule besitzt es aus, und melden Sie sich mit einem Azure AD an.
1. Stellen Sie nach Abschluss des Setupssicher, dass die Kontoeinstellungen (  >  **EinstellungenKonten**) **Andere Benutzer enthalten.**

Um HoloLens zu verwenden, folgt jeder Benutzer den folgenden Schritten:

1. Wenn ein anderer Benutzer das Gerät verwendet hat, führen Sie einen der folgenden Schritte aus:
   - Drücken Sie einmal den Netzschalter, um in den Standbymodus zu wechseln, und drücken Sie dann erneut den Netzschalter, um zum Sperrbildschirm zurückzukehren.
   - HoloLens 2 Benutzer können die Benutzerkachel aus dem Startmenü, um den aktuellen Benutzer abmelden zu können.

1. Verwenden Sie Azure AD Anmeldeinformationen ihres Kontos, um sich beim Gerät anzumelden.  
    Wenn Sie das Gerät zum ersten Mal verwenden, [](hololens-calibration.md) müssen Sie HoloLens auf Ihre eigenen Augen kalibrieren.

Um eine Liste der Gerätebenutzer anzuzeigen oder einen Benutzer vom Gerät zu entfernen, wechseln Sie zu **Einstellungen**  >  **Konten**  >  **Andere Benutzer**.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Freigeben für mehrere Personen, die alle das gleiche Konto verwenden

Mehrere Benutzer können ein HoloLens-Gerät auch freigeben, während sie ein einzelnes Benutzerkonto verwenden.

**Wenn ein** neuer Benutzer das Gerät auf HoloLens 2 zum ersten Mal auf den Kopf stellt (während dasselbe Konto angemeldet bleibt), fordert das Gerät den neuen Benutzer auf, die Anzeige schnell zu kalibrieren und zu personalisieren. Das Gerät kann die Kalibrierungsinformationen speichern, damit das Gerät in Zukunft automatisch die Qualität und den Komfort der Anzeige der einzelnen Benutzer optimieren kann. Die Benutzer müssen das Gerät nicht erneut kalibrieren.

**Auf HoloLens (1. Generation)** müssen Benutzer, die ein Konto freigeben, aufgefordert werden, die Neubibliothek in der Einstellungs-App vorzunehmen.  Weitere Informationen zur [Kalibrierung](hololens-calibration.md)finden Sie hier.
