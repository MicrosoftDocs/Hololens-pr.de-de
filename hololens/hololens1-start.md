---
title: Einrichten HoloLens (1. Generation)
description: Erfahren Sie, wie Sie Ihre HoloLens (1. Generation) zum ersten Mal über Wi-Fi Netzwerk mit einem Microsoft-Konto (MSA) oder einem Azure Active Directory-Konto (AAD) einrichten.
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
ms.openlocfilehash: 9e09ba1a022428b098392464e5cd2abf84911bd6a86d8e699036b8fc4f91470a
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661865"
---
# <a name="set-up-your-hololens-1st-gen"></a>Einrichten von HoloLens (1. Generation)

Wenn Sie Ihr HoloLens zum ersten Mal aktivieren, werden Sie durch das Kalibrieren Ihres Geräts, das Einrichten Ihres Geräts und das Anmelden geführt.  In diesem Artikel wird die erste Start- und Einrichtungserfahrung HoloLens (1. Generation) beschrieben.

Im nächsten Abschnitt erfahren Sie, wie Sie mit der HoloLens arbeiten und mit Hologrammen interagieren können. Weitere Informationen zu diesem Artikel finden Sie unter [Erste Schritte mit HoloLens (1. Generation).](hololens1-basic-usage.md)

## <a name="before-you-start"></a>Vor der Installation

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes zur Verfügung haben:

**Eine Wi-Fi Verbindung.** Sie müssen Ihre HoloLens mit einem Wi-Fi Netzwerk verbinden, um sie einzurichten. Wenn Sie das erste Mal eine Verbindung herstellen, benötigen Sie ein offenes oder kennwortgeschütztes Netzwerk, das für die Verbindungsherstellung keine Navigation zu einer Website und keine Verwendung von Zertifikaten erfordert. [Erfahren Sie mehr über die von der HoloLens verwendeten Websites](hololens-offline.md).

**Ein Microsoft-Konto oder ein Arbeitskonto.** Sie müssen auch eine Microsoft-Konto (oder ein Arbeitskonto, wenn Ihre Organisation das Gerät besitzt) verwenden, um sich bei HoloLens anzumelden. Wenn Sie nicht über eine Microsoft-Konto verfügen, wechseln Sie zu [account.microsoft.com](https://account.microsoft.com) und richten sie ein kostenloses Konto ein.

**Ein sicherer, gut beleuchteter Raum ohne Stolperfallen**. [Gesundheits- und Sicherheitsinformationen](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Das optionale Komfortzubehör**, das in der HoloLens-Lieferung enthalten ist, ermöglicht Ihnen die komfortabelste Passform. [Weitere Informationen zu Passform und Komfort](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).

> [!NOTE]
>  
> - Wenn Sie Ihr HoloLens zum ersten Mal verwenden, ist [Cortana](hololens-cortana.md) bereits eingeschaltet und bereit, Sie zu leiten (obwohl sie erst nach dem Einrichten Ihres Geräts auf Ihre Fragen antworten kann). Sie können Cortana jederzeit in den Einstellungen Cortana deaktivieren.
> - Um zur chinesischen oder japanischen Version von HoloLens zu wechseln, müssen Sie den Build für die Sprache auf einem PC herunterladen und dann auf Ihrem HoloLens installieren. Weitere Informationen finden Sie unter [Installieren lokalisierter Versionen von HoloLens (1. Generation).](hololens1-install-localized.md)

## <a name="start-your-hololens-and-set-up-windows"></a>Starten Sie Ihre Hololens, und richten Sie Windows

Wenn Sie Ihre HoloLens zum ersten Mal starten, besteht Ihre erste Aufgabe darin, Windows Holographic auf Ihrem Gerät einzurichten.

1. Verbinden in das Internet (HoloLens Sie Wi-Fi Netzwerk auswählen).

1. Melden Sie sich bei Ihrem Benutzerkonto an. Wählen Sie zwischen **"Meine Arbeit" oder "Schule" besitzt sie** und **"Ich besitze sie".**
    - Wenn Sie **Meine Arbeit oder Schule** besitzen auswählen, melden Sie sich mit einem Azure AD-Konto an. Wenn Ihr Unternehmen Azure AD Premium verwendet und die automatische MDM-Registrierung konfiguriert hat, wird HoloLens automatisch in MDM registriert. Wenn Ihre Organisation Azure AD Premium nicht verwendet, ist die automatische MDM-Registrierung nicht verfügbar. Daher müssen Sie [HoloLens manuell bei der Geräteverwaltung registrieren.](hololens-enroll-mdm.md#different-ways-to-enroll) Führen Sie die folgenden Schritte aus, um sich zum ersten Mal mit einem Arbeits- oder Schulkonto bei Ihrem Gerät anzumelden:
        1. Geben Sie Ihre Unternehmenskontodaten ein.
        1. Akzeptieren Sie die Datenschutzerklärung.
        1. Melden Sie sich mit Ihren Azure AD-Anmeldeinformationen an. Hier werden Sie möglicherweise auf die Anmeldeseite Ihres Unternehmens umgeleitet.
        1. Setzen Sie die Einrichtung des Geräts fort.
    - Wenn Sie **ich besitze** auswählen, melden Sie sich mit einem Microsoft-Konto an. Sobald die Installation abgeschlossen ist, können Sie [HoloLens über die Geräteverwaltung manuell registrieren](hololens-enroll-mdm.md#different-ways-to-enroll).
        1. Geben Sie Ihre Microsoft-Kontoinformationen ein.
        1. Geben Sie das Kennwort ein. Wenn für Ihr Microsoft-Konto [eine Überprüfung in zwei Schritten (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) erforderlich ist, schließen Sie den entsprechenden Prozess ab.

1. Das Gerät legt Ihre Zeitzone basierend auf Informationen fest, die es aus dem Wi-Fi Netzwerk erhält.

## <a name="calibration"></a>Kalibrierung

Nachdem Cortana sich selbst vorgestellt hat, ist der nächste Einrichtungsschritt die Kalibrierung. Um die beste HoloLens Zu bieten, sollten Sie den Kalibrierungsprozess während des Setups abschließen.

HoloLens (1. Generation) verwendet den Abstand zwischen Ihren Patienten (IPD oder [Interpupillary distance),](https://en.wikipedia.org/wiki/Interpupillary_distance)um Hologramme klar und einfach zu interagieren. Wenn die IPD nicht richtig ist, sind Hologramme möglicherweise instabil oder in falscher Entfernung.

Während der Kalibrierung werden Sie HoloLens aufgefordert, den Finger an einer Reihe von sechs Zielen pro Auge auszurichten. HoloLens verwendet diesen Prozess, um die richtige IPD für Ihre Augen festzulegen. Wenn die Kalibrierung für einen neuen Benutzer aktualisiert oder angepasst werden muss, kann der neue Benutzer die Kalibrierungs-App außerhalb des Setups ausführen.

![Der IPD-Fingerausrichtungsbildschirm im zweiten Schritt](./images/ipd-finger-alignment-300px.jpg)

*Der IPD-Fingerausrichtungsbildschirm im zweiten Schritt*

Herzlichen Glückwunsch! Das Setup ist abgeschlossen, und Sie können HoloLens verwenden.

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Erste Schritte mit HoloLens (1. Generation)](hololens1-basic-usage.md)
