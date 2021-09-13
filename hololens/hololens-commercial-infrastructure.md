---
title: Infrastruktur-Richtlinien für HoloLens
description: Erfahren Sie mehr über die Infrastruktur-Richtlinien für HoloLens-Geräte, einschließlich drahtloser Netzwerkunterstützung, Remoteunterstützung und Verwaltung mobiler Geräte.
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
ms.openlocfilehash: e23bd458e26668f1f4a9a361ffaadf8fc377933e
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034252"
---
# <a name="configure-your-network-for-hololens"></a>Konfigurieren Ihres Netzwerks für HoloLens

Für diesen Teil des Dokuments werden die folgenden Personen benötigt:

1. Netzwerk-Administrator mit Berechtigungen zum Ändern des Proxys/der Firewall
2. Azure Active Directory-Administrator
3. Mobile Device Manager-Administrator

## <a name="infrastructure-requirements"></a>Anforderungen an die Infrastruktur

HoloLens ist im Kern ein mobiles Windows-Gerät, das in Azure integriert ist.  Es funktioniert am besten in kommerziellen Umgebungen, in denen ein Drahtlosnetzwerk (WLAN) verfügbar und Zugriff auf Microsoft-Dienste möglich ist.

Zu den kritischen Clouddiensten zählen:

- Azure Active Directory (Azure AD)
- Windows Update (WU)

Kommerzielle Kunden benötigen die Infrastrukturen EMM (Enterprise Mobility Management) oder MDM (Mobile Device Management), um HoloLens-Geräte im großen Maßstab zu verwalten.  In diesem Leitfaden wird [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) als Beispiel verwendet. HoloLens kann jedoch von jedem beliebigen Anbieter unterstützt werden, der die Microsoft-Richtlinie in vollem Umfang unterstützt.  Fragen Sie Ihren Anbieter für die Verwaltung von mobilen Geräten, ob er HoloLens 2 unterstützt.

HoloLens unterstützt eine begrenzte Anzahl von Erlebnissen ohne Cloudverbindung.

### <a name="wireless-network-eap-support"></a>EAP-Unterstützung von Drahtlosnetzwerken

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>Spezifische Netzwerkanforderungen für HoloLens

Vergewissern Sie sich, dass die Endpunkte in [dieser Liste](hololens-offline.md) auf Ihrer Netzwerk-Firewall zugelassen sind. Dies ermöglicht HoloLens die ordnungsgemäße Funktion.

### <a name="remote-assist-specific-network-requirements"></a>Spezifische Netzwerkanforderungen für Remote Assist

1. Die empfohlene Bandbreite für eine optimale Leistung von Remote Assist beträgt 1,5 MBit/s. Weitere Informationen finden Sie in den [ausführlichen Netzwerkanforderungen](/MicrosoftTeams/prepare-network).
**(Bitte beachten Sie, dass Remote Assist auch dann noch funktioniert, wenn Ihr Netzwerk nicht über eine Netzwerkgeschwindigkeit von mindestens 1,5 Mbit/s verfügt. Die Qualität ist jedoch möglicherweise eingeschränkt).**
1. Stellen Sie sicher, dass diese Ports und URLs in Ihrer Netzwerkfirewall zulässig sind, damit Microsoft Teams funktionieren kann. Halten Sie Ihre [aktuelle Liste der Ports](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) auf dem Laufenden.

- Erfahren Sie mehr über die spezifischen [Netzwerkanforderungen für Remote Assist](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements). 
- Erfahren Sie mehr darüber, wie Sie das [Netzwerk Ihrer Organisation für Microsoft Teams vorbereiten](/MicrosoftTeams/prepare-network)

### <a name="guides-specific-network-requirements"></a>Spezifische Netzwerkanforderungen für Guides

Guides benötigt nur einen Netzwerkzugang, um die App herunterzuladen und zu verwenden.

## <a name="azure-active-directory-guidance"></a>Azure Active Directory-Leitfaden

> [!NOTE]
> Dieser Schritt ist nur dann erforderlich, wenn Ihre Organisation die Verwaltung von HoloLens plant.

