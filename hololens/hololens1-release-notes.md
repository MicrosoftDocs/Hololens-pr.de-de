---
title: Versionshinweise zu HoloLens 1st (Gen)
description: Informieren Sie sich über Updates in jeder neuen HoloLens-Version.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/12/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: ab67962efdafe3f39097210d60589dc6db715837
ms.sourcegitcommit: c870802ea75a9dd602319c59fedb124f80c19b71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "11136170"
---
# Versionshinweise zu HoloLens 1st (Gen)

## HoloLens (1st Gen) langzeitwartung
HoloLens (1. Generation) hat den Status "langzeitwartung" (LTS) eingegeben. Zukünftige Updates konzentrieren sich auf Problem-und Sicherheitsfixes und unter Beibehaltung der funktionsparität mit der Windows 10 holographischen Version 1809 für HoloLens (1st Generation).

Für Entwickler bedeutet dies, dass HoloLens (1st Gen)-Apps die openxr-API nicht unterstützen.  Diese Headsets bleiben in Unity 2019 LTS mit dem WinRT-API-Back-End für den vollständigen Lebenszyklus von Unity 2019 LTS bis Mid-2022 unterstützt.

### Windows 10 holographisch, Version 1809

> **Gilt für:** HoloLens (1. Generation)

| Feature | Details |
|---|---|
| **Menü ' schnell Aktionen '** | Wenn Sie in einer APP sind, wird mit der Bloom-Geste nun ein Schnellmenü "Aktionen" geöffnet, damit Sie schnell auf häufig verwendete System Features zugreifen können, ohne die app verlassen zu müssen. <br> Informationen zum Menü "schnelle Aktionen" im Kioskmodus finden Sie unter [Einrichten von HoloLens im Kioskmodus](hololens-kiosk.md) .<br><br> |
| **Beenden der Videoaufnahme über das Menü "Start" oder "schnelle Aktionen"** | Wenn Sie die Videoaufnahme über das Menü "Start" oder "schnelle Aktionen" starten, können Sie die Aufzeichnung an derselben Stelle beenden. (Vergessen Sie nicht, dass Sie dies jederzeit auch mit Sprachbefehlen tun können.) |
| **Projekt auf ein Miracast-fähiges Gerät** | Projizieren Sie Ihre HoloLens-Inhalte auf ein nahe gelegenes Surface-Gerät oder einen Fernseher/Monitor, wenn Sie Microsoft Display-Adapter verwenden.  Wählen Sie im **Startmenü**die Option **verbinden**aus, und wählen Sie dann das Gerät aus, auf das Sie projizieren möchten. **Hinweis:** Sie können HoloLens bereitstellen, um die Miracast-Projektion zu verwenden, ohne den Entwicklermodus zu aktivieren. |
| **Neue Benachrichtigungen** | Sie können Benachrichtigungs-Toasts auf HoloLens anzeigen und darauf reagieren, genau wie auf einem PC. Schauen Sie, um Sie zu beantworten oder zu entlassen (oder wenn Sie in einer immersiven Umgebung sind, verwenden Sie die Bloom-Geste). |
| **HoloLens-Overlays**<br>(Dateiauswahl, Tastatur, Dialogfelder usw.) | Sie sehen nun Overlays wie Tastatur, Dialogfelder, Dateiauswahl usw., wenn Sie immersive Apps verwenden. |
| **Visuelle Feedback-Overlay-UI für Volumenänderung** | Wenn Sie die Lautstärketasten auf Ihrem HoloLens verwenden, sehen Sie eine visuelle Anzeige des Lautstärkepegels. |
| **Neue Benutzeroberfläche für den gerätestart** | Während des Startvorgangs wurde ein Lade Indikator hinzugefügt, um visuelles Feedback bereitzustellen, das vom System geladen wird. Starten Sie Ihr Gerät neu, um den neuen Lade Indikator anzuzeigen – zwischen der Nachricht "Hallo" und dem Windows-Start-Logo. |
| **Freigabe in der Nähe** | Hinzufügen der in der Nähe befindlichen Windows-Freigabefunktion, die es Ihnen ermöglicht, eine Aufzeichnung mit einem nahe gelegenen Windows-Gerät zu teilen. Wenn Sie ein Foto oder Video auf HoloLens erfassen (oder die Schaltfläche "freigeben" in einer APP wie Microsoft Edge verwenden), wählen Sie ein nahe gelegenes Windows-Gerät aus, für das Sie freigeben möchten. |
| **Freigeben von Microsoft Edge** | Die Schaltfläche "freigeben" ist jetzt in Microsoft Edge Windows auf HoloLens verfügbar. Wählen Sie in Microsoft Edge die Option **Freigeben**aus. Verwenden Sie die HoloLens-Freigabe Auswahl, um Webinhalte freizugeben. |

