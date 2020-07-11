---
title: Einrichten von HoloLens in einer geschäftlichen Umgebung
description: Weitere Informationen finden Sie unter Bereitstellen und Verwalten von HoloLens in Enterprise-Umgebungen.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.openlocfilehash: e53e6575ef688e01ce2d1f6124f3214b18b05c95
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865564"
---
# Bereitstellen von HoloLens in einer kommerziellen Umgebung

Sie können HoloLens im Maßstab in einer kommerziellen Einstellung bereitstellen und konfigurieren. Dieser Artikel enthält Anweisungen zum Bereitstellen von HoloLens-Geräten in einer geschäftlichen Umgebung. Dieser Leitfaden geht von grundlegender Vertrautheit mit HoloLens aus. Folgen Sie dem Leitfaden "erste [Schritte](hololens1-setup.md) ", um HoloLens zum ersten Mal einzurichten.

In diesem Dokument wird auch davon ausgegangen, dass das HoloLens von Sicherheitsteams als sicher für die Verwendung im Unternehmensnetzwerk ausgewertet wurde.  
> [!Tip]
> Weitere Informationen zur [HoloLens-Sicherheit](security-overview.md).
> Für HoloLens (1st Gen)-Sicherheit lesen Sie bitte [diese FAQ](hololens1-faq-security.md).

## Übersicht über Bereitstellungsschritte

