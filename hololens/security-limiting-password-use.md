---
title: Begrenzen der Verwendung von Kennwörtern
description: Begrenzen der Verwendung von Kennwörtern für HoloLens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: Sicherheit, Hololens, begrenzen der Verwendung von Kennwörtern, Kennwort, Hololens-Kennwort, Anmeldung, anmelden, Windows Hello, Hello, Windows-Konto-Manager, FIDO2 anmelden, Fido 2, Webauthentifizierung, lokales Konto, Hololens Sicherheit
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2d9527c9fee2818dfe8aa1f88a2f193415323bb1
ms.sourcegitcommit: 37910c10f0f98aa9cbdc29124cd8f14ee0af3fbd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2021
ms.locfileid: "11280664"
---
# Begrenzen der Verwendung von Kennwörtern

Auf den meisten Computersystemen dienen Benutzeranmeldeinformationen als Grundlage für die Sicherheit, wodurch die Systeme von wiederverwendbaren, vom Benutzer erstellten Kennwörtern abhängig sind. Dies hat zur Folge, dass Kennwörter auch zu den häufigsten Ursachen von Kontokompromittierungen und Datenschutzverletzungen zählen. Kennwörter können beispielsweise während der Übertragung abgefangen oder von einem Server gestohlen (durch Phishing- oder Passwort-Spraying-Angriffe) und kompromittiert werden, um Zugriff auf ein Benutzerkonto zu erhalten.

Für mehr Sicherheit und besseren Kontoschutz bietet HoloLens 2 die Möglichkeit, starke, hardwaregesicherte "kennwortfreie" Anmeldeinformationen (einschließlich Windows Hello) für die Anmeldung bei Geräten zu aktivieren, die einen nahtlosen Zugang zur Microsoft-Cloud ermöglichen. 

## Anmelden über ein anderes Gerät

HoloLens 2 bietet Anmeldeoptionen für Remotegeräte für Azure Active Directory-Arbeitskonten während des anfänglichen Geräte-Setups und der Benutzeranmeldung, um die Notwendigkeit der Eingabe komplexer Kennwörter zu reduzieren und jene von Kennwörtern als Anmeldeinformationen zu minimieren. Benutzer und Organisationen, die Smartcards zur Authentifizierung verwenden, haben Schwierigkeiten beim Verwenden dieser Anmeldeinformationen auf Geräten wie HoloLens 2, und häufig erstellen Organisationen komplexe Systeme und kostspielige Prozesse, um dieses Problem zu umgehen. Zu dessen Behebung bietet Azure AD zwei Optionen für die kennwortlose Anmeldung bei HoloLens 2. 

Die erste Authentifizierungsmethode basiert auf den neuen Funktionen in der Microsoft Authentifikator-App zur Bereitstellung schlüsselbasierter Authentifizierung, durch die Benutzeranmeldeinformationen an ein Gerät gebunden sind. Nachdem der Administrator die Aktivierung für einen Mandanten durchgeführt hat, wird den Benutzern während des Setups eines HoloLens-Geräts eine Meldung angezeigt, in der sie aufgefordert werden, auf eine Zahl in ihrer App zu tippen. Sie müssen dann eine Zahl angeben, die mit jener in ihrer Authentifikator-App übereinstimmt, "Genehmigen" auswählen, ihre PIN oder eine biometrische Anmeldeinformation angeben und die Authentifizierung abschließen, damit das HoloLens-Setup fortgesetzt werden kann. Dieser Vorgang wird unter [kennwortlose Anmeldung](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone) genauer beschrieben.

