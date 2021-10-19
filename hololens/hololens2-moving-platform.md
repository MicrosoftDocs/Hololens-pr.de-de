---
title: HoloLens 2-Modus für bewegliche Plattformen
description: Verwenden von HoloLens auf beweglichen Plattformen
keywords: Bewegliche Plattformen, dynamische Bewegung, HoloLens, Modus für bewegliche Plattformen
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 10/12/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 7c636cd97e31c74d4976e71ec3f41ac5afe5bdcc
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924427"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Modus für bewegliche Plattformen auf beweglichen Plattformen mit geringer dynamischer Bewegung

In [Windows Holographic, Version 21H2](hololens-release-notes.md#windows-holographic-version-21h2) haben wir in HoloLens 2 Betaunterstützung für die Nachverfolgung auf beweglichen Plattformen mit geringer dynamischer Bewegung hinzugefügt. Nachdem Sie den Build installiert und den Modus für bewegliche Plattformen aktiviert haben, können Sie Ihre HoloLens 2 in bis dahin unzugänglichen Umgebungen verwenden, z. B. auf großen Schiffen und Wasserfahrzeugen. Derzeit ist das Feature nur auf die Unterstützung dieser spezifischen beweglichen Plattformen ausgerichtet. Zwar hindert Sie nichts daran, die Verwendung des Features in anderen Umgebungen zu versuchen, der Schwerpunkt bei diesem Feature liegt aber zuerst bei der hinzugefügten Unterstützung für diese Umgebungen.

![Beispiel für bewegliche Plattformen.](./images/mpm-compare.gif)

In diesem Artikel wird Folgendes behandelt:

1. [Darum sind bewegliche Plattformen erforderlich](#why-moving-platform-mode-is-necessary)
1. [Aktivieren des Modus für bewegliche Plattformen](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Darum ist der Modus für bewegliche Plattformen erforderlich

HoloLens muss in der Lage sein, Ihre Kopfposition mit [6 Freiheitsgraden](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) (X, Y, Z, Verschiebung sowie Roll-, Nick- und Gierrotation) nachzuverfolgen, um stabile Hologramme darzustellen. Zu diesem Zweck verfolgt HoloLens zwei ähnliche Informationen aus zwei separaten Quellen nach:

1. **Kameras für sichtbares Licht.** Diese Kameras verfolgen die Umgebung nach, z. B. den physischen Raum, in dem Sie die HoloLens verwenden
1. **Trägheitsmesseinheit (Inertial Measurement Unit, IMU).** Die Trägheitsmesseinheit besteht aus einem Beschleunigungsmesser, Gyroskop und Magnetometer und verfolgt Ihre Kopfbewegung und -ausrichtung relativ zur Erde

Informationen aus diesen beiden Quellen werden zusammengesetzt, um Ihre Kopfposition mit einer geringen Latenz und ausreichend hohen Frequenz nachzuverfolgen, um Hologramme reibungslos zu rendern.

Dieser Ansatz basiert jedoch auf einer kritischen Annahme: Die Umgebung (von den Kameras nachverfolgt) bleibt relativ zur Erde (für die die IMU Messungen durchführen kann) unbewegt. Wenn dies nicht der Fall ist, wie bei einem Schiff im Wasser, können die Informationen aus beiden Quellen miteinander in Konflikt stehen und dazu führen, dass der Tracker die Orientierung verliert. Dieser Konflikt erzeugt falsche Positionsinformationen und führt zu „schwimmenden“ Hologrammen oder sogar dem Verlust der Nachverfolgung.

Der Modus für bewegliche Plattformen behebt dieses Problem. Wenn Sie den Modus für bewegliche Plattformen aktivieren, ist dies ein Hinweis an unseren Tracker, dass wir uns nicht darauf verlassen können, dass unsere Sensoreingaben jederzeit vollständig zueinander kongruent sind. Stattdessen müssen wir uns stärker auf die visuelle Nachverfolgung verlassen, um inkongruente Bewegungsdaten aus der Massenmessung schnell erkennen und herausfiltern zu können, bevor wir die IMU-Eingaben verwenden können.

## <a name="supported-environments-and-known-limitations"></a>Unterstützte Umgebungen und bekannte Einschränkungen

Der Modus für bewegliche Plattformen wurde zwar entwickelt, um Konfliktfälle bei den Massenträgheits- und visuellen Daten intelligent zu behandeln, ist aber derzeit auf den Bereich großer Wasserfahrzeuge ausgelegt, die geringe dynamische Bewegungsabläufe erfahren. Das bedeutet, dass es fraglos Einschränkungen und nicht unterstützte Szenarien gibt.

### <a name="known-limitations"></a>Bekannte Einschränkungen

- Die einzigen unterstützten Umgebungen für den Modus für bewegliche Plattformen (Moving Platform Mode, MPM) sind große Wasserfahrzeuge, die geringen dynamischen Bewegungen ausgesetzt sind. Anders ausgedrückt: Viele allgemeine Umgebungen/Situationen werden aufgrund der hohen Frequenz ihrer Bewegungen und des hohen Beschleunigungs- und [Ruckniveaus](https://en.wikipedia.org/wiki/Jerk_(physics)) noch **nicht** unterstützt. Beispiele: Flugzeuge, Züge, Autos, Fahrräder, Busse, kleine Boote, Aufzüge usw.
- Hologramme können bei aktiviertem MPM leicht schwanken, insbesondere bei bewegter See.
- Nichts hindert Benutzer daran, MPM in nicht unterstützten Umgebungen auszuprobieren. Jedoch können die Benutzer unerwünschten Nebenwirkungen ausgesetzt sein, wenn das Gerät in der Lage ist, die Nachverfolgung im nicht unterstützten Bereich aufrecht zu erhalten. Beispielsweise können Benutzer feststellen, dass sich HoloLens 2 mit MPM in einem Aufzug beim Wechsel von Stockwerken verwenden lässt, was zuvor nicht möglich war. Unglücklicherweise ermöglicht MPM dem Gerät zwar, die Nachverfolgung aufrecht zu erhalten, es verarbeitet aber zurzeit die Kartenverwaltung nicht. Benutzer werden feststellen, dass der Wechsel von Stockwerken in einem Aufzug dazu führt, dass das Gerät die oberen und unteren Stockwerke verwechselt und die Kartenqualität beeinträchtigt ist.

## <a name="prerequisites"></a>Voraussetzungen

Die Betaunterstützung für den Modus für bewegliche Plattformen erfordert nur einige wenige Voraussetzungen:

1. Installieren Sie [Windows Holographic, Version 21H2](hololens-release-notes.md#windows-holographic-version-21h2) oder höher, indem Sie den [neuesten Build](https://aka.ms/hololens2download)[über ARC](hololens-recovery.md#clean-reflash-the-device)aktualisieren oder flashen.

2. Aktivieren Sie den [Entwicklermodus und das Geräteportal](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).

## <a name="enabling-moving-platform-mode"></a>Aktivieren des Modus für bewegliche Plattformen

Zum Aktivieren des Modus für bewegliche Plattformen [aktivieren Sie das Geräteportal](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).

1. Wählen Sie im Menü auf der linken Seite **System** aus

   ![Erste Abbildung.](.\images\mpm-01.png)

2. Wählen Sie die Seite **Moving Platform Mode** (Modus für bewegliche Plattformen) aus, und aktivieren Sie das Kontrollkästchen **Moving Platform Mode**

    ![Zweite Abbildung.](.\images\mpm-02.png)

3. Wenn Ihnen eine Warnung angezeigt wird, wählen Sie **OK** aus.

   ![Dritte Abbildung.](.\images\mpm-03.png)

4. Starten Sie Ihr Gerät neu. Dies kann entweder über das Menü **Ein/Aus** oben rechts im Geräteportal oder durch Ausführen des folgenden Sprachbefehls &quot;Gerät neu starten&quot; und Auswahl von &quot;Ja&quot; erfolgen.

   ![Vierte Abbildung.](.\images\mpm-04.png)

Wenn die Option für den Modus für bewegliche Plattformen im Geräteportal nicht angezeigt wird, bedeutet dies wahrscheinlich, dass Sie nicht den richtigen Build ausführen. Weitere Informationen finden Sie im Abschnitt [Voraussetzungen](#prerequisites).

## <a name="reporting-issues"></a>Melden von Problemen

Wie bereits erwähnt, ist dieses Feature eine Betafunktion, die nur im Entwicklermodus verfügbar ist. Dies bedeutet, dass Probleme auftreten können. Gehen Sie in diesem Fall wie folgt vor, damit wir das Problem untersuchen und das Produkt verbessern können:

1. Melden Sie das Problem über den [Feedback-Hub](hololens-feedback.md) unter der Kategorie **Hologram accuracy, stability, and reliability** (Genauigkeit, Stabilität und Zuverlässigkeit von Hologrammen), und schließen Sie Folgendes ein:
    1. Eine Beschreibung des Problems, einschließlich des erwarteten Verhaltens und des aufgetretenen Verhaltens
    1. Eine Mixed Reality-[Videoaufnahme](holographic-photos-and-videos.md#capture-a-mixed-reality-video) des Problems
2.  Öffnen Sie eine Supportanfrage bei [https://aka.ms/hlsupport](https://aka.ms/hlsupport), und teilen Sie die Feedback-Hub-URL, damit wir uns an Sie wenden können, falls Anschlussfragen auftreten