---
description: 'Dowiedz się więcej o: E. zachowania zdefiniowane w implementacji w OpenMP C/C++'
title: E. Zachowania zdefiniowane w implementacji w programie OpenMP C/C++
ms.date: 01/22/2019
ms.assetid: b8d660ca-9bb3-4b6b-87af-45c67d43a731
ms.openlocfilehash: e8ebc8a336578a888ff8a7152552d4381a9d5add
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342481"
---
# <a name="e-implementation-defined-behaviors-in-openmp-cc"></a>E. Zachowania zdefiniowane w implementacji w programie OpenMP C/C++

Ten dodatek zawiera podsumowanie zachowań, które są opisane jako "zdefiniowane w implementacji" w tym interfejsie API.  Każde zachowanie jest odwołujące się do opisu w głównej specyfikacji.

## <a name="remarks"></a>Uwagi

Implementacja jest wymagana do zdefiniowania i udokumentowania zachowania w takich przypadkach, ale ta lista może być niekompletna.

- **Liczba wątków:** Jeśli zostanie wykryty region równoległy, gdy dynamiczne dopasowanie liczby wątków jest wyłączone, a liczba wątków żądana dla regionu równoległego jest większa niż liczba, którą system w czasie wykonywania może dostarczyć, zachowanie programu jest zdefiniowane przez implementację (zobacz stronę 9).

   W Visual C++ dla niezagnieżdżonego regionu równoległego zostanie podana 64 wątków (wartość maksymalna).

- **Liczba procesorów:** Liczba procesorów fizycznych, w których faktycznie hostuje wątki w danym momencie, jest definiowana przez implementację (zobacz stronę 10).

   W Visual C++ ta liczba nie jest stała i jest kontrolowana przez system operacyjny.

- **Tworzenie zespołów wątków:** Liczba wątków w zespole, które wykonują zagnieżdżony region równoległy, jest definiowana przez implementację (zobacz stronę 10).

   W Visual C++ ten numer jest określany przez system operacyjny.

- **harmonogram (środowisko uruchomieniowe):** Decyzja o planowaniu jest odroczona do czasu uruchomienia. Typ harmonogramu i rozmiar fragmentu można wybrać w czasie wykonywania przez ustawienie `OMP_SCHEDULE` zmiennej środowiskowej. Jeśli ta zmienna środowiskowa nie jest ustawiona, wynikający z nich harmonogram jest zdefiniowany przez implementację (zobacz stronę 13).

   W Visual C++ typ harmonogramu nie ma `static` rozmiaru fragmentu.

- **Domyślne planowanie:** W przypadku braku klauzuli Schedule domyślny harmonogram jest zdefiniowany przez implementację (zobacz stronę 13).

   W Visual C++ domyślny typ harmonogramu `static` nie ma rozmiaru fragmentu.

- **Niepodzielny:** Jest definiowana przez implementację, czy implementacja zastępuje wszystkie `atomic` dyrektywy dyrektywami `critical` , które mają taką samą unikatową nazwę (zobacz stronę 20).

   W Visual C++, jeśli dane zmodyfikowane przez [niepodzielność](reference/openmp-directives.md#atomic) nie są na naturalnym wyrównaniu lub jeśli jest to jeden lub dwa bajty, wszystkie operacje niepodzielne, które spełniają tę właściwość, będą używały jednej sekcji krytycznej. W przeciwnym razie sekcje krytyczne nie będą używane.

- **[omp_get_num_threads](3-run-time-library-functions.md#312-omp_get_num_threads-function):** Jeśli liczba wątków nie została jawnie ustawiona przez użytkownika, wartością domyślną jest zdefiniowana implementacja (zobacz stronę 9).

   W Visual C++ domyślna liczba wątków jest równa liczbie procesorów.

- **[omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function):** Wartość domyślna dla korekty wątku dynamicznego jest definiowana przez implementację.

   W Visual C++ wartość domyślna to `FALSE` .

- **[omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function):** Gdy włączona jest zagnieżdżona równoległość, liczba wątków używanych do wykonywania zagnieżdżonych regionów równoległych jest definiowana przez implementację.

   W Visual C++ liczba wątków jest określana przez system operacyjny.

- [OMP_SCHEDULE](4-environment-variables.md#41-omp_schedule) zmienna środowiskowa: wartość domyślna dla tej zmiennej środowiskowej jest zdefiniowana przez implementację.

   W Visual C++ typ harmonogramu nie ma `static` rozmiaru fragmentu.

- [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads) zmienna środowiskowa: Jeśli nie określono żadnej wartości dla `OMP_NUM_THREADS` zmiennej środowiskowej lub jeśli określona wartość nie jest dodatnią liczbą całkowitą lub jeśli wartość jest większa niż maksymalna liczba wątków obsługiwanych przez system, liczba wątków do użycia jest zdefiniowana przez implementację.

   W Visual C++, jeśli określona wartość wynosi zero lub mniej, liczba wątków jest równa liczbie procesorów.  Jeśli wartość jest większa niż 64, liczba wątków wynosi 64.

- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic) zmienna środowiskowa: wartość domyślna to zdefiniowana przez implementację.

   W Visual C++ wartość domyślna to `FALSE` .
