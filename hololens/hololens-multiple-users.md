---
title: Freigeben Ihrer HoloLens für mehrere Personen
description: Sie können HoloLens so konfigurieren, dass sie von mehreren Azure Active Directory Konten oder von mehreren Benutzern, die ein einzelnes Konto verwenden, freigegeben werden.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/23/2021
ms.reviewer: anisgup
manager: sean-kerawala
appliesto:
- HoloLens 2
ms.openlocfilehash: bbb955edaa500187ea921538291bb1c7bda05422
ms.sourcegitcommit: be1393d24a98381e37bd1f56183c1f381f87cbd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2021
ms.locfileid: "129600728"
---
# <a name="share-your-hololens-with-multiple-people"></a>Freigeben Ihrer HoloLens für mehrere Personen

## <a name="overview"></a>Übersicht

Unternehmen investieren häufig in viele gemeinsam genutzte HoloLens Geräte. Die Verwendung von HoloLens ist je nach Ihren individuellen Anforderungen flexibel. Hier sehen Sie ein Beispiel für einige Benutzeroberflächen mit mehreren Benutzern:

- Eine Gruppe von HoloLens 2 Geräten wird über Windows Autopilot für HoloLens 2 mit einem konsistenten Portfolio von Unternehmensanwendungen auf jedem Gerät eingerichtet. Sie haben einige verschiedene Kioskprofile für verschiedene Azure AD Gruppen eingerichtet. Jeder Benutzer meldet sich mit FIDO2-Schlüsseln bei der HoloLens an und meldet sich bei seinem eigenen Azure AD-Konto an, und es wird eine maßgeschneiderte Benutzeroberfläche angezeigt.
- Ein unabhängiger Softwarehersteller (Independent Software Vendor, ISV) mieten HoloLens 2 Geräte mit D365-Remote Assist und deren Branchenanwendung an das Unternehmen eines Kunden. Diese Geräte sind für Kiosks konfiguriert, die nur ihre branchenspezifische App und Remote Assist enthalten und von mehreren Endbenutzern gemeinsam genutzt werden. WDAC wird verwendet, um den Start der Einstellungen-App und Microsoft Edge zu hindern. Im Lieferumfang des Verleihs ist ein USB-C-Akkupaket enthalten, mit dem die Geräte über mehrere Schichten vollständig geladen werden können.
- Ein Endbenutzer in einem Unternehmen versucht, Anpassungen an Bluetooth auf dem Gerät vorzunehmen, damit er eine Verbindung mit einem neuen Gerät herstellen kann. Die Richtlinie "Seite Einstellungen Sichtbarkeit" ist jedoch aktiviert, um die Anzeige der Seite Geräte zu beschränken. Sie können weiterhin bei Bedarf auf andere Seiten zugreifen, z. B. Wi-Fi, sodass sie Remote Assist an mehreren Stellen mit demselben HoloLens verwenden können.

## <a name="best-practices"></a>Bewährte Methoden

Wenn Sie planen, Ihre Geräte freizugeben, gibt es mehrere Überlegungen, um Ihre Geräteumgebung basierend auf Ihren Geschäftsanforderungen zu optimieren.

