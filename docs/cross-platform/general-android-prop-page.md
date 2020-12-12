---
description: 'Dowiedz się więcej o: ogólne właściwości projektu (Android C++)'
title: Ogólne właściwości projektu (Android C++)
ms.date: 10/23/2017
ms.assetid: 65f4868b-b864-4989-a275-1e51869ef599
f1_keywords:
- VC.Project.VCConfiguration.Android.OutputDirectory
- VC.Project.VCConfiguration.Android.IntermediateDirectory
- VC.Project.VCConfiguration.Android.TargetName
- VC.Project.VCConfiguration.Android.TargetExt
- VC.Project.VCConfiguration.Android.DeleteExtensionsOnClean
- VC.Project.VCConfiguration.Android.BuildLogFile
- VC.Project.VCConfiguration.Android.PlatformToolset
- VC.Project.VCConfiguration.Android.ConfigurationType
- VC.Project.VCConfiguration.UseOfSTL
- VC.Project.VCConfiguration.ThumbMode
ms.openlocfilehash: 84f45afad9cc36eb0fbe5b2dd1da895b3e50fcea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319238"
---
# <a name="general-project-properties-android-c"></a>Ogólne właściwości projektu (Android C++)

| Właściwość | Opis | Choices |
|--|--|--|
| Katalog wyjściowy | Określa ścieżkę względną do katalogu pliku wyjściowego; może zawierać zmienne środowiskowe. |
| Katalog pośredni | Określa ścieżkę względną do pośredniego katalogu plików; może zawierać zmienne środowiskowe. |
| Nazwa obiektu docelowego | Określa nazwę pliku, który zostanie wygenerowany przez ten projekt. |
| Rozszerzenie docelowe | Określa rozszerzenie pliku, które generuje ten projekt. (Przykład: *. exe* lub *. dll*) |
| Rozszerzenia do usunięcia podczas czyszczenia | Rozdzielana średnikami Specyfikacja symboli wieloznacznych, dla których pliki w katalogu pośrednim mają zostać usunięte podczas czyszczenia lub odbudowy. |
| Plik dziennika kompilacji | Określa plik dziennika kompilacji, w którym ma zostać zapisany wpis, gdy rejestrowanie kompilacji jest włączone. |
| Zestaw narzędzi platformy | Określa zestaw narzędzi używany do tworzenia bieżącej konfiguracji; Jeśli nie zostanie ustawiona, używany jest domyślny zestaw narzędzi |
| Typ konfiguracji | Określa typ danych wyjściowych generowanych przez tę konfigurację. | **Biblioteka dynamiczna (. so)** — Biblioteka dynamiczna (*. tak*)<br>**Biblioteka statyczna (. a)** — Biblioteka statyczna (*. a*)<br>**Narzędzia — narzędzie**<br>**Reguł programu make** — plik reguł programu make<br> |
| Docelowy poziom interfejsu API | Poziom interfejsu API NDK dla systemu Android, którego dotyczy ta konfiguracja. |
| Użycie STL | Określa, która standardowa biblioteka języka C++ ma być używana dla tej konfiguracji. | **Minimalna Biblioteka środowiska uruchomieniowego języka C++ (system)**<br>**Biblioteka statyczna środowiska uruchomieniowego języka C++ (Gabi + + _static)**<br>**Biblioteka udostępniona środowiska uruchomieniowego języka C++ (Gabi + + _shared)**<br>**Biblioteka statyczna środowiska uruchomieniowego STLport (stlport_static)**<br>**Biblioteka udostępniona środowiska uruchomieniowego STLport (stlport_shared)**<br>**Biblioteka statyczna GNU STL (gnustl_static)**<br>**Udostępniona biblioteka GNU STL (gnustl_shared)**<br>**Biblioteka statyczna LLVM libc + + (c++ _static)**<br>**Biblioteka udostępniona LLVM libc + + (c++ _shared)**<br> |
| Tryb przewijania | Generuj kod, który jest wykonywany dla mikroarchitektury przycisku przewijania. Dotyczy to tylko architektury ARM. | **Thumb**<br>**ARM**<br>**Disabled**<br> |
