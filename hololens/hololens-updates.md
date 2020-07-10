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
ms.date: 03/24/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: f8d0c788756b0a24ac8a26b8258b267483f1a890
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857753"
---
# Verwalten von HoloLens-Updates

HoloLens verwendet Windows Update auf die gleiche Weise wie andere Windows 10-Geräte. Wenn ein Update verfügbar ist, wird es automatisch heruntergeladen und installiert, wenn das Gerät das nächste Mal angeschlossen und mit dem Internet verbunden ist. In diesem Artikel wird beschrieben, wie Sie Updates in einem Unternehmen oder in einer anderen verwalteten Umgebung verwalten können. Informationen zum Verwalten von Updates für einzelne HoloLens-Geräte finden Sie unter [Aktualisieren von HoloLens](hololens-update-hololens.md).

## Automatische Verwaltung von Updates

Windows Holographic for Business kann [Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) für die Verwaltung von Updates verwenden. Alle HoloLens 2-Geräte können Windows Holographic for Business verwenden. Stellen Sie sicher, dass sie Windows Holographic for Business, Build 10.0.18362.1042 oder einen späteren Build verwenden. Wenn Sie über HoloLens-Geräte der 1. Generation verfügen, müssen Sie sie auf [Windows Holographic for Business upgraden](hololens1-upgrade-enterprise.md), um ihre Updates zu verwalten.

Windows Update for Business verbindet HoloLens-Geräte direkt mit dem Windows Update-Dienst. Mithilfe von Windows Update for Business können Sie mehrere Aspekte des Updateprozesses steuern&mdash;, d. h. welche Geräte welche Updates zu welchem Zeitpunkt erhalten. So können Sie z. B. Updates auf nur einem Teil der Geräte zu Testzwecken installieren, und zu einem späteren Zeitpunkt auch auf den verbleibenden Geräten. Oder Sie können unterschiedliche Aktualisierungszeitpläne für verschiedene Arten von Updates festlegen.

> [!NOTE]  
> Bei HoloLens-Geräten können Funktionsupdates (zwei Mal pro Jahr veröffentlicht) und Qualitätsupdates (monatlich oder nach Bedarf veröffentlicht, einschließlich kritischer Sicherheitsupdates) automatisch verwaltet werden. Weitere Informationen zu Updatetypen finden Sie unter [Von Windows Update for Business verwaltete Arten von Updates](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Sie können die Einstellungen für Windows Update for Business für HoloLens mithilfe von Richtlinien in einer MDM-Lösung (Mobile Device Management, Verwaltung mobiler Geräte) wie Microsoft Intune konfigurieren.

Einzelheiten zur Verwendung von Intune zum Konfigurieren von Windows Update for Business finden Sie unter [Verwalten von Windows 10-Softwareupdates in Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure).

> [!IMPORTANT]  
> Intune bietet zwei Richtlinientypen für die Verwaltung von Updates: *Windows 10-Updatering* und *Windows 10-Featureupdates*. Der Richtlinientyp "Windows 10-Featureupdates" ist derzeit in der öffentlichen Vorschau-Phase und wird für HoloLens nicht unterstützt.
>  
> Für die Verwaltung von HoloLens 2-Updates können Sie Windows 10 Updatering-Richtlinien verwenden.

### Konfigurieren von Update-Richtlinien für HoloLens 2 oder HoloLens (1. Generation)

In diesem Abschnitt werden die Richtlinien beschrieben, die Sie zur Verwaltung von Updates für HoloLens 2 oder HoloLens (1. Generation) verwenden können. Informationen zu zusätzlichen verfügbaren Funktionen für HoloLens 2 finden Sie unter [Planen und Konfigurieren von Update-Rollouts für HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).

Der [Konfigurationsdienstanbieter für Richtlinien (Policy Configuration Service Provider, CSP)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) definiert die Richtlinien, die Windows Update for Business konfigurieren.

> [!NOTE]  
> Ausführliche Informationen zu bestimmten Richtlinien, die von bestimmten Editionen von HoloLens unterstützt werden, finden Sie unter [Von HoloLens-Geräten unterstützte Richtlinien](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-hololens-devices).

#### Konfigurieren automatischer Überprüfungen auf Updates

Sie können die Richtlinie **Update/AllowAutoUpdate** verwenden, um automatische Updates zu verwalten, darunter das Suchen, Herunterladen und Installieren von Updates.

Diese Richtlinie unterstützt die folgenden Werte:

- **0**: Informieren des Benutzers, wenn ein Update für das Gerät verfügbar ist und heruntergeladen werden kann.
- **1**: Automatische Installation des Updates und anschließende Benachrichtigung des Benutzers, dass ein Geräteneustart geplant werden muss.  
- **2**: Automatische Installation des Updates und anschließender Neustart des Geräts. Dies ist der empfohlene Wert und zugleich der Standardwert für diese Richtlinie.  

- **3**: Automatische Installation des Updates und anschließender Neustart des Geräts zu einem bestimmten Zeitpunkt. Geben Sie den Installationstag und die Uhrzeit an. Wenn keine Tage und keine Uhrzeit angegeben werden, ist die Standardeinstellung täglich um 03:00 Uhr.  

- **4**: Automatische Installation des Updates und anschließender Neustart des Geräts. Mit dieser Option wird auch reiner Lesezugriff für die Seite "Einstellungen" festgelegt.

- **5**: Deaktivierung automatischer Updates.

Weitere Informationen zu den für diese Richtlinie verfügbaren Einstellungen finden Sie unter [Update-AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> In Microsoft Intune können Sie **Verhalten der automatischen Aktualisierung** verwenden, um diese Richtlinie zu ändern. Weitere Informationen finden Sie unter [Verwalten von Softwareupdates in Microsoft Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).

#### Konfigurieren eines Update-Zeitplans

Verwenden Sie die folgenden Richtlinien, um zu konfigurieren, wie und wann Updates angewendet werden sollen:

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday).  
   - Werte: **0**-**7** (0 = jeden Tag, 1 = Sonntag, 7 = Samstag)
   - Standardwert: **0** (jeden Tag)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime).
   - Werte: 0 - 23 (0 = Mitternacht; 23 = 23:00 Uhr)
   - Standardwert: 15:00 Uhr

