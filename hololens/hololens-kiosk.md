---
title: Einrichten von HoloLens als Kiosk
description: Erfahren Sie, wie Sie eine Kioskkonfiguration einrichten und verwenden, um die Apps auf HoloLens Geräten zu sperren.
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
ms.openlocfilehash: e8f269a3793a5e61eb3eb4b88084a5e4af375ffa
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351718"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Einrichten von HoloLens als Kiosk

## <a name="what-is-kiosk-mode"></a>Was ist der Kioskmodus?

Der Kioskmodus ist ein Feature, mit dem Sie steuern können, welche Anwendungen im Startmenü angezeigt werden, wenn sich ein Benutzer bei HoloLens anmeldet. Es gibt zwei unterstützte Szenarien:

1. **Einzel-App-Kioskmodus:** Es wird kein Startmenü angezeigt, und eine einzelne App wird automatisch gestartet, wenn sich der Benutzer anmeldet. <br> *Beispiel verwendet*: Ein Gerät, das nur Dynamics 365 Guides App ausgeführt wird.
2. **Kioskmodus** für mehrere Apps: Startmenü werden nur die Anwendungen angezeigt, die bei der Benutzeranmeldung in der Kioskkonfiguration angegeben wurden. Eine App kann bei Bedarf automatisch gestartet werden. <br> *Beispiel verwendet*: Ein Gerät, das nur die Store App, Feedback-Hub und Einstellungen App im Startmenü anzeigt.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>Beschreibung der Kioskmodusbenutzeroberfläche bei der Benutzerbenutzeroberfläche

In der folgenden Tabelle sind die Featurefunktionen in den verschiedenen Kioskmodi aufgeführt.

| &nbsp; |Startmenü |Menü "Schnelle Aktionen" |Kamera und Video |Miracast |Cortana |Integrierte Sprachbefehle |
| --- | --- | --- | --- | --- | --- | --- |
|Kiosk mit einzelner App |Disabled |Disabled |Disabled |Disabled   |Disabled |Aktiviert* |
|Kiosk mit mehreren Apps |Aktiviert |Aktiviert*  |Verfügbar*  |Verfügbar* |Verfügbar*   |Aktiviert*  |

