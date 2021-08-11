---
title: Freigeben Ihrer HoloLens für mehrere Personen
description: Sie können HoloLens so konfigurieren, dass sie von mehreren Azure Active Directory Konten oder von mehreren Benutzern, die ein einzelnes Konto verwenden, freigegeben werden.
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
ms.openlocfilehash: 821ef2d17531226177e508b1428af82012c16406e9fbce3ed1a5617c767adfe8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663073"
---
# <a name="share-your-hololens-with-multiple-people"></a>Freigeben Ihrer HoloLens für mehrere Personen

Es ist üblich, eine HoloLens für viele Personen freizugeben oder eine Reihe von HoloLens Geräten gemeinsam zu nutzen.  In diesem Artikel werden die verschiedenen Möglichkeiten beschrieben, wie Sie ein Gerät freigeben können.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Freigeben für mehrere Personen mit jeweils einem eigenen Konto

**Voraussetzung:** Auf dem HoloLens Gerät muss Windows 10 Version 1803 oder höher ausgeführt werden.  HoloLens (1. Generation) müssen ebenfalls [auf Windows Holographic for Business aktualisiert](hololens-upgrade-enterprise.md)werden.

Wenn sie ihre eigenen Azure Active Directory -Konten (Azure AD) verwenden, können mehrere Benutzer jeweils ihre eigenen Benutzereinstellungen und Benutzerdaten auf dem Gerät beibehalten.

Um sicherzustellen, dass mehrere Personen ihre eigenen Konten in Ihrem HoloLens verwenden können, führen Sie die folgenden Schritte aus, um sie zu konfigurieren:

1. Stellen Sie sicher, dass auf dem Gerät Windows 10 Version 1803 oder höher ausgeführt wird.
   > [!IMPORTANT]
   > Wenn Sie ein HoloLens -Gerät (1. Generation) verwenden, aktualisieren Sie [das Gerät auf Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. Wenn Sie das Gerät einrichten, wählen Sie **Meine Arbeit oder Schule besitzt es** aus, und melden Sie sich mit einem Azure AD-Konto an.
1. Stellen Sie nach Abschluss des Setups sicher, dass die Kontoeinstellungen (**Einstellungen**  >  **Konten**) **andere Benutzer** enthalten.

Um HoloLens verwenden zu können, befolgt jeder Benutzer die folgenden Schritte:

1. Wenn ein anderer Benutzer das Gerät verwendet hat, gehen Sie wie folgt vor:
   - Drücken Sie einmal den Netzschalter, um in den Standbymodus zu wechseln, und drücken Sie dann erneut den Netzschalter, um zum Sperrbildschirm zurückzukehren.
   - HoloLens 2 Benutzer können die Benutzerkachel aus dem Startmenü auswählen, um den aktuellen Benutzer abzu abmelden.

1. Melden Sie sich mit ihren Azure AD-Kontoanmeldeinformationen beim Gerät an.  
    Wenn Sie das Gerät zum ersten Mal verwenden, müssen Sie HoloLens an Ihre eigenen Augen [kalibrieren.](hololens-calibration.md)

Um eine Liste der Gerätebenutzer anzuzeigen oder einen Benutzer vom Gerät zu entfernen, wechseln Sie zu **Einstellungen**  >  **Konten**  >  **Andere Benutzer**.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Freigeben für mehrere Personen, die alle das gleiche Konto verwenden

Mehrere Benutzer können ein HoloLens Gerät auch freigeben, während sie ein einzelnes Benutzerkonto verwenden.

**Wenn ein** neuer Benutzer das Gerät auf HoloLens 2 zum ersten Mal auf den Kopf stellt (während dasselbe Konto angemeldet bleibt), fordert das Gerät den neuen Benutzer auf, die Anzeige schnell zu kalibrieren und zu personalisieren. Das Gerät kann die Kalibrierungsinformationen speichern, damit das Gerät in Zukunft automatisch die Qualität und den Komfort der Anzeige der einzelnen Benutzer optimieren kann. Die Benutzer müssen das Gerät nicht erneut kalibrieren.

**Bei HoloLens (1. Generation)** müssen Benutzer, die ein Konto freigeben, in der Einstellungen-App eine neucalibrieren.  Weitere Informationen zur [Kalibrierung](hololens-calibration.md)finden Sie hier.