#### Nur für Windows 10-Geräte, Version 1607

Mithilfe der folgenden Update-Richtlinien können Sie Geräte so konfigurieren, dass Updates vom Windows Server Update-Dienst (WSUS) anstelle von Windows Update abgerufen werden:

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### Planen und Konfigurieren von Update-Rollouts für HoloLens 2

HoloLens 2 unterstützt mehr Upadate-Automatisierungsfeatures als HoloLens (1. Generation). Dies gilt insbesondere, wenn Sie Microsoft Intune zum Verwalten von Windows Update for Business-Richtlinien verwenden. Mithilfe dieser Funktionen können Sie Update-Rollouts in der gesamten Organisation einfacher planen und umsetzen.

#### Planen der Updatestrategie

Windows Updates for Business unterstützt Zurückstellungsrichtlinien. Nachdem Microsoft ein Update veröffentlicht hat, können Sie mithilfe einer Zurückstellungsrichtlinie definieren, wie lange die Installation dieses Updates auf den Geräten verzögert werden soll. Sie können eine Update-Rollout-Strategie für Ihre Organisation koordinieren, indem Sie Teilmengen Ihrer Geräte (als *Updateringe* bezeichnet) unterschiedlichen Zurückstellungsrichtlinien zuordnen.

Gehen wir beispielsweise von einer Organisation mit 1.000 Geräten aus, die auf fünf Arten aktualisiert werden müssen. Die Organisation kann fünf Updateringe erstellen, wie in der folgenden Tabelle gezeigt.

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

Eine Zurückstellungsrichtlinie gibt die Anzahl der Tage zwischen dem Datum, an dem ein Update verfügbar wird, und dem Datum an, an dem das Update für ein Gerät bereitgestellt wird.

Sie können unterschiedliche Verzögerungen für Feature- und Qualitätsupdates festlegen. In der folgenden Tabelle sind die einzelnen Richtlinien aufgelistet, die für den jeweiligen Typ verwendet werden, sowie die jeweilige maximale Verzögerung.

|Kategorie |Richtlinie |Maximale Verzögerung |
| --- | --- | --- |
|Funktionsupdates |DeferFeatureUpdatesPeriodInDays |365 Tage |
|Qualitätsupdates |DeferQualityUpdatesPeriodInDays |30Tage |

####  Beispiele: Verwendung von Intune zum Verwalten von Updates

**Beispiel 1: Erstellen und Zuweisen eines Updaterings**

