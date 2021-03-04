---
title: Bereitstellungshandbuch für externe Clients
description: Bereitstellungshandbuch für HoloLens 2 für externe Clients (mit Remoteunterstützung als Beispiel)
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 56930ceea05cd5713b9c7eb57e0967a9d0cd4988
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385583"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>Bereitstellen von HoloLens2 auf externen Clients mit Remote Assist

Dieses Handbuch unterstützt IT-Experten bei der Bereitstellung von Microsoft HoloLens 2-Geräten in ihrer Organisation:

1. Cloud connect HoloLens 2-Geräte
1. HoloLens 2-Geräte zur Verwendung an externe Clients ausleihen
1. Sichere ausgeliehene Geräte

Dieses Handbuch enthält allgemeine [HoloLens 2-Bereitstellungsempfehlungen,](#general-deployment-recommendations-and-instructions) die für [](#common-concerns) die meisten HoloLens 2-Bereitstellungsszenarien gelten, sowie allgemeine Bedenken, die Kunden bei der Bereitstellung der Remoteunterstützung für die externe Verwendung haben.

## <a name="scenario-description"></a>Szenariobeschreibung

Für die Zwecke dieses Dokuments möchte contoso Company ein HoloLens 2-Gerät zur kurz- oder langfristigen Verwendung an das Werk eines externen Clients senden. Wenn der Client Unterstützungswartungsgeräte benötigt, loggt sich der Client mit den von Contoso Company bereitgestellten Anmeldeinformationen beim HoloLens 2-Gerät ein und kontaktiert die Experten des Contoso-Unternehmens mithilfe der Remoteunterstützung.

Weitere Informationen zur Remoteunterstützung finden Sie [hier.](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="requirements-for-this-scenario"></a>Anforderungen für dieses Szenario

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. Mobile Device Manager – z. B. [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. Remote Assist-Lizenz
    1. [Kaufen der Remoteunterstützung](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Remoteunterstützung für Testversionen](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Häufige Bedenken

- [Sicherstellen, dass externe Clients nicht miteinander kommunizieren können](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Sicherstellen, dass Clients keinen Zugriff auf Unternehmensressourcen haben](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Einschränken von Apps](#how-to-restrict-apps)
- [Verwalten von Kennwörtern](#how-to-manage-passwords)
- [Sicherstellen, dass Clients keinen Zugriff auf den Chatverlauf haben](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Sicherstellen, dass externe Clients nicht miteinander kommunizieren können

Da Remote assist HoloLens to HoloLens-Anrufe nicht unterstützt werden, können Clients suchen, aber nicht miteinander kommunizieren. Um weiter einzuschränken, nach wem Clients suchen und anrufen können, können  [Informationsbarrieren](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) einschränken, mit wem ein Client kommunizieren kann. Eine weitere option to consider is using [Scoped Directory Search](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Da einmaliges Anmelden aktiviert ist, ist es wichtig, den Browser mithilfe von [**WDAC zu deaktivieren.**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) Wenn ein externer Client den Browser öffnet und die Webversion von Teams verwendet, hat der Client Zugriff auf den Anruf-/Chatverlauf.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>Sicherstellen, dass Clients keinen Zugriff auf Unternehmensressourcen haben

Es gibt zwei Optionen, die Sie berücksichtigen sollten.

Die erste Option ist ein Mehrschichtansatz:

1. Weisen Sie nur Lizenzen zu, die der Benutzer benötigt. Wenn Sie dem Benutzer oneDrive, Outlook, SharePoint, Yammer usw. nicht zuweisen, hat er keinen Zugriff auf diese Ressourcen. Die einzigen Lizenzen, die die Benutzer benötigen, sind Remote assist-, Intune- und AAD-Lizenzen, um zu beginnen.
1. Blockieren von Apps (z. B. E-Mails), auf die Clients nicht zugreifen möchten (siehe [Einschränken von Apps](#how-to-restrict-apps)).
1. Geben Sie keine Benutzernamen oder Kennwörter für Clients an. Zum Anmelden bei HoloLens 2 ist eine E-Mail und eine numerische PIN erforderlich.

Die zweite Option besteht in der Erstellung eines separaten Mandanten, der Clients hostet (siehe Abbildung 1.1).

**Abbildung 1.1**

![Image des Dienst-Mandanten](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Einschränken von Apps

[Kioskmodus](https://docs.microsoft.com/hololens/hololens-kiosk) und/oder [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) sind Optionen zum Einschränken von Anwendungen.

### <a name="how-to-manage-passwords"></a>Verwalten von Kennwörtern

1. Entfernen des Kennwortablaufs. Dies erhöht jedoch die Wahrscheinlichkeit, dass ein Konto gefährdet wird. NIST-Kennwortempfehlung ist, Kennwörter alle 30-90 Tage zu ändern.
1. Verlängern Sie den Kennwortablauf für HoloLens 2-Geräte auf mehr als 90 Tage.
1. Die Geräte sollten an Contoso zurückgegeben werden, um die Kennwörter zu ändern. Dies kann jedoch zu Problemen führen, wenn erwartet wird, dass sich die Geräte mehr als 90 Tage im Werk des Kunden befinden.  
1. Für Geräte, die an mehrere Clients gesendet werden, setzen Sie Kennwörter zurück, bevor Sie das Gerät an Clients senden.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>Sicherstellen, dass Clients keinen Zugriff auf den Chatverlauf haben

Die Remoteunterstützung entfernt den Chatverlauf nach jeder Sitzung. Der Chatverlauf ist jedoch für den Microsoft Teams-Benutzer verfügbar.

> [!NOTE]
> Da einmaliges Anmelden aktiviert ist, ist es wichtig, den Browser mithilfe von [**WDAC zu deaktivieren.**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) Wenn ein externer Client den Browser öffnet und die Webversion von Teams verwendet, hat der Client Zugriff auf den Anruf-/Chatverlauf.

## <a name="general-deployment-recommendations-and-instructions"></a>Allgemeine Bereitstellungsempfehlungen und -anweisungen

Für HoloLens 2-Bereitstellungsschritte wird Folgendes empfohlen:

1. Verwenden Sie [die neueste HoloLens-Betriebssystemversion](https://aka.ms/hololens2download) als Basisversion.
1. Weisen Sie benutzer- oder gerätebasierte Lizenzen zu:
    1. Benutzer- und gerätebasierte Lizenzen führen beide die folgenden Schritte aus:
        1. [Erstellen Sie eine Gruppe in AAD, und fügen Sie Mitglieder](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) für HoloLens/RA-Benutzer hinzu.
        1. [Weisen Sie dieser](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) Gruppe geräte- oder benutzerbasierte Lizenzen zu.
        1. (Optional) Sie können Zielgruppen für MDM-Richtlinien zielgruppen.

1. Geräte sollten AAD sein, die Mit Ihrem Mandanten verbunden, [automatisch](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)registriert und über [Auto Pilot konfiguriert werden.](https://docs.microsoft.com/hololens/hololens2-autopilot)
    1. Beachten Sie, dass der erste Benutzer auf dem Gerät der Gerätebesitzer ist.
    1. Beachten Sie, dass der Benutzer, der den Beitritt ausgeführt hat, gerätebesitzer wird, wenn das Gerät AAD beigetreten ist.
    1. Weitere Informationen finden Sie unter [Gerätebesitzer](https://docs.microsoft.com/hololens/security-adminless-os#device-owner).
1. [Der Mandant](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) sperrt das Gerät, sodass es nur Ihrem Mandanten beigetreten werden kann.
    1. **Zusätzlicher Link:** [Mandantensperre CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).
1. Konfigurieren des Kiosks mithilfe des globalen zugewiesenen Zugriffs auf [hier](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk).
1. Es wird empfohlen, die folgenden (optionalen) Funktionen zu deaktivieren:
    1. Möglichkeit, das Gerät hier in den Entwicklermodus [zu setzen.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Die Möglichkeit, die HoloLens mit einem PC zu verbinden, um datumsgemäß zu [kopieren, deaktivieren Sie USB.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Wenn Sie USB nicht deaktivieren möchten, aber die Möglichkeit haben möchten, ein Bereitstellungspaket mithilfe von USB auf das Gerät anzuwenden, befolgen Sie die hier aufgeführten [**Anweisungen.**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Verwenden [Sie WDAC,](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) um Apps auf dem HoloLens 2-Gerät zu erlauben oder zu blockieren.
1. Aktualisieren der Remoteunterstützung auf die neueste Version im Rahmen des Setups. Dazu gibt es zwei Möglichkeiten:
    1. Dazu gehen Sie zu Windows **Microsoft Store --> Remote Assist --> und Update App**.
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) , das automatische App-Updates zulässt, ist standardmäßig aktiviert. Lassen Sie das Gerät angeschlossen, um Updates zu erhalten.
1. [Deaktivieren Sie alle Einstellungsseiten](https://docs.microsoft.com/hololens/settings-uri-list) mit Ausnahme der Netzwerkeinstellungen, damit Benutzer eine Verbindung mit Gastnetzwerken an Clientstandorten herstellen können.
1. [Verwalten von HoloLens-Updates](https://docs.microsoft.com/hololens/hololens-updates)
    1. Option zum [Steuern von Betriebssystemupdates](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) oder zum freien Fluss.
1. [Allgemeine Geräteeinschränkungen](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).
