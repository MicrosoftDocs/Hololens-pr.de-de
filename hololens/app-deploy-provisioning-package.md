---
title: Bereitstellungspaket
description: APP, App Deployment, Enterprise App demployment, Bereitstellung
keywords: APP, App Deployment, Enterprise App demployment, Bereitstellung
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 60efc454f9e1221372279401da9f8ee918e061e7
ms.sourcegitcommit: efa3fb7e353c5e56ee467cc7fd94ffdfaf46e2e5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "11219222"
---
# Bereitstellungspaket

Bereitstellungspakete können zum Vorbereiten und Konfigurieren von Geräten in einer Umgebung ohne Zugriff auf die Endpunkt Verwaltung verwendet werden. Sie können auch unabhängig von der Identität des Benutzers, dem Registrierungsstatus, während der Out-of-Box-Umgebung (OOBE) oder durch [Anwenden eines Bereitstellungspakets während des Setups](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)auf einem Gerät bereitgestellt werden.

## Überlegungen zu Bereitstellungspaketen:
* Nicht öffentliche apps
* Nur USB-Seite laden
* Keine automatische Aktualisierung (erfordert manuelle Updates über PPKGs)

Apps, die über ein Bereitstellungspaket installiert wurden, müssen mit einem Zertifikat im lokalen Computerspeicher signiert sein. Bereitstellungspakete können nur Zertifikate auf dem Gerätespeicher (lokaler Computer) installieren, daher können die APP und das Zertifikat über dasselbe Bereitstellungspaket installiert werden. Wenn Sie Ihr Zertifikat von MDM bereitstellen oder über den [Zertifikat-Manager](certificate-manager.md)installieren, stellen Sie sicher, dass Sie das Zertifikat im lokalen Computerspeicher bereitstellen, um auf diese Weise installierte apps zu signieren.

Informationen zu den Grundlagen zum Erstellen eines Bereitstellungspakets für HoloLens-Geräte finden Sie unter [HoloLens-Bereitstellung](https://docs.microsoft.com/hololens/hololens-provisioning). Um eine APP bereitzustellen, müssen Sie mit der erweiterten Bereitstellung beginnen.

> [!NOTE]
> HoloLens (1st Generation) hat begrenzte Unterstützung bei der Installation von apps (**UniversalAppInstall**) mithilfe eines Bereitstellungspakets. HoloLens (1st Gen)-Geräte unterstützen nur die Installation einer APP über PPKG nur während der OOBE und nur bei Installationen des Benutzerkontexts.

## Setup

Führen Sie im [Windows-Konfigurations-Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) die folgenden vier Schritte aus.

1. Setzen Sie ApplicationManagement/AllowAllTrustedApps auf "Ja". Siehe: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Geben Sie unter **UniversalAppInstall**  >  **UserContextAppLicense** die **PackageFamilyName**ein. Siehe [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall). Siehe auch: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Sie können Device Portal auf einem Gerät verwenden, auf dem Sie Ihre APP bereits installiert haben. Besuchen Sie die Seite "Apps", und schauen Sie sich die PackageRelativeID-Zeile, alle Informationen vor dem "!" an. Ist Ihre **PackageFamilyName**.
    
3. Sie sehen dann, dass Sie einen neuen Abschnitt, " **applicationdatei**" haben. In diesem Bereich können Sie Ihr AppX-Bundle hochladen.

4. Je nachdem, ob Sie Ihre APP gekauft oder eine eigene Branchen-App erstellt haben, müssen Sie die Lizenzdatei oder das Sicherheitszertifikat hochladen.

    - Für Lizenzdatei: unter **UniversalAppInstall**  >  **UserContextAppLience** , und navigieren Sie zum Speicherort Ihrer Lizenz, und laden Sie Sie hoch. 
    - Klicken Sie für Sicherheitsdatei auf **Zertifikate** , und wählen Sie das Zertifikat aus, das Sie neben Ihrem AppX-Paket installieren möchten.

Stellen Sie sicher, dass Sie Ihr Projekt an einem sicheren Ort speichern. **Exportieren** Sie Sie dann als **Bereitstellungspaket**.  
    
Siehe auch: [Anwenden Ihres Provisiong-Pakets auf HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
