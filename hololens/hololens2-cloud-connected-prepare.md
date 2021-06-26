---
title: Bereitstellungshandbuch – Cloud connected HoloLens 2 deployment at scale with Remote Assist – Prepare
description: Erfahren Sie, wie Sie die Registrierung von HoloLens-Geräten über ein mit der Cloud verbundenes Netzwerk mithilfe von Azure Active Directory und der Identitätsverwaltung vorbereiten.
keywords: HoloLens, Verwaltung, cloudgebunden, Remote Assist, AAD, Azure AD, MDM, Mobile Geräteverwaltung
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
ms.openlocfilehash: 21132ed5d1e84d92a877747ac9a4c090b177ca08
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924569"
---
# <a name="prepare---cloud-connected-guide"></a>Prepare – Cloud connected Guide (Vorbereiten – Leitfaden für cloudbasierte Verbindung)

Am Ende dieses Artikels haben Sie Azure AD MDM eingerichtet und erfahren mehr über die Verwendung Azure AD Konten und Netzwerkanforderungen. Dieser Abschnitt des Leitfadens hilft Ihnen und Ihrer Organisation, sich auf die Bereitstellung von HoloLens 2 in der Cloud und die Verwendung von Dynamics 365 Remote Assist. Es geht um die Wichtigkeit der einzelnen Teile Ihrer Infrastruktur sowie um Links zu Leitfäden, die Sie bei Bedarf beim Einrichten dieser Teile unterstützen.

## <a name="infrastructure-essentials"></a>Infrastructure Essentials

