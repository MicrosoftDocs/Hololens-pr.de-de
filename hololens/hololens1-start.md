---
title: Einrichten HoloLens (1. Generation)
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
ms.openlocfilehash: 06b7142be471d0db3f45812654288a33425abd60
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189867"
---
# <a name="set-up-your-hololens-1st-gen"></a>Einrichten von HoloLens (1. Generation)

Wenn Sie Ihr Gerät zum ersten Mal HoloLens, werden Sie durch die Kalibrierung Ihres Geräts, die Einrichtung Ihres Geräts und die Anmeldung geführt.  In diesem Artikel werden die ersten HoloLens -Setups (1. Generation) beschrieben.

Im nächsten Abschnitt erfahren Sie, wie Sie mit der HoloLens arbeiten und mit Hologrammen interagieren können. Informationen zum Überspringen dieses Artikels finden Sie unter [Erste Schritte mit HoloLens (1. Generation)](hololens1-basic-usage.md).

## <a name="before-you-start"></a>Vor der Installation

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes zur Verfügung haben:

**Eine Wi-Fi Verbindung.** Sie müssen Ihre Verbindung mit HoloLens mit einem Wi-Fi Herstellen einer Verbindung herstellen, um sie einrichten zu können. Wenn Sie das erste Mal eine Verbindung herstellen, benötigen Sie ein offenes oder kennwortgeschütztes Netzwerk, das für die Verbindungsherstellung keine Navigation zu einer Website und keine Verwendung von Zertifikaten erfordert. [Erfahren Sie mehr über die von der HoloLens verwendeten Websites](hololens-offline.md).

**Ein Microsoft-Konto oder ein Arbeitskonto.** Sie müssen auch ein Konto Microsoft-Konto (oder ein Arbeitskonto, wenn Ihre Organisation das Gerät besitzt) verwenden, um sich bei HoloLens. Wenn Sie nicht über eine Microsoft-Konto verfügen, wechseln Sie zu [account.microsoft.com](https://account.microsoft.com) und richten sie ein kostenloses Konto ein.

**Ein sicherer, gut beleuchteter Raum ohne Stolperfallen**. [Gesundheits- und Sicherheitsinformationen](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Das optionale Komfortzubehör**, das in der HoloLens-Lieferung enthalten ist, ermöglicht Ihnen die komfortabelste Passform. [Weitere Informationen zu Passform und Komfort](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).

> [!NOTE]
>  
> - Wenn Sie Ihre HoloLens zum ersten Mal verwenden, ist [Cortana](hololens-cortana.md) bereits bereit, Sie zu leiten (obwohl sie erst nach der Einrichtung Ihres Geräts auf Ihre Fragen antworten kann). Sie können Cortana jederzeit in den Einstellungen Cortana deaktivieren.
> - Um zur chinesischen oder japanischen Version von HoloLens zu wechseln, müssen Sie den Build für die Sprache auf einen PC herunterladen und dann auf Ihrem Computer HoloLens. Weitere Informationen finden Sie unter [Installieren lokalisierter Versionen von HoloLens (1. Generation).](hololens1-install-localized.md)

## <a name="start-your-hololens-and-set-up-windows"></a>Starten Sie Ihre Hololens, und richten Sie Windows

Beim ersten Starten ihrer HoloLens ist ihre erste Aufgabe die Einrichtung Windows Holographic auf Ihrem Gerät.

1. Verbinden mit dem Internet (HoloLens sie durch die Auswahl Wi-Fi Netzwerk).

1. Melden Sie sich bei Ihrem Benutzerkonto an. Wählen Sie **zwischen My work or school owns it** und I own it (Mein Arbeitsplatz oder meine Schule besitzt und ich bin **derEntspricht).**
    - Wenn Sie **Mein Arbeits- oder Schulkonto besitzen** auswählen, melden Sie sich mit einem Azure AD an. Wenn Ihr Unternehmen Azure AD Premium verwendet und die automatische MDM-Registrierung konfiguriert hat, wird HoloLens automatisch in MDM registriert. Wenn Ihre Organisation keine Azure AD Premium verwendet, ist die automatische MDM-Registrierung nicht verfügbar, daher müssen Sie HoloLens [geräteverwaltung manuell registrieren.](hololens-enroll-mdm.md#different-ways-to-enroll) Führen Sie die folgenden Schritte aus, um sich zum ersten Mal mit einem Arbeits- oder Schulkonto bei Ihrem Gerät anmelden zu können:
        1. Geben Sie Ihre Unternehmenskontodaten ein.
        1. Akzeptieren Sie die Datenschutzerklärung.
        1. Melden Sie sich mit Ihren Azure AD-Anmeldeinformationen an. Hier werden Sie möglicherweise auf die Anmeldeseite Ihres Unternehmens umgeleitet.
        1. Setzen Sie die Einrichtung des Geräts fort.
    - Wenn Sie I **own it auswählen,** melden Sie sich mithilfe eines Microsoft-Konto. Sobald die Installation abgeschlossen ist, können Sie [HoloLens über die Geräteverwaltung manuell registrieren](hololens-enroll-mdm.md#different-ways-to-enroll).
        1. Geben Sie Ihre Microsoft-Kontoinformationen ein.
        1. Geben Sie das Kennwort ein. Wenn für Ihr Microsoft-Konto [eine Überprüfung in zwei Schritten (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) erforderlich ist, schließen Sie den entsprechenden Prozess ab.

1. Das Gerät legt Ihre Zeitzone basierend auf Informationen fest, die es aus dem netzwerkbasierten Wi-Fi erhält.

## <a name="calibration"></a>Kalibrierung

Nachdem Cortana sich selbst einführen, ist der nächste Einrichtungsschritt die Kalibrierung. Um die beste HoloLens zu erhalten, sollten Sie den Kalibrierungsprozess während des Setups abschließen.

HoloLens (1. Generation) verwendet den Abstand zwischen Ihren Brillen (IPD oder [Interpupillary-Abstand),](https://en.wikipedia.org/wiki/Interpupillary_distance)um Hologramme klar zu machen und einfach zu interagieren. Wenn die IPD nicht korrekt ist, erscheinen Hologramme möglicherweise instabil oder in einem falschen Abstand.

Während der Kalibrierung HoloLens Sie auf, ihren Finger mit einer Reihe von sechs Zielen pro Auge auszurichten. HoloLens verwendet diesen Prozess, um die richtige IPD für Ihre Augen zu setzen. Wenn die Kalibrierung für einen neuen Benutzer aktualisiert oder angepasst werden muss, kann der neue Benutzer die Kalibrierungs-App außerhalb des Setups ausführen.

![IPD-Fingerausrichtungsbildschirm im zweiten Schritt.](./images/ipd-finger-alignment-300px.jpg)

*Der IPD-Fingerausrichtungsbildschirm im zweiten Schritt*

Glückwunsch! Das Setup ist abgeschlossen, und Sie können mit der Verwendung HoloLens.

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Erste Schritte mit HoloLens (1. Generation)](hololens1-basic-usage.md)
