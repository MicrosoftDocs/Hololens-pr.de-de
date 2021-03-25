---
title: Bereitstellungshandbuch – Unternehmensverknte HoloLens 2 mit Dynamics 365-Anleitungen – Vorbereiten
description: Erfahren Sie, wie Sie sich auf die Registrierung von HoloLens 2-Geräten über ein unternehmensverbundenes Netzwerk mit Dynamics 365-Anleitungen vorbereiten.
keywords: HoloLens, Verwaltung, unternehmensgebunden, Dynamics 365-Anleitungen, AAD, Azure AD, MDM, Verwaltung mobiler Geräte
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2ab24aeac371b8d4a17d6121c3adf317cac7daf1
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448555"
---
# <a name="prepare---corporate-connected-guide"></a>Prepare – Corporate Connected Guide
## <a name="infrastructure-essentials"></a>Infrastructure Essentials
Für persönliche und Unternehmensbereitstellungsszenarien ist ein Mobile Device Management (MDM)-System die wesentliche Infrastruktur, die für die Bereitstellung und Verwaltung von Windows 10-Geräten erforderlich ist, insbesondere für HoloLens 2. Ein [Azure AD Premium-Abonnement](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium) wird als Identitätsanbieter empfohlen und **muss bestimmte** Funktionen unterstützen.

> [!NOTE]
> Obwohl HoloLens 2 wie ein mobiles Gerät bereitgestellt und verwaltet wird, wird es in der Regel als freigegebenes Gerät zwischen vielen Benutzern verwendet.

