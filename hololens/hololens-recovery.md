---
title: HoloLens neu starten, zurücksetzen oder wiederherstellen
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: Verwenden von Advanced Recovery Companion (ARC), um einen Flashs eines Images in HoloLens 2 auszuführen.
keywords: Hilfe & Anleitung, Neustart, zurücksetzen, wiederherstellen, Kaltstart, Warmstart, Energiezyklus, HoloLens, Herunterfahren, ARC, Advanced Recovery Companion
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
ms.openlocfilehash: 7845a00d1141fb721683c4e3f2a884ed0c37c735
ms.sourcegitcommit: 33911e3b405732d0d31a27039c8f590d52b647c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "11254832"
---
# HoloLens 2 neu starten, zurücksetzen oder wiederherstellen

## Laden des Geräts

Bevor Sie eine Problembehandlung starten, stellen Sie sicher, dass Ihr Gerät möglichst auf 20 bis 40 Prozent der Akkukapazität aufgeladen wurde. Verwenden Sie das Ladegerät und die USB-Typ-C-Kabel, die mit dem HoloLens2-Gerät geliefert wurden. Die in der Lieferung des Geräts enthaltene Stromversorgung und das USB-C-zu-C-Kabel sind die beste Methode zum Aufladen Ihrer HoloLens2. Das Ladegerät liefert 18W (9V bei 2A). Mit dem mitgelieferten Wandladegerät können HoloLens 2-Geräte den Akku in weniger als 65 Minuten voll aufladen, wenn sich das Gerät im Standbymodus befindet. Wenn das Zubehör nicht verfügbar ist, vergewissern Sie sich, dass das verfügbare Ladegerät mindestens 15W Leistung unterstützt.

> [!NOTE]
> Vermeiden Sie nach Möglichkeit die Verwendung eines PCs, um das Gerät über USB zu laden, was sehr langsam ist.

Wenn das Gerät korrekt hochgefahren und ausgeführt wird, gibt es drei verschiedene Möglichkeiten, den Ladezustand des Akkus zu überprüfen:

- Über das Hauptmenü der Benutzeroberfläche des HoloLens-Geräts.
- Sehen Sie sich die LEDs in der Nähe des Netzschalters an (bei 40 % sollten mindestens zwei LEDs ununterbrochen leuchten).
    - Während des Ladevorgangs leuchtet die Akkuanzeige auf, um den aktuellen Ladezustand anzuzeigen.  Die letzte Anzeige leuchtet auf und erlischt, um den aktiven Ladevorgang anzuzeigen.
    - Wenn Ihre HoloLens eingeschaltet ist, zeigt die Akkuanzeige den Akkustand in fünf Schritten an.
    - Wenn nur eine der fünf LEDs leuchtet, ist der Akkustand unter 20%.
    - Wenn der Akkuladestand kritisch niedrig ist und Sie versuchen, das Gerät einzuschalten, blinkt eine LED kurz und erlischt anschließend.
- Öffnen Sie auf Ihrem Host-PC den **Datei-Explorer**, und suchen Sie Ihr HoloLens 2-Gerät auf der linken Seite unter **Dieser PC**. Klicken Sie mit der rechten Maustaste auf das Gerät, und wählen Sie **Eigenschaften** aus. Ein Dialogfeld mit dem Akkuladezustand wird angezeigt.

   ![Ein HoloLens 2-Eigenschaftenbildschirm zeigt den Akkuladezustand.](images/ResetRecovery2.png)

