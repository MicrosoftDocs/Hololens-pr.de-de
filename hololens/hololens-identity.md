---
title: Verwalten der Benutzeridentität und Anmeldung für HoloLens
description: Erfahren Sie, wie Sie Die Benutzeridentität, Unterstützung für mehrere Benutzer, Sicherheit, Unternehmensauthentifizierung und Anmeldung für HoloLens-Geräte verwalten.
keywords: HoloLens, Benutzer, Konto, AAD, Azure AD, adfs, Microsoft-Konto, msa, Anmeldeinformationen, Referenz
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
ms.openlocfilehash: fbef357053900f6495cb59f52cba8669f0d0a3db
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924416"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Verwalten der Benutzeridentität und Anmeldung für HoloLens

> [!NOTE]
> Dieser Artikel ist eine technische Referenz für IT-Profis und Tech-Fans. Wenn Sie nach HoloLens-Einrichtungsanweisungen suchen, lesen Sie " Einrichten Ihrer[HoloLens (1. Generation)](hololens1-start.md)" oder "[Einrichten Ihrer](hololens2-start.md)HoloLens 2 ".

Wie andere Windows-Geräte arbeitet HoloLens immer unter einem Benutzerkontext. Es gibt immer eine Benutzeridentität. HoloLens behandelt Identitäten fast auf die gleiche Weise wie andere Windows 10 Geräte. Dieser Artikel ist eine tiefgehende Referenz zur Identität auf HoloLens und konzentriert sich darauf, wie sich HoloLens von anderen Windows 10 unterscheidet.

HoloLens unterstützt verschiedene Arten von Benutzeridentitäten. Sie können ein oder mehrere Benutzerkonten für die Anmeldung verwenden. Im Folgenden finden Sie eine Übersicht über die Identitätstypen und Authentifizierungsoptionen auf HoloLens:

