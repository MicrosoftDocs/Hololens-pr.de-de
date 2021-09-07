---
title: Einrichten von HoloLens 2
description: Erfahren Sie, wie Sie Ihre HoloLens 2 zum ersten Mal über ein WLAN-Netzwerk mit einem Microsoft (MSA)- oder Active Directory Domain Services-Konto einrichten.
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 8f07ed42c873b62b3b4201c2756b55bbb29707d3
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189765"
---
# <a name="set-up-your-hololens-2"></a>Einrichten von HoloLens 2

Wenn Sie Ihre HoloLens zum ersten Mal einschalten, werden Sie durch die Einrichtung Ihres Geräts geführt, welches die Anmeldung mit einem Benutzerkonto und die Kalibrierung der HoloLens für Ihre Augen beinhaltet.  In diesem Abschnitt werden die ersten Schritte zur Einrichtung der HoloLens 2 erläutert.

Im nächsten Abschnitt erfahren Sie, wie Sie mit der HoloLens arbeiten und mit Hologrammen interagieren können. Um zu diesem Artikel zu gelangen, lesen Sie bitte: [Einstieg in HoloLens 2](hololens2-basic-usage.md).

## <a name="before-you-start"></a>Vor der Installation

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes zur Verfügung haben:

**Eine Netzwerkverbindung**. Sie müssen Ihre HoloLens mit einem Netzwerk verbinden, um sie einzurichten. Mit HoloLens 2 können Sie eine Verbindung über WLAN oder über Ethernet herstellen (dazu benötigen Sie einen USB-C-zu-Ethernet-Adapter). Wenn Sie das erste Mal eine Verbindung herstellen, benötigen Sie ein offenes oder kennwortgeschütztes Netzwerk, das für die Verbindungsherstellung keine Navigation zu einer Website und keine Verwendung von Zertifikaten erfordert. [Erfahren Sie mehr über die von der HoloLens verwendeten Websites](hololens-offline.md).

