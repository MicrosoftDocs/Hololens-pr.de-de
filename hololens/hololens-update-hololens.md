---
title: Update HoloLens 2
description: Erfahren Sie, wie HoloLens Buildnummer überprüfen, mit Geräteupdates auf dem Laufenden bleiben, am Insider-Programm teilnehmen und ein Rollback für Updates erstellen.
keywords: How-to, update, rollback, HoloLens, check build, build number
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
ms.openlocfilehash: 49036135ba13a93d2e8be97a7f3a95d50785c5c5
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034262"
---
# <a name="update-hololens-2"></a>Update HoloLens 2

## <a name="overview"></a>Übersicht

Wir arbeiten immer an neuen Features, Fehlerbehebungen und Sicherheitsupdates. Sie werden benachrichtigt, wenn diese Updates bereit sind.

Je nach Ihren Vorlieben werden Systemupdates von HoloLens automatisch heruntergeladen und installiert, wenn sie an den Strom angeschlossen, mit dem Internet verbunden und sogar im Standbymodus angeschlossen ist.

Um sicherzustellen, HoloLens immer aktualisiert wird, lassen Sie es mit der 10000-000-000-000-Version verbunden. Sie möchten auch, dass HoloLens mit dem Internet verbunden ist. Auf diese Weise werden automatisch Systemupdates heruntergeladen und installiert. 

Mit Windows Updatedienst steuern Sie mehrere Aspekte des Updateprozesses, z. B. welche Geräte zu welchem Zeitpunkt welche Updates erhalten. Dieses Steuerelement ist hilfreich, da Sie Updates für eine Teilmenge von HoloLens für Tests bereitstellen können. Anschließend werden Updates für die verbleibenden Updates veröffentlicht. Oder Sie können unterschiedliche Zeitpläne für verschiedene Arten von Updates festlegen.

## <a name="types-of-updates"></a>Updatetypen

Für HoloLens können Sie automatisch zwei Arten von Updates verwalten.

- Featureupdates: zweimal pro Jahr veröffentlicht.
- Qualitätsupdates: Enthalten wichtige Sicherheitsupdates. Sie werden monatlich oder nach Bedarf veröffentlicht.

Verwenden **Sie** / **AllowAutoUpdate aktualisieren,** um das Scannen, Herunterladen und Installieren von Updates zu verwalten. 

## <a name="scheduling-updates"></a>Planen von Updates

Sie können auch einen Updatezeitplan festlegen. Dies kann an einem bestimmten Tag oder täglich zu einem bestimmten Zeitpunkt der Fall sein. Beispielsweise um 17:00 Uhr oder außerhalb der aktiven Stunden.

Abschließend noch ein paar Worte zur Planung Ihrer Updatestrategie. Wir unterstützen Verzögerungen bei Updates, sodass Sie entscheiden können, wie lange gewartet werden soll, nachdem Microsoft ein Update veröffentlicht hat, um dieses Update auf Geräten zu installieren.

Manchmal möchte ein Unternehmen zuerst alle neuen Features ausprobieren, um sicherzustellen, dass alles funktioniert, und es ist mit den neuen Updates vertraut, damit das Supportteam vorbereitet ist. Nachdem bestätigt wurde, dass alles gut ist, werden die Updates für das gesamte Unternehmen veröffentlicht. Indem Sie Teilmengen Ihrer Geräte verschiedenen Zurückungsrichtlinien zuordnen, die als Updateringe bezeichnet werden, können Sie eine Updaterolloutstrategie für Ihre Organisation koordinieren.

## <a name="hololens-update-tools"></a>HoloLens Updatetools

In diesem Abschnitt werden die folgenden HoloLens beschrieben:

- Suchen nach Updates
- Manuelles Aktualisieren HoloLens
- Anzeigen ihrer aktuellen Betriebssystemversion (Buildnummer)
- Roll zurück zu einem älteren Update

### <a name="check-for-updates-and-manually-update"></a>Suchen nach Updates und manuelles Aktualisieren

Sie können jederzeit in den Einstellungen nach Updates suchen.  So sehen Sie verfügbare Updates und suchen nach neuen Updates:

1. Öffnen Sie die App **Einstellungen**.
1. Navigieren Sie **zu Update & Security** Windows  >  **Update**.
1. Wählen Sie **Nach Updates suchen** aus.

Wenn ein Update verfügbar ist, wird mit dem Herunterladen der neuen Version gestartet. Wählen Sie nach Abschluss des Downloads die Schaltfläche **Jetzt neu starten** aus, um die Installation auszulösen. Wenn Ihr Gerät unter 40 % liegt und nicht angeschlossen ist, beginnt der Neustart nicht mit der Installation des Updates.

Während Ihr HoloLens das Update installiert, werden spinnende Zahnrad und eine Statusanzeige angezeigt. Deaktivieren Sie ihre HoloLens während dieser Zeit nicht. Sie wird nach Abschluss der Installation automatisch neu gestartet.

HoloLens wird ein Update nach dem anderen angewendet.  Wenn Ihr HoloLens mehr als eine Version hinter der neuesten Version liegt, müssen Sie den Updateprozess möglicherweise mehrmals ausführen, um ihn vollständig auf dem neuesten Stand zu halten.

### <a name="check-your-operating-system-version-build-number"></a>Überprüfen Ihrer Betriebssystemversion (Buildnummer)

Sie können die Systemversionsnummer (Buildnummer) überprüfen, indem Sie Einstellungen **system** about **(System about)**  >  **auswählen.**

### <a name="go-back-to-a-previous-version"></a>Zurück zu einer früheren Version

In einigen Fällen möchten Sie möglicherweise zu einer früheren Version der HoloLens wechseln. Die folgenden Schritte werden empfohlen:

1. Wenden Sie sich an den Support, um zu erfahren, ob er Ihr Problem beheben kann.
    1. Stellen Sie **sicher, dass** **optionale** oder vollständige Telemetrie aktiviert ist. Dadurch wird Ihr Fehler umsetzbarer und einfacher für Techniker zu diagnostizieren.
    1. Geben [Sie unter Dateifeedback](hololens-feedback.md) so beschreibend wie möglich an. Notieren Sie sich den Titel, oder verwenden Sie das Freigabefeature, damit Sie Ihren Fehler für den Support freigeben können.
    1. Wenden Sie [sich an den Support.](https://aka.ms/hlsupport) Wenn Ihr Problem gelöst werden muss, indem sie zu einer früheren Version zurückkehren, können sie Ihnen die FFU zum Flashen Ihres Geräts zur Verfügung geben.

1. Wenn dies nicht funktioniert, geben Sie ihren HoloLens 2 mit [dem Advanced Recovery Companion neu.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> Wenn Sie zu einer früheren Version zurückkommen, werden Ihre persönlichen Dateien und Einstellungen gelöscht.

Wenn Sie das derzeit installierte Release weiterhin verwenden möchten, können Sie Updates auch [manuell anhalten.](hololens-updates.md#pause-updates-via-device) Dies gibt dem Engineering-Team Zeit, das Problem zu beheben.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider-Programm HoloLens

Möchten Sie die neuesten Features in HoloLens?  Wenn ja, treten Sie dem Windows Insider-Programm bei. Sie erhalten Zugriff auf Vorschauversionen von HoloLens Softwareupdates, bevor sie für die allgemeine Öffentlichkeit verfügbar sind.

[Hier Windows Insider-Vorschau für Microsoft HoloLens.](hololens-insider.md)