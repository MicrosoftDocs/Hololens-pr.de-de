---
title: Installieren von apps über das Web Installer
description: Installieren von apps über das Web Installer für das App-Installationsprogramm
keywords: App-Verwaltung, APP, hololens, App-Installationsprogramm, Webinstallation
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 186cbefb2822455dcf922804ea09533b833b8663
ms.sourcegitcommit: a3e53f0e5070d0538f3ed74259914c59413eafd0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135443"
---
# <span data-ttu-id="b1805-104">Installieren von apps von einer Webseite</span><span class="sxs-lookup"><span data-stu-id="b1805-104">Installing apps from a web page</span></span>

<span data-ttu-id="b1805-105">Benutzer können eine APP direkt von einem Webserver installieren.</span><span class="sxs-lookup"><span data-stu-id="b1805-105">Users can install an app directly from a web server.</span></span> <span data-ttu-id="b1805-106">Dadurch wird das App-Installationsprogramm in Kombination mit einer einfachen Download-und Installations Verteilungsmethode verwendet.</span><span class="sxs-lookup"><span data-stu-id="b1805-106">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="b1805-107">Dieses Feature ist derzeit nur avalible in Windows Insider-Builds 19041.1366 +.</span><span class="sxs-lookup"><span data-stu-id="b1805-107">This feature is currently only avalible in Windows Insider builds 19041.1366+.</span></span> <span data-ttu-id="b1805-108">[Weitere Informationen zum Registrieren von Windows Insider-Builds](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="b1805-108">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

## <span data-ttu-id="b1805-109">So richten Sie das ein:</span><span class="sxs-lookup"><span data-stu-id="b1805-109">How to set this up:</span></span>
1.  <span data-ttu-id="b1805-110">Stellen Sie sicher, dass Ihre APP für die Installation richtig konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="b1805-110">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="b1805-111">Führen Sie die folgenden [Schritte aus, um diese auf einer Webseite zu aktivieren](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="b1805-111">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 
1.  <span data-ttu-id="b1805-112">Entscheiden Sie sich für eine Zertifikat Bereitstellungsmethode.</span><span class="sxs-lookup"><span data-stu-id="b1805-112">Pick a certificate deployment method.</span></span> 
    1.  <span data-ttu-id="b1805-113">[Bereitstellungspakete](hololens-provisioning.md) können auf lokale Geräte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="b1805-113">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
    1.  <span data-ttu-id="b1805-114">MDM kann verwendet werden, um [Zertifikate mit Gerätekonfigurationen anzuwenden](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="b1805-114">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
    1.  <span data-ttu-id="b1805-115">Verwenden Sie den [Zertifikat-Manager](hololens-insider.md#certificate-manager)für Geräte.</span><span class="sxs-lookup"><span data-stu-id="b1805-115">Use the on device [Certificate Manager](hololens-insider.md#certificate-manager).</span></span> 

## <span data-ttu-id="b1805-116">Benutzerfreundlichkeit:</span><span class="sxs-lookup"><span data-stu-id="b1805-116">End User Experience:</span></span>
1.  <span data-ttu-id="b1805-117">Der Benutzer empfängt und installiert das Zertifikat auf dem Gerät mithilfe einer zuvor ausgewählten Methode.</span><span class="sxs-lookup"><span data-stu-id="b1805-117">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1.  <span data-ttu-id="b1805-118">Der Benutzer besucht die URL, die aus dem obigen Schritt erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b1805-118">User visits the URL created from the step above.</span></span>

<span data-ttu-id="b1805-119">Die APP wird nun auf dem Gerät installiert.</span><span class="sxs-lookup"><span data-stu-id="b1805-119">The app will now install to the device.</span></span> <span data-ttu-id="b1805-120">Um die APP zu finden, öffnen Sie das **Startmenü** , und wählen Sie die Schaltfläche **alle apps** aus, um Ihre APP zu finden.</span><span class="sxs-lookup"><span data-stu-id="b1805-120">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="b1805-121">Hilfe zur Problembehandlung dieser Installationsmethode finden Sie unter [Problembehandlung von Problemen mit dem App-Installationsprogramm](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span><span class="sxs-lookup"><span data-stu-id="b1805-121">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="b1805-122">Die Benutzeroberfläche wird während des Aktualisierungsvorgangs nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b1805-122">UI during the update process is not supported.</span></span> <span data-ttu-id="b1805-123">Daher werden die ShowPrompt-Option auf [dieser Seite](https://docs.microsoft.com/windows/msix/app-installer/update-settings) und die zugehörigen Optionen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b1805-123">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>
