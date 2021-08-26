---
title: Einrichten von HoloLens als Kiosk
description: Erfahren Sie, wie Sie eine Kioskkonfiguration einrichten und verwenden, um die Apps auf HoloLens sperren.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: daab30a8ea5200ca145b6b0234b8bd060b8cec5f
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859106"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Einrichten von HoloLens als Kiosk

## <a name="what-is-kiosk-mode"></a>Was ist der Kioskmodus?

Der Kioskmodus ist ein Feature, mit dem Sie steuern können, welche Anwendungen im Startmenü angezeigt werden, wenn sich ein Benutzer bei einem HoloLens. Es gibt zwei unterstützte Szenarien:

1. **Kioskmodus für einzelne Apps:** Es wird kein Startmenü angezeigt, und eine einzelne App wird automatisch gestartet, wenn sich der Benutzer an diesem Gerät anknappt. <br> *Im Beispiel wird* verwendet: Ein Gerät, das nur Dynamics 365 Guides ausgeführt wird.
2. **Kioskmodus für mehrere** Apps: Startmenü zeigt nur die Anwendungen an, die bei der Anmeldung eines Benutzers in der Kioskkonfiguration angegeben wurden. Eine App kann bei Wunsch automatisch gestartet werden. <br> *Im Beispiel wird* verwendet: Ein Gerät, das nur die Store-App, Feedback-Hub und Einstellungen-App im Startmenü zeigt.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>Beschreibung der Kioskmoduserfahrung bei der Benutzerbenutzeroberfläche

In der folgenden Tabelle sind die Featurefunktionen in den verschiedenen Kioskmodi aufgeführt.

| &nbsp; |Startmenü |Menü "Schnellaktionen" |Kamera und Video |Miracast |Cortana |Integrierte Sprachbefehle |
| --- | --- | --- | --- | --- | --- | --- |
|Kiosk mit nur einer App |Disabled |Disabled |Disabled |Disabled   |Disabled |Aktiviert* |
|Kiosk mit mehreren Apps |Aktiviert |Aktiviert*  |Verfügbar*  |Verfügbar* |Verfügbar*   |Aktiviert*  |

