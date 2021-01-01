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
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253252"
---
# <span data-ttu-id="61cc8-104">Übersicht über die Sicherheit und Architektur</span><span class="sxs-lookup"><span data-stu-id="61cc8-104">Security overview and architecture</span></span>

<span data-ttu-id="61cc8-105">Die Sicherheitsarchitektur von HoloLens 2 wurde von Grund auf so konzipiert und entwickelt, dass es keine Sicherheitsprobleme aus älteren Versionen enthält und gleichzeitig eine minimierte Angriffsfläche aufweist.</span><span class="sxs-lookup"><span data-stu-id="61cc8-105">The HoloLens 2 security architecture was designed and engineered from the ground up to be free from legacy security issues, while creating a minimized attack surface.</span></span> <span data-ttu-id="61cc8-106">Diese neue, innovative Architektur bietet sichere Speicherorte und erweiterte Sicherheitselemente mit Mechanismen zum Schutz von Betriebssystemen vor potenziellen Bedrohungen und Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="61cc8-106">This new, innovative architecture offers secure storage locations and advanced security elements, with mechanisms capable of shielding operating systems from potential threats and vulnerabilities.</span></span>

<span data-ttu-id="61cc8-107">HoloLens 2 kombiniert Hardware, Software, Netzwerk und Dienste, um End-to-End-Sicherheit zu bieten und gleichzeitig eine optimale Benutzererfahrung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="61cc8-107">HoloLens 2 combines hardware, software, networking, and services to deliver end-to-end security, while providing the user with an optimal experience.</span></span> <span data-ttu-id="61cc8-108">Bei HoloLens 2 sind die meisten Sicherheitsfeatures jetzt automatisch aktiviert, wodurch der Aufwand für die ordnungsgemäße Einrichtung und Konfiguration des Betriebssystems minimiert wird.</span><span class="sxs-lookup"><span data-stu-id="61cc8-108">With HoloLens 2, a large majority of security features are now turned on automatically, minimizing the effort required to correctly set up and configure the operating system.</span></span>

<span data-ttu-id="61cc8-109">Die Architektur von Windows HoloLens 2 und des Betriebssystems bietet die folgenden innovativen Sicherheitsfeatures:</span><span class="sxs-lookup"><span data-stu-id="61cc8-109">Windows HoloLens 2 and operating system architecture offers these innovative security features:</span></span>

  * <span data-ttu-id="61cc8-110">**Statustrennung und -isolation**: Diese neue Architektur schützt kritische Teile des HoloLens 2-Betriebssystems vor Veränderungen – wie z.B. diejenigen, die erforderlich sind, damit das Kernbetriebssystem in einen vertrauenswürdigen Status booten kann.</span><span class="sxs-lookup"><span data-stu-id="61cc8-110">**State separation and isolation**:  This new architecture protects critical portions of the HoloLens 2 operating system from change - such as those required for the core operating system to boot into a trusted state.</span></span> <span data-ttu-id="61cc8-111">Die Isolationstechnologie wird verwendet, um nicht vertrauenswürdige Apps in einem Sandkastenbereich zu beschränken, sodass sichergestellt ist, dass sie keine Auswirkungen auf die Systemsicherheit haben.</span><span class="sxs-lookup"><span data-stu-id="61cc8-111">Isolation technology is used to confine untrusted apps in a sandbox area, ensuring that they cannot impact the system security.</span></span> <span data-ttu-id="61cc8-112">Das gesamte Betriebssystem ist in sichere Abschnitte unterteilt, wobei jeder Abschnitt durch eine Kombination unterschiedlicher Sicherheitstechnologien geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="61cc8-112">The entire operating system is segmented into secure sections, with each section shielded by a combination of different security technologies.</span></span>
  
  * <span data-ttu-id="61cc8-113">**Datenschutz**: Wenn das Gerät eines Benutzers verloren geht oder gestohlen wird, hindert HoloLens 2 nicht autorisierte Anwendungen dank BitLocker-Datenverschlüsselung daran, vertrauliche Informationen zu lesen.</span><span class="sxs-lookup"><span data-stu-id="61cc8-113">**Data Protection**: If a user’s device is lost or stolen, HoloLens 2 prevents unauthorized applications from reading sensitive information by relying on BitLocker encryption of data.</span></span> 
  
  * <span data-ttu-id="61cc8-114">**Betriebssystem ohne Kennwort**: Bei älteren, kennwortbasierten Betriebssystemen könnten Benutzer versehentlich Phishing-Angriffen ausgesetzt werden, und diese sind häufig für kompromittierte Konten verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="61cc8-114">**Password-less operating system**:  Older, password-based operating systems could inadvertently expose users to phishing threats and were often responsible for compromised accounts.</span></span> <span data-ttu-id="61cc8-115">Windows Holographic for Business eliminiert die Verwendung von Kennwörtern für MSA- und Azure AD-Anmeldungen und stärkt den Schutz der Benutzeridentität mit Windows Hello™ und FIDO2-Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="61cc8-115">Windows Holographic for Business eliminates the use of passwords for MSA and Azure AD sign-in and strengthens user-identity protection with Windows Hello™ and FIDO2 sign-in.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="61cc8-116">Damit FIDO2 unterstützt wird, muss das Gerät Build 19041 oder höher aufweisen.</span><span class="sxs-lookup"><span data-stu-id="61cc8-116">To have FIDO2 support, the device must be on Build 19041 or higher.</span></span> 

  * <span data-ttu-id="61cc8-117">**Netzwerksicherheit**: HoloLens 2 bietet dem Benutzer eine höhere Netzwerksicherheit durch verbesserte Protokolle und Standardeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="61cc8-117">**Network security**: HoloLens 2 offers the user increased network security via improved protocols and default settings.</span></span>
