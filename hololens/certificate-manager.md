---
title: Zertifikat-Manager
description: Erfahren Sie, wie Sie Zertifikate auf HoloLens 2 Mixed Reality-Geräten manuell installieren, verwalten und entfernen.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/12/2021
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: af9c6634ddbb40acace9a2abf8dd933ec05704de
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924384"
---
# <a name="certificate-manager"></a>Zertifikat-Manager

- Verbesserte Überwachungs-, Diagnose- und Validierungstools für Gerätesicherheit und -konformität über den neuen Zertifikat-Manager. Mit dieser Funktion können Sie Ihre Zertifikate in kommerziellen Umgebungen im großen Stil bereitstellen, behandeln und überprüfen.

In Windows Holographic, Version 20H2, fügen wir einen Zertifikat-Manager in der HoloLens 2 Einstellungen-App hinzu. Wechseln Sie zu **Einstellungen > Update & Security > Certificates**. Dieses Feature bietet eine einfache und benutzerfreundliche Möglichkeit zum Anzeigen, Installieren und Entfernen von Zertifikaten auf Ihrem Gerät. Mit dem neuen Zertifikat-Manager verfügen Administratoren und Benutzer jetzt über verbesserte Überwachungs-, Diagnose- und Validierungstools, um sicherzustellen, dass Geräte sicher und konform bleiben.

-   **Überwachung:** Möglichkeit, zu überprüfen, ob ein Zertifikat ordnungsgemäß bereitgestellt wurde, oder um zu bestätigen, dass es ordnungsgemäß entfernt wurde.
-   **Diagnose:** Wenn Probleme auftreten, spart die Überprüfung, ob die entsprechenden Zertifikate auf dem Gerät vorhanden sind, Zeit und hilft bei der Problembehandlung.
-   **Überprüfung:** Die Überprüfung, ob ein Zertifikat den beabsichtigten Zweck erfüllt und funktionsfähig ist, kann insbesondere in kommerziellen Umgebungen erhebliche Zeit sparen, bevor Zertifikate in größerem Umfang bereitgestellt werden.

Um schnell ein bestimmtes Zertifikat in der Liste zu finden, gibt es Optionen zum Sortieren nach Name, Speicher oder Ablaufdatum. Benutzer können auch direkt nach einem Zertifikat suchen. Um einzelne Zertifikateigenschaften anzuzeigen, wählen Sie das Zertifikat aus, und klicken Sie auf **Info**.

Die Zertifikatinstallation unterstützt derzeit CER- und CRT-Dateien. Gerätebesitzer können Zertifikate auf dem lokalen Computer und dem aktuellen Benutzer installieren.  alle anderen Benutzer können nur in Current User installieren.

## <a name="to-install-a-certificate"></a>So installieren Sie ein Zertifikat:

1.  Verbinden Ihre HoloLens 2 zu einem PC.
1.  Platzieren Sie die Zertifikatdatei, die Sie installieren möchten, an einem Speicherort auf Ihrem HoloLens 2.
1.  Navigieren Sie zu **Einstellungen App > Update & Security > Certificates**, und wählen Sie Zertifikat installieren aus.
1.  Klicken Sie auf **Datei importieren,** und navigieren Sie zu dem Speicherort, an dem Sie das Zertifikat gespeichert haben.
1.  Wählen Sie **Store Standort aus.**
1.  Wählen Sie **Zertifikat Store** aus.
1.  Klicken Sie auf **Installieren**.

Das Zertifikat sollte nun auf dem Gerät installiert sein.

![Zertifikatanzeige in der Einstellungen-App unter Zertifikate.](images/certificate-viewer-device.jpg)

![Abbildung: Verwenden der Zertifikat-Benutzeroberfläche zum Installieren eines Zertifikats in Einstellungen](images/certificate-device-install.jpg)

## <a name="to-remove-a-certificate"></a>So entfernen Sie ein Zertifikat:

> [!WARNING]
> Mithilfe des Zertifikat-Managers können Benutzer nur Zertifikate entfernen, die direkt von der Einstellungen Ui installiert wurden. Wenn ein Zertifikat auf andere Weise installiert wurde, muss es auch mit demselben Mechanismus entfernt werden und kann nicht aus dem Zertifikat-Manager entfernt werden. Sie können mit MDM bereitgestellte Zertifikate zwar im Zertifikat-Manager anzeigen, aber nicht im Zertifikat-Manager deinstallieren. Sie müssen sie über MDM deinstallieren.

1. Navigieren Sie zu **Einstellungen App > Update and Security > Certificates**.
1. Suchen Sie im Suchfeld nach dem Zertifikat anhand des Namens.
1. Wählen Sie das Zertifikat aus.
1. Klicken Sie auf **Entfernen.**
1. Wählen Sie **Ja** aus, wenn Sie zur Bestätigung aufgefordert werden.

## <a name="pfx-file-support-for-certificate-manager"></a>PFX-Dateiunterstützung für den Zertifikat-Manager

- Eingeführt in [Windows Holographic, Version 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

 Wir haben dem Zertifikat-Manager Unterstützung für die Verwendung von PFX-Zertifikaten hinzugefügt. Wenn Benutzer zu **Einstellungen** Update &  >  **Sicherheitszertifikate** navigieren und Zertifikat  >   **installieren** auswählen, unterstützt die Benutzeroberfläche jetzt PFX-Zertifikatsdateien.
Benutzer können ein PFX-Zertifikat mit privatem Schlüssel in den Benutzer- oder Computerspeicher importieren.