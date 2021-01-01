---
title: Verwalten der Benutzeridentität und der Anmeldung für HoloLens
description: Verwalten von Benutzeridentität, Sicherheit und Anmeldung für HoloLens.
keywords: HoloLens, Benutzer, Konto, AAD, Azure AD, ADFS, Microsoft-Konto, MSA, Anmeldeinformationen, Referenz
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
ms.openlocfilehash: 96e3b90a24d297631d39a1eb62888e4f4aa1098e
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253222"
---
# Verwalten der Benutzeridentität und der Anmeldung für HoloLens

> [!NOTE]
> Dieser Artikel ist eine technische Referenz für IT-Experten und Tech-Enthusiasten. Wenn Sie nach Anleitungen für die HoloLens-Einrichtung suchen, lesen Sie "[Einrichten Ihres HoloLens (1st Generation)](hololens1-start.md)" oder "[Einrichten Ihres HoloLens 2](hololens2-start.md)".

Wie bei anderen Windows-Geräten funktioniert HoloLens immer unter einem Benutzerkontext. Es gibt immer eine Benutzeridentität. HoloLens behandelt Identität auf fast die gleiche Weise wie andere Windows 10-Geräte. Dieser Artikel ist ein Deep-Dive-Referenz für Identity auf HoloLens und konzentriert sich auf die Unterschiede zwischen HoloLens und anderen Windows 10-Geräten.

HoloLens unterstützt verschiedene Arten von Benutzeridentitäten. Sie können ein oder mehrere Benutzerkonten zur Anmeldung verwenden. Nachfolgend finden Sie eine Übersicht über die Identitätstypen und Authentifizierungsoptionen in HoloLens:

