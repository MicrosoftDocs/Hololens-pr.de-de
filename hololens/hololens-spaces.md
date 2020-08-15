---
title: Abbilden von physischen Räumen mit HoloLens
description: HoloLens lernt im Laufe der Zeit, wie ein Raum aussieht. Benutzer können diesen Prozess vereinfachen, indem sie die HoloLens auf bestimmte Weise durch den Raum bewegen.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: Hololens, Windows Mixed Reality, Design, räumliche Zuordnung, HoloLens, Surface Rekonstruktion, Gittermodell, Head Tracking, Mapping
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: 7cedf2af90744477c33736087c85a43168167707
ms.sourcegitcommit: 6f2ec9ced776166f96eddcd601bef5de715703a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2020
ms.locfileid: "10931837"
---
# <span data-ttu-id="36eda-105">Abbilden von physischen Räumen mit HoloLens</span><span class="sxs-lookup"><span data-stu-id="36eda-105">Map physical spaces with HoloLens</span></span>

<span data-ttu-id="36eda-106">HoloLens verbindet Hologramme mit Ihrer physischen Welt.</span><span class="sxs-lookup"><span data-stu-id="36eda-106">HoloLens blends holograms with your physical world.</span></span> <span data-ttu-id="36eda-107">Dazu muss HoloLens die Ihre physische Umgebung kennen lernen und sich merken, wo Sie Hologramme in diesem Raum platzieren.</span><span class="sxs-lookup"><span data-stu-id="36eda-107">To do that, HoloLens has to learn about the physical world around you and remember where you place holograms within that space.</span></span>

<span data-ttu-id="36eda-108">Nach und nach baut HoloLens eine *räumliche Karte* der Umgebung, die HoloLens gesehen hat.</span><span class="sxs-lookup"><span data-stu-id="36eda-108">Over time, the HoloLens builds up a *spatial map* of the environment that it has seen.</span></span>  <span data-ttu-id="36eda-109">HoloLens aktualisiert die Karte, wenn sich die Umgebung ändert.</span><span class="sxs-lookup"><span data-stu-id="36eda-109">HoloLens updates the map as the environment changes.</span></span> <span data-ttu-id="36eda-110">Solange Sie angemeldet sind und das Gerät aktiviert ist, erstellt HoloLens räumliche Karten Ihrer Umgebung.</span><span class="sxs-lookup"><span data-stu-id="36eda-110">As long as you are logged in and the device is turned on, HoloLens creates and updates your spatial maps.</span></span> <span data-ttu-id="36eda-111">Wenn Sie das Gerät mit den Kameras in einen Raum halten oder tragen, versucht HoloLens die Umgebung zu kartieren.</span><span class="sxs-lookup"><span data-stu-id="36eda-111">If you hold or wear the device with the cameras pointed at a space, the HoloLens tries to map the area.</span></span> <span data-ttu-id="36eda-112">Während HoloLens mit der Zeit einen Raum kennenlernt, können Sie HoloLens helfen, Ihre Umgebung schneller und effizienter zu kartieren.</span><span class="sxs-lookup"><span data-stu-id="36eda-112">While the HoloLens learns a space naturally over time, there are ways in which you can help HoloLens map your space more quickly and efficiently.</span></span>  

> [!NOTE]
> <span data-ttu-id="36eda-113">Wenn HoloLens Ihre Umgebung nicht kartieren kann oder nicht mehr kalibriert ist, kann HoloLens in den eingeschränkten Modus wechseln.</span><span class="sxs-lookup"><span data-stu-id="36eda-113">If your HoloLens can't map your space or is out of calibration, HoloLens may enter Limited mode.</span></span> <span data-ttu-id="36eda-114">Im eingeschränkten Modus können Sie keine Hologramme in Ihrer Umgebung platzieren.</span><span class="sxs-lookup"><span data-stu-id="36eda-114">In Limited mode, you won't be able to place holograms in your surroundings.</span></span>

<span data-ttu-id="36eda-115">In diesem Artikel wird erläutert, wie HoloLens Räume erfasst, wie die räumliche Zuordnung verbessert werden kann und wie die von HoloLens gesammelten räumlichen Daten zu verwalten sind.</span><span class="sxs-lookup"><span data-stu-id="36eda-115">This article explains how HoloLens maps spaces, how to improve spatial mapping, and how to manage the spatial data that HoloLens collects.</span></span>

## <span data-ttu-id="36eda-116">Ihre räumliche Umgebung auswählen und einrichten</span><span class="sxs-lookup"><span data-stu-id="36eda-116">Choosing and setting up and your space</span></span>

<span data-ttu-id="36eda-117">Bestimmte Merkmale in Ihrer Umgebung erschweren es HoloLens, einen Raum zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="36eda-117">Features in your environment can make it difficult for the HoloLens to interpret a space.</span></span> <span data-ttu-id="36eda-118">Belichtungsstufen, Materialien im Raum, die Anordnung von Objekten und vieles mehr, können sich auf die Art und Weise auswirken, wie HoloLens einen Bereich kartiert.</span><span class="sxs-lookup"><span data-stu-id="36eda-118">Light levels, materials in the space, the layout of objects, and more can all affect how HoloLens maps an area.</span></span>

<span data-ttu-id="36eda-119">HoloLens funktioniert am besten in bestimmten Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="36eda-119">HoloLens works best in certain kinds of environments.</span></span> <span data-ttu-id="36eda-120">Um die beste räumliche Karte zu erstellen, wählen Sie einen Raum mit ausreichend Licht und viel Platz.</span><span class="sxs-lookup"><span data-stu-id="36eda-120">To produce the best spatial map, choose a room that has adequate light and plenty of space.</span></span> <span data-ttu-id="36eda-121">Vermeiden Sie dunkle Räume und Räume mit vielen dunklen, glänzenden oder durchscheinenden Oberflächen (z.B. Spiegel oder lichtdurchlässige Gardinen).</span><span class="sxs-lookup"><span data-stu-id="36eda-121">Avoid dark spaces and rooms that have a lot of dark, shiny, or translucent surfaces (for instance, mirrors or gauzy curtains).</span></span>

<span data-ttu-id="36eda-122">HoloLens ist für den Inneneinsatz optimiert.</span><span class="sxs-lookup"><span data-stu-id="36eda-122">HoloLens is optimized for indoor use.</span></span> <span data-ttu-id="36eda-123">Die räumliche Zuordnung funktioniert am besten bei aktiviertem WLAN, auch wenn es nicht mit einem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="36eda-123">Spatial mapping also works best when Wi-Fi is turned on, although it doesn't have to be connected to a network.</span></span> <span data-ttu-id="36eda-124">HoloLens kann WLAN-Zugriffspunkte abrufen, auch wenn es nicht verbunden oder authentifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="36eda-124">HoloLens can obtain Wi-Fi access points even if it is not connected or authenticated.</span></span> <span data-ttu-id="36eda-125">Die HoloLens-Funktionalität ändert sich nicht, wenn die Zugriffspunkte mit dem Internet, Intranet oder lokal verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="36eda-125">HoloLens functionality does not change whether the access points are internet-connected or intranet/local only.</span></span>

<span data-ttu-id="36eda-126">Verwenden Sie HoloLens nur an sicheren Orten ohne Stolperfallen.</span><span class="sxs-lookup"><span data-stu-id="36eda-126">Only use HoloLens in safe places with no tripping hazards.</span></span> <span data-ttu-id="36eda-127">[Mehr zur Sicherheit](https://support.microsoft.com/help/4023454/safety-information).</span><span class="sxs-lookup"><span data-stu-id="36eda-127">[More on safety](https://support.microsoft.com/help/4023454/safety-information).</span></span>

## <span data-ttu-id="36eda-128">Kartieren Ihres Raumes</span><span class="sxs-lookup"><span data-stu-id="36eda-128">Mapping your space</span></span>

<span data-ttu-id="36eda-129">Jetzt können Sie mit der Zuordnung Ihres Raumes beginnen.</span><span class="sxs-lookup"><span data-stu-id="36eda-129">Now you're ready to start mapping your spare.</span></span>  <span data-ttu-id="36eda-130">Wenn HoloLens die Zuordnung Ihrer Umgebung beginnt, wird ein Gittermodell angezeigt, das sich über dem Raum ausbreitet.</span><span class="sxs-lookup"><span data-stu-id="36eda-130">When HoloLens starts mapping your surroundings, you'll see a mesh graphic spreading over the space.</span></span>  <span data-ttu-id="36eda-131">In der Mixed Reality Startumgebung können Sie die Anzeige der Karte auslösen, indem Sie eine zugeordnete Oberfläche auswählen.</span><span class="sxs-lookup"><span data-stu-id="36eda-131">In mixed reality home, you can trigger the map to show by selecting on a mapped surface.</span></span>

<span data-ttu-id="36eda-132">Hier finden Sie Anleitungen zum Erstellen einer großartigen räumlichen Karte.</span><span class="sxs-lookup"><span data-stu-id="36eda-132">Here are guidelines for building a great spatial map.</span></span>

### <span data-ttu-id="36eda-133">Grundlegende Informationen zu den Szenarien der Umgebung</span><span class="sxs-lookup"><span data-stu-id="36eda-133">Understand the scenarios for the area</span></span>

<span data-ttu-id="36eda-134">Es ist wichtig, dass Sie die meiste Zeit dort verbringen, wo HoloLens verwendet wird, damit die Karte relevant und vollständig ist.</span><span class="sxs-lookup"><span data-stu-id="36eda-134">It is important to spend the most time where you will be using the HoloLens, so that the map is relevant and complete.</span></span> <span data-ttu-id="36eda-135">Wenn z.B. ein Benutzerszenario für HoloLens die Bewegung von Punkt A nach Punkt B erfordert, gehen Sie diesen Pfad zwei bis dreimal und sehen Sie sich dabei in alle Richtungen um.</span><span class="sxs-lookup"><span data-stu-id="36eda-135">For example, if a user scenario for HoloLens involves moving from Point A to Point B, walk that path two to three times, looking in all directions as you move.</span></span>  

### <span data-ttu-id="36eda-136">Gehen Sie langsam im Raum herum</span><span class="sxs-lookup"><span data-stu-id="36eda-136">Walk slowly around the space</span></span>

<span data-ttu-id="36eda-137">Wenn Sie sich zu schnell bewegen, fehlen HoloLens möglicherweise einige Zuordnungsbereiche.</span><span class="sxs-lookup"><span data-stu-id="36eda-137">If you walk too quickly around the area, it's likely that the HoloLens will miss mapping areas.</span></span> <span data-ttu-id="36eda-138">Gehen Sie langsam durch den Raum, halten Sie alle 1,5–2,5m an und sehen Sie sich in Ihrer Umgebung um.</span><span class="sxs-lookup"><span data-stu-id="36eda-138">Walk slowly around the space, stopping every 5-8 feet to look around at your surroundings.</span></span>  

<span data-ttu-id="36eda-139">Mit weichen Bewegungen wird Ihre HoloLens-Karte genauer.</span><span class="sxs-lookup"><span data-stu-id="36eda-139">Smooth movements also help the HoloLens map more efficiently.</span></span>

### <span data-ttu-id="36eda-140">Sehen Sie sich in alle Richtungen um.</span><span class="sxs-lookup"><span data-stu-id="36eda-140">Look in all directions</span></span>

<span data-ttu-id="36eda-141">Wenn Sie sich beim Kartieren des Raums umschauen, erhält die HoloLens mehr Daten darüber, wo Punkte relativ zueinander sind.</span><span class="sxs-lookup"><span data-stu-id="36eda-141">Looking around as you map the space gives the HoloLens more data on where points are relative to each other.</span></span>  

<span data-ttu-id="36eda-142">Wenn Sie beispielsweise nicht nach oben sehen, weiß HoloLens möglicherweise nicht, wo sich die Decke befindet.</span><span class="sxs-lookup"><span data-stu-id="36eda-142">If you don't look up, for example, the HoloLens may not know where the ceiling in a room is.</span></span>  

<span data-ttu-id="36eda-143">Vergessen Sie nicht, beim Kartieren auf den Boden zu sehen.</span><span class="sxs-lookup"><span data-stu-id="36eda-143">Don't forget to look down at the floor as you map the space.</span></span>

### <span data-ttu-id="36eda-144">Schlüsselbereiche mehrfach abdecken</span><span class="sxs-lookup"><span data-stu-id="36eda-144">Cover key areas multiple times</span></span>

<span data-ttu-id="36eda-145">Wenn Sie mehrere Male durch einen Bereich gehen, werden möglicherweise Einzelheiten erfasst, die beim ersten Durchgang übersehen wurden.</span><span class="sxs-lookup"><span data-stu-id="36eda-145">Moving through an area multiple times will help pick up features you may have missed on the first walkthrough.</span></span> <span data-ttu-id="36eda-146">Wenn Sie eine ideale Karte erstellen möchten, versuchen Sie, einen Bereich zwei bis dreimal zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="36eda-146">To build an ideal map, try traversing an area two to three times.</span></span>

<span data-ttu-id="36eda-147">Wenn möglich, durchgehen Sie einen Bereich in eine Richtung, drehen sich dann um und gehen den gleichen Weg zurück.</span><span class="sxs-lookup"><span data-stu-id="36eda-147">If possible, while repeating these movements, spend time walking through an area in one direction, then turn around and walk back the way you came.</span></span>

### <span data-ttu-id="36eda-148">Nehmen Sie sich Zeit, um den Bereich zu kartieren</span><span class="sxs-lookup"><span data-stu-id="36eda-148">Take your time mapping the area</span></span>

<span data-ttu-id="36eda-149">Es kann 15 bis 20 Minuten dauern, bis sich HoloLens vollständig an die Umgebung angepasst und sie kartiert hat.</span><span class="sxs-lookup"><span data-stu-id="36eda-149">It can take between 15 and 20 minutes for the HoloLens to fully map and adjust itself to its surroundings.</span></span> <span data-ttu-id="36eda-150">Wenn Sie HoloLens in einem bestimmten Raum häufig verwenden möchten, können Sie im Vorfeld die Zeit nutzen und den Raum kartieren, um spätere Probleme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="36eda-150">If you have a space in which you plan to use a HoloLens frequently, taking that time up front to map the space can prevent issues later on.</span></span>  

## <span data-ttu-id="36eda-151">Mögliche Fehler in der räumlichen Zuordnung</span><span class="sxs-lookup"><span data-stu-id="36eda-151">Possible errors in the spatial map</span></span>

<span data-ttu-id="36eda-152">Die Fehler in den Kartierungsdaten lassen sich in einige Kategorien unterteilen:</span><span class="sxs-lookup"><span data-stu-id="36eda-152">Errors in spatial mapping data fall into a few categories:</span></span>

- <span data-ttu-id="36eda-153">*Löcher*: Reale Oberflächen fehlen in den Kartierungsdaten.</span><span class="sxs-lookup"><span data-stu-id="36eda-153">*Holes*: Real-world surfaces are missing from the spatial mapping data.</span></span>
- <span data-ttu-id="36eda-154">*Halluzinationen*: Flächen in den Kartierungsdaten sind in der Realität nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="36eda-154">*Hallucinations*: Surfaces exist in the spatial mapping data that do not exist in the real world.</span></span>
- <span data-ttu-id="36eda-155">*Wurmlöcher*: HoloLens „verliert“ einen Teil der räumlichen Karte, indem sie sich woanders verortet als sie sich tatsächlich befindet.</span><span class="sxs-lookup"><span data-stu-id="36eda-155">*Wormholes*: HoloLens 'loses' part of the spatial map by thinking it is in a different part of the map than it actually is.</span></span>
- <span data-ttu-id="36eda-156">*Bias*: Flächen in den Kartierungsdaten werden nicht perfekt an realen Oberflächen ausgerichtet, entweder nach hinten oder nach vorne verschoben.</span><span class="sxs-lookup"><span data-stu-id="36eda-156">*Bias*: Surfaces in the spatial mapping data are imperfectly aligned with real-world surfaces, either pushed in or pulled out.</span></span>

<span data-ttu-id="36eda-157">Wenn einer dieser Fehler angezeigt wird, senden Sie Ihr Feedback an [FeedbackHub](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="36eda-157">If you see any of these errors please use the [FeedbackHub](hololens-feedback.md) to send feedback.</span></span>

## <span data-ttu-id="36eda-158">Sicherheit und Speicherplatz für räumliche Daten</span><span class="sxs-lookup"><span data-stu-id="36eda-158">Security and storage for spatial data</span></span>

<span data-ttu-id="36eda-159">Das Windows 10-Update für Version 1803 für Microsoft HoloLens und höher speichert Zuordnungsdaten in einer lokalen Datenbank (auf dem Gerät).</span><span class="sxs-lookup"><span data-stu-id="36eda-159">Windows 10 version 1803 update for Microsoft HoloLens and later stores mapping data in a local (on-device) database.</span></span>

<span data-ttu-id="36eda-160">HoloLens-Benutzer können nicht direkt auf die Kartendatenbank zugreifen, selbst wenn das Gerät an einen PC oder die Datei-Explorer-App angeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="36eda-160">HoloLens users cannot directly access the map database, even when the device is plugged into a PC or when using the File Explorer app.</span></span> <span data-ttu-id="36eda-161">Wenn BitLocker auf HoloLens aktiviert ist, werden die gespeicherten Kartendaten auch zusammen mit dem gesamten Volume verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="36eda-161">When BitLocker is enabled on HoloLens, the stored map data is also encrypted along with the entire volume.</span></span>

### <span data-ttu-id="36eda-162">Kartendaten und bekannte Räume aus HoloLens entfernen</span><span class="sxs-lookup"><span data-stu-id="36eda-162">Remove map data and known spaces from HoloLens</span></span>

<span data-ttu-id="36eda-163">Es gibt zwei Optionen zum Löschen von Kartendaten in **Einstellungen > System > Hologramme**:</span><span class="sxs-lookup"><span data-stu-id="36eda-163">There are two options for deleting map data in **Settings > System > Holograms**:</span></span>

- <span data-ttu-id="36eda-164">Wenn Sie Hologramme in der Nähe löschen möchten, wählen Sie **Hologramme in der Nähe entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="36eda-164">To delete nearby holograms, select **Remove nearby holograms**.</span></span> <span data-ttu-id="36eda-165">Mit diesem Befehl werden die Kartendaten und die verknüpften Hologramme für den aktuellen Raum gelöscht.</span><span class="sxs-lookup"><span data-stu-id="36eda-165">This command clears the map data and anchored holograms for the current space.</span></span> <span data-ttu-id="36eda-166">Wenn Sie das Gerät weiterhin im selben Raum verwenden, wird ein ganz neuer Kartenabschnitt erstellt und gespeichert, um die gelöschten Informationen zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="36eda-166">If you continue to use the device in the same space, it creates and stores a brand new map section to replace the deleted information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="36eda-167">Hologramme „in der Nähe“ sind Hologramme, die im aktuellen Raum im selben Kartenabschnitt verankert sind.</span><span class="sxs-lookup"><span data-stu-id="36eda-167">"Nearby" holograms are holograms that are anchored within the same map section in the current space.</span></span>

   <span data-ttu-id="36eda-168">Mit dieser Option können Sie beispielsweise arbeitsbezogene Kartendaten löschen, ohne dass dies Auswirkungen auf hausbezogene Kartendaten hat.</span><span class="sxs-lookup"><span data-stu-id="36eda-168">For example, you can use this option to clear work-related map data without affecting any home-related map data.</span></span>

- <span data-ttu-id="36eda-169">Wenn Sie alle Hologramme löschen möchten, wählen Sie **Alle Hologramme entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="36eda-169">To delete all holograms, select **Remove all holograms**.</span></span> <span data-ttu-id="36eda-170">Mit diesem Befehl werden alle auf dem Gerät gespeicherten Kartendaten sowie alle verankerten Hologramme gelöscht.</span><span class="sxs-lookup"><span data-stu-id="36eda-170">This command clears all map data that is stored on the device as well as all anchored holograms.</span></span> <span data-ttu-id="36eda-171">Sie müssen alle Hologramme explizit platzieren.</span><span class="sxs-lookup"><span data-stu-id="36eda-171">You will need to explicitly place any holograms.</span></span> <span data-ttu-id="36eda-172">Sie können die zuvor platzierten Hologramme nicht neu entdecken.</span><span class="sxs-lookup"><span data-stu-id="36eda-172">You will not be able to rediscover the previously-placed holograms.</span></span>

> [!NOTE]
> <span data-ttu-id="36eda-173">Nachdem Sie die in der Nähe befindlichen oder alle Hologramme entfernt haben, beginnt HoloLens sofort mit dem Überprüfen und Zuordnen des aktuellen Raumes.</span><span class="sxs-lookup"><span data-stu-id="36eda-173">After you remove nearby or all holograms, HoloLens immediately starts scanning and mapping the current space.</span></span>

### <span data-ttu-id="36eda-174">WLAN-Daten in räumlichen Karten</span><span class="sxs-lookup"><span data-stu-id="36eda-174">Wi-Fi data in spatial maps</span></span>

<span data-ttu-id="36eda-175">HoloLens speichert WLAN-Merkmale, um Rabattenkompositionen und Kartenbereiche, die in der HoloLens-Datenbank bekannter Räume gespeichert sind, in Korrelation zu bringen.</span><span class="sxs-lookup"><span data-stu-id="36eda-175">HoloLens stores Wi-Fi characteristics to help correlate hologram locations and map sections that are stored within the HoloLens database of known spaces.</span></span> <span data-ttu-id="36eda-176">Informationen zu WLAN-Merkmalen sind für Benutzer nicht zugänglich und werden nicht über die Cloud oder über Telemetrie an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="36eda-176">Information about Wi-Fi characteristics is not accessible to users, and not sent to Microsoft using the cloud or using telemetry.</span></span>

<span data-ttu-id="36eda-177">Solange WLAN aktiviert ist, korreliert HoloLens Kartendaten mit WLAN-Zugriffspunkten in der Nähe.</span><span class="sxs-lookup"><span data-stu-id="36eda-177">As long as Wi-Fi is enabled, HoloLens correlates map data with nearby Wi-Fi access points.</span></span> <span data-ttu-id="36eda-178">Es gibt keinen Unterschied im Verhalten, ob ein Netzwerk verbunden ist oder nur in der Nähe erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="36eda-178">There is no difference in behavior whether a network is connected or just detected nearby.</span></span> <span data-ttu-id="36eda-179">Wenn WLAN deaktiviert ist, durchsucht HoloLens den Raum weiterhin.</span><span class="sxs-lookup"><span data-stu-id="36eda-179">If Wi-Fi is disabled, HoloLens still searches the space.</span></span> <span data-ttu-id="36eda-180">HoloLens muss jedoch mehr Kartendaten in der Datenbank des Raumes durchsuchen und benötigt möglicherweise mehr Zeit zum Auffinden von Hologrammen.</span><span class="sxs-lookup"><span data-stu-id="36eda-180">However, HoloLens has to search more of the map data within the spaces database, and may need more time to find holograms.</span></span> <span data-ttu-id="36eda-181">Ohne die WLAN-Informationen muss HoloLens aktive Scans mit allen Hologramm- und Kartenabschnitten vergleichen, die auf dem Gerät gespeichert sind, um den richtigen Teil der Karte zu finden.</span><span class="sxs-lookup"><span data-stu-id="36eda-181">Without the Wi-Fi info, the HoloLens has to compare active scans to all hologram anchors and map sections that are stored on the device in order to locate the correct portion of the map.</span></span>

## <span data-ttu-id="36eda-182">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="36eda-182">Related topics</span></span>

- [<span data-ttu-id="36eda-183">Entwurf der Raumabbildung</span><span class="sxs-lookup"><span data-stu-id="36eda-183">Spatial mapping design</span></span>](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
