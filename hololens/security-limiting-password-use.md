---
title: Begrenzen der Verwendung von Kennwörtern
description: Begrenzen der Verwendung von Kennwörtern für HoloLens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: Sicherheit, Hololens, begrenzen der Verwendung von Kennwörtern, Kennwort, Hololens-Kennwort, Anmeldung, anmelden, Windows Hello, Hello, Windows-Konto-Manager, FIDO2 anmelden, Fido 2, WEBAUTHN, lokales Konto, Hololens-Sicherheit
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 074fffc8350dd6deb876a19320397674bcac3e46
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639300"
---
# <a name="limiting-password-use"></a>Begrenzen der Verwendung von Kennwörtern

Auf den meisten Computersystemen dienen Benutzeranmeldeinformationen als Grundlage für die Sicherheit, wodurch die Systeme von wiederverwendbaren, vom Benutzer erstellten Kennwörtern abhängig sind. Dies hat dazu geführt, dass Kennwörter auch die häufigste Ursache von Kontokompromittierungen und Datenschutzverletzungen darstellen. Kennwörter können beispielsweise während der Übertragung abgefangen oder von einem Server gestohlen (durch Phishing- oder Passwort-Spraying-Angriffe) und kompromittiert werden, um Zugriff auf ein Benutzerkonto zu erhalten.

Für mehr Sicherheit und besseren Kontoschutz bietet HoloLens 2 die Möglichkeit, starke, hardwaregeschützte „kennwortfreie“ Anmeldeinformationen (einschließlich Windows Hello) für die Anmeldung bei Geräten zu aktivieren, die einen nahtlosen Zugang zur Microsoft-Cloud ermöglichen.

## <a name="signing-in-from-another-device"></a>Anmelden über ein anderes Gerät

HoloLens 2 bietet Anmeldeoptionen für Remotegeräte für Azure Active Directory-Arbeitskonten während des erstmaligen Geräte-Setups und der Benutzeranmeldung, um das Erfordernis der Eingabe komplexer Kennwörter zu reduzieren und die Notwendigkeit von Kennwörtern als Anmeldeinformationen zu minimieren. Benutzer und Organisationen, die Smartcards zur Authentifizierung verwenden, haben Schwierigkeiten beim Verwenden dieser Anmeldeinformationen auf Geräten wie HoloLens 2, und häufig entwickeln Organisationen komplexe Systeme und kostspielige Prozesse, um dieses Problem zu umgehen. Zur Lösung dieses Problems bietet Azure AD zwei Optionen für die kennwortlose Anmeldung bei HoloLens 2.

Die erste Authentifizierungsmethode stützt sich auf die neuen Funktionen in der Microsoft Authenticator-App zur Bereitstellung schlüsselbasierter Authentifizierung, durch die Benutzeranmeldeinformationen an ein Gerät gebunden sind. Nachdem der Administrator die Aktivierung für einen Mandanten durchgeführt hat, wird den Benutzern während des Setups eines HoloLens-Geräts eine Meldung angezeigt, in der sie aufgefordert werden, auf eine Zahl in ihrer App zu tippen. Sie müssen dann eine Zahl angeben, die mit jener in ihrer Authenticator-App übereinstimmt, „Genehmigen“ auswählen, ihre PIN oder eine biometrische Anmeldeinformation angeben und die Authentifizierung abschließen, damit das HoloLens-Setup fortgesetzt werden kann. Dies wird unter [passwordless sign-in](/azure/active-directory/authentication/howto-authentication-passwordless-phone) (Anmeldung ohne Kennwort) ausführlicher beschrieben.

