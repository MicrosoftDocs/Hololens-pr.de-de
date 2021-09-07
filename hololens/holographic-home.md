---
title: Verwenden des Startmenüs und der Mixed Reality-Startseite
description: Erfahren Sie, wie Sie auf HoloLens-Geräten das Startmenü verwenden, Apps verwalten und darauf zugreifen und in der Mixed Reality-Startumgebung navigieren.
ms.assetid: 742bc126-7996-4f3a-abb2-cf345dff730c
ms.date: 08/07/2019
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f9a6f1692df05e5fd8faec3da07cc85f7c6a32c7
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189170"
---
# <a name="use-the-start-menu-and-mixed-reality-home"></a>Verwenden des Startmenüs und der Mixed Reality-Startseite

So wie die Benutzererfahrung auf einem Windows-PC mit dem Desktop beginnt, beginnt sie bei Windows Holographic mit der Mixed Reality-Startumgebung.  Über das Startmenü können Sie in der Mixed Reality-Startumgebung App-Fenster, immersive App-Startprogramme und 3D-Inhalte öffnen und platzieren, wobei die Platzierung in Ihrem physischen Raum gespeichert wird.

## <a name="use-the-start-menu"></a>Das Startmenü

Im Startmenü von HoloLens öffnen Sie Apps, sehen wichtige Statusinformationen und greifen auf Tools wie die Kamera zu.

