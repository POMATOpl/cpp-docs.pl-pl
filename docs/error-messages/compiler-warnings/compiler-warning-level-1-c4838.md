---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4838'
title: Ostrzeżenie kompilatora (poziom 1) C4838
ms.date: 11/04/2016
f1_keywords:
- C4838
helpviewer_keywords:
- C4838
ms.assetid: fea07924-5feb-4ed4-99b5-1a8c41d28db6
ms.openlocfilehash: 2676ef05934ee3c5e6afbf6df8d6d7a306db68ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197963"
---
# <a name="compiler-warning-level-1-c4838"></a>Ostrzeżenie kompilatora (poziom 1) C4838

Konwersja z "type_1" na "type_2" wymaga konwersji z zawężaniem

Znaleziono niejawną konwersję zawężaną podczas korzystania z inicjalizacji agregacji lub listy.

Język C umożliwia niejawne zawężanie konwersji w przypisaniach i inicjalizacji, a w języku C++ występuje kolor, nawet jeśli nieoczekiwane Zawężanie jest przyczyną wystąpienia wielu błędów kodu. Aby zapewnić bezpieczniejsze użycie kodu, w standardzie C++ wymagany jest komunikat diagnostyczny, gdy na liście inicjalizacji występuje konwersja z zawężaniem. W Visual C++ Diagnostyka jest [błędem kompilatora C2397](../../error-messages/compiler-errors-1/compiler-error-c2397.md) w przypadku korzystania ze składni jednolitej inicjalizacji obsługiwanej w programie Visual Studio 2015. Kompilator generuje ostrzeżenie C4838, gdy używana jest składnia inicjalizacji listy lub agregacji obsługiwanej przez Visual Studio 2013.

Zawężanie konwersji może być odpowiednie, gdy wiadomo, że możliwy zakres przekonwertowanych wartości może pasować do obiektu docelowego. W takim przypadku wiadomo, że masz więcej niż kompilator. W przypadku zamierzonego zawężania konwersji należy zapewnić jawne użycie rzutowania statycznego. W przeciwnym razie ten komunikat ostrzegawczy prawie zawsze wskazuje, że w kodzie znajduje się błąd. Możesz rozwiązać ten problem, upewniając się, że inicjowane obiekty mają wystarczająco duże typy, aby obsłużyć dane wejściowe.

Poniższy przykład generuje C4838 i pokazuje jeden ze sposobów rozwiązania tego problemu:

```cpp
// C4838.cpp -- C++ narrowing conversion diagnostics
// Compile by using: cl /EHsc C4838.cpp

struct S1 {
    int m1;
    double m2, m3;
};

void function_C4838(double d1) {
    double ad[] = { 1, d1 }; // OK
    int ai[] = { 1, d1 };    // warning C4838
    S1 s11 = { 1, 2, d1 };   // OK
    S1 s12 { d1, 2, 3 };     // warning C4838
    S1 s13 { static_cast<int>(d1), 2, 3 }; // possible fix for C4838
}
```
