---
title: Bereitstellungspaket
description: Erfahren Sie mehr über das Packen, Bereitstellen, Bereitstellen und Bereitstellen von Unternehmens-Apps für HoloLens-Geräte.
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283696"
---
# Bereitstellungspaket

Bereitstellungspakete können zum Vorbereiten und Konfigurieren von Geräten in einer Umgebung ohne Zugriff auf die Endpunktverwaltung verwendet werden. Sie können auch auf einem Gerät bereitgestellt werden, unabhängig von der Identität des Benutzers, des Registrierungsstatus, während der Out of Box Experience (OOBE) oder durch Anwenden eines Bereitstellungspakets während des [Setups.](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## Überlegungen zu Bereitstellungspaketen:

* Nicht öffentliche Apps
* Nur usbseitiges Laden
* Kein automatisches Update (erfordert manuelle Updates über PPKGs)

Apps, die über ein Bereitstellungspaket installiert werden, müssen von einem Zertifikat im lokalen Computerspeicher signiert sein. Bereitstellungspakete können nur Zertifikate im Speicher des Geräts (lokaler Computer) installieren, daher können eine App und ein Zertifikat über dasselbe Bereitstellungspaket installiert werden. Wenn Sie Ihr Zertifikat von MDM bereitstellen oder über den [Zertifikat-Manager](certificate-manager.md)installieren, stellen Sie sicher, dass Sie das Zertifikat im lokalen Computerspeicher bereitstellen, um auf diese Weise installierte Apps zu signieren.

Informationen zu den Grundlagen des Erstellens eines Bereitstellungspakets für HoloLens-Geräte finden Sie unter [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning). Um eine App bereitstellen zu können, müssen Sie mit der erweiterten Bereitstellung beginnen.

> [!NOTE]
> HoloLens (1. Generation) bietet eingeschränkte Unterstützung für die Installation von Apps (**UniversalAppInstall**) mithilfe eines Bereitstellungspakets. HoloLens (1. Generation)-Geräte unterstützen nur die Installation einer App über PPKG nur während der OOBE und nur bei Installationen des Benutzerkontexts.

## Setup

In [Windows-Konfigurations-Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) gehen Sie wie folgt vor:

1. Legen Sie "ApplicationManagement/AllowAllTrustedApps" auf "Ja" fest. Siehe: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Navigieren Sie **zu "UniversalAppInstall**  >  **UserContextAppLicense"** und geben Sie **"PackageFamilyName" ein.** Siehe [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall). Siehe auch: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Sie können device Portal auf einem Gerät verwenden, auf dem Sie Ihre App bereits installiert haben. Besuchen Sie die Seite "Apps", und sehen Sie sich die Zeile "PackageRelativeID" an, alle Informationen vor dem "!" Ist Ihr **PackageFamilyName**.

3. Sie werden dann sehen, dass Sie einen neuen Abschnitt haben, **ApplicationFile**. Verwenden Sie diesen Bereich, um Ihr appx-Bündel hochzuladen.

4. Je nachdem, ob Sie Ihre App erworben oder Ihre eigene Branchen-App erstellt haben, müssen Sie die Lizenzdatei oder das Sicherheitszertifikat hochladen.

    - For license file: navigate to **UniversalAppInstall**  >  **UserContextAppLicence** and browse to the location of your license and upload it.
    - Navigieren Sie für die Sicherheitsdatei zu **"Zertifikate",** und wählen Sie Ihr Zertifikat aus, das Sie zusammen mit Ihrem .appx-Bundle installieren möchten.

Stellen Sie sicher, dass Sie Ihr Projekt an einem sicheren Ort speichern. Exportieren Sie **es** dann als **Bereitstellungspaket.**  

Siehe auch: [Wenden Sie Ihr Bereitstellungspaket auf HoloLens an.](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)
