---
title: Verschlüsselung und Datenschutz
description: Hier erfahren Sie mehr über Verschlüsselung und Datenschutz auf HoloLens 2-Geräten, einschließlich BitLocker und Azure-Integration.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: Sicherheit, HoloLens, Verschlüsselung, Datenschutz, BitLocker-Gerät, BitLocker, bitlocker, BitLocker-Verschlüsselung, Azure-Integration,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ebe1d072f36cdf4ad9b3543882e61fa2ed4a0300
ms.sourcegitcommit: b1362ab822d1cba97fe0b3fb4e666d9b68b6adbf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "11406751"
---
# <a name="encryption-and-data-protection"></a>Verschlüsselung und Datenschutz

Verschlüsselung und Datenschutz dienen zum Schutz von Daten im Falle des Verlusts oder Diebstahl des Geräts, und verhindert nicht autorisierte Anwendungen am Zugriff auf vertrauliche Informationen.

## <a name="bitlocker-device-encryption"></a>BitLocker-Geräteverschlüsselung

Bei BitLocker handelt es sich um ein Feature zur Verschlüsselung vollständiger Volumes, um die Integrität schreibgeschützter Medien und den Datenschutz beschreibbarer Medien zu gewährleisten.  Seit seiner Entwicklung bietet BitLocker einen wirksamen Schutz gegen unbefugten Zugriff auf die Daten bei Offlineangriffen. HoloLens 2 aktiviert die BitLocker-Geräteverschlüsselung (Bitlocker Device Encryption, BDE) standardmäßig, um Daten auf dem Gerät vor jeglichem unbefugten physischen Zugriff zu schützen. Microsoft entwickelt sich ständig weiter, um den Anforderungen der Zukunft gerecht zu werden, und investiert weiterhin in diese Technologie und verbessert sie.

BDE ist ein Datenschutzfeature, das AES-XTS-256-Verschlüsselung auf allen Volumes im zustandsgetrennten Layout des Geräts verwendet. BDE bietet eine Verschlüsselung auf Geräteebene in einem zustandsgetrennten Layout. BitLocker-Geräteverschlüsselung wird auf Betriebssystem- und Festplattenvolumes automatisch aktiviert und kann auch von IT-Administratoren nicht deaktiviert werden, sodass das Gerät immer geschützt ist.

BDE-Verschlüsselungsschlüssel werden dann verwendet, um Binärdateien und die zum Booten des Geräts erforderlichen Daten transparent zu entschlüsseln. Wenn das Betriebssystemvolume entsperrt und ein System gestartet wird, kann auf andere Volumes über eine volumenspezifische Version der Schutzvorrichtung zum automatischen Entsperren zugegriffen werden. Um den Datenschutz der Benutzer zu gewährleisten, sind keine anderen Schutzvorrichtungen verfügbar, und das Laufwerk kann nur auf demselben Gerät entsperrt werden. Die Erzwingung des Schreibschutzes für erforderliche Volumes wird beim ersten Starten sofort angewendet und erzwungen. Der Bitlocker-Wiederherstellungsschlüssel wird im Lebenszyklus von HoloLens 2 nicht benötigt.

## <a name="azure-integration"></a>Azure-Integration 

Mit HoloLens 2 können Kunden ihre Geräte in Azure-Dienste integrieren. Kommunikation zwischen HoloLens 2-Geräten und Azure verwenden das TLS-Protokoll (Transport Layer Security), um Daten bei der Übertragung zu den Clouddiensten und zurück zu schützen. Dadurch werden eine starke Authentifizierung, Datenschutz von Nachrichten sowie Integrität gewährleistet. TLS 1.2 wird von allen Azure-Diensten vollständig unterstützt, und alle Dienste, bei denen Kunden nur TLS 1.2 verwenden, akzeptieren nur TLS 1.2-Datenverkehr. Die Azure-Verschlüsselungsstandards für Daten während der Übertragung werden unter [Übersicht über die Azure-Verschlüsselung](https://docs.microsoft.com/azure/security/fundamentals/encryption-overview) beschrieben. In der Azure-Dokumentation erfahren Sie mehr über [Bewährte Methoden für Azure-Datensicherheit und -Verschlüsselung](https://docs.microsoft.com/azure/security/fundamentals/data-encryption-best-practices). 

OneDrive, ein Beispiel für die Cloudintegration mit HoloLens 2, verfügt über ein Feature zum automatischen Hochladen von Dateien und Dokumenten in die Cloud, wenn eine Verbindung mit dem Internet besteht. Das Anhalten der automatischen Synchronisierung von Dateien kann nicht über die Richtlinie abgeschaltet werden, sondern ist direkt über das UX konfigurierbar. 
