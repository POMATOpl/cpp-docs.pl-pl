---
description: 'Dowiedz się więcej o programie: uruchamianie i kończenie działania programu C++'
title: Uruchamianie i kończenie działania programu C++
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Standard Library, program startup and termination
- terminating execution
- Function Main procedures
- control text streams
- startup code, and C++ program termination
- main function, program startup
ms.assetid: f72c8f76-f507-4ddd-a270-7b60f4fed625
ms.openlocfilehash: 644be6d4392f8e41b1d1cf7d45b484ed9903d463
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324790"
---
# <a name="c-program-startup-and-termination"></a>Uruchamianie i kończenie działania programu C++

Program w języku C++ wykonuje te same operacje co program C w trakcie uruchamiania programu i po zakończeniu działania programu oraz kilka bardziej opisanych tutaj.

Przed wywołaniem funkcji przez środowisko docelowe `main` i po przechowywaniu wszystkich stałych wartości początkowych określonych we wszystkich obiektach, które mają statyczny czas trwania, program wykonuje wszystkie pozostałe konstruktory dla takich obiektów statycznych. Kolejność wykonywania nie jest określona między jednostkami tłumaczenia, ale można jednak założyć, że niektóre obiekty [iostreams](../standard-library/iostreams-conventions.md) są prawidłowo zainicjowane do użytku przez te konstruktory statyczne. Te strumienie tekstu kontrolki są następujące:

- [CIN](../standard-library/iostream.md#cin) — dla standardowych danych wejściowych.

- [cout](../standard-library/iostream.md#cout) — dla wyjścia standardowego.

- [cerr](../standard-library/iostream.md#cerr) — w przypadku niebuforowanego wyjścia błędu standardowego.

- [CLOG](../standard-library/iostream.md#clog) — dla buforowanych standardowych danych wyjściowych błędu.

Można również użyć tych obiektów w destruktorach wywoływanych dla obiektów statycznych podczas kończenia działania programu.

Podobnie jak w przypadku języka C, zwracanie z `main` lub wywołania `exit` wywołań wszystkie funkcje zarejestrowane `atexit` w odwrotnej kolejności rejestru. Zgłoszono wyjątek z takich zarejestrowanych wywołań funkcji `terminate` .

## <a name="see-also"></a>Zobacz też

[Omówienie standardowej biblioteki języka C++](../standard-library/cpp-standard-library-overview.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