\*Weitere Informationen zum Aktivieren deaktivierter Features oder zur Interaktion von Sprachbefehlen mit deaktivierten Features und Cortana finden Sie unter [HoloLens AUMIDs für Apps.](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>Wichtige allgemeine Überlegungen vor dem Konfigurieren des Kioskmodus

1. Bestimmen Sie die Art des Benutzerkontos, das sich in Ihrer Umgebung bei HoloLens anmeldet– HoloLens unterstützt Azure Active Directory -Konten (AAD), Microsoft-Konten (MSA) und lokale Konten. Darüber hinaus werden vorübergehend erstellte Konten, die als Gäste/Besucher bezeichnet werden, ebenfalls unterstützt (nur für AAD Geräte beitreten). Weitere Informationen finden Sie unter [Verwalten der Benutzeridentität und Anmeldung für HoloLens](hololens-identity.md).
2. Bestimmen sie die Ziele der Kioskmodus-Benutzeroberfläche– ob es sich um einen Einzelnen, einen einzelnen Benutzer, bestimmte Benutzer oder Benutzer handelt, die Mitglied AAD Gruppe(en) sind usw.
3. Legen Sie für den Kioskmodus für mehrere Apps fest, welche Anwendungen im Startmenü angezeigt werden sollen. Für jede Anwendung wird die [ZUGEHÖRIGE BENUTZERMODELL-ID (Application User Model ID, AUMID)](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) benötigt.
4. Bestimmen Sie, ob der Kioskmodus auf HoloLens über Laufzeitbereitstellungspakete oder mobile Geräteverwaltung(MDM)-Server angewendet wird.

## <a name="security-considerations"></a>Sicherheitshinweise

Der Kioskmodus sollte nicht als Sicherheitsmethode betrachtet werden, sondern als Mittel zum Steuern der Starterfahrung bei der Benutzeranmeldung. Sie können die Kioskmodus-Benutzeroberfläche mit den unten genannten Optionen kombinieren, wenn bestimmte sicherheitsbezogene Anforderungen bestehen:

- Wenn Einstellungen App so konfiguriert ist, dass sie im Kioskmodus angezeigt wird, und Sie steuern möchten, welche Seiten in Einstellungen App angezeigt werden, lesen Sie [Seite Einstellungen Sichtbarkeit.](settings-uri-list.md)
- Wenn Sie den Zugriff auf bestimmte Hardwarefunktionen wie Kamera, Bluetooth usw. für bestimmte Apps usw. steuern möchten, lesen Sie [Richtlinien in Richtlinien-CSP, der von HoloLens 2 unterstützt wird](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2)– Windows Clientverwaltung . Weitere Informationen finden Sie unter [Allgemeine Geräteeinschränkungen.](hololens-common-device-restrictions.md)
- Der Kioskmodus verhindert nicht, dass eine App (die als Teil der Kioskerfahrung konfiguriert ist) andere Apps startet. Wenn Sie den Start bestimmter Apps/Prozesse auf HoloLens vollständig blockieren möchten, lesen [Sie Verwenden von Windows Defender Anwendungssteuerung auf HoloLens 2 Geräten in Microsoft Intune – Azure.](/mem/intune/configuration/custom-profile-hololens)

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>Wichtige technische Überlegungen zum Kioskmodus für HoloLens

Gilt nur, wenn Sie planen, Laufzeitbereitstellungspakete zu verwenden oder Kioskkonfigurationen manuell selbst zu erstellen. Die Konfiguration des Kioskmodus verwendet eine hierarchische Struktur, die auf XML basiert:

- Ein zugewiesenes Zugriffsprofil definiert, welche Anwendungen im Startmenü im Kioskmodus angezeigt werden. Sie können mehrere Profile in derselben XML-Struktur definieren, auf die später verwiesen werden kann.
- Eine zugewiesene Zugriffskonfiguration verweist auf ein Profil und die Zielbenutzer dieses Profils, z. B. einen bestimmten Benutzer oder AAD Gruppe oder Besucher usw. Sie können abhängig von der Komplexität Ihrer Verwendungsszenarien mehrere Konfigurationen in derselben XML-Struktur definieren (siehe Abschnitt unterstützte Szenarien weiter unten).
- Weitere Informationen finden Sie unter [AssignedAccess CSP](/windows/client-management/mdm/assignedaccess-csp).

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Unterstützte Szenarien für den Kioskmodus basierend auf dem Identitätstyp

Unter [Referenzlinks](hololens-kiosk-reference.md#kiosk-xml-code-samples) finden Sie Beispiele, die auf Ihrem Szenario basieren, und aktualisieren Sie nach Bedarf vor dem Kopieren und Einfügen.

> [!NOTE]
> Verwenden Sie XML nur, wenn Sie die Intune-Benutzeroberfläche nicht zum Erstellen der Kioskkonfiguration verwenden.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>Für Benutzer, die sich entweder als lokales Konto oder als MSA anmelden

| **Gewünschte Kioskerfahrung** | **Empfohlene Kioskkonfiguration** | **Möglichkeiten zum Konfigurieren**  | **Anmerkungen** |
| --- | --- | --- | --- |
| Jeder Benutzer, der sich anmeldet, erhält Kioskerfahrung. | [Konfigurieren eines Global Assigned Access-Profils für mehrere Apps](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune benutzerdefinierte Vorlage](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Laufzeitbereitstellung – Mehrere Apps](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Global zugewiesener Zugriff erfordert [20H2 und neuere Builds](hololens-release-notes.md#windows-holographic-version-20h2) |
| Ein bestimmter Benutzer, der sich anmeldet, erhält Kioskerfahrung.  | [Konfigurieren Sie ein oder mehrere app-zugewiesene Zugriffsprofile (sofern erforderlich), und geben Sie dabei den Namen eines bestimmten Benutzers an.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [Weitere Informationen finden Sie weiter unten unter unterstützte Optionen.](#steps-in-configuring-kiosk-mode-for-hololens) | Für den Kioskmodus einer einzelnen App wird nur ein lokales Benutzerkonto oder MSA-Konto auf HoloLens unterstützt. <br> Für den Kioskmodus mehrerer Apps wird nur ein MSA-Konto oder AAD-Konto auf HoloLens unterstützt. |

### <a name="for-users-who-sign-in-as-aad-account"></a>Für Benutzer, die sich als AAD Konto anmelden

| **Gewünschte Kioskerfahrung** | **Empfohlene Kioskkonfiguration** | **Möglichkeiten zum Konfigurieren** | **Anmerkungen** |
| --- | --- | --- | --- |
| Jeder Benutzer, der sich anmeldet, erhält Kioskerfahrung. | [Konfigurieren eines Global Assigned Access-Profils für mehrere Apps](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune benutzerdefinierte Vorlage](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Laufzeitbereitstellung – Mehrere Apps](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Global zugewiesener Zugriff erfordert [20H2 und neuere Builds](hololens-release-notes.md#windows-holographic-version-20h2) |
| Jeder Benutzer, der sich anmeldet, erhält Kioskerfahrung mit Ausnahme bestimmter Benutzer. | [Konfigurieren Sie mehrere Global Assigned Access-App-Profile, indem Sie bestimmte Benutzer ausschließen (die Gerätebesitzer sein müssen).](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners) | • [Microsoft Intune benutzerdefinierte Vorlage](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Laufzeitbereitstellung – Mehrere Apps](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Global zugewiesener Zugriff erfordert [20H2 und neuere Builds](hololens-release-notes.md#windows-holographic-version-20h2) |
| Jeder AAD Benutzer erhält eine separate Kioskerfahrung, die für diesen Benutzer spezifisch ist. | [Konfigurieren Sie die Konfiguration des zugewiesenen Zugriffs für jeden Benutzer, und geben Sie dabei den AAD Kontonamen an.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune benutzerdefinierte Vorlage](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Laufzeitbereitstellung – Mehrere Apps](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| Benutzer in unterschiedlichen AAD Gruppen verfügen über einen Kioskmodus, der nur für ihre Gruppe gilt. | [Konfigurieren Sie die Konfiguration des zugewiesenen Zugriffs für jede gewünschte AAD Gruppe.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune benutzerdefinierte Vorlage](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Laufzeitbereitstellung – Mehrere Apps](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • Wenn sich ein Benutzer anmeldet und HoloLens mit dem Internet verbunden ist und dieser Benutzer Mitglied AAD Gruppe ist, für die eine Kioskkonfiguration vorhanden ist, wird der Benutzer zum Kiosk für diese AAD Gruppe. <br> • Wenn bei der [Benutzeranmeldung kein Internet verfügbar ist, tritt für den Benutzer HoloLens Fehlermodusverhalten auf.](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • Wenn die Internetverfügbarkeit nicht garantiert wird, wenn sich Benutzer anmelden und AAD gruppenbasierte Kiosk verwendet werden muss, [sollten Sie die Verwendung von AADGroupMembershipCacheCacheCacheInDayspolicy in Betracht ziehen.](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk) <br> • Um eine optimale Erfahrung mit AAD Gruppen während der Anmeldung zu gewährleisten, empfiehlt es sich, [AADGroupMembershipCacheCacheCacheInDayspolicy](/hololens/hololens-release-notes#cache-azure-ad-group-membership-for-offline-kiosk) zu verwenden. |
| Benutzer, die HoloLens für temporäre Zwecke verwenden müssen, erhalten Kioskerfahrung. | [Konfigurieren der Konfiguration des zugewiesenen Zugriffs für Besucher](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune benutzerdefinierte Vorlage](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Laufzeitbereitstellung – Einzelne App](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • Temporäres Benutzerkonto wird automatisch von HoloLens bei der Anmeldung erstellt und entfernt, wenn sich ein temporärer Benutzer abmeldet. <br> • Aktivieren Sie die Richtlinie für [die automatische Anmeldung](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience)von Besuchern. |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>Schritte zum Konfigurieren des Kioskmodus für HoloLens

Kioskkonfigurationen können auf folgende Weise erstellt und angewendet werden:

1. Mit der Benutzeroberfläche des MDM-Servers, z. B. den Kioskvorlagen von Intune oder benutzerdefinierten OMA-URI-Konfigurationen, die dann remote auf HoloLens angewendet werden.
2. Mit Laufzeitbereitstellungspaketen, die dann direkt auf HoloLens angewendet werden.

Im Folgenden finden Sie die folgenden Möglichkeiten zum Konfigurieren. Wählen Sie die Registerkarte aus, die dem gewünschten Prozess entspricht.

1. [Microsoft Intune-Kioskvorlage für einzelne Apps](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune-Kioskvorlage für mehrere Apps](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Benutzerdefinierte Microsoft Intune-Vorlage](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [Laufzeitbereitstellung: Mehrere Apps](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Laufzeitbereitstellung: Einzelne App](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>Wie können sich Besucherkonten automatisch bei Kiosk anmelden?

Auf Builds [Windows Holographic, Version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) und höher:

- AAD- und Nicht-ADD-Konfigurationen unterstützen die automatische Anmeldung von Besucherkonten für Kioskmodi.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>Wird die Kioskerfahrung in HoloLens (1. Generation) unterstützt?

Der Kioskmodus ist nur verfügbar, wenn das Gerät über Windows Holographic for Business verfügt. Alle HoloLens 2 Geräte werden mit Windows Holographic for Business versendet, und es gibt keine anderen Editionen. Jedes HoloLens 2 Gerät kann den Kioskmodus sofort ausführen.

HoloLens -Geräte (1. Generation) müssen sowohl im Hinblick auf den Betriebssystembuild als auch die Betriebssystemedition aktualisiert werden. Hier finden Sie weitere Informationen zum Aktualisieren eines HoloLens (1. Generation) auf [Windows Holographic for Business](hololens1-upgrade-enterprise.md) Edition. Um ein HoloLens Gerät (1. Generation) für die Verwendung des Kioskmodus zu aktualisieren, müssen Sie zunächst sicherstellen, dass das Gerät Windows 10 Version 1803 oder höher ausgeführt wird. Wenn Sie das Windows Device Recovery Tool verwendet haben, um Ihr HoloLens Gerät (1. Generation) auf dem Standardbuild wiederherzustellen, oder wenn Sie die neuesten Updates installiert haben, kann Ihr Gerät konfiguriert werden.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>Wie wird das Geräteportal verwendet, um Kiosk in Nicht-Produktionsumgebungen zu konfigurieren?

Richten Sie das [HoloLens Gerät für die Verwendung des Windows Geräteportal](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)ein. Das Geräteportal ist ein Webserver auf der HoloLens, mit dem Sie über einen Webbrowser auf dem PC eine Verbindung herstellen können.

 > [!CAUTION]
 > Wenn Sie HoloLens für die Verwendung des Geräteportal einrichten, müssen Sie den Entwicklermodus auf dem Gerät aktivieren. Im Entwicklermodus auf einem Gerät mit Windows Holographic for Business können Sie Apps querladen. Diese Einstellung birgt jedoch das Risiko, dass ein Benutzer Apps installieren kann, die nicht vom Microsoft Store zertifiziert wurden. Administratoren können die Möglichkeit zum Aktivieren des Entwicklermodus mithilfe der Einstellung **ApplicationManagement/AllowDeveloper Unlock** im [Richtlinien-CSP](/windows/client-management/mdm/policy-configuration-service-provider)blockieren. [Weitere Informationen zum Entwicklermodus](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

Der Kioskmodus kann über die REST-API von Geräteportal festgelegt werden, indem ein POST für /api/holographic/kioskmode/settings mit einem erforderlichen Abfragezeichenfolgenparameter ("kioskModeEnabled" mit dem Wert "true" oder "false") und einem optionalen Parameter ("startupApp" mit dem Wert eines Paketnamens) ausgeführt wird. Beachten Sie, dass Geräteportal nur für Entwickler vorgesehen ist und nicht auf Geräten ohne Entwickler aktiviert werden sollte. Die REST-API kann in zukünftigen Updates/Releases geändert werden.

## <a name="troubleshooting"></a>Problembehandlung

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>Problem: Im Kioskmodus werden keine Apps im Startmenü angezeigt.

**Symptome**

Wenn beim Anwenden des Kioskmodus Fehler auftreten, wird das folgende Verhalten angezeigt:

- Vor Windows Holographic zeigt Version 20H2 – HoloLens alle Anwendungen im Startmenü an.
- Windows Holographic, Version 20H2: Wenn ein Gerät über eine Kioskkonfiguration verfügt, bei der es sich um eine Kombination aus global zugewiesenem Zugriff und AAD gruppenzugewiesenem Zugriff handelt, wird dem Benutzer im Startmenü nichts angezeigt, wenn die Ermittlung AAD Gruppenmitgliedschaft fehlschlägt.

    ![Abbildung, wie der Kioskmodus jetzt aussieht, wenn ein Fehler auftritt.](images/hololens-kiosk-failure-behavior.png )

- Ab [Windows Holographic, Version 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)sucht der Kioskmodus nach global zugewiesenem Zugriff, bevor ein leeres Startmenü angezeigt wird. Die Kioskbenutzeroberfläche wird auf eine globale Kioskkonfiguration (falls vorhanden) zurückfallen, wenn während AAD Gruppenkioskmodus Fehler vorliegen.

**Schritte zur Problembehandlung**

- Stellen Sie sicher, dass AUMID der App richtig angegeben ist und keine Versionen enthält. Beispiele finden Sie unter [HoloLens AUMIDs](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) für Posteingangs-Apps.
- Stellen Sie sicher, dass die Anwendung auf dem Gerät für diesen Benutzer installiert ist.
- Wenn die Kioskkonfiguration auf AAD Gruppen basiert, stellen Sie sicher, dass die Internetverbindung vorhanden ist, wenn sich der AAD Benutzer anmeldet. Konfigurieren Sie bei Bedarf [die Richtlinie MixedReality/AADGroupMembershipCacheCacheInDays,](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) damit dies auch ohne Internet funktionieren kann.

Wenn XML verwendet wurde, um die Konfiguration des zugewiesenen Zugriffs zu erstellen (entweder über die Laufzeitbereitstellung oder den intune custom-OMA-URI), stellen Sie sicher, dass XML wohlgeformt ist, indem Sie ihn in einem beliebigen Webbrowser oder XML-Editor öffnen. Informationen zu wohlgeformten und gültigen Vorlagen finden Sie in den [Kiosk-XML-Codebeispielen.](hololens-kiosk-reference.md#kiosk-xml-code-samples)

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>Problem: Fehler beim Erstellen eines Pakets mit Kioskmodus

**Symptome**

Ein Dialogfeld wie unten wird angezeigt.

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**Schritte zur Problembehandlung**

1. Klicken Sie auf den Hyperlink, der im obigen Dialogfeld angezeigt wird.
1. Öffnen Sie ICD.log in einem Text-Editor, und der Inhalt sollte auf den Fehler hinweisen.

> [!NOTE]
> Wenn Sie mehrere Versuche unternommen haben, überprüfen Sie die Zeitstempel im Protokoll. Dadurch können Sie nur die aktuellen Probleme überprüfen.

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>Problem: Das Bereitstellungspaket wurde erfolgreich erstellt, konnte aber nicht angewendet werden.

**Symptome**

Fehler beim Anwenden des Bereitstellungspakets auf Hololens

**Schritte zur Problembehandlung**

1. Navigieren Sie zu dem Ordner, in dem Windows Configuration Designer-Projekt für das Laufzeitbereitstellungspaket vorhanden ist.
1. Öffnen Sie ICD.log, und stellen Sie sicher, dass beim Erstellen des Bereitstellungspakets keine Fehler im Protokoll vorhanden sind. Einige Fehler werden während des Buildbuilds nicht angezeigt, werden aber weiterhin in ICD.log protokolliert.

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>Problem: Mehrere App-zugewiesener Zugriff auf AAD Gruppe funktioniert nicht

**Symptome**

Bei AAD Benutzeranmeldung wechselt das Gerät nicht in den erwarteten Kioskmodus.

**Schritte zur Problembehandlung**

- Vergewissern Sie sich in der XML-Konfigurationsdatei für zugewiesenen Zugriff, dass die GUID AAD Gruppe verwendet wird, der der angemeldete Benutzer angehört, und nicht die GUID des AAD Benutzers.
- Vergewissern Sie sich, dass AAD Benutzer im Intune-Portal tatsächlich als Mitglied AAD Gruppe angezeigt wird.
- Vergewissern Sie sich nur für Intune, dass das Gerät als konform angezeigt wird. Weitere Informationen finden Sie in der Referenz zur [Gerätekonformität.](/mem/intune/protect/device-compliance-get-started)
