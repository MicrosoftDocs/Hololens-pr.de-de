---
title: Einrichten der HoloLens (1. Generation)
description: Hier erfahren Sie, wie Sie HoloLens (1. Generation) zum ersten Mal über ein Wi-Fi-Netzwerk mit einem Microsoft (MSA)- oder einem Azure Active Directory (AAD)-Konto einrichten.
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: aca7b287b3d26ab37ddb90e4245a1e0b3adc17e2
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283926"
---
# Einrichten von HoloLens (1. Generation)

Wenn Sie Ihre HoloLens zum ersten Mal einschalten, werden Sie durch die Kalibrierung Ihres Geräts, die Einrichtung und die Anmeldung geführt.  In diesem Artikel werden die Schritte zum erstmaligen Starten und Einrichten von HoloLens (1. Generation) erläutert.

Im nächsten Abschnitt erfahren Sie, wie Sie mit HoloLens arbeiten und mit Hologrammen interagieren können. Informationen zu diesem Artikel finden Sie unter [Erste Schritte mit HoloLens (1. Generation)](hololens1-basic-usage.md).

## Vorbereitung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes zur Verfügung haben:

**Eine WLAN-Verbindung**. Sie müssen HoloLens zum Einrichten mit einem WLAN-Netzwerk verbinden. Wenn Sie das erste Mal eine Verbindung herstellen, benötigen Sie ein offenes oder kennwortgeschütztes Netzwerk, das für die Verbindungsherstellung keine Navigation zu einer Website oder die Verwendung von Zertifikaten erfordert. [Erfahren Sie mehr über die Websites, die HoloLens verwendet](hololens-offline.md).

**Ein Microsoft-Konto oder ein Geschäftskonto**. Sie müssen auch ein Microsoft-Konto (oder ein Geschäftskonto, wenn Ihre Organisation Besitzer des Geräts ist) verwenden, um sich bei HoloLens anzumelden. Wenn Sie noch kein Microsoft-Konto besitzen, können Sie unter [account.microsoft.com](https://account.microsoft.com) ein kostenloses Konto einrichten.

**Einen sicheren, gut beleuchteten Raum ohne Stolperfallen**. [Informationen zu Gesundheit und Sicherheit](https://go.microsoft.com/fwlink/p/?LinkId=746661).

Das **optionale Komfortzubehör**, das mit Ihrer HoloLens geliefert wurde, bietet Ihnen die bequemste Passform. [Weitere Informationen zu Passform und Komfort](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).

> [!NOTE]
>  
> - Wenn Sie Ihre HoloLens zum ersten Mal verwenden, ist [Cortana](hololens-cortana.md) bereits eingeschaltet und bereit, Sie anzuleiten (obwohl sie Ihre Fragen erst beantworten kann, nachdem Sie Ihr Gerät eingerichtet haben). Sie können Cortana jederzeit in den Cortana-Einstellungen deaktivieren.
> - Um zur chinesischen oder japanischen Version von HoloLens zu wechseln, müssen Sie den Build für die Sprache auf einem PC herunterladen und dann auf Ihrem HoloLens installieren. Weitere Informationen finden Sie unter [Installieren lokalisierter Versionen von HoloLens (1. Generation)](hololens1-install-localized.md).

## Starten Ihrer HoloLens und Einrichten von Windows

Wenn Sie Ihre HoloLens zum ersten Mal starten, müssen Sie auf Ihrem Gerät zunächst Windows Holographic einrichten.

1. Stellen Sie eine Verbindung zum Internet her (HoloLens hilft Ihnen bei der Auswahl des WLAN-Netzwerks).

1. Melden Sie sich bei Ihrem Benutzerkonto an. Wählen Sie entweder [Es gehört] **Meinem Arbeitgeber oder meiner Bildungseinrichtung** oder **Mir** aus.
    - Wenn Sie " **Meinem Arbeitgeber oder Bildungseinrichtung** auswählen, können Sie sich mit einem Azure AD-Konto anmelden. Wenn Ihr Unternehmen Azure AD Premium verwendet und die automatische MDM-Registrierung konfiguriert wurde, wird HoloLens automatisch in MDM registriert. Wenn Ihr Unternehmen kein Azure AD Premium verwendet, ist die automatische MDM-Registrierung nicht verfügbar. In diesem Fall müssen Sie [HoloLens über die Geräteverwaltung manuell registrieren](hololens-enroll-mdm.md#different-ways-to-enroll). Führen Sie die folgenden Schritte aus, um sich bei Ihrem Gerät zum ersten Mal mit einem Geschäfts-oder Schulkonto anzumelden:
        1. Geben Sie Ihre Unternehmenskontodaten ein.
        1. Akzeptieren Sie die Datenschutzbestimmungen.
        1. Melden Sie sich mit Ihren Azure AD-Anmeldeinformationen an. Hier werden Sie möglicherweise auf die Anmeldeseite Ihres Unternehmens umgeleitet.
        1. Setzen Sie die Einrichtung des Geräts fort.
    - Wenn Sie die Option **Mir** auswählen, können Sie sich mit einem Microsoft-Konto anmelden. Nach Abschluss der Installation können Sie [HoloLens manuell in der Geräteverwaltung registrieren](hololens-enroll-mdm.md#different-ways-to-enroll).
        1. Geben Sie Ihre Microsoft-Kontoinformationen ein.
        1. Geben Sie Ihr Kennwort ein. Wenn für Ihr Microsoft-Konto [eine Überprüfung in zwei Schritten (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) erforderlich ist, schließen Sie den entsprechenden Prozess ab.

1. Das Gerät legt Ihre Zeitzone basierend auf den Informationen fest, die es aus dem WLAN-Netzwerk erhält.

## Kalibrierung

Nachdem Cortana sich vorgestellt hat, ist der nächste Einrichtungsschritt die Kalibrierung. Für eine optimale HoloLens-Funktionalität sollten Sie den Kalibrierungsvorgang während des Setups durchführen.

HoloLens (1. Generation) verwendet die Entfernung zwischen Ihren Augen (IPD oder [Interpupillary Distance](https://en.wikipedia.org/wiki/Interpupillary_distance)), damit die Interaktion mit Hologrammen klar und einfach ist. Wenn der IPD nicht korrekt ist, erscheinen Hologramme möglicherweise instabil oder in einem falschen Abstand.

Während der Kalibrierung fordert HoloLens Sie auf, Ihren Finger mit einer Reihe von sechs Zielen pro Auge auszurichten. HoloLens verwendet diesen Vorgang, um den richtigen IPD für Ihre Augen einzurichten. Wenn die Kalibrierung für einen neuen Benutzer aktualisiert oder angepasst werden muss, kann der neue Benutzer die Kalibrierungs-App außerhalb des Setups ausführen.

![IPD-Fingerausrichtungsbildschirm im zweiten Schritt](./images/ipd-finger-alignment-300px.jpg)

*IPD-Fingerausrichtungsbildschirm im zweiten Schritt*

Herzlichen Glückwunsch! Die Einrichtung ist abgeschlossen, und Sie können mit der Verwendung von HoloLens beginnen.

## Nächste Schritte

> [!div class="nextstepaction"]
> [Erste Schritte mit HoloLens (1. Generation)](hololens1-basic-usage.md)
