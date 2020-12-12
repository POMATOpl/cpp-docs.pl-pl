---
description: 'Dowiedz się więcej o: zrozumieniu funkcji pomocnika'
title: Ogólne informacje funkcji Pomocnik
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, helper function
- __delayLoadHelper2 function
- delayimp.lib
- __delayLoadHelper function
- delayhlp.cpp
- delayimp.h
- helper functions
ms.assetid: 6279c12c-d908-4967-b0b3-cabfc3e91d3d
ms.openlocfilehash: d47e392d78d6cf872af28b992885c57d34bddf0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247101"
---
# <a name="understanding-the-helper-function"></a>Ogólne informacje funkcji Pomocnik

Funkcja pomocnika dla z opóźnionym załadowaniem obsługiwana przez konsolidatora to rzeczywista zawartość biblioteki DLL w czasie wykonywania. Można zmodyfikować funkcję pomocnika, aby dostosować jej zachowanie, pisząc własną funkcję i łącząc ją z programem zamiast korzystać z dostarczonej funkcji pomocnika w Delayimp. lib. Jedna funkcja pomocnika obsługuje wszystkie biblioteki DLL, które są ładowane z opóźnieniem.

Możesz udostępnić własną wersję funkcji pomocnika, jeśli chcesz przeprowadzić konkretne przetwarzanie na podstawie nazw bibliotek DLL lub importów.

Funkcja pomocnik wykonuje następujące czynności:

- Sprawdza przechowywane dojście do biblioteki, aby sprawdzić, czy zostało już załadowane

- Wywołuje metodę **LoadLibrary** w celu próby ZAŁADOWANIA biblioteki DLL

- Wywołuje metodę **GetProcAddress** w celu uzyskania adresu procedury

- Powraca do opóźnionego importowania thunk ładowania, aby wywołać teraz załadowany punkt wejścia

Funkcja pomocnika może wywoływać z powrotem do punktu zaczepienia powiadomienia w programie po każdej z następujących akcji:

- Po uruchomieniu funkcji pomocnika

- Tuż przed wywołaniem funkcji **LoadLibrary** jest wywoływana w funkcjach pomocnika

- Tuż przed wywołaniem **GetProcAddress** w funkcji pomocnika

- Jeśli wywołanie metody **LoadLibrary** w funkcji pomocnika nie powiodło się

- Jeśli wywołanie **GetProcAddress** w funkcji pomocnika nie powiodło się

- Po zakończeniu przetwarzania funkcji pomocnika

Każdy z tych punktów zaczepienia może zwrócić wartość, która będzie zmieniać normalne przetwarzanie procedury pomocnika, z wyjątkiem powrotu do thunk obciążenia importu.

Domyślny kod pomocnika można znaleźć w Delayhlp. cpp i Delayimp. h (w vc\include) i jest kompilowany w Delayimp. lib (w vc\lib). Musisz dołączyć tę bibliotekę do kompilacji, chyba że napiszesz własną funkcję pomocnika.

W poniższych tematach opisano funkcję pomocnika:

- [Zmiany w funkcji pomocnika opóźnionego ładowania bibliotek DLL od Visual C++ 6,0](changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)

- [Konwencje wywoływania, parametry i zwracany typ](calling-conventions-parameters-and-return-type.md)

- [Struktura i definicje stałe](structure-and-constant-definitions.md)

- [Obliczanie niezbędnych wartości](calculating-necessary-values.md)

- [Zwalnianie Delay-Loaded DLL](explicitly-unloading-a-delay-loaded-dll.md)

## <a name="see-also"></a>Zobacz też

[Obsługa konsolidatora dla Delay-Loaded bibliotek DLL](linker-support-for-delay-loaded-dlls.md)
