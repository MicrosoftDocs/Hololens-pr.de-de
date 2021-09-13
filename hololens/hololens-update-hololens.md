---
title: Aktualisieren HoloLens 2
description: Erfahren Sie, wie Sie Ihre HoloLens Buildnummer überprüfen, über Geräteupdates auf dem Laufenden bleiben, am Insiders-Programm teilnehmen und Updates zurücksetzen.
keywords: Vorgehensweise, Update, Rollback, HoloLens, Überprüfen des Builds, Buildnummer
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: f39fc2c6c0aaf16f304f38216a424c3811eb439d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032866"
---
# <a name="update-hololens-2"></a>Aktualisieren HoloLens 2

## <a name="overview"></a>Übersicht

Wir arbeiten immer an neuen Features, Fehlerbehebungen und Sicherheitsupdates. Sie werden benachrichtigt, wenn diese Updates bereit sind.

Je nach Ihren Wünschen lädt Ihr HoloLens Systemupdates automatisch herunter und installiert sie, wenn es an den Strom angeschlossen, mit dem Internet verbunden und sogar im Standbymodus ist.

Um sicherzustellen, dass Ihre HoloLens immer aktualisiert wird, lassen Sie sie mit der Vorrichtung verbunden, die mit ihr geliefert wurde. Sie möchten auch, dass Ihre HoloLens mit dem Internet verbunden ist. Auf diese Weise werden Systemupdates automatisch heruntergeladen und installiert. 

Mit Windows Updatedienst steuern Sie mehrere Aspekte des Updateprozesses, z. B. welche Geräte zu welchem Zeitpunkt welche Updates erhalten. Dieses Steuerelement ist hilfreich, da Sie Updates für eine Teilmenge von HoloLens Geräten zu Testzwecken bereitstellen können. Anschließend werden Updates für die verbleibenden Updates bereitgestellt. Oder Sie können unterschiedliche Zeitpläne für verschiedene Arten von Updates festlegen.

## <a name="types-of-updates"></a>Updatetypen

Für HoloLens können Sie automatisch zwei Arten von Updates verwalten. 

- Featureupdates: zweimal pro Jahr veröffentlicht.
- Qualitätsupdates: Wichtige Sicherheitsupdates sind enthalten. Sie werden monatlich oder nach Bedarf veröffentlicht.

Verwenden Sie **Update** / **AllowAutoUpdate,** um das Scannen, Herunterladen und Installieren von Updates zu verwalten. 

## <a name="scheduling-updates"></a>Planen von Updates

Sie können auch einen Updatezeitplan festlegen. Dies kann zu einem bestimmten Zeitpunkt an einem bestimmten Tag oder an jedem Tag erfolgen. Beispielsweise um 17:00 Uhr oder außerhalb der aktiven Stunden.

Abschließend noch ein paar Worte zur Planung Ihrer Updatestrategie. Updaterückstellungen werden unterstützt. Sie können also entscheiden, wie lange nach der Veröffentlichung eines Updates durch Microsoft gewartet werden soll, um dieses Update auf Geräten zu installieren.

Manchmal versucht ein Unternehmen, zuerst alle neuen Features auszuprobieren, um sicherzustellen, dass alles funktioniert, und ist mit den neuen Updates vertraut, damit das Supportteam vorbereitet ist. Nachdem sie bestätigt haben, dass alles gut ist, stellen sie die Updates für das gesamte Unternehmen bereit. Indem Sie Teilmengen Ihrer Geräte verschiedenen Zurückstellungsrichtlinien zuordnen, die als Updateringe bezeichnet werden, können Sie eine Updaterolloutstrategie für Ihre Organisation koordinieren.

## <a name="hololens-update-tools"></a>HoloLens-Updatetools

Dieser Abschnitt führt Sie durch HoloLens Tools für:

- Überprüfen auf Updates
- manuelles Aktualisieren HoloLens
- Anzeigen der aktuellen Betriebssystemversion (Buildnummer)
- Rollback zu einem älteren Update

### <a name="check-for-updates-and-manually-update"></a>Suchen nach Updates und manuelles Aktualisieren

Sie können jederzeit in den Einstellungen nach Updates suchen.  So können Sie verfügbare Updates anzeigen und nach neuen Updates suchen:

1. Öffnen Sie die App **Einstellungen**.
1. Navigieren Sie zu **Update & Security** Windows  >  **Update**.
1. Wählen Sie **Nach Updates suchen** aus.

Wenn ein Update verfügbar ist, beginnt es mit dem Herunterladen der neuen Version. Wählen Sie nach Abschluss des Downloads die Schaltfläche **Jetzt neu starten** aus, um die Installation auszulösen. Wenn Ihr Gerät unter 40 % liegt und nicht angeschlossen ist, startet der Neustart nicht mit der Installation des Updates.

