---
title: Einrichten von HoloLens (1. Generation)
description: Erfahren Sie, wie Sie Ihre HoloLens (1. Generation) zum ersten Mal über ein Wi-Fi-Netzwerk mit einem Microsoft-Konto (MSA) oder einem Azure Active Directory-Konto (AAD) einrichten.
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f0ec62e55f15fda6d5a8304ea2bb77039d644b9e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308700"
---
# <a name="set-up-your-hololens-1st-gen"></a>Einrichten ihrer HoloLens (1. Generation)

Wenn Sie Ihre HoloLens zum ersten Mal aktivieren, werden Sie durch die Kalibrierung Ihres Geräts, die Einrichtung Ihres Geräts und die Anmeldung geführt.  In diesem Artikel werden die ersten Start- und Einrichtungserfahrungen von HoloLens (1. Generation) beschrieben.

Im nächsten Abschnitt erfahren Sie, wie Sie mit HoloLens arbeiten und mit Hologrammen interagieren. Informationen zum Überspringen dieses Artikels finden Sie unter [Erste Schritte mit HoloLens (1. Generation).](hololens1-basic-usage.md)

## <a name="before-you-start"></a>Vorbereitung

Bevor Sie beginnen, stellen Sie sicher, dass Folgendes verfügbar ist:

**Eine Wi-Fi Verbindung**. Sie müssen Ihre HoloLens mit einem Wi-Fi verbinden, um sie einrichten zu können. Wenn Sie zum ersten Mal eine Verbindung herstellen, benötigen Sie ein offenes oder kennwortgeschütztes Netzwerk, das keine Navigation zu einer Website oder die Verwendung von Zertifikaten zum Herstellen einer Verbindung erfordert. [Erfahren Sie mehr über die Websites, die HoloLens verwendet.](hololens-offline.md)

**Ein Microsoft-Konto oder ein Arbeitskonto.** Sie müssen auch ein Konto Microsoft-Konto (oder ein Arbeitskonto, wenn Ihre Organisation das Gerät besitzt) verwenden, um sich bei HoloLens anmelden zu können. Wenn Sie nicht über eine Microsoft-Konto verfügen, wechseln Sie zu [account.microsoft.com](https://account.microsoft.com) und richten sie kostenlos ein.

**Ein sicherer, gut erlichterer Raum ohne tripping-bedingte**. [Integritäts- und Sicherheitsinformationen](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Das optionale Komfort-Zubehör,** das in Ihrer HoloLens enthalten ist, um Ihnen die komfortableste Anpassung zu bieten. [Weitere Informationen zu Fit und Komfort.](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)

> [!NOTE]
>  
> - Wenn Sie Ihre HoloLens zum ersten Mal verwenden, ist [Cortana](hololens-cortana.md) bereits aktiviert und kann Sie unterstützen (obwohl sie erst nach der Einrichtung Ihres Geräts auf Ihre Fragen antworten kann). Sie können Cortana jederzeit in den Cortana-Einstellungen deaktivieren.
> - Um zur chinesischen oder japanischen Version von HoloLens zu wechseln, müssen Sie den Build für die Sprache auf einem PC herunterladen und dann auf Ihrer HoloLens installieren. Weitere Informationen finden Sie unter [Installieren lokalisierter Versionen von HoloLens (1. Generation).](hololens1-install-localized.md)

## <a name="start-your-hololens-and-set-up-windows"></a>Starten Sie Ihre Hololens, und richten Sie Windows ein.

Wenn Sie Ihre HoloLens zum ersten Mal starten, besteht Ihre erste Aufgabe darin, Windows Holographic auf Ihrem Gerät einzurichten.

1. Herstellen einer Verbindung mit dem Internet (HoloLens führt Sie zur Auswahl Wi-Fi Netzwerks).

1. Melden Sie sich bei Ihrem Benutzerkonto an. Wählen Sie zwischen **Mein Arbeitsplatz oder meine Schule besitzt es** und ich **besitze es**.
    - Wenn Sie **Meine Arbeit oder Schule** besitzen auswählen, melden Sie sich mit einem Azure AD-Konto an. Wenn Ihre Organisation Azure AD Premium verwendet und die automatische MDM-Registrierung konfiguriert hat, wird HoloLens automatisch bei MDM registriert. Wenn Ihre Organisation Azure AD Premium nicht verwendet, ist die automatische MDM-Registrierung nicht verfügbar. Daher müssen Sie [HoloLens manuell in der Geräteverwaltung registrieren.](hololens-enroll-mdm.md#different-ways-to-enroll) Führen Sie die folgenden Schritte aus, um sich zum ersten Mal mit einem Arbeits- oder Schulkonto bei Ihrem Gerät anzumelden:
        1. Geben Sie Informationen zu Ihrem Organisationskonto ein.
        1. Akzeptieren Sie die Datenschutzerklärung.
        1. Melden Sie sich mit Ihren Azure AD Anmeldeinformationen an. Hier werden Sie möglicherweise auf die Anmeldeseite Ihres Unternehmens umgeleitet.
        1. Fahren Sie mit der Einrichtung des Geräts fort.
    - Wenn Sie **ich besitze** auswählen, melden Sie sich mit einem Microsoft-Konto an. Nach Abschluss des Setups können Sie [HoloLens manuell in der Geräteverwaltung registrieren.](hololens-enroll-mdm.md#different-ways-to-enroll)
        1. Geben Sie Ihre Microsoft-Konto Informationen ein.
        1. Geben Sie das Kennwort ein. Wenn für Ihr Microsoft-Konto [eine Überprüfung in zwei Schritten (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) erforderlich ist, schließen Sie den entsprechenden Prozess ab.

1. Das Gerät legt Ihre Zeitzone basierend auf Informationen fest, die es aus dem Wi-Fi Netzwerk erhält.

## <a name="calibration"></a>Kalibrierung

Nach der Einführung von Cortana ist der nächste Einrichtungsschritt die Kalibrierung. Für eine optimale HoloLens-Erfahrung sollten Sie den Kalibrierungsprozess während des Setups abschließen.

HoloLens (1. Generation) verwendet den Abstand zwischen Ihren Brillen (IPD oder [Interpupillary-Abstand),](https://en.wikipedia.org/wiki/Interpupillary_distance)um Hologramme klar zu machen und einfach zu interagieren. Wenn die IPD nicht korrekt ist, erscheinen Hologramme möglicherweise instabil oder in einem falschen Abstand.

Während der Kalibrierung fordert HoloLens Sie auf, ihren Finger mit einer Reihe von sechs Zielen pro Auge auszurichten. HoloLens verwendet diesen Prozess, um die richtige IPD für Ihre Augen zu setzen. Wenn die Kalibrierung für einen neuen Benutzer aktualisiert oder angepasst werden muss, kann der neue Benutzer die Kalibrierungs-App außerhalb des Setups ausführen.

![IPD-Fingerausrichtungsbildschirm im zweiten Schritt](./images/ipd-finger-alignment-300px.jpg)

*IPD-Fingerausrichtungsbildschirm im zweiten Schritt*

Glückwunsch! Das Setup ist abgeschlossen, und Sie können mit der Verwendung von HoloLens beginnen.

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Erste Schritte mit HoloLens (1. Generation)](hololens1-basic-usage.md)
