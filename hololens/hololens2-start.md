---
title: Einrichten Ihrer HoloLens 2
description: Erfahren Sie, wie Sie HoloLens 2 zum ersten Mal über ein Wi-Fi-Netzwerk mit einem Microsoft (MSA)- oder einem Azure Active Directory (AAD)-Konto einrichten.
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 9824de1d81fd6ba9ccafc8627d660aebefeaed15
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283876"
---
# Einrichten Ihrer HoloLens 2

Wenn Sie Ihre HoloLens zum ersten Mal einschalten, werden Sie durch die Einrichtung Ihres Geräts, die Anmeldung mit einem Benutzerkonto und die Kalibrierung der HoloLens für Ihre Augen geführt.  In diesem Abschnitt werden die ersten Schritte zur Einrichtung der HoloLens 2 erläutert.

Im nächsten Abschnitt erfahren Sie, wie Sie mit HoloLens arbeiten und mit Hologrammen interagieren können. Weitere Informationen zu diesem Artikel finden Sie unter [Erste Schritte mit HoloLens 2](hololens2-basic-usage.md).

## Vorbereitung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes zur Verfügung haben:

**Eine Netzwerkverbindung**. Sie müssen Ihre HoloLens mit einem Netzwerk verbinden, um sie einzurichten. Mit HoloLens 2 können Sie eine Verbindung über WLAN oder über Ethernet herstellen (dazu benötigen Sie einen USB-C-zu-Ethernet-Adapter). Wenn Sie das erste Mal eine Verbindung herstellen, benötigen Sie ein offenes oder kennwortgeschütztes Netzwerk, das für die Verbindungsherstellung keine Navigation zu einer Website oder die Verwendung von Zertifikaten erfordert. [Erfahren Sie mehr über die Websites, die HoloLens verwendet](hololens-offline.md).