**Ein Microsoft-Konto**. Sie müssen sich außerdem bei HoloLens mit einem Microsoft-Konto anmelden (oder mit Ihrem Geschäftskonto, wenn Ihr Unternehmen das Gerät besitzt). Wenn Sie nicht über eine Microsoft-Konto verfügen, wechseln Sie zu [account.microsoft.com](https://account.microsoft.com) und richten sie ein kostenloses Konto ein.

**Ein sicherer, gut beleuchteter Raum ohne Stolperfallen**. [Gesundheits- und Sicherheitsinformationen](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Das optionale Komfortzubehör**, das in der HoloLens-Lieferung enthalten ist, ermöglicht Ihnen die komfortabelste Passform. [Weitere Informationen zu Passform und Komfort](hololens2-setup.md#adjust-fit).

## <a name="set-up-windows"></a>Einrichten von Windows

Wenn Sie Ihre HoloLens 2 zum ersten Mal starten, müssen Sie zunächst Windows Holographic einrichten.  Beim Starten Ihrer HoloLens hören Sie Musik und sehen ein Microsoft-Logo.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGGGk]

<br/>
<img src="images/01-magic-moment.png" width="500px" alt="First screen during first boot">

Sie sehen einen umherfliegenden Kolibri.

<img src="images/hummingbird-1.png" width="500px" alt="Hummingbird flying">

Er folgt Ihrer Hand.

<img src="images/hummingbird-2.png" width="500px" alt="Hummingbird flying close up">

Eine Schaltfläche mit einem Microsoft-Logo wird angezeigt. Drücken Sie die Schaltfläche, dann führt HoloLens 2 Sie durch die folgenden Schritte:

1. Wählen Sie Ihre Sprache aus.

    <img src="images/04-language.png" width="500px" alt="Select language">

1. Wählen Sie Ihre Region aus.

    <img src="images/05-region.png" width="500px" alt="Select region">

1. Kalibrieren Sie HoloLens auf Ihre Augen.  Wenn Sie die Kalibrierung überspringen möchten, werden Sie bei Ihrer nächsten Anmeldung dazu aufgefordert. 

    1. Passen Sie zuerst Ihr Visier an.
    
    <img src="images/06-et-corners.png" width="500px" alt="Calibration selection screen">
    
    2. Zum Kalibrieren betrachten Sie eine Reihe von Zielen (als Edelsteine bezeichnet). Es ist in Ordnung, wenn Sie während der Kalibrierung blinzeln oder die Augen schließen. Versuchen Sie jedoch, nicht auf andere Gegenstände im Raum oder auf physischen Raum zu starren. HoloLens verwendet diesen Vorgang, um Ihre Augenposition zu ermitteln, um so Ihre holografische Welt besser darstellen zu können. 

        <img src="images/07-adjust-eyes.png" width="500px" alt="Adjust for your eyes">

        Nach der Kalibrierung werden Hologramme korrekt angezeigt, auch wenn sich das Visier auf Ihrem Kopf verschiebt. Kalibrierinformationen werden lokal auf dem Gerät gespeichert und sind nicht mit Kontoinformationen verknüpft. Weitere Informationen finden Sie unter [Kalibrierungsdaten und Sicherheit](hololens-calibration.md#calibration-data-and-security).

        <img src="images/calibration-complete.png" width="500px" alt="Calibration is complete">

1. Stellen Sie eine Verbindung mit dem Internet her (wählen Sie WLAN oder Ihre Ethernet-Verbindung).

     HoloLens legt Ihre Zeitzone basierend auf den Informationen, die aus dem WLAN-Netzwerk abgerufen werden, automatisch fest. Nachdem das Setup abgeschlossen ist, können Sie die Zeitzone mithilfe der Einstellungen-App ändern.

    ![Herstellen einer WLAN-Verbindung.](images/11-network.png)

    > [!NOTE] 
    > Wenn Sie über den WLAN-Schritt hinausgehen und später zu einem anderen Netzwerk wechseln müssen, während Sie sich noch in der Einrichtung befinden, können Sie die Tasten **Lautstärke senken** und **Ein/Aus** gleichzeitig drücken, um zu diesem Schritt zurückzukehren. Das ist möglich, wenn Sie eine Betriebssystemversion von Oktober 2019 oder später verwenden. Bei früheren Versionen ist es möglicherweise erforderlich, dass Sie das [Gerät zurücksetzen](hololens-recovery.md) oder an einem Ort, an dem das WLAN-Netzwerk nicht verfügbar ist, neu starten, um zu verhindern, dass es sich automatisch verbindet.
    > 
    > Beachten Sie außerdem, dass beim HoloLens-Setup für Anmeldeinformationen eine zeitliche Obergrenze von zwei Minuten besteht. Der Benutzername/das Kennwort muss innerhalb von zwei Minuten eingegeben werden, andernfalls wird der Wert im Feld „Benutzername“ automatisch gelöscht.

1. HoloLens 2 wird nach einem Autopilot-Profil suchen und es anwenden, sofern vorhanden. Auf diesem Bildschirm ist keine Aktion erforderlich.
 
    ![Autopilot-Profilsuche.](images/autopilot-profile-search.png) 

1. Klicken Sie auf dem Bildschirm „Lizenzierung“ **Akzeptieren** an.

    ![Windows-Lizenzvertrag.](images/windows-license-agreement.png)

1. Melden Sie sich bei Ihrem Benutzerkonto an. Sie wählen zwischen **Die Lizenz gehört meinem Arbeitgeber oder meiner Bildungseinrichtung** und **Die Lizenz gehört mir**.

    ![Benutzer festlegen.](images/13-device-owner.png)
    - Wenn Sie **Meinem Arbeitgeber oder meiner Bildungseinrichtung** gewählt haben, melden Sie sich mit dem Azure AD-Konto an. Wenn Ihr Unternehmen Azure AD Premium verwendet und die automatische MDM-Registrierung konfiguriert hat, wird HoloLens automatisch in MDM registriert. Wenn in Ihrer Organisation kein Azure AD Premium verwendet wird, ist die automatische MDM-Registrierung nicht verfügbar. In diesem Fall müssen Sie [HoloLens manuell in der Geräteverwaltung registrieren](hololens-enroll-mdm.md#different-ways-to-enroll).

        1. Geben Sie Ihre Unternehmenskontodaten ein.
        1. Akzeptieren Sie die Datenschutzerklärung und den Endnutzer-Lizenzvereinbarung.
        1. Melden Sie sich mit Ihren Azure AD-Anmeldeinformationen an. Hier werden Sie möglicherweise auf die Anmeldeseite Ihres Unternehmens umgeleitet.
        1. Setzen Sie die Einrichtung des Geräts fort.

    - Wenn Sie **Mir** ausgewählt haben, melden Sie sich mit einem Microsoft-Konto an. Sobald die Installation abgeschlossen ist, können Sie [HoloLens über die Geräteverwaltung manuell registrieren](hololens-enroll-mdm.md#different-ways-to-enroll).

        1. Geben Sie Ihre Microsoft-Kontoinformationen ein.
        2. Geben Sie das Kennwort ein. Wenn für Ihr Microsoft-Konto [eine Überprüfung in zwei Schritten (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) erforderlich ist, schließen Sie den entsprechenden Prozess ab.

        
1. Anmeldung per Iriserkennung einrichten indem Sie **Weiter** auswählen. Sie werden eine ähnliche Vorgehensweise wie bei der Augenkalibrierung anwenden. Wählen Sie **Fertig** aus, wenn der Scan abgeschlossen ist. Sie können auch **Überspringen** auswählen, um diesen Schritt zu umgehen.
    
    <img src="images/setup-iris.png" width="500px" alt="Iris setup">

    <img src="images/iris-setup-complete.png" width="500px" alt="Iris setup completion">

     
  
1. Einrichten einer PIN zur Anmeldung am Gerät. Diese PIN ist gerätespezifisch. 

    ![Einrichten von Windows Hello.](images/setup-windows-hello.png)

    ![Einrichten einer Windows Hello PIN.](images/windows-hello-pin.png)

    ![Einrichten von Windows Hello erfolgreich.](images/windows-hello-successful.png) 

    
1. Wählen Sie, ob Sprache auf der HoloLens 2 aktiviert werden soll.

    <img src="images/22-do-more-with-voice.png" width="500px" alt="Enable Cortana">

1. Wählen Sie aus, ob der Standort auf der HoloLens 2 aktiviert werden soll.
    
    <img src="images/setup-location-services.png" width="500px" alt="Enable location services">

1. Wählen Sie Ihre Telemetrie-Stufe aus. Aktivieren Sie optionale Telemetrie, wenn dies möglich ist. Diese Informationen sind für das HoloLens-Entwicklungsteam wirklich hilfreich.

    <img src="images/24-telemetry.png" width="500px" alt="Telemetry level">


1. Erfahren Sie, wie Sie die Startgeste auf HoloLens 2 verwenden.

    <img src="images/26-01-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 1">

    <img src="images/26-02-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 2">
    
    > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxng]
    
    Herzlichen Glückwunsch!  Die Einrichtung ist abgeschlossen, und Sie können HoloLens verwenden!

## <a name="next-steps"></a>Nächste Schritte

1. Beginnen Sie sofort, mit Mixed Reality zu interagieren und der Navigation in Windows 10 auf Ihrer HoloLens – in der App **Tipps** finden Sie praktische Tutorials für Handinteraktionen. Verwenden Sie die Startgeste, um zum Startmenü zu wechseln. Oder sagen Sie „Zum Startmenü”, und wählen Sie „Tipps“ aus.

1. Klicken Sie unten, um mehr über den Umgang mit HoloLens 2 zu lesen.

> [!div class="nextstepaction"]
> [Immer auf dem richtigen Weg in HoloLens 2](hololens2-basic-usage.md)
