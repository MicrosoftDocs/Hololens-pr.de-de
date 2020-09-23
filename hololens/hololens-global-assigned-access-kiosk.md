---
title: Global zugewiesener Zugriff
description: Leitfaden für die Verwendung von Oma-URI für global zugewiesene Zugriff-Kioske
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: HoloLens, HoloLens 2, zugewiesener Zugriff, Kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: c2be1123d0e8a09d6955fb6e5da782daebc96bcf
ms.sourcegitcommit: 89ce6cdc0fc6d70a88217791c5f6d613778af614
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052624"
---
# <span data-ttu-id="dbd5c-104">Global zugewiesener Zugriff – Kiosk</span><span class="sxs-lookup"><span data-stu-id="dbd5c-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="dbd5c-105">Dieses Feature konfiguriert das Hololens 2-Gerät für den Multi-App-Kioskmodus, der auf Systemebene anwendbar ist, keine Affinität zu einer anderen Identität des Systems hat und für jeden gilt, der sich auf dem Gerät anmeldet.</span><span class="sxs-lookup"><span data-stu-id="dbd5c-105">This feature configures Hololens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> 

> [!NOTE]
> <span data-ttu-id="dbd5c-106">Dieses Feature ist derzeit nur in Windows-Insider-Builds verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dbd5c-106">This feature is currently only avalible in Windows Insider builds.</span></span> <span data-ttu-id="dbd5c-107">Wenn Sie dieses Feature ausprobieren möchten, bevor es in HoloLens-Versionen allgemein verfügbar sein wird, lesen Sie weitere Informationen zu [Windows Insider-](hololens-insider.md)-Builds.</span><span class="sxs-lookup"><span data-stu-id="dbd5c-107">If you would like to try this feature before it is generally avalible in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>
 
## <span data-ttu-id="dbd5c-108">Wie verwende ich dies in InTune?</span><span class="sxs-lookup"><span data-stu-id="dbd5c-108">How to use this in Intune?</span></span> 

> [!NOTE]
> <span data-ttu-id="dbd5c-109">Bitte beachten Sie die mit "<!-" markierten Bereiche.</span><span class="sxs-lookup"><span data-stu-id="dbd5c-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="dbd5c-110">In diesen Bereichen müssen Sie Änderungen vornehmen, die Ihren Voreinstellungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="dbd5c-110">These areas will require you to make modifications based on your preferences.</span></span> 

1.  <span data-ttu-id="dbd5c-111">Erstellen Sie ein benutzerdefiniertes Konfigurationsprofil für OMA-URI-Geräte wie folgt, und wenden Sie es auf die HoloLens-Gerätegruppe an: ![Global zugewiesene Zugriff Oma-URI in InTune</span><span class="sxs-lookup"><span data-stu-id="dbd5c-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group: ![Global Assigned Access OMA-URI in Intune</span></span>](images/global-assigned-access-omauri.png)

2.  <span data-ttu-id="dbd5c-112">Für Wert, aktualisieren und einfügen des folgenden Inhalts:</span><span class="sxs-lookup"><span data-stu-id="dbd5c-112">For value, update and paste following content:</span></span> 

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <span data-ttu-id="dbd5c-113">Wie verwende ich das im Windows Konfigurations-Designer?</span><span class="sxs-lookup"><span data-stu-id="dbd5c-113">How to use this in Windows Configuration Designer?</span></span> 
 
1.  <span data-ttu-id="dbd5c-114">Aktualisieren und speichern Sie den oben erwähnten XML-BLOB als XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="dbd5c-114">Update and save XML blob mentioned above as XML file.</span></span> 

2.  <span data-ttu-id="dbd5c-115">Führen Sie die Schritte in [Verwenden eines Bereitstellungspakets aus, um einen Single-App- oder Multi-App-Kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)einzurichten, insbesondere den Abschnitt Prov.</span><span class="sxs-lookup"><span data-stu-id="dbd5c-115">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="dbd5c-116">Paket, Schritt 2 – Fügen Sie die Kiosk-Konfigurations-XML-Datei zu einem Bereitstellungspaket hinzu und verweisen Sie auf die XML-Datei, die im vorherigen Schritt gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="dbd5c-116">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span> 

## <span data-ttu-id="dbd5c-117">Kann ich eine Konfiguration erstellen, bei der eine globale Konfiguration für alle und eine separate Konfiguration für 1 AAD-Konto oder eine AAD-Gruppe gilt?</span><span class="sxs-lookup"><span data-stu-id="dbd5c-117">Can I create a configuration where global applies to everyone and separate configuration applies to 1 AAD account or AAD group?</span></span> 

<span data-ttu-id="dbd5c-118">Ja, weitere Informationen dazu finden Sie im folgenden Beispiel-XML-BLOB.</span><span class="sxs-lookup"><span data-stu-id="dbd5c-118">Yes, please refer to the example XML blob below.</span></span> <span data-ttu-id="dbd5c-119">Das global zugewiesene Zugriff-Profil wird auf HoloLens angewendet, wenn ein bestimmtes Profil für den angemeldeten Benutzer nicht gefunden wird. Daher ist dies die Standardkonfiguration für den Kioskmodus für angemeldete Benutzer.</span><span class="sxs-lookup"><span data-stu-id="dbd5c-119">Global Assigned Access profile is applied on Hololens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span> <span data-ttu-id="dbd5c-120">Hier ist ein Beispiel für die Verwendung von XML-BLOB:</span><span class="sxs-lookup"><span data-stu-id="dbd5c-120">Here is an example of XML blob to be used:</span></span> 

> [!NOTE]
> <span data-ttu-id="dbd5c-121">Bitte beachten Sie die mit <! markierten Bereiche. In diesen Bereichen müssen Sie Änderungen vornehmen, die Ihren Einstellungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="dbd5c-121">Please be aware of the highlighted areas marked with <!-  these areas will require you to make modifications based on your preferences.</span></span> 

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <span data-ttu-id="dbd5c-122">Ausschließen von DeviceOwners aus dem globalen zugewiesenen Access-Profil</span><span class="sxs-lookup"><span data-stu-id="dbd5c-122">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="dbd5c-123">Diese Funktion ermöglicht es einem Benutzer, der als "[Gerätebesitzer](security-adminless-os.md)" betrachtet wird, auf Hololens, von dem globalen zugewiesenen Zugriff auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="dbd5c-123">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on Hololens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="dbd5c-124">Um dieses Feature nutzen zu können, stellen Sie sicher, dass in der XML-BLOB-Konfiguration für mehrere-App-Kiosks hervorgehobene Zeilen hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="dbd5c-124">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span> 

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::
 
