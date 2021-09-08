---
title: Bereitstellungspaket
description: Erfahren Sie mehr über app packaging, provisioning, deployment und enterprise app deployment for HoloLens devices (Packen, Bereitstellen, Bereitstellen und Bereitstellen HoloLens Unternehmens-Apps).
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
ms.openlocfilehash: d071f4326a35a9ea61e2069618da7107bb808f04
ms.sourcegitcommit: f480d3cc8d549fa356e05df6ce15e9517f5b978a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2021
ms.locfileid: "123610988"
---
# <a name="provisioning-package"></a>Bereitstellungspaket

Bereitstellungspakete können verwendet werden, um Geräte in einer Umgebung ohne Zugriff auf die Endpunktverwaltung vorzubereiten und zu konfigurieren. Sie können auch auf einem Gerät bereitgestellt werden, unabhängig von der Identität des Benutzers, dem Registrierungsstatus, während der Out-of-Box-Benutzeroberfläche (OOBE) oder durch Anwenden eines Bereitstellungspakets während des [Setups.](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## <a name="provisioning-packages-considerations"></a>Überlegungen zur Bereitstellung von Paketen

* Nicht öffentliche Apps
* Nur usbseitiges Laden
* Keine automatische Aktualisierung (erfordert manuelle Updates über PPKGs)

Apps, die über ein Bereitstellungspaket installiert werden, müssen durch ein Zertifikat im Speicher des lokalen Computers signiert werden. Bereitstellungspakete können nur Zertifikate im Gerätespeicher (lokaler Computer) installieren. Daher können eine App und ein Zertifikat über dasselbe Bereitstellungspaket installiert werden. Wenn Sie Ihr Zertifikat über MDM bereitstellen oder über den [Zertifikat-Manager](certificate-manager.md)installieren, stellen Sie sicher, dass Sie das Zertifikat im lokalen Computerspeicher bereitstellen, um auf diese Weise installierte Apps zu signieren.

Informationen zu den Grundlagen zum Erstellen eines Bereitstellungspakets für HoloLens-Geräte finden Sie [unter HoloLens Provisioning](/hololens/hololens-provisioning). Um eine App bereitzustellen, müssen Sie mit der erweiterten Bereitstellung beginnen.

> [!NOTE]
> HoloLens (1. Generation) bietet eingeschränkte Unterstützung für die Installation von Apps (**UniversalAppInstall**) mithilfe eines Bereitstellungspakets. HoloLens -Geräte (1. Generation) unterstützen die Installation einer App über PPKG nur während oobe und nur mit Benutzerkontext-Installationen.

## <a name="setup"></a>Einrichten

Gehen [Windows Im Konfigurations-Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) die folgenden vier Schritte aus.

1. Legen Sie ApplicationManagement/AllowAllTrustedApps auf "Ja" fest. Siehe: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Navigieren Sie **zu UniversalAppInstall**  >  **UserContextApp, und** geben Sie **PackageFamilyName ein.** Weitere Informationen [finden Sie unter UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).

   Sie können Geräteportal auf einem Gerät verwenden, auf dem Sie Ihre App bereits installiert haben. Besuchen Sie die Seite Apps, und sehen Sie sich die Zeile PackageRelativeID mit allen Informationen vor dem "!" an. Ist Ihr **PackageFamilyName.**

3. Sie sehen dann, dass Sie über den neuen Abschnitt **ApplicationFile verfügen.** Verwenden Sie diesen Bereich, um Ihr AppX-Paket hochzuladen.

4. Je nachdem, ob Sie Ihre App erworben oder Eine eigene BRANCHEN-App erstellt haben, müssen Sie die Lizenzdatei oder das Sicherheitszertifikat hochladen.

    - Für die Lizenzdatei: Navigieren Sie zu **UniversalAppInstall**  >  **UserContextAppLicence,** und geben Sie Ihre Lizenzprodukt-ID ein. Ein neuer Abschnitt <b>LicenseProductID:</b><i>yourlicenseproductid</i> wird erstellt. Wählen Sie diesen neuen Abschnitt aus, navigieren Sie zum Speicherort Ihrer Lizenz, und laden Sie ihn hoch.
        - Weitere Informationen [finden Sie unter UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).
    - Navigieren Sie für die Sicherheitsdatei zu **Zertifikate,** und wählen Sie Ihr Zertifikat aus, das zusammen mit Ihrem APPX-Paket installiert werden soll.

Stellen Sie sicher, dass Sie Ihr Projekt an einem sicheren Speicherort speichern. Exportieren Sie **sie** dann als **Bereitstellungspaket.**  

Siehe auch: [Anwenden Ihres Bereitstellungspakets auf HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
