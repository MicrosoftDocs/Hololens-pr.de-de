---
title: Aktualisieren HoloLens 2
description: Erfahren Sie, wie Sie Ihre HoloLens Buildnummer überprüfen, über Geräteupdates auf dem Laufenden bleiben, am Insiders-Programm teilnehmen und Updates zurücksetzen.
keywords: Vorgehensweise, Update, Rollback, HoloLens, Build überprüfen, Buildnummer
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-beehanson
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/11/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: 080fb184c7eca3fdb978e860a29764f5012a179e
ms.sourcegitcommit: f105a770814ccd61e88b650448902a03c95b7a3c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2021
ms.locfileid: "130151689"
---
# <a name="update-hololens-2"></a>Aktualisieren HoloLens 2

## <a name="overview"></a>Übersicht

Wir arbeiten immer an neuen Features, Fehlerbehebungen und Sicherheitsupdates. Sie werden benachrichtigt, wenn diese Updates bereit sind.

Je nach Ihren Wünschen lädt Ihr HoloLens Systemupdates automatisch herunter und installiert sie, sobald es an den Strom angeschlossen, mit dem Internet verbunden und sogar im Standbymodus ist.

Um sicherzustellen, dass Ihre HoloLens immer aktualisiert wird, lassen Sie sie mit der Vorrichtung verbunden, die mit ihr geliefert wurde. Sie möchten auch, dass Ihre HoloLens mit dem Internet verbunden ist. Auf diese Weise werden Systemupdates automatisch heruntergeladen und installiert. 

Mit Windows Updatedienst steuern Sie mehrere Aspekte des Updateprozesses, z. B. welche Geräte zu welchem Zeitpunkt welche Updates erhalten. Dieses Steuerelement ist hilfreich, da Sie Updates für eine Teilmenge von HoloLens Geräten zu Testzwecken bereitstellen können. Anschließend werden Updates für die verbleibenden Updates bereitgestellt. Oder Sie können unterschiedliche Zeitpläne für verschiedene Arten von Updates festlegen.

## <a name="types-of-updates"></a>Updatetypen

Für HoloLens können Sie automatisch zwei Arten von Updates verwalten.

- Featureupdates: zweimal pro Jahr veröffentlicht.
- Qualitätsupdates: Wichtige Sicherheitsupdates sind enthalten. Sie werden monatlich oder nach Bedarf veröffentlicht.

Verwenden Sie **Update** / **AllowAutoUpdate,** um das Scannen, Herunterladen und Installieren von Updates zu verwalten. 

## <a name="scheduling-updates"></a>Planen von Updates

Sie können auch einen Updatezeitplan festlegen. Dies kann an einem bestimmten Tag oder an jedem Tag zu einer bestimmten Zeit erfolgen. Beispielsweise um 17:00 Uhr oder außerhalb der aktiven Stunden.

Abschließend ein paar Worte zur Planung Ihrer Updatestrategie. Wir unterstützen Updaterückstellungen, sodass Sie entscheiden können, wie lange nach der Veröffentlichung eines Updates durch Microsoft gewartet werden soll, um dieses Update auf Geräten zu installieren.

Manchmal möchte ein Unternehmen zuerst alle neuen Features ausprobieren, um sicherzustellen, dass alles funktioniert, und es ist mit den neuen Updates vertraut, damit das Supportteam vorbereitet ist. Nachdem sie bestätigt haben, dass alles gut ist, stellen sie die Updates für das gesamte Unternehmen bereit. Indem Sie Teilmengen Ihrer Geräte verschiedenen Zurückstellungsrichtlinien zuordnen, die als Updateringe bezeichnet werden, können Sie eine Updaterolloutstrategie für Ihre Organisation koordinieren.

## <a name="hololens-update-tools"></a>HoloLens-Updatetools

Dieser Abschnitt führt Sie durch HoloLens Tools für:

- Suchen nach Updates
- manuelles Aktualisieren HoloLens
- Anzeigen der aktuellen Betriebssystemversion (Buildnummer)
- Rollback zu einem älteren Update

