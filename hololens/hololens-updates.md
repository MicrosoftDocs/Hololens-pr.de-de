---
title: Verwalten von HoloLens-Updates
description: Administratoren können die Lösung zur Verwaltung mobiler Geräte verwenden, um Updates für HoloLens-Geräte zu verwalten.
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
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 3a2246296c5ab8aa86dfaa419ed02aa5a961dbfc
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163134"
---
# Verwalten von HoloLens-Updates

HoloLens verwendet Windows Update auf die gleiche Weise wie andere Windows 10-Geräte. Wenn ein Update verfügbar ist, wird es automatisch heruntergeladen und installiert, wenn das Gerät das nächste Mal angeschlossen und mit dem Internet verbunden ist. In diesem Artikel wird beschrieben, wie Sie Updates in einem Unternehmen oder in einer anderen verwalteten Umgebung verwalten können. Informationen zum Verwalten von Updates für einzelne HoloLens-Geräte finden Sie unter [Aktualisieren von HoloLens](hololens-update-hololens.md).

## Automatische Verwaltung von Updates

### Updates mit Windows Update for Business verwalten

Windows Holographic for Business kann [Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) für die Verwaltung von Updates verwenden. Alle HoloLens 2-Geräte können Windows Holographic for Business verwenden. Stellen Sie sicher, dass sie Windows Holographic for Business, Build 10.0.18362.1042 oder einen späteren Build verwenden. Wenn Sie über HoloLens-Geräte der 1. Generation verfügen, müssen Sie diese auf [Windows Holographic for Business upgraden](hololens1-upgrade-enterprise.md), um Updates zu verwalten.

Windows Update for Business verbindet HoloLens-Geräte direkt mit dem Windows Update-Dienst. Mithilfe von Windows Update for Business können Sie mehrere Aspekte des Updateprozesses steuern&mdash;, d. h. welche Geräte welche Updates zu welchem Zeitpunkt erhalten. So können Sie z. B. Updates auf nur einem Teil der Geräte zu Testzwecken installieren, und zu einem späteren Zeitpunkt auch auf den verbleibenden Geräten. Oder Sie können unterschiedliche Aktualisierungszeitpläne für verschiedene Arten von Updates festlegen.

