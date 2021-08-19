---
title: Bereitstellen von mit der Cloud verbundenen HoloLens 2 für externe Clients
description: Bereitstellungshandbuch für HoloLens 2 für externe Clients (mit Remoteunterstützung als Beispiel)
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/6/2021
ms.custom: ''
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: 476ea17dfad114741191595fa0ce3bd1c7bca28d
ms.sourcegitcommit: 7b666c63a0367032a4a3f366b7f9029b2613e345
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2021
ms.locfileid: "122401132"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>Bereitstellen von mit der Cloud verbundenen HoloLens 2 für externe Clients

Dieser Leitfaden ist eine Ergänzung zum [Cloud Connected Deployment Guide](hololens2-cloud-connected-overview.md). Sie wird in Situationen verwendet, in denen Ihre Organisation HoloLens 2 Geräte zur kurz- oder langfristigen Verwendung an die Einrichtung eines externen Clients versenden möchte. Der externe Client meldet sich mit den von Ihrer Organisation bereitgestellten Anmeldeinformationen beim HoloLens 2 Gerät an und verwendet [Remote Assist,](/dynamics365/mixed-reality/remote-assist/ra-overview) um Sich an Ihre Experten zu wenden. Dieser Leitfaden enthält [allgemeine HoloLens 2 Bereitstellungsempfehlungen,](#general-deployment-recommendations) die für die meisten externen HoloLens 2 Bereitstellungsszenarien gelten, sowie [allgemeine Bedenken,](#common-external-client-deployment-concerns) die Kunden bei der Bereitstellung von Remote Assist für die externe Verwendung haben. 

## <a name="prerequisites"></a>Voraussetzungen

Die folgende Infrastruktur sollte gemäß dem Leitfaden für die [cloudgebundene Bereitstellung](hololens2-cloud-connected-overview.md) vorhanden sein, um die HoloLens 2 extern bereitzustellen.

- Azure AD Beitreten zur automatischen MDM-Registrierung – MDM-verwaltet (Intune)
- Benutzer melden sich mit ihrem eigenen Unternehmenskonto (Azure AD) an.
    - Einzelne oder mehrere Benutzer pro Gerät werden unterstützt.

### <a name="remote-assist-licensing-and-requirements"></a>Remote Assist Lizenzierung und Anforderungen

- Azure AD-Konto (erforderlich für den Erwerb des Abonnements und die Zuweisung von Lizenzen)
- [Remote Assist-Abonnement](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (oder [Remote Assist-Testversion](/dynamics365/mixed-reality/remote-assist/try-remote-assist))

Weitere [Informationen zu Remote Assist](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)finden Sie unter .

### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist-Benutzer

- Remote Assist-Lizenz
- Netzwerkverbindung

### <a name="microsoft-teams-user"></a>Microsoft Teams-Benutzer

- Microsoft Teams oder [Teams Freemium](https://products.office.com/microsoft-teams/free)
- Netzwerkverbindungen

## <a name="general-deployment-recommendations"></a>Allgemeine Bereitstellungsempfehlungen

Für die Bereitstellung externer HoloLens 2 werden die folgenden Schritte empfohlen:

1. Verwenden Sie die [neueste HoloLens Betriebssystemversion](https://aka.ms/hololens2download) als Baselinebuild.
1. Weisen Sie benutzer- oder gerätebasierte Lizenzen zu, indem Sie die folgenden Schritte ausführen:
    1. [Erstellen Sie eine Gruppe in AAD, und fügen Sie Mitglieder](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) für HoloLens/RA-Benutzer hinzu.
    1. Weisen Sie dieser Gruppe [gerätebasierte oder benutzerbasierte Lizenzen](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) zu.
    1. (Optional) Zielgruppen für [Mdm-Richtlinien (Mobile Device Management).](hololens-enroll-mdm.md)

1. Verbinden Sie AAD-Geräte mit Ihrem Mandanten, [registrieren Sie sich automatisch,](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)und konfigurieren Sie über [Autopilot](/hololens/hololens2-autopilot). Weitere Informationen finden Sie unter [Gerätebesitzer.](/hololens/security-adminless-os#device-owner)
    1. Der erste Benutzer auf dem Gerät ist der Gerätebesitzer.
    1. Wenn das Gerät in AAD eingebunden ist, wird der Benutzer, der die Verknüpfung durchgeführt hat, zum Gerätebesitzer.
    
1. [Der Mandant sperrt](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) das Gerät so, dass es nur von Ihrem Mandanten eingebunden werden kann.
    1. Siehe auch [Mandantensperr-CSP.](/windows/client-management/mdm/tenantlockdown-csp)

1. [Konfigurieren Sie den Kioskmodus mit global zugewiesenem Zugriff.](/hololens/hololens-global-assigned-access-kiosk)

1. Deaktivieren Sie die folgenden (optionalen) Funktionen:
    1. Hier können Sie das Gerät in den [Entwicklermodus](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)versetzen.
    1. Die Möglichkeit, die HoloLens mit einem PC zum Kopieren des Datums zu verbinden, [deaktiviert USB.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Wenn Sie USB nicht deaktivieren möchten, aber ein Bereitstellungspaket über USB auf das Gerät anwenden möchten, befolgen Sie die Anweisungen unter Zulassen der [Installation des Bereitstellungspakets.](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Verwenden Sie [Windows Defender Application Control (WDAC),](/hololens/windows-defender-application-control-wdac) um Apps auf dem HoloLens 2 Gerät zuzulassen oder zu blockieren.
1. Aktualisieren Sie Remote Assist im Rahmen des Setups auf die neueste Version. Betrachten Sie die folgenden beiden Optionen:
    1. Wechseln Sie zu Windows **Microsoft Store --> Remote Assist --> und App aktualisieren.**
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) , das automatische App-Updates zulässt, ist standardmäßig aktiviert. Lassen Sie das Gerät angeschlossen, um Updates zu erhalten.
1. [Deaktivieren Sie alle Einstellungsseiten](/hololens/settings-uri-list) mit Ausnahme der Netzwerkeinstellungen, damit Benutzer eine Verbindung mit Gastnetzwerken an Clientstandorten herstellen können.
1. [Verwalten von HoloLens-Updates](/hololens/hololens-updates)
    1. Option zum Steuern von [Betriebssystemupdates](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) oder zulassen des freien Flusses.
1. Legen Sie [allgemeine Geräteeinschränkungen fest.](/hololens/hololens-common-device-restrictions)

Jetzt können Ihre externen Clients ihre HoloLens 2 verwenden.

## <a name="common-external-client-deployment-concerns"></a>Allgemeine Probleme bei der Bereitstellung externer Clients

- [Sicherstellen, dass Clients nicht miteinander kommunizieren können](#ensure-that-external-clients-cant-communicate-with-one-another)
- [Sicherstellen, dass Clients nicht auf Unternehmensressourcen zugreifen können](#ensure-that-clients-wont-have-access-to-company-resources)
- [Ausblenden oder Einschränken von Apps](#hidden-or-restricted-apps)
- [Verwalten von Kennwörtern für Ihre Clients](#password-management-for-your-clients) 
- [Sicherstellen, dass Clients nicht auf den Chatverlauf zugreifen können](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>Sicherstellen, dass externe Clients nicht miteinander kommunizieren können

Remote Assist HoloLens HoloLens Aufrufe werden nicht unterstützt. Clients können nach suchen, aber nicht miteinander kommunizieren. [Informationsbarrieren in Microsoft 365](/microsoft-365/compliance/information-barriers) können weiter einschränken, mit wem ein Client suchen und aufrufen kann. Eine weitere Option ist die Verwendung [Microsoft Teams Bereichsverzeichnissuche.](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Da einmaliges Anmelden aktiviert ist, ist es wichtig, den Browser mit [Windows Defender Application Control (WDAC)](/hololens/windows-defender-application-control-wdac)zu deaktivieren. Wenn ein externer Client den Browser öffnet und die Webversion von Teams verwendet, hat der Client Zugriff auf Ihren Chatverlauf.

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>Sicherstellen, dass Clients keinen Zugriff auf Unternehmensressourcen haben

Es gibt zwei Optionen zu berücksichtigen.

Die erste Option ist ein mehrschichtiger Ansatz:

1. Weisen Sie nur Lizenzen zu, die der Benutzer benötigt. Wenn Sie OneDrive, Outlook, SharePoint, Yammer usw. nicht zuweisen, hat der Benutzer keinen Zugriff auf diese Ressourcen. Die einzigen Lizenzen, die Benutzer benötigen, sind Remote Assist, Intune und AAD-Lizenzen, um zu beginnen.
1. Blockieren Sie Apps (z. B. E-Mails), auf die Clients nicht zugreifen sollen (siehe [Apps sind ausgeblendet oder eingeschränkt).](#apps are hidden or restricted)
1. Geben Sie Benutzernamen und Kennwörter nicht für Clients frei. Um sich beim HoloLens 2 anzumelden, sind eine E-Mail und eine numerische PIN erforderlich.

Die zweite Option besteht darin, einen separaten Mandanten zu erstellen, der Clients hostet (siehe Abbildung 1.1).

**Abbildung 1.1**

![Image des Dienstmandanten](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>Ausgeblendete oder eingeschränkte Apps

[Kioskmodus](/hololens/hololens-kiosk) und/oder [Windows Defender Anwendungssteuerung (WDAC)](/hololens/windows-efender-application-control-wdac) sind Optionen zum Ausblenden und/oder Einschränken von Anwendungen.

### <a name="password-management-for-your-clients"></a>Kennwortverwaltung für Ihre Clients

1. Entfernen Sie den Ablauf des Kennworts. Diese Option kann jedoch die Wahrscheinlichkeit erhöhen, dass ein Konto kompromittiert wird. NIST-Kennwortempfehlung: Kennwörter alle 30 bis 90 Tage ändern.
1. Verlängern Sie den Ablauf des Kennworts für HoloLens 2 Geräte auf mehr als 90 Tage.
1. Die Geräte sollten an Ihre Organisation zurückgegeben werden, um die Kennwörter zu ändern. Diese Option kann jedoch Probleme verursachen, wenn die Geräte voraussichtlich mehr als 90 Tage im Werk des Clients sind.  
1. Setzen Sie für Geräte, die an mehrere Clients gesendet werden, Kennwörter zurück, bevor Sie das Gerät an Clients senden.

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>Sicherstellen, dass Clients keinen Zugriff auf den Chatverlauf haben

Remote Assist löscht den Chatverlauf nach jeder Sitzung. Der Chatverlauf ist jedoch für Microsoft Teams Benutzer verfügbar.

> [!NOTE]
> Da einmaliges Anmelden aktiviert ist, ist es wichtig, den Browser mit [Windows Defender Application Control (WDAC)](/hololens/windows-defender-application-control-wdac)zu deaktivieren.  Wenn ein externer Client den Browser öffnet und die Webversion von Teams verwendet, hat der Client Zugriff auf den Anruf-/Chatverlauf.