| Identitätstyp | Konten pro Gerät | Authentifizierungsoptionen |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Azure-Web-Anmeldeinformationsanbieter</li><li>Azure Authenticator-App</li><li>Biometrische Daten (Iris) &ndash; HoloLens 2<sup>nur 2</sup> </li><li>PIN &ndash; optional für HoloLens (1. Generation), erforderlich für HoloLens 2</li><li>Kennwort</li></ul> |
| [Microsoft-Konto (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Nur biometrische Daten &ndash; (Iris HoloLens 2</li><li>PIN &ndash; optional für HoloLens (1. Generation), erforderlich für HoloLens 2</li><li>Kennwort</li></ul> |
| [Lokales Konto](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Kennwort |

Mit der Cloud verbundene Konten (Azure AD und MSA) bieten mehr Features, da sie Azure-Dienste verwenden können.  
> [!IMPORTANT]
> 1 – Azure AD Premium nicht erforderlich, um sich beim Gerät anmelden zu können. Dies ist jedoch für andere Features einer cloudbasierten Bereitstellung mit geringem Touchaufwand erforderlich, z. B. automatische Registrierung und Autopilot.

> [!NOTE]
> 2 – Ein HoloLens 2-Gerät kann bis zu 64 Azure AD Unterstützen, aber nur 10 dieser Konten können sich bei Iris Authentication registrieren. Dies ist auf andere [Biometrische Authentifizierungsoptionen für Windows Hello for Business.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## <a name="setting-up-users"></a>Einrichten von Benutzern

Die gängigste Methode zum Einrichten eines neuen Benutzers ist die Verwendung der HoloLens-Willkommensseite (Out-of-Box Experience, OOBE). Während des Setups fordert HoloLens einen Benutzer zur Anmeldung auf, indem er das Konto verwendet, das er auf dem Gerät verwenden möchte. Bei diesem Konto kann es sich um ein Microsoft-Konto oder um ein in Azure konfiguriertes Unternehmenskonto geben. Weitere Informationen finden Sie unter [Einrichten ihrer HoloLens (1. Generation)](hololens1-start.md) [oder HoloLens 2](hololens2-start.md).

Wie bei Windows auf anderen Geräten wird bei der Anmeldung während des Setups ein Benutzerprofil auf dem Gerät erstellt. Im Benutzerprofil werden Apps und Daten gespeichert. Dasselbe Konto bietet auch einmaliges Anmelden für Apps wie Edge oder Microsoft Store mithilfe der Windows-Konto-Manager-APIs.  

Wenn Sie sich mit einem Unternehmens- oder Organisationskonto bei HoloLens anmelden, wird HoloLens bei der IT-Infrastruktur der Organisation registriert. Mit dieser Registrierung kann Ihr IT-Administrator Mobile Geräteverwaltung (MDM) konfigurieren, um Gruppenrichtlinien an Ihre HoloLens zu senden.

Standardmäßig müssen Sie sich wie bei anderen Windows 10-Geräten erneut anmelden, wenn HoloLens neu gestartet oder aus dem Standbymodus fortgesetzt wird. Sie können die App Einstellungen verwenden, um dieses Verhalten zu ändern, oder das Verhalten kann durch eine Gruppenrichtlinie gesteuert werden.

### <a name="linked-accounts"></a>Verknüpfte Konten

Wie in der Desktopversion von Windows können Sie zusätzliche Webkontoanmeldeinformationen mit Ihrem HoloLens-Konto verknüpfen. Eine solche Verknüpfung erleichtert den Zugriff auf Ressourcen innerhalb oder innerhalb von Apps (z. B. store) oder das Kombinieren des Zugriffs auf persönliche und Arbeitsressourcen. Nachdem Sie ein Konto mit dem Gerät verbinden, können Sie Apps die Berechtigung zum Verwenden des Geräts erteilen, damit Sie sich nicht einzeln bei jeder App anmelden müssen.

Beim Verknüpfen von Konten werden die auf dem Gerät erstellten Benutzerdaten, z. B. Bilder oder Downloads, nicht voneinander getrennt.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Einrichten der Unterstützung für mehrere Benutzer (nur Azure AD)

HoloLens unterstützt mehrere Benutzer aus demselben Azure AD Mandanten. Um dieses Feature verwenden zu können, müssen Sie zum Einrichten des Geräts ein Konto verwenden, das Ihrer Organisation angehört. Anschließend können sich andere Benutzer desselben Mandanten über den Anmeldebildschirm oder durch Tippen auf die Benutzerkachel im Startbereich beim Gerät anmelden. Es kann immer nur ein Benutzer gleichzeitig angemeldet werden. Wenn sich ein Benutzer anknabschreibt, wird der vorherige Benutzer von HoloLens ab- ab. Der erste Benutzer auf dem Gerät wird als Gerätebesitzer betrachtet, mit Ausnahme von Azure AD Join weitere [Informationen zu Gerätebesitzern.](security-adminless-os.md#device-owner)

Alle Benutzer können die auf dem Gerät installierten Apps verwenden. Jeder Benutzer verfügt jedoch über eigene App-Daten und -Einstellungen. Wenn Sie eine App vom Gerät entfernen, wird sie für alle Benutzer entfernt.  

Geräte, die mit Azure AD-Konten eingerichtet sind, lassen die Anmeldung beim Gerät mit einem Microsoft-Konto nicht zu. Alle nachfolgend verwendeten Konten müssen Azure AD demselben Mandanten wie das Gerät verwendet werden. Sie können sich [weiterhin mit einem Microsoft-Konto bei](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) Apps anmelden, die es unterstützen (z. B. Microsoft Store). Um von der Verwendung Azure AD-Konten zu Microsoft-Konten für die Anmeldung beim Gerät zu wechseln, müssen Sie das Gerät neu [erstellen.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens (1. Generation)** hat damit begonnen, [](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) mehrere Azure AD-Benutzer in der Windows 10 April 2018 Update im Rahmen von [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

### <a name="multiple-users-listed-on-sign-in-screen"></a>Mehrere Benutzer, die auf dem Anmeldebildschirm aufgeführt sind

Zuvor wurde auf dem Bildschirm Anmelden nur der zuletzt angemeldete Benutzer sowie ein Einstiegspunkt "Anderer Benutzer" angezeigt. Wir haben Kundenfeedback erhalten, dass dies nicht ausreicht, wenn sich mehrere Benutzer beim Gerät angemeldet haben. Sie mussten weiterhin ihren Benutzernamen usw. erneut eingeben.

Eingeführt in [Windows Holographic, Version 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)zeigt der Bildschirm Anmelden mehrere Benutzer an, die sich zuvor bei dem Gerät angemeldet haben, wenn Sie Andere Benutzer rechts neben dem PIN-Eingabefeld auswählen.  Dadurch können Benutzer ihr Benutzerprofil auswählen und sich dann mit ihren Anmeldeinformationen Windows Hello anmelden. Über die Schaltfläche Konto hinzufügen kann dem Gerät auch ein neuer Benutzer über die Seite Andere **Benutzer hinzugefügt** werden.

Im Menü Andere Benutzer zeigt die Schaltfläche Andere Benutzer den letzten Benutzer an, der sich am Gerät angemeldet hat. Wählen Sie diese Schaltfläche aus, um zum Anmeldebildschirm für diesen Benutzer zurückzukehren.

![Standardeinstellung des Anmeldebildschirms](./images/multiusers1.jpg)

<br>

![Anmeldebildschirm für andere Benutzer](./images/multiusers2.jpg)

## <a name="removing-users"></a>Entfernen von Benutzern

Sie können einen Benutzer vom Gerät entfernen, indem Sie zu **Einstellungen**  >  **Konten Andere**  >  **Personen.** Diese Aktion gibt auch Speicherplatz frei, indem alle App-Daten dieses Benutzers vom Gerät entfernt werden.  

## <a name="using-single-sign-on-within-an-app"></a>Verwenden des einmaligen Anmeldens in einer App

Als App-Entwickler können Sie verknüpfte Identitäten auf HoloLens nutzen, indem Sie die [Windows-Konto-Manager-APIs](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)wie auf anderen Windows-Geräten verwenden. Einige Codebeispiele für diese APIs sind auf GitHub verfügbar: [Beispiel für die Webkontoverwaltung.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

Alle Kontounterbrechungen, die auftreten können, z. B. das Anfordern der Benutzererwilligung für Kontoinformationen, die zwei faktorbasierte Authentifizierung usw., müssen verarbeitet werden, wenn die App ein Authentifizierungstoken an fordert.

Wenn Ihre App einen bestimmten Kontotyp erfordert, der zuvor nicht verknüpft wurde, kann Ihre App das System auffordern, den Benutzer auffordern, einen hinzuzufügen. Diese Anforderung löst den Kontoeinstellungsbereich aus, um als modales untergeordnetes Gerät Ihrer App zu starten. Bei 2D-Apps wird dieses Fenster direkt über der Mitte Ihrer App gerendert. Bei Unity-Apps wird der Benutzer mit dieser Anforderung kurz aus Ihrer holografischen App herausgeholen, um das untergeordnete Fenster zu rendern. Informationen zum Anpassen der Befehle und Aktionen in diesem Bereich finden Sie unter [WebAccountCommand-Klasse](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Unternehmensauthentifizierung und andere Authentifizierung

Wenn Ihre App andere Authentifizierungstypen verwendet, z. B. NTLM, Basic oder Kerberos, können Sie die [Benutzeroberfläche](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) für Windows-Anmeldeinformationen verwenden, um die Anmeldeinformationen des Benutzers zu erfassen, zu verarbeiten und zu speichern. Die Benutzererfahrung zum Sammeln dieser Anmeldeinformationen ähnelt stark anderen cloudgesteuerten Kontounterbrechungen und wird als untergeordnete App über Ihrer 2D-App angezeigt oder unterbricht kurz eine Unity-App, um die Benutzeroberfläche anzuzeigen.

## <a name="deprecated-apis"></a>Nicht mehr unterstützte APIs

Eine Möglichkeit, wie sich die Entwicklung für HoloLens von der Entwicklung für Desktop unterscheidet, ist, dass die [OnlineIDAuthenticator-API](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) nicht vollständig unterstützt wird. Obwohl die API ein Token zurückgibt, wenn sich das primäre Konto in einem guten Zustand befindet, zeigen Unterbrechungen wie die in diesem Artikel beschriebenen keine Benutzeroberfläche für den Benutzer an und können das Konto nicht ordnungsgemäß authentifizieren.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Wird Windows Hello for Business HoloLens (1. Generation) unterstützt?

Windows Hello for Business (die die Verwendung einer PIN für die Anmeldung unterstützt) wird für HoloLens (1. Generation) unterstützt. So lassen Sie Windows Hello for Business PIN-Anmeldung bei HoloLens zu:

1. Das HoloLens-Gerät muss [von MDM verwaltet](hololens-enroll-mdm.md)werden.
1. Sie müssen Windows Hello for Business für das Gerät aktivieren. ([Weitere Informationen finden Sie in den Anweisungen für Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello))
1. Auf HoloLens kann der Benutzer dann einstellungen  >  **Anmeldeoptionen**  >  **PIN** hinzufügen verwenden, um eine PIN einzurichten.

> [!NOTE]
> Benutzer, die sich mit einem Microsoft-Konto anmelden, können auch eine PIN in **Einstellungen**  >  **Anmeldeoptionen**  >  **PIN hinzufügen** einrichten. Diese PIN ist [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)und nicht [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)zugeordnet.

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Wie wird die biometrische Iris-Authentifizierung auf HoloLens 2 implementiert?

HoloLens 2 unterstützt die Iris-Authentifizierung. Iris basiert auf Windows Hello Technologie und wird sowohl von Azure Active Directory als auch von Microsoft-Konten unterstützt. Iris wird auf die gleiche Weise wie andere Windows Hello-Technologien implementiert und erreicht biometrische Sicherheit von 1/100 KB.

Weitere Informationen finden Sie in den [biometrischen Anforderungen und Spezifikationen für Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) Erfahren Sie mehr über [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) und [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Wie wirkt sich der Kontotyp auf das Anmeldeverhalten aus?

Wenn Sie Richtlinien für die Anmeldung anwenden, wird die Richtlinie immer beachtet. Wenn keine Richtlinie für die Anmeldung angewendet wird, sind dies die Standardverhaltensweisen für jeden Kontotyp:

- **Azure AD:** fordert standardmäßig die Authentifizierung an und kann über **Einstellungen** konfiguriert werden, um keine Authentifizierung mehr anzufordern.
- **Microsoft-Konto:** Das Sperrverhalten unterscheidet sich, sodass das automatische Entsperren möglich ist, die Anmeldeauthentifizierung ist jedoch nach dem Neustart weiterhin erforderlich.
- **Lokales Konto:** Fordert immer die Authentifizierung in Form eines Kennworts an, das in **den Einstellungen** nicht konfiguriert werden kann.

> [!NOTE]
> Inaktivitätstimer werden derzeit nicht unterstützt. Dies bedeutet, dass die **Richtlinie AllowIdleReturnWithoutPassword** nur berücksichtigt wird, wenn das Gerät in StandBy wechselt.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

Weitere Informationen zum Schutz und zur Authentifizierung von Benutzeridentitäten finden Sie [in der Dokumentation zu sicherheit und identitätsbasierten Windows 10](https://docs.microsoft.com/windows/security/identity-protection/).

Weitere Informationen zum Einrichten der Hybrididentitätsinfrastruktur finden Sie in der Dokumentation zur [Azure-Hybrididentität.](https://docs.microsoft.com/azure/active-directory/hybrid/)