1. [Ermitteln der benötigten Features](hololens-requirements.md#step-1-determine-what-you-need)
1. [Ermitteln, welche Lizenzen erforderlich sind](hololens-licenses-requirements.md)
1. [Konfigurieren Sie Ihr Netzwerk für HoloLens](hololens-commercial-infrastructure.md).
    1. Dieser Abschnitt enthält Bandbreitenanforderungen, URL und Ports, die für Ihre Firewall zugelassen werden müssen. Azure AD-Anleitung; Anleitung zur Verwaltung mobiler Geräte (MDM); Anleitung zur Bereitstellung und Verwaltung von apps und Zertifikat Leit Faden.
1. Optional [Konfigurieren von HoloLens mit einem Bereitstellungspaket](hololens-provisioning.md)
1. [Gerät registrieren](hololens-enroll-mdm.md)
1. [Einrichten von ringbasierten Updates für HoloLens](hololens-updates.md)
1. [Aktivieren der Bitlocker-Geräteverschlüsselung für HoloLens](security-encryption-data-protection.md)

## Schritt 1. Bestimmen, was Sie benötigen

Bevor Sie das HoloLens in Ihrer Umgebung bereitstellen, müssen Sie zunächst ermitteln, welche Features, Apps und Typen von Identitäten erforderlich sind. Darüber hinaus ist es wichtig, sicherzustellen, dass Ihr Sicherheitsteam die Nutzung des HoloLens im Netzwerk des Unternehmens genehmigt hat. Weitere Sicherheitsinformationen finden Sie unter [HoloLens2-Sicherheit](security-overview.md) .

### Art der Identität

Ermitteln Sie den Typ der Identität, die zum Anmelden beim Gerät verwendet wird.

1. **Lokale Konten:** Dieses Konto ist auf dem Gerät lokal (wie ein lokales Administratorkonto auf einem Windows-PC). Dadurch können sich nur 1 Benutzer beim Gerät anmelden.
2. **MSA:** Hierbei handelt es sich um ein privates Konto (wie Outlook, Hotmail, Gmail, Yahoo usw.). Dadurch können sich nur 1 Benutzer beim Gerät anmelden.
3. **Azure Active Directory-Konten (Azure AD):** Hierbei handelt es sich um ein in Azure AD erstelltes Konto. Dies gewährt ihrem Unternehmen die Möglichkeit, das HoloLens-Gerät zu verwalten. Auf diese Weise können sich mehrere Benutzer bei der HoloLens 1st Gen Commercial Suite/dem HoloLens 2-Gerät anmelden.

Ausführlichere Informationen zu Identitätstypen finden Sie im Artikel [HoloLens Identity](hololens-identity.md) .

### Art der Features

Ihre Funktionsanforderungen bestimmen, welche HoloLens Sie benötigen. Eine beliebte Funktion, die in Kundenumgebungen häufig bereitgestellt wird, ist der Kiosk Modus. Eine Liste der HoloLens-Schlüsselfeatures und die Editionen von HoloLens, die Sie unterstützen, finden Sie [hier](hololens-commercial-features.md).

**Was ist der Kiosk Modus?**

Der Kiosk Modus ist eine Möglichkeit, die apps zu beschränken, auf die ein Benutzer Zugriff hat. Das bedeutet, dass Benutzern nur der Zugriff auf bestimmte apps gestattet ist.

**Welchen Kiosk Modus benötige ich?**

Es gibt zwei Arten von Kiosk Modi: einzelne APP und Multi-app. Mit einem einzelnen App-Kioskmodus kann der Benutzer nur auf eine App zugreifen, während der Multi-App-Kioskmodus Benutzern den Zugriff auf mehrere angegebene Apps ermöglicht. Um festzustellen, welcher Kioskmodus für Ihr Unternehmen richtig ist, müssen die folgenden beiden Fragen beantwortet werden:

1. **Erfordern verschiedene Benutzer unterschiedliche Erfahrungen/Einschränkungen?** Das folgende Beispiel: Benutzer a ist ein Field Service Engineer, der nur Zugriff auf Remote Assist benötigt. Benutzer B ist ein Praktikant, der nur Zugriff auf Leitfäden benötigt.
    1. Wenn ja, benötigen Sie Folgendes:
        1. Azure Ad-Konten als die Methode zum Anmelden beim Gerät.
        1. **Multi-App-** Kioskmodus.
    1. Wenn Nein, fahren Sie mit der Frage zwei fort
1. **Benötigen Sie eine Multi-App-Umgebung?**
    1. Wenn ja, ist der Modus für **Multi-App-** Kiosk erforderlich.
    1. Wenn Sie die Antwort auf Frage 1 und 2 nicht haben, kann der **Einzel-App-** Kioskmodus verwendet werden.

**So konfigurieren Sie den Kiosk Modus:**

Es gibt zwei Hauptmethoden ([Bereitstellungspakete](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) und [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) zum Bereitstellen des Kioskmodus für HoloLens. Diese Optionen werden später im Dokument erläutert. Sie können jedoch die obigen Links verwenden, um zu den entsprechenden Abschnitten in diesem Dokument zu wechseln.

### Spezifische Szenarien für apps und Apps

Die meisten der in diesem Dokument gefundenen Schritte gelten auch für die folgenden apps:

| App | App-spezifische Szenarien |
| --- | --- |
| Remote Unterstützung | [Mandantenübergreifende Kommunikation](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| Handbücher  | *Demnächst* |
|Benutzerdefinierte apps | *Demnächst* |

### Ermitteln der Registrierungsmethode

1. Massenregistrierung mit einem Sicherheitstoken in einem Bereitstellungspaket.  
  Pros: Dies ist der automatisierte Ansatz \
  Cons: übernimmt das erste serverseitige Setup  
1. Anmeldung für Benutzer automatisch registrieren.  
  Pros: einfachster Ansatz  
  Nachteile: die Benutzer müssen die Einrichtung abschließen, nachdem das Bereitstellungspaket angewendet wurde.
1. _nicht empfohlen_ – Manuelles Registrieren des Post-Setups.  
  Pros: nach der Einrichtung möglich registrieren  
  Nachteile: die meisten manuellen Vorgehensweisen und Geräte sind erst dann zentral verwaltbar, wenn Sie manuell registriert werden.

  Weitere Informationen finden Sie [hier](hololens-enroll-mdm.md) .

### Ermitteln, ob Sie ein Bereitstellungspaket erstellen müssen

Es gibt zwei Methoden zum Konfigurieren eines HoloLens-Geräts (Bereitstellungspakete und MDMs). Wir empfehlen Ihnen, Ihr MDM-Gerät zum Konfigurieren Ihres HoloLens-Geräts zu verwenden. Es gibt jedoch einige Szenarien, in denen die Verwendung eines Bereitstellungspakets die bessere Wahl ist:

1. Sie möchten das HoloLens so konfigurieren, dass die Out-of-Box-Umgebung übersprungen wird (OOBE)
1. Sie haben Probleme beim Bereitstellen von Zertifikaten in einem komplexen Netzwerk. Die meiste Zeit können Sie Zertifikate mithilfe von MDM (auch in komplexen Umgebungen) bereitstellen. Einige Szenarien erfordern jedoch, dass Zertifikate über das Bereitstellungspaket bereitgestellt werden.

Einige der HoloLens-Konfigurationen, die in einem Bereitstellungspaket angewendet werden können:

- Anwenden von Zertifikaten auf das Gerät
- Einrichten einer WLAN-Verbindung
- Vorkonfigurieren von vordefinierten Fragen wie Sprache und Gebietsschema
- (HoloLens 2) Massenregistrieren für den Mobilgeräte-Verwaltungsdienst
- (HoloLens v1) Anwenden des Schlüssels zum Aktivieren von Windows Holographic for Business

Wenn Sie Bereitstellungspakete verwenden möchten, folgen Sie [diesem Leitfaden](hololens-provisioning.md).

## Support erhalten

Support erhalten Sie über die Microsoft-Support Website.

[Support-Anfrage einreichen](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