| Identity-Typ | Konten pro Gerät | Authentifizierungsoptionen |
| --- | --- | --- |
| [Azure Active Directory (AzureAD)](https://docs.microsoft.com/azure/active-directory/) | 64 | <ul><li>Azure Web Credential-Anbieter</li><li>Azure Authenticator-App</li><li>Biometrische (IRIS) &ndash; HoloLens 2 nur <sup> 1</sup> </li><li>PIN &ndash; optional für HoloLens (1st Gen), erforderlich für HoloLens 2</li><li>Kennwort</li></ul> |
| [Microsoft-Konto (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Nur biometrische (IRIS) &ndash; HoloLens 2</li><li>PIN &ndash; optional für HoloLens (1st Gen), erforderlich für HoloLens 2</li><li>Kennwort</li></ul> |
| [Lokales Konto](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Kennwort |

Cloud-verbundene Konten (Azure AD und MSA) bieten weitere Features, da Sie Azure-Dienste verwenden können.  

> [!NOTE]
> 1 – während ein HoloLens 2-Gerät bis zu 64 Azure Ad-Konten unterstützenkann, können sich nur 10 dieser Konten bei der Iris-Authentifizierung registrieren. Dies ist an andere biometrische Authentifizierungsoptionen für Windows Hello for Business ausgerichtet. [Weitere Informationen finden Sie hier.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## Einrichten von Benutzern

Die häufigste Möglichkeit zum Einrichten eines neuen Benutzers liegt während der HoloLens-out-of-Box-Benutzeroberfläche (OOBE). Während des Setups fordert HoloLens einen Benutzer auf, sich mit dem Konto anzumeldet, das er auf dem Gerät verwenden möchte. Bei diesem Konto kann es sich um ein Consumer Microsoft-Konto oder ein Unternehmenskonto handeln, das in Azure konfiguriert wurde. Weitere Informationen finden Sie unter Einrichten Ihres [HoloLens (1st Gen)](hololens1-start.md) oder [HoloLens 2](hololens2-start.md).

Wie bei Windows auf anderen Geräten wird bei der Anmeldung während des Setups ein Benutzerprofil auf dem Gerät erstellt. Das Benutzerprofil speichert apps und Daten. Das gleiche Konto bietet auch einmaliges Anmelden für apps wie Edge oder Skype mithilfe der Windows-Konto-Manager-APIs.  

Wenn Sie ein Unternehmens-oder organisationskonto für die Anmeldung bei HoloLens verwenden, registriert HoloLens die IT-Infrastruktur des Unternehmens. Diese Registrierung ermöglicht es Ihrem IT-Administrator, das Mobile Device Management (MDM) so zu konfigurieren, dass Gruppenrichtlinien an Ihre HoloLens gesendet werden.

Standardmäßig müssen Sie, wie bei anderen Windows 10-Geräten, sich erneut anmelden, wenn HoloLens neu gestartet oder aus dem Standbymodus fortgesetzt wird. Sie können die Einstellungs-APP verwenden, um dieses Verhalten zu ändern, oder das Verhalten kann durch Gruppenrichtlinien gesteuert werden.

### Verknüpfte Konten

Wie in der Desktop Version von Windows können Sie zusätzliche Webkonto Anmeldeinformationen mit Ihrem HoloLens-Konto verknüpfen. Durch diese Verknüpfung ist es einfacher, auf Ressourcen über oder innerhalb von apps (wie dem Store) zuzugreifen oder den Zugriff auf persönliche und geschäftliche Ressourcen zu kombinieren. Nachdem Sie ein Konto mit dem Gerät verbunden haben, können Sie die Berechtigung zum Verwenden des Geräts für apps erteilen, damit Sie sich nicht bei jeder App einzeln anmelden müssen.

Durch das Verknüpfen von Konten werden die auf dem Gerät erstellten Benutzerdaten wie Bilder oder Downloads nicht getrennt.  

### Einrichten der Multi-User-Unterstützung (nur Azure AD)

HoloLens unterstützt mehrere Benutzer aus dem gleichen Azure AD-Mandanten. Um dieses Feature verwenden zu können, müssen Sie ein Konto verwenden, das zu Ihrer Organisation gehört, um das Gerät einzurichten. Anschließend können sich andere Benutzer desselben Mandanten über den Anmeldebildschirm oder durch Tippen auf die Kachel "Benutzer" im Start Bereich anmelden. Es kann jeweils nur ein Benutzer angemeldet werden. Wenn sich ein Benutzer anmeldet, zeichnet HoloLens den vorherigen Benutzer ab. Der erste Benutzer auf dem Gerät gilt als Gerätebesitzer, außer bei Azure AD Join finden [Sie weitere Informationen zu Geräte Besitzern](security-adminless-os.md#device-owner).

Alle Benutzer können die auf dem Gerät installierten Apps verwenden. Jeder Benutzer verfügt jedoch über eigene APP-Daten und-Einstellungen. Wenn Sie eine APP vom Gerät entfernen, wird Sie für alle Benutzer entfernt.  

Bei Geräten, die mit Azure Ad-Konten eingerichtet sind, ist es nicht möglich, sich mit einem Microsoft-Konto bei dem Gerät anzumelden. Alle nachfolgenden Konten müssen Azure Ad-Konten vom gleichen Mandanten wie das Gerät sein. Sie können [sich mit einem Microsoft-Konto weiterhin für Apps anmelden](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) , die es unterstützen (wie etwa den Microsoft Store). Wenn Sie von Azure Ad-Konten zu Microsoft-Konten wechseln möchten, um sich beim Gerät anzumelden, müssen Sie [das Gerät erneut Aufblitzen](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> **HoloLens (1st Generation)** unterstützt mehrere Azure AD-Benutzer im [Windows 10 April 2018-Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) als Teil von [Windows holographisch für Unternehmen](hololens-upgrade-enterprise.md).

## Entfernen von Benutzern

Sie können einen Benutzer aus dem Gerät entfernen, indem Sie zu **Einstellungen**  >  -**Konten**  >  **andere Personen**wechseln. Durch diese Aktion wird auch Speicherplatz frei, indem alle App-Daten dieses Benutzers vom Gerät entfernt werden.  

## Verwenden von einmaligem Anmelden in einer APP

Als App-Entwickler können Sie verknüpfte Identitäten auf HoloLens mithilfe der [Windows-Konto-Manager-APIs](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)nutzen, genau wie auf anderen Windows-Geräten. Einige Codebeispiele für diese APIs finden Sie unter GitHub: [Web Account Management-Beispiel](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Eventuell auftretende Konto Unterbrechungen, beispielsweise das Anfordern einer Benutzer Zustimmung für Kontoinformationen, die zweistufige Authentifizierung usw., müssen behandelt werden, wenn die APP ein Authentifizierungstoken anfordert.

Wenn für Ihre APP ein bestimmter Kontotyp erforderlich ist, der zuvor nicht verknüpft wurde, kann Ihre APP das System bitten, den Benutzer aufzufordern, ein Konto hinzuzufügen. Diese Anforderung löst den Bereich Kontoeinstellungen aus, um als modales untergeordnetes Element Ihrer APP zu starten. Bei 2D-apps wird dieses Fenster direkt über der Mitte Ihrer APP gerendert. Bei Unity-apps führt diese Anforderung den Benutzer kurz aus ihrer holographischen APP, um das untergeordnete Fenster zu rendern. Informationen zum Anpassen der Befehle und Aktionen in diesem Bereich finden Sie unter [WebAccountCommand-Klasse](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## Enterprise-und andere Authentifizierung

Wenn Ihre APP andere Authentifizierungsarten wie NTLM, Basic oder Kerberos verwendet, können Sie die Anmeldeinformationen des Benutzers mithilfe der [Windows-Anmelde Informationsschnittstelle](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) sammeln, verarbeiten und speichern. Die Benutzererfahrung beim Sammeln dieser Anmeldeinformationen ist mit anderen cloudbasierten Konto Unterbrechungen sehr ähnlich und wird als untergeordnete APP oben auf Ihrer 2D-App angezeigt, oder es wird eine Einheits-App kurz angehalten, um die Benutzeroberfläche anzuzeigen.

## Veraltete APIs

Eine Möglichkeit, wie sich die Entwicklung für HoloLens von der Entwicklung für Desktop unterscheidet, besteht darin, dass die [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) -API nicht vollständig unterstützt wird. Obwohl die API ein Token zurückgibt, wenn sich das primäre Konto in gutem Status befindet, werden Unterbrechungen, wie Sie in diesem Artikel beschrieben sind, keine Benutzeroberfläche für den Benutzer angezeigt, und das Konto konnte nicht ordnungsgemäß authentifiziert werden.

## Häufig gestellte Fragen

### Wird Windows Hello for Business auf HoloLens (1st Gen) unterstützt?

Windows Hello for Business (das die Verwendung einer PIN zur Anmeldung unterstützt) wird für HoloLens (1st Gen) unterstützt. So lassen Sie Windows Hello for Business-Pin-Anmeldung auf HoloLens zu:

1. Das HoloLens-Gerät muss [vom MDM verwaltet](hololens-enroll-mdm.md)werden.
1. Sie müssen Windows Hello for Business für das Gerät aktivieren. ([Weitere Informationen finden Sie unter Anweisungen für Microsoft InTune.](https://docs.microsoft.com/intune/windows-hello))
1. Auf HoloLens kann der Benutzer dann die **Einstellungen**  >  für die**Anmeldeoptionen**  >  **Hinzufügen** , um eine PIN einzurichten.

> [!NOTE]
> Benutzer, die sich mit einem Microsoft-Konto anmelden, können auch eine PIN in den **Einstellungen**der  >  **Anmeldeoptionen**für das  >  **Hinzufügen von Pins**einrichten. Diese PIN ist [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)und nicht [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)zugeordnet.

### Wie wird die Iris biometrische Authentifizierung auf HoloLens 2 implementiert?

HoloLens 2 unterstützt die Iris-Authentifizierung. IRIS basiert auf der Windows Hello-Technologie und wird für die Verwendung durch Azure Active Directory-und Microsoft-Konten unterstützt. IRIS ist auf die gleiche Weise implementiert wie andere Windows Hello-Technologien und erreicht die Biometrie-Sicherheit weit von 1/100K.

Weitere Informationen zu biometrischen Anforderungen und Spezifikationen für Windows Hello finden Sie [hier](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements). Weitere Informationen zu [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) und [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### Wie wirkt sich der Kontotyp auf das Anmeldeverhalten aus?

Wenn Sie Richtlinien für die Sign-In-Verhalten verwenden, werden die Richtlinie immer berücksichtigt. Wenn keine Richtlinie für die Anmeldung angewendet wird, handelt es sich hierbei um das Standardverhalten für die einzelnen Kontotypen:

- **Azure AD**: fordert standardmäßig eine Authentifizierung an und kann durch **Einstellungen** konfiguriert werden, um keine Authentifizierung mehr zu fordern.
- **Microsoft-Konto**: das Sperrverhalten unterscheidet sich von der automatischen Sperrung, die Anmeldeauthentifizierung ist jedoch beim Neustart weiterhin erforderlich.
- **Lokales Konto**: fragt immer nach Authentifizierung in Form eines Kennworts, das nicht in den **Einstellungen** konfiguriert werden kann.

> [!NOTE]
> Inaktive Timer werden derzeit nicht unterstützt, was bedeutet, dass die **AllowIdleReturnWithoutPassword** -Richtlinie nur eingehaltenwird, wenn das Gerät in den Standbymodus wechselt.

## Zusätzliche Ressourcen

Lesen Sie weitere Informationen zum Schutz von Benutzeridentitäten und zur Authentifizierung in [der Windows 10-Dokumentation zur Sicherheit und Identität](https://docs.microsoft.com/windows/security/identity-protection/).

Weitere Informationen zum Einrichten einer hybriden Identitätsinfrastruktur finden Sie in der [Dokumentation zur Azure-Hybrid Identität](https://docs.microsoft.com/azure/active-directory/hybrid/).