Weitere Informationen zum Aktivieren deaktivierter Features oder zur Interaktion von Sprachbefehlen mit deaktivierten Features und Cortana finden Sie unter HoloLens [AUMIDs für Apps.](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>Wichtige allgemeine Überlegungen vor dem Konfigurieren des Kioskmodus

1. Bestimmen Sie die Art der Anmeldung bei Hololens in Ihrer Umgebung: HoloLens unterstützt Azure Active Directory-Konten (AAD), Microsoft-Konten (MSA) und Lokale Konten. Darüber hinaus werden vorübergehend erstellte Konten mit dem Namen "Gäste/Besucher" ebenfalls unterstützt (nur für AAD-Joingeräte). Weitere Informationen finden [Sie unter Verwalten der Benutzeridentität und Anmeldung für HoloLens](hololens-identity.md).
2. Bestimmen sie die Ziele der Kioskmoduserfahrung: Ob es sich um alle Benutzer, einen einzelnen Benutzer, bestimmte Benutzer oder Benutzer handelt, die Mitglied von AAD-Gruppen sind usw.
3. Legen Sie für den Kioskmodus mit mehreren Apps fest, dass die Anwendungen im Startmenü angezeigt werden. Für jede Anwendung wird die [Anwendungsbenutzermodell-ID (AUMID)](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) benötigt.
4. Bestimmen Sie, ob der Kioskmodus auf HoloLens laufzeitbereitstellungspakete oder mobile Geräteverwaltung (MDM)-Server angewendet wird.

## <a name="security-considerations"></a>Sicherheitsüberlegungen

Der Kioskmodus sollte nicht als Sicherheitsmethode betrachtet werden, sondern als Mittel zur Steuerung der Starterfahrung bei der Benutzer anmeldung. Sie können die Kioskmoduserfahrung mit den unten genannten Optionen kombinieren, wenn bestimmte sicherheitsbezogene Anforderungen erfüllt sind:

- Wenn Einstellungen-App so konfiguriert ist, dass sie im Kioskmodus angezeigt wird, und Sie steuern möchten, welche Seiten in der Einstellungen-App angezeigt werden, finden Sie weitere Informationen unter [Einstellungen Sichtbarkeit.](settings-uri-list.md)
- Wenn Sie den Zugriff auf bestimmte Hardwarefunktionen steuern möchten, z. B. Kamera, Bluetooth usw. für bestimmte Apps, finden Sie weitere Informationen unter Richtlinien [in Richtlinien-CSP,](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2)die von HoloLens 2 unterstützt werden – Windows ClientVerwaltung . Ideen finden Sie unter [Allgemeine Geräteeinschränkungen.](hololens-common-device-restrictions.md)
- Der Kioskmodus blockiert nicht, dass eine App (die als Teil der Kioskerfahrung konfiguriert ist) andere Apps startet. Wenn Sie den Start bestimmter Apps/Prozesse auf HoloLens vollständig blockieren möchten, lesen Sie Verwenden der Windows Defender-Anwendungssteuerung auf HoloLens 2-Geräten [in Microsoft Intune – Azure.](/mem/intune/configuration/custom-profile-hololens)

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>Wichtige technische Überlegungen zum Kioskmodus für HoloLens

Gilt nur, wenn Sie planen, Laufzeitbereitstellungspakete zu verwenden oder Kioskkonfigurationen manuell selbst zu erstellen. Die Kioskmoduskonfiguration verwendet eine hierarchische Struktur, die auf XML basiert:

- Ein zugewiesenes Zugriffsprofil definiert, welche Anwendungen im Startmenü im Kioskmodus angezeigt werden. Sie können mehrere Profile in derselben XML-Struktur definieren, auf die später verwiesen werden kann.
- Eine zugewiesene Zugriffskonfiguration verweist auf ein Profil und zielbenutzer dieses Profils, z. B. einen bestimmten Benutzer, eine AAD-Gruppe oder einen Besucher usw. Abhängig von der Komplexität Ihrer Verwendungsszenarien können Sie mehrere Konfigurationen in derselben XML-Struktur definieren (siehe Abschnitt unterstützte Szenarien weiter unten).
- Weitere Informationen finden Sie unter [AssignedAccess CSP](/windows/client-management/mdm/assignedaccess-csp).

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Unterstützte Szenarien für den Kioskmodus basierend auf dem Identitätstyp

> [!NOTE]
> Verwenden Sie XML nur, wenn Sie die Benutzeroberfläche von Intune nicht zum Erstellen der Kioskkonfiguration verwenden.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>Für Benutzer, die sich entweder als lokales Konto oder MSA anmelden

| **Gewünschte Kioskerfahrung** | **Empfohlene Kioskkonfiguration** | **Möglichkeiten zum Konfigurieren**  | **Anmerkungen** |
| --- | --- | --- | --- |
| Jeder Benutzer, der sich an einem Kiosk ankn.) | [Konfigurieren eines Profils für den global zugewiesenen Zugriff für mehrere Apps](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune benutzerdefinierte Vorlage](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Laufzeitbereitstellung – Mehrere Apps](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Global zugewiesener Zugriff erfordert [20H2 und neuere Builds.](hololens-release-notes.md#windows-holographic-version-20h2) |
| Ein bestimmter Benutzer, der sich an diesem Computer ankn., erhält eine Kioskerfahrung.  | [Konfigurieren Sie ein oder mehrere app-zugewiesene Zugriffsprofile (nach Bedarf), und geben Sie dabei den Namen eines bestimmten Benutzers an.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [Weitere Informationen finden Sie weiter unten in den unterstützten Optionen.](#steps-in-configuring-kiosk-mode-for-hololens) | Für den Kioskmodus einer einzelnen App wird nur ein lokales Benutzerkonto oder ein MSA-Konto auf HoloLens. <br> Für den Kioskmodus mit mehreren Apps wird nur das MSA-Konto oder das AAD-Konto auf HoloLens. |

### <a name="for-users-who-sign-in-as-aad-account"></a>Für Benutzer, die sich als AAD-Konto anmelden

| **Gewünschte Kioskerfahrung** | **Empfohlene Kioskkonfiguration** | **Möglichkeiten zum Konfigurieren** | **Anmerkungen** |
| --- | --- | --- | --- |
| Jeder Benutzer, der sich an einem Kiosk ankn.) | [Konfigurieren eines Profils für den global zugewiesenen Zugriff für mehrere Apps](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune benutzerdefinierte Vorlage](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Laufzeitbereitstellung – Mehrere Apps](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Global zugewiesener Zugriff erfordert [20H2 und neuere Builds.](hololens-release-notes.md#windows-holographic-version-20h2) |
| Mit Ausnahme bestimmter Benutzer erhält jeder Benutzer, der sich an einem Kiosk ankn., eine Kioskerfahrung. | [Konfigurieren Sie mehrere Global Assigned Access-Profile für apps, indem Sie](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners)bestimmte Benutzer ausschließen (die Gerätebesitzer sein müssen). | • [Microsoft Intune benutzerdefinierte Vorlage](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Laufzeitbereitstellung – Mehrere Apps](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Global zugewiesener Zugriff erfordert [20H2 und neuere Builds.](hololens-release-notes.md#windows-holographic-version-20h2) |
| Jeder AAD-Benutzer erhält eine separate Kioskerfahrung, die für diesen Benutzer spezifisch ist. | [Konfigurieren Sie die Konfiguration des zugewiesenen Zugriffs für jeden Benutzer, und geben Sie dabei den Namen des AAD-Kontos an.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune benutzerdefinierte Vorlage](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Laufzeitbereitstellung – Mehrere Apps](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| Benutzer in verschiedenen AAD-Gruppen verfügen über den Kioskmodus, der nur für ihre Gruppe gilt. | [Konfigurieren Sie die zugewiesene Zugriffskonfiguration für jede gewünschte AAD-Gruppe.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune benutzerdefinierte Vorlage](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Laufzeitbereitstellung – Mehrere Apps](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • Wenn ein Benutzer sich an- und HoloLens mit dem Internet verbunden ist und dieser Benutzer mitglied der AAD-Gruppe ist, für die eine Kioskkonfiguration vorhanden ist, wird dem Benutzer ein Kiosk für diese AAD-Gruppe angezeigt. <br> • [Wenn bei der Benutzeranmelde-Anmeldung](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) kein Internet verfügbar ist, tritt HoloLens Verhalten im Fehlermodus auf. <br> • Wenn die Internetverfügbarkeit nicht garantiert wird, wenn sich der Benutzer an- und ein gruppenbasierter AAD-Kiosk verwenden muss, sollten Sie die Verwendung von [AADGroupMembershipCacheValidityInDayspolicy in Erwägung ziehen.](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk) |
| Benutzer, die HoloLens für temporäre Zwecke verwenden müssen, erhalten kioskerfahrung. | [Konfigurieren der Konfiguration des zugewiesenen Zugriffs für Besucher](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune benutzerdefinierte Vorlage](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Laufzeitbereitstellung – Einzelne App](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • Ein temporäres Benutzerkonto wird automatisch von HoloLens bei der Anmeldung erstellt und entfernt, wenn sich ein temporärer Benutzer abmeldet. <br> • Erwägen Sie, die [Richtlinie für die automatische Anmeldung von Besucher zu aktivieren.](#how-to-can-visitor-accounts-automatically-logon-into-kiosk-experience) |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>Schritte zum Konfigurieren des Kioskmodus für HoloLens

Kioskkonfigurationen können auf folgende Weise erstellt und angewendet werden:

1. Mit der Benutzeroberfläche des MDM-Servers, z. B. den Kioskvorlagen von Intune oder benutzerdefinierten OMA-URI-Konfigurationen, die dann remote auf die HoloLens.
2. Mit Laufzeitbereitstellungspaketen, die dann direkt auf die HoloLens.

Wählen Sie im Folgenden die folgenden Konfigurationsmöglichkeiten aus, und wählen Sie die Registerkarte aus, die mit dem Prozess übereinstimmen soll, den Sie verwenden möchten.

1. [Microsoft Intune Einer-App-Kioskvorlage](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune Kioskvorlage für mehrere Apps](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune benutzerdefinierte Vorlage](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [Laufzeitbereitstellung : Mehrere Apps](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Laufzeitbereitstellung : Einzelne App](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="how-to-can-visitor-accounts-automatically-logon-into-kiosk-experience"></a>Wie können sich Besucherkonten automatisch bei der Kioskerfahrung anmelden?

Auf Builds [Windows Holographic, Version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) und ab:

- AAD- und Nicht-ADD-Konfigurationen unterstützen die automatische Anmeldung von Besucherkonten für Kioskmodi.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>Wird die Kioskerfahrung auf Hololens (1. Generation) unterstützt?

Der Kioskmodus ist nur verfügbar, wenn das Gerät Windows Holographic for Business. Alle HoloLens 2-Geräte werden mit Windows Holographic for Business, und es gibt keine anderen Editionen. Jedes HoloLens 2 Gerät kann den Kioskmodus vor der Box ausführen.

HoloLens -Geräten (1. Generation) müssen sowohl im Hinblick auf den Betriebssystem-Build als auch auf die Betriebssystemversion aktualisiert werden. Hier finden Sie weitere Informationen zum Aktualisieren eines HoloLens (1. Generation) auf [Windows Holographic for Business](hololens1-upgrade-enterprise.md) Edition. Um ein HoloLens-Gerät (1. Generation) für die Verwendung des Kioskmodus zu aktualisieren, müssen Sie zunächst sicherstellen, dass das Gerät Windows 10, Version 1803 oder höher, ausgeführt wird. Wenn Sie das Windows Device Recovery Tool verwendet haben, um Ihr HoloLens-Gerät (1. Generation) auf dem Standard-Build wiederhergestellt zu haben, oder wenn Sie die neuesten Updates installiert haben, kann Ihr Gerät konfiguriert werden.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>Verwenden des Geräteportals zum Konfigurieren eines Kiosks in Nicht-Produktionsumgebungen

Richten Sie das [HoloLens für die Verwendung des Windows Geräteportal.](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) Das Geräteportal ist ein Webserver auf der HoloLens, mit dem Sie über einen Webbrowser auf dem PC eine Verbindung herstellen können.

 > [!CAUTION]
 > Wenn Sie einen HoloLens für die Geräteportal einrichten, müssen Sie den Entwicklermodus auf dem Gerät aktivieren. Im Entwicklermodus auf einem Gerät mit Windows Holographic for Business können Sie Apps seitlich laden. Diese Einstellung stellt jedoch das Risiko dar, dass ein Benutzer Apps installieren kann, die nicht vom Benutzer zertifiziert Microsoft Store. Administratoren können die Möglichkeit zum Aktivieren des Entwicklermodus blockieren, indem sie die **Einstellung ApplicationManagement/AllowDeveloper Unlock** im [Richtlinien-CSP verwenden.](/windows/client-management/mdm/policy-configuration-service-provider) [Weitere Informationen zum Entwicklermodus](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

Der Kioskmodus kann über die REST-API von Geräteportal festgelegt werden, indem post to /api/holographic/kioskmode/settings mit einem erforderlichen Abfragezeichenfolgenparameter ("kioskModeEnabled" mit dem Wert "true" oder "false") und einem optionalen Parameter ("startupApp" mit einem Wert eines Paketnamens) ausgeführt wird. Beachten Sie, dass Geräteportal nur für Entwickler vorgesehen ist und nicht auf Nicht-Entwicklergeräten aktiviert werden sollte. Die REST-API kann sich in zukünftigen Updates/Releases ändern.

## <a name="troubleshooting"></a>Problembehandlung

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>Problem: Im Startmenü im Kioskmodus werden keine Apps angezeigt?

**Symptome**

Wenn beim Anwenden des Kioskmodus Fehler auftreten, wird das folgende Verhalten angezeigt:

- Vor der Windows Holographic, Version 20H2 – HoloLens werden alle Anwendungen in der Startmenü.
- Windows Holographic, Version 20H2: Wenn ein Gerät über eine Kioskkonfiguration verfügt, bei der es sich um eine Kombination aus global zugewiesenem Zugriff und zugewiesenem Zugriff für AAD-Gruppenmitglied handelt, wird dem Benutzer das Menü "Im Startmenü wird nichts angezeigt" angezeigt, wenn die Bestimmung der AAD-Gruppenmitgliedschaft fehlschlägt.

    ![Abbildung des Kioskmodus, der jetzt aussieht, wenn ein Fehler auftritt.](images/hololens-kiosk-failure-behavior.png )

- Ab Windows [Holographic Version 21H1](hololens-release-notes.md#windows-holographic-version-21h1)sucht der Kioskmodus nach global zugewiesenem Zugriff, bevor ein leeres Startmenü angezeigt wird. Die Kioskerfahrung wird auf eine globale Kioskkonfiguration (falls vorhanden) zurückfallen, wenn während des Kioskmodus der AAD-Gruppe Fehler vorhanden sind.

**Schritte zur Problembehandlung**

- Stellen Sie sicher, dass AUMID der App richtig angegeben ist und keine Versionen enthält. Beispiele finden [HoloLens AUMIDs](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) für Posteingangs-Apps.
- Stellen Sie sicher, dass die Anwendung für diesen Benutzer auf dem Gerät installiert ist.
- Wenn die Kioskkonfiguration auf AAD-Gruppen basiert, stellen Sie sicher, dass bei der AAD-Benutzeranbindung eine Internetverbindung vorhanden ist. Konfigurieren Sie bei Wunsch [die Richtlinie MixedReality/AADGroupMembershipCacheValidityInDays,](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) damit diese auch ohne Internet funktionieren kann.

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>Problem: Fehler beim Erstellen eines Pakets im Kioskmodus

**Symptome**

Ein Dialogfeld wie unten wird angezeigt.

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**Schritte zur Problembehandlung**

1. Klicken Sie auf den Hyperlink, der im obigen Dialogfeld angezeigt wird.
1. Öffnen Sie ICD.log in einem Text-Editor, und sein Inhalt sollte auf den Fehler hinweisen.

> [!NOTE]
> Wenn Sie mehrere Versuche unternommen haben, überprüfen Sie die Zeitstempel im Protokoll. Dadurch können Sie nur die aktuellen Probleme überprüfen.

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>Problem: Das Bereitstellungspaket wurde erfolgreich erstellt, konnte aber nicht angewendet werden.

**Symptome**

Fehler beim Anwenden des Bereitstellungspakets auf Hololens

**Schritte zur Problembehandlung**

1. Navigieren Sie zu dem Ordner, in dem Windows Configuration Designer-Projekt für das Laufzeitbereitstellungspaket vorhanden ist.
1. Öffnen Sie ICD.log, und stellen Sie sicher, dass beim Erstellen des Bereitstellungspakets keine Fehler im Protokoll enthalten sind. Einige Fehler werden während der Erstellung nicht angezeigt, werden aber weiterhin in ICD.log protokolliert.

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>Problem: Mehrere App zugewiesener Zugriff auf die AAD-Gruppe funktioniert nicht

**Symptome**

Bei der AAD-Benutzer-Anmeldung wird das Gerät nicht in den Kioskmodus wechseln.

**Schritte zur Problembehandlung**

- Vergewissern Sie sich in Der KONFIGURATIONS-XML-Code für den zugewiesenen Zugriff, dass die GUID der AAD-Gruppe verwendet wird, deren Mitglied der angemeldete Benutzer ist, und nicht die GUID des AAD-Benutzers.
- Vergewissern Sie sich im Intune-Portal, dass der AAD-Benutzer tatsächlich als Mitglied der AAD-Zielgruppe angezeigt wird.