- [Identität und Authentifizierung](#identity-and-authentication)
- [Geräteverwaltung](#device-management)
- [Erweiterte Geräteverwaltung – Kiosk und WDAC](#advanced-device-management---kiosk-and-wdac)
- [Physische Verwaltung](#physical-management)

### <a name="identity-and-authentication"></a>[Identität und Authentifizierung](hololens-identity.md)

Wenn Sie mehrere Konten auf einem Gerät verwenden möchten, verfügen Sie über Azure AD Konten mit allen Authentifizierungsmodi. Diese Authentifizierungsmethoden basieren auf [Windows Hello](/windows-hardware/design/device-experiences/windows-hello), einschließlich Iris- und FIDO2-Schlüsseln.

- FIDO 2-Sicherheitsschlüssel sind hervorragend, wenn Sie über mehrere Geräte, viele Benutzer oder ständig neue Geräte verfügen.
- Wenn Sie über 10 oder weniger Benutzer verfügen, ist Iris eine schnelle Lösung zum Anmelden von Benutzern, die sich zuvor auf demselben Gerät angemeldet haben.

### <a name="device-management"></a>[Geräteverwaltung](hololens-csp-policy-overview.md)

Wenn Geräte von Benutzern gemeinsam genutzt werden, sollten Sie wahrscheinlich Geräteeinschränkungen verwenden. Mithilfe der Geräteverwaltung können Sie einige Richtlinien festlegen, um Ihren Benutzern die Verwendung des Geräts zu ermöglichen, Updates zu verwalten oder die Möglichkeiten des Geräts einzuschränken. Es wird empfohlen, dass Sie unsere [allgemeinen Geräteeinschränkungen](hololens-common-device-restrictions.md)überprüfen und überprüfen, ob diese Empfehlungen für Ihre Organisation geeignet zu sein scheinen. Sobald Sie wissen, welche Richtlinien Sie verwenden möchten, können Sie sie über [die microsoft-Endpoint Manager (MDM) oder Bereitstellungspakete](hololens-mdm-configure.md) anwenden.

### <a name="advanced-device-management---kiosk-and-wdac"></a>Erweiterte Geräteverwaltung – [Kiosk](hololens-kiosk.md) und [WDAC](windows-defender-application-control-wdac.md)

In einigen Fällen möchten Sie möglicherweise einschränken, auf welche Anwendungen die Endbenutzer zugreifen können. Sie können einschränken, welche Apps Benutzern im Startmenü angezeigt werden, indem Sie den [Kioskmodus verwenden.](hololens-kiosk.md) Kiosk kann so konfiguriert werden, dass je nach Benutzer, Azure-Gruppen oder speziellen Benutzertypen verschiedene Startmenüs angezeigt werden. solche Besucher oder ausgenommen Gerätebesitzer. Sie können mehrere Apps oder nur eine einzelne App auswählen. Ein Kiosk mit mehreren Apps verhindert nicht, dass eine App eine andere startet. Wenn der Store oder eine andere App verfügbar ist, können Benutzer weiterhin eine andere App starten.

Möglicherweise möchten Sie auch den Start von Apps oder Diensten mithilfe von [Windows Defender Application Control (WDAC)](windows-defender-application-control-wdac.md) vollständig beenden, um Apps einzuschränken. WDAC unterscheidet sich von Kiosk, da es die Benutzeroberfläche von HoloLens nicht ändert, sondern nicht das Starten einer blockierten App zulässt.

[Seiten-Einstellungen Sichtbarkeit](settings-uri-list.md) ist eine weitere Möglichkeit zum Hinzufügen von Einschränkungen zu einem Gerät. Für den Fall, dass Sie Benutzern Zugriff auf einige Seiten in der Einstellungen-App gewähren müssen, können Sie jedoch nicht alle Seiten Einstellungen Sichtbarkeit verwenden, um den Zugriff einzuschränken. Dies ist beispielsweise nützlich, wenn Ihre Benutzer das WLAN ändern müssen, aber nicht möchten, dass sie auf die Seite Konten zugreifen.

### <a name="physical-management"></a>Physische Verwaltung

Beim Freigeben des Geräts zwischen mehreren Benutzern gibt es einige physische Überlegungen.

- Stellen Sie sicher, dass Geräte zwischen Schichten abladen.
- Wenn ein Gerät für eine Schicht erforderlich ist und mehrere Schichten dauern muss, ziehen Sie die Verwendung eines externen Akkus zu Beginn einer Schicht in Betracht, während das Gerät weiterhin über eine erhebliche Gebühr gemäß der Verwalten von [Wärmerichtungen](hololens2-charging.md#managing-heat)verfügt.
- Wenn Sie Geräte speichern, halten Sie sie angeschlossen und mit einem Netzwerk verbunden. Dies ist die beste Möglichkeit, um Betriebssystem- und App-Updates sicherzustellen.
- Überlegen Sie, wie Sie das Gerät zwischen Benutzern [bereinigen](hololens2-maintenance.md) möchten.
- Wenn Sie für ein Gerät mit einem einzelnen freigegebenen Benutzer eine gemeinsam genutzte PIN/ein Kennwort für einen einzelnen Benutzer verwenden, legen Sie die PIN/das Kennwort nicht auf der Seite des Geräts ab.
- Verwenden Sie für mehrere Geräte mit einem einzelnen freigegebenen Benutzer verschiedene PINs/Kennwörter.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Freigeben für mehrere Personen mit jeweils einem eigenen Konto

Individuelle Azure Active Directory -Konten (Azure AD) sind der bevorzugte und sicherste Identitätsnutzungsfall für HoloLens 2 Benutzer. Wenn Sie ihre eigenen Azure AD-Konten verwenden, können mehrere Benutzer jeweils ihre eigenen Benutzereinstellungen und Benutzerdaten auf dem Gerät beibehalten. Es kann jeweils nur ein Benutzer angemeldet werden. Wenn sich ein Benutzer anmeldet, meldet HoloLens den vorherigen Benutzer ab.

Um sicherzustellen, dass mehrere Personen ihre eigenen Konten in Ihrem HoloLens verwenden können, führen Sie die folgenden Schritte aus, um sie zu konfigurieren:

1. Wenn Sie [das Gerät einrichten,](hololens2-start.md)wählen Sie **Meine Arbeit oder Schule besitzt es** aus, und melden Sie sich mit einem Azure AD Konto an.
1. Stellen Sie nach Abschluss der Einrichtung sicher, dass die Kontoeinstellungen (Einstellungen > Konten) **Andere Benutzer** enthalten.

> [!NOTE]
> Wenn Ihr Gerät nicht mit einem Azure AD-Konto eingerichtet wurde, muss es entweder [zurückgesetzt oder mit einem Schrägstrich angepasst](hololens-recovery.md) und ordnungsgemäß eingerichtet werden.

Um HoloLens zu verwenden, befolgt jeder Benutzer die folgenden Schritte:

1. Wenn ein anderer Benutzer das Gerät verwendet hat, wählen Sie eine der folgenden Optionen aus:
   - Drücken Sie einmal den Netzschalter, um in den Standbymodus zu wechseln, und drücken Sie dann erneut den Netzschalter, um zum Sperrbildschirm zurückzukehren.
   - Wählen Sie im **Startmenü** die Benutzerkachel aus, oder wählen Sie im **Power-Menü** Abmelden aus, um den aktuellen Benutzer abzu abmelden.

1. Melden Sie sich mit ihren Azure AD-Kontoanmeldeinformationen beim Gerät an.  
    - Wenn Sie das Gerät zum ersten Mal verwenden, werden Sie aufgefordert, die HoloLens an Ihre eigenen Augen zu [kalibrieren.](hololens-calibration.md)
    - Wenn Sie das Gerät zuvor verwendet haben:
        - [Windows Holographic, Version 20H2, Build 19041.1128](hololens-release-notes.md#windows-holographic-version-20h2) oder höher, passt sich die Anzeige nahtlos an die Qualität und eine komfortable Anzeige an.
        - Vorherige Builds benötigen eine manuelle Kalibrierung, um sich an Ihre Augen anzupassen.

> [!TIP]
> Wenn sich ein Benutzer noch nicht bei einem Gerät angemeldet hat, probieren Sie eine dieser beiden Methoden für eine schnellere Anmeldung aus:
>
> - **FIDO 2-Sicherheitsschlüssel:** Ihr FIDO2-Sicherheitsschlüssel wird automatisch erkannt, und der Benutzer muss seine Benutzeranmeldeinformationen nicht eingeben oder MFA verwenden. Dies ist die schnellste Methode, um sich auf einem neuen Gerät anzumelden.
> - **Webauthentifizierung:** Wenn Sie sich bei einem neuen Gerät anmelden, können Sie den Link **Von einem anderen Gerät anmelden** auswählen, der einen 9-stelligen Code generiert, den Sie bei [aka.ms/devicelogin](https://login.microsoftonline.com/common/oauth2/deviceauth) verwenden können, um sich entweder als Benutzer auf dem Gerät anzumelden, oder Ihren Benutzernamen und Ihr Kennwort zur Vereinfachung über eine Tastatur einzugeben.

Um eine Liste der Gerätebenutzer anzuzeigen oder einen Benutzer vom Gerät zu entfernen, wechseln Sie zu **Einstellungen**  >  **Konten**  >  **Andere Benutzer**.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Freigeben für mehrere Personen, die alle das gleiche Konto verwenden

Mehrere Benutzer können ein HoloLens Gerät auch freigeben, während sie ein einzelnes Benutzerkonto verwenden. Obwohl es für HoloLens Benutzer bevorzugt wird, sich mit ihren individuellen Identitäten (Azure AD Konten) beim Gerät anzumelden, ist dies in einigen Organisationen keine Option.

Es sind zwei methoden für gemeinsam genutzte Geräte verfügbar:

- **Mehrere Endbenutzer,** die ein Gerät gemeinsam nutzen: Ein HoloLens Gerät wird einem bestimmten Bereich zugeordnet, in dem jeder Mitarbeiter das Gerät verwenden kann. Beispiele hierfür sind ein cleaner Raum oder eine Suite für Diess.

- **Mehrere Endbenutzer,** die mehrere Geräte gemeinsam nutzen– HoloLens Geräte befinden sich in einem freigegebenen Speicherplatz, in dem Mitarbeiter ein beliebiges Gerät verwenden können. Beispiele hierfür sind eine Ölplattform oder ein Autohändler/Autoladen.

Wenn ein neuer Benutzer das Gerät zum ersten Mal einschaltet, während dasselbe Konto angemeldet bleibt, fordert das Gerät den Benutzer auf, die Anzeige schnell zu kalibrieren und zu personalisieren. Das Gerät speichert die Kalibrierungsinformationen, um die Qualität und den Komfort der Anzeige der einzelnen Benutzer automatisch zu optimieren. Benutzer müssen das Gerät nicht erneut kalibrieren.
