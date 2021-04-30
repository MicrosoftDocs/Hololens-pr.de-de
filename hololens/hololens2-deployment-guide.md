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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308677"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>Bereitstellen von HoloLens 2 auf externen Clients mit Remote Assist

Dieser Leitfaden unterstützt IT-Experten bei der Bereitstellung Microsoft HoloLens 2 Geräten in ihrer Organisation:

1. Cloud connect HoloLens 2 Devices
1. Beliehen HoloLens 2 geräte an externe Clients zur Verwendung
1. Sichern von geliehenen Geräten

Dieser Leitfaden enthält allgemeine Empfehlungen [HoloLens 2](#general-deployment-recommendations-and-instructions) Bereitstellung, die für die meisten [](#common-concerns) HoloLens 2-Bereitstellungsszenarien gelten, sowie allgemeine Bedenken, die Kunden bei der Bereitstellung von Remote Assist für die externe Verwendung haben.

## <a name="scenario-description"></a>Beschreibung des Szenarios

Für die Zwecke dieses Dokuments möchte contoso company ein HoloLens 2-Gerät zur kurzfristigen oder langfristigen Verwendung an das Werk eines externen Clients versenden. Wenn der Client Hilfe bei der Wartung von Maschinen benötigt, anmeldet sich der Client beim HoloLens 2-Gerät mit den Anmeldeinformationen des Contoso-Unternehmens und verwendet Remote Assist, um sich mit den Experten des Contoso-Unternehmens in Verbindung zu setzen.

Weitere Informationen zu Remote Assist [finden Sie hier.](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="requirements-for-this-scenario"></a>Anforderungs for this Scenario

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. Mobile Geräte-Manager– z. B. [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. Remote Assist-Lizenz
    1. [Kaufen Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Test Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Allgemeine Bedenken

- [Sicherstellen, dass externe Clients nicht miteinander kommunizieren können](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Sicherstellen, dass Clients keinen Zugriff auf Unternehmensressourcen haben](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Einschränken von Apps](#how-to-restrict-apps)
- [Verwalten von Kennwörtern](#how-to-manage-passwords)
- [Sicherstellen, dass Clients keinen Zugriff auf den Chatverlauf haben](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>So stellen Sie sicher, dass externe Clients nicht miteinander kommunizieren können

Da Remote Assist HoloLens-zu-HoloLens-Aufrufe nicht unterstützt werden, können Clients suchen, aber nicht miteinander kommunizieren. Um weiter einzuschränken, nach wem Clients suchen und aufrufen können, können  [Informationsbarrieren](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) einschränken, mit wem ein Client kommunizieren kann. Eine weitere zu berücksichtigende Option ist die Verwendung der [Bereichsverzeichnissuche.](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Da einmaliges Anmelden aktiviert ist, ist es wichtig, den Browser mithilfe von [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)zu deaktivieren. Wenn ein externer Client den Browser öffnet und die Webversion von Teams verwendet, hat der Client Zugriff auf den Anruf-/Chatverlauf.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>Sicherstellen, dass Clients keinen Zugriff auf Unternehmensressourcen haben

Es gibt zwei Optionen zu berücksichtigen.

Die erste Option ist ein mehrschichtiger Ansatz:

1. Weisen Sie nur Lizenzen zu, die der Benutzer benötigt. Wenn Sie dem Benutzer oneDrive, Outlook, SharePoint, Yammer usw. nicht zuweisen, hat er keinen Zugriff auf diese Ressourcen. Die einzigen Lizenzen, die Benutzer benötigen, sind Remote Assist, Intune und AAD-Lizenzen, um zu beginnen.
1. Blockieren Sie Apps (z. B. E-Mails), auf die Clients nicht zugreifen sollen (siehe [Einschränken von Apps).](#how-to-restrict-apps)
1. Geben Sie Benutzernamen und Kennwörter NICHT für Clients frei. Um sich beim HoloLens 2 anzumelden, sind eine E-Mail und eine numerische PIN erforderlich.

Die zweite Option besteht darin, einen separaten Mandanten zu erstellen, der Clients hostet (siehe Abbildung 1.1).

**Abbildung 1.1**

![Image des Dienstmandanten](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Einschränken von Apps

[Kioskmodus](https://docs.microsoft.com/hololens/hololens-kiosk) und/oder [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) sind Optionen zum Einschränken von Anwendungen.

### <a name="how-to-manage-passwords"></a>Verwalten von Kennwörtern

1. Kennwortablauf entfernen. Dies erhöht jedoch die Wahrscheinlichkeit, dass ein Konto kompromittiert wird. NIST-Kennwortempfehlung: Kennwörter werden alle 30 bis 90 Tage geändert.
1. Verlängern Sie den Kennwortablauf für HoloLens 2 Geräte auf mehr als 90 Tage.
1. Die Geräte sollten an Contoso zurückgegeben werden, um die Kennwörter zu ändern. Dies kann jedoch Probleme verursachen, wenn erwartet wird, dass sich die Geräte mehr als 90 Tage im Werk des Clients befinden.  
1. Setzen Sie für Geräte, die an mehrere Clients gesendet werden, Kennwörter zurück, bevor Sie das Gerät an Clients versenden.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>Sicherstellen, dass Clients keinen Zugriff auf den Chatverlauf haben

Remote Assist nach jeder Sitzung den Chatverlauf. Der Chatverlauf ist jedoch für den Microsoft Teams-Benutzer verfügbar.

> [!NOTE]
> Da einmaliges Anmelden aktiviert ist, ist es wichtig, den Browser mit [**WDAC zu deaktivieren.**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) Wenn ein externer Client den Browser öffnet und die Webversion von Teams verwendet, hat der Client Zugriff auf den Anruf-/Chatverlauf.

## <a name="general-deployment-recommendations-and-instructions"></a>Allgemeine Empfehlungen und Anweisungen für die Bereitstellung

Es wird Folgendes für die HoloLens 2 empfohlen:

1. Verwenden Sie [das neueste HoloLens-Betriebssystem-Release](https://aka.ms/hololens2download) als Baseline-Build.
1. Zuweisen von benutzer- oder gerätebasierten Lizenzen:
    1. Benutzer- und gerätebasierte Lizenzen führen beide die folgenden Schritte aus:
        1. [Erstellen Sie eine Gruppe in AAD, und fügen Sie Mitglieder](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) für HoloLens/RA-Benutzer hinzu.
        1. Weisen Sie dieser Gruppe [gerätebasierte oder benutzerbasierte Lizenzen](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) zu.
        1. (Optional) Sie können Zielgruppen für MDM-Richtlinien verwenden.

1. Geräte sollten AAD in Ihren Mandanten eingebunden, [automatisch registriert](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)und über autopilot konfiguriert [werden.](https://docs.microsoft.com/hololens/hololens2-autopilot)
    1. Beachten Sie, dass der erste Benutzer auf dem Gerät der Gerätebesitzer ist.
    1. Beachten Sie Folgendes: Wenn das Gerät in AAD eingebunden ist, wird der Benutzer, der die Verknüpfung durchgeführt hat, zum Gerätebesitzer.
    1. Weitere Informationen finden Sie unter [Gerätebesitzer.](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)
1. [Der Mandant sperrt](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) das Gerät so, dass es nur in Ihren Mandanten eingebunden werden kann.
    1. **Zusätzlicher Link:** [Mandantensperre CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).
1. Konfigurieren Sie kiosk mit global zugewiesenem Zugriff auf [.](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)
1. Es wird empfohlen, die folgenden (optionalen) Funktionen zu deaktivieren:
    1. Hier können Sie das Gerät in den [Entwicklermodus](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)versetzen.
    1. Die Fähigkeit zum Verbinden der HoloLens mit einem PC zum Kopieren des Datums [deaktivieren USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).
       > [!NOTE]
        > Wenn Sie USB nicht deaktivieren möchten, aber ein Bereitstellungspaket über USB auf das Gerät anwenden möchten, befolgen Sie die [**hier**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)aufgeführten Anweisungen.

1. Verwenden Sie [WDAC,](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) um Apps auf dem HoloLens 2 Gerät zuzulassen oder zu blockieren.
1. Aktualisieren Sie Remote Assist im Rahmen des Setups auf die neueste Version. Hierfür stehen zwei Optionen zur Verfügung:
    1. Dies können Sie erreichen, indem Sie zu Windows **Microsoft Store --> Remote Assist --> und App aktualisieren.**
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) , das automatische App-Updates zulässt, ist standardmäßig aktiviert. Lassen Sie das Gerät angeschlossen, um Updates zu erhalten.
1. [Deaktivieren Sie alle Einstellungsseiten](https://docs.microsoft.com/hololens/settings-uri-list) mit Ausnahme der Netzwerkeinstellungen, damit Benutzer eine Verbindung mit Gastnetzwerken an Clientstandorten herstellen können.
1. [Verwalten von HoloLens-Updates](https://docs.microsoft.com/hololens/hololens-updates)
    1. Option zum [Steuern von Betriebssystemupdates](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) oder zum zulassen des freien Flusses.
1. [Allgemeine Geräteeinschränkungen.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)
