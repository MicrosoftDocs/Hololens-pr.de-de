---
title: Verwenden des 3D-Viewers (Beta) mit HoloLens (1. Generation)
description: Beschreibt die Dateitypen und Features, die vom 3D-Viewer (Beta) auf HoloLens (1. Generation) unterstützt werden, sowie Informationen zur Verwendung und Problembehandlung für die App.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f5481d6466459667deb99232fdd67c4491798cbe
ms.sourcegitcommit: 1b19b0eb552189d7c50617bbdf3a102d3c85ee0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016286"
---
# <span data-ttu-id="83c9a-103">Verwenden des 3D-Viewers (Beta) mit HoloLens (1. Generation)</span><span class="sxs-lookup"><span data-stu-id="83c9a-103">Using 3D Viewer Beta on HoloLens (1st gen)</span></span>

<span data-ttu-id="83c9a-104">3D-Viewer (Beta) ermöglicht das Anzeigen von 3D-Modellen auf HoloLens (1. Generation).</span><span class="sxs-lookup"><span data-stu-id="83c9a-104">3D Viewer Beta lets you view 3D models on HoloLens (1st gen).</span></span> <span data-ttu-id="83c9a-105">Sie können *unterstütze* FBX-Dateien von Microsoft Edge, OneDrive und anderen Apps öffnen und anzeigen.</span><span class="sxs-lookup"><span data-stu-id="83c9a-105">You can open and view *supported* .fbx files from Microsoft Edge, OneDrive, and other apps.</span></span>

