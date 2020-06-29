---
title: Teilen von HoloLens mit mehreren Personen
description: Sie können HoloLens so konfigurieren, dass es von mehreren Azure Active Directory-Konten oder von mehreren Benutzern, die ein einzelnes Konto verwenden, freigegeben wird.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828421"
---
# <span data-ttu-id="3817f-103">Teilen von HoloLens mit mehreren Personen</span><span class="sxs-lookup"><span data-stu-id="3817f-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="3817f-104">Es ist üblich, eine HoloLens für viele Personen freizugeben oder viele Personen mit einer Reihe von HoloLens-Geräten zu teilen.</span><span class="sxs-lookup"><span data-stu-id="3817f-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="3817f-105">In diesem Artikel werden die verschiedenen Möglichkeiten beschrieben, wie Sie ein Gerät freigeben können.</span><span class="sxs-lookup"><span data-stu-id="3817f-105">This article describes the different ways in which you can share a device.</span></span>

## <span data-ttu-id="3817f-106">Freigeben für mehrere Personen mit jeweils eigenem Konto</span><span class="sxs-lookup"><span data-stu-id="3817f-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="3817f-107">**Voraussetzung**: auf dem HoloLens-Gerät muss Windows 10, Version 1803 oder höher, ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3817f-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="3817f-108">HoloLens (1st Generation) muss ebenfalls [auf Windows holographisch for Business aktualisiert](hololens-upgrade-enterprise.md)werden.</span><span class="sxs-lookup"><span data-stu-id="3817f-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="3817f-109">Wenn Sie eigene Azure Active Directory-Konten (Azure AD) verwenden, können mehrere Benutzer jeweils ihre eigenen Benutzereinstellungen und Benutzerdaten auf dem Gerät behalten.</span><span class="sxs-lookup"><span data-stu-id="3817f-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="3817f-110">Führen Sie die folgenden Schritte aus, um sicherzustellen, dass mehrere Personen Ihre eigenen Konten auf Ihrem HoloLens verwenden können:</span><span class="sxs-lookup"><span data-stu-id="3817f-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="3817f-111">Stellen Sie sicher, dass auf dem Gerät Windows 10, Version 1803 oder höher ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3817f-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="3817f-112">Wenn Sie ein HoloLens (1st Generation)-Gerät verwenden, [Aktualisieren Sie das Gerät auf Windows holographisch for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="3817f-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="3817f-113">Wenn Sie das Gerät einrichten, wählen Sie **mein Geschäfts-oder Schul Besitzer** aus, und melden Sie sich mit einem Azure AD-Konto an.</span><span class="sxs-lookup"><span data-stu-id="3817f-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="3817f-114">Nachdem Sie das Setup abgeschlossen haben, stellen Sie sicher, dass die Kontoeinstellungen (**Einstellungs**  >  **Konten**) **andere Benutzer**umfassen.</span><span class="sxs-lookup"><span data-stu-id="3817f-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="3817f-115">Um HoloLens zu verwenden, führt jeder Benutzer die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="3817f-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="3817f-116">Wenn ein anderer Benutzer das Gerät verwendet hat, führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="3817f-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="3817f-117">Drücken Sie die Power-Taste einmal, um in den Standbymodus zu wechseln, und drücken Sie dann erneut die Power-Taste, um zum Sperrbildschirm zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="3817f-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="3817f-118">HoloLens 2 Benutzer können die Kachel "Benutzer" im Menü "Start" auswählen, um den aktuellen Benutzer abzumelden.</span><span class="sxs-lookup"><span data-stu-id="3817f-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="3817f-119">Verwenden Sie Ihre Azure AD-Kontoanmeldeinformationen, um sich beim Gerät anzumelden.</span><span class="sxs-lookup"><span data-stu-id="3817f-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="3817f-120">Wenn Sie das Gerät zum ersten Mal verwenden, müssen Sie HoloLens mit eigenen Augen [Kalibrieren](hololens-calibration.md) .</span><span class="sxs-lookup"><span data-stu-id="3817f-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="3817f-121">Wenn Sie eine Liste der Geräte Benutzer anzeigen oder einen Benutzer vom Gerät entfernen möchten, wechseln Sie zu **Einstellungen**für  >  **Accounts**  >  **andere Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="3817f-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <span data-ttu-id="3817f-122">Freigeben für mehrere Personen, die alle dasselbe Konto verwenden</span><span class="sxs-lookup"><span data-stu-id="3817f-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="3817f-123">Mehrere Benutzer können auch ein HoloLens-Gerät freigeben, während Sie ein einzelnes Benutzerkonto verwenden.</span><span class="sxs-lookup"><span data-stu-id="3817f-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="3817f-124">Wenn ein neuer Benutzer das Gerät zum ersten Mal auf dem Kopf platziert (unter Beibehaltung desselben Kontos), fordert das Gerät den neuen Benutzer **auf HoloLens 2**auf, die Anzeigeumgebung schnell zu kalibrieren und zu personalisieren.</span><span class="sxs-lookup"><span data-stu-id="3817f-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="3817f-125">Das Gerät kann die Kalibrierungsinformationen speichern, damit das Gerät in Zukunft automatisch die Qualität und den Komfort der Anzeige Erfahrung jedes Benutzers optimieren kann.</span><span class="sxs-lookup"><span data-stu-id="3817f-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="3817f-126">Die Benutzer müssen das Gerät nicht erneut kalibrieren.</span><span class="sxs-lookup"><span data-stu-id="3817f-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="3817f-127">**Bei HoloLens (1st Gen)** müssen Benutzer, die ein Konto freigeben, die erneute Kalibrierung in der Einstellungs-APP anfordern.</span><span class="sxs-lookup"><span data-stu-id="3817f-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="3817f-128">Weitere Informationen finden Sie im Artikel [Kalibrieren](hololens-calibration.md).</span><span class="sxs-lookup"><span data-stu-id="3817f-128">Read more about [calibration](hololens-calibration.md).</span></span>