### <a name="check-for-updates-and-manually-update"></a>Suchen nach Updates und manuelles Aktualisieren

Sie können jederzeit in den Einstellungen nach Updates suchen.  So können Sie verfügbare Updates anzeigen und nach neuen Updates suchen:

1. Öffnen Sie die App **Einstellungen**.
1. Navigieren Sie zu **Update & Security** Windows  >  **Update**.
1. Wählen Sie **Nach Updates suchen** aus.

Wenn ein Update verfügbar ist, wird die neue Version heruntergeladen. Wählen Sie nach Abschluss des Downloads die Schaltfläche **Jetzt neu starten** aus, um die Installation auszulösen. Wenn Ihr Gerät unter 40 % liegt und nicht angeschlossen ist, wird die Installation des Updates durch einen Neustart nicht gestartet.

Während Ihr HoloLens das Update installiert, werden drehende Zahnradschaltungen und eine Statusanzeige angezeigt. Deaktivieren Sie ihre HoloLens während dieser Zeit nicht. Sie wird nach Abschluss der Installation automatisch neu gestartet.

HoloLens wendet jeweils ein Update an.  Wenn Ihr HoloLens mehr als eine Version hinter der neuesten version liegt, müssen Sie den Updateprozess möglicherweise mehrmals ausführen, um ihn vollständig auf dem neuesten Stand zu halten.

### <a name="check-your-operating-system-version-build-number"></a>Überprüfen der Betriebssystemversion (Buildnummer)

Sie können die Systemversionsnummer (Buildnummer) überprüfen, indem Sie **Einstellungen** öffnen und **System**  >  **about** auswählen.

### <a name="go-back-to-a-previous-version"></a>Zurück zu einer früheren Version

In einigen Fällen möchten Sie möglicherweise zu einer früheren Version der HoloLens-Software zurückkehren. Die folgenden Schritte werden empfohlen:

1. Wenden Sie sich an den Support, um zu prüfen, ob das Problem behoben werden kann.
    1. Stellen Sie sicher, dass **optionale** oder **vollständige** Telemetrie aktiviert ist. Dies macht Ihren Fehler handlungsfähiger und für Techniker einfacher zu diagnostizieren.
    1. Unter [Dateifeedback](hololens-feedback.md) ist so beschreibend wie möglich. Notieren Sie sich den Titel, oder verwenden Sie das Freigabefeature, damit Sie Ihren Fehler mit dem Support teilen können.
    1. Wenden Sie sich an [den Support.](https://aka.ms/hlsupport) Wenn Ihr Problem gelöst werden muss, indem Sie zu einer früheren Version zurückkehren, können Sie die FFU zum Flashen Ihres Geräts bereitstellen.

1. Alternativ können Sie [ihre HoloLens 2 mit dem Advanced Recovery Companion umschwenkten.](hololens-recovery.md#clean-reflash-the-device)
    1.  Wählen Sie aus, in welche Version Sie flashen möchten: 
        1.  Sie können das [neueste HoloLens 2 Release](https://aka.ms/hololens2download)herunterladen.
        1.  Sie können den Standardbuild verwenden, der von ARC gehostet wird.
        1.  Sie können einen Buildsupport verwenden, der Ihnen zur Verfügung gestellt wird.

> [!NOTE]
> Wenn Sie zu einer früheren Version zurückkehren, werden Ihre persönlichen Dateien und Einstellungen gelöscht.

Darüber hinaus können Sie Updates auch manuell [anhalten,](hololens-updates.md#pause-updates-via-device)wenn Sie ihr derzeit installiertes Release fortsetzen möchten. Dadurch erhält das Engineering-Team Zeit, das Problem zu beheben.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Program on HoloLens

Möchten Sie die neuesten Features in HoloLens anzeigen?  Wenn ja, treten Sie dem Windows Insider-Programm bei. Sie erhalten Zugriff auf Vorschaubuilds von HoloLens Softwareupdates, bevor sie für die allgemeine Öffentlichkeit verfügbar sind.

[Erhalten Sie Windows Insider-Vorschauversion für Microsoft HoloLens](hololens-insider.md).