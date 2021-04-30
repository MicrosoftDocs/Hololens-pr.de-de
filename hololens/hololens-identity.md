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
ms.openlocfilehash: 2d84658ef76ff2c5d8ef7dabe857892e7129a965
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309887"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Verwalten der Benutzeridentität und Anmeldung für HoloLens

> [!NOTE]
> Dieser Artikel ist eine technische Referenz für IT-Profis und Tech-Fans. Wenn Sie nach HoloLens-Einrichtungsanweisungen suchen, lesen Sie " Einrichten Ihrer[HoloLens (1. Generation)](hololens1-start.md)" oder "[Einrichten Ihrer](hololens2-start.md)HoloLens 2 ".

Wie andere Windows-Geräte arbeitet HoloLens immer unter einem Benutzerkontext. Es gibt immer eine Benutzeridentität. HoloLens behandelt Identitäten fast auf die gleiche Weise wie andere Windows 10 Geräte. Dieser Artikel ist eine tiefgehende Referenz zur Identität auf HoloLens und konzentriert sich darauf, wie sich HoloLens von anderen Windows 10 unterscheidet.

HoloLens unterstützt verschiedene Arten von Benutzeridentitäten. Sie können ein oder mehrere Benutzerkonten für die Anmeldung verwenden. Im Folgenden finden Sie eine Übersicht über die Identitätstypen und Authentifizierungsoptionen auf HoloLens:

| Identitätstyp | Konten pro Gerät | Authentifizierungsoptionen |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (erfordert Azure AD Premium) | 64 | <ul><li>Azure-Web-Anmeldeinformationsanbieter</li><li>Azure Authenticator-App</li><li>Biometrie (Iris) &ndash; HoloLens 2<sup>nur 1</sup> </li><li>PIN &ndash; optional für HoloLens (1. Generation), erforderlich für HoloLens 2</li><li>Kennwort</li></ul> |
| [Microsoft-Konto (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Nur biometrische &ndash; (Iris)-HoloLens 2</li><li>PIN &ndash; optional für HoloLens (1. Generation), erforderlich für HoloLens 2</li><li>Kennwort</li></ul> |
| [Lokales Konto](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Kennwort |

Mit der Cloud verbundene Konten (Azure AD und MSA) bieten mehr Features, da sie Azure-Dienste verwenden können.  

> [!NOTE]
> 1 – Während ein HoloLens 2 Gerät bis zu 64 Azure AD Konten unterstützen kann, können sich nur 10 dieser Konten bei Iris Authentication registrieren. Dies ist an anderen [biometrischen Authentifizierungsoptionen für Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)ausgerichtet.

## <a name="setting-up-users"></a>Einrichten von Benutzern

Die gängigste Methode zum Einrichten eines neuen Benutzers ist die Out-of-Box-Benutzeroberfläche (OOBE) von HoloLens. Während des Setups fordert HoloLens einen Benutzer auf, sich mit dem Konto anzumelden, das er auf dem Gerät verwenden möchte. Dieses Konto kann ein Consumer Microsoft-Konto oder ein Unternehmenskonto sein, das in Azure konfiguriert wurde. Weitere Informationen finden Sie unter Einrichten Von [HoloLens (1. Generation)](hololens1-start.md) oder [HoloLens 2](hololens2-start.md).

Wie bei Windows auf anderen Geräten wird bei der Anmeldung während des Setups ein Benutzerprofil auf dem Gerät erstellt. Das Benutzerprofil speichert Apps und Daten. Dasselbe Konto bietet auch einmaliges Anmelden für Apps wie Edge oder Skype mithilfe der Windows-Konto-Manager-APIs.  

Wenn Sie sich mit einem Unternehmens- oder Organisationskonto bei HoloLens anmelden, registriert sich HoloLens in der IT-Infrastruktur des Unternehmens. Mit dieser Registrierung kann Ihr IT-Administrator Mobile Geräteverwaltung (MDM) konfigurieren, um Gruppenrichtlinien an Ihre HoloLens zu senden.

Standardmäßig müssen Sie sich wie bei anderen Windows 10 Geräten erneut anmelden, wenn HoloLens neu gestartet oder aus dem Standbymodus fortgesetzt wird. Sie können dieses Verhalten mithilfe der Einstellungs-App ändern, oder das Verhalten kann durch Gruppenrichtlinien gesteuert werden.

### <a name="linked-accounts"></a>Verknüpfte Konten

Wie in der Desktopversion von Windows können Sie zusätzliche Webkontoanmeldeinformationen mit Ihrem HoloLens-Konto verknüpfen. Eine solche Verknüpfung erleichtert den Zugriff auf Ressourcen in oder innerhalb von Apps (z. B. dem Store) oder das Kombinieren des Zugriffs auf persönliche und Arbeitsressourcen. Nachdem Sie ein Konto mit dem Gerät verbunden haben, können Sie Apps die Berechtigung zum Verwenden des Geräts erteilen, damit Sie sich nicht einzeln bei jeder App anmelden müssen.

Beim Verknüpfen von Konten werden die auf dem Gerät erstellten Benutzerdaten, z. B. Bilder oder Downloads, nicht voneinander getrennt.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Einrichten der Unterstützung für mehrere Benutzer (nur Azure AD)

HoloLens unterstützt mehrere Benutzer aus demselben Azure AD Mandanten. Um dieses Feature verwenden zu können, müssen Sie zum Einrichten des Geräts ein Konto verwenden, das Ihrer Organisation angehört. Anschließend können sich andere Benutzer desselben Mandanten über den Anmeldebildschirm oder durch Tippen auf die Benutzerkachel im Startbereich beim Gerät anmelden. Es kann immer nur ein Benutzer gleichzeitig angemeldet werden. Wenn sich ein Benutzer anknabschreibt, wird der vorherige Benutzer von HoloLens ab- ab. Der erste Benutzer auf dem Gerät wird als Gerätebesitzer betrachtet, mit Ausnahme von Azure AD Join weitere [Informationen zu Gerätebesitzern.](security-adminless-os.md#device-owner)

Alle Benutzer können die auf dem Gerät installierten Apps verwenden. Jeder Benutzer verfügt jedoch über eigene App-Daten und -Einstellungen. Wenn Sie eine App vom Gerät entfernen, wird sie für alle Benutzer entfernt.  

Geräte, die mit Azure AD-Konten eingerichtet sind, lassen die Anmeldung beim Gerät mit einem Microsoft-Konto nicht zu. Alle nachfolgend verwendeten Konten müssen Azure AD demselben Mandanten wie das Gerät verwendet werden. Sie können sich [weiterhin mit einem Microsoft-Konto bei](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) Apps anmelden, die es unterstützen (z. B. Microsoft Store). Um von der Verwendung Azure AD-Konten zu Microsoft-Konten für die Anmeldung beim Gerät zu wechseln, müssen Sie das Gerät neu [erstellen.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens (1. Generation)** hat damit begonnen, [](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) mehrere Azure AD-Benutzer in der Windows 10 April 2018 Update im Rahmen von [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

## <a name="removing-users"></a>Entfernen von Benutzern

Sie können einen Benutzer vom Gerät entfernen, indem Sie zu **Einstellungen**  >  **Konten Andere**  >  **Personen.** Diese Aktion gibt auch Speicherplatz frei, indem alle App-Daten dieses Benutzers vom Gerät entfernt werden.  

## <a name="using-single-sign-on-within-an-app"></a>Verwenden des einmaligen Anmeldens in einer App

Als App-Entwickler können Sie verknüpfte Identitäten auf HoloLens wie auf anderen Windows-Geräten mithilfe der [Windows-Konto-Manager-APIs](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)nutzen. Einige Codebeispiele für diese APIs sind auf GitHub verfügbar: Beispiel für [die Webkontoverwaltung.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

Kontounterbrechungen, die auftreten können, z. B. das Anfordern der Benutzereinwilligung für Kontoinformationen, die zweistufige Authentifizierung usw., müssen behandelt werden, wenn die App ein Authentifizierungstoken anfordert.

Wenn Ihre App einen bestimmten Kontotyp erfordert, der zuvor nicht verknüpft wurde, kann Ihre App das System auffordern, den Benutzer aufzufordern, einen hinzuzufügen. Diese Anforderung löst den Kontoeinstellungsbereich aus, der als modales untergeordnetes Element Ihrer App gestartet wird. Bei 2D-Apps wird dieses Fenster direkt über die Mitte Ihrer App gerendert. Bei Unity-Apps nimmt diese Anforderung den Benutzer kurz aus Ihrer holografischen App heraus, um das untergeordnete Fenster zu rendern. Informationen zum Anpassen der Befehle und Aktionen in diesem Bereich finden Sie unter [WebAccountCommand-Klasse.](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)

## <a name="enterprise-and-other-authentication"></a>Unternehmensauthentifizierung und andere Authentifizierung

Wenn Ihre App andere Authentifizierungstypen wie NTLM, Basic oder Kerberos verwendet, können Sie die [Windows-Anmeldeinformations-Benutzeroberfläche](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) verwenden, um die Anmeldeinformationen des Benutzers zu erfassen, zu verarbeiten und zu speichern. Die Benutzeroberfläche zum Sammeln dieser Anmeldeinformationen ähnelt sehr anderen cloudgesteuerten Kontounterbrechungen und wird als untergeordnete App auf Ihrer 2D-App angezeigt oder hält eine Unity-App kurz an, um die Benutzeroberfläche anzuzeigen.

## <a name="deprecated-apis"></a>Nicht mehr unterstützte APIs

Eine Möglichkeit, wie sich die Entwicklung für HoloLens von der Entwicklung für Desktop unterscheidet, besteht darin, dass die [OnlineIDAuthenticator-API](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) nicht vollständig unterstützt wird. Obwohl die API ein Token zurückgibt, wenn das primäre Konto fehlerfrei ist, zeigen Unterbrechungen wie die in diesem Artikel beschriebenen keine Benutzeroberfläche für den Benutzer an und können das Konto nicht ordnungsgemäß authentifizieren.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Wird Windows Hello for Business auf HoloLens (1. Generation) unterstützt?

Windows Hello for Business (die die Verwendung einer PIN für die Anmeldung unterstützt) wird für HoloLens (1. Generation) unterstützt. So lassen Sie Windows Hello for Business PIN-Anmeldung bei HoloLens zu:

1. Das HoloLens-Gerät muss von [MDM verwaltet werden.](hololens-enroll-mdm.md)
1. Sie müssen die Windows Hello for Business für das Gerät aktivieren. ([Siehe Anweisungen für Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello))
1. Auf HoloLens kann der Benutzer dann einstellungen Anmeldeoptionen PIN hinzufügen verwenden, um eine  >    >  **PIN** zu einrichten.

> [!NOTE]
> Benutzer, die sich mithilfe eines Microsoft-Konto anmelden, können auch eine PIN **unter** Einstellungen  >  **Anmeldeoptionen** PIN hinzufügen  >  **einrichten.** Diese PIN ist [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)zugeordnet, anstatt [Windows Hello for Business.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Wie wird die biometrische Iris-Authentifizierung auf HoloLens 2?

HoloLens 2 unterstützt die Iris-Authentifizierung. Iris basiert auf Windows Hello-Technologie und wird für die Verwendung durch Azure Active Directory microsoft-Konten unterstützt. Iris wird auf die gleiche Weise wie andere Windows Hello implementiert und erreicht die biometrische Sicherheit FAR von 1/100.000.

Weitere Informationen [finden Sie in den biometrischen Anforderungen Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) Spezifikationen. Erfahren Sie mehr [über Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) [und Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Wie wirkt sich der Kontotyp auf das Anmeldeverhalten aus?

Wenn Sie Richtlinien für die Anmeldung anwenden, wird die Richtlinie immer beachtet. Wenn keine Richtlinie für die Anmeldung angewendet wird, sind dies die Standardverhalten für jeden Kontotyp:

- **Azure AD**: fordert standardmäßig zur Authentifizierung auf  und kann von den Einstellungen konfiguriert werden, um keine Authentifizierung mehr zu erfragen.
- **Microsoft-Konto:** Das Sperrverhalten ist anders, sodass die automatische Entsperrung ermöglicht wird, aber die Anmeldeauthentifizierung ist beim Neustart weiterhin erforderlich.
- **Lokales Konto:** Fordert immer die Authentifizierung in Form eines Kennworts an, das in den Einstellungen nicht konfigurierbar **ist.**

> [!NOTE]
> Inaktivitäts-Timer werden derzeit nicht unterstützt. Dies bedeutet, dass die **Richtlinie AllowIdleReturnWithoutPassword** nur berücksichtigt wird, wenn das Gerät in StandBy übergeht.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

Weitere Informationen zum Schutz der Benutzeridentität und zur Authentifizierung finden Sie in der Windows 10 security and identity documentation (Sicherheits- [und Identitätsdokumentation).](https://docs.microsoft.com/windows/security/identity-protection/)

Weitere Informationen zum Einrichten der Hybrididentitätsinfrastruktur finden Sie in der Dokumentation zur [Azure-Hybrididentität.](https://docs.microsoft.com/azure/active-directory/hybrid/)