Bei der zweiten Methode handelt es sich um einen benutzerfreundlichen Gerätecodecode-Vorgang, für den keine zusätzliche Infrastruktur erforderlich ist.  Dieser Remote-Anmeldevorgang basiert auf einem anderen vertrauenswürdigen Gerät, das den bevorzugten Authentifizierungsmechanismus der Organisation unterstützt. Nach Abschluss des Vorgangs werden Token zurück an das HoloLens-Gerät ausgegeben, um die Anmeldung oder das Gerätesetup abzuschließen. Nachfolgend die Schritte bei diesem Vorgang:

  1.    Beim anfänglichen Gerätesetup- oder Anmeldevorgang wird Benutzern auf der Windows-Willkommensseite ein "Von einem anderen Gerät anmelden"-Link angezeigt, auf den sie dann tippen. Damit wird eine Remote-Anmeldesitzung gestartet.
  2.    Anschließend wird dem Benutzer eine Abfrageseite mit einem kurzen URI ([https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)) angezeigt, der auf den Endpunkt für die Geräteauthentifizierung des Azure AD Secure Token Service (STS) verweist. Dem Benutzer wird außerdem ein einmaliger Code angezeigt, der in der Cloud sicher generiert wird und maximal 15 Minuten gültig ist. Neben der Codegenerierung erstellt Azure AD beim Initiieren der Remote-Anmeldeanforderung im vorherigen Schritt auch eine verschlüsselte Sitzung, und der URI und der Code werden zusammen für die Genehmigung der Remote-Anmeldeanforderung verwendet. 
  3.    Der Benutzer navigiert dann von dem anderen Gerät zum URI und wird aufgefordert, den Code einzugeben, der auf seinem HoloLens 2-Gerät angezeigt wird. 
  4.    Nachdem der Benutzer den Code eingegeben hat, wird von Azure AD STS eine Seite angezeigt, auf der das HoloLens 2-Gerät des Benutzers anzeigt wird, von dem die Remote-Anmeldeanforderung ausgelöst und die Codegenerierung angefordert wurde. Der Benutzer wird dann zur Bestätigung aufgefordert, um Phishing-Angriffe zu verhindern. 
  5.    Wenn der Benutzer die Anmeldung bei der angezeigten "Anwendung" fortsetzen möchte, wird er von Azure AD STS zur Eingabe seiner Anmeldeinformationen aufgefordert. Bei erfolgreicher Authentifizierung aktualisiert Azure AD STS die Remotesitzung im Cache als "genehmigt" und stellt einen Autorisierungscode bereit.
  6.    Schließlich empfängt die Abfrageseite auf dem HoloLens 2-Gerät des Benutzers die Antwort "autorisiert" von Azure AD und geht zur Validierung des Benutzercodes sowie des zugehörigen gespeicherten Autorisierungscodes über, und generiert dann OAuth-Token wie angefordert, um das Setup des Geräts abzuschließen. Das erstellte Authentifizierungstoken ist eine Stunde lang gültig, das Aktualisierungstoken hingegen 90 Tage. 

