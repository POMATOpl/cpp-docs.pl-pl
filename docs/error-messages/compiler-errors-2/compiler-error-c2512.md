---
description: 'Dowiedz się więcej o: błąd kompilatora C2512'
title: Błąd kompilatora C2512
ms.date: 02/09/2018
f1_keywords:
- C2512
helpviewer_keywords:
- C2512
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
ms.openlocfilehash: 40574ab7fc54ba678729429401ed14fefefe9ebd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212912"
---
# <a name="compiler-error-c2512"></a>Błąd kompilatora C2512

> "*Identyfikator*": Brak dostępnego odpowiedniego domyślnego konstruktora

*Konstruktor domyślny*, Konstruktor, który nie wymaga argumentów, nie jest dostępny dla określonej klasy, struktury lub związku. Kompilator dostarcza konstruktora domyślnego tylko wtedy, gdy nie podano żadnych konstruktorów zdefiniowanych przez użytkownika.

W przypadku podania konstruktora, który przyjmuje parametr inny niż void i chcesz zezwolić na tworzenie klasy bez parametrów (na przykład jako elementy tablicy), należy również dostarczyć konstruktora domyślnego. Konstruktor domyślny może być konstruktorem z wartościami domyślnymi dla wszystkich parametrów.

## <a name="example"></a>Przykład

Typową przyczyną błędu C2512 jest Definiowanie klasy lub konstruktora struktury, który przyjmuje argumenty, a następnie próbuje zadeklarować wystąpienie klasy lub struktury bez żadnych argumentów. Na przykład `struct B` poniżej deklaruje konstruktora, który wymaga `char *` argumentu, ale nie, który nie przyjmuje argumentów. W programie `main` wystąpienie B jest zadeklarowane, ale nie podano żadnego argumentu. Kompilator generuje C2512, ponieważ nie może znaleźć domyślnego konstruktora dla B.

```cpp
// C2512.cpp
// Compile with: cl /W4 c2512.cpp
// C2512 expected
struct B {
   B (char *) {}
   // Uncomment the following line to fix.
   // B() {}
};

int main() {
   B b;   // C2512 - This requires a default constructor
}
```

Ten problem można rozwiązać przez zdefiniowanie domyślnego konstruktora dla danej struktury lub klasy, takiej jak `B() {}` lub konstruktora, gdzie wszystkie argumenty mają wartości domyślne, takie jak `B (char * = nullptr) {}` .
