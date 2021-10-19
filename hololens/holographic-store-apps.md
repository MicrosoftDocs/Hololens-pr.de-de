---
title: Suchen, Installieren und Deinstallieren von Anwendungen
description: Der Microsoft Store ist Ihre Anlaufstelle für Apps und Spiele, die mit HoloLens funktionieren.  Erfahren Sie mehr über das Suchen, Installieren und Deinstallieren von holographischen Apps.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 9/7/2021
manager: jarrettr
keywords: Hololens, Store, UWP, App, Installieren
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4705112ee41ce6de0598358b9c81775f261bb2fa
ms.sourcegitcommit: 8a3f925d2bda13c095b35f14d80afdd876aa859c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2021
ms.locfileid: "129800554"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Suchen, Installieren und Deinstallieren von Anwendungen aus dem Microsoft Store

Der Microsoft-Store ist Ihre erste Anlaufstelle für Apps und Spiele, die mit der HoloLens funktionieren. Wenn Sie auf Ihrer HoloLens in den Store wechseln, können alle dort angezeigten Apps darauf ausgeführt werden.

Apps auf HoloLens verwenden entweder eine 2D- oder eine holographische Darstellung. Apps, die 2D-Ansichten verwenden, sehen wie Fenster aus und können überall in Ihrer Umgebung positioniert werden. Apps, die holographische Darstellung verwenden, umgeben Sie und werden zur einzigen App in Ihrem Sichtfeld.

HoloLens unterstützt viele vorhandene Anwendungen aus dem Microsoft Store sowie neue Apps, die speziell für HoloLens entwickelt wurden.  Dieser Artikel befasst sich mit holographischen Anwendungen aus dem Microsoft Store.

Weitere Informationen zum Installieren und Ausführen von benutzerdefinierten Apps finden Sie unter [Benutzerdefinierte holografische Anwendungen](holographic-custom-apps.md).

## <a name="find-apps"></a>Suchen von Anwendungen

Öffnen Sie im **Startmenü** den Microsoft Store. Suchen Sie dann nach Apps und Spielen. Sie können [Sprachbefehle](hololens-cortana.md) für die Suche verwenden, indem Sie „Suchen“ sagen. Nachdem das Suchfenster geöffnet wurde, sagen Sie „Starte diktieren“, und nach erfolgter Aufforderung beginnen Sie, Ihre Suchbegriffe zu sprechen.

> [!NOTE]
> Die Systemanforderungen für HoloLens-Geräte basieren auf der Architektur des App-Builds. Wenn ein App-Build für HoloLens (1. Generation) nicht im Store mit einem neueren UWP aktualisiert wurde, sodass er das ARM-Architekturpaket integriert, ist er für HoloLens 2-Geräte nicht verfügbar. Analog dazu ist eine HoloLens 2-App, die das x86-Architekturpaket nicht enthält, nicht für HoloLens-Geräte (1. Generation) verfügbar. HoloLens-Gerätearchitekturen:
>
> - x86 = HoloLens (1. Generation)
> - ARM = HoloLens 2

> [!NOTE]
> Am 12. Januar 2021 erreichen die folgenden Apps das Supportende für HoloLens-Geräte. Wir empfehlen Ihnen, auf Ihrem Gerät über den folgenden Link die Webversion der App zu verwenden.

