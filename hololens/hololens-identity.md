---
title: Verwalten der Benutzeridentität und -anmeldung für HoloLens
description: Erfahren Sie, wie Sie Die Benutzeridentität, Unterstützung mehrerer Benutzer, Sicherheit, Unternehmensauthentifizierung und Anmeldung für HoloLens Geräte verwalten.
keywords: HoloLens, Benutzer, Konto, AAD, Azure AD, adfs, Microsoft-Konto, msa, Anmeldeinformationen, Referenz
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: qianw211
ms.author: v-qianwen
ms.date: 8/13/2021
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c2fd7c8ee82fbf70b9eaa2b5eee1d73e1235d8b5
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032596"
---
# <a name="manage-user-identity-and-login-for-hololens"></a>Verwalten der Benutzeridentität und -anmeldung für HoloLens

> [!NOTE]
> Dieser Artikel ist eine technische Referenz für IT-Spezialisten und Technologieinteressierte. Wenn Sie nach HoloLens Anweisungen zum Einrichten suchen, lesen Sie "[Einrichten Ihrer HoloLens (1. Generation)](hololens1-start.md)" oder "[Einrichten Ihrer HoloLens 2](hololens2-start.md)".

## <a name="lets-talk-about-setting-up-user-identity-for-hololens-2"></a>Im Folgenden wird das Einrichten der Benutzeridentität für HoloLens 2

Wie andere Windows Geräte wird HoloLens immer unter einem Benutzerkontext betrieben. Es gibt immer eine Benutzeridentität. HoloLens behandelt Identitäten fast genauso wie ein Windows 10 Gerät. Wenn Sie sich während des Setups anmelden, wird ein Benutzerprofil für HoloLens erstellt, in dem Apps und Daten gespeichert werden. Dasselbe Konto bietet auch einmaliges Anmelden für Apps wie Edge oder Dynamics 365 Remote Assist mithilfe der Windows Account Manager-APIs. 

HoloLens unterstützt verschiedene Arten von Benutzeridentitäten. Sie können einen dieser drei Kontotypen auswählen. Es wird jedoch dringend empfohlen, Azure AD zu verwenden, da dies für die Verwaltung von Geräten am besten geeignet ist. Nur Azure AD Konten unterstützen mehrere Benutzer. 

