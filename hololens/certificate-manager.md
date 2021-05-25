---
title: Zertifikat-Manager
description: Erfahren Sie, wie Sie Zertifikate manuell auf Mixed Reality-Geräten HoloLens 2, verwalten und entfernen.
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
ms.openlocfilehash: f9dcf98cbd200ac54cd786648fdfe286bff1aa00
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397451"
---
# <a name="certificate-manager"></a><span data-ttu-id="51365-103">Zertifikat-Manager</span><span class="sxs-lookup"><span data-stu-id="51365-103">Certificate Manager</span></span>

- <span data-ttu-id="51365-104">Verbesserte Überwachungs-, Diagnose- und Überprüfungstools für Gerätesicherheit und -konformität über den neuen Zertifikat-Manager.</span><span class="sxs-lookup"><span data-stu-id="51365-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="51365-105">Mit dieser Funktion können Sie Ihre Zertifikate in kommerziellen Umgebungen im großen Stil bereitstellen, behandeln und überprüfen.</span><span class="sxs-lookup"><span data-stu-id="51365-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="51365-106">In Windows Holographic, Version 20H2, fügen wir einen Zertifikat-Manager in der HoloLens 2-App hinzu.</span><span class="sxs-lookup"><span data-stu-id="51365-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="51365-107">Wechseln Sie **zu Einstellungen > Update & Security > Certificates**.</span><span class="sxs-lookup"><span data-stu-id="51365-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="51365-108">Dieses Feature bietet eine einfache und benutzerfreundliche Möglichkeit zum Anzeigen, Installieren und Entfernen von Zertifikaten auf Ihrem Gerät.</span><span class="sxs-lookup"><span data-stu-id="51365-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="51365-109">Mit dem neuen Zertifikat-Manager verfügen Administratoren und Benutzer jetzt über verbesserte Überwachungs-, Diagnose- und Validierungstools, um sicherzustellen, dass Geräte sicher und konform bleiben.</span><span class="sxs-lookup"><span data-stu-id="51365-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="51365-110">**Überwachung:** Möglichkeit, zu überprüfen, ob ein Zertifikat ordnungsgemäß bereitgestellt wurde, oder um zu bestätigen, dass es ordnungsgemäß entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="51365-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="51365-111">**Diagnose:** Wenn Probleme auftreten, spart die Validierung, ob die entsprechenden Zertifikate auf dem Gerät vorhanden sind, Zeit und hilft bei der Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="51365-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="51365-112">**Überprüfung:** Die Überprüfung, ob ein Zertifikat den beabsichtigten Zweck erfüllt und funktionsfähig ist, kann insbesondere in kommerziellen Umgebungen viel Zeit sparen, bevor Zertifikate in größerem Umfang bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="51365-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="51365-113">Um ein bestimmtes Zertifikat schnell in der Liste zu finden, gibt es Optionen zum Sortieren nach Name, Speicher oder Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="51365-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="51365-114">Benutzer können auch direkt nach einem Zertifikat suchen.</span><span class="sxs-lookup"><span data-stu-id="51365-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="51365-115">Wählen Sie zum Anzeigen einzelner Zertifikateigenschaften das Zertifikat aus, und klicken Sie auf **Info**.</span><span class="sxs-lookup"><span data-stu-id="51365-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="51365-116">Die Zertifikatinstallation unterstützt derzeit CER- und CRT-Dateien.</span><span class="sxs-lookup"><span data-stu-id="51365-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="51365-117">Gerätebesitzer können Zertifikate auf dem lokalen Computer und dem aktuellen Benutzer installieren.  alle anderen Benutzer können nur unter Aktueller Benutzer installieren.</span><span class="sxs-lookup"><span data-stu-id="51365-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="51365-118">Benutzer können zertifikate, die direkt über die Benutzeroberfläche "Einstellungen" installiert wurden, nur entfernen.</span><span class="sxs-lookup"><span data-stu-id="51365-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="51365-119">Wenn ein Zertifikat auf andere Weise installiert wurde, muss es auch mit demselben Mechanismus entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="51365-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <a name="to-install-a-certificate"></a><span data-ttu-id="51365-120">So installieren Sie ein Zertifikat:</span><span class="sxs-lookup"><span data-stu-id="51365-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="51365-121">Verbinden Sie ihre HoloLens 2 mit einem PC.</span><span class="sxs-lookup"><span data-stu-id="51365-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="51365-122">Platzieren Sie die Zertifikatdatei, die Sie installieren möchten, an einem Speicherort auf Ihrem HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="51365-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="51365-123">Navigieren Sie zu **Einstellungen App > Update & Security > Certificates**, und wählen Sie Zertifikat installieren aus.</span><span class="sxs-lookup"><span data-stu-id="51365-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="51365-124">Klicken Sie auf **Datei importieren,** und navigieren Sie zu dem Speicherort, an dem Sie das Zertifikat gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="51365-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="51365-125">Wählen Sie **Store Location (Speicherort) aus.**</span><span class="sxs-lookup"><span data-stu-id="51365-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="51365-126">Wählen Sie **Zertifikatspeicher** aus.</span><span class="sxs-lookup"><span data-stu-id="51365-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="51365-127">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="51365-127">Click **Install**.</span></span>

<span data-ttu-id="51365-128">Das Zertifikat sollte nun auf dem Gerät installiert sein.</span><span class="sxs-lookup"><span data-stu-id="51365-128">The certificate should now be installed on the device.</span></span>

## <a name="to-remove-a-certificate"></a><span data-ttu-id="51365-129">So entfernen Sie ein Zertifikat:</span><span class="sxs-lookup"><span data-stu-id="51365-129">To remove a certificate:</span></span> 
>[!WARNING]
> <span data-ttu-id="51365-130">Obwohl Sie MDM-bereitgestellte Zertifikate im Zertifikat-Manager anzeigen können, können Sie sie nicht im Zertifikat-Manager deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="51365-130">Although you can view MDM-deployed certificates in Certificate Manager, you cannot uninstall them in Certificate Manager.</span></span> <span data-ttu-id="51365-131">Sie müssen sie über MDM deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="51365-131">You must uninstall them through MDM.</span></span>
1. <span data-ttu-id="51365-132">Navigieren Sie zu **Einstellungen App > Update- und Sicherheitszertifikate >**.</span><span class="sxs-lookup"><span data-stu-id="51365-132">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="51365-133">Suchen Sie im Suchfeld nach dem Zertifikat anhand des Namens.</span><span class="sxs-lookup"><span data-stu-id="51365-133">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="51365-134">Wählen Sie das Zertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="51365-134">Select the certificate.</span></span>
1. <span data-ttu-id="51365-135">Klicken Sie auf **Entfernen.**</span><span class="sxs-lookup"><span data-stu-id="51365-135">Click **Remove**</span></span>
1. <span data-ttu-id="51365-136">Wählen Sie **Ja** aus, wenn Sie zur Bestätigung aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="51365-136">Select **Yes** when prompted for confirmation.</span></span>



![Zertifikatanzeige in der Einstellungs-App unter Zertifikate](images/certificate-viewer-device.jpg)

![Abbildung: Verwenden der Zertifikat-Benutzeroberfläche zum Installieren eines Zertifikats in den Einstellungen](images/certificate-device-install.jpg)
