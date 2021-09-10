---
title: HoloLens-Sicherheitsarchitektur
description: Sicherheitsarchitektur
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: Sicherheit, HoloLens, HoloLens 2, HoloLens2-Sicherheit, Sicherheitsübersicht, Sicherheitsarchitektur, Architektur, HoloLens 2-Architektur
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428394"
---
# <a name="security-overview-and-architecture"></a>Übersicht zu Sicherheit und Architektur

Die Sicherheitsarchitektur von HoloLens 2 wurde von Grund auf so konzipiert und entwickelt, dass sie keine Sicherheitsprobleme aus älteren Versionen enthält und zugleich eine minimierte Angriffsfläche aufweist. Diese neue, innovative Architektur bietet sichere Speicherorte und erweiterte Sicherheitselemente mit Mechanismen zum Schutz von Betriebssystemen vor potenziellen Bedrohungen und Sicherheitsrisiken.

HoloLens 2 kombiniert Hardware, Software, Netzwerk und Dienste, um End-to-End-Sicherheit zu bieten und zugleich eine optimale Benutzererfahrung zu ermöglichen. Bei HoloLens 2 sind die meisten Sicherheitsfeatures jetzt automatisch aktiviert, sodass der Aufwand für die ordnungsgemäße Einrichtung und Konfiguration des Betriebssystems minimiert wird.

Windows HoloLens 2 und die Architektur des Betriebssystems bietet diese innovativen Sicherheitsfeatures:

  * **Statustrennung und -isolation**: Diese neue Architektur schützt kritische Teile des HoloLens 2-Betriebssystems vor Veränderungen – wie z. B. diejenigen, die zum Starten des Betriebssystems in einen vertrauenswürdigen Zustand erforderlich sind. Die Isolationstechnologie wird verwendet, um nicht vertrauenswürdige Apps auf einen Sandkastenbereich zu beschränken, sodass sichergestellt ist, dass sie keine Auswirkungen auf die Systemsicherheit haben. Das gesamte Betriebssystem ist in sichere Abschnitte unterteilt, wobei jeder Abschnitt durch eine Kombination unterschiedlicher Sicherheitstechnologien geschützt ist.
  
  * **Schutz der Daten**: Wenn das Gerät eines Benutzers verloren geht oder gestohlen wird, hindert HoloLens 2 nicht autorisierte Anwendungen mithilfe der BitLocker-Datenverschlüsselung daran, vertrauliche Informationen zu lesen. 
  
  * **Kennwortloses Betriebssystem**: Bei älteren, kennwortbasierten Betriebssystemen könnten Benutzer versehentlich Phishing-Angriffen ausgesetzt werden, und diese sind häufig der Grund für kompromittierte Konten. Windows Holographic for Business eliminiert die Verwendung von Kennwörtern für MSA- und Azure AD-Anmeldungen und stärkt den Schutz der Benutzeridentität mit Windows Hello™ und FIDO2-Anmeldung. 
  
    > [!NOTE]
    > Damit FIDO2 unterstützt wird, muss das Gerät Build 19041 oder höher aufweisen. 

  * **Netzwerksicherheit**: HoloLens 2 bietet dem Benutzer durch verbesserte Protokolle und Standardeinstellungen eine höhere Netzwerksicherheit.
