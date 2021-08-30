---
title: Bereitstellungshandbuch – Unternehmens verbundene HoloLens 2 mit Dynamics 365 Guides – Vorbereiten
description: Erfahren Sie, wie Sie sich auf die Registrierung HoloLens 2 Geräten über ein verbundenes Unternehmensnetzwerk mit Dynamics 365 Guides.
keywords: HoloLens, Verwaltung, unternehmens verbunden, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Geräteverwaltung
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
ms.openlocfilehash: 5d8fc2eb0a8dafaae0e1b222b7451877975cf90b
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190207"
---
# <a name="prepare---corporate-connected-guide"></a>Prepare – Corporate Connected Guide (Vorbereiten – Leitfaden für verbundene Unternehmen)
## <a name="infrastructure-essentials"></a>Infrastructure Essentials
Sowohl für private als auch für Unternehmensbereitstellungsszenarien ist ein Mobile Geräteverwaltung-System (MDM) die wesentliche Infrastruktur, die zum Bereitstellen und Verwalten von Windows 10-Geräten erforderlich ist, insbesondere HoloLens 2. Ein [Azure AD Premium abonnement](/azure/active-directory/fundamentals/active-directory-get-started-premium) wird als Identitätsanbieter empfohlen und **ist erforderlich,** um bestimmte Funktionen zu unterstützen.