Sowohl für persönliche als auch für Unternehmensbereitstellungsszenarien ist ein MDM-System die wesentliche Infrastruktur, die zum Bereitstellen und Verwalten von Windows 10 Holographic ist. Ein Azure AD Premium-Abonnement wird als Identitätsanbieter empfohlen und ist erforderlich, um bestimmte Funktionen zu unterstützen.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD ist ein cloudbasierter Verzeichnisdienst zur Identitäts- und Zugriffsverwaltung. Organisationen, die Microsoft Office 365 oder Intune verwenden, verwenden bereits Azure AD mit drei Editionen: Free, Premium P1 und Premium P2 (siehe [Azure Active Directory Editionen](https://azure.microsoft.com/documentation/articles/active-directory-editions)). Alle Editionen unterstützen Azure AD Geräteregistrierung, aber Premium P1 ist erforderlich, um die automatische MDM-Registrierung zu aktivieren, die wir später in diesem Handbuch verwenden werden.

> [!IMPORTANT]
> Es ist wichtig, über eine Azure Active Directory verfügen, da HoloLens-Geräte keine lokale AD-Verknüpfung unterstützen. Wenn Sie noch&#39;noch keine Azure Active Directory haben, wechseln Sie zu Erstellen eines neuen Mandanten [in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## <a name="identity-management"></a>Identitätsverwaltung

Mitarbeiter können nur ein Konto verwenden, um ein Gerät zu initialisieren, sodass es&#39;, dass Ihre Organisation zuerst steuert, welches Konto aktiviert wird. Die Wahl des Kontos bestimmt, wer das Gerät kontrolliert und welche Verwaltungsfunktionen Ihnen zur Verfügung stehen.

In diesem Leitfaden haben wir [](https://docs.microsoft.com/hololens/hololens-identity) ausgewählt, dass wir für die verwendete Identität Azure AD konten oder Azure Active Directory verwenden. Es gibt mehrere Vorteile für Azure AD, die wir verwenden möchten, z. B.:

- Mitarbeiter verwenden ihr Azure AD-Konto, um das Gerät in Azure AD zu registrieren, und registrieren es automatisch bei der MDM-Lösung der Organisation&#39;(Azure AD+MDM – erfordert Azure AD Premium).
- Azure AD-Konten unterstützen [einmaliges Anmelden.](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) Wenn sich ein Benutzer bei Remote Assist, wird seine Identität aus dem angemeldeten Azure AD-Benutzer erkannt, und der Benutzer wird zur Optimierung bei der App angemeldet.
- Azure AD Konten verfügen über zusätzliche [Authentifizierungsoptionen](https://docs.microsoft.com/hololens/hololens-identity) [über Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). Zusätzlich zur Iris-Anmeldung können sich Benutzer von einem anderen Gerät aus anmelden oder FIDO-Sicherheitsschlüssel verwenden.

### <a name="mobile-device-management"></a>Verwaltung mobiler Geräte

Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)ist Teil des Enterprise Mobility + Security, ein cloudbasiertes MDM-System, das Geräte verwaltet, die mit Ihrem Mandanten verbunden sind. Wie Office 365 verwendet Intune Azure AD für die Identitätsverwaltung, sodass Mitarbeiter dieselben Anmeldeinformationen verwenden, um Geräte bei Intune zu registrieren, die sie für die Anmeldung bei Office 365 verwenden. Intune unterstützt auch Geräte, auf denen andere Betriebssysteme wie iOS und Android ausgeführt werden, um eine vollständige MDM-Lösung zu bieten. Im Rahmen dieses Leitfadens konzentrieren wir uns&#39;darauf, Intune zu verwenden, um eine Cloudbereitstellung im großen Stil mit HoloLens 2.

> [!IMPORTANT]
> Mobile Apps müssen unbedingt Geräteverwaltung. Wenn Sie die&#39;noch nicht eingerichtet haben, befolgen Sie diese Anleitung und [erste Schritte mit Intune.](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)

> [!NOTE]
> Mehrere MDM-Systeme unterstützen Windows 10, und die meisten unterstützen Bereitstellungsszenarien für persönliche und unternehmenseigene Geräte. MDM-Anbieter, die Windows 10 Holographic unterstützen, umfassen derzeit u.a. AirWatch, MobileIron. Die meisten branchenführenden MDM-Anbieter unterstützen bereits die Integration in Azure AD. Die MDM-Anbieter mit Azure AD-Unterstützung finden Sie im [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## <a name="network"></a>Netzwerk

Bei diesem Setup wird davon HoloLens 2, dass geräte, die eine Verbindung mit dem Internet herstellen, von jedem verfügbaren offenen Wi-Fi herstellen. Da ein Benutzer die Netzwerkverbindung je nach Standort ändern muss, sollte er erfahren, wie [HoloLens-Geräte](https://docs.microsoft.com/hololens/hololens-network) mit WLAN verbunden werden.

Für Dynamics 365 Remote Assist gibt es eine Vielzahl von Netzwerkbedingungen, einschließlich Bandbreite, Latenz, Jitter und Paketverlust, die sich auf die Videoanruferfahrung auswirken können. Obwohl Audio- und Videoaufrufe in Umgebungen mit geringerer Bandbreite möglich sind, kann es zu Funktionsbeeinträchtigungen kommen. Wenn Sie Dynamics 365 Remote Assist HoloLens verwenden, sollten Sie die Netzwerkanforderungen beachten:

**Minimum:** Für Peer-to-Peer-Videoanrufe in HD-Qualität mit einer Auflösung von HD 1080p bei 30 FPS sind mindestens 1,5 MBit/s erforderlich.

**Optimal:** Für Peer-to-Peer-Videoanrufe in HD-Qualität mit einer Auflösung von HD 1080p sollten 4-5 MBit/s auf/ab erwartet werden.

Weitere Informationen:

- [Netzwerkanforderungen](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Empfehlungen zur Netzwerkoptimierung](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>Optional: Herstellen einer Verbindung zwischen HoloLens und VPN

Die Geräte, die mit diesem Leitfaden verbunden werden, werden über und ein externes Cloudnetzwerk eine Verbindung mit dem Netzwerk herstellen. Möglicherweise müssen Sie für den Zugriff auf Unternehmensressourcen&#39;Ihre Geräte über VPN verbinden. Es gibt verschiedene Möglichkeiten, Ihre Geräte mit VPN zu verbinden. Dabei kann der Endbenutzer entweder über die Gerätebenutzeroberfläche eine Verbindung herstellen, oder die Geräte können verwaltet werden und das VPN-Profil von einem PPKG oder MDM empfangen. Das Einrichten von VPN won&#39;wird in diesem Artikel nicht behandelt. Wenn Sie&#39;also mehr über die verschiedenen VPN-Protokolle oder Möglichkeiten zur Vpn-Verwaltung erfahren möchten, finden Sie in diesen Leitfäden Informationen zu [HoloLens](https://docs.microsoft.com/hololens/hololens-network#vpn) und VPN.

## <a name="next-step"></a>Nächster Schritt

> [!div class="nextstepaction"]
> [Mit der Cloud verbundene Bereitstellung: Konfigurieren](hololens2-cloud-connected-configure.md)
