---
title: Verwalten der Benutzeridentität und der Anmeldung für HoloLens
description: Erfahren Sie, wie Sie benutzeridentität, Unterstützung für mehrere Benutzer, Sicherheit, Unternehmensauthentifizierung und Anmeldung für HoloLens-Geräte verwalten.
keywords: HoloLens, Benutzer, Konto, AAD, Azure AD, Adfs, Microsoft-Konto, Msa, Anmeldeinformationen, Referenz
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
ms.openlocfilehash: d9b7bebd9fd326def4ddfc2982bfecb09cb14186
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283276"
---
# Verwalten der Benutzeridentität und der Anmeldung für HoloLens

> [!NOTE]
> Dieser Artikel ist eine technische Referenz für IT-Profis und Tech-Interessierte. Wenn Sie nach Anleitungen zum Einrichten von HoloLens suchen, lesen Sie "Einrichten Ihrer[HoloLens (1. Generation)](hololens1-start.md)" oder "[Einrichten Ihrer HoloLens 2".](hololens2-start.md)

Wie andere Windows-Geräte arbeitet HoloLens immer unter einem Benutzerkontext. Es gibt immer eine Benutzeridentität. HoloLens behandelt Identität fast genauso wie andere Windows 10-Geräte. Dieser Artikel ist eine tiefgehende Referenz zur Identität auf HoloLens und befasst sich mit dem Unterschied zwischen HoloLens und anderen Windows 10-Geräten.

HoloLens unterstützt verschiedene Arten von Benutzeridentitäten. Sie können sich mit einem oder mehreren Benutzerkonten anmelden. Hier ist eine Übersicht über die Identitätstypen und Authentifizierungsoptionen für HoloLens:

| Identitätstyp | Konten pro Gerät | Authentifizierungsoptionen |
| --- | --- | --- |
| [Azure Active Directory (AzureAD)](https://docs.microsoft.com/azure/active-directory/) | 64 | <ul><li>Azure Web Credential Provider</li><li>Azure Authenticator App</li><li>Biometrie (Iris) &ndash; HoloLens 2 nur <sup> 1</sup> </li><li>Pin &ndash; optional für HoloLens (1. Generation), erforderlich für HoloLens 2</li><li>Kennwort</li></ul> |
| [Microsoft Account (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Nur &ndash; HoloLens 2 biometrisch (Iris)</li><li>Pin &ndash; optional für HoloLens (1. Generation), erforderlich für HoloLens 2</li><li>Kennwort</li></ul> |
| [Lokales Konto](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Kennwort |

Mit der Cloud verbundene Konten (Azure AD und MSA) bieten weitere Features, da sie die Dienste von Azure nutzen können.  

> [!NOTE]
> 1 – Ein HoloLens 2-Gerät kann zwar bis zu 64 Azure AD-Konten unterstützen, aber nur 10 dieser Konten können sich für die Irisauthentifizierung registrieren. Dies wird mit anderen [biometrischen Authentifizierungsoptionen für Windows Hello for Business abgestimmt.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## Einrichten von Benutzern

Die gängigste Methode zum Einrichten eines neuen Benutzers ist die Verwendung der HoloLens-Out-of-Box-Erfahrung (OOBE). Während des Setups fordert HoloLens einen Benutzer auf, sich mit dem Konto anmelden, das er auf dem Gerät verwenden möchte. Bei diesem Konto kann es sich um ein Consumer-Microsoft-Konto oder ein Unternehmenskonto, das in Azure konfiguriert wurde, um ein Unternehmenskonto sein. Weitere Informationen finden Sie unter Einrichten Ihrer [HoloLens (1. Generation)](hololens1-start.md) oder [HoloLens 2.](hololens2-start.md)

Wie bei Windows auf anderen Geräten wird beim Anmelden während des Setups ein Benutzerprofil auf dem Gerät erstellt. Im Benutzerprofil werden Apps und Daten gespeichert. Dasselbe Konto bietet auch einmaliges Anmelden für Apps wie Edge oder Skype mithilfe der Windows Account Manager-APIs.  

Wenn Sie ein Unternehmens- oder Organisationskonto für die Anmeldung bei HoloLens verwenden, registriert sich HoloLens in der IT-Infrastruktur der Organisation. Diese Registrierung ermöglicht Es Ihrem IT-Administrator, die Mobile Device Management (MDM) so zu konfigurieren, dass Gruppenrichtlinien an Ihre HoloLens gesendet werden.

Wie bei anderen Windows 10-Geräten müssen Sie sich standardmäßig erneut anmelden, wenn HoloLens neu gestartet oder aus dem Standbymodus fortgesetzt wird. Sie können dieses Verhalten mithilfe der App "Einstellungen" ändern, oder das Verhalten kann durch Gruppenrichtlinien gesteuert werden.

### Verknüpfte Konten

Wie in der Desktopversion von Windows können Sie zusätzliche Webkontoanmeldeinformationen mit Ihrem HoloLens-Konto verknüpfen. Eine solche Verknüpfung erleichtert den Zugriff auf Ressourcen in Apps (z. B. dem Store) oder das Kombinieren des Zugriffs auf persönliche und Arbeitsressourcen. Nachdem Sie ein Konto mit dem Gerät verbinden, können Sie die Berechtigung zum Verwenden des Geräts für Apps erteilen, damit Sie sich nicht einzeln bei jeder App anmelden müssen.

Durch das Verknüpfen von Konten werden die auf dem Gerät erstellten Benutzerdaten, z. B. Bilder oder Downloads, nicht getrennt.  

### Einrichten der Unterstützung für mehrere Benutzer (nur Azure AD)

HoloLens unterstützt mehrere Benutzer aus demselben Azure AD-Mandanten. Um dieses Feature verwenden zu können, müssen Sie zum Einrichten des Geräts ein Konto verwenden, das Zu Ihrer Organisation gehört. Anschließend können sich andere Benutzer aus demselben Mandanten über den Anmeldebildschirm oder durch Tippen auf die Benutzerkachel im Startbereich beim Gerät anmelden. Es kann immer nur ein Benutzer angemeldet werden. Wenn sich ein Benutzer meldet, meldet HoloLens den vorherigen Benutzer ab. Der erste Benutzer auf dem Gerät wird als Gerätebesitzer betrachtet, außer im Falle des Azure AD Join, erfahren Sie mehr [über Gerätebesitzer.](security-adminless-os.md#device-owner)

Alle Benutzer können die auf dem Gerät installierten Apps verwenden. Jeder Benutzer verfügt jedoch über eigene App-Daten und -Einstellungen. Wenn Sie eine App vom Gerät entfernen, wird sie für alle Benutzer entfernt.  

Geräte, die mit Azure AD-Konten eingerichtet sind, lassen keine Anmeldung am Gerät mit einem Microsoft-Konto zu. Alle nachfolgend verwendeten Konten müssen Azure AD-Konten aus demselben Mandanten wie das Gerät sein. Sie können sich [weiterhin mit einem Microsoft-Konto](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) bei Apps anmelden, die es unterstützen (z. B. den Microsoft Store). Um von der Verwendung von Azure AD-Konten zu Microsoft-Konten für die Anmeldung am Gerät zu wechseln, müssen Sie [das Gerät neu schrägen.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens (1. Generation)** begann mit der Unterstützung mehrerer Azure AD-Benutzer im [Windows 10 April 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) als Teil von [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

## Entfernen von Benutzern

Sie können einen Benutzer vom Gerät entfernen, indem Sie zu **"Einstellungen"**  >  **"Konten**  >  **andere Personen" gehen.** Durch diese Aktion wird auch Speicherplatz freigegeben, indem alle App-Daten dieses Benutzers vom Gerät entfernt werden.  

## Verwenden des einmaligen Anmeldens in einer App

Als App-Entwickler können Sie verknüpfte Identitäten auf HoloLens nutzen, indem Sie die [Windows Account Manager-APIs](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)verwenden, genau wie auf anderen Windows-Geräten. Einige Codebeispiele für diese APIs sind auf GitHub verfügbar: [Beispiel für die Webkontoverwaltung.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

Alle eventuellen Kontounterbrechungen, z. B. das Anfordern der Zustimmung des Benutzers für Kontoinformationen, die zweistufige Authentifizierung usw., müssen behandelt werden, wenn die App ein Authentifizierungstoken anfordert.

Wenn Ihre App einen bestimmten Kontotyp erfordert, der zuvor noch nicht verknüpft wurde, kann Ihre App das System bitten, den Benutzer auf, einen hinzuzufügen. Diese Anforderung löst den Bereich "Kontoeinstellungen" aus, der als modales untergeordnetes Kind Ihrer App gestartet wird. Bei 2D-Apps wird dieses Fenster direkt über der Mitte Ihrer App gerendert. Bei Unity-Apps nimmt diese Anforderung den Benutzer kurz aus Ihrer holografischen App, um das untergeordnete Fenster zu rendern. Informationen zum Anpassen der Befehle und Aktionen in diesem Bereich finden Sie unter [WebAccountCommand Class](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## Unternehmens- und andere Authentifizierung

Wenn Ihre App andere Authentifizierungstypen wie NTLM, Basic oder Kerberos verwendet, können Sie die [Windows-Anmeldeinformations-UI](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) verwenden, um die Anmeldeinformationen des Benutzers zu sammeln, zu verarbeiten und zu speichern. Die Benutzeroberfläche zum Sammeln dieser Anmeldeinformationen ähnelt anderen cloudgesteuerten Kontounterbrechungen und wird als untergeordnete App über Ihrer 2D-App angezeigt oder eine Unity-App kurz angehalten, um die Benutzeroberfläche anzeigen zu können.

## Veraltete APIs

Eine Möglichkeit, wie sich die Entwicklung für HoloLens von der Entwicklung für Desktop unterscheidet, ist, dass die [OnlineIDAuthenticator-API](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) nicht vollständig unterstützt wird. Obwohl die API ein Token zurückgibt, wenn das primäre Konto einen guten Stand hat, zeigen Unterbrechungen wie die in diesem Artikel beschriebenen keine Benutzeroberfläche für den Benutzer an und können das Konto nicht ordnungsgemäß authentifizieren.

## Häufig gestellte Fragen

### Wird Windows Hello for Business auf HoloLens (1. Generation) unterstützt?

Windows Hello for Business (unterstützt die Verwendung einer PIN zum Anmelden) wird für HoloLens (1. Generation) unterstützt. So lassen Sie die Windows Hello for Business-PIN-Anmeldung bei HoloLens zu:

1. Das HoloLens-Gerät muss von [MDM verwaltet werden.](hololens-enroll-mdm.md)
1. Sie müssen Windows Hello for Business für das Gerät aktivieren. ([Siehe Anweisungen für Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello))
1. Auf HoloLens kann der Benutzer **** dann die Einstellungs-Anmeldeoptionen verwenden, um  >  ****  >  **eine PIN** hinzuzufügen.

> [!NOTE]
> Benutzer, die sich mit einem Microsoft-Konto anmelden, können auch eine PIN **in**den Anmeldeoptionen "Einstellungen" einrichten. Fügen Sie  >  ****  >  **eine PIN hinzu.** Diese PIN ist [Windows Hello und](https://support.microsoft.com/help/17215/windows-10-what-is-hello)nicht Windows Hello for Business [zugeordnet.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)

### Wie wird die biometrische Authentifizierung von Iris auf HoloLens 2 implementiert?

HoloLens 2 unterstützt die Irisauthentifizierung. Iris basiert auf der Windows Hello-Technologie und wird sowohl von Azure Active Directory- als auch von Microsoft-Konten unterstützt. Iris wird auf die gleiche Weise wie andere Windows -Hello-Technologien implementiert und erreicht biometrische Sicherheit far von 1/100K.

Weitere Informationen finden Sie in den [biometrischen Anforderungen und](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) Spezifikationen für Windows Hello. Erfahren Sie mehr über [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) und Windows Hello [for Business.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) 

### Wie wirkt sich der Kontotyp auf das Anmeldeverhalten aus?

Wenn Sie Richtlinien für die Sign-In-Verhalten verwenden, werden die Richtlinie immer berücksichtigt. Wenn keine Richtlinie für die Anmeldung angewendet wird, sind dies die Standardverhalten für jeden Kontotyp:

- **Azure AD**: fordert standardmäßig die Authentifizierung **** an und kann durch Einstellungen so konfiguriert werden, dass keine Authentifizierung mehr erforderlich ist.
- **Microsoft-Konto:** Das Sperrverhalten ist anders und ermöglicht die automatische Entsperrung. Die Anmeldeauthentifizierung ist jedoch beim Neustart weiterhin erforderlich.
- **Lokales Konto:** fordert immer die Authentifizierung in Form eines Kennworts an, nicht **in** den Einstellungen konfigurierbar

> [!NOTE]
> Inaktivitätszeitgeber werden derzeit nicht unterstützt. Dies bedeutet, dass die **Richtlinie "AllowIdleReturnWithoutPassword"** nur berücksichtigt wird, wenn das Gerät in "StandBy" eingereiht wird.

## Zusätzliche Ressourcen

Weitere Informationen zum Schutz und zur Authentifizierung von Benutzeridentität finden Sie in der Sicherheits- und Identitätsdokumentation [zu Windows 10.](https://docs.microsoft.com/windows/security/identity-protection/)

Weitere Informationen zum Einrichten der Hybrididentitätsinfrastruktur finden Sie in der [Dokumentation zur Azure Hybrid-Identität.](https://docs.microsoft.com/azure/active-directory/hybrid/)