**Ein Microsoft-Konto**. Sie müssen sich bei HoloLens mit einem Microsoft-Konto anmelden (oder mit Ihrem Geschäftskonto, wenn Ihr Unternehmen das Gerät besitzt). Wenn Sie noch kein Microsoft-Konto besitzen, können Sie unter [account.microsoft.com](https://account.microsoft.com) ein kostenloses Konto einrichten.

**Einen sicheren, gut beleuchteten Raum ohne Stolperfallen**. [Informationen zu Gesundheit und Sicherheit](https://go.microsoft.com/fwlink/p/?LinkId=746661).

Das **optionale Komfortzubehör**, das mit Ihrer HoloLens geliefert wurde, bietet Ihnen die bequemste Passform. [Weitere Informationen zu Passform und Komfort](hololens2-setup.md#adjust-fit).

## Einrichten von Windows

Wenn Sie HoloLens 2 zum ersten Mal starten, müssen Sie zunächst Windows Holographic einrichten.  Beim Starten Ihrer HoloLens hören Sie Musik und sehen ein Windows-Logo.

![Erster Bildschirm während des ersten Starts](images/01-magic-moment.png)

HoloLens 2 führt Sie durch die folgenden Schritte:

1. Wählen Sie Ihre Sprache aus.
    ![Sprache auswählen](images/04-language.png)

1. Wählen Sie Ihre Region aus.
    ![Region auswählen](images/05-region.png)

1. Kalibrieren Sie HoloLens auf Ihre Augen.  Wenn Sie die Kalibrierung überspringen möchten, werden Sie bei der nächsten Anmeldung dazu aufgefordert.

    Zum Kalibrieren betrachten Sie eine Reihe von Zielen (als Edelsteine bezeichnet). Es ist in Ordnung, wenn Sie während der Kalibrierung blinzeln oder die Augen schließen. Versuchen Sie jedoch, andere Gegenstände im Raum nicht anzustarren. HoloLens verwendet diesen Vorgang, um Ihre Augenposition zu ermitteln und so Ihre holografische Welt besser darstellen zu können. Nach der Kalibrierung werden Hologramme korrekt angezeigt, auch wenn sich das Visier auf Ihrem Kopf verschiebt.

    Kalibrierinformationen werden lokal auf dem Gerät gespeichert und sind nicht mit Kontoinformationen verknüpft. Weitere Informationen finden Sie unter [Kalibrierdaten und Sicherheit](hololens-calibration.md#calibration-data-and-security).

    ![Kalibrierungs-Auswahlbildschirm](images/06-et-corners.png)

1. Stellen Sie eine Verbindung mit dem Internet her (Wählen Sie WLAN oder Ihre Ethernet-Verbindung).
     HoloLens legt Ihre Zeitzone basierend auf den Informationen, die aus dem WLAN-Netzwerk abgerufen werden, automatisch fest. Nachdem das Setup abgeschlossen ist, können Sie die Zeitzone mithilfe der Einstellungs-App ändern.

    ![Herstellen einer WLAN-Verbindung](images/11-network.png)
> [!NOTE] 
> Wenn Sie den WLAN-Schritt auslassen und später zu einem anderen Netzwerk wechseln müssen, während Sie sich noch im Setup befinden, können Sie die Tasten **Leiser** und **Ein/Aus** gleichzeitig drücken, um zu diesem Schritt zurückzukehren, sofern Sie eine Betriebssystemversion von Oktober2019 oder später ausführen. Bei früheren Versionen müssen Sie [das Gerät ggf. zurücksetzen](hololens-recovery.md) oder an einem Ort neu starten, an dem das WLAN-Netzwerk nicht verfügbar ist, um zu verhindern, dass es automatisch eine Verbindung herstellt.
> 
> Beachten Sie außerdem, dass beim HoloLens-Setup für Anmeldeinformationen eine Zeitüberschreitung von zwei Minuten besteht. Der Benutzername/das Kennwort muss innerhalb von zwei Minuten eingegeben werden, andernfalls wird der Wert im Feld „Benutzername“ automatisch gelöscht.

1. Melden Sie sich bei Ihrem Benutzerkonto an. Sie haben die Wahl zwischen [es gehört] **Meinem Arbeitgeber oder meiner Bildungseinrichtung** und **Mir**.
    - Wenn Sie **Meinem Arbeitgeber oder meiner Bildungseinrichtung** gewählt haben, melden Sie sich mit einem Azure AD-Konto an. Wenn Ihre Organisation Azure AD Premium verwendet und die automatische MDM-Registrierung konfiguriert hat, wird HoloLens automatisch in MDM registriert. Wenn in Ihrer Organisation Azure AD Premium nicht verwendet wird, ist die automatische MDM-Registrierung nicht verfügbar. In diesem Fall müssen Sie [HoloLens manuell in der Geräteverwaltung registrieren](hololens-enroll-mdm.md#different-ways-to-enroll).
        1. Geben Sie Ihre Unternehmenskontodaten ein.
        1. Akzeptieren Sie die Datenschutzerklärung und den Endnutzer-Lizenzvertrag.
        1. Melden Sie sich mit Ihren Azure AD-Anmeldeinformationen an. Hier werden Sie möglicherweise auf die Anmeldeseite Ihres Unternehmens umgeleitet.
        1. Setzen Sie die Einrichtung des Geräts fort.
    - Wenn Sie **Mir** ausgewählt haben, melden Sie sich mit einem Microsoft-Konto an. Nach Abschluss der Installation können Sie [HoloLens manuell in der Geräteverwaltung registrieren](hololens-enroll-mdm.md#different-ways-to-enroll).
        1. Geben Sie Ihre Microsoft-Kontoinformationen ein.
        2. Geben Sie Ihr Kennwort ein. Wenn für Ihr Microsoft-Konto [eine Überprüfung in zwei Schritten (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) erforderlich ist, schließen Sie den entsprechenden Prozess ab.

    ![Benutzer einrichten](images/13-device-owner.png)

1. Wählen Sie aus, ob Sprache auf HoloLens 2 aktiviert und Diagnosetelemetrie gesendet werden soll.
    ![Aktivieren von Cortana](images/22-do-more-with-voice.png)

1. Wählen Sie Ihre Telemetrie-Stufe aus. Falls möglich, aktivieren Sie die vollständige Telemetrie. Diese Informationen helfen dem HoloLens-Entwicklungsteam wirklich.
     ![Telemetriestufe](images/24-telemetry.png)

1. Hier erfahren Sie, wie Sie die Startgeste auf HoloLens 2 verwenden.
     ![Erfahren Sie, wie Sie die Startgeste verwenden, Abbildung 1](images/26-01-startmenu-learning.png) ![Erfahren Sie, wie Sie die Startgeste verwenden, Abbildung 2](images/26-02-startmenu-learning.png)

Herzlichen Glückwunsch!  Die Einrichtung ist abgeschlossen, und Sie können HoloLens verwenden!

## Nächste Schritte

> [!div class="nextstepaction"]
> [Erste Schritte mit HoloLens 2](hololens2-basic-usage.md)
