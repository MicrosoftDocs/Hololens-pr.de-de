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
ms.openlocfilehash: c0ea468df2188700af408803ae1c55b9d0e4c763
ms.sourcegitcommit: ea5fa6c970756025b77c00b4ea600d60ce033106
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "11268001"
---
# Bereitstellen von HoloLens 2 auf externen Clients mit Remote Assist

Dieses Dokument hilft IT-Berufen bei der Planung und Bereitstellung von HoloLens 2-Geräten, die sich auf Remote Assist konzentrieren. [Erfahren Sie mehr über Remote Assist](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).

## Beschreibung des Szenarios

Für dieses Dokument möchte Contoso Company ein HoloLens 2-Gerät zur kurzfristigen oder langfristigen Verwendung an das Werk eines externen Clients senden. Wenn der Client Unterstützung bei der Wartung von Wartungsleistungen benötigt, wird der Client sich mit den von Contoso Company bereitgestellten Anmeldeinformationen beim HoloLens 2-Gerät anmelden und remote Assist verwenden, um die Experten von Contoso Company zu kontaktieren.

### Anforderungen für dieses Szenario

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. Mobile Device Manager – z. [B. Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. Remote Assist-Lizenz
    1. [Remote Assist kaufen](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Remote Assist für Testversionen](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## Häufige Bedenken

- [Sicherstellen, dass externe Clients nicht miteinander kommunizieren können](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Sicherstellen, dass Clients keinen Zugriff auf Unternehmensressourcen haben](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Einschränken von Apps](#how-to-restrict-apps)
- [Verwalten von Kennwörtern](#how-to-manage-passwords)
- [Sicherstellen, dass Clients keinen Zugriff auf den Chatverlauf haben](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### Sicherstellen, dass externe Clients nicht miteinander kommunizieren können

Da Remote Assist HoloLens-zu-HoloLens-Anrufe nicht unterstützt werden, können Clients suchen, aber nicht miteinander kommunizieren. Um weiter einzuschränken, nach wem Clients suchen und anrufen können, können  [Informationsbarrieren](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) einschränken, mit wem ein Client kommunizieren kann. Eine weitere zu erwägende Option ist die Verwendung [der Bereichsverzeichnissuche.](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Da einmaliges Anmelden aktiviert ist, ist es wichtig, den Browser mithilfe von [**WDAC zu deaktivieren.**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) Wenn ein externer Client den Browser öffnet und die Webversion von Teams verwendet, hat der Client Zugriff auf den Anruf-/Chatverlauf.

### Sicherstellen, dass Clients keinen Zugriff auf Unternehmensressourcen haben

Es gibt zwei Optionen, die sie berücksichtigen sollten.

Die erste Option ist ein Ansatz mit mehreren Ebenen:

1. Weisen Sie nur Lizenzen zu, die der Benutzer benötigt. Wenn Sie dem Benutzer oneDrive, Outlook, SharePoint, Yammer usw. nicht zuweisen, hat er keinen Zugriff auf diese Ressourcen. Die einzigen Lizenzen, die die Benutzer benötigen, sind Remote Assist-, Intune- und AAD-Lizenzen, um zu beginnen.
1. Blockieren von Apps (z. B. E-Mail), auf die Clients nicht zugreifen möchten (Siehe [So schränken Sie Apps ein).](#how-to-restrict-apps)
1. Geben Sie keine Benutzernamen oder Kennwörter für Clients gemeinsam. Um sich bei HoloLens 2 anmelden zu können, ist eine E-Mail und eine numerische PIN erforderlich.

Die zweite Option besteht im Erstellen eines separaten Mandanten, der Clients hostet (siehe Abbildung 1.1).

**Abbildung 1.1**

![Image des Dienst-Mandanten](./images/hololens-service-tenant-image.png)

### Einschränken von Apps

[Der Kioskmodus](https://docs.microsoft.com/hololens/hololens-kiosk) und/oder [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) sind Optionen zum Einschränken von Anwendungen.

### Verwalten von Kennwörtern

1. Entfernen des Kennwortablaufs. Dies erhöht jedoch die Wahrscheinlichkeit, dass ein Konto gefährdet wird. Die Empfehlung für das NIST-Kennwort besteht in der Änderung von Kennwörtern alle 30 bis 90 Tage.
1. Verlängern Sie den Kennwortablauf für HoloLens 2-Geräte auf mehr als 90 Tage.
1. Die Geräte sollten an Contoso zurückgegeben werden, um die Kennwörter zu ändern. Dies kann jedoch zu Problemen führen, wenn erwartet wird, dass sich die Geräte mehr als 90 Tage im Werk des Clients befinden.  
1. Setzen Sie für Geräte, die an mehrere Clients gesendet werden, Kennwörter zurück, bevor Sie das Gerät an Clients senden.

### Sicherstellen, dass Clients keinen Zugriff auf den Chatverlauf haben

Remote Assist clears chat history after each session. Der Chatverlauf ist jedoch für den Microsoft Teams-Benutzer verfügbar.

> [!NOTE]
> Da einmaliges Anmelden aktiviert ist, ist es wichtig, den Browser mithilfe von [**WDAC zu deaktivieren.**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) Wenn ein externer Client den Browser öffnet und die Webversion von Teams verwendet, hat der Client Zugriff auf den Anruf-/Chatverlauf.

## Allgemeine Bereitstellungsempfehlungen und -anweisungen

Für die Bereitstellungsschritte von HoloLens 2 wird Folgendes empfohlen:

1. Verwenden Sie [die neueste HoloLens-Betriebssystemversion](https://aka.ms/hololens2download) als Basis-Build.
1. Weisen Sie benutzer- oder gerätebasierte Lizenzen zu:
    1. Benutzerbasierte und gerätebasierte Lizenzen führen beide die folgenden Schritte aus:
        1. [Erstellen Sie eine Gruppe in AAD, und fügen Sie Mitglieder](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) für HoloLens/RA-Benutzer hinzu.
        1. [Weisen Sie dieser Gruppe geräte- oder benutzerbasierte](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) Lizenzen zu.
        1. (Optional) Sie können Zielgruppen für MDM-Richtlinien.

1. Geräte sollten AAD ihrem Mandanten beigetreten sein, [automatisch](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)registriert und über [autopilot konfiguriert werden.](https://docs.microsoft.com/hololens/hololens2-autopilot)
    1. Beachten Sie, dass der erste Benutzer auf dem Gerät der Gerätebesitzer ist.
    1. Beachten Sie, dass der Benutzer, der die Verknüpfung ausgeführt hat, gerätebesitzer wird, wenn das Gerät mit AAD verbunden ist.
    1. Weitere Informationen finden Sie unter ["Gerätebesitzer".](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)
1. [Der Mandant sperrt](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) das Gerät, sodass es nur Ihrem Mandanten beigetreten sein kann.
    1. **Zusätzlicher Link:** [Mandantensperre CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).
1. Hier können Sie kiosk mit global zugewiesenem Zugriff [konfigurieren.](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)
1. Es wird empfohlen, die folgenden (optionalen) Funktionen zu deaktivieren:
    1. Möglichkeit, das Gerät hier in den Entwicklermodus [zu setzen.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Die Möglichkeit, die HoloLens mit einem PC zu verbinden, um das Datum zu kopieren, [deaktivieren Sie USB.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Wenn Sie USB nicht deaktivieren möchten, aber die Möglichkeit haben möchten, ein Bereitstellungspaket mithilfe von USB auf das Gerät anzuwenden, befolgen Sie die hier [**aufgeführten Anweisungen.**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Verwenden [Sie WDAC,](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) um apps auf dem HoloLens 2-Gerät zu erlauben oder schwarze Apps zu verwenden.
1. Aktualisieren Sie Remote Assist im Rahmen des Setups auf die neueste Version. Dazu gibt es zwei Möglichkeiten:
    1. Dies können Sie tun, indem Sie zu Windows **Microsoft Store --> Remote Assist --> und Update App gehen.**
    1. Eine weitere Methode ist, die HoloLens 2 über Nacht für automatische Updates eingesteckt zu lassen.
1. [Deaktivieren Sie alle Einstellungsseiten](https://docs.microsoft.com/hololens/settings-uri-list) mit Ausnahme der Netzwerkeinstellungen, damit Benutzer eine Verbindung mit Gastnetzwerken an Clientstandorten herstellen können.
1. [Verwalten von HoloLens-Updates](https://docs.microsoft.com/hololens/hololens-updates)
    1. Option zum [Steuern von Betriebssystemupdates](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) oder zum freien Fluss.
1. [Allgemeine Geräteeinschränkungen](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).
