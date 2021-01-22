---
title: Bereitstellungshandbuch – Mit der Cloud verbundene HoloLens 2-Bereitstellung im großen Maßstab mit Remote Assist – Vorbereiten
description: Erfahren Sie, wie Sie sich auf die Registrierung von HoloLens-Geräten über ein cloudverbundenes Netzwerk mit Azure Active Directory und Identitätsverwaltung vorbereiten.
keywords: HoloLens, Verwaltung, mit der Cloud verbunden, Remote Assist, AAD, Azure AD, MDM, Verwaltung mobiler Geräte
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283866"
---
# Vorbereiten – Leitfaden mit Verbindung mit der Cloud

Am Ende dieses Artikels haben Sie Azure AD, MDM eingerichtet und erfahren mehr über die Verwendung von Azure AD-Konten und Netzwerkanforderungen. Dieser Abschnitt des Leitfadens hilft Ihnen und Ihrer Organisation bei der Vorbereitung auf die Bereitstellung von HoloLens 2 in der Cloud und die Verwendung von Dynamics 365 Remote Assist. Dabei geht es um die Bedeutung der einzelnen Teile Ihrer Infrastruktur sowie um links zu Anleitungen, mit denen Sie diese Teile bei Bedarf einrichten können.

## Infrastructure Essentials

Sowohl für persönliche als auch für Unternehmensbereitstellungsszenarien ist ein MDM-System die wesentliche Infrastruktur, die zum Bereitstellen und Verwalten von Windows 10 -Holographic-Geräten erforderlich ist. Ein Azure AD Premium-Abonnement wird als Identitätsanbieter empfohlen und ist erforderlich, um bestimmte Funktionen zu unterstützen.

### Azure Active Directory

AzureAD ist ein cloudbasierter Verzeichnisdienst zur Identitäts- und Zugriffsverwaltung. Organisationen, die Microsoft Office 365 oder Intune verwenden, verwenden bereits Azure AD mit drei Editionen: Kostenlos, Premium P1 und Premium P2 (siehe [Azure Active Directory-Editionen).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Alle Editionen unterstützen die Azure AD-Geräteregistrierung, Premium P1 ist jedoch erforderlich, um die automatische MDM-Registrierung zu aktivieren, die wir später in diesem Handbuch verwenden werden.

> [!IMPORTANT]
> Es ist wichtig, über ein Azure Active Directory zu verfügen, da die lokale AD-Verknüpfung von HoloLens-Geräten nicht unterstützt wird. Wenn Sie noch&#39;azure Active Directory eingerichtet haben, befolgen Sie die Anweisungen in diesem Link, um zu beginnen und einen neuen Mandanten [in Azure Active Directory zu erstellen.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## Identitätsverwaltung

Mitarbeiter können nur ein Konto verwenden, um ein Gerät zu initialisieren, sodass es&#39;, dass Ihre Organisation steuert, welches Konto zuerst aktiviert wird. Die Wahl des Kontos bestimmt, wer das Gerät kontrolliert und welche Verwaltungsfunktionen Ihnen zur Verfügung stehen.

In diesem Leitfaden haben wir [](https://docs.microsoft.com/hololens/hololens-identity) ausgewählt, dass wir für die verwendete Identität Azure AD- oder Azure Active Directory-Konten verwenden. Es gibt mehrere Vorteile für Azure AD-Konten, die wir verwenden möchten, z. B.:

- Mitarbeiter verwenden ihr Azure AD-Konto, um das Gerät in Azure AD zu registrieren und es automatisch bei der&#39;-MDM-Lösung der Organisation zu registrieren (Azure AD+MDM – erfordert Azure AD Premium).
- Azure AD-Konten unterstützen [einmaliges Anmelden.](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) Wenn sich ein Benutzer bei Remote Assist registriert, wird seine Identität des angemeldeten Azure AD-Benutzers erkannt, und der Benutzer wird für eine optimierte Benutzererfahrung bei der App angemeldet.
- Azure AD-Konten verfügen über zusätzliche [Authentifizierungsoptionen](https://docs.microsoft.com/hololens/hololens-identity) [über Windows Hello for Business.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) Zusätzlich zur Anmeldung mit Iris können sich Benutzer von einem anderen Gerät aus anmelden oder DIE SICHERHEITSSCHLÜSSEL von FIDO verwenden.

### Verwaltung mobiler Geräte

Microsoft [Intune,](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)Teil von Enterprise Mobility + Security, ist ein cloudbasiertes MDM-System, das Geräte verwaltet, die mit Ihrem Mandanten verbunden sind. Wie Office 365 verwendet Intune Azure AD für die Identitätsverwaltung, sodass Mitarbeiter die gleichen Anmeldeinformationen verwenden, um Geräte in Intune zu registrieren, die sie zum Anmelden bei Office 365 verwenden. Intune unterstützt auch Geräte, die andere Betriebssysteme wie iOS und Android ausführen, um eine vollständige MDM-Lösung bereitzustellen. Im Rahmen dieses Leitfadens konzentrieren&#39;auf die Verwendung von Intune für die Bereitstellung einer Cloud im großen Maßstab mit HoloLens 2.

> [!IMPORTANT]
> Die Verwaltung mobiler Geräte ist unerlässlich. Wenn Sie noch&#39;sie noch nicht eingerichtet haben, folgen Sie diesem Handbuch und [den ersten Schritte mit Intune.](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)

> [!NOTE]
> Mehrere MDM-Systeme unterstützen Windows10, und die meisten unterstützen Bereitstellungsszenarien für persönliche und unternehmenseigene Geräte. Zu den MDM-Anbietern, die Windows 10 Holographic unterstützen, gehören derzeit: AirWatch, MobileIron und andere. Die meisten branchenführenden MDM-Anbieter unterstützen bereits die Integration in AzureAD. Die MDM-Anbieter mit Azure AD-Unterstützung finden Sie im [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## Network

Bei diesem Setup erwarten wir, dass HoloLens 2-Geräte eine Verbindung mit dem Internet von allen verfügbaren open Wi-Fi herstellen. Da ein Benutzer die Netzwerkverbindung je nach Standort ändern muss, sollte er erfahren, wie er die Geräte von [HoloLens](https://docs.microsoft.com/hololens/hololens-network) mit dem WLAN verbindet.

Für Dynamics 365 Remote Assist gibt es eine Vielzahl von Netzwerkbedingungen, einschließlich Bandbreite, Latenz, Jitter und Paketverlust, die sich auf Ihre Videoanruferfahrung auswirken können. Obwohl Audio- und Videoanrufe in Umgebungen mit geringerer Bandbreite möglich sein können, kann es zu Funktionsbeeinträchtigungen kommen. Wenn Sie Dynamics 365 Remote Assist auf HoloLens verwenden, müssen Sie die Netzwerkanforderungen beachten:

**Minimum:** 1,5 MBit/s nach oben/unten sind für Peer-to-Peer-HD-Videoanrufe mit einer Auflösung von HD 1080p bei 30 fps erforderlich.

**Optimal:** Für Videoanrufe in Peer-zu-Peer-HD-Qualität mit einer Auflösung von HD 1080p sollten 4 bis 5 MBit/s nach oben/unten erwartet werden.

Weitere Informationen:

- [Netzwerkanforderungen](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Empfehlungen zur Netzwerkoptimierung](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### Optional: Verbinden Ihrer HoloLens mit VPN

Die Geräte, die mit diesem Handbuch verbunden sind, werden über das externe Cloudnetzwerk eine Verbindung mit dem Netzwerk herstellen. Es kann sein, dass Sie für den Zugriff auf Unternehmensressourcen,&#39;Ihre Geräte über VPN verbinden müssen. Es gibt verschiedene Möglichkeiten, Ihre Geräte mit VPN zu verbinden. Dabei kann der Endbenutzer über die Gerätebenutzeroberfläche eine Verbindung herstellen, oder die Geräte können verwaltet werden und das VPN-Profil von einer PPKG oder MDM empfangen. Die Einrichtung von VPN wird&#39;diesem Artikel nicht behandelt. Wenn Sie also mehr über die verschiedenen&#39;oder Möglichkeiten zum Verwalten von VPN erfahren möchten, besuchen Sie diese Handbücher, um Informationen zu [HoloLens](https://docs.microsoft.com/hololens/hololens-network#vpn) und VPN zu erhalten.

## Nächster Schritt

> [!div class="nextstepaction"]
> [Mit der Cloud verbundene Bereitstellung – Konfigurieren](hololens2-cloud-connected-configure.md)