Die in diesem Vorgang verwendeten Codegenerierungs- und -verschlüsselungsalgorithmen sind FIPS-konform. HoloLens 2-Geräte verwenden das TPM zum Sichern von Geräteschlüsseln und zum Verschlüsseln von Token, die nach der Benutzerauthentifizierung mithilfe von hardwaregeschützten Schlüsseln generiert werden. Weitere Informationen zum Thema Tokenschutz in HoloLens 2 finden Sie unter [Was ist ein primäres Aktualisierungstoken (PRT)?](https://docs.microsoft.com/azure/active-directory/devices/concept-primary-refresh-token).

## Geräteanmeldung mit Windows Hello

[Windows Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) bietet kennwortfreie Optionen, die direkt in das Betriebssystem integriert sind, sodass sich die Benutzer über Iris oder PIN beim Gerät anmelden können. Eine PIN ist immer als Anmeldeinformationen verfügbar und für das Einrichten von Geräten erforderlich, während Iris optional ist und übersprungen werden kann. Benutzer können sich mit ihrem persönlichen Microsoft-Konto oder [Azure Active Directory-Arbeitskonto* ohne* Eingabe eines Kennworts auf HoloLens-Geräten anmelden](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless). Optionen wie diese bieten Benutzern schnellen und sicheren Zugriff auf ihre vollständige Windows-Umgebung, Apps, Daten, Websites und Dienste. Näheres zur Strategie von Microsoft in Bezug auf kennwortlose Lösungen finden Sie hier.

Wenn eine Windows Hello-Anmeldeinformation erstellt wird, stellt sie ein Vertrauensverhältnis mit einem Identitätsanbieter her und erstellt ein asymmetrisches Schlüsselpaar für die Authentifizierung. Eine Windows Hello-Geste (wie z. B. Iris oder PIN) liefert Entropie zum Entschlüsseln eines privaten Schlüssels, der durch den TPM-Chip (Trusted Platform Module) des Geräts gesichert wird. Dieser private Schlüssel wird dann verwendet, um an einen authentifizierenden Server gesendete Anforderungen zu signieren, und nach erfolgreicher Authentifizierung wird dem Benutzer der Zugriff auf seine E-Mails, Bilder und andere Kontoeinstellungen gewährt. 

Weitere Informationen können Sie der folgenden Infografik entnehmen:

  ![Windows Hello-Anmeldung](images/security-hello-sign-in.png)
  
Beachten Sie in der vorstehenden Abbildung, dass "nonce" für "Nonce-Zahl" steht und eine Zufalls- oder halbzufällig generierte Zahl ist. Sobald die biometrischen oder PIN-Anmeldeinformationen für Windows Hello eingerichtet sind, verlassen sie nie das Gerät, auf dem sie bereitgestellt werden. Selbst wenn die Windows Hello-PIN des Benutzers gestohlen würde, z. B. bei einem Phishing-Angriff, wäre sie [ohne das physische Gerät des Benutzers nutzlos](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password). 

Für zusätzliche Sicherheit sind Windows Hello-Anmeldeinformationen durch das Trusted Platform Module (TPM) geschützt, um sie manipulationssicher zu machen und durch Anti-Hammering-Schutz gegen mehrfache falsche Einträge sowie durch Schutz vor Schadsoftware zu schützen, um eine Gefährdung zu vermeiden. Weitere Informationen über das einmalige Anmelden (Single Sign-on, SSO) finden Sie in dieser [Übersicht über SSO-Methoden](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).

Die Iris-Authentifizierung greift auf die PIN zurück. Um eine neue PIN (ein starker Authentifikator) auf dem Gerät einzurichten, muss der Benutzer erst kürzlich eine[mehrstufige Authentifizierung (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) durchgeführt haben, um den Vorgang ausführen zu können.

## Einmaliges Anmelden mit Web Account Manager 

Einmaliges Anmelden (Single Sign-on, SSO) ermöglicht es kennwortfreien Benutzern, sich beim Gerät mit ihrem persönlichen Konto bzw. ihr Geschäfts- oder Uni-/Schulkonto anzumelden. Der Benutzer wird durch SSO automatisch zur Nutzung aller integrierten Apps und Dienste über die [Web Account Manager-APIs](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true) autorisiert.

Nachdem eine Identität über eine Anwendung hinzugefügt wurde, kann sie, bei Einwilligung des Benutzers, über die systembasierte Integration für alle Apps und Dienste bereitgestellt werden. Dadurch wird die Mühe, um sich bei der App anzumelden, erheblich reduziert, und den Benutzern wird eine nahtlose Identitätsumgebung geboten.

Weitere Informationen zum Implementieren von Web Account Manager-APIs finden Sie unter [Implementieren von Web Account Manager-APIs](https://docs.microsoft.com/windows/uwp/security/web-account-manager).

  ![Sicherheits-API](images/security-api-img.png)
  
Bei App-Suites mit speziellen Authentifizierungsanforderungen ist das WAM-Framework (Web Account Manager) auf benutzerdefinierte Identitätsanbieter erweiterbar. Benutzer können den benutzerdefinierten Identitätsanbieter, der als universelle UWP-App (Universelle Windows Platform) gepackt ist, aus dem Microsoft Store herunterladen, um SSO auf weiteren Apps zu aktivieren, in die dieser Identitätsanbieter integriert ist. 

Weitere Informationen zum Implementieren von benutzerdefinierten WAM-Identitätsanbietern finden Sie unter [API-Referenz für benutzerdefinierte WAM-Identitätsanbieter](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true).

## Windows-Hello- und FIDO2-Anmeldung mittels WebAuthn

In HoloLens 2 können kennwortfreie Benutzeranmeldeinformationen (z. B. Windows Hello- oder FIDO2-Sicherheitsschlüssel) genutzt werden, um sich im Web über Microsoft Edge und auf Websites anzumelden, die WebAuthn unterstützen. FIDO2 ermöglicht es, Benutzeranmeldeinformationen auf standardbasierten Geräte zur Authentifizierung bei Onlinediensten zu nutzen.

> [!Note] 
> Die [WebAuthn](https://www.w3.org/TR/webauthn/)- und FIDO2[ CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html)-Spezifikationen werden in Dienste implementiert. Die von WebAuthn und FIDO2 angegebenen signierten Metadaten stellen Informationen bereit wie z. B., ob der Benutzer anwesend war, und überprüfen die Authentifizierung über die lokale Geste.

Wie bei Windows Hello generiert das Gerät (HoloLens 2 oder der FIDO2-Sicherheitsschlüssel), wenn der Benutzer FIDO2-Anmeldeinformationen erstellt und registriert, einen privaten und einen öffentlichen Schlüssel auf dem Gerät. Der private Schlüssel wird auf dem Gerät sicher gespeichert und kann nur verwendet werden, nachdem er mit einer lokalen Geste (z. B. einer biometrischen Information oder einer PIN) entsperrt wurde. Nachdem der private Schlüssel gespeichert wurde, wird der öffentliche Schlüssel an das Microsoft-Kontensystem in der Cloud gesendet und für das zugeordnete Benutzerkonto registriert.

Nach der Anmeldung mit einem MSA- und Azure AD-Konto sendet das System eine generierte Nummer oder Datenvariable an das HoloLens 2- oder FIDO2-Gerät. HoloLens 2 oder das Gerät verwendet den privaten Schlüssel, um die Identifikation zu signieren. Die signierten Identifikations- und-Metadaten werden an das Microsoft-Kontensystem zurückgesendet und mithilfe des öffentlichen Schlüssels überprüft.

Windows Hello- und FIDO2-Geräte implementieren Anmeldeinformationen, die auf dem HoloLens-Gerät basieren, insbesondere der integrierten sicheren Trusted Platform Module-Enklave. Der private Schlüssel wird in der TPM-Enklave gespeichert und kann nur entweder über biometrische Informationen oder eine PIN entsperrt werden. In ähnlicher Weise ist ein FIDO2-Sicherheitsschlüssel ein kleines externes Gerät mit einer integrierten sicheren Enklave, in der der private Schlüssel gespeichert wird, für dessen Entsperrung biometrische Informationen oder eine PIN erforderlich ist.

Beide Optionen bieten eine zweistufige Authentifizierung in einem Schritt, bei der sowohl ein registriertes Gerät als auch eine biometrische Information oder eine PIN erforderlich sind, um sich anmelden zu können. Weitere Informationen hierzu können Sie der folgenden Abbildung zur strengen Authentifizierung mit FIDO2-Sicherheitsschlüsseln entnehmen:

  ![FIDO img](images/security-fido2-whfb.png)

MSA und Azure AD gehören zu den ersten vertrauenden Parteien, die die kennwortlose Authentifizierung durch die Implementierung von WebAuthn unterstützen. 

Weitere Informationen zum Verwenden von WebAuthn mit Anwendungen und/oder SDKs finden Sie unter [WebAuthn-APIs für die kennwortlose Authentifizierung unter Windows 10](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/webauthnapis).

## Lokale Konten

Für die Bereitstellung im Offlinemodus kann ein einzelnes lokales Konto konfiguriert werden. Lokale Konten sind standardmäßig nicht aktiviert und müssen während der Gerätebereitstellung konfiguriert werden. Es ist erforderlich, dass sie sich mittels eines Kennworts anmelden und keine alternativen Authentifizierungsmethoden (z. B. [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) oder [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)) unterstützen. 

Weitere Informationen zu HoloLens-Benutzerkonten finden Sie unter [HoloLens-Identität](https://docs.microsoft.com/hololens/hololens-identity). 

IT-Administratoren legen über [AllowMicrosoftAccountConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection) fest, ob der Benutzer ein MSA-Konto für Verbindungsauthentifizierungen und Dienste verwenden darf, die nicht auf E-Mails bezogen sind. Informationen zu Konfigurationsrichtlinien für Kennwörter, Leerlauf- und Sperrbildschirm-Richtlinien finden Sie unter [Gerätesperrung](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock). 