| App        | Link                                          |
|------------|-----------------------------------------------|
| Excel Mobile      | [https://office.live.com/start/Excel.aspx](https://office.live.com/start/Excel.aspx)      |
| Word Mobile       | [https://office.live.com/start/Word.aspx](https://office.live.com/start/Word.aspx)       |
| PowerPoint Mobile | [https://office.live.com/start/PowerPoint.aspx](https://office.live.com/start/PowerPoint.aspx) |

> [!NOTE]
> Die OneDrive-App wird für Azure AD Konten auf HoloLens derzeit nicht unterstützt. Es wird empfohlen, die Microsoft OneDrive PWA-App herunterzuladen. [Führen Sie diese Schritte aus, um die App herunterzuladen.]

## <a name="install-apps"></a>Installieren von Apps

Zum Herunterladen von Apps müssen Sie mit einem Microsoft-Konto angemeldet sein. Einige Apps sind kostenlos und können sofort heruntergeladen werden. Für Apps, für die ein Kauf erforderlich ist, müssen Sie mit Ihrem Microsoft-Konto im Store angemeldet sein und über eine gültige Zahlungsmethode verfügen.

> [!NOTE]
> Das Konto, das Sie im Microsoft Store verwenden, muss nicht mit dem Konto identisch sein, mit dem Sie angemeldet sind. Wenn Sie ein Geschäfts- oder Schul- oder Unikonto auf HoloLens verwenden, müssen Sie sich möglicherweise mit Ihrem persönlichen Konto in der Microsoft Store-App anmelden, um einen Kauf zu tätigen.

> [!TIP]
> Zum Einrichten einer Zahlungsmethode wechseln Sie zu [account.microsoft.com](https://account.microsoft.com/), und wählen Sie **Zahlung und Abrechnung** > **Zahlungsoptionen** > **Zahlungsoption hinzufügen** aus.

1. Zum Öffnen des [**Startmenüs**](holographic-home.md) führen Sie auf HoloLens (1. Generation) eine [Startgeste](/hololens/hololens2-basic-usage#start-gesture) oder eine [Öffnengeste](hololens1-basic-usage.md) aus.

1. Wählen Sie die Microsoft Store-App aus. Nach dem Öffnen der Store-App:
   1. Verwenden Sie die Suchleiste, um nach Anwendungen zu suchen.
   1. Wählen Sie wichtige Apps oder speziell für HoloLens entwickelte Apps in einer der betreuten Kategorien aus.
   1. Wählen Sie oben rechts in der Store-App die Schaltfläche **„...“** und dann **Meine Bibliothek** aus, um alle zuvor erworbenen Apps anzuzeigen.

1. Wählen Sie auf der Seite der Anwendung **Abrufen** oder **Installieren** aus (möglicherweise ist ein Kauf erforderlich).

### <a name="install-microsoft-onedrive-pwa-app"></a>Install Microsoft OneDrive PWA App

> [!NOTE]
> PWA kann nicht über Microsoft Intune/MDM verwaltet oder bereitgestellt werden.

Voraussetzungen: Der Benutzer hat das HoloLens 2-Gerät bereits mit seinem Arbeitsmandanten verknüpft.

1. Öffnen Sie das Startmenü, und starten Sie den Edge-Browser.

    ![Startmenü](images/office-pwa-1.jpg)

1. Wechseln Sie auf Ihrer HoloLens zu [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin), und geben Sie die Anmeldeinformationen ihres Arbeitskontos ein.

    ![Anmeldung mit Arbeitsinformationen](images/office-pwa-2.jpg)

1. Nachdem Sie sich erfolgreich bei Ihrem OneDrive-Webportal angemeldet haben, warten Sie 30 bis 60 Sekunden, bis die Schaltfläche „Herunterladen“ für PWA angezeigt wird.

    ![PWA-Schaltfläche „Installieren”](images/office-pwa-3.jpg)

1. Wählen Sie die PWA-Schaltfläche zum Herunterladen aus, und installieren Sie die App.

    ![Installationsaufforderung](images/office-pwa-4.jpg)

1. Schließen Sie den Edge-Browser, wählen Sie im Startmenü die Schaltfläche **Alle Apps** aus, und starten Sie die OneDrive PWA App mit der Bezeichnung **Microsoft OneDrive**

    ![„Alle Apps“ mit Darstellung beider Apps.](images/office-pwa-5.jpg)

    > [!NOTE]
    > „Microsoft OneDrive“ ist die PWA-App, wohingegen „OneDrive“ die ältere UWP-App ist.

1. Anschließend können Sie Ihre OneDrive Dateien anzeigen.

    ![OneDrive PWA](images/office-pwa-6.jpg)

Siehe auch: [Aktivieren automatischer Uploads in OneDrive for Business](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload)

## <a name="update-apps"></a>Aktualisierung von Apps

### <a name="manual-updates"></a>Manuelle Updates

Zum Aktualisieren einer App, die Sie aus dem Microsoft Store installiert haben, können Sie ein Update der App über die Microsoft Store-App ausführen. Apps, die für den Microsoft Store for Business installiert wurden, können ebenfalls über den Microsoft Store for Business aktualisiert werden.

1. Zum Öffnen des [**Startmenüs**](holographic-home.md) führen Sie auf HoloLens (1. Generation) eine [Startgeste](/hololens/hololens2-basic-usage#start-gesture) oder eine [Öffnengeste](hololens1-basic-usage.md) aus.

1. Wählen Sie die Shop-App aus.

1. Blicken Sie in die obere rechte Ecke der Store-App.

1. Wählen Sie die Schaltfläche **„...“** oder „Mehr anzeigen“ aus.

   > [!div class="mx-imgBorder"]
   > ![Screenshot der Microsoft Store-App](images/store-update-1.png).

1. Wählen Sie **Downloads und Updates** aus.
    1. Wenn Ihr Gerät zuvor Updates identifiziert hat, gibt es möglicherweise einen Abwärtspfeil und eine Nummer, die für ausstehende Updates steht.

1. Wählen Sie **Updates abrufen** aus. Ihr Gerät sucht nun nach Updates und legt diese zum Herunterladen und Installieren fest.

   > [!div class="mx-imgBorder"]
   > ![Screenshot der Microsoft Store-App zum Abrufen von Updates](images/store-update-2.png.jpg).

> [!NOTE]
> Wenn die Apps auf Ihrem Gerät von Ihrer Organisation verteilt wurden, können sie mit den gleichen kommerziellen Methoden für das App-Management aktualisiert werden. Wenn dies auf Ihre Situation zutrifft, lesen Sie mehr über unsere [Übersicht über die Bereitstellung kommerzieller Apps](app-deploy-overview.md).
>
> Wenn Sie eine benutzerdefinierte App aktualisieren möchten, die quergeladen oder bereitgestellt wurde, müssen Sie dieselbe Methode für die aktualisierte Version Ihrer App verwenden. Weitere Informationen zum Installieren und Ausführen von benutzerdefinierten Apps finden Sie unter [Benutzerdefinierte holografische Anwendungen](holographic-custom-apps.md).

### <a name="automatic-app-updates"></a>Automatische App-Updates

Automatische Updates gelten für Apps aus dem Microsoft Store oder dem Microsoft Store für Unternehmen und können nur automatisch aktualisiert werden, wenn sie direkt aus dem Store installiert wurden. Wenn sie von Intune installiert wurden, kann die IT-Abteilung Updates per Push von MDM übertragen, indem sie eine Synchronisierung mit dem Microsoft Store für Unternehmen einrichtet, um die neueste verfügbare Version für die App zu erhalten.

> [!NOTE]
> Für Apps, die aus dem Microsoft Store für Unternehmen stammen, müssen Sie beim Store angemeldet und beim gleichen Mandanten authentifiziert sein, der dem Katalog des Microsoft Stores für Unternehmen zugeordnet ist, der auf dem Gerät verwendet wird.

#### <a name="how-automatic-updates-work"></a>Funktionsweise automatischer Updates

Automatische App-Updates werden je nach der Netzwerkverfügbarkeit täglich (etwa alle 24 Stunden) durchgeführt. Halten Sie Ihr Gerät entweder aktiv oder an das Stromnetz angeschlossen, um Updates zu erhalten. Auch wenn App-Updates während der aktiven täglichen Nutzung heruntergeladen werden, werden sie nur angewendet, wenn die zu aktualisierende App nicht mehr verwendet wird.

> [!TIP]
> Laden Sie Ihr Gerät nach Möglichkeit über Nacht, während es mit dem Unternehmensnetzwerk verbunden ist. Wenn Updates über Nacht heruntergeladen und installiert werden können, ist es weniger wahrscheinlich, dass die aktive Gerätenutzung unterbrochen wird.

#### <a name="how-it-administrators-can-control-automatic-updates"></a>So können IT-Administratoren automatische Updates steuern

IT-Administratoren können automatische App-Updates über die Richtlinie [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) steuern. Mithilfe dieser Richtlinie können sie automatische App-Updates im Ganzen aktivieren oder deaktivieren, aber nicht steuern, wann Updates ausgeführt werden.

Von [21H2](hololens-release-notes.md#windows-holographic-version-21h1) an können IT-Administratoren außerdem die Richtlinie [ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures) verwenden, um zu steuern, wann Apps, die verwendet wurden, bei früheren Versuchen aber nicht aktualisiert werden konnten, zwangsweise neu gestartet werden sollen.

## <a name="uninstall-apps"></a>Deinstallieren von Apps

Es gibt drei Möglichkeiten zum Deinstallieren von Anwendungen. Sie können Anwendungen über den Microsoft-Shop, das Startmenü oder „Einstellungen“ deinstallieren.

> [!WARNING]
> System-Apps oder der Microsoft Store selbst können nicht deinstalliert werden.

> [!IMPORTANT]
> Wenn Ihre HoloLens 2 über mehrere Benutzer verfügt, müssen Sie als der Benutzer angemeldet sein, der die App installiert hat, um sie zu deinstallieren.

### <a name="uninstall-from-the-microsoft-store"></a>Deinstallieren über den Microsoft Store

Öffnen Sie den Microsoft Store im **Startmenü**, und suchen Sie dann nach der Anwendung, die Sie deinstallieren möchten.  Auf der Store-Seite weist jede installierte Anwendung eine Schaltfläche zum **Deinstallieren** auf.

### <a name="uninstall-from-the-start-menu"></a>Deinstallieren über das Startmenü

Navigieren Sie zum **Startmenü** oder in der Liste **Alle Apps** zur App. Wählen Sie die App aus und halten Sie sie, bis das Menü angezeigt wird. Wählen Sie dann **Deinstallieren** aus.

### <a name="uninstall-from-settings"></a>Deinstallieren über die Einstellungen

Wählen Sie im **Startmenü** **Einstellungen > Apps** aus. Suchen Sie in der Liste nach der App, wählen Sie sie aus, und klicken Sie dann auf **Deinstallieren**.

Wenn Sie eine App nicht deinstallieren können, senden Sie [Feedback](/hololens/hololens-feedback) mithilfe des Feedback-Hubs.