Während Ihr HoloLens das Update installiert, werden drehende Zahnradgeräte und eine Statusanzeige angezeigt. Deaktivieren Sie ihre HoloLens während dieser Zeit nicht. Nach Abschluss der Installation wird er automatisch neu gestartet.

HoloLens wendet jeweils ein Update an.  Wenn Ihr HoloLens mehr als eine Version hinter der neuesten version liegt, müssen Sie den Updateprozess möglicherweise mehrmals ausführen, um ihn vollständig auf dem neuesten Stand zu halten.

### <a name="check-your-operating-system-version-build-number"></a>Überprüfen der Betriebssystemversion (Buildnummer)

Sie können die Systemversionsnummer (Buildnummer) überprüfen, indem Sie **Einstellungen** öffnen und **System**  >  **about** auswählen.

### <a name="go-back-to-a-previous-version"></a>Zurück zu einer früheren Version

In einigen Fällen möchten Sie möglicherweise zu einer früheren Version der HoloLens-Software zurückkehren. Die folgenden Schritte werden empfohlen:

1. Wenden Sie sich an den Support, um zu prüfen, ob das Problem behoben werden kann.
    1. Stellen Sie sicher, dass **optionale** oder **vollständige** Telemetrie aktiviert ist. Dies erleichtert Technikern das Diagnostizieren des Fehlers.
    1. [Dateifeedback](hololens-feedback.md) ist so beschreibend wie möglich. Notieren Sie sich den Titel, oder verwenden Sie das Freigabefeature, damit Sie Ihren Fehler für den Support freigeben können.
    1. Wenden Sie sich an [den Support.](https://aka.ms/hlsupport) Wenn Ihr Problem gelöst werden muss, indem Sie zu einer früheren Version zurückkehren, können Sie die FFU zum Flashen Ihres Geräts bereitstellen.

1. Wenn dies nicht funktioniert, [setzen Sie Ihre HoloLens 2 mit dem Advanced Recovery Companion zurück, oder setzen Sie](hololens-recovery.md)den Schrägstrich zurück.
    1. Laden Sie auf Ihrem PC den [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) von der Microsoft Store herunter.
    1. Stellen Sie sicher, dass keine Telefone oder Windows Geräte an Ihren PC angeschlossen sind.
    1. Wählen Sie aus, in welche Version Sie flashen möchten:
        1. Sie können das [neueste HoloLens 2 Release](https://aka.ms/hololens2download)herunterladen.
        1. Sie können den Standardbuild verwenden, der von ARC gehostet wird. (Wenn Sie diese Option auswählen, überspringen Sie den nächsten Schritt.)
        1. Sie können einen Buildsupport verwenden, der Ihnen zur Verfügung gestellt wird.
    1. Wenn Sie diese Downloads abgeschlossen haben, öffnen Sie **Datei-Explorer-Downloads**  >  . Klicken Sie mit der rechten Maustaste auf den gezippten Ordner, den Sie heruntergeladen haben, und wählen **Sie Extract all** Extract  >  **(Alle extrahieren)** aus, um ihn zu entzippen.
    1. Verbinden Ihre HoloLens mithilfe eines USB-A-zu-USB-C-Kabels an Ihren PC. (Auch wenn Sie andere Kabel verwendet haben, um Ihre HoloLens zu verbinden, funktioniert dieses am besten.)
    1. Der Advanced Recovery Companion erkennt Automatisch Ihre HoloLens. Wählen Sie die Kachel **Microsoft HoloLens** aus.
    1. Klicken Sie auf dem nächsten Bildschirm auf **Manuelle Paketauswahl,** und wählen Sie dann die Installationsdatei aus, die in dem Ordner enthalten ist, den Sie in Schritt 4 entpackt haben. (Suchen Sie nach einer Datei mit der `.ffu` Erweiterung .)
    1. Wählen Sie **Software installieren** aus, und befolgen Sie die Anweisungen.

> [!NOTE]
> Wenn Sie zu einer früheren Version zurückkehren, werden Ihre persönlichen Dateien und Einstellungen gelöscht.

Darüber hinaus können Sie Updates auch manuell [anhalten,](hololens-updates.md#pause-updates-via-device)wenn Sie ihr derzeit installiertes Release fortsetzen möchten. Dadurch erhält das Engineering-Team Zeit, das Problem zu beheben.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Program on HoloLens

Möchten Sie die neuesten Features in HoloLens anzeigen?  Wenn ja, treten Sie dem Windows Insider-Programm bei. Sie erhalten Zugriff auf Vorschaubuilds von HoloLens Softwareupdates, bevor sie für die allgemeine Öffentlichkeit verfügbar sind.

[Erhalten Sie Windows Insider-Vorschauversion für Microsoft HoloLens](hololens-insider.md).