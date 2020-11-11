---
title: Zertifikat-Manager
description: Erfahren Sie mehr über das manuelle Verwalten von Zertifikaten auf HoloLens 2.
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
ms.openlocfilehash: 04d7e8cb78357b5398c58e0a0c55e6e530fa363a
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163220"
---
# <span data-ttu-id="8cbad-103">Zertifikat-Manager</span><span class="sxs-lookup"><span data-stu-id="8cbad-103">Certificate Manager</span></span>

- <span data-ttu-id="8cbad-104">Verbesserte Überwachungs-, Diagnose-und Validierungstools für Gerätesicherheit und-Compliance durch den neuen Zertifikat-Manager.</span><span class="sxs-lookup"><span data-stu-id="8cbad-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="8cbad-105">Mit dieser Funktion können Sie Ihre Zertifikate in kommerzieller Umgebung bereitstellen, beheben und überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8cbad-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="8cbad-106">In Windows holographisch, Version 20H2, fügen wir einen Zertifikat-Manager in die HoloLens 2-Einstellungs-APP ein.</span><span class="sxs-lookup"><span data-stu-id="8cbad-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="8cbad-107">Wechseln Sie zu **Einstellungen > Update & Security >-Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="8cbad-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="8cbad-108">Dieses Feature bietet eine einfache und benutzerfreundliche Möglichkeit, Zertifikate auf Ihrem Gerät anzuzeigen, zu installieren und zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="8cbad-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="8cbad-109">Mit dem neuen Zertifikat-Manager verfügen Administratoren und Benutzer nun über verbesserte Überwachungs-, Diagnose-und Validierungstools, um sicherzustellen, dass die Geräte sicher und kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="8cbad-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="8cbad-110">**Überwachung:** Fähigkeit, zu überprüfen, ob ein Zertifikat richtig bereitgestellt wurde, oder zu bestätigen, dass es ordnungsgemäß entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="8cbad-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="8cbad-111">**Diagnose:** Wenn Probleme auftreten, können Sie überprüfen, ob die entsprechenden Zertifikate auf dem Gerät vorhanden sind, Zeit sparen und bei der Problembehandlung helfen.</span><span class="sxs-lookup"><span data-stu-id="8cbad-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="8cbad-112">**Validierung:** Wenn Sie überprüfen, ob ein Zertifikat den beabsichtigten Zweck erfüllt und funktionell ist, können Sie vor allem in kommerziellen Umgebungen beträchtliche Zeit sparen, bevor Sie Zertifikate im größeren Maßstab bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8cbad-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="8cbad-113">Um schnell ein bestimmtes Zertifikat in der Liste zu finden, gibt es Optionen zum Sortieren nach Name, Store oder Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="8cbad-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="8cbad-114">Benutzer können auch direkt nach einem Zertifikat suchen.</span><span class="sxs-lookup"><span data-stu-id="8cbad-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="8cbad-115">Wenn Sie einzelne Zertifikateigenschaften anzeigen möchten, wählen Sie das Zertifikat aus, und klicken Sie auf **Info**.</span><span class="sxs-lookup"><span data-stu-id="8cbad-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="8cbad-116">Die Zertifikatinstallation unterstützt derzeit CER-und CRT-Dateien.</span><span class="sxs-lookup"><span data-stu-id="8cbad-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="8cbad-117">Gerätebesitzer können Zertifikate auf dem lokalen Computer und dem aktuellen Benutzer installieren.  alle anderen Benutzer können nur in den aktuellen Benutzer installieren.</span><span class="sxs-lookup"><span data-stu-id="8cbad-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="8cbad-118">Benutzer können nur Zertifikate entfernen, die direkt von der UI für Einstellungen installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="8cbad-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="8cbad-119">Wenn ein Zertifikat auf andere Weise installiert wurde, muss es auch vom gleichen Mechanismus entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="8cbad-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <span data-ttu-id="8cbad-120">So installieren Sie ein Zertifikat:</span><span class="sxs-lookup"><span data-stu-id="8cbad-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="8cbad-121">Verbinden Sie Ihr HoloLens 2 mit einem PC.</span><span class="sxs-lookup"><span data-stu-id="8cbad-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="8cbad-122">Legen Sie die Zertifikatdatei, die Sie installieren möchten, an einem Speicherort auf Ihrem HoloLens 2 ab.</span><span class="sxs-lookup"><span data-stu-id="8cbad-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="8cbad-123">Navigieren Sie zu **Einstellungen-app > aktualisieren Sie & Security >-Zertifikate**, und wählen Sie Zertifikat installieren aus.</span><span class="sxs-lookup"><span data-stu-id="8cbad-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="8cbad-124">Klicken Sie auf **Datei importieren** , und navigieren Sie zu dem Speicherort, an dem Sie das Zertifikat gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="8cbad-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="8cbad-125">Wählen Sie **Store Location**aus.</span><span class="sxs-lookup"><span data-stu-id="8cbad-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="8cbad-126">Wählen Sie **Zertifikatspeicher**aus.</span><span class="sxs-lookup"><span data-stu-id="8cbad-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="8cbad-127">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="8cbad-127">Click **Install**.</span></span>

<span data-ttu-id="8cbad-128">Das Zertifikat sollte nun auf dem Gerät installiert sein.</span><span class="sxs-lookup"><span data-stu-id="8cbad-128">The certificate should now be installed on the device.</span></span>

## <span data-ttu-id="8cbad-129">So entfernen Sie ein Zertifikat:</span><span class="sxs-lookup"><span data-stu-id="8cbad-129">To remove a certificate:</span></span> 
1. <span data-ttu-id="8cbad-130">Navigieren Sie zu **Einstellungen-app > Update-und Sicherheits > Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="8cbad-130">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="8cbad-131">Suchen Sie im Suchfeld nach dem Namen des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="8cbad-131">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="8cbad-132">Wählen Sie das Zertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="8cbad-132">Select the certificate.</span></span>
1. <span data-ttu-id="8cbad-133">Klicken Sie auf **Entfernen** .</span><span class="sxs-lookup"><span data-stu-id="8cbad-133">Click **Remove**</span></span>
1. <span data-ttu-id="8cbad-134">Wählen Sie **Ja** aus, wenn Sie zur Bestätigung aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="8cbad-134">Select **Yes** when prompted for confirmation.</span></span>


![Zertifikatanzeige in der Einstellungs-APP unter Ceritifcates](images/certificate-viewer-device.jpg)

![Abbildung, die zeigt, wie Sie mithilfe der Zertifikat-UI ein Zertifikat in Einstellungen installieren.](images/certificate-device-install.jpg)
