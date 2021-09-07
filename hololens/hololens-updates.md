---
title: Verwalten von HoloLens-Updates
description: Hier erfahren Sie, wie Administratoren über die Verwaltung mobiler Geräte Updates für HoloLens-Geräte verwalten.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/13/2020
ms.reviewer: jarrettr
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 3afe3d2aecd64c2b4724f4805571cb3c46112875
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190037"
---
# <a name="manage-hololens-updates"></a>Verwalten von HoloLens-Updates

HoloLens verwendet Windows Update auf die gleiche Weise wie andere Windows 10-Geräte. Wenn ein Update verfügbar ist, wird es automatisch heruntergeladen und installiert, sobald das Gerät das nächste Mal angeschlossen und mit dem Internet verbunden ist. In diesem Artikel wird beschrieben, wie Sie Updates in einem Unternehmen oder in einer anderen verwalteten Umgebung verwalten können. Informationen zum Verwalten von Updates für einzelne HoloLens-Geräte finden Sie unter [Aktualisieren von HoloLens](hololens-update-hololens.md).

## <a name="manage-updates-automatically"></a>Automatische Verwaltung von Updates

### <a name="managing-updates-by-using-windows-update-for-business"></a>Verwalten von Updates mit Windows Update for Business

Windows Holographic for Business kann [Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb) verwenden, um Updates zu verwalten. Alle HoloLens 2-Geräte können Windows Holographic for Business verwenden. Stellen Sie sicher, dass sie Windows Holographic for Business ab Build 10.0.18362.1042 verwenden. Wenn Sie HoloLens-Geräte (der 1. Generation) haben, müssen Sie [diese auf Windows Holographic for Business](hololens1-upgrade-enterprise.md) upgraden, um deren Updates zu verwalten.

Windows Update for Business verbindet HoloLens-Geräte direkt mit dem Windows Update-Dienst. Mithilfe von Windows Update for Business können Sie mehrere Aspekte des Updateprozesses steuern, d. h. welche Geräte welche Updates zu welchem Zeitpunkt erhalten. So können Sie z. B. Updates auf nur einem Teil der Geräte zu Testzwecken installieren und zu einem späteren Zeitpunkt auch auf den verbleibenden Geräten. Oder Sie können unterschiedliche Zeitpläne für verschiedene Arten von Updates festlegen.

