---
title: Verwenden Ihrer Stimme zum Bedienen von HoloLens
description: Cortana kann Ihnen helfen, alle möglichen Dinge auf Ihrem HoloLens zu erledigen.
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
audience: ITPro
ms.author: v-tea
ms.topic: article
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d6fc83e81ce6f02047cff8a5d1944156f769e056
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828380"
---
# <span data-ttu-id="e5e84-104">Verwenden Ihrer Stimme zum Bedienen von HoloLens</span><span class="sxs-lookup"><span data-stu-id="e5e84-104">Use your voice to operate HoloLens</span></span>

<span data-ttu-id="e5e84-105">Mit Ihrer Stimme können Sie auf HoloLens die meisten Aufgaben erledigen, z. B. schnell ein Foto aufnehmen oder eine App öffnen.</span><span class="sxs-lookup"><span data-stu-id="e5e84-105">You can use your voice to do almost anything on HoloLens, such as taking a quick photo or opening an app.</span></span> <span data-ttu-id="e5e84-106">Viele Sprachbefehle sind in HoloLens integriert, während andere über Cortana zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="e5e84-106">Many voice commands are built into HoloLens, while others are available through Cortana.</span></span>

<span data-ttu-id="e5e84-107">In diesem Artikel erfahren Sie, wie Sie HoloLens und Ihre holografische Welt mit Sprachbefehlen und Cortana steuern können.</span><span class="sxs-lookup"><span data-stu-id="e5e84-107">This article teaches you how to control HoloLens and your holographic world with your voice and with Cortana.</span></span>

> [!NOTE]
> <span data-ttu-id="e5e84-108">Die Spracherkennung wird nur in [einigen Sprachen](hololens2-language-support.md)unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e5e84-108">Speech is only supported in [some languages](hololens2-language-support.md).</span></span> <span data-ttu-id="e5e84-109">Die für die Spracherkennung verwendete Sprache basiert auf der Windows-Anzeigesprache, nicht auf der Tastatursprache.</span><span class="sxs-lookup"><span data-stu-id="e5e84-109">The speech language is based on the Windows display language, not the keyboard language.</span></span>  
>  
> <span data-ttu-id="e5e84-110">Sie können die Windows-Anzeigesprache überprüfen, indem Sie **Einstellungen** > **Zeit und Sprache** > **Sprache** auswählen.</span><span class="sxs-lookup"><span data-stu-id="e5e84-110">You can verify the Windows display language by selecting **Settings** > **Time and Language** > **Language**.</span></span>

## <span data-ttu-id="e5e84-111">Integrierte Sprachbefehle</span><span class="sxs-lookup"><span data-stu-id="e5e84-111">Built-in voice commands</span></span>

<span data-ttu-id="e5e84-112">Mit den folgenden grundlegenden Befehlen können Sie sich schneller in HoloLens zurechtfinden.</span><span class="sxs-lookup"><span data-stu-id="e5e84-112">Get around HoloLens faster with these basic commands.</span></span> <span data-ttu-id="e5e84-113">Um diese verwenden zu können, müssen Sie die Spracherkennung während der ersten Ausführung des Geräts oder unter **Einstellungen** > **Datenschutz** > **Spracherkennung** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e5e84-113">In order to use these, you need to enable Speech during the first run of the device or in **Settings** > **Privacy** > **Speech**.</span></span> <span data-ttu-id="e5e84-114">Anhand des Status oben im Startmenü können Sie jederzeit überprüfen, ob die Spracherkennung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e5e84-114">You can always check whether speech is enabled by looking at the status at the top of the Start menu.</span></span> <span data-ttu-id="e5e84-115">Für optimale Ergebnisse der Spracherkennung verwendet HoloLens 2 die Cloud-basierten Dienste von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e5e84-115">For the best speech recognition results, HoloLens 2 uses the Microsoft cloud-based services.</span></span> <span data-ttu-id="e5e84-116">Sie können dieses Feature jedoch mithilfe des Menüs Einstellungen deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e5e84-116">However, you can use Settings to disable this feature.</span></span> <span data-ttu-id="e5e84-117">Deaktivieren Sie dazu in den Einstellungen die **Online-Spracherkennung**.</span><span class="sxs-lookup"><span data-stu-id="e5e84-117">To do this, in Settings, turn off **Online speech recognition**.</span></span> <span data-ttu-id="e5e84-118">Nachdem Sie diese Einstellung geändert haben, verarbeitet HoloLens 2 Sprachdaten nur lokal zum Erkennen von Befehlen und Diktaten und Cortana ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e5e84-118">After you change this setting, HoloLens 2 will only process voice data locally to recognize commands and dictation, and Cortana will not be available.</span></span>

### <span data-ttu-id="e5e84-119">Allgemeine Sprachbefehle</span><span class="sxs-lookup"><span data-stu-id="e5e84-119">General speech commands</span></span>

<span data-ttu-id="e5e84-120">Verwenden Sie diese Befehle in Windows Mixed Reality, um schneller zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="e5e84-120">Use these commands throughout Windows Mixed Reality to get around faster.</span></span> <span data-ttu-id="e5e84-121">Einige Befehle verwenden den Anvisier-Cursor, den Sie mit dem Sprachbefehl "Auswählen" aufrufen.</span><span class="sxs-lookup"><span data-stu-id="e5e84-121">Some commands use the gaze cursor, which you bring up by saying "select."</span></span>

> [!NOTE]
> <span data-ttu-id="e5e84-122">Handstrahlen werden auf HoloLens (1.Generation) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e5e84-122">Hand rays are not supported on HoloLens (1st Gen).</span></span>

| <span data-ttu-id="e5e84-123">Sagen Sie das</span><span class="sxs-lookup"><span data-stu-id="e5e84-123">Say this</span></span> | <span data-ttu-id="e5e84-124">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="e5e84-124">To do this</span></span> |
| - | - |
| <span data-ttu-id="e5e84-125">„Auswählen“</span><span class="sxs-lookup"><span data-stu-id="e5e84-125">"Select"</span></span> | <span data-ttu-id="e5e84-126">Sagen Sie „Auswählen“, um den Anvisier-Cursor aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="e5e84-126">Say "select" to bring up the gaze cursor.</span></span> <span data-ttu-id="e5e84-127">Drehen Sie dann Ihren Kopf, um den Cursor auf das zu positionieren, was Sie auswählen möchten, und sagen Sie erneut „Auswählen“.</span><span class="sxs-lookup"><span data-stu-id="e5e84-127">Then, turn your head to position the cursor on the thing you want to select, and say "select" again.</span></span> |
|<span data-ttu-id="e5e84-128">Öffnen des Startmenüs</span><span class="sxs-lookup"><span data-stu-id="e5e84-128">Open the Start menu</span></span> | <span data-ttu-id="e5e84-129">„Zum Startmenü”</span><span class="sxs-lookup"><span data-stu-id="e5e84-129">"Go to Start"</span></span> |
|<span data-ttu-id="e5e84-130">Startmenü schließen</span><span class="sxs-lookup"><span data-stu-id="e5e84-130">Close the Start menu</span></span> | <span data-ttu-id="e5e84-131">„Schließen“</span><span class="sxs-lookup"><span data-stu-id="e5e84-131">"Close"</span></span> |
|<span data-ttu-id="e5e84-132">Eine immersive App schließen</span><span class="sxs-lookup"><span data-stu-id="e5e84-132">Leave an immersive app</span></span> | <span data-ttu-id="e5e84-133">Sagen Sie „Zum Startmenü“, um das Menü „Schnelle Aktionen“ zu öffnen, und sagen Sie dann „Mixed Reality Startumgebung“.</span><span class="sxs-lookup"><span data-stu-id="e5e84-133">Say "Go to Start" to bring up the quick actions menu, then say "Mixed reality home."</span></span> |
|<span data-ttu-id="e5e84-134">Handstrahl ein- und ausblenden</span><span class="sxs-lookup"><span data-stu-id="e5e84-134">Hide and show hand ray</span></span> | <span data-ttu-id="e5e84-135">„Handstrahl ausblenden“/„Handstrahl einblenden“</span><span class="sxs-lookup"><span data-stu-id="e5e84-135">"Hide hand ray" / "Show hand ray"</span></span> |
|<span data-ttu-id="e5e84-136">Anzeigen von verfügbaren Sprachbefehlen</span><span class="sxs-lookup"><span data-stu-id="e5e84-136">See available speech commands</span></span> | <span data-ttu-id="e5e84-137">Was kann ich sagen?</span><span class="sxs-lookup"><span data-stu-id="e5e84-137">"What can I say?"</span></span> |

<span data-ttu-id="e5e84-138">Aber der Version 19041.x von HoloLens 2 können Sie auch die folgenden Befehle verwenden:</span><span class="sxs-lookup"><span data-stu-id="e5e84-138">Starting with version 19041.x of HoloLens 2, you can also use these commands:</span></span>

| <span data-ttu-id="e5e84-139">Sagen Sie das</span><span class="sxs-lookup"><span data-stu-id="e5e84-139">Say this</span></span> | <span data-ttu-id="e5e84-140">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="e5e84-140">To do this</span></span> |
| - | - |
| <span data-ttu-id="e5e84-141">„Gerät neu starten“</span><span class="sxs-lookup"><span data-stu-id="e5e84-141">"Restart device"</span></span> | <span data-ttu-id="e5e84-142">Rufen Sie ein Dialogfeld auf, um zu bestätigen, dass Sie das Gerät neu starten möchten.</span><span class="sxs-lookup"><span data-stu-id="e5e84-142">Bring up a dialogue to confirm you want to restart the device.</span></span> <span data-ttu-id="e5e84-143">Um neu zu starten, können Sie „Ja“ sagen.</span><span class="sxs-lookup"><span data-stu-id="e5e84-143">You can say "yes" to restart.</span></span> |
| <span data-ttu-id="e5e84-144">„Gerät herunterfahren“</span><span class="sxs-lookup"><span data-stu-id="e5e84-144">"Shutdown device"</span></span> | <span data-ttu-id="e5e84-145">Rufen Sie ein Dialogfeld auf, um zu bestätigen, dass Sie das Gerät ausschalten möchten.</span><span class="sxs-lookup"><span data-stu-id="e5e84-145">Bring up a dialogue to confirm you want to turn off the device.</span></span> <span data-ttu-id="e5e84-146">Zur Bestätigung können Sie „Ja“ sagen.</span><span class="sxs-lookup"><span data-stu-id="e5e84-146">You can say "yes" to confirm.</span></span> |
| <span data-ttu-id="e5e84-147">„Heller/dunkler“</span><span class="sxs-lookup"><span data-stu-id="e5e84-147">"Brightness up/down"</span></span> | <span data-ttu-id="e5e84-148">Erhöhen oder verringern Sie die Anzeigehelligkeit um 10 %.</span><span class="sxs-lookup"><span data-stu-id="e5e84-148">Increase or decrease the display brightness by 10%.</span></span> |
| <span data-ttu-id="e5e84-149">„Lauter/leiser“</span><span class="sxs-lookup"><span data-stu-id="e5e84-149">"Volume up/down"</span></span> | <span data-ttu-id="e5e84-150">Erhöhen oder verringern Sie die Lautstärke um 10 %.</span><span class="sxs-lookup"><span data-stu-id="e5e84-150">Increase or decrease the volume by 10%.</span></span> |
| <span data-ttu-id="e5e84-151">„Wie lautet meine IP?“</span><span class="sxs-lookup"><span data-stu-id="e5e84-151">"What's my IP address"</span></span> | <span data-ttu-id="e5e84-152">Rufen Sie ein Dialogfeld auf, das die aktuelle IP-Adresse Ihres Computers im lokalen Netzwerk anzeigt.</span><span class="sxs-lookup"><span data-stu-id="e5e84-152">Bring up a dialogue displaying your device's current IP address on the local network.</span></span> |
| <span data-ttu-id="e5e84-153">„Bild aufnehmen“</span><span class="sxs-lookup"><span data-stu-id="e5e84-153">"Take a picture"</span></span> | <span data-ttu-id="e5e84-154">Nehmen Sie ein Mixed-Reality-Bild von dem auf, was Sie gerade sehen.</span><span class="sxs-lookup"><span data-stu-id="e5e84-154">Capture a mixed reality photo of what you are currently seeing.</span></span> |
| <span data-ttu-id="e5e84-155">„Video aufzeichnen“</span><span class="sxs-lookup"><span data-stu-id="e5e84-155">"Take a video"</span></span> | <span data-ttu-id="e5e84-156">Beginnen Sie mit der Aufzeichnung eines Mixed-Reality-Videos.</span><span class="sxs-lookup"><span data-stu-id="e5e84-156">Start recording a mixed reality video.</span></span> | 
| <span data-ttu-id="e5e84-157">„Aufzeichnung beenden“</span><span class="sxs-lookup"><span data-stu-id="e5e84-157">"Stop recording"</span></span> | <span data-ttu-id="e5e84-158">Stoppt die aktuelle Mixed-Reality-Videoaufzeichnung, wenn diese gerade läuft.</span><span class="sxs-lookup"><span data-stu-id="e5e84-158">Stops the current mixed reality video recording if one is in progress.</span></span> |

### <span data-ttu-id="e5e84-159">Hologrammbefehle</span><span class="sxs-lookup"><span data-stu-id="e5e84-159">Hologram commands</span></span>

<span data-ttu-id="e5e84-160">Wenn Sie diese Befehle verwenden möchten, visieren Sie ein 3D-Objekt, Hologramm oder App-Fenster an.</span><span class="sxs-lookup"><span data-stu-id="e5e84-160">To use these commands, gaze at a 3D object, hologram, or app window.</span></span>

| <span data-ttu-id="e5e84-161">Sagen Sie das</span><span class="sxs-lookup"><span data-stu-id="e5e84-161">Say this</span></span> | <span data-ttu-id="e5e84-162">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="e5e84-162">To do this</span></span> |
| - | - |
| <span data-ttu-id="e5e84-163">„Vergrößern“</span><span class="sxs-lookup"><span data-stu-id="e5e84-163">"Bigger"</span></span> | <span data-ttu-id="e5e84-164">Vergrößern</span><span class="sxs-lookup"><span data-stu-id="e5e84-164">Make it bigger</span></span> |
| <span data-ttu-id="e5e84-165">„Kleiner“</span><span class="sxs-lookup"><span data-stu-id="e5e84-165">"Smaller"</span></span> | <span data-ttu-id="e5e84-166">Verkleinern</span><span class="sxs-lookup"><span data-stu-id="e5e84-166">Make it smaller</span></span> |
| <span data-ttu-id="e5e84-167">„Zu mir drehen“</span><span class="sxs-lookup"><span data-stu-id="e5e84-167">"Face me"</span></span> | <span data-ttu-id="e5e84-168">Zu Ihnen drehen</span><span class="sxs-lookup"><span data-stu-id="e5e84-168">Turn it to face you</span></span> |
| <span data-ttu-id="e5e84-169">„Verschieben“</span><span class="sxs-lookup"><span data-stu-id="e5e84-169">"Move this"</span></span> | <span data-ttu-id="e5e84-170">Verschieben (Ihrem Blick folgen)</span><span class="sxs-lookup"><span data-stu-id="e5e84-170">Move it (follow your gaze)</span></span> |
| <span data-ttu-id="e5e84-171">„Schließen“</span><span class="sxs-lookup"><span data-stu-id="e5e84-171">"Close"</span></span> | <span data-ttu-id="e5e84-172">Schließen</span><span class="sxs-lookup"><span data-stu-id="e5e84-172">Close it</span></span> |
| <span data-ttu-id="e5e84-173">„Folgen beginnen“/„Folgen beenden“</span><span class="sxs-lookup"><span data-stu-id="e5e84-173">"Follow me" / "Stop following"</span></span> | <span data-ttu-id="e5e84-174">Ihren Bewegungen folgen lassen</span><span class="sxs-lookup"><span data-stu-id="e5e84-174">Make it follow you as you move around</span></span> |

### <span data-ttu-id="e5e84-175">Sehen, sagen</span><span class="sxs-lookup"><span data-stu-id="e5e84-175">See it, say it</span></span>

<span data-ttu-id="e5e84-176">Viele Schaltflächen und andere Elemente auf HoloLens reagieren ebenfalls auf Ihre Stimme, z.B. **Folgen beginnen** und **Schließen** auf der App-Leiste oder die Schaltfläche **Zurück** in Edge.</span><span class="sxs-lookup"><span data-stu-id="e5e84-176">Many buttons and other elements on HoloLens also respond to your voice—for example, **Follow me** and **Close** on the app bar, or the **Back** button in Edge.</span></span> <span data-ttu-id="e5e84-177">Wenn Sie ermitteln möchten, ob eine Schaltfläche sprachsteuerungsfähig ist, zeigen Sie einen Moment lang mit dem **Anvisier-Cursor**, dem **Touch-Cursor** oder einem **Handstrahl** darauf.</span><span class="sxs-lookup"><span data-stu-id="e5e84-177">To find out if a button is voice-enabled, rest your **gaze cursor**,**touch cursor** or one **hand ray** on it for a moment.</span></span> <span data-ttu-id="e5e84-178">Wenn die Schaltfläche für die Sprachausgabe aktiviert ist, wird ein Sprachausgabe-Tipp angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5e84-178">If the button is voice-enabled, you'll see a voice tip.</span></span>

### <span data-ttu-id="e5e84-179">Diktiermodus</span><span class="sxs-lookup"><span data-stu-id="e5e84-179">Dictation mode</span></span>

<span data-ttu-id="e5e84-180">Keine Lust mehr auf Tippen?</span><span class="sxs-lookup"><span data-stu-id="e5e84-180">Tired of typing?</span></span> <span data-ttu-id="e5e84-181">Wechseln Sie jederzeit in den Diktiermodus, wenn die holografische Tastatur aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="e5e84-181">Switch to dictation mode any time that the holographic keyboard is active.</span></span> <span data-ttu-id="e5e84-182">Wählen Sie zunächst die Schaltfläche „Mikrofon“ aus, oder sagen Sie „Starte diktieren“.</span><span class="sxs-lookup"><span data-stu-id="e5e84-182">To get started, select the microphone button or say "Start dictating."</span></span> <span data-ttu-id="e5e84-183">Wenn Sie das Diktat beenden möchten, wählen Sie die Schaltfläche erneut aus, oder sagen Sie „Diktat beenden“.</span><span class="sxs-lookup"><span data-stu-id="e5e84-183">To stop dictating, select the button again or say "Stop dictating."</span></span> <span data-ttu-id="e5e84-184">Um zu löschen, was Sie gerade diktiert haben, sagen Sie „Eingabe löschen“.</span><span class="sxs-lookup"><span data-stu-id="e5e84-184">To delete what you just dictated, say "Delete that."</span></span> 

> [!NOTE]
> <span data-ttu-id="e5e84-185">Wenn Sie den Diktiermodus verwenden möchten, benötigen Sie eine Internetverbindung.</span><span class="sxs-lookup"><span data-stu-id="e5e84-185">To use dictation mode, you have to have an internet connection.</span></span>

<span data-ttu-id="e5e84-186">Die Diktierfunktion von HoloLens verwendet explizite Interpunktion. Dies bedeutet, dass Sie den Namen des zu verwendenden Satzzeichens sagen.</span><span class="sxs-lookup"><span data-stu-id="e5e84-186">HoloLens dictation uses explicit punctuation, meaning that you say the name of the punctuation you want to use.</span></span> <span data-ttu-id="e5e84-187">Sie können beispielsweise Folgendes sagen: „Hallo **Komma** was machst du gerade **Fragezeichen**“.</span><span class="sxs-lookup"><span data-stu-id="e5e84-187">For instance, you might say "Hey **comma** what are you up to **question mark**."</span></span>

<span data-ttu-id="e5e84-188">Sie können die folgenden Interpunktionsbefehle verwenden:</span><span class="sxs-lookup"><span data-stu-id="e5e84-188">Here are the punctuation keywords that you can use:</span></span>

- <span data-ttu-id="e5e84-189">Punkt, Komma, Fragezeichen, Ausrufezeichen</span><span class="sxs-lookup"><span data-stu-id="e5e84-189">Period, comma, question mark, exclamation point/exclamation mark</span></span>
- <span data-ttu-id="e5e84-190">Neue Zeile/neuer Absatz</span><span class="sxs-lookup"><span data-stu-id="e5e84-190">New line/new paragraph</span></span>
- <span data-ttu-id="e5e84-191">Semikolon, Doppelpunkt</span><span class="sxs-lookup"><span data-stu-id="e5e84-191">Semicolon, colon</span></span>
- <span data-ttu-id="e5e84-192">Anführungszeichen unten, Anführungszeichen oben</span><span class="sxs-lookup"><span data-stu-id="e5e84-192">Open quote(s), close quote(s)</span></span>
- <span data-ttu-id="e5e84-193">Hashtag, Smiley, trauriges Smiley, zwinkerndes Smiley</span><span class="sxs-lookup"><span data-stu-id="e5e84-193">Hashtag, smiley/smiley face, frowny, winky</span></span>
- <span data-ttu-id="e5e84-194">US-Dollar, Prozent</span><span class="sxs-lookup"><span data-stu-id="e5e84-194">Dollar, percent</span></span>

