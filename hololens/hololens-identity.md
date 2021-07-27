---
title: Verwalten der Benutzeridentität und Anmeldung für HoloLens
description: Erfahren Sie, wie Sie benutzeridentität, Mehrbenutzerunterstützung, Sicherheit, Unternehmensauthentifizierung und Anmeldung für HoloLens verwalten.
keywords: HoloLens, Benutzer, Konto, AAD, Azure AD, adfs, microsoft account, msa, credentials, reference
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 10/6/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 1081ed512183592e66e65f2e69323752b822f1c1
ms.sourcegitcommit: 5130823947caffd2a444e9d8fb15cd24cbb6414c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2021
ms.locfileid: "114659181"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Verwalten der Benutzeridentität und Anmeldung für HoloLens

> [!NOTE]
> Dieser Artikel ist eine technische Referenz für IT-Profis und Tech-Fans. Wenn Sie Nachschlageanweisungen HoloLens einrichten möchten, lesen Sie " Einrichten Ihrer[HoloLens (1. Generation)](hololens1-start.md)" oder "[Einrichten ihrer](hololens2-start.md)HoloLens 2 ".

Wie andere Windows geräte auch, HoloLens immer in einem Benutzerkontext betrieben. Es gibt immer eine Benutzeridentität. HoloLens behandelt Identitäten fast auf die gleiche Weise wie andere Windows 10 Geräte. Dieser Artikel ist eine tiefgehende Referenz zu Identitäten auf HoloLens und konzentriert sich darauf, wie sich HoloLens von anderen Windows 10 unterscheidet.

HoloLens unterstützt verschiedene Arten von Benutzeridentitäten. Sie können ein oder mehrere Benutzerkonten für die Anmeldung verwenden. Im Folgenden finden Sie eine Übersicht über die Identitätstypen und Authentifizierungsoptionen HoloLens:

| Identitätstyp | Konten pro Gerät | Authentifizierungsoptionen |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Azure-Web-Anmeldeinformationsanbieter</li><li>Azure Authenticator-App</li><li>Biometrische Daten (Iris) &ndash; HoloLens 2<sup>nur 2</sup> </li><li>PIN &ndash; optional für HoloLens (1. Generation), erforderlich für HoloLens 2</li><li>Kennwort</li></ul> |
| [Microsoft-Konto (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Nur biometrische &ndash; (Iris HoloLens 2 Metrie</li><li>PIN &ndash; optional für HoloLens (1. Generation), erforderlich für HoloLens 2</li><li>Kennwort</li></ul> |
| [Lokales Konto](/windows/security/identity-protection/access-control/local-accounts) | 1 | Kennwort |

Mit der Cloud verbundene Konten (Azure AD und MSA) bieten mehr Features, da sie Azure-Dienste verwenden können.  
> [!IMPORTANT]
> 1 – Azure AD Premium ist nicht erforderlich, um sich beim Gerät anmelden zu können. Dies ist jedoch für andere Features einer cloudbasierten Bereitstellung mit geringem Touchaufwand erforderlich, z. B. automatische Registrierung und Autopilot.

> [!NOTE]
> 2 – Ein HoloLens 2-Gerät kann bis zu 64 Azure AD Unterstützen, aber nur 31 dieser Konten können sich bei Iris Authentication registrieren. Dies ist auf andere [biometrische Authentifizierungsoptionen für Windows Hello business ausgerichtet.](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## <a name="setting-up-users"></a>Einrichten von Benutzern

Die gängigste Methode zum Einrichten eines neuen Benutzers ist die HoloLens out-of-box experience (OOBE). Während des Setups werden HoloLens benutzeraufforderungen, sich mit dem Konto anmelden, das er auf dem Gerät verwenden möchte. Bei diesem Konto kann es sich um ein Microsoft-Konto oder um ein in Azure konfiguriertes Unternehmenskonto geben. Weitere Informationen finden Sie [unter HoloLens (1. Generation)](hololens1-start.md) oder [HoloLens 2](hololens2-start.md).

Wie Windows auf anderen Geräten erstellt die Anmeldung während des Setups ein Benutzerprofil auf dem Gerät. Im Benutzerprofil werden Apps und Daten gespeichert. Dasselbe Konto bietet auch einmaliges Anmelden für Apps wie Edge oder Microsoft Store mithilfe der Windows Account Manager-APIs.  

Wenn Sie sich mit einem Unternehmens- oder Organisationskonto bei HoloLens anmelden, HoloLens sich bei der IT-Infrastruktur der Organisation registrieren. Mit dieser Registrierung kann Ihr IT-Administrator Mobile Geräteverwaltung (MDM) konfigurieren, um Gruppenrichtlinien an Ihre HoloLens.

Standardmäßig müssen Sie sich wie bei anderen Windows 10-Geräten erneut anmelden, wenn HoloLens im Standbymodus neu gestartet oder fortgesetzt wird. Sie können die Einstellungen-App verwenden, um dieses Verhalten zu ändern, oder das Verhalten kann durch eine Gruppenrichtlinie gesteuert werden.

### <a name="linked-accounts"></a>Verknüpfte Konten

Wie in der Desktopversion von Windows können Sie zusätzliche Webkontoanmeldeinformationen mit Ihrem HoloLens verknüpfen. Eine solche Verknüpfung erleichtert den Zugriff auf Ressourcen innerhalb oder innerhalb von Apps (z. B. Store) oder das Kombinieren des Zugriffs auf persönliche und Arbeitsressourcen. Nachdem Sie ein Konto mit dem Gerät verbinden, können Sie Apps die Berechtigung zum Verwenden des Geräts erteilen, damit Sie sich nicht einzeln bei jeder App anmelden müssen.

Beim Verknüpfen von Konten werden die auf dem Gerät erstellten Benutzerdaten nicht getrennt, z. B. Bilder oder Downloads.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Einrichten der Unterstützung für mehrere Benutzer (nur Azure AD)

HoloLens unterstützt mehrere Benutzer aus demselben Azure AD Mandanten. Um dieses Feature verwenden zu können, müssen Sie zum Einrichten des Geräts ein Konto verwenden, das Ihrer Organisation angehört. Anschließend können sich andere Benutzer desselben Mandanten über den Anmeldebildschirm oder durch Tippen auf die Benutzerkachel im Startbereich beim Gerät anmelden. Es kann immer nur ein Benutzer gleichzeitig angemeldet werden. Wenn sich ein Benutzer an diesem HoloLens den vorherigen Benutzer ab. Der erste Benutzer auf dem Gerät wird als Gerätebesitzer betrachtet, mit Ausnahme von Azure AD Join weitere [Informationen zu Gerätebesitzern.](security-adminless-os.md#device-owner)

Alle Benutzer können die auf dem Gerät installierten Apps verwenden. Jeder Benutzer verfügt jedoch über eigene App-Daten und -Einstellungen. Wenn Sie eine App vom Gerät entfernen, wird sie für alle Benutzer entfernt.  

Geräte, die mit Azure AD-Konten eingerichtet sind, lassen die Anmeldung beim Gerät mit einem Microsoft-Konto nicht zu. Alle nachfolgend verwendeten Konten müssen Azure AD demselben Mandanten wie das Gerät verwendet werden. Sie können sich [weiterhin mit einem Microsoft-Konto bei](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) Apps anmelden, die es unterstützen (z. B. Microsoft Store). Um von der Verwendung Azure AD-Konten zu Microsoft-Konten für die Anmeldung beim Gerät zu wechseln, müssen Sie das Gerät neu [erstellen.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens (1. Generation)** hat mit der Unterstützung mehrerer Azure AD-Benutzer im Update vom [Windows 10 April 2018](/windows/mixed-reality/release-notes-april-2018) im Rahmen von [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

### <a name="multiple-users-listed-on-sign-in-screen"></a>Mehrere Benutzer, die auf dem Anmeldebildschirm aufgeführt sind

Zuvor wurde auf dem Bildschirm Anmelden nur der zuletzt angemeldete Benutzer sowie ein Einstiegspunkt "Anderer Benutzer" angezeigt. Wir haben Kundenfeedback erhalten, dass dies nicht ausreicht, wenn sich mehrere Benutzer beim Gerät angemeldet haben. Sie mussten weiterhin ihren Benutzernamen usw. erneut eingeben.

Eingeführt in [Windows Holographic, Version 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)  zeigt der Anmeldebildschirm mehrere Benutzer an, die sich zuvor bei dem Gerät angemeldet haben, wenn Sie Auf der rechten Seite des PIN-Eingabefelds anderer Benutzer auswählen. Dadurch können Benutzer ihr Benutzerprofil auswählen und sich dann mit ihren Anmeldeinformationen Windows Hello anmelden. Über die Schaltfläche Konto hinzufügen kann dem Gerät auch ein neuer Benutzer über die Seite Andere **Benutzer hinzugefügt** werden.

Im Menü Andere Benutzer zeigt die Schaltfläche Andere Benutzer den letzten Benutzer an, der sich am Gerät angemeldet hat. Wählen Sie diese Schaltfläche aus, um zum Anmeldebildschirm für diesen Benutzer zurückzukehren.

![Standardeinstellung des Anmeldebildschirms](./images/multiusers1.jpg)

<br>

![Anmeldebildschirm für andere Benutzer](./images/multiusers2.jpg)

## <a name="removing-users"></a>Entfernen von Benutzern

Sie können einen Benutzer vom Gerät entfernen, indem Sie Einstellungen  >  **Konten Andere**  >  **Personen.** Diese Aktion gibt auch Speicherplatz frei, indem alle App-Daten dieses Benutzers vom Gerät entfernt werden.  

## <a name="using-single-sign-on-within-an-app"></a>Verwenden des einmaligen Anmeldens in einer App

Als App-Entwickler können Sie verknüpfte Identitäten auf HoloLens nutzen, indem Sie die [Windows-Konto-Manager-APIs](/uwp/api/Windows.Security.Authentication.Web.Core)wie auf anderen Windows verwenden. Einige Codebeispiele für diese APIs sind unter GitHub: [Beispiel für die Webkontoverwaltung verfügbar.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

Alle Kontounterbrechungen, die auftreten können, z. B. das Anfordern der Benutzererwilligung für Kontoinformationen, die zwei faktorbasierte Authentifizierung usw., müssen verarbeitet werden, wenn die App ein Authentifizierungstoken an fordert.

Wenn Ihre App einen bestimmten Kontotyp erfordert, der zuvor noch nicht verknüpft wurde, kann Ihre App das System auffordern, den Benutzer zum Hinzufügen eines Kontos auffordern. Diese Anforderung löst den Kontoeinstellungsbereich aus, um als modales untergeordnetes Gerät Ihrer App zu starten. Bei 2D-Apps wird dieses Fenster direkt über der Mitte Ihrer App gerendert. Bei Unity-Apps wird der Benutzer mit dieser Anforderung kurz aus Ihrer holografischen App herausgeholen, um das untergeordnete Fenster zu rendern. Informationen zum Anpassen der Befehle und Aktionen in diesem Bereich finden Sie unter [WebAccountCommand-Klasse](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Enterprise und andere Authentifizierung

Wenn Ihre App andere Authentifizierungstypen verwendet, z. B. NTLM, Basic oder Kerberos, können Sie die Anmeldeinformationen des Benutzers mithilfe der [Windows-Benutzeroberfläche für Anmeldeinformationen](/uwp/api/Windows.Security.Credentials.UI) erfassen, verarbeiten und speichern. Die Benutzererfahrung zum Sammeln dieser Anmeldeinformationen ähnelt stark anderen cloudgesteuerten Kontounterbrechungen und wird als untergeordnete App über Ihrer 2D-App angezeigt oder unterbricht kurz eine Unity-App, um die Benutzeroberfläche anzuzeigen.

## <a name="deprecated-apis"></a>Nicht mehr unterstützte APIs

Eine Möglichkeit, wie sich die Entwicklung für HoloLens desktop unterscheidet, ist, dass die [OnlineIDAuthenticator-API](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) nicht vollständig unterstützt wird. Obwohl die API ein Token zurückgibt, wenn sich das primäre Konto in einem guten Zustand befindet, zeigen Unterbrechungen wie die in diesem Artikel beschriebenen keine Benutzeroberfläche für den Benutzer an und können das Konto nicht ordnungsgemäß authentifizieren.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Wird Windows Hello for Business auf HoloLens (1. Generation) unterstützt?

Windows Hello for Business (das die Verwendung einer PIN für die Anmeldung unterstützt) wird für HoloLens (1. Generation) unterstützt. So ermöglichen Windows Hello die Anmeldung mit der Business-PIN HoloLens:

1. Das HoloLens muss von [MDM verwaltet werden.](hololens-enroll-mdm.md)
1. Sie müssen Windows Hello für Unternehmen für das Gerät aktivieren. ([Siehe Anweisungen für Microsoft Intune.](/intune/windows-hello))
1. Auf HoloLens kann der Benutzer dann Einstellungen Anmeldeoptionen PIN hinzufügen verwenden, um  >    >   eine PIN zu einrichten.

> [!NOTE]
> Benutzer, die sich mithilfe eines Microsoft-Konto anmelden, können auch eine PIN **in** Einstellungen  >  **Anmeldeoptionen** PIN hinzufügen  >  **einrichten.** Diese PIN ist [mit](https://support.microsoft.com/help/17215/windows-10-what-is-hello)Windows Hello verknüpft, anstatt Windows Hello [für Unternehmen.](/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Wie wird die biometrische Iris-Authentifizierung auf HoloLens 2?

HoloLens 2 unterstützt die Iris-Authentifizierung. Iris basiert auf Windows Hello-Technologie und wird für die Verwendung durch Azure Active Directory microsoft-Konten unterstützt. Iris wird auf die gleiche Weise wie andere Windows Hello implementiert und erreicht die biometrische Sicherheit FAR von 1/100.000.

Weitere Informationen [finden Sie in den biometrischen Anforderungen Windows Hello](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) Spezifikationen. Erfahren Sie mehr [über Windows Hello](/windows-hardware/design/device-experiences/windows-hello) und Windows Hello [for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Wie wirkt sich der Kontotyp auf das Anmeldeverhalten aus?

Wenn Sie Richtlinien für die Anmeldung anwenden, wird die Richtlinie immer beachtet. Wenn keine Richtlinie für die Anmeldung angewendet wird, sind dies die Standardverhalten für jeden Kontotyp:

- **Azure AD**: fordert standardmäßig zur Authentifizierung auf  und kann von Einstellungen nicht mehr zur Authentifizierung aufgefordert werden.
- **Microsoft-Konto:** Das Sperrverhalten ist anders, sodass das automatische Entsperren ermöglicht wird, aber die Anmeldeauthentifizierung ist beim Neustart weiterhin erforderlich.
- **Lokales Konto:** Fordert immer zur Authentifizierung in Form eines Kennworts auf, das **in** der Einstellungen

> [!NOTE]
> Inaktivitäts-Timer werden derzeit nicht unterstützt. Dies bedeutet, dass die **Richtlinie AllowIdleReturnWithoutPassword** nur berücksichtigt wird, wenn das Gerät in StandBy übergeht.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

Weitere Informationen zum Schutz der Benutzeridentität und -Authentifizierung finden Sie in der Windows 10 security and identity documentation (Sicherheits- [und Identitätsdokumentation).](/windows/security/identity-protection/)

Weitere Informationen zum Einrichten der Hybrididentitätsinfrastruktur finden Sie in der [Dokumentation zur Azure-Hybrididentität.](/azure/active-directory/hybrid/)
