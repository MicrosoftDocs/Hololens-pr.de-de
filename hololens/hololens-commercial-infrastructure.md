---
title: Infrastruktur-Richtlinien für die HoloLens
description: Erfahren Sie mehr über die Infrastrukturrichtlinien für HoloLens-Geräte, einschließlich drahtlose Netzwerkunterstützung, Remoteunterstützung und Verwaltung mobiler Geräte.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4eb55bec56e53de9195ac87e0491eefd91992f3d
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283386"
---
# Konfigurieren Ihres Netzwerks für HoloLens

Für diesen Teil des Dokuments werden die folgenden Personen benötigt:

1. Netzwerk-Administrator mit Berechtigungen zum Ändern des Proxys/der Firewall
2. Azure Active Directory-Administrator
3. Mobile Device Manager-Administrator

## Infrastruktur-Anforderungen

HoloLens ist im Kern ein mobiles Windows-Gerät, das in Azure integriert ist.  Es funktioniert am besten in kommerziellen Umgebungen, in denen ein Drahtlosnetzwerk (WLAN) verfügbar und Zugriff auf Microsoft-Dienste möglich ist.

Zu den kritischen Clouddiensten zählen:

- Azure Active Directory (Azure AD)
- Windows Update (WU)

Kommerzielle Kunden benötigen die Enterprise Mobility Management (EMM)-Infrastruktur oder die Mobile Geräteverwaltung (MDM), um HoloLens-Geräte im großen Maßstab zu verwalten.  In diesem Leitfaden wird [Microsoft Intune-](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) als Beispiel verwendet. HoloLens kann jedoch von einem beliebigen unterstützt werden, der die Microsoft-Richtlinie voll unterstützt.  Wenden Sie sich an Ihren Anbieter die Mobile Geräteverwaltung, wenn er HoloLens 2 unterstützt.

HoloLens unterstützt eine begrenzte Anzahl von unterschiedlichen Cloud-Erlebnissen.

### EAP-Unterstützung von Drahtlosnetzwerken

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### Spezifische Netzwerkanforderungen für HoloLens

Vergewissern Sie sich, dass [diese Liste](hololens-offline.md) der Endpunkte auf Ihrer Netzwerk-Firewall zugelassen sind. Dies ermöglicht der HoloLens ordnungsgemäß zu funktionieren.

### Spezifische Netzwerkanforderungen für Remote Assist

