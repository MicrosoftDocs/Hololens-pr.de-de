---
title: Vorbereiten von Zertifikaten und Netzwerkprofilen für HoloLens 2
description: Hier erfahren Sie, wie Sie Zertifikate für das Netzwerk auf Mixed-Reality-Geräten mit HoloLens 2 konfigurieren, verwenden und bereitstellen, und lernen, wie Sie Probleme behandeln.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 1bfac948b493c2e55207e45042d6b022c1818969
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283436"
---
# Vorbereiten von Zertifikaten und Netzwerkprofilen für HoloLens 2

Die zertifikatbasierte Authentifizierung wird häufig von Kunden benötigt, die HoloLens 2 verwenden. Möglicherweise benötigen Sie Zertifikate für den WLAN-Zugriff, zum Herstellen einer Verbindung mit VPN-Lösungen oder für den Zugriff auf interne Ressourcen in Ihrer Organisation.

Da HoloLens 2-Geräte in der Regel mit Azure AD (Azure Active Directory) verbunden sind und über Intune oder einen anderen MDM-Anbieter verwaltet werden, müssen Sie diese Zertifikate mithilfe einer SCEP- (Simple Certificate Enrollment Protocol) oder einer PKCS-Zertifikatinfrastruktur (Public Key Cryptography Standard) bereitstellen, die in Ihre MDM-Lösung integriert ist.

## Zertifikatanforderungen
Für die Bereitstellung von Zertifikaten über eine SCEP- oder PKCS-Infrastruktur sind Stammzertifikate erforderlich. Andere Anwendungen und Dienste in Ihrer Organisation erfordern möglicherweise, dass Stammzertifikate auch für Ihre HoloLens 2-Geräte bereitgestellt werden. 

## Anforderungen an die WLAN-Konnektivität
Wenn Sie zulassen möchten, dass ein Gerät automatisch mit der für Ihr Unternehmensnetzwerk erforderlichen WLAN-Konfiguration ausgestattet wird, benötigen Sie ein WLAN-Konfigurationsprofil. Sie können Intune oder einen anderen MDM-Anbieter so konfigurieren, dass diese Profile auf Ihren Geräten bereitgestellt werden. Wenn es zum Schutz Ihres Netzwerks erforderlich ist, dass die Geräte der lokalen Domäne angehören, müssen Sie möglicherweise auch Ihre WLAN-Netzwerkinfrastruktur überprüfen, um sicherzustellen, dass sie mit HoloLens 2-Geräten kompatibel ist (HoloLens 2-Geräte sind nur in Azure AD eingebunden).

## Bereitstellen der Zertifikatinfrastruktur
Wenn noch keine SCEP- oder PKCS-Infrastruktur vorhanden ist, müssen Sie eine solche vorbereiten. Für die Unterstützung der Verwendung von SCEP- oder PKCS-Zertifikaten für die Authentifizierung erfordert Intune die Verwendung eines [Zertifikat-Connectors](https://docs.microsoft.com/mem/intune/protect/certificate-connectors).

> [!NOTE]
> Wenn Sie SCEP mit einer Microsoft-Zertifizierungsstelle verwenden, müssen Sie auch den [Registrierungsdienst für Netzwerkgeräte (Network Device, NDES)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes) konfigurieren.

Weitere Informationen finden Sie unter [Konfigurieren eines Zertifikatprofils für Ihre Geräte in Microsoft Intune](https://docs.microsoft.com/intune/certificates-configure).

## Bereitstellen von Zertifikaten und WLAN-/VPN-Profilen
Führen Sie die folgenden Schritte aus, um Zertifikate und Profile bereitzustellen:
1.  Erstellen Sie ein Profil für jedes der Stamm- und Zwischen-Zertifikate (siehe [Erstellen von Profilen für vertrauenswürdige Zertifikate](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)). Jedes dieser Profile muss eine Beschreibung mit einem Ablaufdatum im Format TT/MM/JJJJ aufweisen. **Zertifikatprofile ohne Ablaufdatum werden nicht bereitgestellt.**
1.  Erstellen Sie ein Profil für jedes SCEP- oder PKCS-Zertifikat (siehe [Erstellen eines SCEP-Zertifikatprofils oder eines PKCS-Zertifikatprofils](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)). Jedes dieser Profile muss eine Beschreibung mit einem Ablaufdatum im Format TT/MM/JJJJ aufweisen. **Zertifikatprofile ohne Ablaufdatum werden nicht bereitgestellt.**

    > [!NOTE]
    > Da HoloLens 2 von vielen als freigegebenes Gerät (mehrere Benutzer pro Gerät) angesehen wird, empfiehlt es sich, wenn möglich Gerätezertifikate anstelle von Benutzerzertifikaten für die WLAN-Authentifizierung bereitzustellen.

3.  Erstellen Sie ein Profil für jedes WLAN-Unternehmensnetzwerk (siehe [WLAN-Einstellungen für Geräte mit Windows 10 und höher](https://docs.microsoft.com/intune/wi-fi-settings-windows)). 
    > [!NOTE]
    > Es empfiehlt sich, das WLAN-Profil möglichst Gerätegruppen statt Benutzergruppen[ zuzuweisen](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign). 

    > [!TIP]
    > Sie können auch ein funktionierendes WLAN-Profil von einem Windows 10-PC in Ihrem Unternehmensnetzwerk exportieren. Mit diesem Export wird eine XML-Datei mit allen aktuellen Einstellungen erstellt. Importieren Sie dann diese Datei in Intune, und verwenden Sie sie als WLAN-Profil für Ihre HoloLens 2-Geräte. Siehe [Export und Import von WLAN-Einstellungen für Windows-Geräte](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

4.  Erstellen Sie ein Profil für jedes Unternehmens-VPN (siehe [Einstellungen für Windows 10- und Windows Holographic-Geräte zum Hinzufügen von VPN-Verbindungen mit Intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).

## Problembehandlung bei Zertifikaten

Für den Fall, dass Sie überprüfen müssen, ob ein Zertifikat korrekt eingesetzt wird, verwenden Sie den [Zertifikat-Manager](certificate-manager.md) auf dem Gerät, um zu überprüfen, ob Ihr Zertifikat vorhanden ist.  


