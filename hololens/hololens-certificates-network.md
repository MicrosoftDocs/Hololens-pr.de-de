---
title: Vorbereiten von Zertifikaten und Netzwerkprofilen für HoloLens 2
description: Hier erfahren Sie, wie Sie Netzwerkzertifikate auf HoloLens 2 Mixed-Reality-Geräten konfigurieren, verwenden und bereitstellen und wie Sie Probleme behandeln.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: eedb451847757eba02465d7ded4494b9712497ff
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397441"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Vorbereiten von Zertifikaten und Netzwerkprofilen für HoloLens 2

Die zertifikatbasierte Authentifizierung wird häufig von Kunden benötigt, die HoloLens 2 verwenden. Möglicherweise benötigen Sie Zertifikate für den WLAN-Zugriff, zum Herstellen einer Verbindung mit VPN-Lösungen oder für den Zugriff auf interne Ressourcen in Ihrem Unternehmen.

HoloLens 2-Geräte werden in der Regel mit Azure AD (Azure Active Directory) verbunden und über Intune oder einen anderen MDM-Anbieter verwaltet. Daher müssen Sie diese Zertifikate mit einem SCEP- (Simple Certificate Enrollment Protocol) oder einer PKCS-Zertifikatinfrastruktur (Public Key Cryptography Standard) bereitstellen, die in Ihre MDM-Lösung integriert ist. 

>[!NOTE]
> Wenn Sie keinen MDM-Anbieter haben, können Sie die Zertifikate trotzdem über ein [Bereitstellungspaket](https://docs.microsoft.com/hololens/hololens-provisioning#steps-for-creating-provisioning-packages) im [Windows-Konfigurations-Designer](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) oder über den [Zertifikat-Manager](https://docs.microsoft.com/hololens/certificate-manager) bereitstellen, indem Sie **Einstellungen > Update und Sicherheit >Zertifikat-Manager** auswählen.

## <a name="certificate-requirements"></a>Zertifikatanforderungen
Für die Bereitstellung von Zertifikaten über eine SCEP- oder PKCS-Infrastruktur sind Stammzertifikate erforderlich. Andere Anwendungen und Dienste in Ihrem Unternehmen erfordern möglicherweise, dass Stammzertifikate auch für Ihre HoloLens 2-Geräte bereitgestellt werden. 

## <a name="wi-fi-connectivity-requirements"></a>Anforderungen an die WLAN-Verbindung
Wenn Sie zulassen möchten, dass ein Gerät automatisch mit der für Ihr Unternehmensnetzwerk erforderlichen WLAN-Konfiguration ausgestattet wird, benötigen Sie ein WLAN-Konfigurationsprofil. Sie können Intune oder einen anderen MDM-Anbieter so konfigurieren, dass diese Profile auf Ihren Geräten bereitgestellt werden. Wenn es zum Schutz Ihres Netzwerks erforderlich ist, dass die Geräte der lokalen Domäne angehören, müssen Sie möglicherweise auch Ihre WLAN-Netzwerkinfrastruktur überprüfen, um sicherzustellen, dass sie mit HoloLens 2-Geräten kompatibel ist (HoloLens 2-Geräte sind nur in Azure AD eingebunden).

## <a name="deploy-certificate-infrastructure"></a>Bereitstellen der Zertifikatinfrastruktur
Wenn noch keine SCEP- oder PKCS-Infrastruktur vorhanden ist, müssen Sie eine solche vorbereiten. Für die Unterstützung der Verwendung von SCEP- oder PKCS-Zertifikaten für die Authentifizierung erfordert Intune die Verwendung eines [Zertifikatconnectors](https://docs.microsoft.com/mem/intune/protect/certificate-connectors).

> [!NOTE]
> Wenn Sie SCEP mit einer Microsoft-Zertifizierungsstelle verwenden, müssen Sie auch [NDES (Network Device Enrollment Service)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes) konfigurieren.

Weitere Informationen finden Sie unter [Konfigurieren eines Zertifikatprofils für Ihre Geräte in Microsoft Intune](https://docs.microsoft.com/intune/certificates-configure).

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Bereitstellen von Zertifikaten und WLAN-/VPN-Profilen
Führen Sie die folgenden Schritte aus, um Zertifikate und Profile bereitzustellen:
1.  Erstellen Sie für jedes der Stamm- und Zwischen-Zertifikate ein Profil (siehe [Erstellen vertrauenswürdiger Zertifikatsprofile](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles).) Jedes dieser Profile muss eine Beschreibung mit einem Ablaufdatum im Format TT/MM/JJJJ aufweisen. **Zertifikatprofile ohne Ablaufdatum werden nicht bereitgestellt.**
1.  Erstellen Sie ein Profil für jedes SCEP- oder PKCS-Zertifikat (siehe [Erstellen eines SCEP-Zertifikatprofils oder Erstellen eines PKCS-Zertifikatprofils](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)). Jedes dieser Profile muss eine Beschreibung aufweisen, die ein Ablaufdatum im Format TT/MM/YYYY enthält. **Zertifikatprofile ohne Ablaufdatum werden nicht bereitgestellt.**

    > [!NOTE]
    > Da HoloLens 2 von vielen als freigegebenes Gerät (mehrere Benutzer pro Gerät) angesehen wird, empfiehlt es sich, wenn möglich Gerätezertifikate anstelle von Benutzerzertifikaten für die WLAN-Authentifizierung bereitzustellen

3.  Erstellen Sie ein Profil für jedes unternehmensspezifische WLAN-Netzwerk (siehe [WLAN-Einstellungen für Windows 10-Geräte und höher](https://docs.microsoft.com/intune/wi-fi-settings-windows)). 
    > [!NOTE]
    > Es empfiehlt sich, WLAN-Profile möglichst Gerätegruppen statt Benutzergruppen [zuzuweisen](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign). 

    > [!TIP]
    > Sie können auch ein funktionierendes WLAN-Profil von einem Windows 10-PC in Ihrem Unternehmensnetzwerk exportieren. Mit diesem Export wird eine XML-Datei mit allen aktuellen Einstellungen erstellt. Importieren Sie dann diese Datei in Intune, und verwenden Sie sie als WLAN-Profil für Ihre HoloLens 2-Geräte. Weitere Informationen finden Sie unter [Exportieren und Importieren von WLAN-Einstellungen für Windows-Geräte](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

4.  Erstellen Sie ein Profil für jedes Unternehmens-VPN (siehe [Windows 10 und Windows Holographic-Geräteeinstellungen, um VPN-Verbindungen mit Intune hinzuzufügen](https://docs.microsoft.com/intune/vpn-settings-windows-10)).

## <a name="troubleshooting-certificates"></a>Fehlerbehebung für Zertifikate

Für den Fall, dass Sie überprüfen müssen, ob ein Zertifikat korrekt eingesetzt wird, verwenden Sie bitte den [Zertifikat-Manager](certificate-manager.md) auf dem Gerät, um zu überprüfen, ob Ihr Zertifikat vorhanden ist.  

>[!WARNING]
> Sie können mit MDM bereitgestellte Zertifikate zwar im Zertifikat-Manager anzeigen, aber nicht im Zertifikat-Manager deinstallieren. Sie müssen sie über MDM deinstallieren.


