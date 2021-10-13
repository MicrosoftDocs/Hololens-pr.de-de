---
title: Microsoft Store für Unternehmen
description: Erfahren Sie, wie Sie mit dem Microsoft Store für Unternehmen, um Ihre Mixed Reality-Anwendungen in Ihrem Unternehmen zu veröffentlichen.
keywords: Microsoft Store für Unternehmen, msfb, app deployment, store
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
ms.openlocfilehash: 5bc719539aaa254b8aacb05e24554152231f7e5a
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924329"
---
# <a name="microsoft-store-for-business"></a>Microsoft Store für Unternehmen

Das [Microsoft Store für Unternehmen](/microsoft-store/microsoft-store-for-business-overview) ist in erster Linie für IT-Entscheidungsträger und Administratoren in Unternehmen oder Organisationen mit einer flexiblen Möglichkeit konzipiert, kostenlose und kostenpflichtige Apps in ausgewählten Märkten zu finden, zu erwerben, zu verwalten und zu verteilen, um gerätebasierte Geräte zu Windows 10 zu verteilen. 

Sie können Microsoft Store-Apps und private Line-of-Business-Apps in einem Bestand verwalten und lizenzen nach Bedarf zuweisen und wiederver verwenden. Sie können auch die beste Verteilungsmethode für Ihre Organisation auswählen: Direktes Zuweisen von Apps zu Einzelpersonen und Teams, Veröffentlichen von Apps auf privaten Seiten in Microsoft Store oder Herstellen einer Verbindung mit Verwaltungslösungen, um weitere Optionen zu erhalten.

Wenn Microsoft Store für Unternehmen von einem Endbenutzer verwendet wird, startet er die Microsoft Store App. Nach dem Start kann der Benutzer die Registerkarte mit dem Namen seiner Organisation auswählen. Anschließend werden die Apps angezeigt, die für den Benutzer oder dieses Gerät verfügbar sind.

> [!Note]
> Microsoft Store für Unternehmen werden apps nicht automatisch auf Geräte heruntergeladen (pushen). Apps aus dem Microsoft Store für Unternehmen können jedoch Ihrem MDM-Server (Device Management) zugeordnet werden, um Apps als Ziel zu verwenden und mit Geräten zu synchronisieren.

Auf den folgenden Seiten finden Sie weitere Informationen zur Verwendung der Microsoft Store für Unternehmen:

* [Berechtigungsebenen, die zum Installieren von Anwendungen verwendet werden](/mem/intune/configuration/device-restrictions-windows-holographic#app-store)
* [Hinzufügen einer App zu Ihrer Store for Business](/mem/intune/apps/store-apps-windows)
* [Zuweisen von Apps zu Mitarbeitergruppen](/mem/intune/apps/windows-store-for-business)

Informationen zum Zuordnen Ihrer Microsoft Store für Unternehmen Finden Sie unter [Zuordnen Ihrer Microsoft Store für Unternehmen Intune.](/mem/intune/apps/windows-store-for-business#associate-your-microsoft-store-for-business-account-with-intune)

> [!Tip]
> Erfahren Sie mehr [über das Verteilen von Offline-Apps bei](/microsoft-store/distribute-offline-apps) Verwendung von Apps wie Advanced Recovery Companion (ARC) und Windows Configuration Designer (WCD).

## <a name="use-only-private-store-apps-for-microsoft-store"></a>Verwenden Sie nur private Store-Apps für Microsoft Store

- Eingeführt in [Windows Holographic, Version 21H2](hololens-release-notes.md#windows-holographic-version-21h2).

Die RequirePrivateStoreOnly-Richtlinie wurde für die HoloLens. Mit dieser Richtlinie kann die Microsoft Store-App so konfiguriert werden, dass nur der für Ihre Organisation konfigurierte private Speicher angezeigt wird. Beschränken des Zugriffs nur auf die Apps, die Sie zur Verfügung gestellt haben.

Weitere Informationen zu [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

## <a name="smart-retry-for-app-updates"></a>Smart Retry für App-Updates

- Eingeführt in [Windows Holographic, Version 21H2](hololens-release-notes.md#windows-holographic-version-21h2).

Jetzt für HoloLens ist eine neue Richtlinie, mit der IT-Administratoren ein wiederholungsfähiges oder einmaliges Datum für den Neustart von Apps festlegen können, deren Update fehlgeschlagen ist, weil die App verwendet wird und das Update angewendet werden kann. Diese können basierend auf einigen verschiedenen Triggern festgelegt werden, z. B. einer geplanten Zeit oder Anmeldung. Weitere Informationen zur Verwendung dieser Richtlinie finden Sie unter [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures).