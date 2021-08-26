---
ms.openlocfilehash: d96a769b40daba0948f8f3c71a88513576c531b5
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859209"
---
# <a name="non-aad-configuration"></a>[Nicht-AAD-Konfiguration](#tab/nonaadlogon)

#### <a name="non-aad-configuration"></a>Nicht-AAD-Konfiguration

1. Erstellen Sie ein Bereitstellungspaket, das:
    1. Konfiguriert Laufzeiteinstellungen/AssignedAccess, um Besucherkonten zuzulassen.
    1. Registriert das Gerät optional bei MDM (Laufzeiteinstellungen/Arbeitsplatz/Registrierungen), damit es später verwaltet werden kann.
    1. Erstellen Sie kein lokales Konto.
2. [Wenden Sie das Bereitstellungspaket an.](../hololens-provisioning.md)

# <a name="aad-configuration"></a>[AAD-Konfiguration](#tab/aadlogon)

#### <a name="aad-configuration"></a>AAD-Konfiguration

In AAD eingebundene Geräte, die für den Kioskmodus konfiguriert sind, können sich mit einer einzigen Schaltfläche auf dem Anmeldebildschirm bei einem Besucherkonto anmelden. Nach der Anmeldung beim Besucherkonto fordert das Gerät erst dann zur erneuten Anmeldung auf, wenn der Besucher explizit über das Startmenü abgemeldet oder das Gerät neu gestartet wird.

Die automatische Anmeldung des Besuchers kann über [eine benutzerdefinierte OMA-URI-Richtlinie](/mem/intune/configuration/custom-settings-windows-10)verwaltet werden:

- URI-Wert: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Richtlinie | BESCHREIBUNG | Configurations |
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Ermöglicht einem Besucher die automatische Anmeldung bei einem Kiosk. | 1 (Ja), 0 (Nein, Standard) |