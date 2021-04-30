---
title: HoloLens 1st (Gen)-Versionshinweise
description: Erfahren Sie mehr über Updates in jedem neuen HoloLens-Release.
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
ms.openlocfilehash: 0fb6c9ed1cd8d3ecc23975052eed54512a465bfb
ms.sourcegitcommit: 35e180e09e3938c25e4cac8e99885d7e57fa4dad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "108310068"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens 1st (Gen)-Versionshinweise

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (1. Generation) Long Term Servicing
HoloLens (1. Generation) wurde in den Lts-Zustand (Long Term Servicing) übergegangen. Zukünftige Updates konzentrieren sich auf Problem- und Sicherheitskorrekturen, während gleichzeitig die Featureparität mit der Windows 10 Holographic Version 1809 für HoloLens (1. Generation) beibehalten wird.

Für Entwickler bedeutet dies, dass HoloLens-Apps (1. Generation) die OpenXR-API nicht unterstützen.  Diese Headsets werden in Unity 2019 LTS mit dem WinRT-API-Back-End für den gesamten Lebenszyklus von Unity 2019 LTS bis Mitte 2022 weiterhin unterstützt.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic, Version 1809

> **Gilt für:** HoloLens (1. Generation)

| Funktion | Details |
|---|---|
| **Menü "Schnelle Aktionen"** | Wenn Sie in einer App sind, öffnet die Geste Bloom jetzt ein Menü Schnellaktionen, um Ihnen schnellen Zugriff auf häufig verwendete Systemfeatures zu ermöglichen, ohne die App verlassen zu müssen. <br> Informationen zum Menü "Schnelle Aktionen" im Kioskmodus finden Sie unter Einrichten von [HoloLens](hololens-kiosk.md) im Kioskmodus.<br><br> |
| **Beenden der Videoaufnahme über das Menü "Start" oder "Schnellaktionen"** | Wenn Sie die Videoaufnahme über das Menü "Startmenü" oder "Schnelle Aktionen" starten, können Sie die Aufzeichnung an derselben Stelle beenden. (Vergessen Sie nicht, sie können dies auch immer mit Sprachbefehlen tun.) |
| **Projekt auf ein Miracast-fähiges Gerät** | Prognannen Sie Ihre HoloLens-Inhalte auf ein Surface-Gerät in der Nähe oder einen Tv/Monitor, wenn Sie den Microsoft Display-Adapter verwenden.  Wählen **Sie unter Start** die Option **Verbinden** aus, und wählen Sie dann das Gerät aus, auf das Sie projektieren möchten. **Hinweis:** Sie können HoloLens für die Verwendung der Miracast-Projektion bereitstellen, ohne den Entwicklermodus zu aktivieren. |
| **Neue Benachrichtigungen** | Zeigen Sie Benachrichtigungs-Popups auf HoloLens an, und reagieren Sie darauf, genau wie auf einem PC. Anvieren, um darauf zu reagieren oder sie zu verdringen (oder wenn Sie sich in einer immersiven Umgebung sind, verwenden Sie die Blumengeste). |
| **HoloLens-Überlagerungen**<br>(Dateiauswahl, Tastatur, Dialogfelder usw.) | Wenn Sie immersive Apps verwenden, werden nun Überlagerungen wie Tastatur, Dialogfelder, Dateiauswahl usw. angezeigt. |
| **Visuelle Feedbacküberlagerungsbenutzeroberfläche für Volumeänderung** | Wenn Sie die Auf-/Ab-Schaltflächen des Volumes auf Ihrer HoloLens verwenden, wird eine visuelle Darstellung der Volumeebene angezeigt. |
| **Neue Benutzeroberfläche für den Gerätestart** | Während des Startvorgangs wurde ein Ladeindikator hinzugefügt, um visuelles Feedback zu geben, das das System lädt. Starten Sie Ihr Gerät neu, um den neuen Ladeindikator zu sehen– er liegt zwischen der Nachricht "Hello" und dem Windows-Startlogo. |
| **Freigabe in der Nähe** | Zusätzlich zur Umgebungsfreigabe von Windows in der Nähe, mit der Sie eine Erfassung für ein Windows-Gerät in der Nähe freigeben können. Wenn Sie ein Foto oder Video auf HoloLens erfassen (oder die Schaltfläche "Freigeben" aus einer App wie Microsoft Edge) verwenden, wählen Sie ein Windows-Gerät in der Nähe aus, für das die Freigabe ausgeführt werden soll. |
| **Freigeben aus Microsoft Edge** | Die Schaltfläche "Freigeben" ist jetzt in Microsoft Edge HoloLens verfügbar. Wählen Microsoft Edge die Option **Freigeben aus.** Verwenden Sie die HoloLens-Freigabeauswahl, um Webinhalte zu teilen. |

