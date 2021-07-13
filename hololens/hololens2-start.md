---
title: Einrichten von HoloLens 2
description: Erfahren Sie, wie Sie Ihre HoloLens 2 zum ersten Mal über ein WLAN-Netzwerk mit einem Microsoft (MSA)- oder Active Directory Domain Services-Konto einrichten.
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 0d087037e94bcaed2cd79d9cff77ed3039919a09
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923781"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="7b506-104">Einrichten von HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="7b506-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="7b506-105">Wenn Sie Ihre HoloLens zum ersten Mal einschalten, werden Sie durch die Einrichtung Ihres Geräts geführt, welches die Anmeldung mit einem Benutzerkonto und die Kalibrierung der HoloLens für Ihre Augen beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="7b506-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="7b506-106">In diesem Abschnitt werden die ersten Schritte zur Einrichtung der HoloLens 2 erläutert.</span><span class="sxs-lookup"><span data-stu-id="7b506-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="7b506-107">Im nächsten Abschnitt erfahren Sie, wie Sie mit der HoloLens arbeiten und mit Hologrammen interagieren können.</span><span class="sxs-lookup"><span data-stu-id="7b506-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="7b506-108">Um zu diesem Artikel zu gelangen, lesen Sie bitte: [Einstieg in HoloLens 2](hololens2-basic-usage.md).</span><span class="sxs-lookup"><span data-stu-id="7b506-108">To skip ahead to that article, see [Getting around HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="7b506-109">Vor der Installation</span><span class="sxs-lookup"><span data-stu-id="7b506-109">Before you start</span></span>

<span data-ttu-id="7b506-110">Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes zur Verfügung haben:</span><span class="sxs-lookup"><span data-stu-id="7b506-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="7b506-111">**Eine Netzwerkverbindung**.</span><span class="sxs-lookup"><span data-stu-id="7b506-111">**A network connection**.</span></span> <span data-ttu-id="7b506-112">Sie müssen Ihre HoloLens mit einem Netzwerk verbinden, um sie einzurichten.</span><span class="sxs-lookup"><span data-stu-id="7b506-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="7b506-113">Mit HoloLens 2 können Sie eine Verbindung über WLAN oder über Ethernet herstellen (dazu benötigen Sie einen USB-C-zu-Ethernet-Adapter).</span><span class="sxs-lookup"><span data-stu-id="7b506-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="7b506-114">Wenn Sie das erste Mal eine Verbindung herstellen, benötigen Sie ein offenes oder kennwortgeschütztes Netzwerk, das für die Verbindungsherstellung keine Navigation zu einer Website und keine Verwendung von Zertifikaten erfordert.</span><span class="sxs-lookup"><span data-stu-id="7b506-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="7b506-115">[Erfahren Sie mehr über die von der HoloLens verwendeten Websites](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="7b506-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="7b506-116">**Ein Microsoft-Konto**.</span><span class="sxs-lookup"><span data-stu-id="7b506-116">**A Microsoft account**.</span></span> <span data-ttu-id="7b506-117">Sie müssen sich außerdem bei HoloLens mit einem Microsoft-Konto anmelden (oder mit Ihrem Geschäftskonto, wenn Ihr Unternehmen das Gerät besitzt).</span><span class="sxs-lookup"><span data-stu-id="7b506-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="7b506-118">Wenn Sie nicht über eine Microsoft-Konto verfügen, wechseln Sie zu [account.microsoft.com](https://account.microsoft.com) und richten sie ein kostenloses Konto ein.</span><span class="sxs-lookup"><span data-stu-id="7b506-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="7b506-119">**Ein sicherer, gut beleuchteter Raum ohne Stolperfallen**.</span><span class="sxs-lookup"><span data-stu-id="7b506-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="7b506-120">[Gesundheits- und Sicherheitsinformationen](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span><span class="sxs-lookup"><span data-stu-id="7b506-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="7b506-121">**Das optionale Komfortzubehör**, das in der HoloLens-Lieferung enthalten ist, ermöglicht Ihnen die komfortabelste Passform.</span><span class="sxs-lookup"><span data-stu-id="7b506-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="7b506-122">[Weitere Informationen zu Passform und Komfort](hololens2-setup.md#adjust-fit).</span><span class="sxs-lookup"><span data-stu-id="7b506-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="7b506-123">Einrichten von Windows</span><span class="sxs-lookup"><span data-stu-id="7b506-123">Set up Windows</span></span>

<span data-ttu-id="7b506-124">Wenn Sie Ihre HoloLens 2 zum ersten Mal starten, müssen Sie zunächst Windows Holographic einrichten.</span><span class="sxs-lookup"><span data-stu-id="7b506-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="7b506-125">Beim Starten Ihrer HoloLens hören Sie Musik und sehen ein Windows-Logo.</span><span class="sxs-lookup"><span data-stu-id="7b506-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![Erster Bildschirm während des ersten Starts](images/01-magic-moment.png)

<span data-ttu-id="7b506-127">HoloLens 2 führt Sie durch die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="7b506-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="7b506-128">Wählen Sie Ihre Sprache aus.</span><span class="sxs-lookup"><span data-stu-id="7b506-128">Select your language.</span></span>

    ![Sprache auswählen](images/04-language.png)

1. <span data-ttu-id="7b506-130">Wählen Sie Ihre Region aus.</span><span class="sxs-lookup"><span data-stu-id="7b506-130">Select your region.</span></span>

    ![Region auswählen](images/05-region.png)

1. <span data-ttu-id="7b506-132">Kalibrieren Sie HoloLens auf Ihre Augen.</span><span class="sxs-lookup"><span data-stu-id="7b506-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="7b506-133">Wenn Sie die Kalibrierung überspringen möchten, werden Sie bei Ihrer nächsten Anmeldung dazu aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7b506-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span> 

    1. <span data-ttu-id="7b506-134">Passen Sie zuerst Ihr Visier an.</span><span class="sxs-lookup"><span data-stu-id="7b506-134">First, you'll adjust your visor.</span></span>
    
        ![Der Bildschirm „Kalibrierungsauswahl“](images/06-et-corners.png)

    2. <span data-ttu-id="7b506-136">Zum Kalibrieren betrachten Sie eine Reihe von Zielen (als Edelsteine bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="7b506-136">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="7b506-137">Es ist in Ordnung, wenn Sie während der Kalibrierung blinzeln oder die Augen schließen. Versuchen Sie jedoch, nicht auf andere Gegenstände im Raum oder auf physischen Raum zu starren.</span><span class="sxs-lookup"><span data-stu-id="7b506-137">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="7b506-138">HoloLens verwendet diesen Vorgang, um Ihre Augenposition zu ermitteln, um so Ihre holografische Welt besser darstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="7b506-138">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> 

        ![Einstellung für Ihre Augen](images/07-adjust-eyes.png)

        <span data-ttu-id="7b506-140">Nach der Kalibrierung werden Hologramme korrekt angezeigt, auch wenn sich das Visier auf Ihrem Kopf verschiebt.</span><span class="sxs-lookup"><span data-stu-id="7b506-140">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span> <span data-ttu-id="7b506-141">Kalibrierinformationen werden lokal auf dem Gerät gespeichert und sind nicht mit Kontoinformationen verknüpft.</span><span class="sxs-lookup"><span data-stu-id="7b506-141">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="7b506-142">Weitere Informationen finden Sie unter [Kalibrierungsdaten und Sicherheit](hololens-calibration.md#calibration-data-and-security).</span><span class="sxs-lookup"><span data-stu-id="7b506-142">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

        ![Die Kalibrierung ist abgeschlossen](images/calibration-complete.png)

1. <span data-ttu-id="7b506-144">Stellen Sie eine Verbindung mit dem Internet her (wählen Sie WLAN oder Ihre Ethernet-Verbindung).</span><span class="sxs-lookup"><span data-stu-id="7b506-144">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="7b506-145">HoloLens legt Ihre Zeitzone basierend auf den Informationen, die aus dem WLAN-Netzwerk abgerufen werden, automatisch fest.</span><span class="sxs-lookup"><span data-stu-id="7b506-145">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="7b506-146">Nachdem das Setup abgeschlossen ist, können Sie die Zeitzone mithilfe der Einstellungen-App ändern.</span><span class="sxs-lookup"><span data-stu-id="7b506-146">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Herstellen einer WLAN-Verbindung](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="7b506-148">Wenn Sie über den WLAN-Schritt hinausgehen und später zu einem anderen Netzwerk wechseln müssen, während Sie sich noch in der Einrichtung befinden, können Sie die Tasten **Lautstärke senken** und **Ein/Aus** gleichzeitig drücken, um zu diesem Schritt zurückzukehren. Das ist möglich, wenn Sie eine Betriebssystemversion von Oktober 2019 oder später verwenden.</span><span class="sxs-lookup"><span data-stu-id="7b506-148">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="7b506-149">Bei früheren Versionen ist es möglicherweise erforderlich, dass Sie das [Gerät zurücksetzen](hololens-recovery.md) oder an einem Ort, an dem das WLAN-Netzwerk nicht verfügbar ist, neu starten, um zu verhindern, dass es sich automatisch verbindet.</span><span class="sxs-lookup"><span data-stu-id="7b506-149">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="7b506-150">Beachten Sie außerdem, dass beim HoloLens-Setup für Anmeldeinformationen eine zeitliche Obergrenze von zwei Minuten besteht.</span><span class="sxs-lookup"><span data-stu-id="7b506-150">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="7b506-151">Der Benutzername/das Kennwort muss innerhalb von zwei Minuten eingegeben werden, andernfalls wird der Wert im Feld „Benutzername“ automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7b506-151">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="7b506-152">HoloLens 2 wird nach einem Autopilot-Profil suchen und es anwenden, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="7b506-152">HoloLens 2 will search and apply an Autopilot profile if one exists.</span></span> <span data-ttu-id="7b506-153">Auf diesem Bildschirm ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7b506-153">No action is needed on this screen.</span></span>
 
    ![Autopilot-Profilsuche](images/autopilot-profile-search.png) 

1. <span data-ttu-id="7b506-155">Klicken Sie auf dem Bildschirm „Lizenzierung“ **Akzeptieren** an.</span><span class="sxs-lookup"><span data-stu-id="7b506-155">Click **Accept** on the licensing screen.</span></span>

    ![Windows-Lizenzvereinbarung](images/windows-license-agreement.png)

1. <span data-ttu-id="7b506-157">Melden Sie sich bei Ihrem Benutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="7b506-157">Sign in to your user account.</span></span> <span data-ttu-id="7b506-158">Sie wählen zwischen **Die Lizenz gehört meinem Arbeitgeber oder meiner Bildungseinrichtung** und **Die Lizenz gehört mir**.</span><span class="sxs-lookup"><span data-stu-id="7b506-158">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    - <span data-ttu-id="7b506-159">Wenn Sie **Meinem Arbeitgeber oder meiner Bildungseinrichtung** gewählt haben, melden Sie sich mit dem Azure AD-Konto an.</span><span class="sxs-lookup"><span data-stu-id="7b506-159">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="7b506-160">Wenn Ihr Unternehmen Azure AD Premium verwendet und die automatische MDM-Registrierung konfiguriert hat, wird HoloLens automatisch in MDM registriert.</span><span class="sxs-lookup"><span data-stu-id="7b506-160">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="7b506-161">Wenn in Ihrer Organisation kein Azure AD Premium verwendet wird, ist die automatische MDM-Registrierung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7b506-161">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="7b506-162">In diesem Fall müssen Sie [HoloLens manuell in der Geräteverwaltung registrieren](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="7b506-162">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="7b506-163">Geben Sie Ihre Unternehmenskontodaten ein.</span><span class="sxs-lookup"><span data-stu-id="7b506-163">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="7b506-164">Akzeptieren Sie die Datenschutzerklärung und den Endnutzer-Lizenzvereinbarung.</span><span class="sxs-lookup"><span data-stu-id="7b506-164">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="7b506-165">Melden Sie sich mit Ihren Azure AD-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="7b506-165">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="7b506-166">Hier werden Sie möglicherweise auf die Anmeldeseite Ihres Unternehmens umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="7b506-166">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="7b506-167">Setzen Sie die Einrichtung des Geräts fort.</span><span class="sxs-lookup"><span data-stu-id="7b506-167">Continue setting up the device.</span></span>

    - <span data-ttu-id="7b506-168">Wenn Sie **Mir** ausgewählt haben, melden Sie sich mit einem Microsoft-Konto an.</span><span class="sxs-lookup"><span data-stu-id="7b506-168">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="7b506-169">Sobald die Installation abgeschlossen ist, können Sie [HoloLens über die Geräteverwaltung manuell registrieren](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="7b506-169">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="7b506-170">Geben Sie Ihre Microsoft-Kontoinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="7b506-170">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="7b506-171">Geben Sie das Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="7b506-171">Enter your password.</span></span> <span data-ttu-id="7b506-172">Wenn für Ihr Microsoft-Konto [eine Überprüfung in zwei Schritten (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) erforderlich ist, schließen Sie den entsprechenden Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="7b506-172">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![Benutzer festlegen](images/13-device-owner.png)

1. <span data-ttu-id="7b506-174">Anmeldung per Iriserkennung einrichten indem Sie **Weiter** auswählen.</span><span class="sxs-lookup"><span data-stu-id="7b506-174">Setup Iris sign-in by selecting **Next**.</span></span> <span data-ttu-id="7b506-175">Sie werden eine ähnliche Vorgehensweise wie bei der Augenkalibrierung anwenden.</span><span class="sxs-lookup"><span data-stu-id="7b506-175">You will go through a similar experience to the eye calibration.</span></span> <span data-ttu-id="7b506-176">Wählen Sie **Fertig** aus, wenn der Scan abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="7b506-176">Select **Done** when the scan is complete.</span></span> <span data-ttu-id="7b506-177">Sie können auch **Überspringen** auswählen, um diesen Schritt zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="7b506-177">You may also select **Skip** to bypass this step.</span></span>
    
    <span data-ttu-id="7b506-178">![Iriserkennung einrichten](images/setup-iris.png) ![Iriserkennung ist abgeschlossen](images/iris-setup-complete.png)</span><span class="sxs-lookup"><span data-stu-id="7b506-178">![Iris setup](images/setup-iris.png) ![Iris setup completion](images/iris-setup-complete.png)</span></span> 
     
  
1. <span data-ttu-id="7b506-179">Einrichten einer PIN zur Anmeldung am Gerät.</span><span class="sxs-lookup"><span data-stu-id="7b506-179">You'll setup a PIN to log into the device.</span></span> <span data-ttu-id="7b506-180">Diese PIN ist gerätespezifisch.</span><span class="sxs-lookup"><span data-stu-id="7b506-180">This PIN is device specific.</span></span> 

    ![Einrichten von Windows Hello](images/setup-windows-hello.png)

    ![Einrichten einer Windows Hello PIN](images/windows-hello-pin.png)

    ![Einrichten von Windows Hello war erfolgreich](images/windows-hello-successful.png) 
    
1. <span data-ttu-id="7b506-184">Wählen Sie, ob Sprache auf der HoloLens 2 aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="7b506-184">Select whether to enable speech on HoloLens 2.</span></span>

    ![Aktivieren von Cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="7b506-186">Wählen Sie aus, ob der Standort auf der HoloLens 2 aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="7b506-186">Select whether to enable location on HoloLens 2.</span></span>
    
    ![Aktivieren von Standortdiensten](images/setup-location-services.png)

1. <span data-ttu-id="7b506-188">Wählen Sie Ihre Telemetrie-Stufe aus.</span><span class="sxs-lookup"><span data-stu-id="7b506-188">Select your telemetry level.</span></span> <span data-ttu-id="7b506-189">Aktivieren Sie optionale Telemetrie, wenn dies möglich ist.</span><span class="sxs-lookup"><span data-stu-id="7b506-189">If you can, please enable Optional telemetry.</span></span> <span data-ttu-id="7b506-190">Diese Informationen sind für das HoloLens-Entwicklungsteam wirklich hilfreich.</span><span class="sxs-lookup"><span data-stu-id="7b506-190">This information really helps the HoloLens engineering team.</span></span>

     ![Telemetrie-Stufe](images/24-telemetry.png)

1. <span data-ttu-id="7b506-192">Erfahren Sie, wie Sie die Startgeste auf HoloLens 2 verwenden.</span><span class="sxs-lookup"><span data-stu-id="7b506-192">Learn how to use the start gesture on HoloLens 2.</span></span>

     ![Erfahren Sie, wie Sie die Startgeste verwenden, Abbildung 1](images/26-01-startmenu-learning.png)

     ![Erfahren Sie, wie Sie die Startgeste verwenden, Abbildung 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="7b506-195">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="7b506-195">Congratulations!</span></span>  <span data-ttu-id="7b506-196">Die Einrichtung ist abgeschlossen, und Sie können HoloLens verwenden!</span><span class="sxs-lookup"><span data-stu-id="7b506-196">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="7b506-197">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7b506-197">Next steps</span></span>

1. <span data-ttu-id="7b506-198">Beginnen Sie sofort, mit Mixed Reality zu interagieren und der Navigation in Windows 10 auf Ihrer HoloLens – in der **Tipps**-App finden Sie praktische Tutorials für Handinteraktionen.</span><span class="sxs-lookup"><span data-stu-id="7b506-198">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="7b506-199">Verwenden Sie die Startgeste, um zum Start zu gelangen oder sagen Sie „Zum Startmenü gehen“, und wählen Sie Tipps aus.</span><span class="sxs-lookup"><span data-stu-id="7b506-199">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="7b506-200">Klicken Sie unten, um mehr über den Umgang mit HoloLens 2 zu lesen.</span><span class="sxs-lookup"><span data-stu-id="7b506-200">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7b506-201">Immer auf dem richtigen Weg in HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="7b506-201">Getting around HoloLens 2</span></span>](hololens2-basic-usage.md)