#### Für internationale Kunden

| Feature | Details |
| --- | --- |
| Lokalisierte Chinesisch-und Japanisch-Builds | Verwenden Sie HoloLens mit einer lokalisierten Benutzeroberfläche für vereinfachtes Chinesisch oder Japanisch, einschließlich lokalisierter Pinyin-Tastatur-, Diktier-und Sprachbefehle.<br>[Hier erfahren Sie, wie Sie die chinesische und japanische Version von HoloLens installieren.](hololens1-install-localized.md) |
| Sprachsynthese (TTS) | Das Feature für die Sprachsynthese unterstützt jetzt Chinesisch, Japanisch und Englisch. |

#### Für Administratoren

| Feature |  Details  |
|---|----|
| [Aktivieren der Bereitstellung nach dem Setup](hololens-provisioning.md) | Sie können jetzt ein Bereitstellungspaket für die Laufzeit über die **Einstellungen**jederzeit anwenden. |
| Zugewiesener Zugriff mit Azure Ad-Gruppen | Sie können jetzt Azure-Anzeigengruppen für die Konfiguration von Windows verwenden, dem Zugriff zum Einrichten einer einzelnen oder mehrerer App-Kiosk Konfiguration zugewiesen ist. |
| PIN-Anmeldung beim Profilwechsel vom Anmeldebildschirm | Die PIN-Anmeldung steht nun für **andere Benutzer**zur Verfügung. |
| Anmelden mit dem Web-Anmeldeinformationsanbieter mithilfe eines Kennworts | Sie können jetzt die Globe-Anmeldeoption auswählen, um die Web-Anmeldung mit Ihrem Kennwort zu starten. Wählen Sie im Anmeldebildschirm die Option **Anmeldeoptionen** aus, und wählen Sie die Option Globus aus, um die Web-Anmeldung zu starten. Geben Sie bei Bedarf Ihren Benutzernamen und dann Ihr Kennwort ein. <br>**Hinweis:** Wenn Sie während der Web-Anmeldung dazu aufgefordert werden, können Sie alle Pin/Smartcard-Optionen umgehen. |
| Gerätehardware Informationen durch MDM lesen, damit Geräte nach Seriennummer nachverfolgt werden können | IT-Administratoren können HoloLens nach Geräteseriennummer in der MDM-Konsole anzeigen und nachvollziehen. Informationen zur Verfügbarkeit und zu den Anleitungen finden Sie in der MDM-Dokumentation. |
| Einrichten des HoloLens-Gerätenamens über MDM (umbenennen) | IT-Administratoren können HoloLens-Geräte in ihrer MDM-Konsole anzeigen und umbenennen. Informationen zur Verfügbarkeit und zu den Anleitungen finden Sie in der MDM-Dokumentation. |

### Windows 10, Version 1803 für Microsoft HoloLens

> **Gilt für:** HoloLens (1. Generation)

Windows 10, Version 1803, ist das erste Funktions Update für Windows holographische for Business seit seiner Veröffentlichung in Windows 10, Version 1607. Mit diesem Update werden die folgenden Änderungen eingeführt:

- Zuvor konnten Sie nur überprüfen, ob die Upgrade-Lizenz für Commercial Suite auf Ihr HoloLens-Gerät angewendet wurde, indem Sie überprüfen, ob VPN eine verfügbare Option auf dem Gerät war. Jetzt zeigt das **Einstellungs**  >  **System** **Windows holographisch für Unternehmen an** , nachdem die Upgrade-Lizenz angewendet wurde. [Hier erfahren Sie, wie Sie Windows holographische for Business-Features entsperren](hololens1-upgrade-enterprise.md).

- Sie können die Buildnummer des Betriebssystems in den Geräteeigenschaften in der App "Datei-Explorer" und im [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)anzeigen.
- Die Bereitstellungeines HoloLens-Geräts ist jetzt mit dem Assistenten für neue **Bereitstellungs HoloLens-Geräte** im Windows-Konfigurations-Designer-Tool einfacher. Im Assistenten können Sie die Setup Umgebung und Netzwerkverbindungen konfigurieren, den Entwicklermodus festlegen und Massen Azure AD-Token abrufen. [Hier erfahren Sie, wie Sie den einfachen Bereitstellungs-Assistenten für HoloLens verwenden](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Wenn Sie ein lokales Konto in einem Bereitstellungspaket erstellen, läuft das Kennwort nicht mehr alle 42 Tage ab.

- Sie können [HoloLens als Single-APP-oder Multi-App-Kiosk konfigurieren](hololens-kiosk.md). Im Multi-App-Kioskmodus können Sie einen HoloLens so einrichten, dass nur die von Ihnen angegebenen apps ausgeführt werden, und es wird verhindert, dass Benutzer Änderungen vornehmen.

- Das Media Transfer Protocol (MTP) ist aktiviert, sodass Sie das HoloLens-Gerät über USB an einen PC anschließen und Dateien zwischen HoloLens und dem PC übertragen können. Sie können auch die Datei-Explorer-App verwenden, um Dateien in HoloLens zu verschieben und zu löschen.

- Nachdem Sie sich zuvor mit einem Azure Active Directory (Azure AD)-Konto bei dem Gerät angemeldet haben, mussten Sie in den **Einstellungen** den **Arbeits Zugriff hinzufügen** , um Zugriff auf Unternehmensressourcen zu erhalten. Nun können Sie sich mit einem Azure AD-Konto anmelden, und die Registrierung erfolgt automatisch.

- Bevor Sie sich anmelden, können Sie das Netzwerksymbol unter dem Kennwortfeld auswählen, um ein anderes Wi-Fi Netzwerk auszuwählen, mit dem eine Verbindung hergestellt werden soll. Sie können auch eine Verbindung mit einem Gastnetzwerk herstellen, beispielsweise in einem Hotel, einem Konferenzzentrum oder einem Unternehmen.

- Sie können HoloLens nun problemlos [für mehrere Personen](hololens-multiple-users.md) mit Azure Ad-Konten freigeben.

- Wenn Setup oder Anmeldung fehlschlägt, wählen Sie die Option neue **Sammlungsinformationen** aus, um Diagnoseprotokolle für die Problembehandlung abzurufen.

- Einzelne Benutzer können Ihre Firmen-e-Mails synchronisieren, ohne Ihr Gerät in Mobile Device Management (MDM) zu registrieren. Sie können das Gerät mit einem Microsoft-Konto verwenden, die e-Mail-app herunterladen und installieren sowie ein e-Mail-Konto direkt hinzufügen.

- Sie können den MDM-Synchronisierungsstatus für ein Gerät unter **Einstellungen**für  >  **Konten**  >  **Zugriff auf Arbeit oder Schul**  >  **Informationen**überprüfen. Im Abschnitt **Geräte Synchronisierungsstatus** können Sie eine Synchronisierung starten, die von MDM verwalteten Bereiche anzeigen sowie einen erweiterten Diagnosebericht erstellen und exportieren.