Eine detailliertere Version dieses Beispiels finden Sie unter [Erstellen und Zuweisen von Aktualisierungsringen](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

1. Melden Sie sich beim [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)an, und navigieren Sie zu Ihren Intune-Profilen.
1. Wählen Sie **Software-Updates** > **Windows 10-Updateringe** > **Erstellen** aus.
1. Geben Sie unter **Grundlagen**einen Namen und eine Beschreibung an (optional), und wählen Sie dann **Weiter** aus.
1. Wählen Sie unter **Updatering-Einstellungen** für **Servicing Channel****Halbjährlicher Kanal** aus, und ändern Sie dann den **Zurückstellungszeitraum für Featureupdates** zu **120**. Wählen Sie dann **Weiter** aus.
1. Wählen Sie unter **Zuweisungen** die Option **+ Einzuschließende Gruppen auswählen** aus, und weisen Sie dann den Updatering einer oder mehreren Gruppen zu. Unter **+ Auszuschließende Gruppen auswählen** können Sie die Zuweisungen optimal abstimmen. Wählen Sie dann **Weiter** aus.
1. Überprüfen Sie die Einstellungen unter **Überprüfen und erstellen**. Wählen Sie abschließend zum Speichern der Updatering-Konfiguration **Erstellen** aus.

Die Liste der Aktualisierungsringe umfasst nun den neuen Windows 10-Updatering.

**Beispiel 2: Pausieren eines Updaterings**

Wenn bei der Installation eines Feature- oder Qualitätsupdates ein Problem auftritt, können Sie die Aktualisierung für 35 Tage (ab einem bestimmten Datum) anhalten. Durch diese Pause wird verhindert, dass das Update auf anderen Geräten installiert wird, bis Sie das Problem behoben oder Abhilfemaßnahmen ergriffen haben. Wenn Sie ein Featureupdate pausieren, werden den Geräten nach wie vor Qualitätsupdates bereitgestellt, um sicherzustellen, dass sie weiterhin sicher sind. Nach Ablauf des angegebenen Zeitraums wird die Pause automatisch aufgehoben. Der Aktualisierungsvorgang wird ab diesem Zeitpunkt fortgesetzt.

Führen Sie die folgenden Schritte aus, um einen Aktualisierungsring in Intune zu pausieren:

1. Wählen Sie auf der Übersichtsseite für den Updatering **Pausieren** aus.
1. Wählen Sie den Updatetyp (**Feature** oder **Qualität**) und dann **OK**aus.

Wenn ein Updatetyp pausiert wird, wird im Übersichtsbereich dieses Rings angezeigt, wie viele Tage noch verbleiben, bevor dieser Updatetyp fortgesetzt wird.

Während der Updatering pausiert ist, können Sie eine der folgenden Optionen auswählen:

- Wenn Sie die Pausendauer für einen Updatetyp auf 35 Tage verlängern möchten, wählen Sie **Verlängern** aus.
- Wählen Sie **Fortsetzen** aus, um Updates für diesen Ring wieder zu aktivieren. Sie können den Updatering bei Bedarf erneut anhalten.

> [!NOTE]  
> Der Vorgang zum **Deinstallieren** von Updateringen wird für HoloLens 2-Geräte nicht unterstützt.

## Manuell nach Updates suchen

Obwohl HoloLens regelmäßig nach Systemupdates sucht, kann es Situationen geben, in denen Sie dies manuell tun möchten.

Wenn Sie manuell nach Updates suchen möchten, wechseln Sie zu **Einstellungen** > **Update und Sicherheit** > **Nach Updates suchen**. Wenn die App "Einstellungen" anzeigt, dass Ihr Gerät auf dem neuesten Stand ist, sind alle Updates installiert, die aktuell verfügbar sind.

## Manuelles Zurücksetzen eines Updates

Es kann vorkommen, dass eine Rückkehr zu einer früheren Version der HoloLens-Software erforderlich ist. Die Vorgehensweise hierfür hängt davon ab, ob Sie HoloLens 2 oder HoloLens (1. Generation) verwenden.

### Zurückkehren zu einer vorherigen Version (HoloLens 2)

Sie können Updates zurücksetzen und zu einer früheren Version von HoloLens 2 zurückkehren, indem Sie Advanced Recovery Companion verwenden, um Ihre HoloLens auf die frühere Version zurückzusetzen.

> [!NOTE]
> Wenn Sie zu einer früheren Version zurückkehren, werden Ihre persönlichen Dateien und Einstellungen gelöscht.

Führen Sie die folgenden Schritte aus, um zu einer früheren Version von HoloLens 2 zurückzukehren:

1. Stellen Sie sicher, dass keine Smartphones oder Windows-Geräte an Ihren Computer angeschlossen sind.
1. Laden Sie [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) aus dem Microsoft Store auf Ihren Computer herunter.
1. Laden Sie die [neueste HoloLens 2-Version](https://aka.ms/hololens2download) herunter.
1. Öffnen Sie nach Abschluss des Downloads **Datei-Explorer** > **Downloads**, klicken Sie mit der rechten Maustaste auf den komprimierten (gezippten) Ordner, den Sie soeben heruntergeladen haben, und wählen Sie dann **Alle extrahieren** > **Extrahieren** aus, um die Datei zu dekomprimieren.
1. Verwenden Sie ein USB-A-zu-USB-C-Kabel, um Ihr HoloLens-Gerät an Ihren Computer anzuschließen. Auch wenn Sie Ihre HoloLens mit anderen Kabeln angeschlossen haben, funktioniert diese Art von Kabel am besten.
1. Advanced Recovery Companion erkennt Ihr HoloLens-Gerät automatisch. Wählen Sie die Kachel **Microsoft HoloLens** aus.
1. Wählen Sie im nächsten Bildschirm **Manuelle Paketauswahl** aus, und öffnen Sie dann den Ordner, den Sie zuvor dekomprimiert hatten. 
1. Wählen Sie die Installationsdatei (die Datei mit der Erweiterung .ffu) aus.
1. Wählen Sie **Software installieren** aus, und folgen Sie den Anweisungen.

### Zurückkehren zu einer vorherigen Version (HoloLens (1. Generation))

Sie können Updates zurücksetzen und zu einer früheren Version von HoloLens (1. Generation) zurückkehren, indem Sie das Windows Device Recovery-Tool verwenden, um Ihre HoloLens auf die frühere Version zurückzusetzen.

> [!NOTE]
> Wenn Sie zu einer früheren Version zurückkehren, werden Ihre persönlichen Dateien und Einstellungen gelöscht.

Führen Sie die folgenden Schritte aus, um zu einer früheren Version von HoloLens (1. Generation) zurückzukehren:

1. Stellen Sie sicher, dass keine Smartphones oder Windows-Geräte an Ihren Computer angeschlossen sind.
1. Laden Sie das [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) auf Ihren Computer herunter.
1. Laden Sie das [HoloLens Anniversary Update-Wiederherstellungspaket](https://aka.ms/hololensrecovery) herunter.
1. Öffnen Sie nach Abschluss des Downloads **Datei-Explorer** > **Downloads**, klicken Sie mit der rechten Maustaste auf den komprimierten (gezippten) Ordner, den Sie soeben heruntergeladen haben, und wählen Sie dann **Alle extrahieren** > **Extrahieren** aus, um die Datei zu dekomprimieren.
1. Verwenden Sie das zusammen mit Ihrem HoloLens-Gerät gelieferte Micro-USB-Kabel, um das Gerät an Ihren Computer anzuschließen. Auch wenn Sie Ihr HoloLens-Gerät mit anderen Kabeln verbunden haben, funktioniert dieses am besten.
1. Das WDRT erkennt automatisch Ihr HoloLens-Gerät. Wählen Sie die Kachel **Microsoft HoloLens** aus.
1. Wählen Sie im nächsten Bildschirm **Manuelle Paketauswahl** aus, und öffnen Sie dann den Ordner, den Sie zuvor dekomprimiert hatten. 
1. Wählen Sie die Installationsdatei (die Datei mit der Erweiterung .ffu) aus.
1. Wählen Sie **Software installieren** aus, und folgen Sie den Anweisungen.

> [!NOTE]
> Falls das WDRT Ihr HoloLens-Gerät nicht erkennt, versuchen Sie, Ihren Computer neu zu starten. Wenn das nicht funktioniert, wählen Sie **Mein Gerät wurde nicht erkannt** und anschließend **Microsoft HoloLens** aus, und folgen Sie dann den Anweisungen.

## Verwandte Artikel

- [Bereitstellen von Updates mit Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Zuweisen von Geräten zu Servicing-Kanälen für Windows10-Updates](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Verwalten von Windows 10-Softwareupdates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