> [!NOTE]  
> Bei HoloLens-Geräten können Sie Feature-Updates (zweimal im Jahr) und Qualitätsupdates (monatlich oder nach Bedarf, einschließlich kritischer Sicherheitsupdates) automatisch verwalten. Weitere Informationen zu Updatetypen finden Sie unter [Von Windows Update for Business verwaltete Arten von Updates](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Sie können die Einstellungen für Windows Update for Business für HoloLens mithilfe von Richtlinien in einer MDM-Lösung (Mobile Device Management, Verwaltung mobiler Geräte) wie Microsoft Intune konfigurieren.

### Windows Update for Business mit Microsoft Intune verwalten.

Einzelheiten zur Verwendung von Intune zum Konfigurieren von Windows Update for Business finden Sie unter [Verwalten von Windows 10-Softwareupdates in Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure). Weitere Informationen zu den von HoloLens unterstützten spezifischen Intune-Funktionen finden Sie unter [Intune-Update-Verwaltungsfunktionen, die HoloLens unterstützt](#intune-update-management-functions-that-hololens-supports).

> [!IMPORTANT]  
> Intune bietet zwei Richtlinientypen für die Verwaltung von Updates: *Windows 10-Update-Ring* und *Windows 10-Funktionsupdates*. Der Richtlinientyp "Windows 10-Featureupdates" ist derzeit in der öffentlichen Vorschau-Phase und wird für HoloLens nicht unterstützt.
>  
> Für die Verwaltung von HoloLens 2-Updates können Sie Windows 10 Updatering-Richtlinien verwenden.

### Konfigurieren von Update-Richtlinien für HoloLens 2 oder HoloLens (1. Generation)

In diesem Abschnitt werden die Richtlinien beschrieben, die Sie zur Verwaltung von Updates für HoloLens 2 oder HoloLens (1. Generation) verwenden können. Informationen zu zusätzlichen verfügbaren Funktionen für HoloLens 2 finden Sie unter [Planen und Konfigurieren von Update-Rollouts für HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).

[Policy CSP – Update](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) definiert die Richtlinien, die Windows Update for Business konfigurieren.

> [!NOTE]  
> Eine Liste der spezifischen Richtlinien-Konfigurationsdienstanbieter (CSP), die von bestimmten Editionen von HoloLens unterstützt werden, finden Sie unter [Richtlinien Kryptografiedienstanbieter, die von HoloLens-Geräten](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)unterstützt werden.

#### Konfigurieren automatischer Überprüfungen auf Updates

Sie können die Richtlinie **Update/AllowAutoUpdate** verwenden, um automatische Updates zu verwalten, darunter das Suchen, Herunterladen und Installieren von Updates. Weitere Informationen zu den für diese Richtlinie verfügbaren Einstellungen finden Sie unter [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> In Microsoft Intune können Sie **Verhalten der automatischen Aktualisierung** verwenden, um diese Richtlinie zu ändern. Weitere Informationen finden Sie unter [Windows 10 Softwareupdates in Intune verwalten](https://docs.microsoft.com/intune/windows-update-for-business-configure).

#### Konfigurieren eines Update-Zeitplans

Verwenden Sie die folgenden Richtlinien, um zu konfigurieren, wie und wann Updates angewendet werden sollen:

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Werte: **0**-**7** (0 = jeden Tag, 1 = Sonntag, 7 = Samstag)
  - Standardwert: **0** (jeden Tag)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Werte: 0–23 (0 = Mitternacht; 23 = 23:00 Uhr)
  - Standardwert: 15:00 Uhr

#### Nutzungszeit konfigurieren
Beginnend mit [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) kann ein IT-Administrator den aktiven Stundenbereich für HoloLens 2-Geräte festlegen.

Nutzungszeit ist der Zeitraum, in dem das Gerät voraussichtlich in Gebrauch ist. Automatische Neustarts nach einem Update erfolgen außerhalb der Nutzungszeit. Der angegebene Bereich wird ab dem Startzeitpunkt der Nutzungszeit gezählt. Sie können MDM verwenden, wie unter [Nutzungszeit mit MDM konfigurieren](https://docs.microsoft.com/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm) beschrieben. MDM verwendet die Einstellungen Update/ActiveHoursStart und Update/ActiveHoursEnd und Update/ActiveHoursMaxRange im Richtlinien-CSP, um die Nutzungszeit zu konfigurieren.

-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend) – dieser Wert legt die Endzeit fest. Maximal 12 Stunden ab Startzeit.
    -   Unterstützte Werte sind 0 bis 23, wobei 0 ist 12 Uhr, 1 ist 1 Uhr usw.
    -   Der Standardwert ist 17 (17:00).
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) – dieser Wert legt die maximale Dauer der Nutzungszeit ab Startzeit fest.
    -   Unterstützte Werte sind 8 bis 18.
    -   Der Standardwert ist 18 (Stunden).
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart) – dieser Wert legt die Startzeit fest. Maximal 12 Stunden ab Endzeit.
    -   Unterstützte Werte sind 0 bis 23, wobei 0 ist 12 Uhr, 1 ist 1 Uhr usw.
    -   Der Standardwert ist 8 (8:00).

#### Nur für Windows 10-Geräte, Version 1607

Mithilfe der folgenden Update-Richtlinien können Sie Geräte so konfigurieren, dass Updates vom Windows Server Update-Dienst (WSUS) anstelle von Windows Update abgerufen werden:

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### Planen und Konfigurieren von Update-Rollouts für HoloLens 2

HoloLens 2 unterstützt mehr Update-Automatisierungsfeatures als HoloLens (1. Generation). Dies gilt insbesondere, wenn Sie Microsoft Intune zum Verwalten von Windows Update for Business-Richtlinien verwenden. Mithilfe dieser Funktionen können Sie Update-Rollouts in der gesamten Organisation einfacher planen und umsetzen.

#### Planen der Updatestrategie

Windows Updates for Business unterstützt Zurückstellungsrichtlinien. Nachdem Microsoft ein Update veröffentlicht hat, können Sie mithilfe einer Zurückstellungsrichtlinie definieren, wie lange die Installation dieses Updates auf den Geräten verzögert werden soll. Sie können eine Update-Rollout-Strategie für Ihre Organisation koordinieren, indem Sie Teilmengen Ihrer Geräte (als *Update-Ringe* bezeichnet) unterschiedlichen Zurückstellungsrichtlinien zuordnen.

Gehen wir beispielsweise von einer Organisation mit 1.000Geräten aus, die in fünf Wellen aktualisiert werden müssen. Die Organisation kann fünf Updateringe erstellen, wie in der folgenden Tabelle gezeigt.

|Gruppe |Anzahl der Geräte |Verzögerung (Tage) |
| ---| :---: | :---: |
|Grp 1 (IT-Mitarbeiter) |5 |0 |
|Grp 2 (Early Adopters) |50 |60 |
|Grp 3 (primär 1) |250 |120 |
|Grp 4 (primär 2) |300 |150 |
|Grp 5 (primär 3) |395 |180 |

Hier wird verdeutlicht, wie das Rollout über einen Zeitraum auf die gesamte Organisation ausgedehnt wird.

![Zeitachse für die Installation von Updates](./images/hololens-updates-timeline.png)

#### Konfigurieren einer Update-Zurückstellungsrichtlinie

Eine Zurückstellungsrichtlinie gibt die Anzahl der Tage zwischen dem Datum, an dem ein Update verfügbar wird, und dem Datum, an dem das Update für ein Gerät bereitgestellt wird.

Sie können unterschiedliche Verzögerungen für Feature- und Qualitätsupdates festlegen. In der folgenden Tabelle sind die einzelnen Richtlinien aufgelistet, die für den jeweiligen Typ verwendet werden, sowie die jeweilige maximale Verzögerung.

|Kategorie |Richtlinie |Maximale Verzögerung |
| --- | --- | --- |
|Funktionsupdates |DeferFeatureUpdatesPeriodInDays |365 Tage |
|Qualitätsupdates |DeferQualityUpdatesPeriodInDays |30Tage |

#### Updates über ein Gerät anhalten

Wenn Benutzer keinen Zugang zu MDM haben, können sie Updates bis zu 35 Tage manuell auf einem HoloLens 2-Gerät mit [Windows Holographic, Version 2004 oder später](hololens-release-notes.md#windows-holographic-version-2004), einzeln unterbrechen. Benutzer erreichen diese Einstellung, indem sie zu **Einstellungen -> Aktualisierung & Sicherheit -> Erweiterte Optionen** navigieren, nach unten zu **Aktualisierungen pausieren** scrollen und das Datum auswählen, bis zu dem sie Aktualisierungen pausieren. Sobald die Pausengrenze erreicht ist, erhält das Gerät neue Updates, da diese erneut pausiert werden können. 

Beginnend mit [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) kann die Funktion „Aktualisierungen pausieren“ für HoloLens 2-Geräte verwaltet werden. 
- [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (Standard) – Aktiviert
    - 1 – Deaktiviert

#### Intune Update-Verwaltungsfunktionen, die HoloLens unterstützt

Sie können die folgenden Intune-Updateverwaltungsfunktionen zum Verwalten von Updates für HoloLens verwenden.

- **Erstellen** und **Zuweisen**: diese Funktionen fügen einen Windows 10-Update Ring zur Liste der Update-Ringe hinzu. Weitere Informationen finden Sie unter [Update-Ringe erstellen und zuweisen](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

- **Pause**: Wenn bei der Installation eines Funktions- oder Qualitätsupdates ein Problem auftritt, können Sie die Aktualisierung für 35 Tage (ab einem bestimmten Datum) anhalten. Durch diese Pause wird verhindert, dass das Update auf anderen Geräten installiert wird, bis Sie das Problem behoben oder Abhilfemaßnahmen ergriffen haben. Wenn Sie ein Featureupdate pausieren, werden den Geräten nach wie vor Qualitätsupdates bereitgestellt, um sicherzustellen, dass sie weiterhin sicher sind. Wenn ein Updatetyp pausiert wird, wird im Übersichtsbereich dieses Rings angezeigt, wie viele Tage noch verbleiben, bevor dieser Updatetyp fortgesetzt wird. Nach Ablauf des angegebenen Zeitraums wird die Pause automatisch aufgehoben und der Update-Vorgang fortgesetzt.

  Während der Updatering pausiert ist, können Sie eine der folgenden Optionen auswählen:

  - **Verlängern**: Pausendauer eines Updatetyps um 35 Tage verlängern.
  - **Fortsetzen**: Updates für diesen Ring wieder aktivieren. Sie können den Updatering bei Bedarf erneut anhalten.

  > [!NOTE]  
  > Der Vorgang zum **Deinstallieren** von Updateringen wird für HoloLens 2-Geräte nicht unterstützt.

## Manuell nach Updates suchen

Obwohl HoloLens regelmäßig nach Systemupdates sucht, kann es Situationen geben, in denen Sie dies manuell tun möchten.

Wenn Sie manuell nach Updates suchen möchten, wechseln Sie zu **Einstellungen** > **Update und Sicherheit** > **Nach Updates suchen**. Wenn die App "Einstellungen" anzeigt, dass Ihr Gerät auf dem neuesten Stand ist, sind alle Updates installiert, die aktuell verfügbar sind.

## Manuelles Zurücksetzen eines Updates

Es kann vorkommen, dass eine Rückkehr zu einer früheren Version der HoloLens-Software erforderlich ist. Die Vorgehensweise hierfür hängt davon ab, ob Sie HoloLens 2 oder HoloLens (1. Generation) verwenden.

### Zurückkehren zu einer vorherigen Version (HoloLens 2)

Sie können Updates zurücksetzen und zu einer früheren Version von HoloLens 2 zurückkehren, indem Sie [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) verwenden, um Ihre HoloLens auf die frühere Version zurückzusetzen.

> [!NOTE]
> Wenn Sie zu einer früheren Version zurückkehren, werden Ihre persönlichen Dateien und Einstellungen gelöscht.

Führen Sie die folgenden Schritte aus, um zu einer früheren Version von HoloLens 2 zurückzukehren:

1. Stellen Sie sicher, dass keine Smartphones oder Windows-Geräte an Ihren Computer angeschlossen sind.
1. Laden Sie [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) aus dem Microsoft Store auf Ihren Computer herunter.
1. Laden Sie die [neueste HoloLens 2-Version](https://aka.ms/hololens2download) herunter.
1. Öffnen Sie nachdem die Downloads abgeschlossen sind **Datei-Explorer** > **Downloads**, klicken Sie mit der rechten Maustaste auf den komprimierten (ZIP) Ordner, den Sie soeben heruntergeladen haben, und wählen Sie dann **Alle extrahieren** > **Extrahieren** aus, um die Datei zu dekomprimieren.
1. Verwenden Sie ein USB-A-zu-USB-C-Kabel, um Ihr HoloLens-Gerät an Ihren Computer anzuschließen. Auch wenn Sie Ihre HoloLens mit anderen Kabeln angeschlossen haben, funktioniert diese Art von Kabel am besten.
1. Advanced Recovery Companion erkennt Ihr HoloLens-Gerät automatisch. Wählen Sie die Kachel **Microsoft HoloLens** aus.
1. Wählen Sie im nächsten Bildschirm **Manuelle Paketauswahl** aus, und öffnen Sie dann den Ordner, den Sie zuvor dekomprimiert hatten.
1. Wählen Sie die Installationsdatei (FFU) aus.
1. Wählen Sie **Software installieren** aus, und folgen Sie den Anweisungen.

### Zurückkehren zu einer vorherigen Version (HoloLens (1. Generation))

Sie können Updates zurücksetzen und zu einer früheren Version von HoloLens (1. Generation) zurückkehren, indem Sie das [Windows Device Recovery-Tool (WDRT)](https://support.microsoft.com/help/12379) verwenden, um Ihre HoloLens auf die frühere Version zurückzusetzen.

> [!NOTE]
> Wenn Sie zu einer früheren HoloLens-Version zurückkehren, werden Ihre persönlichen Dateien und Einstellungen gelöscht.

Führen Sie die folgenden Schritte aus, um zu einer früheren Version von HoloLens (1. Generation) zurückzukehren:

1. Stellen Sie sicher, dass keine Smartphones oder Windows-Geräte an Ihren Computer angeschlossen sind.
1. Laden Sie das [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) auf Ihren Computer herunter.
1. Laden Sie das [HoloLens Anniversary Update-Wiederherstellungspaket](https://aka.ms/hololensrecovery) herunter.
1. Öffnen Sie nach dem Herunterladen **Datei-Explorer** > **Downloads**, klicken Sie mit der rechten Maustaste auf den komprimierten (ZIP) Ordner, den Sie soeben heruntergeladen haben, und wählen Sie dann **Alle extrahieren** > **Extrahieren** aus, um die Datei zu dekomprimieren.
1. Verwenden Sie das zusammen mit Ihrem HoloLens-Gerät gelieferte Micro-USB-Kabel, um das Gerät an Ihren Computer anzuschließen. Auch wenn Sie Ihr HoloLens-Gerät mit anderen Kabeln verbunden haben, funktioniert dieses am besten.
1. Das WDRT erkennt automatisch Ihr HoloLens-Gerät. Wählen Sie die Kachel **Microsoft HoloLens** aus.
1. Wählen Sie im nächsten Bildschirm **Manuelle Paketauswahl** aus, und öffnen Sie dann den Ordner, den Sie zuvor dekomprimiert hatten.
1. Wählen Sie die Installationsdatei (FFU) aus.
1. Wählen Sie **Software installieren** aus, und folgen Sie den Anweisungen.

**Wenn WDRT Ihr Gerät nicht erkennt**

Falls WDRT Ihr HoloLens-Gerät nicht erkennt, starten Sie Ihren Computer neu und versuchen Sie es erneut. Wenn das nicht funktioniert, wählen Sie **Mein Gerät wurde nicht erkannt** und anschließend **Microsoft HoloLens** aus, und folgen Sie dann den Anweisungen.

## Verwandte Artikel

- [Veröffentlichungshinweise für HoloLens 2](https://docs.microsoft.com/hololens/hololens-release-notes)
- [Was ist Windows Update for Business?](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Zuweisen von Geräten zu Servicing-Kanälen für Windows10-Updates](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Verwalten von Windows 10-Softwareupdates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
