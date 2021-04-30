---
title: Freigeben Ihrer HoloLens für mehrere Personen
description: Sie können HoloLens so konfigurieren, dass sie von mehreren Azure Active Directory oder von mehreren Benutzern gemeinsam genutzt wird, die ein einzelnes Konto verwenden.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308838"
---
# <a name="share-your-hololens-with-multiple-people"></a><span data-ttu-id="57e37-103">Freigeben Ihrer HoloLens für mehrere Personen</span><span class="sxs-lookup"><span data-stu-id="57e37-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="57e37-104">Es ist üblich, eine HoloLens für viele Personen zu teilen oder eine Reihe von HoloLens-Geräten gemeinsam zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="57e37-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="57e37-105">In diesem Artikel werden die verschiedenen Möglichkeiten beschrieben, wie Sie ein Gerät freigeben können.</span><span class="sxs-lookup"><span data-stu-id="57e37-105">This article describes the different ways in which you can share a device.</span></span>

## <a name="share-with-multiple-people-each-using-their-own-account"></a><span data-ttu-id="57e37-106">Freigeben für mehrere Personen, die jeweils ihr eigenes Konto verwenden</span><span class="sxs-lookup"><span data-stu-id="57e37-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="57e37-107">**Voraussetzung:** Auf dem HoloLens-Gerät muss Windows 10 Version 1803 oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="57e37-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="57e37-108">HoloLens (1. Generation) muss ebenfalls auf [Windows Holographic for Business.](hololens-upgrade-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="57e37-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="57e37-109">Wenn sie ihre eigenen Azure Active Directory-Konten (Azure AD) verwenden, können mehrere Benutzer jeweils ihre eigenen Benutzereinstellungen und Benutzerdaten auf dem Gerät behalten.</span><span class="sxs-lookup"><span data-stu-id="57e37-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="57e37-110">Um sicherzustellen, dass mehrere Personen ihre eigenen Konten auf Ihrer HoloLens verwenden können, führen Sie die folgenden Schritte aus, um sie zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="57e37-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="57e37-111">Stellen Sie sicher, dass auf dem Gerät Windows 10 Version 1803 oder höher ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="57e37-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="57e37-112">Wenn Sie ein HoloLens-Gerät (1. Generation) verwenden, aktualisieren Sie das Gerät [auf Windows Holographic for Business.](hololens1-upgrade-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="57e37-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="57e37-113">Wenn Sie das Gerät eingerichtet haben, wählen Sie **Mein Unternehmen** oder Meine Schule besitzt es aus, und melden Sie sich mit einem Azure AD an.</span><span class="sxs-lookup"><span data-stu-id="57e37-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="57e37-114">Stellen Sie nach Abschluss des Setupssicher, dass die Kontoeinstellungen (  >  **EinstellungenKonten**) **Andere Benutzer enthalten.**</span><span class="sxs-lookup"><span data-stu-id="57e37-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="57e37-115">Um HoloLens zu verwenden, folgt jeder Benutzer den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="57e37-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="57e37-116">Wenn ein anderer Benutzer das Gerät verwendet hat, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="57e37-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="57e37-117">Drücken Sie einmal den Netzschalter, um in den Standbymodus zu wechseln, und drücken Sie dann erneut den Netzschalter, um zum Sperrbildschirm zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="57e37-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="57e37-118">HoloLens 2 Benutzer können die Benutzerkachel aus dem Startmenü, um den aktuellen Benutzer abmelden zu können.</span><span class="sxs-lookup"><span data-stu-id="57e37-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="57e37-119">Verwenden Sie Azure AD Anmeldeinformationen ihres Kontos, um sich beim Gerät anzumelden.</span><span class="sxs-lookup"><span data-stu-id="57e37-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="57e37-120">Wenn Sie das Gerät zum ersten Mal verwenden, [](hololens-calibration.md) müssen Sie HoloLens auf Ihre eigenen Augen kalibrieren.</span><span class="sxs-lookup"><span data-stu-id="57e37-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="57e37-121">Um eine Liste der Gerätebenutzer anzuzeigen oder einen Benutzer vom Gerät zu entfernen, wechseln Sie zu **Einstellungen**  >  **Konten**  >  **Andere Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="57e37-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <a name="share-with-multiple-people-all-using-the-same-account"></a><span data-ttu-id="57e37-122">Freigeben für mehrere Personen, die alle das gleiche Konto verwenden</span><span class="sxs-lookup"><span data-stu-id="57e37-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="57e37-123">Mehrere Benutzer können ein HoloLens-Gerät auch freigeben, während sie ein einzelnes Benutzerkonto verwenden.</span><span class="sxs-lookup"><span data-stu-id="57e37-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="57e37-124">**Wenn ein** neuer Benutzer das Gerät auf HoloLens 2 zum ersten Mal auf den Kopf stellt (während dasselbe Konto angemeldet bleibt), fordert das Gerät den neuen Benutzer auf, die Anzeige schnell zu kalibrieren und zu personalisieren.</span><span class="sxs-lookup"><span data-stu-id="57e37-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="57e37-125">Das Gerät kann die Kalibrierungsinformationen speichern, damit das Gerät in Zukunft automatisch die Qualität und den Komfort der Anzeige der einzelnen Benutzer optimieren kann.</span><span class="sxs-lookup"><span data-stu-id="57e37-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="57e37-126">Die Benutzer müssen das Gerät nicht erneut kalibrieren.</span><span class="sxs-lookup"><span data-stu-id="57e37-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="57e37-127">**Auf HoloLens (1. Generation)** müssen Benutzer, die ein Konto freigeben, aufgefordert werden, die Neubibliothek in der Einstellungs-App vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="57e37-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="57e37-128">Weitere Informationen zur [Kalibrierung](hololens-calibration.md)finden Sie hier.</span><span class="sxs-lookup"><span data-stu-id="57e37-128">Read more about [calibration](hololens-calibration.md).</span></span>
