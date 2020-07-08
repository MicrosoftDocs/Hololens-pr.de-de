---
title: Verbessern der Grafikqualität und des Komforts
description: Die Kalibrierung Ihres Pupillenabstands (Interpupillary Distance, IPD) kann die Qualität der visuellen Elemente verbessern. Sowohl HoloLens- als auch Windows Mixed Reality-immersive Headsets bieten Möglichkeiten zum Anpassen des IPD.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
keywords: Kalibrierung, Komfort, visuelle Elemente, Qualität, IPD
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f2c8afffdc24eedf9cb6b462448f5ed6ffc8d5d
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828128"
---
# <span data-ttu-id="0eda3-105">Verbessern der Grafikqualität und des Komforts</span><span class="sxs-lookup"><span data-stu-id="0eda3-105">Improve visual quality and comfort</span></span>

<span data-ttu-id="0eda3-106">HoloLens 2 und HoloLens (1. Generation) funktionieren beide besser, wenn sie spezifisch für Ihre Augen kalibriert werden.</span><span class="sxs-lookup"><span data-stu-id="0eda3-106">HoloLens 2 and HoloLens (1st gen) both work better when they're calibrated to your unique eyes.</span></span>

<span data-ttu-id="0eda3-107">Beide Geräte müssen zwar für eine optimale Darstellung des Hologramms kalibriert werden, verwenden jedoch unterschiedliche Kalibrierungstechnologien und -techniken.</span><span class="sxs-lookup"><span data-stu-id="0eda3-107">While both devices need to calibrate for the best hologram viewing experience, they use different calibration technologies and techniques.</span></span>  <span data-ttu-id="0eda3-108">Wechseln Sie zu [HoloLens 2 Kalibrierung](#calibrating-your-hololens-2) oder [HoloLens (1. Generation) Kalibrierung](#calibrating-your-hololens-1st-gen).</span><span class="sxs-lookup"><span data-stu-id="0eda3-108">Jump to [HoloLens 2 calibration](#calibrating-your-hololens-2) or [HoloLens (1st gen) calibration](#calibrating-your-hololens-1st-gen).</span></span>

## <span data-ttu-id="0eda3-109">Kalibrieren Ihrer HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="0eda3-109">Calibrating your HoloLens 2</span></span>

<span data-ttu-id="0eda3-110">HoloLens 2 verwendet die Eye Tracking-Technologie, um das Sehen von und die Interaktion mit der virtuellen Umgebung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="0eda3-110">HoloLens 2 uses eye-tracking technology to improve your experience seeing and interacting with the virtual environment.</span></span> <span data-ttu-id="0eda3-111">Durch die Kalibrierung der HoloLens 2 wird sichergestellt, dass Ihre Augen (und die Augen aller anderen Benutzer des Geräts) genau nachverfolgt werden können.</span><span class="sxs-lookup"><span data-stu-id="0eda3-111">Calibrating the HoloLens 2 ensures that it can accurately track your eyes (and the eyes of anyone else who uses the device).</span></span> <span data-ttu-id="0eda3-112">Es hilft außerdem beim Benutzerkomfort, der Hologramm-Ausrichtung und der Hand Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="0eda3-112">It also helps with user comfort, hologram alignment, and hand tracking.</span></span> <span data-ttu-id="0eda3-113">Nach der Kalibrierung werden Hologramme korrekt angezeigt, auch wenn sich das Visier auf Ihrem Kopf verschiebt.</span><span class="sxs-lookup"><span data-stu-id="0eda3-113">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

<span data-ttu-id="0eda3-114">HoloLens 2 fordert einen Benutzer auf, das Gerät unter den folgenden Umständen zu kalibrieren:</span><span class="sxs-lookup"><span data-stu-id="0eda3-114">HoloLens 2 prompts a user to calibrate the device under the following circumstances:</span></span>

- <span data-ttu-id="0eda3-115">Der Benutzer verwendet das Gerät zum ersten Mal</span><span class="sxs-lookup"><span data-stu-id="0eda3-115">The user is using the device for the first time</span></span>
- <span data-ttu-id="0eda3-116">Der Benutzer hat den Kalibrierungsvorgang zuvor deaktiviert</span><span class="sxs-lookup"><span data-stu-id="0eda3-116">The user previously opted out of the calibration process</span></span>
- <span data-ttu-id="0eda3-117">Der Kalibrierungsvorgang war bei der letzten Verwendung durch den Benutzer nicht erfolgreich</span><span class="sxs-lookup"><span data-stu-id="0eda3-117">The calibration process did not succeed the last time the user used the device</span></span>
- <span data-ttu-id="0eda3-118">Der Benutzer hat seine Kalibrierungsprofile gelöscht.</span><span class="sxs-lookup"><span data-stu-id="0eda3-118">The user has deleted their calibration profiles</span></span>
- <span data-ttu-id="0eda3-119">Das Gerät wird deaktiviert und wieder aktiviert, und es gelten die vorstehenden Umstände.</span><span class="sxs-lookup"><span data-stu-id="0eda3-119">The device is taken off and put back on and any of the above circumstances apply</span></span> 


![Aufforderung zur Kalibrierung](./images/07-et-adjust-for-your-eyes.png)

<span data-ttu-id="0eda3-121">Während dieses Vorgangs sehen Sie sich eine Reihe von Zielen (Edelsteinen) an.</span><span class="sxs-lookup"><span data-stu-id="0eda3-121">During this process, you'll look at a set of targets (gems).</span></span> <span data-ttu-id="0eda3-122">Es ist in Ordnung, wenn Sie während der Kalibrierung blinzeln oder die Augen schließen. Versuchen Sie sich jedoch auf die Edelsteine zu konzentrieren, und nicht auf andere Gegenstände im Raum.</span><span class="sxs-lookup"><span data-stu-id="0eda3-122">It's fine if you blink during calibration, but try to stay focused on the gems instead of other objects in the room.</span></span>  <span data-ttu-id="0eda3-123">Auf diese Weise kann HoloLens Ihre Augenposition ermitteln, um Ihre holografische Welt darzustellen.</span><span class="sxs-lookup"><span data-stu-id="0eda3-123">This allows HoloLens to learn about your eye position to render your holographic world.</span></span>

![Aufforderung zur Kalibrierung](./images/07-et-hold-head-still.png)

![Aufforderung zur Kalibrierung](./images/08-et-gems.png)

![Aufforderung zur Kalibrierung](./images/09-et-adjusting.png)

<span data-ttu-id="0eda3-127">Wenn die Kalibrierung erfolgreich war, wird ein Erfolgsbildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0eda3-127">If calibration was successful, you'll see a success screen.</span></span>  <span data-ttu-id="0eda3-128">Wenn dies nicht der Fall ist, lesen Sie [hier](#troubleshooting-hololens-2-calibration) mehr über die Diagnose von Kalibrierungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="0eda3-128">If not, read more about diagnosing calibration failures [here](#troubleshooting-hololens-2-calibration).</span></span>

![Aufforderung zur Kalibrierung](./images/10-et-success.png)

### <span data-ttu-id="0eda3-130">Kalibrierung beim Freigeben eines Geräts oder einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="0eda3-130">Calibration when sharing a device or session</span></span>

<span data-ttu-id="0eda3-131">Mehrere Benutzer können ein HoloLens 2-Gerät gemeinsam nutzen, ohne dass jede Person die Geräteeinrichtung durchführen muss.</span><span class="sxs-lookup"><span data-stu-id="0eda3-131">Multiple users can share a HoloLens 2 device, without a need for each person to go through device setup.</span></span> <span data-ttu-id="0eda3-132">Wenn ein neuer Benutzer das Gerät zum ersten Mal aufsetzt, fordert HoloLens 2 ihn automatisch auf, die visuellen Elemente zu kalibrieren.</span><span class="sxs-lookup"><span data-stu-id="0eda3-132">When a new user puts the device on their head for the first time, HoloLens 2 automatically prompts the user to calibrate visuals.</span></span> <span data-ttu-id="0eda3-133">Wenn ein Benutzer, der zuvor die visuellen Elemente kalibriert hat, das Gerät aufsetzt, passt die Anzeige die Qualität sowie die komfortable Anzeigeumgebung nahtlos an.</span><span class="sxs-lookup"><span data-stu-id="0eda3-133">When a user that has previously calibrated visuals puts the device on their head, the display seamlessly adjusts for quality and a comfortable viewing experience.</span></span>  

### <span data-ttu-id="0eda3-134">Manuelles Starten des Kalibrierungsvorgangs</span><span class="sxs-lookup"><span data-stu-id="0eda3-134">Manually starting the calibration process</span></span>

1. <span data-ttu-id="0eda3-135">Verwenden Sie die Startgeste, um das [**Startmenü**](hololens2-basic-usage.md#start-gesture) zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0eda3-135">Use the start gesture to open the [**Start** menu](hololens2-basic-usage.md#start-gesture).</span></span>
1. <span data-ttu-id="0eda3-136">Wenn die Einstellungs-App nicht an **Start** angeheftet ist, wählen Sie **Alle Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="0eda3-136">If the Settings app isn't pinned to **Start**, select **All Apps**.</span></span>
1. <span data-ttu-id="0eda3-137">Wählen Sie **Einstellungen** aus, und wählen Sie dann **System** > **Kalibrierung** > **Kalibrierung der Augen** > **Kalibrierung der Augen ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="0eda3-137">Select **Settings**, and then select **System** > **Calibration** > **Eye Calibration** > **Run eye calibration**.</span></span>

   ![Die Einstellungs-App mit der Option „Kalibrierung der Augen ausführen”](./images/C-Settings.Calibration.png)

### <span data-ttu-id="0eda3-139">Problembehandlung bei der HoloLens 2-Kalibrierung</span><span class="sxs-lookup"><span data-stu-id="0eda3-139">Troubleshooting HoloLens 2 calibration</span></span>

<span data-ttu-id="0eda3-140">Die Kalibrierung sollte für die meisten Menschen funktionieren, doch es gibt Fälle, in denen die Kalibrierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="0eda3-140">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="0eda3-141">Mögliche Ursachen für Kalibrierungsfehler sind unter anderem:</span><span class="sxs-lookup"><span data-stu-id="0eda3-141">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="0eda3-142">Abgelenkt werden und den Kalibrierungszielen nicht folgen</span><span class="sxs-lookup"><span data-stu-id="0eda3-142">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="0eda3-143">Schmutziges oder zerkratztes Visier oder nicht richtig positioniertes Visier</span><span class="sxs-lookup"><span data-stu-id="0eda3-143">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="0eda3-144">Schmutzige oder verkratzte Brille</span><span class="sxs-lookup"><span data-stu-id="0eda3-144">Dirty or scratched glasses</span></span>
- <span data-ttu-id="0eda3-145">Bestimmte Arten von Kontaktlinsen und Brillen (farbige Kontaktlinsen, einige torische Kontaktlinsen, IR-Schutzbrillen, einige hochwertige, verschreibungspflichtige Brillen, Sonnenbrillen oder Ähnliches)</span><span class="sxs-lookup"><span data-stu-id="0eda3-145">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="0eda3-146">Stärkeres Make-up und einige Wimpernverlängerungen</span><span class="sxs-lookup"><span data-stu-id="0eda3-146">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="0eda3-147">Haare oder dicke Brillenfassungen, wenn sie das Gerät daran hindern, Ihre Augen zu sehen</span><span class="sxs-lookup"><span data-stu-id="0eda3-147">Hair or thick eyeglass frames if they are blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="0eda3-148">Bestimmte Augenphysiologie, Augenleiden oder Augenchirurgie wie schmale Augen, lange Wimpern, Amblyopie, Nystagmus, einige Fälle von LASIK oder andere Augenoperationen</span><span class="sxs-lookup"><span data-stu-id="0eda3-148">Certain eye physiology, eye conditions or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="0eda3-149">Wenn die Kalibrierung nicht erfolgreich ist, versuchen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0eda3-149">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="0eda3-150">Reinigen Sie das Visier des Geräts</span><span class="sxs-lookup"><span data-stu-id="0eda3-150">Cleaning your device visor</span></span>
- <span data-ttu-id="0eda3-151">Reinigen Sie Ihre Brille</span><span class="sxs-lookup"><span data-stu-id="0eda3-151">Cleaning your glasses</span></span>
- <span data-ttu-id="0eda3-152">Drücken Sie das Visier Ihres Geräts so nah wie möglich an Ihre Augen</span><span class="sxs-lookup"><span data-stu-id="0eda3-152">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="0eda3-153">Räumen Sie Gegenstände aus dem Weg des Visiers (z. B. Haare)</span><span class="sxs-lookup"><span data-stu-id="0eda3-153">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="0eda3-154">Schalten Sie Licht in Ihrem Zimmer ein oder weichen Sie direktem Sonnenlicht aus</span><span class="sxs-lookup"><span data-stu-id="0eda3-154">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="0eda3-155">Wenn Sie alle Richtlinien befolgt haben und die Kalibrierung weiterhin fehlschlägt, können Sie die Eingabeaufforderung zur Kalibrierung unter Einstellungen deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0eda3-155">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="0eda3-156">Bitte teilen Sie uns auch im [Feedback-Hub](hololens-feedback.md) Ihre Meinung mit.</span><span class="sxs-lookup"><span data-stu-id="0eda3-156">Please also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="0eda3-157">Beachten Sie, dass das Einstellen des IPD für HoloLens 2 nicht anwendbar ist, da die Augenpositionen vom System berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="0eda3-157">Note that setting IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span> 

### <span data-ttu-id="0eda3-158">Kalibrierungsdaten und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="0eda3-158">Calibration data and security</span></span>

<span data-ttu-id="0eda3-159">Kalibrierinformationen werden lokal auf dem Gerät gespeichert und sind nicht mit Kontoinformationen verknüpft.</span><span class="sxs-lookup"><span data-stu-id="0eda3-159">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="0eda3-160">Es gibt keine Aufzeichnung darüber, wer das Gerät ohne Kalibrierung verwendet hat.</span><span class="sxs-lookup"><span data-stu-id="0eda3-160">There is no record of who has used the device without calibration.</span></span> <span data-ttu-id="0eda3-161">Dies bedeutet, dass neue Benutzer bei der ersten Verwendung des Geräts aufgefordert werden, visuelle Elemente zu kalibrieren, sowie Benutzer, die zuvor die Kalibrierung deaktiviert haben oder wenn die Kalibrierung nicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="0eda3-161">This mean new users will get prompted to calibrate visuals when they use the device for the first time, as well as users who opted out of calibration previously or if calibration was unsuccessful.</span></span>

<span data-ttu-id="0eda3-162">Auf dem Gerät können bis zu 50-Kalibrierprofile lokal gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="0eda3-162">The device can locally store up to 50 calibration profiles.</span></span> <span data-ttu-id="0eda3-163">Wenn diese Zahl erreicht ist, löscht das Gerät automatisch das älteste nicht verwendete Profil.</span><span class="sxs-lookup"><span data-stu-id="0eda3-163">After this number is reached, the device automatically deletes the oldest unused profile.</span></span>

<span data-ttu-id="0eda3-164">Kalibrierinformationen können unter **Einstellungen** > **Datenschutz** > **Eyetracker** zu jeder Zeit vom Gerät gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="0eda3-164">Calibration information can always be deleted from the device in **Settings** > **Privacy** > **Eye tracker**.</span></span>  

### <span data-ttu-id="0eda3-165">Kalibrierung deaktivieren</span><span class="sxs-lookup"><span data-stu-id="0eda3-165">Disable calibration</span></span>

<span data-ttu-id="0eda3-166">Sie können die Aufforderung zur Kalibrierung auch deaktivieren, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="0eda3-166">You can also disable the calibration prompt by following these steps:</span></span>

1. <span data-ttu-id="0eda3-167">Wählen Sie **Einstellungen** > **System** > **Kalibrierung** aus.</span><span class="sxs-lookup"><span data-stu-id="0eda3-167">Select **Settings** > **System** > **Calibration**.</span></span>
1. <span data-ttu-id="0eda3-168">Deaktivieren Sie die Option **Wenn eine neue Person diese HoloLens verwendet, automatische Aufforderung zur Ausführung der Augenkalibrierung**.</span><span class="sxs-lookup"><span data-stu-id="0eda3-168">Turn off **When a new person uses this HoloLens, automatically ask to run eye calibration**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0eda3-169">Diese Einstellung kann die Qualität und den Komfort der Hologrammwiedergabe beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="0eda3-169">This setting may adversely affect hologram rendering quality and comfort.</span></span>  <span data-ttu-id="0eda3-170">Wenn Sie diese Einstellung deaktivieren, funktionieren Features, die von Eye Tracking abhängig sind (z.B. Textbildlauf), nicht mehr in immersiven Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="0eda3-170">When you turn off this setting, features that depend on eye tracking (such as text scrolling) no longer work in immersive applications.</span></span>

### <span data-ttu-id="0eda3-171">HoloLens 2 Eye Tracking-Technologie</span><span class="sxs-lookup"><span data-stu-id="0eda3-171">HoloLens 2 eye-tracking technology</span></span>

<span data-ttu-id="0eda3-172">Das Gerät verwendet seine Eye Tracking-Technologie, um die Anzeigequalität zu verbessern und um sicherzustellen, dass alle Hologramme exakt und bequem in 3D positioniert werden können.</span><span class="sxs-lookup"><span data-stu-id="0eda3-172">The device uses its eye-tracking technology to improve display quality, and to ensure that all holograms are positioned accurately and comfortable to view in 3D.</span></span> <span data-ttu-id="0eda3-173">Da die Augen als Orientierungspunkte verwendet werden, kann sich das Gerät an jeden Benutzer anpassen und seine visuellen Elemente optimieren, wenn das Headset während der Verwendung geringfügig verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="0eda3-173">Because it uses the eyes as landmarks, the device can adjust itself for every user and tune its visuals as the headset shifts slightly throughout use.</span></span>  <span data-ttu-id="0eda3-174">Alle Anpassungen erfolgen im Handumdrehen, ohne die Notwendigkeit einer manuellen Einstellung.</span><span class="sxs-lookup"><span data-stu-id="0eda3-174">All adjustments happen on the fly without a need for manual tuning.</span></span>
> [!NOTE]
> <span data-ttu-id="0eda3-175">Das Einstellen des IPD ist für HoloLens 2 nicht anwendbar, da die Augenpositionen vom System berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="0eda3-175">Setting the IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span>

<span data-ttu-id="0eda3-176">HoloLens-Anwendungen verwenden Eye Tracking, um in Echtzeit nachzuverfolgen, wo Sie hinschauen.</span><span class="sxs-lookup"><span data-stu-id="0eda3-176">HoloLens applications use eye tracking to track where you are looking in real time.</span></span> <span data-ttu-id="0eda3-177">Dies ist die wichtigste Funktion, die Entwickler nutzen können, um eine völlig neue Ebene von Kontext, menschlichem Verständnis und Interaktionen innerhalb der holographischen Erfahrung zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="0eda3-177">This is the main capability developers can leverage to enable a whole new level of context, human understanding and interactions within the Holographic experience.</span></span> <span data-ttu-id="0eda3-178">Entwickler müssen nichts unternehmen, um diese Funktion zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="0eda3-178">Developers don’t need to do anything to leverage this capability.</span></span>

## <span data-ttu-id="0eda3-179">Kalibrieren Ihrer HoloLens (1. Generation)</span><span class="sxs-lookup"><span data-stu-id="0eda3-179">Calibrating your HoloLens (1st gen)</span></span>

<span data-ttu-id="0eda3-180">HoloLens (1. Generation) passt die Anzeige von Hologrammen entsprechend dem [Pupillenabstand](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD) an.</span><span class="sxs-lookup"><span data-stu-id="0eda3-180">HoloLens (1st gen) adjusts hologram display according to the your [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD).</span></span> <span data-ttu-id="0eda3-181">Wenn der IPD nicht genau ist, erscheinen Hologramme möglicherweise instabil oder in einer falschen Entfernung.</span><span class="sxs-lookup"><span data-stu-id="0eda3-181">If the IPD is not accurate, holograms may appear unstable or at an incorrect distance.</span></span> <span data-ttu-id="0eda3-182">Sie können die Qualität Ihrer visuellen Elemente verbessern, indem Sie das Gerät auf Ihren Pupillenabstand (IPD) kalibrieren.</span><span class="sxs-lookup"><span data-stu-id="0eda3-182">You can improve the quality of your visuals by calibrating the device to your interpupillary distance (IPD).</span></span>

<span data-ttu-id="0eda3-183">Beim Einrichten Ihrer Hololens (1. Generation) werden Sie aufgefordert, Ihre visuellen Elemente zu kalibrieren, nachdem Cortana sich vorgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="0eda3-183">When you set up your Hololens (1st gen) device, it prompts to calibrate your visuals after Cortana introduces herself.</span></span> <span data-ttu-id="0eda3-184">Es wird empfohlen, den Kalibrierungsvorgang während dieser Einrichtungsphase abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0eda3-184">It's recommended that you complete the calibration step during this setup phase.</span></span> <span data-ttu-id="0eda3-185">Sie können ihn jedoch überspringen, indem Sie warten, bis Cortana Sie auffordert, und dann „Überspringen” sagen.</span><span class="sxs-lookup"><span data-stu-id="0eda3-185">However you can skip it by waiting until Cortana prompts you and then saying "Skip."</span></span>

<span data-ttu-id="0eda3-186">Während des Kalibrierungsvorgangs fordert HoloLens Sie auf, Ihren Finger mit einer Reihe von sechs Zielen pro Auge auszurichten.</span><span class="sxs-lookup"><span data-stu-id="0eda3-186">During the calibration process, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="0eda3-187">HoloLens verwendet diesen Vorgang, um den IPD für Ihre Augen richtig einzustellen.</span><span class="sxs-lookup"><span data-stu-id="0eda3-187">HoloLens uses this process to set the IPD correctly for your eyes.</span></span>

![IPD-Fingerausrichtungsbildschirm im zweiten Schritt](./images/ipd-finger-alignment-300px.jpg)

### <span data-ttu-id="0eda3-189">Manuelles Starten des Kalibrierungsvorgangs</span><span class="sxs-lookup"><span data-stu-id="0eda3-189">Manually start the calibration process</span></span>

<span data-ttu-id="0eda3-190">Wenn Sie die Kalibrierung aktualisieren müssen oder wenn ein neuer Benutzer sie anpassen muss, können Sie die Kalibrierungs-App jederzeit manuell ausführen.</span><span class="sxs-lookup"><span data-stu-id="0eda3-190">If you need to update the calibration or if a new user needs to adjust it, you can manually run the Calibration app at any time.</span></span> <span data-ttu-id="0eda3-191">Die Kalibrierungs-App ist standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="0eda3-191">The Calibration app is installed by default.</span></span> <span data-ttu-id="0eda3-192">Sie können über das **Startmenü** oder in der Einstellungs-App darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0eda3-192">You can access it by using eihter the **Start** menu or the Settings app.</span></span>

<span data-ttu-id="0eda3-193">Führen Sie die folgenden Schritte aus, um die Kalibrierungs-App über das **Startmenü** auszuführen:</span><span class="sxs-lookup"><span data-stu-id="0eda3-193">To use the **Start** menu to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="0eda3-194">Verwenden Sie die [Öffnengeste](hololens1-basic-usage.md), um das **Startmenü** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0eda3-194">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="0eda3-195">Um alle Apps anzuzeigen, wählen Sie **+** aus.</span><span class="sxs-lookup"><span data-stu-id="0eda3-195">To view all apps, select **+**.</span></span>
1. <span data-ttu-id="0eda3-196">Wählen Sie **Kalibrierung** aus.</span><span class="sxs-lookup"><span data-stu-id="0eda3-196">Select **Calibration**.</span></span>

![Zugreifen auf die Kalibrierungs-App aus der Shell](./images/calibration-shell.png)

![Die Kalibrierungs-App wird nach dem Start als Live-Kachel angezeigt](./images/calibration-livecube-200px.png)

<span data-ttu-id="0eda3-199">Führen Sie die folgenden Schritte aus, um die Kalibrierungs-App über die Einstellungs-App auszuführen:</span><span class="sxs-lookup"><span data-stu-id="0eda3-199">To use the Settings app to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="0eda3-200">Verwenden Sie die [Öffnengeste](hololens1-basic-usage.md), um das **Startmenü** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0eda3-200">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="0eda3-201">Wenn **Einstellungen** nicht an **Start** angeheftet ist, wählen Sie **+** aus, um alle Apps anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0eda3-201">If **Settings** isn't pinned to **Start**, select **+** to view all apps.</span></span>
1. <span data-ttu-id="0eda3-202">Wählen Sie **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="0eda3-202">Select **Settings**.</span></span>
1. <span data-ttu-id="0eda3-203">Wählen Sie **System** > **Dienstprogramme** > **Kalibrierung öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="0eda3-203">Select **System** > **Utilities** > **Open Calibration**.</span></span>

![Starten der Kalibrierungs-App aus der Einstellungs-App](./images/calibration-settings-500px.jpg)

## <span data-ttu-id="0eda3-205">Immersive Headsets</span><span class="sxs-lookup"><span data-stu-id="0eda3-205">Immersive headsets</span></span>

<span data-ttu-id="0eda3-206">Einige immersive Headsets bieten die Möglichkeit, die IPD-Einstellung anzupassen.</span><span class="sxs-lookup"><span data-stu-id="0eda3-206">Some immersive headsets provide the ability to customize the IPD setting.</span></span> <span data-ttu-id="0eda3-207">Wenn Sie den IPD für Ihr Headset ändern möchten, öffnen Sie die Einstellungs-App und wählen Sie **Mixed Reality** > **Headsetanzeige** aus und bewegen Sie dann das Schieberegler-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0eda3-207">To change the IPD for your headset, open the Settings app and select **Mixed reality** > **Headset display**, and then move the slider control.</span></span> <span data-ttu-id="0eda3-208">Die Änderungen werden in Echtzeit in Ihrem Headset angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0eda3-208">You’ll see the changes in real time in your headset.</span></span> <span data-ttu-id="0eda3-209">Wenn Sie Ihren IPD kennen, vielleicht durch einen Besuch beim Optiker, können Sie ihn auch direkt eingeben.</span><span class="sxs-lookup"><span data-stu-id="0eda3-209">If you know your IPD, maybe from a visit to the optometrist, you can enter it directly as well.</span></span>

<span data-ttu-id="0eda3-210">Sie können diese Einstellung auch auf Ihrem PC anpassen, indem Sie **Einstellungen** > **Mixed Reality** > **Headsetanzeige** auswählen.</span><span class="sxs-lookup"><span data-stu-id="0eda3-210">You can also adjust this setting on your PC by selecting **Settings** > **Mixed reality** > **Headset display**.</span></span>

<span data-ttu-id="0eda3-211">Wenn Ihr Headset die IPD-Anpassung nicht unterstützt, ist diese Einstellung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0eda3-211">If your headset does not support IPD customization, this setting will be disabled.</span></span>
