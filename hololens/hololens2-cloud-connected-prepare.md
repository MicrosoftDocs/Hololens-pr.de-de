---
title: Bereitstellungshandbuch – Cloud Connected HoloLens 2-Bereitstellung im Maßstab mit Remote Unterstützung – vorbereiten
description: Vorbereiten der Registrierung von HoloLens-Geräten über ein in der Cloud verbundenes Netzwerk
keywords: HoloLens, Verwaltung, Cloud Connected, Remote Assist, AAD, Azure AD, MDM, Verwaltung mobiler Geräte
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a4e99740d985a709683595cd5afef76094faaf76
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253052"
---
# Leitfaden "vorbereiten – Wolke verbunden"

Am Ende dieses Artikels haben Sie Azure AD, MDM eingerichtet und mehr über die Verwendung von Azure Ad-Konten und Netzwerkanforderungen erfahren. Dieser Abschnitt des Leitfadens hilft Ihnen und Ihrer Organisation, sich auf die Bereitstellung von HoloLens 2 in der Cloud vorzubereiten und die Verwendung von Dynamics 365-Remote Unterstützung zu verwenden. Es geht um die Wichtigkeit der einzelnen Teile Ihrer Infrastruktur sowie um Links zu Leitfäden, die Ihnen bei der Einrichtung dieser Komponenten bei Bedarf behilflich sein können.

## Infrastruktur-Grundlagen

Sowohl für private als auch für Unternehmens Bereitstellungsszenarien ist ein MDM-System die grundlegende Infrastruktur, die für die Bereitstellung und Verwaltung von holographischen Windows 10-Geräten erforderlich ist. Ein Azure AD Premium-Abonnement wird als Identitätsanbieter empfohlen und ist erforderlich, um bestimmte Funktionen zu unterstützen.

### Azure Active Directory