Bei der zweiten Methode handelt es sich um einen benutzerfreundlichen Gerätecodecode-Vorgang, für den keine zusätzliche Infrastruktur erforderlich ist.  Dieser Remote-Anmeldevorgang basiert auf einem anderen vertrauenswürdigen Gerät, das den bevorzugten Authentifizierungsmechanismus der Organisation unterstützt. Nach Abschluss des Vorgangs werden Token zurück an das HoloLens-Gerät ausgegeben, um die Anmeldung oder das Gerätesetup abzuschließen. Nachfolgend die Schritte bei diesem Vorgang:

  1. Beim anfänglichen Gerätesetup- oder Anmeldevorgang wird Benutzern auf der Windows-Begrüßungsseite ein Link „Von einem anderen Gerät anmelden“ angezeigt, auf den sie dann tippen. Damit wird eine Remote-Anmeldesitzung gestartet.
  1. Dem Benutzer wird dann eine Abrufseite angezeigt, die einen kurzen URI ([https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)) enthält, der auf den Geräteauthentifizierungsendpunkt des Azure AD Secure Token Service (STS) verweist. Außerdem wird dem Benutzer ein einmaliger Code angezeigt, der in der Cloud sicher generiert wird und maximal 15 Minuten lang gültig ist. Neben der Codegenerierung erstellt Azure AD beim Initiieren der Remote-Anmeldeanforderung im vorherigen Schritt auch eine verschlüsselte Sitzung, und der URI und der Code werden zusammen für die Genehmigung der Remote-Anmeldeanforderung verwendet.
  1. Der Benutzer navigiert dann von dem anderen Gerät zum URI und wird aufgefordert, den Code einzugeben, der auf seinem HoloLens 2-Gerät angezeigt wird.
  1. Nachdem der Benutzer den Code eingegeben hat, wird von Azure AD STS eine Seite angezeigt, auf der das HoloLens 2-Gerät des Benutzers anzeigt wird, von dem die Remote-Anmeldeanforderung ausgelöst und die Codegenerierung angefordert wurde. Der Benutzer wird dann zur Bestätigung aufgefordert, um Phishing-Angriffe zu verhindern.
  1. Wenn der Benutzer die Anmeldung bei der angezeigten „Anwendung“ fortsetzen möchte, wird er von Azure AD STS zur Eingabe seiner Anmeldeinformationen aufgefordert. Bei erfolgreicher Authentifizierung aktualisiert Azure AD STS die Remotesitzung im Cache als „genehmigt“ und stellt einen Autorisierungscode bereit.
  1. Schließlich empfängt die Abfrageseite auf dem HoloLens 2-Gerät des Benutzers die Antwort „autorisiert“ von Azure AD und geht zur Validierung des Benutzercodes sowie des zugehörigen gespeicherten Autorisierungscodes über. Anschließend werden wie angefordert OAuth-Token generiert, um das Setup des Geräts abzuschließen. Das erstellte Authentifizierungstoken ist eine Stunde lang gültig, das Aktualisierungstoken hingegen 90 Tage lang.

Die in diesem Ablauf verwendeten Algorithmen zur Codegenerierung und -verschlüsselung sind FIPS-konform. HoloLens 2-Geräte verwenden das TPM zum Sichern von Geräteschlüsseln und zum Verschlüsseln von Token, die nach der Benutzerauthentifizierung mithilfe von hardwaregeschützten Schlüsseln generiert werden. Weitere Informationen zur Tokensicherheit auf HoloLens 2 stehen unter [Was ist ein primäres Aktualisierungstoken (PRT)?](/azure/active-directory/devices/concept-primary-refresh-token) zur Verfügung.

## <a name="device-sign-in-with-windows-hello"></a>Geräteanmeldung mit Windows Hello

[Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification) bietet kennwortfreie Optionen, die direkt in das Betriebssystem integriert sind, sodass sich die Benutzer über Iris oder PIN beim Gerät anmelden können. Eine PIN ist immer als Anmeldeinformationen verfügbar und für das Gerätesetup erforderlich, während Iris optional ist und übersprungen werden kann. Benutzer können sich mit ihrem persönlichen Microsoft-Konto oder [Azure Active Directory Arbeitskonto *bei HoloLens-Geräten anmelden, ohne ein* Kennwort einzugeben](/azure/active-directory/authentication/concept-authentication-passwordless). Optionen wie diese bieten Benutzern schnellen und sicheren Zugriff auf ihre vollständige Windows-Umgebung, Apps, Daten, Websites und Dienste. Näheres zur Strategie von Microsoft in Bezug auf kennwortlose Lösungen finden Sie hier.

Wenn eine Windows Hello-Anmeldeinformation erstellt wird, stellt sie ein Vertrauensverhältnis mit einem Identitätsanbieter her und erstellt ein asymmetrisches Schlüsselpaar für die Authentifizierung. Eine Windows Hello-Geste (wie z. B. Iris oder PIN) liefert Entropie zum Entschlüsseln eines privaten Schlüssels, der durch den TPM-Chip (Trusted Platform Module) des Geräts gesichert wird. Dieser private Schlüssel wird dann verwendet, um die an einen authentifizierenden Server gesendeten Anforderungen zu signieren, und nach erfolgreicher Authentifizierung wird dem Benutzer der Zugriff auf seine E-Mails, Bilder und andere Kontoeinstellungen gewährt.

Weitere Informationen können Sie der folgenden Infografik entnehmen:

  ![Windows Hello-Anmeldung](images/security-hello-sign-in.png)
  
