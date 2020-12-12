---
description: 'Dowiedz się więcej o: właściwości debugera systemu Android'
title: Właściwości debugera systemu Android (C++)
ms.date: 10/23/2017
ms.assetid: 789f7a1c-38b4-41d0-809b-14f4d96c8116
f1_keywords:
- VC.Project.AndroidDebugger.DebuggerType
- VC.Project.AndroidDebugger.AndroidDeviceID
- VC.Project.AndroidDebugger.PackagePath
- VC.Project.AndroidDebugger.LaunchActivity
ms.openlocfilehash: 27068b56421860b1e77b6cacf7e2ef4fae147a24
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136529"
---
# <a name="android-debugger-properties"></a>Właściwości debugera systemu Android

| Właściwość | Opis | Choices |
|--|--|--|
| Typ debugera | Określa typ kodu do debugowania. | **Tylko natywny**<br /><br />**Tylko Java** |
| Element docelowy debugowania | Określa emulator lub urządzenie, które ma być używane na potrzeby debugowania. Jeśli nie są uruchomione żadne emulatory, użyj "Menedżera urządzeń wirtualnych systemu Android (AVD)", aby uruchomić urządzenie. |
| Pakiet do uruchomienia | Określa lokalizację elementu *. apk* , który będzie debugowany. Ta opcja uruchamia pakiet (APK), gdy aplikacja jest debugowana. |
| Działanie uruchamiania | Działanie systemu Android służące do uruchamiania aplikacji musi pasować do używanej w manifeście. Naciśnij przycisk Zastosuj, aby pobrać listę z *AndroidManifest.xml* i wypełnić ją dynamicznie. |
| Dodatkowe ścieżki wyszukiwania symboli | Dodatkowa ścieżka wyszukiwania dla symboli debugowania. |
| Dodatkowe ścieżki wyszukiwania źródła Java | Dodatkowe ścieżki wyszukiwania dla plików źródłowych Java. (Stosuje się tylko wtedy, gdy typ debugera jest tylko w języku Java). |