1. Stellen Sie sicher, dass Sie eine Azure AD-Lizenz besitzen.
Weitere Informationen finden Sie in den [HoloLens-Lizenzanforderungen](hololens-licenses-requirements.md).

1. Wenn Sie die automatische Registrierung verwenden möchten, müssen Sie die [Azure AD-Registrierung konfigurieren](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment).

1. Vergewissern Sie sich, dass sich die Benutzer Ihres Unternehmens in Azure Active Directory (Azure AD) befinden.
Informationen zum Hinzufügen von Benutzern finden Sie in den folgenden [Anweisungen](/azure/active-directory/fundamentals/add-users-azure-active-directory).

1. Wir schlagen vor, dass Benutzer, die ähnliche Lizenzen benötigen, der gleichen Gruppe hinzugefügt werden.
    1. [Erstellen einer Gruppe](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Hinzufügen von Benutzern zu Gruppen](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Stellen Sie sicher, dass den Benutzern (oder Benutzergruppen) Ihres Unternehmens die nötigen Lizenzen zugewiesen werden.
Falls Sie Lizenzen zuweisen müssen, folgen Sie diesen [Anweisungen](/azure/active-directory/fundamentals/license-users-groups).

1. Führen Sie diesen Schritt nur durch, wenn von den Benutzern erwartet wird, dass sie ihr HoloLens/Mobilgerät bei Ihnen registrieren (dazu gibt es drei Optionen). Diese Schritte stellen sicher, dass die Benutzer (oder eine Gruppe von Benutzern) Ihres Unternehmens Geräte hinzufügen können.
    1. **Option 1**: Erteilen Sie allen Benutzern die Berechtigung zum Hinzufügen von Geräten zu Azure AD.
**Melden Sie sich beim Azure-Portal als Administrator an** > **Azure Active Directory** > **Geräte** > **Geräteeinstellungen** >
**Legen Sie „Benutzer dürfen Geräte zu Azure AD hinzufügen“ auf *Alle*** fest

    1. **Option 2:** Erteilen Sie ausgewählten Benutzern/Gruppen die Berechtigung zum Hinzufügen von Geräten zu Azure AD **Melden Sie sich beim Azure-Portal als Administrator an** > **Azure Active Directory** > **Geräte** > **Geräteeinstellungen** >
**Legen Sie „Benutzer dürfen Geräte zu Azure AD hinzufügen“ auf *Ausgewählte*** fest 
![Abbildung der Konfiguration von „In Azure AD eingebundene Geräte“.](images/azure-ad-image.png)

    1. **Option 3**: Sie können die Domäne so einstellen, dass kein Benutzer ein Gerät hinzufügen kann. Dies bedeutet, dass alle Geräte manuell registriert werden müssen.

## <a name="mobile-device-manager-guidance"></a>Leitfaden zum Mobile Device Manager

### <a name="ongoing-device-management"></a>Fortlaufende Geräteverwaltung

> [!NOTE]
> Dieser Schritt ist nur erforderlich, wenn Ihre Organisation die Verwaltung von HoloLens plant.

Die fortlaufende Geräteverwaltung hängt von ihrer Verwaltungsinfrastruktur für mobile Geräte ab.  Die meisten Infrastrukturen weisen die gleiche allgemeine Funktionalität auf, aber die Benutzeroberfläche kann stark variieren.

1. Mit [CSPs (Configuration Service Providers)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) können Sie Verwaltungseinstellungen für die Geräte in Ihrem Netzwerk erstellen und bereitstellen. Weitere Informationen finden Sie in der [Liste der HoloLens-CSPs](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).

1. [Konformitätsrichtlinien](/intune/device-compliance-get-started) sind Regeln und Einstellungen, die von Geräten erfüllt werden müssen, damit sie in Ihrer Unternehmensinfrastruktur kompatibel sind. Verwenden Sie diese Richtlinien mit bedingtem Zugriff, um den Zugriff auf Unternehmensressourcen für Geräte zu blockieren, die nicht kompatibel sind. Sie können beispielsweise eine Richtlinie erstellen, die erfordert, dass „BitLocker“ aktiviert ist.

1. [Konformitätsrichtlinie erstellen](/intune/protect/compliance-policy-create-windows).

1. Mit bedingtem Zugriff wird mobilen Geräten und mobilen Anwendungen den Zugriff auf Unternehmensressourcen erlaubt bzw. verweigert. Zwei Dokumente, die Sie möglicherweise hilfreich finden, sind [Planen der Bereitstellung ihrer Zertifizierungsstelle](/azure/active-directory/conditional-access/plan-conditional-access) und [Bewährte Methoden](/azure/active-directory/conditional-access/best-practices).

1. [Dieser Artikel](/intune/fundamentals/windows-holographic-for-business) befasst sich mit den Verwaltungstools von Intune für HoloLens.

1. [Erstellen eines Geräteprofils](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Verwalten von Updates

Intune enthält ein Feature namens „Updateringe“ für Windows 10-Geräte, einschließlich HoloLens 2 und HoloLens v1 (mit Holographic for Business). Updateringe umfassen eine Gruppe von Einstellungen, mit denen festgelegt wird, wie und wann Updates installiert werden.

Sie können beispielsweise ein Wartungsfenster zum Installieren von Updates erstellen oder einen Neustart durchführen, nachdem Updates installiert wurden.  Sie können sich auch entscheiden, Updates für einen unbegrenzten Zeitraum anzuhalten, bis Sie bereit für die Aktualisierung sind.

Erfahren Sie mehr über das [Konfigurieren von Updateringen mit Intune](/intune/windows-update-for-business-configure).

### <a name="application-management"></a>Anwendungsverwaltung

Verwalten von HoloLens-Anwendungen über:

1. Microsoft Store  
  Der Microsoft Store ist die beste Möglichkeit, Anwendungen auf HoloLens zu verteilen und zu nutzen.  Im Store ist bereits eine tolle Sammlung von wichtigen HoloLens-Anwendungen verfügbar; alternativ können [eigene Anwendungen veröffentlichen](/windows/uwp/publish/).  
  Alle Anwendungen im Store sind öffentlich für jeden verfügbar. Wenn dies für Sie nicht akzeptabel ist, sehen Sie sich den Microsoft Store für Unternehmen an.  

1. [Microsoft Store für Unternehmen](/microsoft-store/)  
  Der Microsoft Store für Unternehmen und Bildungseinrichtungen ist ein benutzerdefinierter Store für Ihre Unternehmensumgebung.  Sie können hier den in Windows 10 und HoloLens integrierten Microsoft Store verwenden, um Apps für Ihre Organisation zu suchen, zu erwerben, zu verteilen und zu verwalten.  Sie können außerdem Apps bereitstellen, die für Ihre kommerzielle Umgebung spezifisch, aber für andere Personen nicht relevant sind.

1. Bereitstellung und Verwaltung von Anwendungen über Intune oder eine andere Lösung für die Verwaltung mobiler Geräte  
  Die meisten Lösungen für die Verwaltung mobiler Geräte, einschließlich Intune, bieten eine Möglichkeit zum direkten Bereitstellen von Branchenanwendungen auf einer Reihe registrierter Geräte.  Weitere Informationen zur [Intune-App-Installation](/intune/apps-deploy) finden Sie in diesem Artikel.

1. _nicht empfohlen_ Geräteportal  
  Anwendungen können mithilfe des Windows-Geräteportals auch direkt auf HoloLens installiert werden.  Dies wird nicht empfohlen, da für die Verwendung des Geräteportals der Entwicklermodus aktiviert sein muss.

Erfahren Sie mehr zum [Installieren von Apps auf HoloLens](hololens-install-apps.md).

### <a name="certificates"></a>Zertifikate

Sie können Zertifikate über Ihren MDM-Anbieter verteilen. Wenn für Ihr Unternehmen Zertifikate erforderlich sind – Intune unterstützt PKCS, PFX und SCEP. Es ist wichtig zu verstehen, welches Zertifikat für Ihr Unternehmen geeignet ist. Lesen Sie die Dokumentation zu [Zertifikatkonfigurationen](/intune/protect/certificates-configure), um zu ermitteln, welches Zertifikat für Sie am besten ist. Wenn Sie beabsichtigen, Zertifikate für die HoloLens-Authentifizierung zu verwenden, sind PFX oder SCEP möglicherweise die richtige Wahl für Sie.

Weitere Informationen zur Verwendung von [SCEP](/intune/protect/certificates-profile-scep) finden Sie in den folgenden Schritten.

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Upgrade auf die Holographics for Business Commercial Suite

> [!NOTE]
> Windows Holographics for Business (Commercial Suite) ist nur für HoloLens-Geräte der 1. Generation vorgesehen. Das Profil wird nicht auf HoloLens 2-Geräte angewendet.

Anweisungen zum Upgrade auf die kommerzielle Suite finden Sie in der Dokumentation zum [Holographic-Upgrade](/intune/configuration/holographic-upgrade).

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Konfigurieren des Kioskmodus mithilfe von Microsoft Intune

1. Synchronisieren des Microsoft Store auf Intune (siehe die folgenden [Anweisungen](/intune/apps/windows-store-for-business)).

1. Überprüfen Sie Ihre App-Einstellungen
    1. Melden Sie sich bei Ihrem Microsoft Store Business-Konto an
    1. **Verwalten > Produkte und Dienste > Apps und Software > Wählen Sie die App aus, die Sie synchronisieren möchten > Verfügbarkeit im Privaten Store > Wählen Sie „Alle“ oder „Bestimmte Gruppen“ aus**
        >[!NOTE]
        >Wenn die gewünschte App nicht angezeigt wird, müssen Sie die App „abrufen“, indem Sie den Shop nach Ihrer App durchsuchen. **Klicken Sie in der oberen rechten Ecke auf die Leiste „Suchen“ > geben Sie den Namen der App ein > klicken Sie auf die App > wählen Sie „Abrufen“ aus.**
    1. Wenn Ihre Apps in **Intune > Client-Apps > Apps** nicht angezeigt werden, müssen Sie möglicherweise noch einmal [Ihre Apps synchronisieren](/intune/apps/windows-store-for-business#synchronize-apps).

1. [Erstellen eines Geräteprofils für den Kioskmodus](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> Sie können verschiedene Benutzer so konfigurieren, dass diese unterschiedliche Kioskmodus-Erlebnisse haben, indem Sie „Azure AD“ als „Benutzeranmeldungstyp“ verwenden. Diese Option steht jedoch nur im Multi-App-Kioskmodus zur Verfügung. Der Multi-App-Kioskmodus funktioniert sowohl mit nur einer als auch mit mehreren Apps.

![Abbildung, in der die Konfiguration des Kioskmodus in Intune dargestellt ist.](images/aad-kioskmode.png)

Anweisungen zu weiteren MDM-Diensten finden Sie in der Dokumentation Ihres Anbieters. Lesen Sie die Anweisungen zum [HoloLens-Kiosk](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens), wenn Sie eine benutzerdefinierte Einstellung und eine vollständige XML-Konfiguration verwenden müssen, um einen Kiosk in Ihrem MDM-Dienst einzurichten.

## <a name="certificates-and-authentication"></a>Zertifikate und Authentifizierung

Zertifikate können über Ihren MDM bereitgestellt werden (siehe „Zertifikate“ im Abschnitt [MDM](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)). Zertifikate können auch mithilfe von Paketbereitstellung für HoloLens bereitgestellt werden. Weitere Informationen finden Sie unter [HoloLens-Bereitstellung](hololens-provisioning.md).

### <a name="additional-intune-quick-links"></a>Weitere Intune-Quicklinks

1. [Erstellen von Profilen](/intune/configuration/device-profile-create): Mithilfe von Profilen können sie Einstellungen hinzufügen oder konfigurieren, die per Push auf die Geräte in Ihrer Organisation übertragen werden.

