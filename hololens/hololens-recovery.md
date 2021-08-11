---
title: Neustarten, Zurücksetzen oder Wiederherstellen von HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Verwenden von Advanced Recovery Companion (ARC), um einen Flash eines Images in HoloLens 2 auszuführen.
keywords: 'Anleitung für: Neustart, Zurücksetzen, Wiederherstellen, Kaltstart, Warmstart, Energiezyklus, HoloLens, Herunterfahren, ARC, Advanced Recovery Companion'
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: 7d8f2f8bf6aaaeb7f6f0ddbd339d428dad9335faeb99bfca48a19e68929921ed
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662971"
---
# <a name="restart-reset-or-recover-hololens-2"></a>Neustarten, Zurücksetzen oder Wiederherstellen von HoloLens 2

>[!IMPORTANT]
> Bevor Sie eine Problembehandlung starten, stellen Sie sicher, dass Ihr Gerät wenn möglich auf **20 bis 40 Prozent** der Akkukapazität aufgeladen wurde. Die [Akkukontrollleuchten](hololens2-setup.md#lights-that-indicate-the-battery-level) unter dem Netzschalter sind eine schnelle Möglichkeit, die Akkukapazität zu überprüfen, ohne sich beim Gerät anzumelden.

Verwenden Sie das [Ladegerät und das USB Type-C-Kabel](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1), das mit der HoloLens 2 geliefert wurde, da dies die beste Möglichkeit zum Laden Ihres Geräts ist. Das Ladegerät liefert 18 W (9 V bei 2 A). Mit dem mitgelieferten Wandladegerät können HoloLens 2-Geräte den Akku in weniger als 65 Minuten voll aufladen, wenn sich das Gerät im Standby-Modus befindet. Wenn das Zubehör nicht verfügbar ist, vergewissern Sie sich, dass das verfügbare Ladegerät mindestens 15 W Leistung unterstützen kann.

> [!NOTE]
> Vermeiden Sie nach Möglichkeit die Verwendung eines PCs, um das Gerät über USB zu laden, was sehr langsam ist.

Wenn das Gerät korrekt hochgefahren ist und läuft, gibt es drei verschiedene Möglichkeiten, den Akkustand zu überprüfen:

- Über das Hauptmenü der Benutzeroberfläche des HoloLens-Geräts.
- Sehen Sie sich die LEDs in der Nähe des Netzschalters an (bei 40 % Akkustand sollten mindestens zwei LEDs leuchten).
    - Während des Ladevorgangs leuchtet die Akkuanzeige auf, um den aktuellen Ladezustand anzuzeigen.  Die letzte Anzeige leuchtet auf und erlischt, um den aktiven Ladevorgang anzuzeigen.
    - Wenn Ihre HoloLens eingeschaltet ist, zeigt die Akkuanzeige den Akkustand in fünf Stufen an.
    - Wenn nur eine der fünf LEDs leuchtet, ist der Akkustand unter 20 %.
    - Wenn der Akkuladestand kritisch niedrig ist und Sie versuchen, das Gerät einzuschalten, blinkt eine LED kurz und erlischt anschließend.
- Öffnen Sie auf Ihrem Host-PC den **Datei-Explorer** und suchen Sie auf der linken Seite unter **Dieser PC** nach Ihrem HoloLens 2 Gerät. Klicken Sie mit der rechten Maustaste auf das Gerät und wählen Sie **Eigenschaften** aus. Ein Dialogfeld mit dem Akkustand wird angezeigt.

   ![Ein Bildschirm mit den HoloLens 2-Eigenschaften zeigt den Akkustand.](images/ResetRecovery2.png)

Wenn das Gerät nicht ins Startmenü hochfahren kann, beachten Sie die LED-Darstellung und die Geräteaufzählung auf dem Host-PC. Befolgen Sie dann die [Anleitung zur Problembehandlung](hololens-troubleshooting.md). Falls der Zustand des Geräts mit keinem der im Handbuch zur Fehlerbehebung aufgeführten Zustände übereinstimmt, führen Sie einen [Kaltstart](hololens-recovery.md#hard-reset-procedure) durch, wobei das Gerät nicht mit Ihrem Host-PC, sondern mit dem Netzteil verbunden sein muss. Warten Sie mindestens eine Stunde, bis das Gerät aufgeladen ist.

## <a name="reset-the-device"></a>Zurücksetzen des Geräts

Unter bestimmten Umständen möchten Sie das Gerät möglicherweise manuell zurücksetzen, ohne die Software-Benutzeroberfläche zu verwenden.

### <a name="standard-procedure"></a>Standardverfahren

1. Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel abziehen.

2. Halten Sie den **Netzschalter** 15 Sekunden lang gedrückt. Alle LEDs sollten aus sein.

3. Warten Sie 2 bis 3 Sekunden und drücken Sie dann kurz den **Netzschalter**. Die LEDs, die sich in der Nähe des Netzschalters befinden, leuchten auf, und das Gerät beginnt hochzufahren.

4. Verbinden Sie das Gerät mit dem Host-PC, und öffnen Sie dann den Geräte-Manager. (Drücken Sie unter Windows 10 die **Windows**-Taste und dann die **X**-Taste und wählen Sie dann **Geräte-Manager** aus.) Stellen Sie sicher, dass das Gerät, wie im folgenden Bild dargestellt, korrekt als *Microsoft HoloLens* aufgeführt wird:

   ![Gerätemanager für HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>Kaltstart-Verfahren

Wenn das Standard Zurücksetzungsverfahren nicht funktioniert, verwenden Sie das Kaltstart-Verfahren:

1. Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel abziehen.

2. Halten Sie Tasten **Lautstärke senken** + und den **Netzschalter** 15 Sekunden lang gedrückt. Das Gerät wird automatisch neu gestartet.

4. Verbinden Sie das Gerät mit dem Host-PC.


5. Öffnen Sie den Geräte-Manager (drücken Sie unter Windows 10 die **Windows**-Taste und dann die **X**-Taste und wählen Sie dann **Gerätemanager** aus). Stellen Sie sicher, dass das Gerät ordnungsgemäß als *Microsoft HoloLens* aufgeführt wird, wie in der folgenden Abbildung dargestellt:

   ![Gerätemanager 2 für HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>Ausführen von „Clean-Reflash“ am Gerät

In außergewöhnlichen Situationen müssen Sie möglicherweise „Clean-Flash“ am HoloLens 2-Gerät durchführen. Beachten Sie, dass sich ein „Clean-Reflash“ erwartungsgemäß nicht auf die folgenden Probleme auswirkt:
- [Display-Farbgleichmäßigkeit](hololens2-display.md)
- Startvorgang mit Sound, aber ohne Bildschirmausgabe
- [1-3-5-LED-Muster](hololens2-setup.md#lights-to-indicate-problems)
- [Überhitzung](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- Betriebssystemabstürze (welche sich von Anwendungsabstürzen unterscheiden)

Es gibt es zwei Möglichkeiten ein „Reflash“ für das Gerät durchzuführen Für beide müssen Sie zunächst [Advanced Recovery Companion aus dem Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) installieren.

>[!WARNING]
>Wenn Sie Ihr Gerät neu „flashen“, werden alle Ihre persönlichen Daten, Apps und Einstellungen gelöscht, einschließlich der TPM-Zurücksetzungsinformationen.

Standardmäßig ist Advanced Recovery Companion so eingestellt, dass der neueste Featurerelease-Build heruntergeladen wird. In unseren [Versionshinweisen](hololens-release-notes.md#) finden Sie weitere Informationen zu den neuesten Featurereleases. Um das neueste HoloLens 2 Full Flash Update (FFU) Paket zu erhalten, um Ihr Gerät über Advanced Recovery Companion zu „reflashen“, [klicken Sie hier, um das neueste monatliche HoloLens 2 Image herunterzuladen](https://aka.ms/hololens2download). Diese Version ist der neueste allgemein verfügbare Build.

Stellen Sie vor dem Starten des „Flashens“ sicher, dass die App auf Ihrem Windows 10-PC installiert ist, läuft und bereit ist, das Gerät zu erkennen. Stellen Sie außerdem sicher, dass Ihre HoloLens auf mindestens 40 % aufgeladen ist.

![„Clean Reflash“ für HoloLens 2 – Screenshot](images/ARC1.png)

### <a name="normal-procedure"></a>Normales Verfahren

1. Während das HoloLens-Gerät läuft, verbinden Sie es mit Ihrem Windows 10-PC, auf dem Sie zuvor die Advanced Recovery Companion-App geöffnet haben.
 
   Das Gerät wird automatisch erkannt und die Benutzeroberfläche der Advanced Recovery Companion-App startet den Updatevorgang:

   ![„Clean Reflash“ für HoloLens 2 – Startbildschirm](images/ARC2.png)

3. Wählen Sie das HoloLens 2-Gerät in der Benutzeroberfläche der Advanced Recovery Companion-Anwendung aus und befolgen Sie die Anweisungen, um den „Reflash“ abzuschließen.

### <a name="manual-procedure"></a>Manuelle Vorgehensweise

Wenn die HoloLens 2 nicht ordnungsgemäß gestartet wird oder Advanced Recovery Companion das Gerät nicht erkennen kann, müssen Sie das Gerät möglicherweise in den Wiederherstellungsmodus versetzen:

1. Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel abziehen.

2. Halten Sie den **Netzschalter** 15 Sekunden lang gedrückt. Alle LEDs sollten erlöschen.

3. Während Sie die Taste **Lautstärke erhöhen** betätigen, drücken Sie den **Netzschalter** und lassen ihn los, um das Gerät zu starten. Warten Sie 15 Sekunden lang, und lassen Sie dann die Taste **Lautstärke erhöhen** los. Nur die mittlere LED der fünf LEDs leuchtet auf.

4. Verbinden Sie das Gerät mit dem Host-PC, und öffnen Sie den Geräte-Manager. (Drücken Sie unter Windows 10 die **Windows**-Taste und dann die **X**-Taste und wählen Sie dann **Geräte-Manager** aus.) Stellen Sie sicher, dass das Gerät, wie im folgenden Bild dargestellt, korrekt als Microsoft HoloLens aufgeführt wird:

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   Das Gerät wird automatisch erkannt und die Benutzeroberfläche der Advanced Recovery Companion-App startet den Updatevorgang:

   ![„Clean Reflash“ für HoloLens 2 – Bildschirm](images/ARC2.png)

6. Wählen Sie das HoloLens 2-Gerät in der Benutzeroberfläche der Advanced Recovery Companion-App aus und befolgen Sie dann die Anweisungen, um das erneute „Flashen“ abzuschließen.

## <a name="troubleshoot-advanced-recovery-companion"></a>Problembehandlung für Advanced Recovery Companion

1. Stellen Sie sicher, dass Ihr Gerät 40 % oder mehr aufgeladen ist, bevor Sie versuchen zu „flashen“.

2. Überprüfen Sie, ob Ihr Gerät entsperrt ist.

1. Überprüfen Sie, ob Ihr Gerät direkt an den Host-PC angeschlossen ist, nicht an einen Hub.

1. Wenn Ihr Gerät unter USB-Treiber (Universeller serieller Bus) nicht als HoloLens/HoloLens Recovery-Gerät angezeigt wird, überprüfen Sie:
    1. **Ports**, als Qualcomm HS-USB-Gerät
    1.   **Sonstige Geräte**, als QUSB_BULK-Gerät: Auf Ihrem Hostcomputer fehlen die erforderlichen Treiber, um Ihre HoloLens zu erkennen. Klicken Sie mit der rechten Maustaste, wählen Sie Treiber aktualisieren aus, und suchen Sie online nach Treibern, oder [aktivieren Sie „Optionale Updates“ in Ihren Windows-Updateeinstellungen](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674). Nachdem der Treiber heruntergeladen wurde, sollte ARC in der Lage sein, ihn zu erkennen.
 
1. Wenn ARC Ihr Gerät nicht erkennt, stellen Sie sicher, dass Sie über den Datei-Explorer auf Ihrem PC eine Verbindung mit Ihrem Gerät herstellen können. Wenn das nicht möglich ist:

    1.  Möglicherweise verfügt Ihr Gerät über USB-Richtlinien, die diese Verbindung deaktivieren. Wenn ja, versuchen Sie den [Manuellen Flash-Modus](hololens-recovery.md#manual-procedure).
    2.  Wenn keine Richtlinien vorhanden sind, versuchen Sie es mit einem anderen USB-Kabel.

1. Stellen Sie sicher, dass ihr Gerät kein [1-3-5-LED-Muster](hololens2-setup.md#lights-to-indicate-problems) anzeigt.

## <a name="download-arc-without-using-the-app-store"></a>Herunterladen von ARC, ohne den App Store zu verwenden

Wenn eine IT-Umgebung die Verwendung der Windows Store-App verhindert oder den Zugriff auf das Einzelhandelsgeschäft einschränkt, können IT-Administratoren diese App über andere "Offline"-Bereitstellungspfade verfügbar machen.

 >[!NOTE]
 > - IT-Administratoren können diese Anwendung auch über System Center Configuration Manager (SCCM) oder Intune verteilen.
 > - Dieses Handbuch konzentriert sich auf Advanced Recovery Companion. Der Prozess kann aber auch für andere „Offline“-Apps verwendet werden.

Führen Sie die folgenden Schritte aus, um den Bereitstellungspfad zu aktivieren:

1. Wechseln Sie zum [Microsoft Store für Unternehmen](https://businessstore.microsoft.com) und melden Sie sich mit einer Azure Active Directory Domain Service-Identität an.

1. Navigieren Sie zu **Verwalten – Einstellungen**. Aktivieren Sie **Offline-Apps anzeigen** unter **Einkaufserlebnis**.

1. Wechseln Sie zum **Shop für meine Gruppe** und suchen Sie nach [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).

1. Ändern Sie den **Lizenztyp** in **_offline_ *_, und wählen Sie _* Verwalten** aus.

1. Wählen unter **Paket für Offline-Verwendung herunterladen** die zweite blaue Schaltfläche **Herunterladen** aus. Stellen Sie sicher, dass die Dateierweiterung *.appxbundle* lautet.

    - Wenn der Desktop-PC zu diesem Zeitpunkt über einen Internetzugang verfügt, doppelklicken Sie auf das Paket, um die App zu installieren.

    - Wenn der Ziel-PC keine Internetverbindung hat, führen Sie die folgenden Schritte aus:
       1. Wählen Sie die unverschlüsselte Lizenz und dann **Lizenz generieren** aus.
       2. Wählen Sie unter **Erforderliche Frameworks** die Option **Herunterladen** aus.
       3. Verwenden Sie DISM, um das Paket mit Abhängigkeit und Lizenz anzuwenden. Führen Sie an einer Administrator-Eingabeaufforderung den folgenden Befehl aus:

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > Die Versionsnummer in diesem Codebeispiel stimmt möglicherweise nicht mit der aktuell verfügbaren Version überein. Möglicherweise haben Sie auch einen anderen Download-Speicherort als im angegebenen Beispiel ausgewählt. Nehmen Sie nach Bedarf Änderungen am Befehl vor.

> [!TIP]
> Wenn Sie beabsichtigen, Advanced Recovery Companion zur Offline-Installation eines FFU zu verwenden, ist es möglicherweise sinnvoll, Ihr Flash-Image herunterzuladen. [**Laden Sie das aktuelle Image für HoloLens 2**](https://aka.ms/hololens2download).


Weitere Ressourcen:
- [Verteilen von Offline-Apps](/microsoft-store/distribute-offline-apps) 
- [DISM-App-Paket (.appx oder .appxbundle) – Befehlszeilenoptionen](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