Unabhängig davon, wo Sie sich in HoloLens befinden, können Sie das Startmenü jederzeit mithilfe der **Startgeste** öffnen.  Auf HoloLens (1. Generation) ist die Startgeste die [Öffnengeste](https://support.microsoft.com/help/12644/hololens-use-gestures). Auf HoloLens 2 müssen Sie als [Startgeste](hololens2-basic-usage.md#start-gesture) auf das Startsymbol tippen, das auf Ihrem Handgelenk angezeigt wird.  Sie können das Startmenü auch über Ihre Stimme öffnen, indem Sie „Zum Startmenü” sagen.

> [!TIP]
> Wenn das Startmenü geöffnet ist, können Sie es mit der Startgeste schließen oder das Startmenü anvisieren und „Schließen” sagen.

Oben im Startmenü werden Statusanzeigen für WLAN, Akku, Lautstärke und eine Uhr angezeigt. Auf der HoloLens 2 gibt es auch eine Höranzeige, die zeigt, ob das Gerät sprachaktiviert ist und auf Sprachbefehle hört. Unten finden Sie die Schaltflächen **Foto** und **Video**, mit denen Sie Fotos und Videoaufnahmen machen können.  Darüber hinaus gibt es die Schaltfläche **Verbinden**, mit der Sie mithilfe von Miracast das Gesehene auf ein anderes Gerät projizieren können.

### <a name="find-apps-on-start-menu"></a>Suchen von Apps im Startmenü

Das Startmenü enthält die Listen **Angeheftete Apps** und **Alle Apps**.

- In der Liste **Angeheftete Apps** werden angeheftete Apps gezeigt. Sie können Apps zur Liste der **angehefteten Apps** hinzufügen und daraus entfernen, indem Sie das Kontextmenü verwenden, das angezeigt wird, wenn Sie eine App-Kachel **auswählen und halten**.

- Die Liste **Alle Apps** enthält alle Apps, die auf dem Gerät installiert sind.  Wählen Sie rechts im **Startmenü** die Schaltfläche **Alle Apps** aus, um zur Liste zu gelangen.

In beiden App-Listen können Sie rechts im Startmenü mit den Schaltflächen **Vorherige Seite** und **Nächste Seite** durch alle Apps in der Liste blättern.  Beide App-Listen werden automatisch auf der Seite geöffnet, die zuletzt während einer Gerätesitzung verwendet wurde.

> [!TIP]
> Auf HoloLens 2 können Sie mit dem Zeigefinger direkt durch die App-Listen scrollen. Berühren Sie die Liste einfach mit der Fingerspitze, und ziehen Sie sie nach oben oder unten.

### <a name="open-apps-from-start-menu"></a>Öffnen von Apps im Startmenü

Um im Startmenü eine App zu öffnen, **wählen** Sie einfach eine **App-Kachel** aus. Sie können auch den Namen einer App sagen, um sie zu öffnen.

Wenn Sie im Startmenü eine App öffnen, wird je nach Art der App eine der folgenden Aktionen ausgeführt:

- Ein **App-Fenster** wird platziert. Die App wird dann in das Fenster geladen, das wie ein Touchscreen verwendet werden kann.
- Ein **3D-App-Launcher** für eine immersive App wird platziert. Sie müssen dann den Launcher **auswählen**, um die immersive App zu öffnen.
- Ein App-Fenster wird platziert und funktioniert wie ein **Launcher** für eine immersive App. Die immersive App wird daraufhin automatisch gestartet.

App-Fenster und App-Launcher, die in der Mixed Reality-Startumgebung platziert wurden, bleiben so lange dort, bis Sie sie entfernen.  Sie bieten eine bequeme Verknüpfung, um diese App-Fenster zu verwenden oder immersive Apps zu starten, ohne sie erneut über das Startmenü öffnen zu müssen. 

> [!NOTE]
>Wie bei einem Smartphone werden Systemressourcen auf der HoloLens automatisch verwaltet.  Wenn Sie beispielsweise eine neue immersive App öffnen, werden alle anderen ausgeführten Apps sofort inaktiv. Es ist nicht erforderlich, App-Fenster und -Launcher aus der Mixed Reality-Startumgebung zu entfernen, um Systemressourcen freizugeben. 

## <a name="using-apps-on-hololens"></a>Verwenden von Apps auf der HoloLens

Apps auf der HoloLens können die App-Fensteransicht oder immersive Ansicht verwenden. In der App-Fensteransicht wird der App-Inhalt einfach in einem Fenster angezeigt. Bei der immersiven Ansicht führt Sie eine App aus der Mixed Reality-Startumgebung heraus, um ihre Inhalte dann in der physischen Umgebung um Sie herum anzuzeigen. Apps können auch beide Ansichten verwenden.

### <a name="use-app-windows"></a>Verwenden von App-Fenstern

Auf HoloLens (1. Generation) werden App-Fenster in der Mixed Reality-Startumgebung genutzt und platziert, wo Sie sie nach Belieben [verschieben, skalieren und drehen](hololens1-basic-usage.md#move-resize-and-rotate-apps) können. Zusätzlich zur Verwendung von App-Fenstern mittels Anvisieren und Gesten können Sie diese auch mit einer über Bluetooth angeschlossenen Maus und Tastatur nutzen.

Auf HoloLens 2 können Sie nicht nur App-Fenster in der Mixed Reality-Startumgebung, sondern auch jeweils ein App-Fenster in einer immersiven App nutzen. Sie können ein App-Fenster auch in den Modus **Mir folgen** versetzen, in dem es vor Ihnen bleibt, während Sie sich umher bewegen. Wenn Sie ein App-Fenster in einer immersiven App öffnen, wird es automatisch im Modus **Mir folgen** geöffnet. In der Mixed Reality-Startumgebung und innerhalb einer immersiven App können Sie App-Fenster mit Ihren Händen direkt [verschieben, skalieren und drehen](hololens2-basic-usage.md#move-resize-and-rotate-holograms).

> [!NOTE]
>
> - In der Mixed Reality-Startumgebung können bis zu drei App-Fenster gleichzeitig aktiv sein. Sie können mehr öffnen, aber nur drei bleiben aktiv.
> - Wenn ein App-Fenster nicht aktiv ist, werden Inhalte angezeigt, die im Vergleich zu einem aktiven Fenster abgedunkelt aussehen.  Bei einigen wird einfach das App-Symbol anstelle von Inhalten angezeigt.  Um ein inaktives Fenster zu aktivieren, müssen Sie es einfach **auswählen**.
> - Jede geöffnete App kann jeweils ein aktives Fenster haben, mit Ausnahme des Browsers Microsoft Edge, bei dem drei Fenster möglich sind.

### <a name="close-apps"></a>Schließen von Apps

Um eine App zu schließen, die ein App-Fenster verwendet, schließen Sie das App-Fenster einfach über die Schaltfläche **Schließen** auf der Titelleiste.  Sie können auch das Fenster anvisieren und „Schließen” sagen.

Um eine App mit immersiver Ansicht zu beenden, verwenden Sie die Startgeste, um das **Startmenü** aufzurufen, und wählen Sie dann die Schaltfläche **Mixed Reality-Startumgebung** aus.

Wenn eine immersive App einen fehlerhaften Zustand hat und Sie sie neu starten müssen, können Sie sicherstellen, dass die App zuerst vollständig heruntergefahren wird, indem Sie ihren Launcher in der Mixed Reality-Startumgebung schließen und sie dann über das Startmenü starten.

### <a name="default-app-picker"></a>Standard-App-Auswahl

Wenn Sie in [Version 21H1 von Windows Holographic](hololens-release-notes.md#windows-holographic-version-21h1) einen Link aktivieren oder einen Dateityp öffnen, der von mehr als einer installierten App unterstützt wird, öffnet sich ein neues Fenster, in dem Sie auswählen können, mit welcher installierten App der Datei- oder Linktyp gehandhabt werden soll. In diesem Fenster können Sie auch festlegen, dass die ausgewählte App die Datei oder den Linktyp „Einmal" oder „Immer“ handhabt.

![App-Auswahlfenster.](images/default-app-picker.png)

Wenn Sie „Immer“ wählen, aber später ändern möchten, mit welcher App eine bestimmte Datei oder ein bestimmter Linktyp gehandhabt wird, können Sie Ihre gespeicherten Standardeinstellungen unter **Einstellungen > Apps** zurücksetzen. Scrollen Sie auf der Seite nach unten, und wählen Sie unter „Standard-Apps für Dateitypen“ und/oder „Standard-Apps für Linktypen“ die Schaltfläche **Löschen** aus. Im Gegensatz zur ähnlichen Einstellung auf Desktop-PCs können Sie die Standardeinstellungen einzelner Dateitypen nicht zurücksetzen.

### <a name="per-app-volume-control"></a>App-bezogene Lautstärkeregelung

In [Version 21H1 von Windows Holographic](hololens-release-notes.md#windows-holographic-version-21h1) können Benutzer den Lautstärkepegel der einzelnen Apps manuell regeln. So können sich Benutzer besser auf die Apps konzentrieren, die sie benötigen, bzw. besser hören, wenn sie mehrere Apps einsetzen. Beispielsweise müssen Sie die Lautstärke einer App reduzieren, während Sie in einer anderen App eine andere Person zwecks Fernbetreuung anrufen.

Um die Lautstärke einer einzelnen App festzulegen, navigieren Sie zu **Einstellungen** -> **System** -> **Klang**, und wählen Sie unter „Erweiterte Klangoptionen“ **App-Lautstärke und Geräteeinstellungen** aus.

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

## <a name="related-info"></a>Verwandte Informationen

[Anwendungen aus dem Microsoft-Shop suchen, installieren und deinstallieren](holographic-store-apps.md)
