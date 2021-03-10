---
title: Verwalten der Benutzeridentität und der Anmeldung für HoloLens
description: Erfahren Sie, wie Sie benutzeridentität, Mehrbenutzerunterstützung, Sicherheit, Unternehmensauthentifizierung und Anmeldung für HoloLens-Geräte verwalten.
keywords: HoloLens, Benutzer, Konto, AAD, Azure AD, Adfs, Microsoft-Konto, msa, Anmeldeinformationen, Referenz
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
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400685"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Verwalten der Benutzeridentität und der Anmeldung für HoloLens

> [!NOTE]
> Dieser Artikel ist eine technische Referenz für IT-Profis und Tech-Enthusiasten. Wenn Sie nach Anleitungen zum Einrichten von HoloLens suchen, lesen Sie " Einrichten Ihrer[HoloLens (1. Generation)](hololens1-start.md)" oder " Einrichten Ihrer[HoloLens 2](hololens2-start.md)".

Wie andere Windows-Geräte arbeitet HoloLens immer unter einem Benutzerkontext. Es gibt immer eine Benutzeridentität. HoloLens behandelt Identität fast genauso wie andere Windows 10-Geräte. Dieser Artikel ist eine tiefgehende Referenz zur Identität auf HoloLens und befasst sich mit der Unterschiede zwischen HoloLens und anderen Windows 10-Geräten.

HoloLens unterstützt verschiedene Arten von Benutzeridentitäten. Sie können sich mit einem oder mehreren Benutzerkonten anmelden. Im Folgenden finden Sie eine Übersicht über die Identitätstypen und Authentifizierungsoptionen für HoloLens:

| Identitätstyp | Konten pro Gerät | Authentifizierungsoptionen |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (erfordert Azure AD Premium) | 64 | <ul><li>Azure Web Credential Provider</li><li>Azure Authenticator App</li><li>Biometrische (Iris) &ndash; HoloLens 2 nur <sup> 1</sup> </li><li>PIN &ndash; Optional für HoloLens (1. Generation), erforderlich für HoloLens 2</li><li>Kennwort</li></ul> |
| [Microsoft-Konto (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Nur biometrisches &ndash; HoloLens 2 (Iris)</li><li>PIN &ndash; Optional für HoloLens (1. Generation), erforderlich für HoloLens 2</li><li>Kennwort</li></ul> |
| [Lokales Konto](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Kennwort |

Mit der Cloud verbundene Konten (Azure AD und MSA) bieten weitere Features, da sie Azure-Dienste nutzen können.  

> [!NOTE]
> 1 – Ein HoloLens 2-Gerät kann zwar bis zu 64 Azure AD-Konten unterstützen, aber nur 10 dieser Konten können sich für die Irisauthentifizierung registrieren. Dies ist an anderen [biometrischen Authentifizierungsoptionen für Windows Hello for Business ausgerichtet.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## <a name="setting-up-users"></a>Einrichten von Benutzern

Die häufigste Methode zum Einrichten eines neuen Benutzers ist die Out-of-Box-Erfahrung (OOBE) von HoloLens. Während des Setups fordert HoloLens einen Benutzer auf, sich mit dem Konto zu anmelden, das er auf dem Gerät verwenden möchte. Bei diesem Konto kann es sich um ein Verbraucher-Microsoft-Konto oder ein Unternehmenskonto, das in Azure konfiguriert wurde, um ein Microsoft-Verbraucherkonto oder um ein Unternehmenskonto, das in Azure konfiguriert wurde. Weitere Informationen finden Sie unter Einrichten ihrer [HoloLens (1. Generation)](hololens1-start.md) oder [HoloLens 2](hololens2-start.md).

Wie bei Windows auf anderen Geräten wird beim Anmelden während des Setups ein Benutzerprofil auf dem Gerät erstellt. Im Benutzerprofil werden Apps und Daten gespeichert. Dasselbe Konto bietet auch einmaliges Anmelden für Apps wie Edge oder Skype mithilfe der Windows Account Manager-APIs.  

Wenn Sie sich mit einem Unternehmens- oder Organisationskonto bei HoloLens anmelden, registriert sich HoloLens in der IT-Infrastruktur der Organisation. Mit dieser Registrierung kann Ihr IT-Administrator mobile Geräteverwaltung (Mobile Device Management, MDM) so konfigurieren, dass Gruppenrichtlinien an Ihre HoloLens gesendet werden.

Wie bei anderen Windows 10-Geräten müssen Sie sich standardmäßig erneut anmelden, wenn HoloLens neu gestartet oder aus dem Standbymodus fortgesetzt wird. Sie können die Einstellungs-App verwenden, um dieses Verhalten zu ändern, oder das Verhalten kann durch Gruppenrichtlinien gesteuert werden.

### <a name="linked-accounts"></a>Verknüpfte Konten

Wie in der Desktopversion von Windows können Sie zusätzliche Webkontoanmeldeinformationen mit Ihrem HoloLens-Konto verknüpfen. Eine solche Verknüpfung erleichtert den Zugriff auf Ressourcen in Apps (z. B. dem Store) oder das Kombinieren des Zugriffs auf persönliche und Arbeitsressourcen. Nachdem Sie ein Konto mit dem Gerät verbinden, können Sie die Berechtigung zum Verwenden des Geräts für Apps erteilen, damit Sie sich nicht einzeln bei jeder App anmelden müssen.

Durch das Verknüpfen von Konten werden die auf dem Gerät erstellten Benutzerdaten, z. B. Bilder oder Downloads, nicht getrennt.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Einrichten der Mehrbenutzerunterstützung (nur Azure AD)

HoloLens unterstützt mehrere Benutzer aus demselben Azure AD-Mandanten. Um dieses Feature verwenden zu können, müssen Sie ein Konto verwenden, das zu Ihrer Organisation gehört, um das Gerät einrichten zu können. Anschließend können sich andere Benutzer aus demselben Mandanten über den Anmeldebildschirm oder durch Tippen auf die Benutzerkachel im Startbereich beim Gerät anmelden. Es kann immer nur ein Benutzer angemeldet werden. Wenn sich ein Benutzer meldet, meldet HoloLens den vorherigen Benutzer ab. Der erste Benutzer auf dem Gerät wird als Gerätebesitzer betrachtet, außer im Fall von Azure AD Join erfahren Sie mehr [über Gerätebesitzer](security-adminless-os.md#device-owner).

Alle Benutzer können die auf dem Gerät installierten Apps verwenden. Jeder Benutzer verfügt jedoch über eigene App-Daten und -Einstellungen. Wenn Sie eine App vom Gerät entfernen, wird sie für alle Benutzer entfernt.  

Geräte, die mit Azure AD-Konten eingerichtet sind, ermöglichen keine Anmeldung beim Gerät mit einem Microsoft-Konto. Alle nachfolgend verwendeten Konten müssen Azure AD-Konten aus demselben Mandanten wie das Gerät sein. Sie können sich [weiterhin mit einem Microsoft-Konto](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) bei Apps anmelden, die es unterstützen (z. B. den Microsoft Store). Um die Verwendung von Azure AD-Konten zu Microsoft-Konten für die Anmeldung beim Gerät zu ändern, müssen Sie [den Schrägstrich für das Gerät neu ändern.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens (1. Generation)** hat begonnen, mehrere Azure AD-Benutzer im [Windows 10 April 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) als Teil von [Windows Holographic for Business zu unterstützen.](hololens-upgrade-enterprise.md)

## <a name="removing-users"></a>Entfernen von Benutzern

Sie können einen Benutzer vom Gerät entfernen, indem Sie zu **Einstellungen**  >  **Konten**  >  **Andere Personen gehen.** Mit dieser Aktion wird auch Speicherplatz freigegeben, indem alle App-Daten dieses Benutzers vom Gerät entfernt werden.  

## <a name="using-single-sign-on-within-an-app"></a>Verwenden des einmaligen Anmeldens in einer App

Als App-Entwickler können Sie verknüpfte Identitäten auf HoloLens nutzen, indem Sie die [Windows Account Manager-APIs](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)verwenden, genau wie auf anderen Windows-Geräten. Einige Codebeispiele für diese APIs finden Sie unter GitHub: [Web account management sample](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Alle möglicherweise eintretenden Kontounterbrechungen, z. B. das Anfordern der Zustimmung des Benutzers für Kontoinformationen, die zweistufige Authentifizierung usw., müssen behandelt werden, wenn die App ein Authentifizierungstoken anfordert.

Wenn Ihre App einen bestimmten Kontotyp erfordert, der zuvor nicht verknüpft wurde, kann Ihre App das System bitten, den Benutzer zum Hinzufügen eines Kontos aufforderen. Diese Anforderung löst den Bereich kontoeinstellungen aus, der als modales untergeordnetes Gerät Ihrer App gestartet wird. Bei 2D-Apps wird dieses Fenster direkt über der Mitte Ihrer App gerendert. Bei Unity-Apps führt diese Anforderung den Benutzer kurz aus Ihrer holografischen App, um das untergeordnete Fenster zu rendern. Informationen zum Anpassen der Befehle und Aktionen in diesem Bereich finden Sie unter [WebAccountCommand Class](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Unternehmens- und andere Authentifizierung

Wenn Ihre App andere Authentifizierungstypen wie NTLM, Basic oder Kerberos verwendet, können Sie die Anmeldeinformationen des Benutzers mithilfe der [Benutzeroberfläche](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) für Windows-Anmeldeinformationen erfassen, verarbeiten und speichern. Die Benutzeroberfläche zum Sammeln dieser Anmeldeinformationen ähnelt sehr anderen cloudgesteuerten Kontounterbrechungen und wird als untergeordnete App über Ihrer 2D-App angezeigt oder eine Unity-App kurz angehalten, um die Benutzeroberfläche zu zeigen.

## <a name="deprecated-apis"></a>Veraltete APIs

Eine Möglichkeit, wie sich die Entwicklung für HoloLens von der Entwicklung für Desktop unterscheidet, ist, dass die [OnlineIDAuthenticator-API](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) nicht vollständig unterstützt wird. Obwohl die API ein Token zurückgibt, wenn sich das primäre Konto in einem guten Zustand befindet, zeigen Unterbrechungen wie die in diesem Artikel beschriebenen keine Benutzeroberfläche für den Benutzer an und können das Konto nicht ordnungsgemäß authentifizieren.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Wird Windows Hello for Business auf HoloLens (1. Generation) unterstützt?

Windows Hello for Business (unterstützt die Verwendung einer PIN zum Anmelden) wird für HoloLens (1. Generation) unterstützt. So lassen Sie die Windows Hello for Business-PIN-Anmeldung bei HoloLens zu:

1. Das HoloLens-Gerät muss von [MDM verwaltet werden.](hololens-enroll-mdm.md)
1. Sie müssen Windows Hello for Business für das Gerät aktivieren. ([Siehe Anweisungen für Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello))
1. In HoloLens kann der Benutzer **** dann Einstellungen Anmelden Optionen PIN hinzufügen verwenden,  >  ****  >  **** um eine PIN einrichten.

> [!NOTE]
> Benutzer, die sich mit einem Microsoft-Konto anmelden, können auch eine PIN unter **Einstellungen**Anmelden  >  **Optionen PIN**hinzufügen  >  **einrichten.** Diese PIN ist [Windows Hello und](https://support.microsoft.com/help/17215/windows-10-what-is-hello)nicht Windows Hello for Business [zugeordnet.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Wie wird die biometrische Irisauthentifizierung in HoloLens 2 implementiert?

HoloLens 2 unterstützt die Irisauthentifizierung. Iris basiert auf der Windows Hello-Technologie und wird sowohl von Azure Active Directory als auch von Microsoft-Konten unterstützt. Iris wird auf die gleiche Weise wie andere Windows Hello-Technologien implementiert und erreicht biometrische Sicherheit FAR von 1/100K.

Weitere Informationen finden Sie in den biometrischen Anforderungen und Spezifikationen für [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) Erfahren Sie mehr [über Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) und Windows Hello for [Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Wie wirkt sich der Kontotyp auf das Anmeldeverhalten aus?

Wenn Sie Richtlinien für die Sign-In-Verhalten verwenden, werden die Richtlinie immer berücksichtigt. Wenn keine Richtlinie für die Anmeldung angewendet wird, sind dies die Standardverhalten für jeden Kontotyp:

- **Azure AD**: fordert standardmäßig die Authentifizierung **** an und kann durch Einstellungen so konfiguriert werden, dass keine Authentifizierung mehr erforderlich ist.
- **Microsoft-Konto:** Das Sperrverhalten ist unterschiedlich, sodass die automatische Entsperrung ermöglicht wird, die Anmeldeauthentifizierung ist jedoch beim Neustart weiterhin erforderlich.
- **Lokales Konto**: fordert immer die Authentifizierung in Form eines Kennworts an, nicht konfigurierbar unter **Einstellungen**

> [!NOTE]
> Inaktivitätszeitgeber werden derzeit nicht unterstützt, was bedeutet, dass die **AllowIdleReturnWithoutPassword-Richtlinie** nur beachtet wird, wenn das Gerät in StandBy eingeht.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

Weitere Informationen zum Schutz und zur Authentifizierung von Benutzeridentität finden Sie in der [Windows 10-Sicherheits- und Identitätsdokumentation](https://docs.microsoft.com/windows/security/identity-protection/).

Weitere Informationen zum Einrichten einer Hybrididentitätsinfrastruktur finden Sie in der [Azure Hybrid Identity Documentation](https://docs.microsoft.com/azure/active-directory/hybrid/).