#### <a name="for-international-customers"></a>Für internationale Kunden

| Funktion | Details |
| --- | --- |
| Lokalisierte chinesische und japanische Builds | Verwenden Sie HoloLens mit lokalisierter Benutzeroberfläche für Chinesisch (vereinfacht) oder Japanisch, einschließlich lokalisierter Pinyin-Tastatur, Diktat und Sprachbefehlen.<br>[Erfahren Sie, wie Sie die chinesische und japanische Version von HoloLens installieren.](hololens1-install-localized.md) |
| Sprachsynthese (TTS) | Die Sprachsynthesefunktion unterstützt jetzt Chinesisch, Japanisch und Englisch. |

#### <a name="for-administrators"></a>Für Administratoren

| Funktion |  Details  |
|---|----|
| [Aktivieren der Bereitstellung nach dem Setup](hololens-provisioning.md) | Sie können jetzt jederzeit mithilfe von **Einstellungen** ein Laufzeitbereitstellungspaket anwenden. |
| Zugewiesener Zugriff mit Azure AD Gruppen | Sie können jetzt Azure AD Gruppen für die Konfiguration des windows-zugewiesenen Zugriffs verwenden, um eine Kioskkonfiguration mit einer oder mehreren Apps einzurichten. |
| Pin-Anmeldeprofilwechsel vom Anmeldebildschirm | Die PIN-Anmeldung ist jetzt für **Andere Benutzer** verfügbar. |
| Anmelden mit Web Anmeldeinformationsanbieter mit kennwort | Sie können jetzt die Globe-Anmeldeoption auswählen, um die Webanmeldung mit Ihrem Kennwort zu starten. Wählen Sie auf dem Anmeldebildschirm **Anmeldeoptionen** und dann die Option Globe aus, um die Webanmeldung zu starten. Geben Sie bei Bedarf Ihren Benutzernamen und dann Ihr Kennwort ein. <br>**Hinweis:** Sie können pin-/Smartcard-Optionen umgehen, wenn Sie während der Webanmeldung dazu aufgefordert werden. |
| Lesen von Gerätehardwareinformationen über MDM, damit Geräte anhand der Seriennummer nachverfolgt werden können | IT-Administratoren können HoloLens anhand der Seriennummer des Geräts in ihrer MDM-Konsole anzeigen und nachverfolgen. Informationen zur Featureverfügbarkeit und Anweisungen finden Sie in der MDM-Dokumentation. |
| Festlegen des HoloLens-Gerätenamens über MDM (Umbenennen) | IT-Administratoren können HoloLens-Geräte in ihrer MDM-Konsole anzeigen und umbenennen. Informationen zur Verfügbarkeit von Features und Anweisungen finden Sie in der MDM-Dokumentation. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10, Version 1803 für Microsoft HoloLens

> **Gilt für:** HoloLens (1. Generation)

Windows 10 Version 1803 ist das erste Featureupdate für Windows Holographic for Business seit der Veröffentlichung in Windows 10 Version 1607. Dieses Update führt die folgenden Änderungen ein:

- Zuvor konnten Sie nur überprüfen, ob die Upgradelizenz für Commercial Suite auf Ihr HoloLens-Gerät angewendet wurde, indem Sie überprüfen, ob VPN eine verfügbare Option auf dem Gerät war. Nun zeigt **das**  >  **Einstellungssystem** Windows Holographic for Business, nachdem die Upgradelizenz angewendet wurde.  [Erfahren Sie, wie Sie Windows Holographic for Business entsperren.](hololens1-upgrade-enterprise.md)

- Sie können die Buildnummer des Betriebssystems in den Geräteeigenschaften in der Datei-Explorer-App und im [Windows Device Recovery Tool (WDRT) anzeigen.](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)
- Die Bereitstellung eines HoloLens-Geräts ist jetzt mit dem neuen Assistenten Zum Bereitstellen von **HoloLens-Geräten** im Windows-Konfigurations-Designer-Tool einfacher. Im Assistenten können Sie die Einrichtungserfahrung und Netzwerkverbindungen konfigurieren, den Entwicklermodus festlegen und Massentoken Azure AD abrufen. [Erfahren Sie, wie Sie den Assistenten für die einfache Bereitstellung für HoloLens verwenden.](hololens-provisioning.md#provisioning-package-hololens-wizard)

- Wenn Sie ein lokales Konto in einem Bereitstellungspaket erstellen, läuft das Kennwort nicht mehr alle 42 Tage ab.

- Sie können [HoloLens als Kiosk](hololens-kiosk.md)mit einer oder mehreren Apps konfigurieren. Im Kioskmodus mit mehreren Apps können Sie eine HoloLens so einrichten, dass nur die von Ihnen angegebenen Apps ausgeführt werden, und Benutzer daran hindert werden, Änderungen vorzunehmen.

- Das Medienübertragungsprotokoll (Media Transfer Protocol, MTP) ist aktiviert, sodass Sie das HoloLens-Gerät per USB mit einem PC verbinden und Dateien zwischen HoloLens und dem PC übertragen können. Sie können auch die Datei-Explorer-App verwenden, um Dateien aus HoloLens zu verschieben und zu löschen.

- Nachdem Sie sich zuvor mit einem Azure Active Directory-Konto (Azure AD) beim Gerät angemeldet haben,  mussten  Sie unter Einstellungen den Arbeitszugriff hinzufügen, um Zugriff auf Unternehmensressourcen zu erhalten. Jetzt melden Sie sich mit einem Azure AD-Konto an, und die Registrierung erfolgt automatisch.

- Bevor Sie sich anmelden, können Sie das Netzwerksymbol unterhalb des Kennwortfelds auswählen, um ein anderes Wi-Fi Netzwerk auszuwählen, mit dem eine Verbindung hergestellt werden soll. Sie können auch eine Verbindung mit einem Gastnetzwerk herstellen, z. B. in einem Hotel, einem Konferenzcenter oder einem Unternehmen.

- Sie können [HoloLens](hololens-multiple-users.md) jetzt problemlos für mehrere Personen freigeben, indem Sie Azure AD Konten verwenden.

- Wenn das Setup oder die Anmeldung fehlschlägt, wählen Sie die neue Option **Informationen sammeln** aus, um Diagnoseprotokolle für die Problembehandlung abzurufen.

- Einzelne Benutzer können ihre Unternehmens-E-Mails synchronisieren, ohne ihr Gerät bei der Verwaltung mobiler Geräte (Mobile Device Management, MDM) zu registrieren. Sie können das Gerät mit einem Microsoft-Konto verwenden, die E-Mail-App herunterladen und installieren und direkt ein E-Mail-Konto hinzufügen.

- Sie können den MDM-Synchronisierungsstatus für ein Gerät unter **Einstellungen**  >  **Konten**  >  **Zugriff auf Arbeits- oder**  >  **Schulinformationen** überprüfen. Im Abschnitt **Gerätesynchronisierungsstatus** können Sie eine Synchronisierung starten, bereiche anzeigen, die von MDM verwaltet werden, und einen erweiterten Diagnosebericht erstellen und exportieren.
