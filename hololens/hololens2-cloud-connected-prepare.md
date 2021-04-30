---
title: 'Bereitstellungshandbuch : Bereitstellung mit cloudbasierter HoloLens 2 im großen Stil mit Remote Assist – Vorbereiten'
description: Erfahren Sie, wie Sie die Registrierung von HoloLens-Geräten über ein mit der Cloud verbundenes Netzwerk mithilfe von Azure Active Directory und Identitätsverwaltung vorbereiten.
keywords: HoloLens, Verwaltung, cloudverbunden, Remote Assist, AAD, Azure AD, MDM, Mobile Geräteverwaltung
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
ms.openlocfilehash: 067917396631f9a89a50b13ef1b7dcca8b631f52
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308688"
---
# <a name="prepare---cloud-connected-guide"></a>Vorbereiten – Leitfaden für cloudverknannte Verbindungen

Am Ende dieses Artikels haben Sie Azure AD, MDM eingerichtet und erfahren mehr über die Verwendung von Azure AD Konten und Netzwerkanforderungen. Dieser Abschnitt des Leitfadens hilft Ihnen und Ihrer Organisation, sich darauf vorzubereiten, HoloLens 2 in der Cloud bereitzustellen und Dynamics 365 Remote Assist zu verwenden. Es geht um die Bedeutung der einzelnen Teile Ihrer Infrastruktur sowie um Links zu Leitfäden, die Sie bei Bedarf beim Einrichten dieser Teile unterstützen.

## <a name="infrastructure-essentials"></a>Infrastructure Essentials

Sowohl für persönliche als auch unternehmensinterne Bereitstellungsszenarien ist ein MDM-System die grundlegende Infrastruktur, die zum Bereitstellen und Verwalten Windows 10 Holographic Geräten erforderlich ist. Ein Azure AD Premium-Abonnement wird als Identitätsanbieter empfohlen und ist erforderlich, um bestimmte Funktionen zu unterstützen.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD ist ein cloudbasierter Verzeichnisdienst zur Identitäts- und Zugriffsverwaltung. Organisationen, die Microsoft Office 365 oder Intune verwenden, verwenden bereits Azure AD mit drei Editionen: Free, Premium P1 und Premium P2 (siehe [Azure Active Directory Editionen](https://azure.microsoft.com/documentation/articles/active-directory-editions)).) Alle Editionen unterstützen Azure AD Geräteregistrierung, aber Premium P1 ist erforderlich, um die automatische MDM-Registrierung zu aktivieren, die wir später in diesem Leitfaden verwenden werden.

> [!IMPORTANT]
> Es ist wichtig, über eine Azure Active Directory zu verfügen, da HoloLens-Geräte keine lokale AD-Verknüpfung unterstützen. Wenn Sie&#39;noch keine Azure Active Directory eingerichtet haben, befolgen Sie die Anweisungen unter diesem Link, um zu beginnen und [einen neuen Mandanten in Azure Active Directory zu erstellen.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## <a name="identity-management"></a>Identitätsverwaltung

Mitarbeiter können nur ein Konto verwenden, um ein Gerät zu initialisieren, sodass es zwingend erforderlich&#39;, dass Ihre Organisation steuert, welches Konto zuerst aktiviert wird. Die Wahl des Kontos bestimmt, wer das Gerät kontrolliert und welche Verwaltungsfunktionen Ihnen zur Verfügung stehen.

In diesem Leitfaden haben wir ausgewählt, dass wir für die verwendete [Identität](https://docs.microsoft.com/hololens/hololens-identity) Azure AD Konten oder Azure Active Directory Konten verwenden. Es gibt mehrere Vorteile für Azure AD Konten, die wir verwenden möchten, z. B.:

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

Für Dynamics 365 Remote Assist gibt es eine Vielzahl von Netzwerkbedingungen, einschließlich Bandbreite, Latenz, Jitter und Paketverlust, die sich auf die Videoanruferfahrung auswirken können. Obwohl Audio- und Videoaufrufe in Umgebungen mit geringerer Bandbreite möglich sind, kann es zu Funktionsbeeinträchtigungen kommen. Wenn Sie Dynamics 365 Remote Assist auf HoloLens verwenden, sind hier die Netzwerkanforderungen zu beachten:

**Minimum:** 1,5 MBit/s nach oben/unten ist für Peer-to-Peer-HD-Videoanrufe mit einer Auflösung von HD 1080p bei 30 FPS erforderlich.

**Optimal:** Für Videoanrufe mit Peer-zu-Peer-HD-Qualität mit einer Auflösung von HD 1080p sollten 4 bis 5 MBit/s nach oben/unten erwartet werden.

Weitere Informationen:

- [Netzwerkanforderungen](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Empfehlungen zur Netzwerkoptimierung](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>Optional: Herstellen einer Verbindung zwischen HoloLens und VPN

Die Geräte, die mit diesem Leitfaden verbunden werden, werden über und ein externes Cloudnetzwerk mit dem Netzwerk verbunden. Es kann sein, dass Sie für den Zugriff auf Unternehmensressourcen, die Sie&#39;benötigen, Ihre Geräte über VPN verbinden müssen. Es gibt verschiedene Möglichkeiten, Ihre Geräte mit VPN zu verbinden, wobei der Endbenutzer über die Geräte-Benutzeroberfläche eine Verbindung herstellen kann, oder die Geräte verwaltet werden können und das VPN-Profil von einer PPKG- oder MDM-Datei empfangen können. Das Einrichten von VPN wird&#39;in diesem Artikel nicht behandelt. Wenn Sie also&#39;mehr über die verschiedenen VPN-Protokolle oder Möglichkeiten zum Verwalten von VPN erfahren möchten, finden Sie [in diesen Handbüchern Informationen zu HoloLens und VPN.](https://docs.microsoft.com/hololens/hololens-network#vpn)

## <a name="next-step"></a>Nächster Schritt

> [!div class="nextstepaction"]
> [Bereitstellung mit Cloudverbindung : Konfigurieren](hololens2-cloud-connected-configure.md)
