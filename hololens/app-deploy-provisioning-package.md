---
title: Bereitstellungspaket
description: APP, App-Bereitstellung, Bereitstellung von Enterprise-apps
keywords: APP, App-Bereitstellung, Bereitstellung von Enterprise-apps
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
ms.openlocfilehash: 11bc83be188e1b81959690efcb2bdf26d800aae3
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252676"
---
# Bereitstellungspaket

Bereitstellungspakete können zum Vorbereiten und Konfigurieren von Geräten in einer Umgebung ohne Zugriff auf die Endpunkt Verwaltung verwendet werden. Sie können auch unabhängig von der Identität des Benutzers, dem Registrierungsstatus, während der Out-of-Box-Umgebung (OOBE) oder durch [Anwenden eines Bereitstellungspakets während des Setups](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)auf einem Gerät bereitgestellt werden.

## Überlegungen zu Bereitstellungspaketen:

* Nicht öffentliche apps
* Nur USB-Seite laden
* Keine automatische Aktualisierung (erfordert manuelle Updates über PPKGs)

Apps, die über ein Bereitstellungspaket installiert wurden, müssen mit einem Zertifikat im lokalen Computerspeicher signiert sein. Bereitstellungspakete können nur Zertifikate auf dem Gerätespeicher (lokaler Computer) installieren, daher kann eine APP und ein Zertifikat über das gleiche Bereitstellungspaket installiert werden. Wenn Sie Ihr Zertifikat von MDM bereitstellen oder über den [Zertifikat-Manager](certificate-manager.md)installieren, stellen Sie sicher, dass Sie das Zertifikat im lokalen Computerspeicher bereitstellen, um auf diese Weise installierte apps zu signieren.

Informationen zu den Grundlagen zum Erstellen eines Bereitstellungspakets für HoloLens-Geräte finden Sie unter [HoloLens-Bereitstellung](https://docs.microsoft.com/hololens/hololens-provisioning). Um eine APP bereitzustellen, müssen Sie mit der erweiterten Bereitstellung beginnen.

> [!NOTE]
> HoloLens (1st Generation) hat begrenzte Unterstützung bei der Installation von apps (**UniversalAppInstall**) mithilfe eines Bereitstellungspakets. HoloLens (1st Gen)-Geräte unterstützen nur die Installation einer APP über PPKG nur während der OOBE und nur bei Installationen des Benutzerkontexts.

## Setup

Führen Sie im [Windows-Konfigurations-Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) die folgenden vier Schritte aus.

1. Setzen Sie ApplicationManagement/AllowAllTrustedApps auf "Ja". Siehe: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Navigieren Sie zu **UniversalAppInstall**  >  **UserContextAppLicense** geben Sie den **PackageFamilyName**ein. Siehe [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall). Siehe auch: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Sie können Device Portal auf einem Gerät verwenden, auf dem Sie Ihre APP bereits installiert haben. Besuchen Sie die Seite "Apps", und schauen Sie sich die PackageRelativeID-Zeile, alle Informationen vor dem "!" an. Ist Ihre **PackageFamilyName**.

3. Sie sehen dann, dass Sie einen neuen Abschnitt, " **applicationdatei**" haben. In diesem Bereich können Sie Ihr AppX-Bundle hochladen.

4. Je nachdem, ob Sie Ihre APP gekauft oder eine eigene Branchen-App erstellt haben, müssen Sie die Lizenzdatei oder das Sicherheitszertifikat hochladen.

    - Für Lizenzdatei: Navigieren Sie zu **UniversalAppInstall**  >  **UserContextAppLicence** , und navigieren Sie zum Speicherort Ihrer Lizenz, und laden Sie Sie hoch.
    - Navigieren Sie für die Sicherheitsdatei zu **Zertifikate** , und wählen Sie das Zertifikat aus, das Sie zusammen mit dem AppX-Paket installieren möchten.

Stellen Sie sicher, dass Sie Ihr Projekt an einem sicheren Ort speichern. **Exportieren** Sie Sie dann als **Bereitstellungspaket**.  

Siehe auch: [Anwenden Ihres Bereitstellungspakets auf HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