1. Die empfohlene Bandbreite für eine optimale Leistung von Remote Assist beträgt 1,5 Mbps. Weitere Informationen finden Sie in den [detaillierten Netzwerkanforderungen](https://docs.microsoft.com/MicrosoftTeams/prepare-network).
**(Bitte beachten Sie, dass Remote Assist auch dann noch funktioniert, wenn Ihr Netzwerk nicht über eine Netzwerkgeschwindigkeit von mindestens 1,5 Mbit/s verfügt. Allerdings kann die Qualität darunter leiden.)**
1. Stellen Sie sicher, dass diese Ports und URLs in Ihrer Netzwerkfirewall zulässig sind, damit Microsoft Teams funktioniert. Bleiben Sie auf dem neuesten Stand mit der [neuesten Liste der Ports](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

- Informieren Sie sich ausführlicher über die spezifischen [Netzwerkanforderungen für Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements). 
- Informieren Sie sich ausführlicher über [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network).

### Spezifische Netzwerkanforderungen für Guides

Guides benötigt nur einen Netzwerkzugang, um die App herunterzuladen und zu verwenden.

## Azure Active Directory-Leitfaden

> [!NOTE]
> Dieser Schritt ist nur dann erforderlich, wenn Ihre Organisation die Verwaltung von HoloLens plant.

1. Stellen Sie sicher, dass Sie eine Azure AD-Lizenz besitzen.
Weitere Informationen finden Sie unter [HoloLens-Lizenzanforderungen](hololens-licenses-requirements.md).

1. Wenn Sie die automatische Registrierung verwenden möchten, müssen Sie die [Azure AD-Registrierung konfigurieren](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment).

1. Stellen Sie sicher, dass sich die Benutzer Ihres Unternehmens im Azure Active Directory (Azure AD) befinden.
Siehe die folgende [Anleitung](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory) zum Hinzufügen von Benutzern.

1. Wir schlagen vor, dass Benutzer, die ähnliche Lizenzen benötigen, der gleichen Gruppe hinzugefügt werden.
    1. [Erstellen einer Gruppe](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Hinzufügen von Benutzern zu Gruppen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Stellen Sie sicher, dass den Benutzern (oder Benutzergruppen) Ihres Unternehmens die nötigen Lizenzen zugewiesen werden.
Wenn Sie Lizenzen zuweisen müssen, folgen Sie dieser [Anleitung](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).

1. Führen Sie diesen Schritt nur durch, wenn von den Benutzern erwartet wird, dass sie ihr HoloLens/Mobilgerät bei Ihnen registrieren (es gibt drei Optionen). Diese Schritte stellen sicher, dass die Benutzer (oder eine Gruppe von Benutzern) Ihres Unternehmens Geräte hinzufügen können.
    1. **Option 1:**: Erteilen Sie allen Benutzern die Berechtigung zum Hinzufügen von Geräten zu Azure AD.
**Melden Sie sich im Azure-Portal als Administrator an** > **Azure Active Directory** > **Geräte** > **Geräteeinstellungen** >
**Benutzer festlegen, die Geräte zu Azure AD hinzufügen dürfen *Alle***

    1. **Option 2:**: Ausgewählten Benutzern/Gruppen die Berechtigung zum Hinzufügen von Geräten zu Azure AD erteilen **Als Administrator im Azure-Portal anmelden** > **Azure Active Directory** > **Geräte** > **Geräteeinstellungen** >
**Die Option „Benutzer dürfen Geräte in Azure AD einbinden“ auf *Ausgewählt*** festlegen
![Abbildung, in der die Konfiguration von mit Azure AD verbundenen Geräten dargestellt ist](images/azure-ad-image.png)

    1. **Option 3:**: Sie können die Domäne so einstellen, dass kein Benutzer ein Gerät hinzufügen kann. Dies bedeutet, dass alle Geräte manuell registriert werden müssen.

## Leitfaden zum Mobile Device Manager

### Fortlaufende Geräteverwaltung

> [!NOTE]
> Dieser Schritt ist nur dann erforderlich, wenn Ihre Organisation die Verwaltung von HoloLens plant.

Die fortlaufende Geräteverwaltung hängt von ihrer Verwaltungsinfrastruktur für mobile Geräte ab.  Die meisten Infrastrukturen weisen die gleiche allgemeine Funktionalität auf, aber die Benutzeroberfläche kann stark variieren.

1. [Mit CSPs (Konfigurationsdienstanbieter)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) können Sie Verwaltungseinstellungen für die Geräte in Ihrem Netzwerk erstellen und bereitstellen. Eine Referenz finden Sie in der [Liste der HoloLens-CSPs.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)

1. [Compliance-Richtlinien](https://docs.microsoft.com/intune/device-compliance-get-started) sind Regeln und Einstellungen, die von Geräten erfüllt werden müssen, damit sie in Ihrer Unternehmensinfrastruktur kompatibel sind. Verwenden Sie diese Richtlinien mit bedingtem Zugriff, um den Zugriff auf Unternehmensressourcen für Geräte zu blockieren, die nicht kompatibel sind. So können Sie beispielsweise eine Richtlinie erstellen, die erfordert, dass BitLocker aktiviert ist.

1. [Erstellen einer Compliance-Richtlinie](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows)

1. Bedingter Zugriff erlaubt/verweigert mobilen Geräten und mobilen Anwendungen den Zugriff auf Unternehmensressourcen. Zwei Dokumente, die für Sie möglicherweise hilfreich sind: [Planen Sie Ihre Bereitstellung mit beschränktem Zugriff (CA, Conditional Access)](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) und [Bewährte Methoden](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).

1. [Dieser Artikel](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) befasst sich mit den Verwaltungstools von Intune für HoloLens.

1. [Erstellen eines Marketingprofils](https://docs.microsoft.com/intune/configuration/device-profile-create)

### Updates verwalten

Intune enthält ein Feature namens „Updateringe“ für Windows 10-Geräte, einschließlich HoloLens 2 und HoloLens v1 (mit Holographic for Business). Updateringe umfassen eine Gruppe von Einstellungen, mit denen festgelegt wird, wie und wann Updates installiert werden.

Sie können z. B. ein Wartungsfenster erstellen, um Updates zu installieren, oder Sie können nach der Installation von Updates einen Neustart auswählen.  Sie können auch beschließen, Updates für einen unbegrenzten Zeitraum anzuhalten, bis Sie bereit für die Aktualisierung sind.

Erfahren Sie mehr über das [Konfigurieren von Updateringen mit Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).

### Anwendungsverwaltung

Verwalten von HoloLens-Anwendungen über:

1. Microsoft Store  
  Der Microsoft Store ist die beste Möglichkeit, um Anwendungen auf HoloLens zu verteilen und zu nutzen.  Es gibt eine großartige Gruppe von wichtigen HoloLens-Anwendungen, die bereits im Store verfügbar sind, oder Sie können [Ihre eigenen veröffentlichen](https://docs.microsoft.com/windows/uwp/publish/).  
  Alle Anwendungen im Store sind öffentlich für jeden verfügbar, wenn dies für Sie nicht akzeptabel ist, können Sie sich den Microsoft Store für Unternehmen ansehen.  

1. [Microsoft Store für Unternehmen](https://docs.microsoft.com/microsoft-store/)  
  Der Microsoft Store für Unternehmen und Bildungseinrichtungen ist ein benutzerdefinierter Store für Ihre Unternehmensumgebung.  Sie können hier den in Windows 10 und HoloLens integrierten Microsoft Store verwenden, um Apps für Ihre Organisation zu suchen, zu erwerben, zu verteilen und zu verwalten.  Sie können außerdem Apps bereitstellen, die für Ihre kommerzielle Umgebung spezifisch, aber für andere Personen nicht relevant sind.

1. Bereitstellung und Verwaltung von Anwendungen über Intune oder eine andere Lösung für die Verwaltung mobiler Geräte  
  Die meisten Lösungen für die Verwaltung mobiler Geräte, einschließlich Intune, bieten eine Möglichkeit zum direkten Bereitstellen von Branchenanwendungen für eine Reihe von registrierten Geräten.  Lesen Sie diesen Artikel für die [Intune-App-Installation](https://docs.microsoft.com/intune/apps-deploy).

1. _nicht empfohlen_ Geräteportal  
  Anwendungen können mithilfe des Windows-Geräteportals auch direkt auf HoloLens installiert werden.  Dies wird nicht empfohlen, da der Entwicklermodus für die Verwendung des Geräteportals aktiviert sein muss.

Hier finden Sie weitere Informationen zum [Installieren von Apps auf HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).

### Zertifikate

Sie können Zertifikate über Ihren MDM-Anbieter verteilen. Wenn für Ihr Unternehmen Zertifikate erforderlich sind – Intune unterstützt PKCS, PFX und SCEP. Es ist wichtig zu verstehen, welches Zertifikat für Ihr Unternehmen geeignet ist. In der Dokumentation zur [Zertifikatkonfiguration](https://docs.microsoft.com/intune/protect/certificates-configure) finden Sie Informationen dazu, welches Zertifikat für Sie am besten ist. Wenn Sie beabsichtigen, Zertifikate für die HoloLens-Authentifizierung zu verwenden, eignen sich möglicherweise PFX oder SCEP für Sie.

Weitere Informationen zur Verwendung von [SCEP](https://docs.microsoft.com/intune/protect/certificates-profile-scep) finden Sie in den folgenden Schritten.

### Upgrade auf Holographics for Business Commercial Suite

> [!NOTE]
> Windows Holographics for Business Commercial Suite ist nur für HoloLens-Geräte der 1. Generation vorgesehen. Das Profil wird nicht auf HoloLens 2-Geräte angewendet.

Anweisungen zum Upgrade auf die kommerzielle Suite finden Sie in der Dokumentation zum [holografischen Upgrade](https://docs.microsoft.com/intune/configuration/holographic-upgrade).

### Konfigurieren des Kioskmodus mithilfe von Microsoft Intune

1. Synchronisieren des Microsoft Store auf Intune (siehe die folgenden [Anweisungen](https://docs.microsoft.com/intune/apps/windows-store-for-business)).

1. Prüfen Sie Ihre App-Einstellungen.
    1. Melden Sie sich bei Ihrem Microsoft Store Business-Konto an.
    1. **Verwalten > Produkte und Dienste > Apps und Software > Wählen Sie die App aus, die Sie synchronisieren möchten > Verfügbarkeit im Privaten Store > Wählen Sie "Alle" oder "Bestimmte Gruppen" aus.**
        >[!NOTE]
        >Wenn die gewünschte App nicht angezeigt wird, müssen Sie die App "abrufen", indem Sie den Shop nach Ihrer App durchsuchen. **Klicken Sie auf die Leiste „Suchen“ in der oberen rechten Ecke > geben Sie den Namen der App ein > klicken Sie auf die App > wählen Sie „Abrufen“ aus**.
    1. Wenn Ihre Apps unter **Intune > Client-Apps > Apps** nicht angezeigt werden, müssen Sie möglicherweise [Ihre Apps erneut synchronisieren](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps).

1. [Erstellen eines Geräteprofils für den Kioskmodus](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> Sie können verschiedene Benutzer so konfigurieren, dass diese unterschiedliche Kioskmodus-Erlebnisse haben, indem Sie „Azure AD“ als „Benutzeranmeldungstyp“ verwenden. Diese Option steht jedoch nur im Multi-App-Kioskmodus zur Verfügung. Der Multi-App-Kioskmodus funktioniert sowohl mit nur einer als auch mit mehreren Apps.

![Abbildung, in der die Konfiguration des Kioskmodus in Intune dargestellt ist](images/aad-kioskmode.png)

Weitere MDM-Dienste finden Sie in der Dokumentation Ihres Anbieters. Lesen Sie die Anweisungen zum [HoloLens-Kiosk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk), wenn Sie eine benutzerdefinierte Einstellung und eine vollständige XML-Konfiguration verwenden müssen, um einen Kiosk in Ihrem MDM-Dienst einrichten zu können.

## Zertifikate und Authentifizierung

Zertifikate können über Ihren MDM bereitgestellt werden (siehe "Zertifikate" im Abschnitt [MDM](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)). Zertifikate können auch über die Paketbereitstellung für HoloLens bereitgestellt werden. Weitere Informationen finden Sie unter [HoloLens-Bereitstellung](hololens-provisioning.md).

### Weitere Intune-Quicklinks

1. [Profile erstellen:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profile ermöglichen es Ihnen, Einstellungen hinzuzufügen oder zu konfigurieren, die auf die Geräte in Ihrer Organisation verschoben werden.

