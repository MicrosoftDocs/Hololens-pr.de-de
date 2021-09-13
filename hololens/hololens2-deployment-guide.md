---
title: Bereitstellen von cloudbasierten HoloLens 2 auf externen Clients
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
ms.openlocfilehash: d5cd9c380e0d276f0a8aa9efac14cf44885446e5
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032682"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>Bereitstellen von cloudbasierten HoloLens 2 auf externen Clients

Dieser Leitfaden ist eine Ergänzung zum [Cloud Connected Deployment Guide](hololens2-cloud-connected-overview.md). Sie wird in Situationen verwendet, in denen Ihre Organisation HoloLens 2 zur kurz- oder langfristigen Verwendung an die Einrichtung eines externen Clients liefern möchte. Der externe Client anmeldet sich mit HoloLens 2 Anmeldeinformationen, die [](/dynamics365/mixed-reality/remote-assist/ra-overview) von Ihrer Organisation bereitgestellt werden, beim Remote Assist, um sich mit Ihren Experten in Verbindung zu setzen. Dieser Leitfaden enthält allgemeine empfehlungen [HoloLens 2](#general-deployment-recommendations) Bereitstellung, die für die meisten [](#common-external-client-deployment-concerns) externen HoloLens 2-Bereitstellungsszenarien gelten, sowie allgemeine Bedenken, die Kunden bei der Bereitstellung von Remote Assist für die externe Verwendung haben. 

## <a name="prerequisites"></a>Voraussetzungen

Die folgende Infrastruktur sollte im Leitfaden für die cloudbasierte Bereitstellung bereitgestellt werden, [um](hololens2-cloud-connected-overview.md) die HoloLens 2 bereitzustellen.

- Azure AD bei der automatischen MDM-Registrierung – MDM-verwaltet (Intune)
- Benutzer melden sich mit ihrem eigenen Unternehmenskonto an (Azure AD)
    - Einzelne oder mehrere Benutzer pro Gerät werden unterstützt.

### <a name="remote-assist-licensing-and-requirements"></a>Remote Assist Lizenzierung und Anforderungen

- Azure AD-Konto (erforderlich für den Erwerb des Abonnements und die Zuweisung von Lizenzen)
- [Remote Assist-Abonnement](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (oder [Remote Assist-Testversion](/dynamics365/mixed-reality/remote-assist/try-remote-assist))

Weitere [Informationen finden Sie unter Remote Assist](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).

### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist-Benutzer

- Remote Assist-Lizenz
- Netzwerkverbindung

### <a name="microsoft-teams-user"></a>Microsoft Teams-Benutzer

- Microsoft Teams oder [Teams Freemium](https://products.office.com/microsoft-teams/free)
- Netzwerkverbindungen

## <a name="general-deployment-recommendations"></a>Allgemeine Bereitstellungsempfehlungen

Es werden die folgenden Schritte für die Bereitstellung externer HoloLens 2 empfohlen:

1. Verwenden Sie [das neueste HoloLens Betriebssystemversion](https://aka.ms/hololens2download) als Baseline-Build.
1. Weisen Sie benutzer- oder gerätebasierte Lizenzen zu, indem Sie die folgenden Schritte ausführen:
    1. [Erstellen Sie eine Gruppe in AAD, und fügen Sie Mitglieder](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) für HoloLens/RA-Benutzer hinzu.
    1. [Weisen Sie dieser Gruppe gerätebasierte oder benutzerbasierte](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) Lizenzen zu.
    1. (Optional) Zielgruppen für [MDM-Richtlinien (Mobile Device](hololens-enroll-mdm.md) Management).

1. Verbinden Sie AAD-Geräte mit Ihrem Mandanten, [registrieren](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)Sie automatisch , und konfigurieren Sie über [Autopilot](/hololens/hololens2-autopilot). Weitere Informationen finden Sie unter [Gerätebesitzer.](/hololens/security-adminless-os#device-owner)
    1. Der erste Benutzer auf dem Gerät ist der Gerätebesitzer.
    1. Wenn das Gerät mit AAD verbunden ist, wird der Benutzer, der die Verknüpfung durchgeführt hat, zum Gerätebesitzer.
    
1. [Der Mandant](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) sperrt das Gerät so, dass es nur von Ihrem Mandanten verbunden werden kann.
    1. Siehe auch [Mandantensperr-CSP.](/windows/client-management/mdm/tenantlockdown-csp)

1. [Konfigurieren Sie den Kioskmodus mit global zugewiesenem Zugriff.](/hololens/hololens-global-assigned-access-kiosk)

1. Deaktivieren Sie die folgenden (optionalen) Funktionen:
    1. Hier können Sie das Gerät in den [Entwicklermodus bringen.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Deaktivieren Sie USB, um HoloLens Verbindung mit einem PC zum Kopieren des Datums [herzustellen.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Wenn Sie USB nicht deaktivieren möchten, aber die Möglichkeit haben möchten, ein Bereitstellungspaket über USB auf das Gerät anzuwenden, befolgen Sie die Anweisungen zum Zulassen der Installation von [Bereitstellungspaketen.](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Verwenden [Windows Defender Application Control (WDAC),](/hololens/windows-defender-application-control-wdac) um Apps auf dem gerät zu HoloLens 2 blockieren.
1. Aktualisieren Remote Assist im Rahmen des Setups auf die neueste Version. Ziehen Sie die folgenden beiden Optionen in Betracht:
    1. Wechseln Sie Windows **Microsoft Store --> Remote Assist --> und App aktualisieren.**
    1. [ApplicationManagement/AllowAppStoreAutoUpdate,](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) die automatische App-Updates zulässt, ist standardmäßig aktiviert. Halten Sie das Gerät angeschlossen, um Updates zu erhalten.
1. [Deaktivieren Sie alle Einstellungsseiten außer](/hololens/settings-uri-list) den Netzwerkeinstellungen, damit Benutzer eine Verbindung mit Gastnetzwerken an Clientstandorten herstellen können.
1. [Verwalten von HoloLens-Updates](/hololens/hololens-updates)
    1. Option zum [Steuern von Betriebssystemupdates](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) oder zum zulassen des freien Flusses.
1. Legen Sie [allgemeine Geräteeinschränkungen fest.](/hololens/hololens-common-device-restrictions)

Jetzt können Ihre externen Clients ihre eigenen HoloLens 2.

## <a name="common-external-client-deployment-concerns"></a>Allgemeine Probleme bei der Bereitstellung externer Clients

- [Sicherstellen, dass Clients nicht miteinander kommunizieren können](#ensure-that-external-clients-cant-communicate-with-one-another)
- [Sicherstellen, dass Clients nicht auf Unternehmensressourcen zugreifen können](#ensure-that-clients-wont-have-access-to-company-resources)
- [Ausblenden oder Einschränken von Apps](#hidden-or-restricted-apps)
- [Verwalten von Kennwörtern für Ihre Clients](#password-management-for-your-clients) 
- [Sicherstellen, dass Clients nicht auf den Chatverlauf zugreifen können](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>Sicherstellen, dass externe Clients nicht miteinander kommunizieren können

Remote Assist HoloLens to HoloLens-Aufrufe werden nicht unterstützt. Clients können suchen, aber nicht miteinander kommunizieren. [Informationsbarrieren in Microsoft 365](/microsoft-365/compliance/information-barriers) können weiter einschränken, mit wem ein Client suchen und aufrufen kann. Eine weitere Möglichkeit ist die Verwendung [Microsoft Teams Bereichsverzeichnissuche.](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Da einmaliges Anmelden aktiviert ist, ist es wichtig, den Browser mithilfe von Windows Defender [Application Control (WDAC) zu deaktivieren.](/hololens/windows-defender-application-control-wdac) Wenn ein externer Client den Browser öffnet und die Webversion von Teams verwendet, hat der Client Zugriff auf Ihren Chatverlauf.

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>Sicherstellen, dass Clients keinen Zugriff auf Unternehmensressourcen haben

Es gibt zwei Optionen, die Sie berücksichtigen sollten.

Die erste Option ist ein mehrschichtiger Ansatz:

1. Weisen Sie nur Lizenzen zu, die der Benutzer benötigt. Wenn Sie keine Ressourcen OneDrive, Outlook, SharePoint, Yammer usw. zuweisen, hat der Benutzer keinen Zugriff auf diese Ressourcen. Die einzigen Lizenzen, die Benutzer benötigen, sind Remote Assist, Intune und AAD-Lizenzen.
1. Blockieren Sie Apps (z. B. E-Mails), auf die Clients nicht zugreifen sollen (siehe [Apps sind ausgeblendet oder eingeschränkt).](#apps are hidden or restricted)
1. Geben Sie weder Benutzernamen noch Kennwörter für Clients weiter. Für die Anmeldung beim HoloLens 2 sind eine E-Mail und eine numerische PIN erforderlich.

Die zweite Option ist das Erstellen eines separaten Mandanten, der Clients hostet (siehe Abbildung 1.1).

**Abbildung 1.1**

![Dienst-Mandantenimage.](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>Ausgeblendete oder eingeschränkte Apps

[Kioskmodus](/hololens/hololens-kiosk) und/oder [Windows Defender Anwendungssteuerung (Application Control, WDAC)](/hololens/windows-efender-application-control-wdac) sind Optionen zum Ausblenden und/oder Einschränken von Anwendungen.

### <a name="password-management-for-your-clients"></a>Kennwortverwaltung für Ihre Clients

1. Kennwortablauf entfernen. Diese Option kann jedoch die Wahrscheinlichkeit erhöhen, dass ein Konto kompromittiert wird. NIST-Kennwortempfehlung: Kennwörter werden alle 30 bis 90 Tage geändert.
1. Verlängern Sie den Kennwortablauf für HoloLens 2 Geräte auf mehr als 90 Tage.
1. Die Geräte sollten an Ihre Organisation zurückgegeben werden, um die Kennwörter zu ändern. Diese Option kann jedoch Probleme verursachen, wenn erwartet wird, dass sich die Geräte mehr als 90 Tage im Werk des Clients befinden.  
1. Setzen Sie für Geräte, die an mehrere Clients gesendet werden, Kennwörter zurück, bevor Sie das Gerät an Clients versenden.

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>Sicherstellen, dass Clients keinen Zugriff auf den Chatverlauf haben

Remote Assist nach jeder Sitzung den Chatverlauf. Der Chatverlauf ist jedoch für benutzer Microsoft Teams verfügbar.

> [!NOTE]
> Da einmaliges Anmelden aktiviert ist, ist es wichtig, den Browser mithilfe von Windows Defender [Application Control (WDAC) zu deaktivieren.](/hololens/windows-defender-application-control-wdac)  Wenn ein externer Client den Browser öffnet und die Webversion von Teams verwendet, hat der Client Zugriff auf den Anruf-/Chatverlauf.