<span data-ttu-id="e5e84-195">Manchmal ist es hilfreich, Dinge wie E-Mail-Adressen zu buchstabieren.</span><span class="sxs-lookup"><span data-stu-id="e5e84-195">Sometimes it's helpful to spell out things like email addresses.</span></span> <span data-ttu-id="e5e84-196">Zum Diktieren von „example@outlook.com“ würden Sie beispielsweise „E X A M P L E at outlook dot com“ sagen.</span><span class="sxs-lookup"><span data-stu-id="e5e84-196">For instance, to dictate example@outlook.com, you'd say "E X A M P L E at outlook dot com."</span></span>

## <span data-ttu-id="e5e84-197">Mit Cortana sind Sie noch produktiver.</span><span class="sxs-lookup"><span data-stu-id="e5e84-197">Do more with Cortana</span></span>

<span data-ttu-id="e5e84-198">Cortana kann Ihnen dabei helfen, alle möglichen Aktionen mit Ihrem HoloLens auszuführen. Je nachdem, welche Windows-Version Sie verwenden, stehen Ihnen verschiedene Möglichkeiten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e5e84-198">Cortana can help you do all kinds of things on your HoloLens, but depending on which version of Windows Holographic you're using, the capablities may be different.</span></span> <span data-ttu-id="e5e84-199">Mehr über die aktuellen Möglichkeiten der neuesten Version von Cortana erfahren Sie [hier](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).</span><span class="sxs-lookup"><span data-stu-id="e5e84-199">You can learn more about the updated capabilites of the latest version of Cortana [here](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).</span></span> 

![Hey Cortana!](images/cortana-on-hololens.png)

<span data-ttu-id="e5e84-201">Im Folgenden finden Sie einige Sprachbefehle, die Sie ausprobieren können (denken Sie daran, zuerst „Hey Cortana“ zu sagen).</span><span class="sxs-lookup"><span data-stu-id="e5e84-201">Here are some things you can try saying (remember to say "Hey Cortana" first).</span></span>

<span data-ttu-id="e5e84-202">**Hallo, Cortana**...</span><span class="sxs-lookup"><span data-stu-id="e5e84-202">**Hey, Cortana**...</span></span>

- <span data-ttu-id="e5e84-203">Was kann ich sagen?</span><span class="sxs-lookup"><span data-stu-id="e5e84-203">What can I say?</span></span>
- <span data-ttu-id="e5e84-204"><*app name*> starten</span><span class="sxs-lookup"><span data-stu-id="e5e84-204">Launch <*app name*>.</span></span>
- <span data-ttu-id="e5e84-205">Wie spät ist es?</span><span class="sxs-lookup"><span data-stu-id="e5e84-205">What time is it?</span></span>
- <span data-ttu-id="e5e84-206">Zeig mir die neuesten NBA-Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="e5e84-206">Show me the latest NBA scores.</span></span>
- <span data-ttu-id="e5e84-207">Erzähl mir einen Witz</span><span class="sxs-lookup"><span data-stu-id="e5e84-207">Tell me a joke.</span></span>

<span data-ttu-id="e5e84-208">Wenn Sie *Version 18362.x oder früher* nutzen, können Sie auch die folgenden Befehle verwenden:</span><span class="sxs-lookup"><span data-stu-id="e5e84-208">If you're using *version 18362.x or earlier*, you can also use these commands:</span></span>

<span data-ttu-id="e5e84-209">**Hallo, Cortana**...</span><span class="sxs-lookup"><span data-stu-id="e5e84-209">**Hey, Cortana**...</span></span>