AzureAD ist ein cloudbasierter Verzeichnisdienst zur Identitäts- und Zugriffsverwaltung. Organisationen, die Microsoft Office 365 oder InTune verwenden, verwenden bereits Azure AD mit drei Editionen: Free, Premium P1 und Premium P2 (siehe [Azure Active Directory-Editionen](https://azure.microsoft.com/documentation/articles/active-directory-editions)). Alle Editionen unterstützen die Azure AD-Geräteregistrierung, aber Premium P1 ist erforderlich, um die MDM-automatische Registrierung zu aktivieren, die wir später in diesem Leitfaden verwenden werden.

> [!IMPORTANT]
> Es ist wichtig, ein Azure Active Directory zu haben, da HoloLens-Geräte lokale Ad-Joins nicht unterstützen. Wenn Sie Don&#39;t bereits über eine Azure Active Directory-Einrichtung verfügen, folgen Sie den Anweisungen in diesem Link, um zu beginnen und [einen neuen Mandanten in Azure Active Directory zu erstellen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## Identitätsverwaltung

Mitarbeiter können nur ein Konto verwenden, um ein Gerät zu initialisieren, damit es&#39;wichtig ist, dass Ihre Organisation steuert, welches Konto zuerst aktiviert wird. Die Wahl des Kontos bestimmt, wer das Gerät kontrolliert und welche Verwaltungsfunktionen Ihnen zur Verfügung stehen.

In diesem Leitfaden haben wir entschieden, dass für die verwendete [Identität](https://docs.microsoft.com/hololens/hololens-identity) Azure Ad-Konten oder Azure Active Directory-Konten verwendet werden. Es gibt mehrere Vorteile für Azure Ad-Konten, die Sie verwenden möchten, beispielsweise:

- Mitarbeiter verwenden Ihr Azure AD-Konto, um das Gerät in Azure AD zu registrieren, und registrieren es automatisch bei der Organisation&#39;s MDM-Lösung (Azure AD + MDM – erfordert Azure AD Premium).
- Azure Ad-Konten unterstützen [einmaliges Anmelden](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on). Wenn sich ein Benutzer bei Remote Assist anmeldet, wird dessen Identität vom signierten Azure AD-Benutzer erkannt, und der Benutzer wird bei der APP für eine optimierte Benutzeroberfläche angemeldet.
- Azure Ad-Konten verfügen über zusätzliche [Authentifizierungsoptionen](https://docs.microsoft.com/hololens/hololens-identity) über [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). Neben der Iris-Anmeldung können sich Benutzer von einem anderen Gerät aus anmelden oder Fido-Sicherheitsschlüssel verwenden.

### Verwaltung mobiler Geräte

Microsoft [InTune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune), ein Bestandteil des Enterprise Mobility + Security, ist ein Cloud-basiertes MDM-System, das Geräte verwaltet, die mit Ihrem Mandanten verbunden sind. Wie in Office 365 verwendet InTune Azure AD für die Identitätsverwaltung, damit Mitarbeiter dieselben Anmeldeinformationen für die Registrierung von Geräten in InTune verwenden, die Sie für die Anmeldung bei Office 365 verwenden. InTune unterstützt auch Geräte, die andere Betriebssysteme wie IOS und Android ausführen, um eine vollständige MDM-Lösung bereitzustellen. Im Sinne dieses Leitfadens&#39;wir uns auf die Verwendung von InTune konzentrieren, um eine Cloud-Bereitstellung mit HoloLens 2 im Maßstab zu ermöglichen.

> [!IMPORTANT]
> Es ist wichtig, die Verwaltung mobiler Geräte zu überlassen. Wenn Sie Don&#39;t bereits eingerichtet haben, folgen Sie diesem Leitfaden und [Erste Schritte mit InTune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up).

> [!NOTE]
> Mehrere MDM-Systeme unterstützen Windows10, und die meisten unterstützen Bereitstellungsszenarien für persönliche und unternehmenseigene Geräte. MDM-Anbieter, die Windows 10 holographische unterstützen, umfassen derzeit: Watch, MobileIron und andere. Die meisten branchenführenden MDM-Anbieter unterstützen bereits die Integration in AzureAD. Die MDM-Anbieter mit Azure AD-Unterstützung finden Sie im [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## Network

In diesem Setup gehen wir davon aus, dass HoloLens 2-Geräte über jedes verfügbare Open Wi-Fi-Netzwerk mit dem Internet verbunden sind. Da ein Benutzer die Netzwerkverbindung je nach Standort ändern muss, sollten Sie erfahren, wie Sie [HoloLens-Geräte mit WLAN verbinden.](https://docs.microsoft.com/hololens/hololens-network)

Für Dynamics 365-Remote Unterstützung gibt es eine Reihe von Netzwerkbedingungen, einschließlich Bandbreite, Latenz, Jitter und Paketverlust, die sich auf die Videoanruf Funktion auswirken können. Obwohl Audio-und Videoanrufe in Umgebungen mit reduzierter Bandbreite möglich sind, kann es zu einer Verschlechterung der Funktion kommen. Bei Verwendung von Dynamics 365 Remote Assist auf HoloLens sind hier die Netzwerkanforderungen, die Sie beachten sollten:

**Mindestens** : 1,5 Mbps für Peer-to-Peer-Videoanrufe in HD-Qualität mit einer Auflösung von HD 1080p bei 30 Bildern pro Sekunde.

**Optimal:** Für Videoanrufe zwischen Peer-to-Peer-HD-Qualität mit einer Auflösung von HD 1080p sollten 4-5 MBit/s erwartet werden.

Weitere Informationen:

- [Netzwerkanforderungen](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Empfehlungen zur Netzwerkoptimierung](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### Optional: Verbinden Ihres HoloLens mit VPN

Die Geräte, die mit diesem Leitfaden verbunden sind, werden über ein externes Cloud-Netzwerk mit dem Netzwerk verbunden. Möglicherweise müssen Sie für den Zugriff auf Unternehmensressourcen&#39;Ihre Geräte über VPN verbinden. Es gibt verschiedene Möglichkeiten, Ihre Geräte mit VPN zu verbinden, und zwar sowohl, wenn der Endbenutzer über die Geräte-UI eine Verbindung herstellen kann, oder die Geräte können verwaltet werden und das VPN-Profil von einem PPKG oder MDM empfangen. Anleitung zum Einrichten von VPN Won&#39;t in diesem Artikel behandelt werden, wenn Sie also&#39;d mehr über die unterschiedlichen VPN-Protokolle oder Methoden zum Verwalten von VPN erfahren möchten, besuchen Sie [Diese Leitfäden, um Informationen zu HoloLens und VPN](https://docs.microsoft.com/hololens/hololens-network#vpn) zu erhalten.

## Nächster Schritt

> [!div class="nextstepaction"]
> [Cloud Connected-Bereitstellung – konfigurieren](hololens2-cloud-connected-configure.md)
