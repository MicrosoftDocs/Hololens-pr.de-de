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
ms.openlocfilehash: 495be858c235931ed591b097e6b5951f7197c3f7a62bd1aaa16bea65a4e3885f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659891"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>Bereitstellen von HoloLens 2 auf externen Clients mit Remote Assist

Dieser Leitfaden unterstützt IT-Experten bei der Bereitstellung Microsoft HoloLens 2 Geräten in ihrer Organisation:

1. Cloud connect HoloLens 2 Devices
1. Beliehen HoloLens 2 geräte an externe Clients zur Verwendung
1. Sichern von geliehenen Geräten

Dieser Leitfaden enthält allgemeine Empfehlungen [HoloLens 2](#general-deployment-recommendations-and-instructions) Bereitstellung, die für die meisten [](#common-concerns) HoloLens 2-Bereitstellungsszenarien gelten, sowie allgemeine Bedenken, die Kunden bei der Bereitstellung von Remote Assist für die externe Verwendung haben.

## <a name="scenario-description"></a>Beschreibung des Szenarios

Im Sinne dieses Dokuments möchte contoso company ein HoloLens 2-Gerät zur kurzfristigen oder langfristigen Verwendung an das Werk eines externen Clients versenden. Wenn der Client Hilfe bei der Wartung benötigt, wird er sich mit den Anmeldeinformationen des Contoso-Unternehmens beim HoloLens 2-Gerät anmelden und Remote Assist verwenden, um sich mit den Experten des Contoso-Unternehmens in Verbindung zu setzen.

Weitere Informationen zu Remote Assist [finden Sie hier.](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="requirements-for-this-scenario"></a>Anforderungs for this Scenario

1. [Azure AD](/azure/active-directory/fundamentals/active-directory-whatis)
1. Mobile Geräte-Manager– z. B. [Intune](/mem/intune/fundamentals/free-trial-sign-up)
1. Remote Assist-Lizenz
    1. [Kaufen Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Test Remote Assist](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Allgemeine Bedenken

- [Sicherstellen, dass externe Clients nicht miteinander kommunizieren können](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Sicherstellen, dass Clients keinen Zugriff auf Unternehmensressourcen haben](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Einschränken von Apps](#how-to-restrict-apps)
- [Verwalten von Kennwörtern](#how-to-manage-passwords)
- [Sicherstellen, dass Clients keinen Zugriff auf den Chatverlauf haben](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Sicherstellen, dass externe Clients nicht miteinander kommunizieren können

Da Remote Assist HoloLens aufrufe HoloLens nicht unterstützt werden, können Clients nacheinander suchen, aber nicht miteinander kommunizieren. Um weiter einzuschränken, nach wem Clients suchen und aufrufen können, können  [Informationsbarrieren](/microsoft-365/compliance/information-barriers) einschränken, mit wem ein Client kommunizieren kann. Eine weitere zu berücksichtigende Option ist die Verwendung [der Bereichsverzeichnissuche.](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Da einmaliges Anmelden aktiviert ist, ist es wichtig, den Browser mit [**WDAC zu deaktivieren.**](/hololens/windows-defender-application-control-wdac) Wenn ein externer Client den Browser öffnet und die Webversion von Teams verwendet, hat der Client Zugriff auf den Anruf-/Chatverlauf.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>Sicherstellen, dass Clients keinen Zugriff auf Unternehmensressourcen haben

Es gibt zwei Optionen, die Sie berücksichtigen sollten.

Die erste Option ist ein mehrschichtiger Ansatz:

1. Weisen Sie nur Lizenzen zu, die der Benutzer benötigt. Wenn Sie dem Benutzer OneDrive, Outlook, SharePoint, Yammer usw. nicht zuweisen, hat er keinen Zugriff auf diese Ressourcen. Die einzigen Lizenzen, die Benutzer benötigen, sind Remote Assist, Intune und AAD-Lizenzen.
1. Blockieren Sie Apps (z. B. E-Mails), auf die Clients nicht zugreifen können (siehe [Einschränken von Apps).](#how-to-restrict-apps)
1. Geben Sie weder Benutzernamen noch Kennwörter für Clients weiter. Für die Anmeldung beim HoloLens 2 sind eine E-Mail und eine numerische PIN erforderlich.

Die zweite Option besteht in der Erstellung eines separaten Mandanten, der Clients hostet (siehe Abbildung 1.1).

**Abbildung 1.1**

![Dienst-Mandantenimage](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Einschränken von Apps

[Kioskmodus](/hololens/hololens-kiosk) und/oder [WDAC (Windows Defender Application Control)](/hololens/windows-defender-application-control-wdac) sind Optionen zum Einschränken von Anwendungen.

### <a name="how-to-manage-passwords"></a>Verwalten von Kennwörtern

1. Kennwortablauf entfernen. Dies erhöht jedoch die Wahrscheinlichkeit, dass ein Konto kompromittiert wird. NIST-Kennwortempfehlung: Kennwörter werden alle 30 bis 90 Tage geändert.
1. Verlängern Sie den Kennwortablauf für HoloLens 2 Geräte auf mehr als 90 Tage.
1. Die Geräte sollten an Contoso zurückgegeben werden, um die Kennwörter zu ändern. Dies kann jedoch zu Problemen führen, wenn erwartet wird, dass sich die Geräte mehr als 90 Tage im Werk des Clients befinden.  
1. Setzen Sie für Geräte, die an mehrere Clients gesendet werden, Kennwörter zurück, bevor Sie das Gerät an Clients versenden.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>Sicherstellen, dass Clients keinen Zugriff auf den Chatverlauf haben

Remote Assist nach jeder Sitzung den Chatverlauf. Der Chatverlauf ist jedoch für den Benutzer Microsoft Teams verfügbar.

> [!NOTE]
> Da einmaliges Anmelden aktiviert ist, ist es wichtig, den Browser mit [**WDAC zu deaktivieren.**](/hololens/windows-defender-application-control-wdac) Wenn ein externer Client den Browser öffnet und die Webversion von Teams verwendet, hat der Client Zugriff auf den Anruf-/Chatverlauf.

## <a name="general-deployment-recommendations-and-instructions"></a>Allgemeine Bereitstellungs- Empfehlungen und Anweisungen

Es wird Folgendes für die HoloLens 2 empfohlen:

1. Verwenden Sie [das neueste HoloLens Betriebssystemversion](https://aka.ms/hololens2download) als Baseline-Build.
1. Zuweisen von benutzer- oder gerätebasierten Lizenzen:
    1. Benutzer- und gerätebasierte Lizenzen führen beide die folgenden Schritte aus:
        1. [Erstellen Sie eine Gruppe in AAD, und fügen Sie Mitglieder](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) für HoloLens/RA-Benutzer hinzu.
        1. [Weisen Sie dieser Gruppe gerätebasierte oder benutzerbasierte](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) Lizenzen zu.
        1. (Optional) Sie können Zielgruppen für MDM-Richtlinien verwenden.

1. Geräte sollten mit Ihrem Mandanten in AAD, [automatisch registriert](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)und über [AutoPilot konfiguriert werden.](/hololens/hololens2-autopilot)
    1. Beachten Sie, dass der erste Benutzer auf dem Gerät der Gerätebesitzer ist.
    1. Beachten Sie, dass der Benutzer, der die Verknüpfung durchgeführt hat, gerätebesitzer ist, wenn das Gerät mit AAD verbunden ist.
    1. Weitere Informationen finden Sie unter [Gerätebesitzer.](/hololens/security-adminless-os#device-owner)
1. [Der Mandant](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) sperrt das Gerät so, dass es nur Ihrem Mandanten beigetreten sein kann.
    1. **Zusätzlicher Link:** [Mandantensperr-CSP](/windows/client-management/mdm/tenantlockdown-csp).
1. Konfigurieren Sie kiosk mit global zugewiesenem Zugriff auf [hier.](/hololens/hololens-global-assigned-access-kiosk)
1. Es wird empfohlen, die folgenden (optionalen) Funktionen zu deaktivieren:
    1. Hier können Sie das Gerät in den [Entwicklermodus bringen.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Deaktivieren Sie USB, um HoloLens Verbindung mit einem PC zum Kopieren des Datums [herzustellen.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Wenn Sie USB nicht deaktivieren möchten, aber ein Bereitstellungspaket über USB auf das Gerät anwenden möchten, befolgen Sie die hier aufgeführten [**Anweisungen.**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Verwenden [Sie WDAC](/hololens/windows-defender-application-control-wdac) zum Zulassen oder Blockieren von Apps auf dem HoloLens 2 Gerät.
1. Aktualisieren Remote Assist im Rahmen des Setups auf die neueste Version. Dazu gibt es zwei Möglichkeiten:
    1. Dies können Sie tun, indem Sie Windows **Microsoft Store --> Remote Assist --> app aktualisieren.**
    1. [ApplicationManagement/AllowAppStoreAutoUpdate,](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) die automatische App-Updates zulässt, ist standardmäßig aktiviert. Halten Sie das Gerät angeschlossen, um Updates zu erhalten.
1. [Deaktivieren Sie alle Einstellungsseiten außer](/hololens/settings-uri-list) den Netzwerkeinstellungen, damit Benutzer eine Verbindung mit Gastnetzwerken an Clientstandorten herstellen können.
1. [Verwalten HoloLens Updates](/hololens/hololens-updates)
    1. Option zum [Steuern von Betriebssystemupdates](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) oder zum zulassen des freien Flusses.
1. [Allgemeine Geräteeinschränkungen.](/hololens/hololens-common-device-restrictions)
