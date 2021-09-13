---
title: 'HoloLens 2: Akku und Ladevorgang'
description: Hier erfahren Sie, wie Sie Ihre HoloLens aufladen und externe Akkusets verwenden.
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: b4692468942da88877370864eda2ce173cc499af
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034349"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2: Akku und Ladevorgang

Auf dieser Seite finden Sie Details zum Laden der HoloLens 2 und zum Verwenden externer Akkusets.

## <a name="charging-the-device"></a>Aufladen des Geräts

Verwenden Sie das [Ladegerät und das USB Type-C-Kabel](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1), das mit der HoloLens 2 geliefert wurde, da dies die beste Möglichkeit zum Laden Ihres Geräts ist. Das in HoloLens 2 enthaltene Ladegerät bietet bis zu 9 V bei 2 A (18W). Mit dem mitgelieferten Wandladegerät können HoloLens 2 Geräte den Akku in weniger als 65 Minuten voll aufladen, wenn sich das Gerät im Standby-Modus befindet. Wenn das Zubehör nicht verfügbar ist, vergewissern Sie sich, dass das verfügbare Ladegerät mindestens 15 W Leistung unterstützt.

> [!NOTE]
> Vermeiden Sie nach Möglichkeit die Verwendung eines PCs, um das Gerät über USB zu laden, was sehr langsam ist.

## <a name="checking-the-battery-charge-level"></a>Überprüfen des Akkustands
Wenn das Gerät korrekt hochgefahren und läuft, gibt es drei verschiedene Möglichkeiten, den Akkustand zu überprüfen:

- Über das Hauptmenü der Benutzeroberfläche des HoloLens-Geräts.
- Sehen Sie sich die LEDs in der Nähe des Netzschalters an (bei 40 % Akkustand sollten mindestens zwei LEDs leuchten).
    - Während des Ladevorgangs leuchtet die Akkuanzeige auf, um den aktuellen Ladezustand anzuzeigen.  Die letzte Anzeige leuchtet auf und erlischt, um den aktiven Ladevorgang anzuzeigen.
    - Wenn Ihre HoloLens eingeschaltet ist, zeigt die Akkuanzeige den Akkustand in fünf Stufen an.
    - Wenn nur eine der fünf LEDs leuchtet, ist der Akkustand unter 20 %.
    - Wenn der Akkuladestand kritisch niedrig ist und Sie versuchen, das Gerät einzuschalten, blinkt eine LED kurz und erlischt anschließend.
- Öffnen Sie auf Ihrem Host-PC den **Datei-Explorer** und suchen Sie auf der linken Seite unter **Dieser PC** nach Ihrem HoloLens 2 Gerät. Klicken Sie mit der rechten Maustaste auf das Gerät und wählen Sie **Eigenschaften** aus. Ein Dialogfeld mit dem Akkustand wird angezeigt.

   ![Ein Bildschirm mit den HoloLens 2-Eigenschaften zeigt den Akkustand.](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Spezifikationen für alternatives Laden

Die HoloLens 2 können von [USB-Stromversorgung](https://www.usb.org/usb-charger-pd)quellen bis zu 27 Watt geladen werden. Wenn die Quelle mindestens 10 Watt bereitstellen kann, kann die HoloLens Betriebszeit verlängert werden (bei einigen Workloads möglicherweise auf unbestimmte Zeit). 

> [!NOTE]
> Durch die Verwendung eines USB-A-auf-USB-C-Ladekabels wird die Ladung auf 7,5 Watt beschränkt. Die Betriebszeit wird immer noch verlängert, aber nicht so lange, wie bei der Verwendung von USB-C auf C.

Wenn sich die HoloLens im Standby-Modus befindet, reichen 18 Watt aus, um die maximale Laderate für den internen Akku zu erreichen. Wenn die HoloLens verwendet wird, kann der Laderate reduziert sein, da die HoloLens den Betrieb gegenüber des Ladevorgangs priorisiert.

> [!IMPORTANT]
> Es wird empfohlen, HoloLens 2 mindestens mit 5 V/1,5 A geladen wird. Es sollten keine Ladegeräte verwendet werden, die nicht mindestens 5 V/1,5 A bereitstellen können. 

### <a name="external-battery-packs"></a>Externe Akkusets

Akkusets, die den oben genannten Spezifikationen entsprechen, können mit der HoloLens 2 verwendet werden. Beachten Sie jedoch, dass einige USB-C-Akkusets die Stromversorgung über den gleichen USB-C-Anschluss bereitstellen und aufladen. Es ist wichtig, dass diese Akkusets [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) implementieren, um sicherzustellen, dass die HoloLens davon laden und nicht von ihr geladen werden. 

### <a name="managing-heat"></a>Erwärmungsmanagement

Wie bei jedem Gerät generiert das Laden der HoloLens Wärme. Je schneller der Ladevorgang, desto mehr Wärme wird generiert. Außerdem erzeugt das Starten bei einem niedrigeren Akkustand mehr Wärme als das Starten, wenn der Akku geladen ist. Kunden, die HoloLens in heißen Umgebungen über einen längeren Zeitraum betreiben müssen, können die folgenden Verfahren verwenden:

- Es ist in Ordnung, die HoloLens 2 auch dann mit einer externen Stromquelle zu verbinden, wenn der interne Akku vollständig geladen ist.
- Wenn ein externer Akku aufgebraucht ist, wird die HoloLens weiterhin mit seinem internen Akku betrieben.    
- Wenn die Wärme, nachdem Sie die obigen Schritte ausgeführt haben, weiterhin ein Problem ist, erwägen Sie die Verwendung eines Ladegeräts oder Akkusets, das den Ladevorgang auf 1,5 A beschränkt. Beachten Sie, dass diese Option nicht so viel Betriebszeit bereitstellt, da sich der interne Akku trotzdem langsam entlädt.

## <a name="troubleshooting"></a>Problembehandlung


### <a name="hololens-charges-external-battery"></a>HoloLens Ladevorgang für externe Akkus
Wenn HoloLens 2 einen externen Akku lädt, anstatt von ihm geladen zu werden, deutet dies darauf hin, dass der Akku [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) nicht implementiert. Der Wechsel zu einem neueren Akkuset ist die empfohlene Methode, um dieses Problem zu beheben. Alternativ können Sie jedoch versuchen, auf ein USB-A-zu-USB-C-Kabel zu wechseln. Beachten Sie, dass dadurch die Ladeleistung auf 7,5 Watt beschränkt wird.