- <span data-ttu-id="e5e84-210">Increase the volume (erhöhe die Lautstärke).</span><span class="sxs-lookup"><span data-stu-id="e5e84-210">Increase the volume.</span></span>
- <span data-ttu-id="e5e84-211">Decrease the brightness (verringere die Helligkeit).</span><span class="sxs-lookup"><span data-stu-id="e5e84-211">Decrease the brightness.</span></span>
- <span data-ttu-id="e5e84-212">Shut down (herunterfahren).</span><span class="sxs-lookup"><span data-stu-id="e5e84-212">Shut down.</span></span>
- <span data-ttu-id="e5e84-213">Restart (neu starten).</span><span class="sxs-lookup"><span data-stu-id="e5e84-213">Restart.</span></span>
- <span data-ttu-id="e5e84-214">Go to sleep (Ruhezustand).</span><span class="sxs-lookup"><span data-stu-id="e5e84-214">Go to sleep.</span></span>
- <span data-ttu-id="e5e84-215">Stummschalten.</span><span class="sxs-lookup"><span data-stu-id="e5e84-215">Mute.</span></span>
- <span data-ttu-id="e5e84-216"><*app name*> hierher verschieben (visieren Sie die Stelle an, an die Sie die App verschieben möchten).</span><span class="sxs-lookup"><span data-stu-id="e5e84-216">Move <*app name*> here (gaze at the spot that you want the app to move to).</span></span>
- <span data-ttu-id="e5e84-217">Zum Startmenü</span><span class="sxs-lookup"><span data-stu-id="e5e84-217">Go to Start.</span></span>
- <span data-ttu-id="e5e84-218">Take a picture (Bild aufnehmen).</span><span class="sxs-lookup"><span data-stu-id="e5e84-218">Take a picture.</span></span>
- <span data-ttu-id="e5e84-219">Start recording (Aufzeichnung starten.</span><span class="sxs-lookup"><span data-stu-id="e5e84-219">Start recording.</span></span> <span data-ttu-id="e5e84-220">(Beginnt die Aufzeichnung eines Videos.)</span><span class="sxs-lookup"><span data-stu-id="e5e84-220">(Starts recording a video.)</span></span>
- <span data-ttu-id="e5e84-221">Aufzeichnung beenden.</span><span class="sxs-lookup"><span data-stu-id="e5e84-221">Stop recording.</span></span> <span data-ttu-id="e5e84-222">(Beendet die Aufzeichnung eines Videos.)</span><span class="sxs-lookup"><span data-stu-id="e5e84-222">(Stops recording a video.)</span></span>
- <span data-ttu-id="e5e84-223">Wie viel Akkukapazität habe ich noch?</span><span class="sxs-lookup"><span data-stu-id="e5e84-223">How much battery do I have left?</span></span>

<span data-ttu-id="e5e84-224">Einige Cortana-Features, die Sie von Windows auf Ihrem PC oder Smartphone kennen (beispielsweise Erinnerungen und Benachrichtigungen) werden in Microsoft HoloLens nicht unterstützt, und die Cortana-Erfahrung kann von Region zu Region variieren.</span><span class="sxs-lookup"><span data-stu-id="e5e84-224">Some Cortana features that you're used to from Windows on your PC or phone (for example, reminders and notifications) aren't supported in Microsoft HoloLens, and the Cortana experience may vary from one region to another.</span></span>

### <span data-ttu-id="e5e84-225">Cortana deaktivieren</span><span class="sxs-lookup"><span data-stu-id="e5e84-225">Turn Cortana off</span></span>

<span data-ttu-id="e5e84-226">Wenn Sie die Spracherkennung aktivieren, ist Cortana bei der ersten Verwendung von HoloLens eingeschaltet.</span><span class="sxs-lookup"><span data-stu-id="e5e84-226">Cortana is on the first time you use HoloLens when you enable speech.</span></span> <span data-ttu-id="e5e84-227">Sie können Cortana in den Cortana-Einstellungen deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e5e84-227">You can turn her off in Cortana's settings.</span></span> <span data-ttu-id="e5e84-228">Wählen Sie aus der Liste **Alle Apps** die Optionen **Cortana** > **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="e5e84-228">In the **All apps** list, select **Cortana** > **Settings**.</span></span> <span data-ttu-id="e5e84-229">Deaktivieren Sie dann „Cortana kann Vorschläge, Ideen, Erinnerungen, Warnungen und vieles mehr anbieten“.</span><span class="sxs-lookup"><span data-stu-id="e5e84-229">Then turn off Cortana can give you suggestions, ideas, reminders, alerts, and more.</span></span>

<span data-ttu-id="e5e84-230">Wenn Cortana nicht auf „Hey Cortana“ reagiert, überprüfen Sie, ob die Spracherkennung beim Start aktiviert ist, und wechseln Sie zu den Einstellungen von Cortana, um sich zu vergewissern, dass sie eingeschaltet ist.</span><span class="sxs-lookup"><span data-stu-id="e5e84-230">If Cortana isn't responding to "Hey Cortana," check that speech is enabled on Start and go to Cortana's settings and check to make sure she's on.</span></span>