Wenn das Gerät nicht ins Startmenü starten kann, beachten Sie das LED-Erscheinungsbild und die Geräteenumeration auf dem Host-PC. Folgen Sie dann der [Anleitung zur Problembehandlung](https://docs.microsoft.com/hololens/hololens-troubleshooting). Falls der Status des Geräts nicht mit einem der im Handbuch zur Fehlerbehebung aufgeführten Zustände übereinstimmt, führen Sie den [Hard-Reset-Vorgang](hololens-recovery.md#hard-reset-procedure) aus, wobei das Gerät nicht mit Ihrem Host-PC, sondern mit dem Netzteil verbunden sein muss. Warten Sie mindestens eine Stunde, bis das Gerät aufgeladen ist.

## Setzen Sie das Gerät zurück

Unter bestimmten Umständen möchten Sie das Gerät möglicherweise manuell zurücksetzen, ohne die Software-Benutzeroberfläche zu verwenden.

### Standardvorgehensweise

1. Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel abziehen.

2. Halten Sie den **Netzschalter** 15 Sekunden lang gedrückt. Alle LEDs sollten aus sein.

3. Warten Sie 2 bis 3 Sekunden, und drücken Sie dann den **Netzschalter**. Die LEDs, die sich in der Nähe des Netzschalters befinden, leuchten auf, und das Gerät wird hochgefahren.

4. Verbinden Sie das Gerät mit dem Host-PC, und öffnen Sie dann den Geräte-Manager. (Drücken Sie unter Windows 10 die **Windows**-Taste und dann die **X**-Taste, und wählen Sie dann **Geräte-Manager** aus.) Stellen Sie sicher, dass das Gerät wie im folgenden Bild korrekt als *Microsoft HoloLens* aufgeführt wird:

   ![Gerätemanager für HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### Hard-Reset-Verfahren

Wenn das Standardzurücksetzungsverfahren nicht funktioniert, verwenden Sie das Hard-Reset-Verfahren:

1. Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel abziehen.

2. Halten Sie die **Leiser-Taste** und den  + **Netzschalter** 15 Sekunden lang gedrückt. Das Gerät wird automatisch neu gestartet.

4. Verbinden Sie das Gerät mit dem Host-PC.
5. Öffnen Sie den Geräte-Manager (drücken Sie unter Windows 10 die **Windows**-Taste und dann die **X**-Taste, und wählen Sie dann **Geräte-Manager** aus). Stellen Sie sicher, dass das Gerät ordnungsgemäß als *Microsoft HoloLens* aufgelistet wird, wie in der folgenden Abbildung dargestellt:

   ![Gerätemanager 2 für HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## Clean-Reflash des Geräts

In außergewöhnlichen Situationen müssen Sie das HoloLens 2 möglicherweise „clean flashen“. Beachten Sie, dass sich ein Clean-Reflash erwartungsgemäß nicht auf die folgenden Probleme auswirkt:
- [Farbhomogenität des Bildschirms](hololens2-display.md)
- Startvorgang mit Sound, aber ohne Bildschirmausgabe
- [1-3-5-LED-Muster](hololens2-setup.md#lights-to-indicate-problems)
- [Überhitzung](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- Betriebssystemabstürze (welche sich von Anwendungsabstürzen unterscheiden)

Dafür gibt es zwei Möglichkeiten. Für beide müssen Sie zuerst [Advanced Recovery Companion aus dem Windows Store installieren](https://www.microsoft.com/store/productId/9P74Z35SFRS8).

>[!WARNING]
>Wenn Sie Ihr Gerät neu flashen, werden alle Ihre persönlichen Daten, Apps und Einstellungen gelöscht, einschließlich der TPM-Zurücksetzungsinformationen.

Standardmäßig ist Advanced Recovery Companion so eingestellt, dass der neueste Featurerelease-Build heruntergeladen wird. In unseren [Versionshinweisen](hololens-release-notes.md#) finden Sie weitere Informationen zu den neuesten Featurereleases. Wenn Sie das neueste HoloLens 2 Full Flash Update (FFU)-Paket herunterladen möchten, um Ihr Gerät über Advanced Recovery Companion zu reflashen, [klicken Sie hier, um das neueste monatliche HoloLens 2-Image herunterzuladen](https://aka.ms/hololens2download). Diese Version ist der neueste allgemein verfügbare Build.

Stellen Sie vor dem Starten des Flashens sicher, dass die Anwendung auf Ihrem Windows 10-PC installiert ist, ausgeführt wird und bereit ist, das Gerät zu erkennen. Stellen Sie außerdem sicher, dass Ihre HoloLens auf mindestens 40% aufgeladen ist.

![„Clean Reflash“ für HoloLens 2 – Screenshot](images/ARC1.png)

### Normales Verfahren

1. Während das HoloLens-Gerät ausgeführt wird, verbinden Sie es mit Ihrem Windows 10-PC, auf dem Sie zuvor die Advanced Recovery Companion-Anwendung gestartet haben.
 
   Das Gerät wird automatisch erkannt und die Benutzeroberfläche der Advanced Recovery Companion-Anwendung startet den Updatevorgang:

   ![„Clean Reflash“ für HoloLens 2 – Startbildschirm](images/ARC2.png)

3. Wählen Sie das HoloLens 2-Gerät in der Benutzeroberfläche der Advanced Recovery Companion-Anwendung aus und befolgen Sie die Anweisungen, um das erneute Flashen abzuschließen.

### Manuelle Vorgehensweise

Wenn das HoloLens 2 nicht richtig startet, müssen Sie das Gerät möglicherweise in den Wiederherstellungsmodus versetzen:

1. Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel abziehen.

2. Halten Sie den **Netzschalter** 15 Sekunden lang gedrückt. Alle LEDs sollten erlöschen.

3. Halten Sie die **Lauter-Taste** gedrückt, während Sie den **Netzschalter** drücken und loslassen, um das Gerät zu starten. Warten Sie 15 Sekunden, bevor Sie die **Lauter-Taste** loslassen. Nur die mittlere LED der fünf LEDs leuchtet auf.

4. Verbinden Sie das Gerät mit dem Host-PC, und öffnen Sie den Geräte-Manager. (Drücken Sie unter Windows 10 die **Windows**-Taste und dann die **X**-Taste, und wählen Sie dann **Geräte-Manager** aus.) Stellen Sie sicher, dass das Gerät wie im folgenden Bild korrekt als „Microsoft HoloLens“ aufgeführt wird:

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   Das Gerät wird automatisch erkannt und die Benutzeroberfläche der Advanced Recovery Companion-Anwendung startet den Updatevorgang:

   ![„Clean Reflash“ für HoloLens 2 – Bildschirm](images/ARC2.png)

6. Wählen Sie das HoloLens 2-Gerät in der Benutzeroberfläche der Advanced Recovery Companion-Anwendung aus und befolgen Sie dann die Anweisungen, um das erneute Flashen abzuschließen.

## Herunterladen von ARC ohne Verwendung des App Store

Wenn eine IT-Umgebung die Verwendung der Windows Store-App verhindert oder den Zugriff auf das Einzelhandelsgeschäft einschränkt, können IT-Administratoren diese Anwendung über andere "Offline"-Bereitstellungspfade verfügbar machen.

 >[!NOTE]
 > - IT-Administratoren können diese Anwendung auch über System Center Configuration Manager (SCCM) oder Intune verteilen.
 > - Dieses Handbuch konzentriert sich auf Advanced Recovery Companion. Der Prozess kann aber auch für andere Offline-Apps verwendet werden.

Führen Sie die folgenden Schritte aus, um den Bereitstellungspfad zu aktivieren:
1. Wechseln Sie zum [Microsoft Store für Unternehmen](https://businessstore.microsoft.com), und melden Sie sich mit einer Azure Active Directory-Identität an.

1. Wechseln Sie zu **Verwalten – Einstellungen**. Aktivieren Sie **Offline-Apps anzeigen** unter **Shopping-Erfahrung**.
1. Wechseln Sie zu **Shop für meine Gruppe**, und suchen Sie nach [**_Advanced Recovery Companion_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).
1. Ändern Sie den _*Lizenztyp** in **_Offline_*_, und wählen Sie _* Manage** aus.
1. Wählen Sie unter **Paket für Offline-Verwendung herunterladen** die zweite blaue Schaltfläche **Herunterladen** aus. Stellen Sie sicher, dass die Dateierweiterung *.appxbundle* lautet.

    - Wenn der Desktop-PC zu diesem Zeitpunkt über einen Internetzugang verfügt, doppelklicken Sie auf das Paket, um die App zu installieren.

    - Wenn der Ziel-PC keine Internetverbindung hat, führen Sie die folgenden Schritte aus:
       1. Wählen Sie die nicht codierte Lizenz aus, und wählen Sie dann **Lizenz generieren** aus.
       2. Wählen Sie unter **Erforderliche Frameworks** die Option **Herunterladen** aus.
       3. Verwenden Sie DISM, um das Paket mit Abhängigkeit und Lizenz anzuwenden. Führen Sie an einer Administrator-Eingabeaufforderung den folgenden Befehl aus:

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > Die Versionsnummer in diesem Codebeispiel stimmt möglicherweise nicht mit der aktuell verfügbaren Version überein. Möglicherweise haben Sie auch einen anderen Download-Speicherort als im angegebenen Beispiel ausgewählt. Nehmen Sie nach Bedarf Änderungen am Befehl vor.

> [!TIP]
> Wenn Sie beabsichtigen, Advanced Recovery Companion zur Offlineinstallation eines FFU zu verwenden, ist es möglicherweise sinnvoll, Ihr Flash-Image herunterzuladen. [**Laden Sie das aktuelle Image für HoloLens 2 herunter**](https://aka.ms/hololens2download).

Andere Ressourcen
- [Verteilen von Offline-Apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [DISM-App-Paket (.appx oder .appxbundle) – Befehlszeilenoptionen](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
