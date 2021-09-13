---
title: Freigeben Ihrer HoloLens für mehrere Personen
description: Sie können die HoloLens, die von mehreren Azure Active Directory oder von mehreren Benutzern, die ein einzelnes Konto verwenden, gemeinsam genutzt werden.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3acd2665e93e44bce2c5dad467c825dc768bfed
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032909"
---
# <a name="share-your-hololens-with-multiple-people"></a>Freigeben Ihrer HoloLens für mehrere Personen

## <a name="overview"></a>Übersicht
Unternehmen investieren häufig in viele gemeinsam genutzte HoloLens Geräte. Die Verwendung HoloLens ist je nach Ihren individuellen Anforderungen flexibel. Hier ist ein Beispiel für einige Benutzererfahrungen: 

- Geräte, die in Rechnung gestellt werden und über Dynamics 365 Guides verfügen und ihren Mitarbeitern ermöglichen, die Einstellungen-App zu öffnen, um Anpassungen an Wi-Fi erforderlich vorzunehmen. Die Richtlinie für die Sichtbarkeit von Seite Einstellungen ist jedoch aktiviert, um die Anzahl der in der Einstellungen-App verfügbaren Seiten zu begrenzen.
- Geräte, die für Remote Assist sind, und Ihre Line-of-Business-App, die an andere Unternehmen geverleiht werden. Diese Geräte verfügen über Kioske, die nur Ihre App und Ihre Remote Assist. WDAC wird verwendet, um den Start Einstellungen App Microsoft Edge zu halten. Im Lieferumfang des Verleihs ist ein USB-C-Akkupaket enthalten, um die Geräte über mehrere Schichten zum vollen Preis zu halten.
- Alle Ihre Geräte sind für Autopilot eingerichtet und laden alle Ihre Unternehmens-Apps herunter. Sie haben einige verschiedene Kioskprofile eingerichtet, die auf verschiedene Azure AD abzielen. Jeder Benutzer meldet sich mithilfe HoloLens FIDO2-Schlüsseln bei der Anwendung an und meldet sich bei seinem Azure AD-Konto an und bietet eine maßgeschneiderte Benutzeroberfläche.



## <a name="share-with-multiple-people-each-using-their-own-account"></a>Freigeben für mehrere Personen, die jeweils ihr eigenes Konto verwenden

**Voraussetzung:** Auf HoloLens Gerät muss Windows 10 Version 1803 oder höher ausgeführt werden.  HoloLens (1. Generation) muss ebenfalls ein Upgrade auf [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

Wenn sie ihre eigenen Azure Active Directory -Konten (Azure AD) verwenden, können mehrere Benutzer ihre eigenen Benutzereinstellungen und Benutzerdaten auf dem Gerät behalten.

Führen Sie die folgenden Schritte aus, um sicherzustellen, dass mehrere Personen ihre eigenen Konten in Ihrer HoloLens verwenden können:

1. Stellen Sie sicher, dass auf dem Gerät Windows 10 Version 1803 oder höher ausgeführt wird.
   > [!IMPORTANT]
   > Wenn Sie ein HoloLens (1. Generation) verwenden, aktualisieren Sie das Gerät [auf Windows Holographic for Business.](hololens1-upgrade-enterprise.md)
1. Wenn Sie das Gerät eingerichtet haben, wählen Sie **Mein Unternehmen** oder Meine Schule besitzt es aus, und melden Sie sich mit einem Azure AD an.
1. Stellen Sie nach Abschluss des Setups sicher, dass die Kontoeinstellungen (**Einstellungen**  >  **Konten**) **Andere Benutzer enthalten.**

Um die HoloLens verwenden zu können, folgt jeder Benutzer den folgenden Schritten:

1. Wenn ein anderer Benutzer das Gerät verwendet hat, wählen Sie eine der folgenden Optionen aus:
   - Drücken Sie einmal den Netzschalter, um in den Standbymodus zu wechseln, und drücken Sie dann erneut den Netzschalter, um zum Sperrbildschirm zurückzukehren.
   - HoloLens 2 Benutzer können die Benutzerkachel aus dem Startmenü, um den aktuellen Benutzer abmelden zu können.

1. Verwenden Sie Azure AD Anmeldeinformationen ihres Kontos, um sich beim Gerät anzumelden.  
    Wenn Sie das Gerät zum ersten Mal verwenden, [](hololens-calibration.md) müssen Sie die HoloLens ihren eigenen Augen kalibrieren.

Wenn Sie eine Liste der Gerätebenutzer anzeigen oder einen Benutzer vom Gerät entfernen möchten, wechseln Sie zu Einstellungen  >  **Konten**  >  **Andere Benutzer.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Freigeben für mehrere Personen, die alle das gleiche Konto verwenden

Mehrere Benutzer können auch ein gerät HoloLens, während sie ein einzelnes Benutzerkonto verwenden.

**Wenn HoloLens 2** ein neuer Benutzer das Gerät zum ersten Mal auf den Kopf legt (während dasselbe Konto angemeldet ist), fordert das Gerät den neuen Benutzer auf, die Anzeigeerfahrung schnell zu kalibrieren und zu personalisieren. Das Gerät kann die Kalibrierungsinformationen speichern, damit das Gerät in Zukunft automatisch die Qualität und den Komfort der Anzeigeerfahrung jedes Benutzers optimieren kann. Die Benutzer müssen das Gerät nicht erneut kalibrieren.

**Auf HoloLens (1. Generation)** müssen Benutzer, die ein Konto freigeben, in der App Einstellungen erneut erstellen.  Erfahren Sie mehr über die [Kalibrierung](hololens-calibration.md)von .