> [!NOTE]
> Obwohl die HoloLens 2 wie ein mobiles Gerät bereitgestellt und verwaltet wird, wird sie in der Regel als gemeinsam genutztes Gerät von vielen Benutzern verwendet.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD ist ein cloudbasierter Verzeichnisdienst zur Identitäts- und Zugriffsverwaltung. Organisationen, die Microsoft Office 365 oder Intune verwenden, verwenden bereits Azure AD mit drei Editionen: Free, Premium P1 und Premium P2 (siehe [Azure Active Directory Editionen).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Alle Editionen unterstützen Azure AD Geräteregistrierung, aber Premium P1 ist erforderlich, um die automatische MDM-Registrierung zu aktivieren, die wir später in diesem Handbuch verwenden werden.
> [!Important]
> Es ist wichtig, dass Sie über Azure AD verfügen, da HoloLens-Geräte keine lokale AD-Verknüpfung unterstützen. Wenn Sie noch nicht über eine Azure AD verfügen, befolgen Sie die Anweisungen zum Einstieg und Erstellen eines neuen Mandanten [in Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## <a name="identity-management"></a>Identitätsverwaltung
In diesem Leitfaden wird [die verwendete Identität](/hololens/hololens-identity) Azure AD verwendet. Es gibt mehrere Vorteile für Azure AD, z. B.:

- Mitarbeiter verwenden ihr Azure AD-Konto, um das Gerät in Azure AD zu registrieren, und können es automatisch bei der MDM-Lösung der Organisation registrieren (Azure AD+MDM – erfordert ein [Azure AD Premium-Abonnement).](/azure/active-directory/fundamentals/active-directory-get-started-premium)
- Azure AD Konten verfügen über zusätzliche [Authentifizierungsoptionen](/hololens/hololens-identity) [über Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification). Zusätzlich zur Iris-Anmeldung können sich Benutzer von einem anderen Gerät aus anmelden oder FIDO-Sicherheitsschlüssel verwenden.

> [!WARNING] 
> Mitarbeiter können nur ein Konto verwenden, um ein Gerät zu initialisieren. Daher ist es zwingend erforderlich, dass Ihre Organisation steuert, **welches Konto zuerst aktiviert wird.** Die Wahl des Kontos bestimmt, wer das Gerät kontrolliert und welche Verwaltungsfunktionen Ihnen zur Verfügung stehen.

## <a name="mobile-device-management"></a>Verwaltung mobiler Geräte
Microsoft Intune, teil Enterprise Mobility + Security, ist ein cloudbasiertes MDM-System, das Geräte verwaltet, die mit Ihrem Mandanten verbunden sind. Wie Office 365 verwendet Intune Azure AD für die Identitätsverwaltung, sodass Mitarbeiter dieselben Anmeldeinformationen verwenden, um Geräte bei Intune zu registrieren, die sie für die Anmeldung bei Office 365. Intune unterstützt auch Geräte, auf denen andere Betriebssysteme wie iOS und Android ausgeführt werden, um eine vollständige MDM-Lösung zu bieten. Im Rahmen dieses Leitfadens konzentrieren wir uns auf die Verwendung von Intune, um eine Bereitstellung in Ihrem internen Netzwerk mit HoloLens 2.
> [!Important] 
> Mobile Apps müssen unbedingt Geräteverwaltung. Wenn Sie dies noch nicht eingerichtet haben, befolgen Sie diese Anleitung und erste Schritte mit Intune.

> [!Important]
> Für die Verwendung von Handbüchern ist ein Azure AD erforderlich.

> [!Note] 
> Mehrere MDM-Systeme unterstützen Windows 10, und die meisten unterstützen Bereitstellungsszenarien für persönliche und unternehmenseigene Geräte. MDM-Anbieter, die Windows 10 Holographic unterstützen, sind u.a. AirWatch, MobileIron. Die meisten branchenführenden MDM-Anbieter unterstützen bereits die Integration in Azure AD. Sie finden die aktuelle Liste der MDM-Anbieter, die Azure AD unterstützen, in [Azure Marketplace.](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)

## <a name="network-access"></a>Netzwerkzugriff 
Dynamics 365 Guides ist eine cloudbasierte Anwendung. Wenn Ihr Netzwerkadministrator über eine Liste mit Genehmigungen verfügt, muss er möglicherweise IP-Adressen und/oder Endpunkte hinzufügen, die zum Herstellen einer Verbindung mit den Dynamics 365-Servern erforderlich sind. [Erfahren Sie mehr über das Entsperren von IP-Adressen und URLs.](/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>Zertifikate
Zertifikate tragen zur Verbesserung der Sicherheit bei, indem sie Kontoauthentifizierung, Wi-Fi Authentifizierung, VPN-Verschlüsselung und SSL-Verschlüsselung von Webinhalten bereitstellen. Obwohl Administratoren Zertifikate auf Geräten manuell über Bereitstellungspakete verwalten können, ist es eine bewährte Methode, ihr MDM-System zu verwenden, um diese Zertifikate während ihres gesamten Lebenszyklus zu verwalten – von der Registrierung über die Verlängerung bis hin zur Sperrung. 

Ihr MDM-System kann diese Zertifikate automatisch in den Zertifikatspeichern der Geräte bereitstellen, nachdem Sie sie registriert haben (solange Ihr MDM-System die **Simple Certificate Enrollment-Protokoll (SCEP)** oder Public **Key Cryptography Standards #12 (PKCS #12) unterstützt).** [Erfahren Sie mehr über Zertifikattypen und Profile, die Sie mit Microsoft Intune.](/mem/intune/protect/certificates-configure) MDM kann auch registrierte Clientzertifikate abfragen und löschen oder eine neue Registrierungsanforderung auslösen, bevor das aktuelle Zertifikat abgelaufen ist.

Wenn Ihre MDM-Systeme bereits für Zertifikate konfiguriert sind, helfen Ihnen die Informationen unter Vorbereiten von Zertifikaten und Netzwerkprofilen für [HoloLens 2 weiter,](/hololens/hololens-certificates-network) um mit der Bereitstellung von Zertifikaten und Profilen für Ihre HoloLens 2 beginnen.

## <a name="scep"></a>SCEP

Die folgenden Dienste sind für die SCEP-Bereitstellung erforderlich, mit Ausnahme von Web Anwendungsproxy Server.

- [Zertifizierungsstelle](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES-Serverrolle](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune Connector](/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

Sie müssen ihre NDES-URL auch extern in Ihrem Unternehmensnetzwerk veröffentlichen, indem Sie Azure AD Anwendungsproxy oder [Webzugriff Proxy verwenden.](/azure/active-directory/manage-apps/application-proxy-add-on-premises-application) Sie können auch einen anderen Reverseproxy Ihrer Wahl verwenden.

![SCEP-Datenfluss.](./images/hololens2-scep-info-flow.png)

Wenn Ihr Netzwerk SCEP nicht bereits unterstützt oder Sie nicht sicher sind, ob Ihr Netzwerk ordnungsgemäß für SCEP mit Intune eingerichtet ist, finden Sie weitere Informationen unter Konfigurieren der Infrastruktur zur Unterstützung von [SCEP mit Intune.](/mem/intune/protect/certificates-scep-configure)

Wenn Ihre Infrastruktur SCEP bereits unterstützt, [](/mem/configmgr/protect/deploy-use/create-certificate-profiles) müssen Sie ein Profil für jedes SCEP-Zertifikat erstellen, das HoloLens 2 verwendet. [](/mem/intune/protect/certificates-profile-scep) Wenn Sie Probleme mit SCEP haben, verwenden Sie Problembehandlung bei der Verwendung von SCEP-Zertifikatprofilen zum Bereitstellen [von Zertifikaten mit Microsoft Intune](/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles).

## <a name="pkcs"></a>PKCS
Intune unterstützt auch die Verwendung von PKCS-Zertifikaten (privates und öffentliches Schlüsselpaar). Weitere Informationen finden Sie unter Use [private and public key certificates in Microsoft Intune](/mem/intune/protect/certificates-pfx-configure) (Verwenden von Zertifikaten mit privatem und öffentlichem Schlüssel in der Microsoft Intune).

## <a name="proxy"></a>Proxy
Die meisten Intranetnetzwerke des Unternehmens nutzen einen Proxy, um externen Datenverkehr zu verwalten. Mit HoloLens 2 können Sie einen Proxyserver für Ethernet-, Wi-Fi- und VPN-Verbindungen konfigurieren.

Es gibt verschiedene Proxytypen und Möglichkeiten zum Konfigurieren des Proxys. Für die Zwecke dieses Handbuchs entscheiden wir uns für **wlan-proxy,** set via PAC URL und deployed via MDM . Dies hat die Vorteile der automatischen Bereitstellung über MDM, die Möglichkeit, die PAC-Datei zu aktualisieren, anstatt eine Server:Port-Konfiguration zu verwenden, und schließlich die Verwendung des Wi-Fi-Proxys, um den Proxy so zu konfigurieren, dass er nur auf eine einzelne Wi-Fi-Verbindung angewendet wird, sodass die Geräte weiterhin verwendet werden können, wenn sie an einem anderen Standort verbunden sind.

Weitere Informationen zu Proxyeinstellungen für Windows 10 finden Sie unter [Erstellen eines Wi-Fi-Profils](/mem/intune/configuration/wi-fi-settings-configure)für Geräte in Microsoft Intune – Azure .

## <a name="line-of-business-apps"></a>Line of Business-Apps 
Zwar können mehrere Apps über die Microsoft Store installiert werden, aber wahrscheinlich verfügen Sie über Eine eigene benutzerdefinierte App, die Sie speziell für die Verwendung in Mixed Reality erstellt haben. Diese benutzerdefinierten Apps, die in Ihrer gesamten Organisation für Ihr Unternehmen verteilt sind, werden als Branchen-Apps bezeichnet.
  
Es gibt mehrere Möglichkeiten zum Bereitstellen von Anwendungen auf HoloLens 2 Geräten. Apps können direkt über MDM, den Microsoft Store für Unternehmen (MSfB) oder per Sideloaded über ein Bereitstellungspaket bereitgestellt werden. Im Rahmen dieses Leitfadens stellen wir Apps über MDM mithilfe der erforderlichen App-Installation zur Verfügung. Dadurch können Ihre BRANCHEN-Apps automatisch auf Ihre HoloLens heruntergeladen werden, sobald sie die Registrierung abgeschlossen haben.

Für diejenigen von Ihnen, die nicht über Eine eigene BRANCHEN verfügen, stellen wir eine Beispiel-App zum Testen dieses Bereitstellungsablaufs zur Verfügung. Diese App ist die [MRTK-Beispiel-App](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) und wurde bereits vorgefertigt und gepackt, um den Proof of Concept zu testen.

Weitere Informationen zur App-Bereitstellung finden Sie unter [App-Verwaltung: Übersicht](/hololens/app-deploy-overview).

> [!NOTE]
> HoloLens 2 unterstützt nur die Ausführung von UWP ARM64-Apps.

## <a name="guides-playbook"></a>Guides Playbook
Leitfäden verwenden eine Microsoft Dataverse-Umgebung als Datenspeicher für Ihre Guides-Apps. Es ist wichtig, den größeren Überblick darüber zu verstehen, wie Ihre Dataverse-Umgebung mit Ihren Guides-Apps und Ihrem Mandanten interagiert. In diesem Leitfaden wird die Verwaltung Ihrer Datenverse nicht weiterberückigt, aber lesen Sie grundlegende Konzepte für die Bereitstellung von Dynamics 365 Guides – [Dynamics 365 Mixed Reality](/dynamics365/mixed-reality/guides/admin-deployment-playbook).

## <a name="next-step"></a>Nächster Schritt 
> [!div class="nextstepaction"]
> [Unternehmens verbundene Bereitstellung: Konfigurieren](hololens2-corp-connected-configure.md)