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
ms.openlocfilehash: f91b77be846b585de8d89c17e516923f97304d57
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253202"
---
# <span data-ttu-id="854d7-104">Global zugewiesener Zugriff – Kiosk</span><span class="sxs-lookup"><span data-stu-id="854d7-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="854d7-105">Dieses Feature konfiguriert das HoloLens 2-Gerät für den Multi-App-Kioskmodus, der auf Systemebene anwendbar ist, keine Affinität zu einer anderen Identität des Systems hat und für jeden gilt, der sich auf dem Gerät anmeldet.</span><span class="sxs-lookup"><span data-stu-id="854d7-105">This feature configures HoloLens 2 device for multiple app kiosk mode, which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span>

> [!NOTE]
> <span data-ttu-id="854d7-106">Dieses Feature ist derzeit nur in Windows-Insider-Builds verfügbar.</span><span class="sxs-lookup"><span data-stu-id="854d7-106">This feature is currently only available in Windows Insider builds.</span></span> <span data-ttu-id="854d7-107">Wenn Sie dieses Feature ausprobieren möchten, bevor es in HoloLens-Versionen allgemein verfügbar sein wird, lesen Sie weitere Informationen zu [Windows-Insider-](hololens-insider.md)-Builds.</span><span class="sxs-lookup"><span data-stu-id="854d7-107">If you would like to try this feature before it is generally available in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>

## <span data-ttu-id="854d7-108">Zur Verwendung des global zugewiesenen Zugriffs in Intune.</span><span class="sxs-lookup"><span data-stu-id="854d7-108">How to use Global Assigned Access in Intune?</span></span>

> [!NOTE]
> <span data-ttu-id="854d7-109">Bitte beachten Sie die mit "<!-" markierten Bereiche.</span><span class="sxs-lookup"><span data-stu-id="854d7-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="854d7-110">In diesen Bereichen müssen Sie Änderungen vornehmen, die Ihren Voreinstellungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="854d7-110">These areas will require you to make modifications based on your preferences.</span></span>

1. <span data-ttu-id="854d7-111">Erstellen Sie wie folgt ein benutzerdefiniertes OMA URI-Gerätekonfigurationsprofil und wenden Sie es auf die HoloLens-Gerätegruppe an:</span><span class="sxs-lookup"><span data-stu-id="854d7-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span>

    <span data-ttu-id="854d7-112">URI-Wert: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="854d7-112">URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

    > [!div class="mx-imgBorder"]
    > ![Globaler zugewiesener Zugriff OMA-URI in Intune](images/global-assigned-access-omauri.png)

2. <span data-ttu-id="854d7-114">Für Wert, aktualisieren und einfügen des folgenden Inhalts:</span><span class="sxs-lookup"><span data-stu-id="854d7-114">For value, update and paste following content:</span></span>

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <span data-ttu-id="854d7-115">Wie verwende ich den global zugewiesenen Zugriff im Windows Configuration Designer?</span><span class="sxs-lookup"><span data-stu-id="854d7-115">How to use Global Assigned Access in Windows Configuration Designer?</span></span>

1. <span data-ttu-id="854d7-116">Aktualisieren und speichern Sie den oben erwähnten XML-BLOB als XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="854d7-116">Update and save XML blob mentioned above as XML file.</span></span> 

2. <span data-ttu-id="854d7-117">Führen Sie die Schritte in [Verwenden eines Bereitstellungspakets aus, um einen Single-App- oder Multi-App-Kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)einzurichten, insbesondere den Abschnitt Prov.</span><span class="sxs-lookup"><span data-stu-id="854d7-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="854d7-118">Paket, Schritt 2 – Fügen Sie die Kiosk-Konfigurations-XML-Datei zu einem Bereitstellungspaket hinzu und verweisen Sie auf die XML-Datei, die im vorherigen Schritt gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="854d7-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span>

## <span data-ttu-id="854d7-119">Kann ich eine Konfiguration erstellen, bei der eine globale Konfiguration für alle und eine separate Konfiguration für 1 Azure AD-Konto oder eine Azure AD-Gruppe gilt?</span><span class="sxs-lookup"><span data-stu-id="854d7-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 Azure AD account or Azure AD group?</span></span> 

