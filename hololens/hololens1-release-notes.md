---
title: Versionshinweise zu HoloLens 1. Generation
description: Erfahren Sie mehr über Updates in jedem neuen HoloLens Release.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: e332794baf20fbab8278a138ceeafb651c6fa2a06f3f41a66038e544f7a6e46b
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661835"
---
# <a name="hololens-1st-gen-release-notes"></a>Versionshinweise zu HoloLens 1. Generation

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (1. Generation) Langfristige Wartung
HoloLens (1. Generation) wurde in den Lts-Zustand (Long Term Servicing) übergegangen. Zukünftige Updates konzentrieren sich auf Problem- und Sicherheitskorrekturen und behalten gleichzeitig die Featureparität mit der Windows 10 Holographic Version 1809 für HoloLens (1. Generation) bei.

Für Entwickler bedeutet dies, dass HoloLens -Apps (1. Generation) die OpenXR-API nicht unterstützen.  Diese Headsets werden in Unity 2019 LTS mit dem WinRT-API-Back-End für den gesamten Lebenszyklus von Unity 2019 LTS bis Mitte 2022 weiterhin unterstützt.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic, Version 1809

> **Gilt für:** HoloLens (1. Generation)

| Funktion | Details |
|---|---|
| **Menü "Schnelle Aktionen"** | Wenn Sie in einer App sind, öffnet die Geste Bloom jetzt ein Menü Schnellaktionen, um Ihnen schnellen Zugriff auf häufig verwendete Systemfeatures zu ermöglichen, ohne die App verlassen zu müssen. <br> Informationen zum Menü Schnellaktionen [im Kioskmodus](hololens-kiosk.md) finden Sie unter Einrichten von HoloLens im Kioskmodus.<br><br> |
| **Beenden der Videoaufnahme über das Menü "Start" oder "Schnellaktionen"** | Wenn Sie die Videoaufnahme über das Menü Startmenü oder schnelle Aktionen starten, können Sie die Aufzeichnung an derselben Stelle beenden. (Vergessen Sie nicht, sie können dies auch immer mit Sprachbefehlen tun.) |
| **Project zu einem Miracast-fähigen Gerät** | Project Ihre HoloLens Inhalte an ein surface-Gerät in der Nähe oder einen Tv/Monitor in der Nähe, wenn Sie den Microsoft Display-Adapter verwenden.  Wählen Sie **unter** **Start** Verbinden aus, und wählen Sie dann das Gerät aus, auf das Sie ein Projekt erstellen möchten. **Hinweis:** Sie können HoloLens bereitstellen, um Miracast Projektion zu verwenden, ohne den Entwicklermodus zu aktivieren. |
| **Neue Benachrichtigungen** | Zeigen Sie wie auf einem PC Benachrichtigungs-Popups auf HoloLens an, und reagieren Sie darauf. Anvisieren, um darauf zu reagieren oder sie zu verwerfen (oder wenn Sie sich in einer immersiven Benutzeroberfläche befinden, verwenden Sie die Geste "Bloom"). |
| **HoloLens Überlagerungen**<br>(Dateiauswahl, Tastatur, Dialogfelder usw.) | Wenn Sie immersive Apps verwenden, werden nun Überlagerungen wie Tastatur, Dialogfelder, Dateiauswahl usw. angezeigt. |
| **Benutzeroberfläche für visuelles Feedbacküberlagerung für Volumenänderungen** | Wenn Sie die Auf-/Ab-Schaltflächen des Volumes auf Ihrem HoloLens wird eine visuelle Anzeige der Volumeebene angezeigt. |
| **Neue Benutzeroberfläche für den Gerätestart** | Während des Startvorgangs wurde ein Ladeindikator hinzugefügt, um visuelles Feedback zu geben, dass das System geladen wird. Starten Sie Ihr Gerät neu, um den neuen Ladeindikator anzuzeigen– er befindet sich zwischen der "Hello"-Nachricht und dem Windows Startlogo. |
| **Freigabe in der Nähe** | Hinzufügen der Windows Umgebung für die Freigabe in der Nähe, sodass Sie eine Erfassung für ein gerät in der Nähe Windows freigeben können. Wenn Sie ein Foto oder Video auf HoloLens aufnehmen (oder die Schaltfläche "Freigeben" aus einer App wie Microsoft Edge verwenden), wählen Sie ein in der Nähe befindliches Windows Gerät aus, für das sie freigegeben werden sollen. |
| **Freigeben über Microsoft Edge** | Die Schaltfläche Freigeben ist jetzt in Microsoft Edge Fenstern auf HoloLens verfügbar. Wählen Sie in Microsoft Edge **freigeben** aus. Verwenden Sie die HoloLens Freigabeauswahl, um Webinhalte freizugeben. |

