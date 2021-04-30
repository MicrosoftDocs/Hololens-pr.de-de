---
title: Bereitstellungspaket
description: Erfahren Sie mehr über app packaging, provisioning, deployment und enterprise app deployment for HoloLens devices (Packen, Bereitstellen, Bereitstellen und Bereitstellen von Unternehmens-Apps für HoloLens-Geräte).
keywords: App, App-Bereitstellung, Enterprise-App-Bereitstellung, Bereitstellung
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
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308731"
---
# <a name="provisioning-package"></a>Bereitstellungspaket

Bereitstellungspakete können verwendet werden, um Geräte in einer Umgebung ohne Zugriff auf die Endpunktverwaltung vorzubereiten und zu konfigurieren. Sie können auch auf einem Gerät bereitgestellt werden, unabhängig von der Identität des Benutzers, dem Registrierungsstatus, während der Out-of-Box-Benutzeroberfläche (OOBE) oder durch Anwenden eines Bereitstellungspakets während des [Setups.](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## <a name="provisioning-packages-considerations"></a>Überlegungen zu Bereitstellungspaketen:

* Nicht öffentliche Apps
* Nur usbseitiges Laden
* Keine automatische Aktualisierung (erfordert manuelle Updates über PPKGs)

Apps, die über ein Bereitstellungspaket installiert werden, müssen durch ein Zertifikat im Speicher des lokalen Computers signiert werden. Bereitstellungspakete können nur Zertifikate im Gerätespeicher (lokaler Computer) installieren, daher können eine App und ein Zertifikat über dasselbe Bereitstellungspaket installiert werden. Wenn Sie Ihr Zertifikat über MDM bereitstellen oder über den [Zertifikat-Manager](certificate-manager.md)installieren, stellen Sie sicher, dass Sie das Zertifikat im lokalen Computerspeicher bereitstellen, um auf diese Weise installierte Apps zu signieren.

Informationen zu den Grundlagen zum Erstellen eines Bereitstellungspakets für HoloLens-Geräte finden Sie unter [HoloLens-Bereitstellung.](https://docs.microsoft.com/hololens/hololens-provisioning) Um eine App bereitzustellen, müssen Sie mit der erweiterten Bereitstellung beginnen.

> [!NOTE]
> HoloLens (1. Generation) bietet eingeschränkte Unterstützung für die Installation von Apps (**UniversalAppInstall**) mithilfe eines Bereitstellungspakets. HoloLens-Geräte (1. Generation) unterstützen nur die Installation einer App über PPKG nur während oobe und nur mit Benutzerkontext-Installationen.

## <a name="setup"></a>Setup

Gehen [Sie im Windows-Konfigurations-Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) wie folgt vor:

1. Legen Sie ApplicationManagement/AllowAllTrustedApps auf "Ja" fest. Siehe: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Navigieren Sie zu **UniversalAppInstall**  >  **UserContextAppLicense,** und geben Sie **PackageFamilyName ein.** Weitere Informationen finden Sie unter [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall). Siehe auch: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Sie können Geräteportal auf einem Gerät verwenden, auf dem Sie Ihre App bereits installiert haben. Besuchen Sie die Seite Apps, und sehen Sie sich die Zeile PackageRelativeID an, alle Informationen vor dem "!" Ist Ihr **PackageFamilyName.**

3. Sie sehen dann, dass Sie über den neuen Abschnitt **ApplicationFile** verfügen. Verwenden Sie diesen Bereich, um Ihr AppX-Paket hochzuladen.

4. Je nachdem, ob Sie Ihre App erworben oder Ihre eigene BRANCHEN-App erstellt haben, müssen Sie die Lizenzdatei oder das Sicherheitszertifikat hochladen.

    - Lizenzdatei: Navigieren Sie zu **UniversalAppInstall**  >  **UserContextAppLicence,** navigieren Sie zum Speicherort Ihrer Lizenz, und laden Sie sie hoch.
    - Navigieren Sie für die Sicherheitsdatei zu **Zertifikate,** und wählen Sie Ihr Zertifikat aus, das Sie zusammen mit Ihrem APPX-Paket installieren möchten.

Stellen Sie sicher, dass Sie Ihr Projekt an einem sicheren Speicherort speichern. Exportieren **Sie** es dann als **Bereitstellungspaket.**  

Siehe auch: [Anwenden Ihres Bereitstellungspakets auf HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)