>[!NOTE]
><span data-ttu-id="83c9a-106">Dieser Artikel bezieht sich auf die immersive Einheit **3D-Viewer (Beta)**-App, die FBX-Dateien unterstützt und nur auf HoloLens (1. Generation) verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="83c9a-106">This article applies to the immersive Unity **3D Viewer Beta** app, which supports .fbx files and is only available on HoloLens (1st gen).</span></span> <span data-ttu-id="83c9a-107">Die vorinstallierte **3D-Viewer**-App auf HoloLens 2 unterstützt das Öffnen von benutzerdefinierten GLB 3D-Modellen in der Mixed-Reality-Startseite (Weitere Informationen finden Sie unter [Übersicht über die Asset-Voraussetzungen](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview)).</span><span class="sxs-lookup"><span data-stu-id="83c9a-107">The pre-installed **3D Viewer** app on HoloLens 2 supports opening custom .glb 3D models in the mixed reality home (see [Asset requirements overview](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) for more details.</span></span>

>[!IMPORTANT]
><span data-ttu-id="83c9a-108">Der 3D Viewer (Beta) ist zwar im Microsoft Store für HoloLens (1. Generation) weiterhin verfügbar, wird aber nicht mehr aktiv weiterentwickelt und auch nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="83c9a-108">While 3D Viewer Beta may remain available in the Microsoft Store for HoloLens (1st gen), it is no longer in active development and is no longer supported.</span></span>

<span data-ttu-id="83c9a-109">Wenn es beim Öffnen eines 3D-Modells im 3D-Viewer (Beta) Probleme gibt oder bestimmte Features Ihres 3D-Modells nicht unterstützt werden, lesen Sie die[Spezifikationen für unterstützte Inhalte](#supported-content-specifications) weiter unten.</span><span class="sxs-lookup"><span data-stu-id="83c9a-109">If you're having trouble opening a 3D model in 3D Viewer Beta, or certain features of your 3D model are unsupported, see [Supported content specifications](#supported-content-specifications) below.</span></span>

<span data-ttu-id="83c9a-110">Informationen zum Erstellen oder Optimieren von 3D-Modellen zur Verwendung mit 3D-Viewer (Beta) finden Sie unter [Optimieren von 3D-Modellen für 3D-Viewer (Beta)](#optimizing-3d-models-for-3d-viewer-beta).</span><span class="sxs-lookup"><span data-stu-id="83c9a-110">To build or optimize 3D models for use with 3D Viewer Beta, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) below.</span></span>

<span data-ttu-id="83c9a-111">Es gibt zwei Möglichkeiten, um ein 3D-Modell auf HoloLens zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="83c9a-111">There are two ways to open a 3D model on HoloLens.</span></span> <span data-ttu-id="83c9a-112">Weitere Informationen hierzu finden Sie in [Anzeigen von FBX-Dateien auf HoloLens](#viewing-fbx-files-on-hololens) weiter unten.</span><span class="sxs-lookup"><span data-stu-id="83c9a-112">See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) below to learn more.</span></span>

<span data-ttu-id="83c9a-113">Wenn Sie nach dem Lesen dieser Themen auf Probleme stoßen, lesen Sie [Problembehandlung](#troubleshooting) weiter unten.</span><span class="sxs-lookup"><span data-stu-id="83c9a-113">If you're having trouble after reading these topics, see [Troubleshooting](#troubleshooting) below.</span></span>

## <span data-ttu-id="83c9a-114">Spezifikationen für unterstützte Inhalte</span><span class="sxs-lookup"><span data-stu-id="83c9a-114">Supported content specifications</span></span>

### <span data-ttu-id="83c9a-115">Dateiformat</span><span class="sxs-lookup"><span data-stu-id="83c9a-115">File format</span></span>

- <span data-ttu-id="83c9a-116">FBX-Format</span><span class="sxs-lookup"><span data-stu-id="83c9a-116">FBX format</span></span>
- <span data-ttu-id="83c9a-117">Maximale FBX-Version 2015.1.0</span><span class="sxs-lookup"><span data-stu-id="83c9a-117">Maximum FBX release 2015.1.0</span></span>

### <span data-ttu-id="83c9a-118">Dateigröße</span><span class="sxs-lookup"><span data-stu-id="83c9a-118">File size</span></span>

- <span data-ttu-id="83c9a-119">Mindestens 5 KB</span><span class="sxs-lookup"><span data-stu-id="83c9a-119">Minimum 5 KB</span></span>
- <span data-ttu-id="83c9a-120">Maximal 500 MB</span><span class="sxs-lookup"><span data-stu-id="83c9a-120">Maximum 500 MB</span></span>

### <span data-ttu-id="83c9a-121">Geometrie</span><span class="sxs-lookup"><span data-stu-id="83c9a-121">Geometry</span></span>

- <span data-ttu-id="83c9a-122">Nur Polygonmodelle.</span><span class="sxs-lookup"><span data-stu-id="83c9a-122">Polygonal models only.</span></span> <span data-ttu-id="83c9a-123">Keine Unterteilungsflächen oder NURBs</span><span class="sxs-lookup"><span data-stu-id="83c9a-123">No subdivision surfaces or NURBs</span></span>
- <span data-ttu-id="83c9a-124">Rechtshändiges Koordinatensystem</span><span class="sxs-lookup"><span data-stu-id="83c9a-124">Right-handed coordinate system</span></span>
- <span data-ttu-id="83c9a-125">Scheren in Transformationsmatrizen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="83c9a-125">Shear in transformation matrices is not supported</span></span>

### <span data-ttu-id="83c9a-126">Texturen</span><span class="sxs-lookup"><span data-stu-id="83c9a-126">Textures</span></span>

- <span data-ttu-id="83c9a-127">Texturkarten müssen in die FBX-Datei eingebettet sein</span><span class="sxs-lookup"><span data-stu-id="83c9a-127">Texture maps must be embedded in the FBX file</span></span>
- <span data-ttu-id="83c9a-128">Unterstützte Bildformate</span><span class="sxs-lookup"><span data-stu-id="83c9a-128">Supported image formats</span></span>
  - <span data-ttu-id="83c9a-129">JPEG- und PNG-Bilder</span><span class="sxs-lookup"><span data-stu-id="83c9a-129">JPEG and PNG images</span></span>
  - <span data-ttu-id="83c9a-130">BMP-Bilder (24-Bit RGB-True-Color)</span><span class="sxs-lookup"><span data-stu-id="83c9a-130">BMP images (24-bit RGB true-color)</span></span>
  - <span data-ttu-id="83c9a-131">TGA-Bilder (24-Bit RGB und 32-Bit RGBQ True-Color)</span><span class="sxs-lookup"><span data-stu-id="83c9a-131">TGA images (24-bit RGB and 32-bit RGBQ true-color)</span></span>
- <span data-ttu-id="83c9a-132">Maximale Texturauflösung von 2.048 x 2.048</span><span class="sxs-lookup"><span data-stu-id="83c9a-132">Maximum texture resolution of 2048x2048</span></span>
- <span data-ttu-id="83c9a-133">Maximale Anzahl einer diffusen Karte, einer normalen Karte und eine Reflexionswürfelkarte pro Gittermodell</span><span class="sxs-lookup"><span data-stu-id="83c9a-133">Maximum of one diffuse map, one normal map, and one reflection cube map per mesh</span></span>
- <span data-ttu-id="83c9a-134">Alpha-Kanal in diffusen Texturen bewirkt, dass Pixel unter 50 % verworfen werden</span><span class="sxs-lookup"><span data-stu-id="83c9a-134">Alpha channel in diffuse textures causes pixels to be discarded if below 50%</span></span>

### <span data-ttu-id="83c9a-135">Animation</span><span class="sxs-lookup"><span data-stu-id="83c9a-135">Animation</span></span>

- <span data-ttu-id="83c9a-136">Skalieren/Drehung/Translation von Animationen auf einzelne Objekte</span><span class="sxs-lookup"><span data-stu-id="83c9a-136">Scale/rotation/translation animation on individual objects</span></span>
- <span data-ttu-id="83c9a-137">Skelettartige (manipulierte) Animation unter Anwendung von Skins</span><span class="sxs-lookup"><span data-stu-id="83c9a-137">Skeletal (rigged) animation with skinning</span></span>
  - <span data-ttu-id="83c9a-138">Maximal 4 Einflüsse pro Scheitelpunkt</span><span class="sxs-lookup"><span data-stu-id="83c9a-138">Maximum of 4 influences per vertex</span></span>

### <span data-ttu-id="83c9a-139">Materialien</span><span class="sxs-lookup"><span data-stu-id="83c9a-139">Materials</span></span>

- <span data-ttu-id="83c9a-140">Lambert- und Phong-Materialien werden unterstützt, mit einstellbaren Parametern</span><span class="sxs-lookup"><span data-stu-id="83c9a-140">Lambert and Phong materials are supported, with adjustable parameters</span></span>
- <span data-ttu-id="83c9a-141">Unterstützte Materialeigenschaften für Lambert</span><span class="sxs-lookup"><span data-stu-id="83c9a-141">Supported material properties for Lambert</span></span>
  - <span data-ttu-id="83c9a-142">Haupttextur (RGB + Alpha-Test)</span><span class="sxs-lookup"><span data-stu-id="83c9a-142">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="83c9a-143">Diffuse Farbe (RGB)</span><span class="sxs-lookup"><span data-stu-id="83c9a-143">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="83c9a-144">Umgebungsfarbe (RGB)</span><span class="sxs-lookup"><span data-stu-id="83c9a-144">Ambient Color (RGB)</span></span>
- <span data-ttu-id="83c9a-145">Unterstützte Materialeigenschaften für Phong</span><span class="sxs-lookup"><span data-stu-id="83c9a-145">Supported material properties for Phong</span></span>
  - <span data-ttu-id="83c9a-146">Haupttextur (RGB + Alpha-Test)</span><span class="sxs-lookup"><span data-stu-id="83c9a-146">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="83c9a-147">Diffuse Farbe (RGB)</span><span class="sxs-lookup"><span data-stu-id="83c9a-147">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="83c9a-148">Umgebungsfarbe (RGB)</span><span class="sxs-lookup"><span data-stu-id="83c9a-148">Ambient Color (RGB)</span></span>
  - <span data-ttu-id="83c9a-149">Glanzfarbe (RGB)</span><span class="sxs-lookup"><span data-stu-id="83c9a-149">Specular Color (RGB)</span></span>
  - <span data-ttu-id="83c9a-150">Glanz</span><span class="sxs-lookup"><span data-stu-id="83c9a-150">Shininess</span></span>
  - <span data-ttu-id="83c9a-151">Reflektivität</span><span class="sxs-lookup"><span data-stu-id="83c9a-151">Reflectivity</span></span>
- <span data-ttu-id="83c9a-152">Benutzerdefinierte Materialien werden nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="83c9a-152">Custom materials are not supported</span></span>
- <span data-ttu-id="83c9a-153">Höchstens ein Material pro Gittermodell</span><span class="sxs-lookup"><span data-stu-id="83c9a-153">Maximum of one material per mesh</span></span>
- <span data-ttu-id="83c9a-154">Höchstens eine Materialschicht</span><span class="sxs-lookup"><span data-stu-id="83c9a-154">Maximum of one material layer</span></span>
- <span data-ttu-id="83c9a-155">Höchstens 8 Materialien pro Datei</span><span class="sxs-lookup"><span data-stu-id="83c9a-155">Maximum of 8 materials per file</span></span>

### <span data-ttu-id="83c9a-156">Datei- und Modellbeschränkungen</span><span class="sxs-lookup"><span data-stu-id="83c9a-156">File and model limitations</span></span>

<span data-ttu-id="83c9a-157">Es gibt feste Beschränkungen hinsichtlich der Dateigröße sowie der Anzahl der Modelle, Scheitelpunkte und Gittermodelle, die im 3D-Viewer (Beta) gleichzeitig geöffnet sein können:</span><span class="sxs-lookup"><span data-stu-id="83c9a-157">There are hard limits on the size of files, as well as the number of models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta:</span></span>

- <span data-ttu-id="83c9a-158">500MB maximale Dateigröße pro Modell</span><span class="sxs-lookup"><span data-stu-id="83c9a-158">500 MB maximum file size per model</span></span>
- <span data-ttu-id="83c9a-159">Scheitelpunkte:600.000insgesamt in allen geöffneten Modellen</span><span class="sxs-lookup"><span data-stu-id="83c9a-159">Vertices: 600,000 combined on all open models</span></span>
- <span data-ttu-id="83c9a-160">Gittermodelle:1.600insgesamt in allen geöffneten Modellen</span><span class="sxs-lookup"><span data-stu-id="83c9a-160">Meshes: 1,600 combined on all open models</span></span>
- <span data-ttu-id="83c9a-161">Höchstens 40 Modelle gleichzeitig geöffnet</span><span class="sxs-lookup"><span data-stu-id="83c9a-161">Maximum of 40 models open at one time</span></span>

## <span data-ttu-id="83c9a-162">Optimieren von 3D-Modellen für 3D-Viewer (Beta)</span><span class="sxs-lookup"><span data-stu-id="83c9a-162">Optimizing 3D models for 3D Viewer Beta</span></span>

### <span data-ttu-id="83c9a-163">Praktische Überlegungen</span><span class="sxs-lookup"><span data-stu-id="83c9a-163">Special considerations</span></span>

- <span data-ttu-id="83c9a-164">Vermeiden Sie schwarze Materialien oder schwarze Bereiche in Textkurkarten.</span><span class="sxs-lookup"><span data-stu-id="83c9a-164">Avoid black materials or black areas in texture maps.</span></span> <span data-ttu-id="83c9a-165">Hologramme bestehen aus Licht. Deshalb rendert HoloLens schwarz (die Abwesenheit von Licht) als transparent.</span><span class="sxs-lookup"><span data-stu-id="83c9a-165">Holograms are made of light, thus HoloLens renders black (the absence of light) as transparent.</span></span>
- <span data-ttu-id="83c9a-166">Vergewissern Sie sich vor dem Exportieren nach FBX aus dem Erstellungstool, dass alle Geometrien sichtbar und entriegelt sind und keine Ebenen, die Geometrie enthalten, deaktiviert oder mit einer Vorlage versehen sind.</span><span class="sxs-lookup"><span data-stu-id="83c9a-166">Before exporting to FBX from your creation tool, ensure all geometry is visible and unlocked and no layers that contain geometry are turned off or templated.</span></span> <span data-ttu-id="83c9a-167">Sichtbarkeit wird nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="83c9a-167">Visibility is not respected.</span></span>
- <span data-ttu-id="83c9a-168">Vermeiden Sie sehr große Translation-Offsets zwischen den Knoten (beispielsweise 100.000Einheiten).</span><span class="sxs-lookup"><span data-stu-id="83c9a-168">Avoid very large translation offsets between nodes (for example, 100,000 units).</span></span> <span data-ttu-id="83c9a-169">Das kann dazu führen, dass das Modell während des Verschiebens/Skalierens/Drehens wackelt.</span><span class="sxs-lookup"><span data-stu-id="83c9a-169">This can cause the model to jitter while being moved/scaled/rotated.</span></span>

### <span data-ttu-id="83c9a-170">Leistungsoptimierung</span><span class="sxs-lookup"><span data-stu-id="83c9a-170">Performance optimization</span></span>

<span data-ttu-id="83c9a-171">Berücksichtigen Sie beim Erstellen von Inhalten die Leistung und validieren Sie in der 3D-Viewer-App (Beta) auf HoloLens während des Erstellungsprozesses, um optimale Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="83c9a-171">Keep performance in mind while authoring content and validate in the 3D Viewer Beta app on HoloLens during the authoring process for best results.</span></span> <span data-ttu-id="83c9a-172">3D-Viewer (Beta) rendert Inhalte in Echtzeit. Die Leistung unterliegt den HoloLens-Hardwarefunktionen.</span><span class="sxs-lookup"><span data-stu-id="83c9a-172">3D Viewer Beta renders content real-time and performance is subject to HoloLens hardware capabilities.</span></span>  

<span data-ttu-id="83c9a-173">Ein 3D-Modell enthält zahlreiche Variablen, die sich auf die Leistung auswirken können.</span><span class="sxs-lookup"><span data-stu-id="83c9a-173">There are many variables in a 3D model that can impact performance.</span></span> <span data-ttu-id="83c9a-174">Im 3D-Viewer (Beta) wird beim Laden eine Warnung angezeigt, wenn mehr als 150.000Scheitelpunkte oder mehr als 400 Gittermodelle vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="83c9a-174">3D Viewer Beta will show a warning on load if there are more than 150,000 vertices or more than 400 meshes.</span></span> <span data-ttu-id="83c9a-175">Animationen können sich auf die Leistung anderer offener Modelle auswirken.</span><span class="sxs-lookup"><span data-stu-id="83c9a-175">Animations can have an impact on the performance of other open models.</span></span> <span data-ttu-id="83c9a-176">Es gibt feste Beschränkungen hinsichtlich der Dateigröße sowie der Anzahl der Modelle, Scheitelpunkte und Gittermodelle, die im 3D-Viewer (Beta) gleichzeitig geöffnet sein können (siehe [Datei- und Modellbeschränkungen](#file-and-model-limitations)).</span><span class="sxs-lookup"><span data-stu-id="83c9a-176">There are also hard limits on the total number models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta (see [File and model limitations](#file-and-model-limitations)).</span></span>  

<span data-ttu-id="83c9a-177">Wenn das 3D-Modell aufgrund der Komplexität des Modells nicht ordnungsgemäß ausgeführt wird, ziehen Sie Folgendes in Betracht:</span><span class="sxs-lookup"><span data-stu-id="83c9a-177">If the 3D model isn't running well due to model complexity, consider:</span></span>

- <span data-ttu-id="83c9a-178">Reduzieren der Polygonanzahl</span><span class="sxs-lookup"><span data-stu-id="83c9a-178">Reducing polygon count</span></span>
- <span data-ttu-id="83c9a-179">Verringern der Anzahl von Bones in manipulierten Animationen</span><span class="sxs-lookup"><span data-stu-id="83c9a-179">Reducing number of bones in rigged animation</span></span>
- <span data-ttu-id="83c9a-180">Vermeiden von Selbstokklusion</span><span class="sxs-lookup"><span data-stu-id="83c9a-180">Avoiding self-occlusion</span></span>

<span data-ttu-id="83c9a-181">Das beidseitige Rendering wird im 3D-Viewer (Beta) unterstützt, aus Leistungsgründen ist es jedoch standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="83c9a-181">Double-sided rendering is supported in 3D Viewer Beta, although it is turned off by default for performance reasons.</span></span> <span data-ttu-id="83c9a-182">Das kann über die Schaltfläche **Beidseitig** auf der Seite **Details** aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="83c9a-182">This can be turned on via the **Double Sided** button on the **Details** page.</span></span> <span data-ttu-id="83c9a-183">Vermeiden Sie beidseitiges Rendern Ihrer Inhalte, um eine optimale Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="83c9a-183">For best performance, avoid the need for double-sided rendering in your content.</span></span>

### <span data-ttu-id="83c9a-184">Überprüfen Ihres 3D-Modells</span><span class="sxs-lookup"><span data-stu-id="83c9a-184">Validating your 3D model</span></span>

<span data-ttu-id="83c9a-185">Überprüfen Sie das Modell, indem Sie es im 3D-Viewer (Beta) auf HoloLens öffnen.</span><span class="sxs-lookup"><span data-stu-id="83c9a-185">Validate your model by opening it in 3D Viewer Beta on HoloLens.</span></span> <span data-ttu-id="83c9a-186">Wählen Sie die Schaltfläche **Details** aus, um die Eigenschaften des Modells und Warnungen für nicht unterstützte Inhalte anzuzeigen (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="83c9a-186">Select the **Details** button to view your model's characteristics and warnings of unsupported content (if present).</span></span>

### <span data-ttu-id="83c9a-187">Rendern von 3D-Modellen mit realer Bemaßung</span><span class="sxs-lookup"><span data-stu-id="83c9a-187">Rendering 3D models with true-to-life dimensions</span></span>

<span data-ttu-id="83c9a-188">Standardmäßig zeigt 3D-Viewer (Beta) 3D-Modelle in komfortabler Größe und Position in Relation zur benutzenden Person an.</span><span class="sxs-lookup"><span data-stu-id="83c9a-188">By default, 3D Viewer Beta displays 3D models at a comfortable size and position relative to the user.</span></span> <span data-ttu-id="83c9a-189">Wenn es jedoch wichtig ist, ein 3D-Modell mit realen Maßen darzustellen (wenn Sie beispielsweise Möbelmodelle in einem Raum evaluieren), kann die/der Ersteller/in der Inhalte eine Kennzeichnung in den Metadaten der Datei festlegen, um zu verhindern, dass das Modell sowohl von der Anwendung als auch von den Benutzenden geändert wird.</span><span class="sxs-lookup"><span data-stu-id="83c9a-189">However, if rendering a 3D model with true-to-life measurements is important (for example, when evaluating furniture models in a room), the content creator can set a flag within the file's metadata to prevent resizing of that model by both the application and the user.</span></span>

<span data-ttu-id="83c9a-190">Wenn Sie das Skalieren des Modells verhindern möchten, fügen Sie ein boolesches benutzerdefiniertes Attribut zu jedem Objekt in der Szene mit dem Namen Microsoft_DisableScale hinzu und legen es auf „true“ fest.</span><span class="sxs-lookup"><span data-stu-id="83c9a-190">To prevent scaling of the model, add a Boolean custom attribute to any object in the scene named Microsoft_DisableScale and set it to true.</span></span> <span data-ttu-id="83c9a-191">3D-Viewer (Beta) berücksichtigt dann die FbxSystemUnit-Informationen, die in der FBX-Datei gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="83c9a-191">3D Viewer Beta will then respect the FbxSystemUnit information baked into the FBX file.</span></span> <span data-ttu-id="83c9a-192">Der Maßstab im 3D-Viewer (Beta) entspricht 1 m pro FBX-Einheit.</span><span class="sxs-lookup"><span data-stu-id="83c9a-192">Scale in 3D Viewer Beta is 1 meter per FBX unit.</span></span>

## <span data-ttu-id="83c9a-193">FBX-Dateien auf HoloLens ansehen</span><span class="sxs-lookup"><span data-stu-id="83c9a-193">Viewing FBX files on HoloLens</span></span>

### <span data-ttu-id="83c9a-194">FBX-Datei über Microsoft Edge öffnen</span><span class="sxs-lookup"><span data-stu-id="83c9a-194">Open an FBX file from Microsoft Edge</span></span>

<span data-ttu-id="83c9a-195">FBX-Dateien können direkt über eine Website mit Microsoft Edge auf HoloLens geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="83c9a-195">FBX files can be opened directly from a website using Microsoft Edge on HoloLens.</span></span>

1. <span data-ttu-id="83c9a-196">Navigieren Sie in Microsoft Edge zu der FBX-Datei auf der Webseite, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="83c9a-196">In Microsoft Edge, navigate to the webpage containing the FBX file you want to view.</span></span>
1. <span data-ttu-id="83c9a-197">Wählen Sie die Datei zum Download aus.</span><span class="sxs-lookup"><span data-stu-id="83c9a-197">Select the file to download it.</span></span>
1. <span data-ttu-id="83c9a-198">Wählen Sie nach Abschluss des Downloads die Schaltfläche **Öffnen** in Microsoft Edge aus, um die Datei im 3D-Viewer (Beta) zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="83c9a-198">When the download is complete, select the **Open** button in Microsoft Edge to open the file in 3D Viewer Beta.</span></span>

<span data-ttu-id="83c9a-199">Die heruntergeladene Datei kann später mithilfe von Downloads in Microsoft Edge aufgerufen und erneut geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="83c9a-199">The downloaded file can be accessed and opened again later by using Downloads in Microsoft Edge.</span></span> <span data-ttu-id="83c9a-200">Wenn Sie ein 3D-Modell speichern und den fortgesetzten Zugriff sicherstellen möchten, laden Sie die Datei auf Ihren Computer herunter, und speichern sie in Ihrem OneDrive-Konto.</span><span class="sxs-lookup"><span data-stu-id="83c9a-200">To save a 3D model and ensure continued access, download the file on your PC and save it to your OneDrive account.</span></span> <span data-ttu-id="83c9a-201">Die Datei kann dann über die OneDrive-App auf HoloLens geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="83c9a-201">The file can then be opened from the OneDrive app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="83c9a-202">Einige Websites mit herunterladbaren FBX-Modellen stellen sie im ZIP-Format bereit.</span><span class="sxs-lookup"><span data-stu-id="83c9a-202">Some websites with downloadable FBX models provide them in compressed ZIP format.</span></span> <span data-ttu-id="83c9a-203">3D-Viewer (Beta) kann ZIP-Dateien nicht direkt öffnen.</span><span class="sxs-lookup"><span data-stu-id="83c9a-203">3D Viewer Beta cannot open ZIP files directly.</span></span> <span data-ttu-id="83c9a-204">Verwenden Sie stattdessen Ihren Computer, um die FBX-Datei zu extrahieren und in Ihrem OneDrive-Konto zu speichern.</span><span class="sxs-lookup"><span data-stu-id="83c9a-204">Instead, use your PC to extract the FBX file and save it to your OneDrive account.</span></span> <span data-ttu-id="83c9a-205">Die Datei kann dann über die OneDrive-App auf HoloLens geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="83c9a-205">The file can then be opened from the OneDrive app on HoloLens.</span></span>

### <span data-ttu-id="83c9a-206">Eine FBX-Datei über Microsoft Edge öffnen</span><span class="sxs-lookup"><span data-stu-id="83c9a-206">Open an FBX file from OneDrive</span></span>

<span data-ttu-id="83c9a-207">FBX-Dateien können über OneDrive geöffnet werden, indem Sie die OneDrive-App auf HoloLens verwenden.</span><span class="sxs-lookup"><span data-stu-id="83c9a-207">FBX files can be opened from OneDrive by using the OneDrive app on HoloLens.</span></span> <span data-ttu-id="83c9a-208">Dazu müssen Sie OneDrive mithilfe der Microsoft Store-App auf HoloLens installiert haben und die FBX-Datei muss sich bereits auf OneDrive auf Ihrem PC befinden.</span><span class="sxs-lookup"><span data-stu-id="83c9a-208">Be sure you've installed OneDrive using Microsoft Store app on HoloLens and that you've already uploaded the FBX file to OneDrive on your PC.</span></span>

<span data-ttu-id="83c9a-209">Sobald sich FBX-Dateien in OneDrive befinden, können sie auf zwei Arten auf HoloLens mit dem 3D-Viewer (Beta) geöffnet werden:</span><span class="sxs-lookup"><span data-stu-id="83c9a-209">Once in OneDrive, FBX files can be opened on HoloLens using 3D Viewer Beta in one of two ways:</span></span>

- <span data-ttu-id="83c9a-210">Starten Sie OneDrive auf HoloLens und wählen Sie die FBX-Datei aus, die Sie im 3D-Viewer (Beta) öffnen möchten.</span><span class="sxs-lookup"><span data-stu-id="83c9a-210">Launch OneDrive on HoloLens and select the FBX file to open it in 3D Viewer Beta.</span></span>
- <span data-ttu-id="83c9a-211">Starten Sie den 3D-Viewer (Beta). Tippen Sie in die Luft, um die Symbolleiste anzuzeigen, und wählen Sie **Datei öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="83c9a-211">Launch 3D Viewer Beta, air tap to show the toolbar, and select **Open File**.</span></span> <span data-ttu-id="83c9a-212">OneDrive wird geöffnet und Sie können eine FBX-Datei auswählen.</span><span class="sxs-lookup"><span data-stu-id="83c9a-212">OneDrive will launch, allowing you to select an FBX file.</span></span>

## <span data-ttu-id="83c9a-213">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="83c9a-213">Troubleshooting</span></span>

### <span data-ttu-id="83c9a-214">Beim Öffnen eines 3D-Modells wird eine Warnung angezeigt</span><span class="sxs-lookup"><span data-stu-id="83c9a-214">I see a warning when I open a 3D model</span></span>

<span data-ttu-id="83c9a-215">Sie sehen beim Öffnen eine Warnung, wenn ein 3D-Modell von 3D-Viewer (Beta) nicht unterstützte Features enthält, oder wenn das Modell zu komplex ist und die Leistung beeinträchtigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="83c9a-215">You will see a warning if you attempt to open a 3D model that contains features that are not supported by 3D Viewer Beta, or if the model is too complex and performance may be affected.</span></span> <span data-ttu-id="83c9a-216">Der 3D-Viewer (Beta) lädt zwar weiterhin das 3D-Modell, die Leistung oder die visuelle Wiedergabetreue ist jedoch möglicherweise beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="83c9a-216">3D Viewer Beta will still load the 3D model, but performance or visual fidelity may be compromised.</span></span>

<span data-ttu-id="83c9a-217">Weitere Informationen hierzu finden Sie unter [Spezifikationen für unterstützte Inhalte](#supported-content-specifications) und [Optimieren von 3D-Modellen für 3D-Viewer (Beta)](#optimizing-3d-models-for-3d-viewer-beta).</span><span class="sxs-lookup"><span data-stu-id="83c9a-217">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <span data-ttu-id="83c9a-218">Eine Warnung wird angezeigt und das 3D-Modell wird nicht geladen</span><span class="sxs-lookup"><span data-stu-id="83c9a-218">I see a warning and the 3D model doesn't load</span></span>

<span data-ttu-id="83c9a-219">Eine Fehlermeldung wird angezeigt, wenn der 3D-Viewer (Beta) aufgrund der Komplexität oder Dateigröße ein 3D-Modell nicht laden kann, oder wenn die FBX-Datei beschädigt oder ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="83c9a-219">You will see an error message when 3D Viewer Beta cannot load a 3D model due to complexity or file size, or if the FBX file is corrupt or invalid.</span></span> <span data-ttu-id="83c9a-220">Eine Fehlermeldung wird angezeigt, wenn die maximale Anzahl von Modellen, Scheitelpunkten oder Gittermodellen erreicht ist, die gleichzeitig geöffnet sein können.</span><span class="sxs-lookup"><span data-stu-id="83c9a-220">You will also see an error message if you have reached the limit on the total number of models, vertices, or meshes that can be open simultaneously.</span></span>  

<span data-ttu-id="83c9a-221">Weitere Informationen hierzu finden Sie unter [Spezifikationen für unterstützte Inhalte](#supported-content-specifications) und [Datei- und Modellbeschränkungen](#file-and-model-limitations).</span><span class="sxs-lookup"><span data-stu-id="83c9a-221">For more info, see [Supported content specifications](#supported-content-specifications) and [File and model limitations](#file-and-model-limitations).</span></span>

### <span data-ttu-id="83c9a-222">Mein 3D-Modell wird geladen, wird jedoch nicht wie erwartet angezeigt</span><span class="sxs-lookup"><span data-stu-id="83c9a-222">My 3D model loads, but does not appear as expected</span></span>

<span data-ttu-id="83c9a-223">Wenn Ihr 3D-Modell im 3D-Viewer (Beta) nicht erwartungsgemäß aussieht, tippen Sie in die Luft, um die Symbolleiste anzuzeigen, und wählen Sie dann **Details** aus.</span><span class="sxs-lookup"><span data-stu-id="83c9a-223">If your 3D model does not look as expected in 3D Viewer Beta, air tap to show the toolbar, then select **Details**.</span></span> <span data-ttu-id="83c9a-224">Aspekte der Datei, die vom 3D-Viewer (Beta) nicht unterstützt werden, werden als Warnungen hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="83c9a-224">Aspects of the file which are not supported by 3D Viewer Beta will be highlighted as warnings.</span></span>

<span data-ttu-id="83c9a-225">Das häufigste Problem sind fehlende Texturen, weil sie wahrscheinlich nicht in die FBX-Datei eingebettet sind.</span><span class="sxs-lookup"><span data-stu-id="83c9a-225">The most common issue you might see is missing textures, likely because they are not embedded in the FBX file.</span></span> <span data-ttu-id="83c9a-226">In diesem Fall wird das Modell weiß angezeigt.</span><span class="sxs-lookup"><span data-stu-id="83c9a-226">In this case, the model will appear white.</span></span> <span data-ttu-id="83c9a-227">Dieses Problem kann bei der Erstellung behoben werden. Wählen Sie dazu beim Export aus Ihrem Erstellungstool nach FBX die Option zum Einbetten der Texturen aus.</span><span class="sxs-lookup"><span data-stu-id="83c9a-227">This issue can be addressed in the creation process by exporting from your creation tool to FBX with the embed textures option selected.</span></span>

<span data-ttu-id="83c9a-228">Weitere Informationen hierzu finden Sie unter [Spezifikationen für unterstützte Inhalte](#supported-content-specifications) und [Optimieren von 3D-Modellen für 3D-Viewer (Beta)](#optimizing-3d-models-for-3d-viewer-beta).</span><span class="sxs-lookup"><span data-stu-id="83c9a-228">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <span data-ttu-id="83c9a-229">Beim Anzeigen meines 3D-Modells sinkt die Leistung</span><span class="sxs-lookup"><span data-stu-id="83c9a-229">I experience performance drops while viewing my 3D model</span></span>

<span data-ttu-id="83c9a-230">Die Leistung beim Laden und Anzeigen eines 3D-Modells kann durch die Komplexität des Modells, die Anzahl der gleichzeitig geöffneten Modelle oder die Anzahl der Modelle mit aktiven Animationen beeinflusst werden.</span><span class="sxs-lookup"><span data-stu-id="83c9a-230">Performance when loading and viewing a 3D model can be affected by the complexity of the model, number of models open simultaneously, or number of models with active animations.</span></span>

<span data-ttu-id="83c9a-231">Weitere Informationen hierzu finden Sie unter [Optimieren von 3D-Modellen für 3D-Viewer (Beta)](#optimizing-3d-models-for-3d-viewer-beta) und [Datei- und Modellbeschränkungen](#file-and-model-limitations).</span><span class="sxs-lookup"><span data-stu-id="83c9a-231">For more info, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) and [File and model limitations](#file-and-model-limitations).</span></span>

### <span data-ttu-id="83c9a-232">Wenn ich eine FBX-Datei auf HoloLens öffne, wird sie nicht im 3D-Viewer (Beta) geöffnet.</span><span class="sxs-lookup"><span data-stu-id="83c9a-232">When I open an FBX file on HoloLens, it doesn't open in 3D Viewer Beta</span></span>

<span data-ttu-id="83c9a-233">3D-Viewer (Beta) wird bei der Installation automatisch mit der Dateierweiterung FBX verknüpft.</span><span class="sxs-lookup"><span data-stu-id="83c9a-233">3D Viewer Beta is automatically associated with the .fbx file extension when it is installed.</span></span>

<span data-ttu-id="83c9a-234">Wenn beim Versuch eine FBX-Datei zu öffnen ein Dialogfeld angezeigt wird, das Sie zum Microsoft Store weiterleitet, dann ist derzeit keine App mit der Dateierweiterung .fbx in HoloLens verknüpft.</span><span class="sxs-lookup"><span data-stu-id="83c9a-234">If you try to open an FBX file and see a dialog box that directs you to Microsoft Store, you do not currently have an app associated with the .fbx file extension on HoloLens.</span></span>

<span data-ttu-id="83c9a-235">Stellen Sie sicher, dass 3D Viewer (Beta) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="83c9a-235">Verify that 3D Viewer Beta is installed.</span></span> <span data-ttu-id="83c9a-236">Wenn er nicht installiert ist, laden Sie ihn aus dem Microsoft Store auf HoloLens herunter.</span><span class="sxs-lookup"><span data-stu-id="83c9a-236">If it is not installed, download it from Microsoft Store on HoloLens.</span></span>

<span data-ttu-id="83c9a-237">Wenn der 3D-Viewer (Beta) bereits installiert ist, starten Sie ihn, und versuchen Sie erneut, die Datei zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="83c9a-237">If 3D Viewer Beta is already installed, launch 3D Viewer Beta, then try opening the file again.</span></span> <span data-ttu-id="83c9a-238">Wenn das Problem weiterhin besteht, deinstallieren Sie 3D-Viewer (Beta), und installieren ihn neu.</span><span class="sxs-lookup"><span data-stu-id="83c9a-238">If the issue persists, uninstall and reinstall 3D Viewer Beta.</span></span> <span data-ttu-id="83c9a-239">Dadurch wird die FBX-Dateierweiterung mit 3D-Viewer (Beta) verknüpft.</span><span class="sxs-lookup"><span data-stu-id="83c9a-239">This will re-associate the .fbx file extension with 3D Viewer Beta.</span></span>

<span data-ttu-id="83c9a-240">Wenn beim Versuch, eine FBX-Datei zu öffnen, eine andere App als 3D-Viewer (Beta) geöffnet wird, wurde diese App wahrscheinlich nach dem 3D-Viewer (Beta) installiert und hat die Zuordnung zur Dateierweiterung FBX übernommen.</span><span class="sxs-lookup"><span data-stu-id="83c9a-240">If attempting to open an FBX file opens an app other than 3D Viewer Beta, that app was likely installed after 3D Viewer Beta and has taken over association with the .fbx file extension.</span></span> <span data-ttu-id="83c9a-241">Wenn der 3D-Viewer (Beta) der Dateierweiterung FBX zugeordnet werden soll, deinstallieren und installieren Sie ihn neu.</span><span class="sxs-lookup"><span data-stu-id="83c9a-241">If you prefer 3D Viewer Beta to be associated with the .fbx file extension, uninstall and reinstall 3D Viewer Beta.</span></span>

### <span data-ttu-id="83c9a-242">Die Schaltfläche „Datei öffnen“ im 3D-Viewer (Beta) öffnet keine App.</span><span class="sxs-lookup"><span data-stu-id="83c9a-242">The Open File button in 3D Viewer Beta doesn't launch an app</span></span>

<span data-ttu-id="83c9a-243">Die Schaltfläche **Datei öffnen** öffnet die App, die mit der Dateiauswahl-Funktion in HoloLens verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="83c9a-243">The **Open File** button will open the app associated with the file picker function on HoloLens.</span></span> <span data-ttu-id="83c9a-244">Wenn OneDrive installiert ist, sollte die Schaltfläche **Datei öffnen** OneDrive starten.</span><span class="sxs-lookup"><span data-stu-id="83c9a-244">If OneDrive is installed, the **Open File** button should launch OneDrive.</span></span> <span data-ttu-id="83c9a-245">Wenn derzeit keine App mit der Dateiauswahl-Funktion verknüpft ist, die auf HoloLens installiert ist, werden Sie zum Microsoft Store weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="83c9a-245">However, if there is currently no app associated with the file picker function installed on HoloLens, you will be directed to Microsoft Store.</span></span>

<span data-ttu-id="83c9a-246">Wenn die Schaltfläche **Datei öffnen** eine andere App als OneDrive startet, wurde diese App wahrscheinlich nach OneDrive installiert und hat die Zuordnung zur Dateiauswahl-Funktion übernommen.</span><span class="sxs-lookup"><span data-stu-id="83c9a-246">If the **Open File** button launches an app other than OneDrive, that app was likely installed after OneDrive and has taken over association with the file picker function.</span></span> <span data-ttu-id="83c9a-247">Wenn OneDrive starten soll, wenn Sie die Schaltfläche **Datei öffnen** im 3D-Viewer (Beta) auswählen, deinstallieren Sie OneDrive, und installieren Sie es neu.</span><span class="sxs-lookup"><span data-stu-id="83c9a-247">If you prefer OneDrive to launch when selecting the **Open File** button in 3D Viewer Beta, uninstall and reinstall OneDrive.</span></span>

<span data-ttu-id="83c9a-248">Wenn die Schaltfläche **Datei öffnen** nicht aktiv ist, haben Sie möglicherweise die maximale Anzahl von Modellen erreicht, die gleichzeitig im 3D-Viewer (Beta) geöffnet sein kann.</span><span class="sxs-lookup"><span data-stu-id="83c9a-248">If the **Open File** button is not active, it's possible that you have reached the limit of models that can be open in 3D Viewer Beta at one time.</span></span> <span data-ttu-id="83c9a-249">Wenn im 3D-Viewer (Beta) 40 Modelle geöffnet sind, müssen Sie einige schließen, bevor Sie weitere öffnen können.</span><span class="sxs-lookup"><span data-stu-id="83c9a-249">If you have 40 models open in 3D Viewer Beta, you will need to close some before you will be able to open additional models.</span></span>

## <span data-ttu-id="83c9a-250">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="83c9a-250">Additional resources</span></span>

- <span data-ttu-id="83c9a-251">[Support-Foren](http://forums.hololens.com/categories/3d-viewer-beta) – nur für Archivierungszwecke.</span><span class="sxs-lookup"><span data-stu-id="83c9a-251">[Support forums](http://forums.hololens.com/categories/3d-viewer-beta) - For archival purposes only.</span></span> <span data-ttu-id="83c9a-252">Dieses Forum ist nicht mehr aktiv.</span><span class="sxs-lookup"><span data-stu-id="83c9a-252">This forum is no longer active.</span></span>
- [<span data-ttu-id="83c9a-253">Hinweise von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="83c9a-253">Third-party notices</span></span>](https://www.microsoft.com/{lang-locale}/legal/products)
