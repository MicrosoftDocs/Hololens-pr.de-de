---
title: Windows Autopilot Registrierungsunterstützung für HoloLens 2
description: Erfahren Sie, wie Sie Registrierungsunterstützung für Autopilot auf HoloLens 2 Geräten erhalten.
author: joyjaz
ms.author: v-jjaswinski
ms.date: 5/20/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilotautzor t
manager: ylempidakis
ms.openlocfilehash: cdd2ab68905d5cc82b1c5ccc50640112e857f2f4
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "110398905"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>HoloLens 2 Registrierungsunterstützung für Autopilot

Kunden und Microsoft Cloud Solution Providers (CSPs) können jetzt HoloLens 2 Geräte registrieren, indem sie ihre Anfragen direkt an den Microsoft-Support senden. Auf dieser Seite werden die Anforderungen für die folgenden unterstützten Autopilot-Registrierungsszenarien beschrieben:

- **Autopilot-Registrierung für das HoloLens 2 Gerät**. Sendet die Anforderung zum Registrieren HoloLens 2 Geräten bei Windows Autopilot.
- **HoloLens 2 Hardwarehashanforderung für das Gerät**. Sendet eine Anforderung an den Microsoft-Support, um Ihnen Hardwarehashes zur Verfügung zu stellen, die Kunden oder CSPs zum Selbstregistern von Geräten über Microsoft Intune oder das Microsoft Partner Center verwenden können.
- **Autopilot-Registrierungsaufhebung für das HoloLens 2 Gerät**. Sendet eine Anforderung zum Löschen von Geräten aus Windows Autopilot, die in der Regel in Szenarien mit dem Ende der Gerätelebensdauer verwendet wird.

In der folgenden Tabelle werden die Informationen aufgeführt, die Sie benötigen, *bevor* Sie Registrierungsanforderungen an den Microsoft-Support senden.

| Erforderliche Informationen | BESCHREIBUNG | Autopilot-Registrierung  | Hardwarehashanforderung | Autopilot Registrierungsaufhebung |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory-Mandanten-ID    |    Ihre Azure Active Directory-Mandanten-ID ist eine GUID (Globally Unique Identifier), die sich vom Namen Oder der Domäne Ihres Unternehmens unterscheidet.    Melden Sie sich beim [Azure-Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) an, um Ihre Mandanten-ID zu finden.    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory-Domänenname    |   Der Domänenname der obersten Ebene. Beispiel: contoso.com.    |     ✔️                         |                              |                         ✔️                        |
|  Eigentumsnachweis    |   Überprüfen Sie den Eigentumsnachweis, indem Sie den ursprünglichen Kaufbeleg oder die Rechnung im PDF-Format hochladen. Screenshots werden nicht akzeptiert. Der Kaufbeleg oder die Rechnung muss Folgendes enthalten: Seriennummern des Geräts. Firmenname.     |     ✔️                         |              ✔️                |                         ✔️                        |
|  Seriennummer des Geräts    |   Hochladen der Excel-Datei im CSV-Format, in der jede Geräteseriennummer in einer neuen Zeile steht.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>Supportanfragen senden

> [!div class="nextstepaction"]
> [Autopilot-Registrierungsunterstützung für HoloLens 2 senden](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