> [!NOTE]  
> Bei HoloLens-Geräten können Sie Featureupdates (zweimal im Jahr) und Qualitätsupdates (monatlich oder nach Bedarf, einschließlich kritischer Sicherheitsupdates) automatisch verwalten. Weitere Informationen zu Updatetypen finden Sie unter [Typen von Updates, die von Windows Update for Business verwaltet werden](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Sie können die Einstellungen für Windows Update for Business für HoloLens mithilfe von Richtlinien in einer MDM-Lösung (Mobile Device Management, Verwaltung mobiler Geräte) wie Microsoft Intune konfigurieren.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Verwalten von Windows Update for Business mit Microsoft Intune

Eine ausführliche Erläuterung zum Konfigurieren von Windows Update for Business mit Intune finden Sie unter [Verwalten von Windows 10-Softwareupdates in Intune](/intune/protect/windows-update-for-business-configure). Weitere Informationen zu den spezifischen von HoloLens unterstützten Intune-Funktionen finden Sie unter [Intune Update-Verwaltungsfunktionen, die HoloLens unterstützt](#intune-update-management-functions-that-hololens-supports).

> [!IMPORTANT]  
> Intune bietet zwei Richtlinientypen für die Verwaltung von Updates: *Windows 10-Updatering* und *Windows 10-Featureupdate*. Der Richtlinientyp „Windows 10-Featureupdate“ ist derzeit in der Public Preview-Phase und wird für HoloLens nicht unterstützt.
>  
> Für die Verwaltung von HoloLens 2-Updates können Sie Windows 10-Updatering-Richtlinien verwenden.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Konfigurieren von Updaterichtlinien für HoloLens 2 oder HoloLens (1. Generation)

In diesem Abschnitt werden die Richtlinien beschrieben, die Sie zur Verwaltung von Updates für HoloLens 2 oder HoloLens (1. Generation) verwenden können. Weitere Informationen zu den Funktionen, die für HoloLens 2 verfügbar sind, finden Sie unter [Planen und Konfigurieren von Updaterollouts für HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).

[Richtlinien-Konfigurationsdienstanbieter: Update](/windows/client-management/mdm/policy-csp-update) definiert die Richtlinien zum Konfigurieren von Windows Update for Business.

> [!NOTE]  
> Eine Liste mit bestimmten Richtlinien-Konfigurationsdienstanbietern (CSPs), die von bestimmten Editionen von HoloLens unterstützt werden, finden Sie unter [Richtlinien-Konfigurationsdienstanbieter](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).

#### <a name="configure-automatic-checks-for-updates"></a>Konfigurieren automatischer Überprüfungen auf Updates

Mit der Richtlinie **Update/AllowAutoUpdate** können Sie das Verhalten bei automatischen Updates verwalten, z. B. das Suchen, Herunterladen und Installieren von Updates. Weitere Informationen zu den verfügbaren Einstellungen für diese Richtlinie finden Sie unter [Update/AllowAutoUpdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> In Microsoft Intune können Sie diese Richtlinie mithilfe des **automatischen Updateverhaltens** ändern. Weitere Informationen finden Sie unter [Verwalten von Windows 10-Softwareupdates in Intune](/intune/windows-update-for-business-configure).

#### <a name="configure-an-update-schedule"></a>Konfigurieren eines Zeitplans für Updates

Um zu konfigurieren, wie und wann Updates angewendet werden, verwenden Sie die folgenden Richtlinien:

- [Update/ScheduledInstallDay](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Werte: **0**-**7** (0 = täglich, 1 = Sonntag, 7 = Samstag)
  - Standardwert: **0** (täglich)
- [Update/ScheduledInstallTime](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Werte: 0-23 (0 = Mitternacht, 23 = 23:00 Uhr)
  - Standardwert: 03:00 Uhr

#### <a name="configure-active-hours"></a>Konfigurieren der Nutzungszeit
Ab der [Windows Holographic-Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) kann ein IT Administrator die aktive Nutzungszeit für HoloLens 2-Geräte festlegen.

Nutzungszeit gibt den Zeitraum an, in dem das Gerät wahrscheinlich genutzt wird. Automatische Neustarts nach einem Update erfolgen außerhalb der Nutzungszeit. Der angegebene Zeitraum wird ab dem Startzeitpunkt der Nutzungszeit gezählt. Sie können MDM verwenden, wie unter [Konfigurieren der Nutzungszeit mit MDM](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm) beschrieben. MDM verwendet die Einstellungen Update/ActiveHoursStart, Update/ActiveHoursEnd und Update/ActiveHoursMaxRange im Richtlinien-Konfigurationsanbieter, um die Nutzungszeit zu konfigurieren.

-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend): Dieser Wert legt die Endzeit fest. Maximal 12 Stunden ab Startzeit.
    -   Unterstützte Werte sind 0-23, wobei gilt: 0 ist 12 Uhr, 1 ist 1 Uhr usw.
    -   Der Standardwert ist 17 (17:00 Uhr).
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange): Dieser Wert legt die maximale Anzahl aktiver Stunden ab Startzeit fest.
    -   Unterstützte Werte sind 8 bis 18.
    -   Der Standardwert ist 18 (Stunden).
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart): Dieser Wert legt die Startzeit fest. Maximal 12 Stunden ab Endzeit.
    -   Unterstützte Werte sind 0-23, wobei gilt: 0 ist 12 Uhr, 1 ist 1 Uhr usw.
    -   Der Standardwert ist 8 (8:00 Uhr).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Nur für Geräte mit Windows 10, Version 1607

Mithilfe der folgenden Updaterichtlinien können Sie Geräte so konfigurieren, dass Updates vom Windows Server Update-Dienst (WSUS) anstelle von Windows Update abgerufen werden:

- [Update/AllowUpdateService](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>Planen und Konfigurieren von Updaterollouts für HoloLens 2

HoloLens 2 unterstützt mehr Automatisierungsfeatures für Updates als HoloLens (1. Generation). Dies gilt insbesondere, wenn Sie Microsoft Intune zum Verwalten von Windows Update for Business-Richtlinien verwenden. Mithilfe dieser Features können Sie Updaterollouts in der gesamten Organisation einfacher planen und umsetzen.

#### <a name="plan-the-update-strategy"></a>Planen der Updatestrategie

Windows Updates for Business unterstützt Zurückstellungsrichtlinien. Nachdem Microsoft ein Update veröffentlicht hat, können Sie mithilfe einer Zurückstellungsrichtlinie definieren, wie lange die Installation dieses Updates auf Geräten zurückgestellt werden soll. Sie können eine Strategie für das Rollout von Updates für Ihre Organisation koordinieren, indem Sie Teilmengen Ihrer Geräte (als *Updateringe* bezeichnet) unterschiedlichen Zurückstellungsrichtlinien zuordnen.

Gehen wir beispielsweise von einer Organisation mit 1.000 Geräten aus, die in fünf Phasen aktualisiert werden müssen. Die Organisation kann fünf Updateringe erstellen, wie in der folgenden Tabelle gezeigt.

|Group |Anzahl von Geräten |Zurückstellung (Tage) |
| ---| :---: | :---: |
|Gruppe 1 (IT-Mitarbeiter) |5 |0 |
|Gruppe 2 (Early Adopters) |50 |60 |
|Gruppe 3 (Primär 1) |250 |120 |
|Gruppe 4 (Primär 2) |300 |150 |
|Gruppe 5 (Primär 3) |395 |180 |

So verläuft der Rollout im Laufe der Zeit in der gesamten Organisation.

![Zeitachse für die Bereitstellung von Updates.](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Konfigurieren einer Zurückstellungsrichtlinie für Updates

Eine Zurückstellungsrichtlinie gibt die Anzahl der Tage zwischen dem Datum, an dem ein Update verfügbar wird, und dem Datum an, an dem das Update einem Gerät angeboten wird.

Sie können für Feature- und Qualitätsupdates unterschiedliche Zurückstellungen festlegen. In der folgenden Tabelle sind die einzelnen Richtlinien aufgelistet, die für den jeweiligen Typ verwendet werden, sowie die jeweilige maximale Zurückstellung.

|Category |Richtlinie |Maximale Verzögerung |
| --- | --- | --- |
|Featureupdates |DeferFeatureUpdatesPeriodInDays |365 Tage |
|Qualitätsupdates |DeferQualityUpdatesPeriodInDays |30 Tage |

#### <a name="pause-updates-via-device"></a>Aussetzen von Updates auf dem Gerät

Wenn ein Benutzer keinen Zugriff auf MDM hat, kann er auf einem HoloLens 2-Gerät mit Build [Windows Holographic, Version 2004](hololens-release-notes.md#windows-holographic-version-2004) oder höher Updates individuell manuell für bis zu 35 Tage aussetzen. Benutzer gelangen zu dieser Einstellung, indem sie zu **Einstellungen > Update & Sicherheit > Erweiterte Optionen** nach unten zu **Updates aussetzen** scrollen und das Datum auswählen, bis zu dem sie Updates aussetzen möchten. Sobald ein Benutzer die Grenze für das Aussetzen erreicht hat, muss das Gerät neue Updates erhalten, bevor diese erneut ausgesetzt werden können. 

Ab der [Windows Holographic-Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) kann diese Funktion zum Aussetzen von Updates für HoloLens 2-Geräte verwaltet werden. 
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (Standard) = aktiviert
    - 1 = deaktiviert

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Von HoloLens unterstützte Intune-Funktionen zur Verwaltung von Updates

Sie können die folgenden Intune-Funktionen zur Verwaltung von Updates für HoloLens verwenden.

- **Erstellen** und **Zuweisen**: diese Funktionen fügen der Liste der Updateringe einen Windows 10-Updatering hinzu. Weitere Informationen finden Sie unter [Erstellen und Zuweisen von Updateringen](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

- **Aussetzen**: Wenn bei der Installation eines Funktions- oder Qualitätsupdates ein Problem auftritt, können Sie das Update 35 Tage (ab einem bestimmten Datum) aussetzen. Durch dieses Aussetzen wird verhindert, dass das Update auf anderen Geräten installiert wird, bis Sie das Problem behoben oder Abhilfemaßnahmen ergriffen haben. Wenn Sie ein Featureupdate aussetzen, werden den Geräten nach wie vor Qualitätsupdates bereitgestellt, um sicherzustellen, dass sie weiterhin sicher sind. Wenn ein Updatetyp angehalten wird, zeigt die Übersicht für diesen Ring an, wie viele Tage verbleiben, bis der Updatetyp fortgesetzt wird. Nach Ablauf der angegebenen Zeit läuft das Aussetzen automatisch ab, und der Updatevorgang wird fortgesetzt.

  Während der Updatering ausgesetzt ist, können Sie eine der folgenden Optionen auswählen:

  - **Verlängern**: Das Aussetzen eines Updatetyps um 35 Tage verlängern.
  - **Fortsetzen**: Updates für diesen Ring reaktivieren. Sie können den Updatering bei Bedarf erneut aussetzen.

  > [!NOTE]  
  > Der Vorgang zum **Deinstallieren** für Updateringe wird für HoloLens 2-Geräte nicht unterstützt.

### <a name="delivery-optimization-preview"></a>Übermittlungsoptimierung (Vorschau)

Die [Windows Holographic-Version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) hat eine frühe Vorschau für Optimierungseinstellungen für die Bereitstellung aktiviert, um die Inanspruchnahme von Bandbreite bei Downloads von mehreren HoloLens-Geräten zu reduzieren. Eine ausführlichere Beschreibung dieser Funktionalität zusammen mit der empfohlenen Netzwerkkonfiguration finden Sie hier: [Übermittlungsoptimierung für Windows 10-Updates](/windows/deployment/update/waas-delivery-optimization).

Die folgenden Einstellungen werden als Teil der Verwaltungsoberfläche aktiviert und [können über Intune konfiguriert werden](/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Dieses Vorschauangebot hat einige Nachteile:

- HoloLens-Unterstützung ist in dieser Vorschau ausschließlich auf Betriebssystemupdates beschränkt.
- Windows Holographic for Business unterstützt nur HTTP-Downloadmodi und Downloads von einem [Microsoft Connected Cache-Endpunkt](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache). Peer-to-Peer-Downloadmodi und Gruppenzuweisungen werden für HoloLens-Geräte derzeit nicht unterstützt.
- HoloLens unterstützt keine Bereitstellungs- oder Übermittlungsoptimierung für Windows Server Update Services-Endpunkte.
- Für die Problembehandlung ist entweder eine Diagnose auf dem Connected Cache-Server oder das Erfassen einer Ablaufverfolgung für HoloLens über **Einstellungen** > **Update und Sicherheit** >  **Problembehandlung** >  **Windows Update** erforderlich.

## <a name="manually-check-for-updates"></a>Manuelles Prüfen auf Updates

Obwohl HoloLens regelmäßig auf Systemupdates prüft, kann es Umstände geben, unter denen Sie dies manuell prüfen möchten.

Um manuell auf Updates zu prüfen, wechseln Sie zu **Einstellungen** > **Update und Sicherheit** > **Auf Updates prüfen**. Wenn die App „Einstellungen“ anzeigt, dass Ihr Gerät auf dem neuesten Stand ist, sind alle Updates installiert, die aktuell verfügbar sind.

## <a name="manually-roll-back-an-update"></a>Manuelles Zurücksetzen eines Updates

Es kann vorkommen, dass ein Zurückkehren zu einer früheren Version der HoloLens-Software erforderlich ist. Die Vorgehensweise hierfür hängt davon ab, ob Sie HoloLens 2 oder HoloLens (1. Generation) verwenden.

### <a name="revert-to-a-previous-version-hololens-2"></a>Zurückkehren zu einer vorherigen Version (HoloLens 2)

Sie können Updates zurücksetzen und zu einer früheren Version von HoloLens 2 zurückkehren, indem Sie Ihre HoloLens mit dem [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) auf die frühere Version zurücksetzen.

> [!NOTE]
> Wenn Sie zu einer früheren Version zurückkehren, werden Ihre persönlichen Dateien und Einstellungen gelöscht.

Führen Sie die folgenden Schritte aus, um zu einer früheren Version von HoloLens 2 zurückzukehren:

1. Stellen Sie sicher, dass keine Smartphones oder Windows-Geräte an Ihren Computer angeschlossen sind.
1. Laden Sie auf Ihrem Computer den [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) aus dem Microsoft Store herunter.
1. Laden Sie das [neueste HoloLens 2-Release](https://aka.ms/hololens2download) herunter.
1. Öffnen Sie nach Abschluss dieser Downloads **Datei-Explorer** > **Downloads**, und klicken Sie mit der rechten Maustaste auf den komprimierten Ordner (.zip), den Sie gerade heruntergeladen haben. Wählen Sie dann **Alle extrahieren** > **Extrahieren** aus, um die Datei zu dekomprimieren.
1. Schließen Sie Ihr HoloLens-Gerät mit einem USB-A-zu-USB-C-Kabel an Ihren Computer an. Auch wenn Sie Ihre HoloLens mit anderen Kabeln angeschlossen haben, funktioniert diese Art von Kabel am besten.
1. Advanced Recovery Companion erkennt Ihr HoloLens-Gerät automatisch. Wählen Sie die Kachel **Microsoft HoloLens** aus.
1. Wählen Sie auf dem nächsten Bildschirm **Manuelle Paketauswahl** aus, und öffnen Sie dann den Ordner, den Sie zuvor erweitert haben.
1. Wählen Sie die Installationsdatei (.ffu) aus.
1. Wählen Sie **Software installieren** aus, und befolgen Sie dann die Anweisungen.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Zurückkehren zu einer vorherigen Version (HoloLens [1. Generation])

Sie können Updates zurücksetzen und zu einer früheren Version von HoloLens (1. Generation) zurückkehren, indem Sie Ihre HoloLens mit dem [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) auf die frühere Version zurücksetzen.

> [!NOTE]
> Wenn Sie zu einer früheren HoloLens-Version zurückkehren, werden Ihre persönlichen Dateien und Einstellungen gelöscht.

Führen Sie die folgenden Schritte aus, um zu einer früheren Version von HoloLens (1. Generation) zurückzukehren:

1. Stellen Sie sicher, dass keine Smartphones oder Windows-Geräte an Ihren Computer angeschlossen sind.
1. Laden Sie das [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) auf Ihren Computer herunter.
1. Laden Sie das [HoloLens Anniversary Update-Wiederherstellungspaket](https://aka.ms/hololensrecovery) herunter.
1. Öffnen Sie nach Abschluss dieser Downloads **Datei-Explorer** > **Downloads**, und klicken Sie mit der rechten Maustaste auf den komprimierten Ordner (.zip), den Sie gerade heruntergeladen haben. Wählen Sie dann **Alle extrahieren** > **Extrahieren** aus, um die Datei zu dekomprimieren.
1. Verwenden Sie das zusammen mit Ihrem HoloLens-Gerät gelieferte Micro-USB-Kabel, um das Gerät an Ihren Computer anzuschließen. Auch wenn Sie Ihr HoloLens-Gerät mit anderen Kabeln verbunden haben, funktioniert dieses am besten.
1. Das WDRT erkennt automatisch Ihr HoloLens-Gerät. Wählen Sie die Kachel **Microsoft HoloLens** aus.
1. Wählen Sie auf dem nächsten Bildschirm **Manuelle Paketauswahl** aus, und öffnen Sie dann den Ordner, den Sie zuvor erweitert haben.
1. Wählen Sie die Installationsdatei (.ffu) aus.
1. Wählen Sie **Software installieren** aus, und befolgen Sie dann die Anweisungen.

**Wenn das WDRT Ihr Gerät nicht erkennt**

Falls das WDRT Ihr HoloLens-Gerät nicht erkennt, starten Sie Ihren Computer neu. Falls dies nicht funktioniert, wählen Sie **Mein Gerät wurde nicht erkannt** und dann **Microsoft HoloLens** aus, und befolgen Sie die Anweisungen.

## <a name="related-articles"></a>Verwandte Artikel

- [Versionshinweise für HoloLens 2](hololens-release-notes.md)
- [Was ist Windows Update for Business?](/windows/deployment/update/waas-manage-updates-wufb)
- [Zuweisen von Geräten zu Servicing Channels für Windows10-Updates](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Verwalten von Windows 10-Softwareupdates in Intune](/mem/intune/protect/windows-update-for-business-configure)