<span data-ttu-id="854d7-120">Ja, weitere Informationen dazu finden Sie im folgenden Beispiel-XML-BLOB.</span><span class="sxs-lookup"><span data-stu-id="854d7-120">Yes, refer to the example XML blob below.</span></span> <span data-ttu-id="854d7-121">Das global zugewiesene Zugriff-Profil wird auf HoloLens angewendet, wenn ein bestimmtes Profil für den angemeldeten Benutzer nicht gefunden wird. Daher ist dies die Standardkonfiguration für den Kioskmodus für angemeldete Benutzer.</span><span class="sxs-lookup"><span data-stu-id="854d7-121">Global Assigned Access profile is applied on HoloLens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span>
<span data-ttu-id="854d7-122">Hier ist ein Beispiel für die Verwendung von XML-BLOB:</span><span class="sxs-lookup"><span data-stu-id="854d7-122">Here is an example of XML blob to be used:</span></span>

> [!NOTE]
> <span data-ttu-id="854d7-123">Bitte beachten Sie die mit `<!-` gekennzeichneten Bereiche.</span><span class="sxs-lookup"><span data-stu-id="854d7-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="854d7-124">In diesen Bereichen müssen Sie Änderungen vornehmen, die Ihren Voreinstellungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="854d7-124">These areas will require you to make modifications based on your preferences.</span></span>

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <span data-ttu-id="854d7-125">Ausschließen von DeviceOwners aus dem globalen zugewiesenen Access-Profil</span><span class="sxs-lookup"><span data-stu-id="854d7-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="854d7-126">Diese Funktion macht es möglich, einen Benutzer, der auf HoloLens als "[Gerätebesitzer](security-adminless-os.md)" betrachtet wird, von dem global zugewiesenen Zugriff auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="854d7-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on HoloLens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="854d7-127">Um dieses Feature nutzen zu können, stellen Sie sicher, dass in der XML-BLOB-Konfiguration für mehrere-App-Kiosks hervorgehobene Zeilen hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="854d7-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span>

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <span data-ttu-id="854d7-128">Zusätzliche Beispiele für den global zugewiesenen Zugriff</span><span class="sxs-lookup"><span data-stu-id="854d7-128">Additional Global Assigned Access Examples</span></span>

<span data-ttu-id="854d7-129">Dies ist ein Beispiel für einen global zugewiesenen Zugriffskiosk. Wenn sich ein Benutzer dort anmeldet, steht ihm ein Multi-App-Kiosk mit der Einstellungen-App, Feedback-Hub und Microsoft Edge zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="854d7-129">This is an example Global Assigned Access kiosk that when any user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

<span data-ttu-id="854d7-130">Bei diesem Beispiel handelt es sich um einen global zugewiesenen Zugriffskiosk, der den Gerätebesitzer ausschließt. Wenn sich ein anderer Azure AD-Benutzer dort anmeldet, steht ihm ein Multi-App-Kiosk mit der Einstellungen-App, Feedback-Hub und Microsoft Edge zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="854d7-130">This example is a Global Assigned Access kiosk that excludes the device owner, when any other Azure AD user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span> <span data-ttu-id="854d7-131">Dieser Kiosk enthält auch eine sekundäre Kiosk-Konfiguration für ein Besucherkonto, bei dem sich alle Benutzer auf dem Sperrbildschirm anmelden können.</span><span class="sxs-lookup"><span data-stu-id="854d7-131">This kiosk also includes a secondary kiosk configuration for a Visitor account, which may be signed into by anyone on the lock screen.</span></span> <span data-ttu-id="854d7-132">Wenn sich ein Benutzer beim Besucherkonto anmeldet, steht ihm ein Multi-App-Kiosk zur Verfügung, der nur die Feedback-Hub-App enthält.</span><span class="sxs-lookup"><span data-stu-id="854d7-132">When a user signs into the Visitor account they will have a multi-app kiosk that only has the Feedback Hub app.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
