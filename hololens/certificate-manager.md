---
title: Zertifikat-Manager
description: Erfahren Sie, wie Sie Zertifikate auf Mixed -Reality-Geräten von HoloLens 2 manuell installieren, verwalten und entfernen.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 9d221321adcb8062206695e3e610d35dee14523e
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283686"
---
# <span data-ttu-id="7d411-103">Zertifikat-Manager</span><span class="sxs-lookup"><span data-stu-id="7d411-103">Certificate Manager</span></span>

- <span data-ttu-id="7d411-104">Verbesserte Überwachungs-, Diagnose- und Validierungstools für Gerätesicherheit und -kompatibilität durch den neuen Zertifikat-Manager.</span><span class="sxs-lookup"><span data-stu-id="7d411-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="7d411-105">Mit dieser Funktion können Sie Ihre Zertifikate in kommerziellen Umgebungen bereitstellen, Eine Problembehandlung und Validierung ihrer Zertifikate im großen Maßstab ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="7d411-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="7d411-106">In Windows Holographic, Version 20H2, fügen wir einen Zertifikat-Manager in der HoloLens 2-Einstellungs-App hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d411-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="7d411-107">Wechseln Sie **zu "Einstellungen > update & Security > Certificates".**</span><span class="sxs-lookup"><span data-stu-id="7d411-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="7d411-108">Dieses Feature bietet eine einfache und benutzerfreundliche Möglichkeit zum Anzeigen, Installieren und Entfernen von Zertifikaten auf Ihrem Gerät.</span><span class="sxs-lookup"><span data-stu-id="7d411-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="7d411-109">Mit dem neuen Zertifikat-Manager verfügen Administratoren und Benutzer jetzt über verbesserte Überwachungs-, Diagnose- und Validierungstools, um sicherzustellen, dass Geräte sicher und kompatibel bleiben.</span><span class="sxs-lookup"><span data-stu-id="7d411-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="7d411-110">**Überwachung:** Möglichkeit, zu überprüfen, ob ein Zertifikat ordnungsgemäß bereitgestellt wurde, oder um zu bestätigen, dass es ordnungsgemäß entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="7d411-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="7d411-111">**Diagnose:** Wenn Probleme auftreten, spart die Validierung, dass die entsprechenden Zertifikate auf dem Gerät vorhanden sind, Zeit und hilft bei der Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="7d411-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="7d411-112">**Überprüfung:** Die Überprüfung, ob ein Zertifikat dem beabsichtigten Zweck dient und funktionsfähig ist, kann erhebliche Zeit sparen, insbesondere in kommerziellen Umgebungen, bevor Zertifikate in größerem Umfang bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7d411-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="7d411-113">Um ein bestimmtes Zertifikat schnell in der Liste zu finden, gibt es Optionen zum Sortieren nach Name, Speicher oder Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="7d411-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="7d411-114">Benutzer können auch direkt nach einem Zertifikat suchen.</span><span class="sxs-lookup"><span data-stu-id="7d411-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="7d411-115">Um einzelne Zertifikateigenschaften anzeigen zu können, wählen Sie das Zertifikat aus, und klicken Sie auf **"Info".**</span><span class="sxs-lookup"><span data-stu-id="7d411-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="7d411-116">Die Zertifikatinstallation unterstützt derzeit CER- und CRT-Dateien.</span><span class="sxs-lookup"><span data-stu-id="7d411-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="7d411-117">Gerätebesitzer können Zertifikate auf dem lokalen Computer und dem aktuellen Benutzer installieren.  Alle anderen Benutzer können nur im aktuellen Benutzer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="7d411-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="7d411-118">Benutzer können nur Direkt installierte Zertifikate aus der Einstellungsbenutzeroberfläche entfernen.</span><span class="sxs-lookup"><span data-stu-id="7d411-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="7d411-119">Wenn ein Zertifikat auf andere Weise installiert wurde, muss es auch mit demselben Mechanismus entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="7d411-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <span data-ttu-id="7d411-120">So installieren Sie ein Zertifikat:</span><span class="sxs-lookup"><span data-stu-id="7d411-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="7d411-121">Verbinden Sie Ihre HoloLens 2 mit einem PC.</span><span class="sxs-lookup"><span data-stu-id="7d411-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="7d411-122">Platzieren Sie die zertifikatsdatei, die Sie installieren möchten, an einem Speicherort auf Ihrer HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="7d411-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="7d411-123">Navigieren Sie **zu "Settings App > Update & Security > Certificates",** und wählen Sie "Zertifikat installieren" aus.</span><span class="sxs-lookup"><span data-stu-id="7d411-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="7d411-124">Klicken **Sie auf "Datei importieren",** und navigieren Sie zu dem Speicherort, an dem Sie das Zertifikat gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="7d411-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="7d411-125">Wählen Sie **"Speicherort" aus.**</span><span class="sxs-lookup"><span data-stu-id="7d411-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="7d411-126">Wählen Sie **Zertifikatspeicher aus.**</span><span class="sxs-lookup"><span data-stu-id="7d411-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="7d411-127">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="7d411-127">Click **Install**.</span></span>

<span data-ttu-id="7d411-128">Das Zertifikat sollte nun auf dem Gerät installiert werden.</span><span class="sxs-lookup"><span data-stu-id="7d411-128">The certificate should now be installed on the device.</span></span>

## <span data-ttu-id="7d411-129">So entfernen Sie ein Zertifikat:</span><span class="sxs-lookup"><span data-stu-id="7d411-129">To remove a certificate:</span></span> 
1. <span data-ttu-id="7d411-130">Navigieren Sie zu **"Settings App > Update and Security > Certificates".**</span><span class="sxs-lookup"><span data-stu-id="7d411-130">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="7d411-131">Suchen Sie im Suchfeld nach dem Namen des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="7d411-131">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="7d411-132">Wählen Sie das Zertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="7d411-132">Select the certificate.</span></span>
1. <span data-ttu-id="7d411-133">Klicken Sie auf **"Entfernen".**</span><span class="sxs-lookup"><span data-stu-id="7d411-133">Click **Remove**</span></span>
1. <span data-ttu-id="7d411-134">Wählen **Sie "Ja"** aus, wenn Sie zur Bestätigung aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="7d411-134">Select **Yes** when prompted for confirmation.</span></span>


![Zertifikatanzeige in der App "Einstellungen" unter "Ceritifcates"](images/certificate-viewer-device.jpg)

![Abbildung der Verwendung der Zertifikatbenutzeroberfläche zum Installieren eines Zertifikats in den Einstellungen.](images/certificate-device-install.jpg)