#### <a name="for-international-customers"></a>Für internationale Kunden

| Funktion | Details |
| --- | --- |
| Lokalisierte chinesische und japanische Builds | Verwenden Sie HoloLens mit lokalisierter Benutzeroberfläche für Chinesisch (vereinfacht) oder Japanisch, einschließlich lokalisierter Pinyin-Tastatur, Diktat und Sprachbefehlen.<br>[Erfahren Sie, wie Sie die chinesische und japanische Version von HoloLens installieren.](hololens1-install-localized.md) |
| Sprachsynthese (TTS) | Die Sprachsynthesefunktion unterstützt jetzt Chinesisch, Japanisch und Englisch. |

#### <a name="for-administrators"></a>Für Administratoren

| Funktion |  Details  |
|---|----|
| [Aktivieren der Bereitstellung nach dem Setup](hololens-provisioning.md) | Sie können jetzt jederzeit ein Laufzeitbereitstellungspaket anwenden, indem Sie **Einstellungen** verwenden. |
| Zugewiesener Zugriff mit Azure AD Gruppen | Sie können jetzt Azure AD Gruppen für die Konfiguration Windows zugewiesenen Zugriffs verwenden, um eine Kioskkonfiguration mit einer oder mehreren Apps einzurichten. |
| Pin-Anmeldeprofilwechsel vom Anmeldebildschirm | Die PIN-Anmeldung ist jetzt für **Andere Benutzer** verfügbar. |
| Anmelden mit Web Anmeldeinformationsanbieter mit kennwort | Sie können jetzt die Globe-Anmeldeoption auswählen, um die Webanmeldung mit Ihrem Kennwort zu starten. Wählen Sie auf dem Anmeldebildschirm **Anmeldeoptionen** und dann die Option Globe aus, um die Webanmeldung zu starten. Geben Sie bei Bedarf Ihren Benutzernamen und dann Ihr Kennwort ein. <br>**Hinweis:** Sie können pin-/Smartcard-Optionen umgehen, wenn Sie während der Webanmeldung dazu aufgefordert werden. |
| Lesen von Gerätehardwareinformationen über MDM, damit Geräte anhand der Seriennummer nachverfolgt werden können | IT-Administratoren können HoloLens nach Geräteseriennummer in ihrer MDM-Konsole anzeigen und nachverfolgen. Informationen zur Featureverfügbarkeit und Anweisungen finden Sie in der MDM-Dokumentation. |
| Festlegen HoloLens Gerätenamens über MDM (Umbenennen) | IT-Administratoren können HoloLens Geräte in ihrer MDM-Konsole anzeigen und umbenennen. Informationen zur Featureverfügbarkeit und Anweisungen finden Sie in der MDM-Dokumentation. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10 Version 1803 für Microsoft HoloLens

> **Gilt für:** HoloLens (1. Generation)

Windows 10, Version 1803, ist das erste Featureupdate für Windows Holographic for Business seit der Veröffentlichung in Windows 10 Version 1607. Dieses Update führt die folgenden Änderungen ein:

- Zuvor konnten Sie nur überprüfen, ob die Upgradelizenz für Commercial Suite auf Ihr HoloLens Gerät angewendet wurde, indem Sie überprüfen, ob VPN auf dem Gerät verfügbar war. Jetzt zeigt **Einstellungen** System Windows Holographic for Business an,  >   nachdem die Upgradelizenz angewendet wurde.  [Erfahren Sie, wie Sie Windows Holographic for Business Features entsperren.](hololens1-upgrade-enterprise.md)

- Sie können die Buildnummer des Betriebssystems in den Geräteeigenschaften in der Datei-Explorer-App und im [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)anzeigen.
- Die Bereitstellung eines HoloLens Geräts ist jetzt mit dem neuen Assistenten zum **Bereitstellen von HoloLens Geräten** im Windows-Konfigurations-Designer-Tool einfacher. Im Assistenten können Sie die Einrichtungsumgebung und Netzwerkverbindungen konfigurieren, den Entwicklermodus festlegen und massenweise Azure AD Token abrufen. [Erfahren Sie, wie Sie den einfachen Bereitstellungs-Assistenten für HoloLens verwenden.](hololens-provisioning.md#provisioning-package-hololens-wizard)

- Wenn Sie ein lokales Konto in einem Bereitstellungspaket erstellen, läuft das Kennwort nicht mehr alle 42 Tage ab.

- Sie können HoloLens als Kiosk mit [einer app oder mehreren Apps konfigurieren.](hololens-kiosk.md) Im Kioskmodus mit mehreren Apps können Sie eine HoloLens einrichten, um nur die von Ihnen angegebenen Apps auszuführen, und Benutzer daran hindern, Änderungen vorzunehmen.

- Das Media Transfer Protocol (MTP) ist aktiviert, sodass Sie das HoloLens Gerät per USB mit einem PC verbinden und Dateien zwischen HoloLens und dem PC übertragen können. Sie können auch die Datei-Explorer-App verwenden, um Dateien innerhalb HoloLens zu verschieben und zu löschen.

- Nachdem Sie sich zuvor mit einem Azure Active Directory-Konto (Azure AD) beim Gerät angemeldet haben, mussten Sie den Arbeitszugriff in **Einstellungen** **hinzufügen,** um Zugriff auf Unternehmensressourcen zu erhalten. Jetzt melden Sie sich mit einem Azure AD-Konto an, und die Registrierung erfolgt automatisch.

- Bevor Sie sich anmelden, können Sie das Netzwerksymbol unterhalb des Kennwortfelds auswählen, um ein anderes Wi-Fi Netzwerk auszuwählen, mit dem eine Verbindung hergestellt werden soll. Sie können auch eine Verbindung mit einem Gastnetzwerk herstellen, z. B. in einem Hotel, einem Konferenzcenter oder einem Unternehmen.

- Sie können jetzt HoloLens mithilfe von Azure AD Konten problemlos [für mehrere Personen freigeben.](hololens-multiple-users.md)

- Wenn das Setup oder die Anmeldung fehlschlägt, wählen Sie die neue Option **Informationen sammeln** aus, um Diagnoseprotokolle für die Problembehandlung abzurufen.

- Einzelne Benutzer können ihre Unternehmens-E-Mails synchronisieren, ohne ihr Gerät bei der Verwaltung mobiler Geräte (Mobile Device Management, MDM) zu registrieren. Sie können das Gerät mit einem Microsoft-Konto verwenden, die E-Mail-App herunterladen und installieren und direkt ein E-Mail-Konto hinzufügen.

- Sie können den MDM-Synchronisierungsstatus für ein Gerät in **Einstellungen**  >  **Konten**  >  **auf Arbeits- oder Schulinformationen zugreifen**  >  überprüfen. Im Abschnitt **Gerätesynchronisierungsstatus** können Sie eine Synchronisierung starten, von MDM verwaltete Bereiche anzeigen und einen erweiterten Diagnosebericht erstellen und exportieren.