## <a name="azure-active-directory"></a>Azure Active Directory
AzureAD ist ein cloudbasierter Verzeichnisdienst zur Identitäts- und Zugriffsverwaltung. Organisationen, die Microsoft Office 365 oder Intune verwenden, verwenden bereits Azure AD, das drei Editionen enthält: Kostenlos, Premium P1 und Premium P2 (siehe [Azure Active Directory-Editionen](https://azure.microsoft.com/documentation/articles/active-directory-editions)). Alle Editionen unterstützen die Azure AD-Geräteregistrierung, Aber Premium P1 ist erforderlich, um die automatische MDM-Registrierung zu aktivieren, die wir später in diesem Handbuch verwenden werden.
> [!Important]
> Es ist wichtig, ein Azure AD zu haben, da HoloLens-Geräte die lokale AD-Verknüpfung nicht unterstützen. Wenn Sie noch nicht über eine Azure AD-Einrichtung verfügen, befolgen Sie die Anweisungen, um zu beginnen und einen neuen Mandanten [in Azure Active Directory zu erstellen.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## <a name="identity-management"></a>Identitätsverwaltung
In diesem Handbuch wird [die verwendete Identität](https://docs.microsoft.com/hololens/hololens-identity) Azure AD-Konten sein. Azure AD-Konten bieten verschiedene Vorteile, z. B.:
- Mitarbeiter verwenden ihr Azure AD-Konto, um das Gerät in Azure AD zu registrieren und können es automatisch bei der MDM-Lösung der Organisation registrieren (Azure AD+MDM – erfordert ein [Azure AD Premium-Abonnement](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium)).
- Azure AD-Konten verfügen über zusätzliche [Authentifizierungsoptionen](https://docs.microsoft.com/hololens/hololens-identity) [über Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). Zusätzlich zur Iris-Anmeldung können sich Benutzer von einem anderen Gerät anmelden oder FIDO-Sicherheitsschlüssel verwenden.

> [!WARNING] 
> Mitarbeiter können nur ein Konto verwenden, um ein Gerät zu **initialisieren,** daher ist es zwingend erforderlich, dass Ihre Organisation steuert, welches Konto zuerst aktiviert ist. Die Wahl des Kontos bestimmt, wer das Gerät kontrolliert und welche Verwaltungsfunktionen Ihnen zur Verfügung stehen.

## <a name="mobile-device-management"></a>Verwaltung mobiler Geräte
Microsoft Intune, Teil von Enterprise Mobility + Security, ist ein cloudbasiertes MDM-System, das Geräte verwaltet, die mit Ihrem Mandanten verbunden sind. Wie Office 365 verwendet Intune Azure AD für die Identitätsverwaltung, sodass Mitarbeiter dieselben Anmeldeinformationen verwenden, um Geräte in Intune zu registrieren, die sie zum Anmelden bei Office 365 verwenden. Intune unterstützt auch Geräte mit anderen Betriebssystemen, z. B. iOS und Android, um eine vollständige MDM-Lösung bereitzustellen. Im Sinne dieses Handbuchs konzentrieren wir uns auf die Verwendung von Intune für die Aktivierung einer Bereitstellung in Ihrem internen Netzwerk mit HoloLens 2.
> [!Important] 
> Die Verwaltung mobiler Geräte ist unerlässlich. Wenn Sie es noch nicht eingerichtet haben, folgen Sie diesem Leitfaden und Erste Schritte mit Intune.

> [!Important]
> Für die Verwendung von Leitfäden ist ein Azure AD-Konto erforderlich.

> [!Note] 
> Mehrere MDM-Systeme unterstützen Windows10, und die meisten unterstützen Bereitstellungsszenarien für persönliche und unternehmenseigene Geräte. MDM-Anbieter, die Windows 10 Holographic unterstützen, umfassen: AirWatch, MobileIron und andere. Die meisten branchenführenden MDM-Anbieter unterstützen bereits die Integration in AzureAD. Die aktuelle Liste der MDM-Anbieter, die Azure AD unterstützen, finden Sie in [Azure Marketplace.](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)

## <a name="network-access"></a>Netzwerkzugriff 
Dynamics 365 Guides ist eine cloudbasierte Anwendung. Wenn Ihr Netzwerkadministrator über eine Genehmigte Liste verfügt, muss er möglicherweise IP-Adressen und/oder Endpunkte hinzufügen, die zum Herstellen einer Verbindung mit den Dynamics 365-Servern erforderlich sind. [Erfahren Sie mehr über das Aufheben der Blockierung von IP-Adressen und URLs](https://docs.microsoft.com/power-platform/admin/online-requirements#ip-addresses-and-urls).

## <a name="certificates"></a>Zertifikate
Zertifikate verbessern die Sicherheit durch die Bereitstellung von Kontoauthentifizierung, Wi-Fi Authentifizierung, VPN-Verschlüsselung und SSL-Verschlüsselung von Webinhalten. Obwohl Administratoren Zertifikate auf Geräten manuell über Bereitstellungspakete verwalten können, ist es eine bewährte Methode, ihr MDM-System zu verwenden, um diese Zertifikate über den gesamten Lebenszyklus zu verwalten – von der Registrierung über die Verlängerung bis hin zum Widerruf. 

Ihr #A0 kann diese Zertifikate automatisch in den Zertifikatspeichern der Geräte bereitstellen, nachdem Sie sie registriert haben (solange Ihr #A1 das **Simple Certificate Enrollment Protocol (SCEP)** oder public key **Cryptography Standards #12 (PKCS#12)** unterstützt). [Erfahren Sie mehr über Zertifikattypen und Profile, die Sie mit Microsoft Intune verwenden.](https://docs.microsoft.com/mem/intune/protect/certificates-configure) MDM kann auch registrierte Clientzertifikate abfragen und löschen oder eine neue Registrierungsanforderung auslösen, bevor das aktuelle Zertifikat abgelaufen ist.
 
Wenn Ihre MDM-Systeme bereits für Zertifikate konfiguriert sind, verweisen Sie auf Zertifikate und Netzwerkprofile für [HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network) vorbereiten, um mit der Bereitstellung von Zertifikaten und Profilen für Ihre HoloLens 2-Geräte zu beginnen.

## <a name="scep"></a>SCEP

Die folgenden Dienste sind für die SCEP-Bereitstellung erforderlich, mit Ausnahme des Webanwendungsproxyservers.
- [Zertifizierungsstelle](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [Rolle "NDES Server"](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune Connector](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

Sie müssen Ihre NDES-URL auch extern in Ihrem Unternehmensnetzwerk mithilfe des [Azure AD-Anwendungsproxys oder Webzugriffsproxys veröffentlichen.](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application) Sie können auch einen anderen Reverseproxy Ihrer Wahl verwenden.

![SCEP-Datenfluss](./images/hololens2-scep-info-flow.png)

Wenn Ihr Netzwerk SCEP nicht bereits unterstützt oder Sie nicht sicher sind, ob Ihr Netzwerk ordnungsgemäß für SCEP mit Intune eingerichtet ist, verweisen Sie auf Konfigurieren der Infrastruktur, um SCEP mit Intune zu [unterstützen.](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure)

Wenn Ihre Infrastruktur scEP bereits unterstützt, [](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-certificate-profiles) müssen Sie ein Profil für jedes SCEP-Zertifikat erstellen, das von HoloLens 2 verwendet wird. [](https://docs.microsoft.com/mem/intune/protect/certificates-profile-scep) Wenn Sie Probleme mit SCEP haben, verwenden Sie die Problembehandlung bei der Verwendung von SCEP-Zertifikatprofilen, um Zertifikate [mit Microsoft Intune bereitzustellen.](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)

## <a name="pkcs"></a>PKCS
Intune unterstützt auch die Verwendung privater und öffentlicher #A0 (Public Key Pair). Referenz [Verwenden Sie private und öffentliche Schlüsselzertifikate in Microsoft Intune,](https://docs.microsoft.com/mem/intune/protect/certificates-pfx-configure) um weitere Informationen zu erhalten.

## <a name="proxy"></a>Proxy
Die meisten Unternehmensintranetnetzwerke nutzen einen Proxy, um externen Datenverkehr zu verwalten. Mit HoloLens 2 können Sie einen Proxyserver für Ethernet-, Wi-Fi und VPN-Verbindungen konfigurieren.

Es gibt einige verschiedene Arten von Proxy und Möglichkeiten zum Konfigurieren von Proxy. Für die Zwecke dieses Handbuchs entscheiden wir uns dafür, wlan-Proxy zu wählen, über PAC-URL festgelegt und **über MDM bereitgestellt zu werden.** Dies bietet die Vorteile der automatischen Bereitstellung über MDM, die Möglichkeit, die PAC-Datei zu aktualisieren, anstatt eine Server:Port-Konfiguration zu verwenden, und schließlich die Verwendung von Wi-Fi-Proxy, um proxy so zu konfigurieren, dass er nur auf eine einzelne Wi-Fi-Verbindung angewendet wird, sodass die Geräte weiterhin verwendet werden können, wenn sie an einem anderen Standort verbunden sind. 


Weitere Informationen zu Proxyeinstellungen für Windows 10 finden Sie unter [Create a Wi-Fi profile for devices in Microsoft Intune - Azure](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure).

## <a name="line-of-business-apps"></a>Business-Apps 
Während mehrere Apps über den Microsoft Store installiert werden können, verfügen Sie wahrscheinlich über Eine eigene benutzerdefinierte App, die Sie speziell für die Verwendung in mixed reality erstellt haben. Diese benutzerdefinierten Apps, die in Ihrer Organisation für Ihr Unternehmen verteilt werden, werden branchenspezifische Apps genannt.
  
Es gibt mehrere Möglichkeiten zum Bereitstellen von Anwendungen auf HoloLens 2-Geräten. Apps können direkt über MDM, den Microsoft Store für Unternehmen (MSfB) oder über ein Bereitstellungspaket bereitgestellt werden. Im Interesse dieses Handbuchs stellen wir Apps über MDM mithilfe der erforderlichen App-Installation zur Verfügung. Dadurch können Ihre Branchen-Apps automatisch auf Ihre HoloLens-Geräte heruntergeladen werden, sobald sie die Registrierung abgeschlossen haben.

Für diejenigen von Ihnen, die nicht über eine eigene Branchenanwendung verfügen, stellen wir eine Beispiel-App zum Testen dieses Bereitstellungsflusses zur Verfügung. Diese App ist die [MRTK-Beispiel-App](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) und wurde bereits vorkonfeiliert und verpackt, um den Nachweis des Konzepts zu testen.
 
Weitere Details zur App-Bereitstellung finden Sie unter [App Management: Overview](https://docs.microsoft.com/hololens/app-deploy-overview).

> [!NOTE]
> HoloLens 2 unterstützt nur die Ausführung von UWP ARM64-Apps.

## <a name="guides-playbook"></a>Anleitungen für Playbook
Handbücher verwenden eine Microsoft Dataverse-Umgebung als Datenspeicher für Ihre Guides-Apps. Es ist wichtig, das größere Bild zu verstehen, wie Ihre Dataverse-Umgebung mit Ihren Guides-Apps und Ihrem Mandanten interagiert. In diesem Handbuch wird nicht beschrieben, wie Sie Ihre Dataverse verwalten. Lesen Sie jedoch grundlegende Konzepte für die Bereitstellung von [Dynamics 365 Guides - Dynamics 365 Mixed Reality](https://docs.microsoft.com/dynamics365/mixed-reality/guides/admin-deployment-playbook).

## <a name="next-step"></a>Nächster Schritt 
> [!div class="nextstepaction"]
> [Unternehmensverkn nnte Bereitstellung – Konfigurieren](hololens2-corp-connected-configure.md)