Beachten Sie in der vorstehenden Abbildung, dass „nonce“ für „nonce-Zahl“ steht und eine zufällig oder halbzufällig generierte Zahl ist. Sobald die biometrischen oder PIN-Anmeldeinformationen für Windows Hello eingerichtet sind, verlassen sie nie das Gerät, auf dem sie bereitgestellt wurden. Auch wenn die Windows Hello-PIN des Benutzers gestohlen wird, etwa durch einen Phishingangriff, ist sie [ohne das physische Gerät des Benutzers unbrauchbar](/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password).

Für zusätzliche Sicherheit sind Windows Hello-Anmeldeinformationen durch das Trusted Platform Module (TPM) geschützt. Dadurch werden sie manipulationssicher. Ergänzend stehen Anti-Hammering-Schutz gegen mehrfache falsche Einträge und Schutz vor Schadsoftware zur Verfügung, um eine Gefährdung zu verhindern. Weitere Informationen zu SSO (Single Sign-On) finden Sie in dieser [Übersicht der SSO-Methoden](/azure/active-directory/manage-apps/what-is-single-sign-on).

Die Iris-Authentifizierung greift auf die PIN zurück. Um eine neue PIN (ein starker Authentifikator) auf dem Gerät einzurichten, muss der Benutzer erst kürzlich eine [mehrstufige Authentifizierung (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks) durchgeführt haben, um den Vorgang ausführen zu können.

## <a name="single-sign-on-with-web-account-manager"></a>Einmaliges Anmelden mit Web Account Manager

Einmaliges Anmelden (Single Sign-on, SSO) ermöglicht es kennwortfreien Benutzern, sich beim Gerät mit ihrem persönlichen Konto bzw. ihrem Geschäfts-, Schul- oder Unikonto anzumelden. Der Benutzer wird durch SSO automatisch zur Nutzung aller integrierten Apps und Dienste über die [Web Account Manager-APIs](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true) autorisiert.

Nachdem eine Identität über eine Anwendung hinzugefügt wurde, kann sie, bei Einwilligung des Benutzers, über die systembasierte Integration für alle Apps und Dienste bereitgestellt werden. Dadurch wird die Mühe der Anmeldung bei Apps erheblich reduziert und den Benutzern die Erfahrung einer nahtlosen Identität geboten.

Weitere Informationen zum Implementieren von Web Account Manager-APIs finden Sie unter [Implementing Web Account Manager APIs](/windows/uwp/security/web-account-manager) (Implementieren von Web Account Manager-APIs).

  ![Sicherheits-API](images/security-api-img.png)
  
Bei App-Suites mit speziellen Authentifizierungsanforderungen ist das WAM-Framework (Web Account Manager) auf benutzerdefinierte Identitätsanbieter erweiterbar. Benutzer können den benutzerdefinierten Identitätsanbieter, der als UWP-App (Universelle Windows Platform) gepackt ist, aus dem Microsoft Store herunterladen, um SSO auf weiteren Apps zu aktivieren, in die dieser Identitätsanbieter integriert ist.

Weitere Informationen zum Implementieren von benutzerdefinierten WAM-Identitätsanbietern finden Sie in der [Custom WAM Identity Provider API reference](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true) (API-Referenz für benutzerdefinierte WAM-Identitätsanbieter).

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>Windows-Hello- und FIDO2-Anmeldung mittels WebAuthn

In HoloLens 2 können kennwortfreie Benutzeranmeldeinformationen (z. B. Windows Hello- oder FIDO2-Sicherheitsschlüssel) genutzt werden, um sich im Web über Microsoft Edge und bei Websites anzumelden, die WebAuthn unterstützen. FIDO2 ermöglicht es, Benutzeranmeldeinformationen auf standardbasierten Geräte zur Authentifizierung bei Onlinediensten zu nutzen.

> [!Note]
> Die Spezifikationen [WebAuthn](https://www.w3.org/TR/webauthn/) und FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) sind in Diensten implementiert. Die von WebAuthn und FIDO2 angegebenen signierten Metadaten stellen Informationen bereit – wie etwa, ob der Benutzer anwesend war – und überprüfen die Authentifizierung über die lokale Geste.

Wie bei Windows Hello generiert das Gerät (HoloLens 2 oder der FIDO2-Sicherheitsschlüssel), einen privaten und einen öffentlichen Schlüssel auf dem Gerät, wenn der Benutzer FIDO2-Anmeldeinformationen erstellt und registriert. Der private Schlüssel wird sicher auf dem Gerät gespeichert und kann nur verwendet werden, nachdem er mit einer lokalen Geste (z. B. einer biometrischen Information oder einer PIN) entsperrt wurde. Nachdem der private Schlüssel gespeichert wurde, wird der öffentliche Schlüssel an das Microsoft-Kontensystem in der Cloud gesendet und für das zugeordnete Benutzerkonto registriert.

Nach der Anmeldung mit einem MSA- und Azure AD-Konto sendet das System eine generierte Nummer oder Datenvariable an das HoloLens 2- oder FIDO2-Gerät. HoloLens 2 oder das Gerät verwendet den privaten Schlüssel, um die Identifikation zu signieren. Die signierten Identifikations- und-Metadaten werden an das Microsoft-Kontensystem zurückgesendet und anhand des öffentlichen Schlüssels überprüft.

Windows Hello- und FIDO2-Geräte stützen sich beim Implementieren der Anmeldeinformationen auf das HoloLens-Gerät, insbesondere auf die integrierte sichere Trusted Platform Module-Enklave. Der private Schlüssel wird in der TPM-Enklave gespeichert und kann nur entweder über biometrische Informationen oder eine PIN entsperrt werden. In ähnlicher Weise stellt ein FIDO2-Sicherheitsschlüssel ein kleines externes Gerät mit einer integrierten sicheren Enklave dar, in der der private Schlüssel gespeichert wird und für dessen Entsperrung biometrische Informationen oder eine PIN erforderlich ist.

Beide Optionen bieten eine zweistufige Authentifizierung in einem Schritt, bei der für eine erfolgreiche Anmeldung sowohl ein registriertes Gerät als auch eine biometrische Information oder eine PIN erforderlich sind. Weitere Informationen hierzu können Sie der folgenden Abbildung und dem Prozess zur strengen Authentifizierung mit FIDO2-Sicherheitsschlüsseln entnehmen.

### <a name="strong-authentication-with-fido2-security-key"></a>Starke Authentifizierung mit dem FIDO2-Sicherheitsschlüssel

  ![FIDO img](images/security-fido2-whfb-smaller.png)

1. Benutzer setzt den FIDO2-Sicherheitsschlüssel in HoloLens 2 ein
1. Windows erkennt den FIDO2-Sicherheitsschlüssel
1. HoloLens sendet eine Authentifizierungsanforderung
1. Azure AD sendet Nonce zurück
1. Benutzer führt die Geste zum Entsperren der privaten Schlüsselspeicher in der sicheren Sicherheitsschlüssel-Enklave aus
1. FIDO2-Sicherheitsschlüssel signiert Nonce mit privatem Schlüssel
1. Die PRT-Tokenanforderung mit signierter Nonce wird an Azure AD gesendet
1. Azure AD überprüft den FIDO-Schlüssel
1. Azure AD gibt PRT und TGT zurück, um den Zugriff auf Ressourcen zu ermöglichen

MSA und Azure AD gehören zu den ersten vertrauenden Parteien, die die kennwortlose Authentifizierung durch die Implementierung von WebAuthn unterstützen.

Weitere Informationen zur Verwendung von WebAuthn mit Anwendungen und/oder SDKs finden Sie unter [WebAuthn-APIs für die kennwortfreie Authentifizierung unter Windows 10](/windows/security/identity-protection/hello-for-business/webauthnapis).

HoloLens 2 unterstützt FIDO2-Sicherheitsgeräte, die gemäß der Spezifikation implementiert sind und die Anforderungen erfüllen, die unter [Azure Active Directory kennwortlose Anmeldung](/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys) aufgeführt sind. FIDO2-Sicherheitsschlüssel sollten unterstützt werden.

## <a name="local-accounts"></a>Lokale Konten

Für die Bereitstellung im Offlinemodus kann ein einzelnes lokales Konto konfiguriert werden. Lokale Konten sind standardmäßig nicht aktiviert und müssen während der Gerätebereitstellung konfiguriert werden. Sie müssen sich mit einem Kennwort anmelden und unterstützen keine alternativen Authentifizierungsmethoden (z. B. [Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-overview) oder [Windows Hello](/windows-hardware/design/device-experiences/windows-hello)).

Weitere Informationen zu HoloLens-Benutzerkonten finden Sie unter [HoloLens Identity](hololens-identity.md) (HoloLens-Identität).

IT-Administratoren legen über [AllowMicrosoftAccountConnection](/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection) fest, ob der Benutzer ein MSA-Konto für Verbindungsauthentifizierungen und Dienste verwenden darf, die nicht auf E-Mails bezogen sind. Informationen zu Konfigurationsrichtlinien für Kennwörter, Leerlauf- und Sperrbildschirm-Richtlinien finden Sie unter [Gerätesperrung](/windows/client-management/mdm/policy-csp-devicelock).