| Identitätstyp | Konten pro Gerät | Authentifizierungsoptionen |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Azure-Webanmeldeinformationsanbieter</li><li>Azure Authenticator-App</li><li>Biometrische (Iris) &ndash; HoloLens 2 nur<sup>2</sup> </li><li>FIDO2-Sicherheitsschlüssel</li><li>PIN &ndash; optional für HoloLens (1. Generation), erforderlich für HoloLens 2</li><li>Kennwort</li></ul> |
| [Microsoft-Konto (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Nur biometrische &ndash; (Iris)-HoloLens 2</li><li>PIN &ndash; optional für HoloLens (1. Generation), erforderlich für HoloLens 2</li><li>Kennwort</li></ul> |
| [Lokales Konto](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | 1 | Kennwort |

Mit der Cloud verbundene Konten (Azure AD und MSA) bieten mehr Features, da sie Azure-Dienste verwenden können.  
> [!IMPORTANT]
> 1 – Azure AD Premium ist nicht erforderlich, um sich beim Gerät anzumelden. Sie ist jedoch für andere Features einer cloudbasierten Bereitstellung mit geringem Touchaufwand erforderlich, z. B. automatische Registrierung und Autopilot.

> [!NOTE]
> 2 – Während ein HoloLens 2 Gerät bis zu 64 Azure AD Konten unterstützen kann, können sich nur 31 dieser Konten bei Iris Authentication registrieren. Dies ist an anderen [biometrischen Authentifizierungsoptionen für Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)ausgerichtet.

> [!IMPORTANT]
> 3 : Ein lokales Konto kann nur [über ein Bereitstellungspaket während der OOBE](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)auf einem Gerät eingerichtet werden. Es kann später in der Einstellungs-App nicht hinzugefügt werden. Wenn Sie ein lokales Konto auf einem bereits eingerichteten Gerät verwenden möchten, müssen Sie [das Gerät umstellen oder zurücksetzen.](hololens-recovery.md)

## <a name="setting-up-users"></a>Einrichten von Benutzern

Es gibt zwei Möglichkeiten, einen neuen Benutzer auf der HoloLens einzurichten. Die gängigste Methode ist während der HoloLens out-of-box experience (OOBE). Wenn sie Azure Active Directory verwenden, können sich andere Benutzer nach oobe mit ihren Azure AD Anmeldeinformationen [anmelden.](#setting-up-multi-user-support-azure-ad-only) HoloLens Geräte, die anfänglich mit einem MSA- oder lokalen Konto während der OoBE eingerichtet wurden, unterstützen nicht mehrere Benutzer. Weitere Informationen finden Sie unter Einrichten Ihrer [HoloLens (1. Generation)](hololens1-start.md) oder [HoloLens 2](hololens2-start.md).

Wenn Sie sich mit einem Unternehmens- oder Organisationskonto bei HoloLens anmelden, wird HoloLens in der IT-Infrastruktur der Organisation registriert. Mit dieser Registrierung kann Ihr IT-Administrator Mobile Geräteverwaltung (MDM) so konfigurieren, dass Gruppenrichtlinien an Ihre HoloLens gesendet werden.

Wie Windows auf anderen Geräten erstellt die Anmeldung während des Setups ein Benutzerprofil auf dem Gerät. Im Benutzerprofil werden Apps und Daten gespeichert. Dasselbe Konto bietet auch einmaliges Anmelden für Apps wie Edge oder die Microsoft Store mithilfe der Windows Account Manager-APIs.

Standardmäßig müssen Sie sich wie bei anderen Windows 10 Geräten erneut anmelden, wenn HoloLens neu gestartet oder aus dem Standbymodus fortgesetzt wird. Sie können die Einstellungen-App verwenden, um dieses Verhalten zu ändern, oder das Verhalten kann durch Gruppenrichtlinien gesteuert werden.

### <a name="linked-accounts"></a>Verknüpfte Konten

Wie in der Desktopversion von Windows können Sie andere Webkontoanmeldeinformationen mit Ihrem HoloLens-Konto verknüpfen. Eine solche Verknüpfung erleichtert den Zugriff auf Ressourcen in oder innerhalb von Apps (z. B. die Store) oder das Kombinieren des Zugriffs auf persönliche und Arbeitsressourcen. Nachdem Sie ein Konto mit dem Gerät verbunden haben, können Sie Apps die Berechtigung zum Verwenden des Geräts erteilen, damit Sie sich nicht einzeln bei jeder App anmelden müssen.

Durch das Verknüpfen von Konten werden die auf dem Gerät erstellten Benutzerdaten nicht getrennt, z. B. Bilder oder Downloads.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Einrichten der Unterstützung mehrerer Benutzer (nur Azure AD)

HoloLens unterstützt mehrere Benutzer aus demselben Azure AD Mandanten. Um dieses Feature verwenden zu können, müssen Sie ein Konto verwenden, das zu Ihrer Organisation gehört, um das Gerät einzurichten. Anschließend können sich andere Benutzer desselben Mandanten über den Anmeldebildschirm oder durch Tippen auf die Benutzerkachel im Startbereich beim Gerät anmelden. Es kann jeweils nur ein Benutzer angemeldet werden. Wenn sich ein Benutzer anmeldet, meldet HoloLens den vorherigen Benutzer ab. 

>[!IMPORTANT]
> Der erste Benutzer auf dem Gerät gilt als Gerätebesitzer. Im Fall von Azure AD Join [erfahren Sie mehr über Gerätebesitzer.](security-adminless-os.md#device-owner)

Alle Benutzer können die auf dem Gerät installierten Apps verwenden. Jeder Benutzer verfügt jedoch über eigene App-Daten und -Einstellungen. Wenn Sie eine App vom Gerät entfernen, wird sie für alle Benutzer entfernt.  

Geräte, die mit Azure AD-Konten eingerichtet wurden, dürfen sich nicht mit einem Microsoft-Konto beim Gerät anmelden. Alle nachfolgenden verwendeten Konten müssen Azure AD Konten desselben Mandanten wie das Gerät sein. Sie können sich weiterhin [mit einem Microsoft-Konto bei Apps anmelden,](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) die es unterstützen (z. B. die Microsoft Store). Um von der Verwendung von Azure AD-Konten zu Microsoft-Konten für die Anmeldung beim Gerät zu wechseln, müssen Sie [den Schrägstrich des Geräts umstellen.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens (1. Generation)** begann im Windows 10 April [2018 Update](/windows/mixed-reality/release-notes-april-2018) im Rahmen Windows Holographic for Business mit der Unterstützung mehrerer [Azure AD](hololens-upgrade-enterprise.md)Benutzer.

### <a name="multiple-users-are-listed-on-sign-in-screen"></a>Mehrere Benutzer werden auf dem Anmeldebildschirm aufgeführt.

Zuvor wurden auf dem Anmeldebildschirm nur der zuletzt angemeldete Benutzer und ein Einstiegspunkt "Anderer Benutzer" angezeigt. Wir haben Kundenfeedback erhalten, dass es nicht ausreicht, wenn sich mehrere Benutzer am Gerät angemeldet haben. Sie mussten weiterhin ihren Benutzernamen usw. erneut eingeben.

In [Windows Holographic, Version 21H1 eingeführt,](hololens-release-notes.md#windows-holographic-version-21h1)zeigt der Anmeldebildschirm mehrere Benutzer mit an, die sich zuvor beim Gerät angemeldet haben, wenn Sie Auf der rechten Seite des PIN-Eingabefelds andere **Benutzer** auswählen. Dadurch können Benutzer ihr Benutzerprofil auswählen und sich dann mit ihren Windows Hello Anmeldeinformationen anmelden. Ein neuer Benutzer kann dem Gerät auch über diese Seite für **andere Benutzer** über die Schaltfläche **Konto hinzufügen** hinzugefügt werden.

Im Menü **Andere Benutzer** zeigt die Schaltfläche Andere **Benutzer** den letzten Benutzer an, der sich am Gerät angemeldet hat. Wählen Sie diese Schaltfläche aus, um zum Anmeldebildschirm für diesen Benutzer zurückzukehren.

![Standardeinstellung des Anmeldebildschirms.](./images/multiusers1.jpg)

<br>

![Anmeldebildschirm für andere Benutzer.](./images/multiusers2.jpg)

## <a name="removing-users"></a>Entfernen von Benutzern

Sie können einen Benutzer vom Gerät entfernen, indem Sie zu **Einstellungen**  >  **Konten**  >  **Andere Personen** gelangen. Diese Aktion gibt auch Speicherplatz frei, indem alle App-Daten dieses Benutzers vom Gerät entfernt werden.  

## <a name="using-single-sign-on-within-an-app"></a>Verwenden des einmaligen Anmeldens in einer App

Als App-Entwickler können Sie verknüpfte Identitäten auf HoloLens nutzen, indem Sie die [Windows Account Manager-APIs](/uwp/api/Windows.Security.Authentication.Web.Core)wie auf anderen Windows Geräten verwenden. Einige Codebeispiele für diese APIs finden Sie unter GitHub: Beispiel für [die Webkontoverwaltung.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

Alle möglichen Kontounterbrechungen, z. B. das Anfordern der Benutzereinwilligung für Kontoinformationen, die zweistufige Authentifizierung usw., müssen behandelt werden, wenn die App ein Authentifizierungstoken anfordert.

Wenn Ihre App einen bestimmten Kontotyp erfordert, der zuvor nicht verknüpft wurde, kann Ihre App das System auffordern, den Benutzer aufzufordern, einen hinzuzufügen. Diese Anforderung löst den Kontoeinstellungsbereich aus, der als modales untergeordnetes Element Ihrer App gestartet wird. Bei 2D-Apps wird dieses Fenster direkt über die Mitte Ihrer App gerendert. Bei Unity-Apps nimmt diese Anforderung den Benutzer kurz aus Ihrer holografischen App heraus, um das untergeordnete Fenster zu rendern. Informationen zum Anpassen der Befehle und Aktionen in diesem Bereich finden Sie unter [WebAccountCommand-Klasse.](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)

## <a name="enterprise-and-other-authentication"></a>Enterprise und andere Authentifizierung

Wenn Ihre App andere Authentifizierungstypen wie NTLM, Basic oder Kerberos verwendet, können Sie [Windows Anmeldeinformations-Benutzeroberfläche](/uwp/api/Windows.Security.Credentials.UI) verwenden, um die Anmeldeinformationen des Benutzers zu erfassen, zu verarbeiten und zu speichern. Die Benutzeroberfläche zum Sammeln dieser Anmeldeinformationen ähnelt anderen cloudgesteuerten Kontounterbrechungen und wird als untergeordnete App neben Ihrer 2D-App angezeigt oder hält eine Unity-App kurz an, um die Benutzeroberfläche anzuzeigen.

## <a name="deprecated-apis"></a>Nicht mehr unterstützte APIs

Eine Möglichkeit, wie sich die Entwicklung für HoloLens desktop unterscheidet, ist, dass die [OnlineIDAuthenticator-API](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) nicht vollständig unterstützt wird. Obwohl die API ein Token zurückgibt, wenn sich das primäre Konto in einem guten Zustand befindet, zeigen Unterbrechungen wie die in diesem Artikel beschriebenen keine Benutzeroberfläche für den Benutzer an und können das Konto nicht ordnungsgemäß authentifizieren.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Wird Windows Hello for Business auf HoloLens (1. Generation) unterstützt?

Windows Hello für Unternehmen (die die Verwendung einer PIN für die Anmeldung unterstützt) wird für HoloLens (1. Generation) unterstützt. So ermöglichen Windows Hello die Anmeldung mit der PIN für Unternehmen HoloLens:

1. Das HoloLens-Gerät muss von [MDM verwaltet werden.](hololens-enroll-mdm.md)
1. Sie müssen Windows Hello für Unternehmen für das Gerät aktivieren. ([Siehe Anweisungen für Microsoft Intune.](/intune/windows-hello))
1. Auf HoloLens kann der Benutzer dann mithilfe Einstellungen Anmeldeoptionen PIN hinzufügen  >    >   eine PIN einrichten.

> [!NOTE]
> Benutzer, die sich mithilfe eines Microsoft-Konto anmelden, können auch eine PIN **in** Einstellungen  >  **Anmeldeoptionen** PIN hinzufügen  >  **einrichten.** Diese PIN ist [mit](https://support.microsoft.com/help/17215/windows-10-what-is-hello)Windows Hello verknüpft, anstatt Windows Hello [für Unternehmen.](/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Wie wird die biometrische Iris-Authentifizierung auf HoloLens 2?

HoloLens 2 unterstützt die Iris-Authentifizierung. Iris basiert auf Windows Hello-Technologie und wird für die Verwendung durch Azure Active Directory microsoft-Konten unterstützt. Iris wird auf die gleiche Weise wie andere Windows Hello-Technologien implementiert und erreicht die biometrische Sicherheit FAR von [1/100.000](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#has-microsoft-set-any-device-requirements-for-windows-hello).

Weitere Informationen [finden Sie in den biometrischen Anforderungen Windows Hello](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) Spezifikationen. Erfahren Sie mehr [über Windows Hello](/windows-hardware/design/device-experiences/windows-hello) und Windows Hello [for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### <a name="where-is-iris-biometric-information-stored"></a>Wo werden biometrische Iris-Informationen gespeichert?

Biometrische Iris-Informationen werden lokal auf jedem HoloLens pro Windows Hello [gespeichert.](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#where-is-windows-hello-data-stored) Sie wird nicht freigegeben und durch zwei Verschlüsselungsebenen geschützt. Es ist nicht für andere Benutzer zugänglich, auch nicht für Administratoren, da es kein Administratorkonto für eine HoloLens.

### <a name="do-i-have-to-use-iris-authentication"></a>Muss ich die Iris-Authentifizierung verwenden?
Nein, Sie können diesen Schritt während des Setups überspringen. 

![Richten Sie Iris ein.](./images/setup-iris.png)

HoloLens 2 bietet viele verschiedene Optionen für die Authentifizierung, einschließlich FIDO2-Sicherheitsschlüsseln.

### <a name="can-iris-information-be-removed-from-the-hololens"></a>Können Iris-Informationen aus dem HoloLens?
Ja, Sie können sie manuell in der Einstellungen.


### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Wie wirkt sich der Kontotyp auf das Anmeldeverhalten aus?

Wenn Sie Richtlinien für die Anmeldung anwenden, wird die Richtlinie immer beachtet. Wenn keine Richtlinie für die Anmeldung angewendet wird, sind dies die Standardverhalten für jeden Kontotyp:

- **Azure AD**: fordert standardmäßig zur Authentifizierung auf  und kann von Einstellungen nicht mehr nach Authentifizierung gefragt werden.
- **Microsoft-Konto:** Das Sperrverhalten ist anders, sodass das automatische Entsperren ermöglicht wird, aber die Anmeldeauthentifizierung ist beim Neustart weiterhin erforderlich.
- **Lokales Konto:** Fordert immer zur Authentifizierung in Form eines Kennworts auf, das **in** der Einstellungen

> [!NOTE]
> Inaktivitäts-Timer werden derzeit nicht unterstützt. Dies bedeutet, dass die **Richtlinie AllowIdleReturnWithoutPassword** nur berücksichtigt wird, wenn das Gerät in StandBy übergeht.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

Weitere Informationen zum Schutz der Benutzeridentität und -Authentifizierung finden Sie in der Windows 10 security and identity documentation (Sicherheits- [und Identitätsdokumentation).](/windows/security/identity-protection/)

Weitere Informationen zum Einrichten der Hybrididentitätsinfrastruktur finden Sie in der [Dokumentation zur Azure-Hybrididentität.](/azure/active-directory/hybrid/)