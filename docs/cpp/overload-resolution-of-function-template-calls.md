---
title: Rozpoznawanie przeciążenia wywołań szablonów funkcji
ms.date: 11/04/2016
helpviewer_keywords:
- function templates overload resolution
ms.assetid: a2918748-2cbb-4fc6-a176-e256f120bee4
ms.openlocfilehash: 7b7e374328b6d234426d8263e4c6655191133700
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008894"
---
# <a name="overload-resolution-of-function-template-calls"></a>Rozpoznawanie przeciążenia wywołań szablonów funkcji

Szablon funkcji może przeciążać nieszablonowe funkcje o tej samej nazwie. W tym scenariuszu wywołania funkcji są rozwiązywane przez pierwsze użycie odliczania argumentu szablonu w celu utworzenia wystąpienia szablonu funkcji z unikatową specjalizacją. Jeśli potrącenie argumentu szablonu nie powiedzie się, inne przeciążenia funkcji są brane pod uwagę w celu rozpoznania wywołania. Te inne przeciążenia, znane także jako zestaw kandydatów, obejmują funkcje nieszablonowe i inne szablony funkcji z utworzonymi wystąpieniami. Jeśli potrącenie argumentu szablonu powiedzie się, wygenerowana funkcja jest porównywana z innymi funkcjami w celu określenia najlepszego dopasowania, zgodnie z regułami dotyczącymi rozpoznawania przeciążenia. Aby uzyskać więcej informacji, zobacz [przeciążanie funkcji](function-overloading.md).

## <a name="example-choose-a-nontemplate-function"></a>Przykład: wybierz funkcję nieszablonu

Jeśli funkcja niebędąca szablonem jest równie dobre dopasowanie do funkcji szablonu, wybierana jest funkcja niebędąca szablonem (chyba że argumenty szablonu zostały jawnie określone), jak w wywołaniu `f(1, 1)` w poniższym przykładzie.

```cpp
// template_name_resolution9.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

void f(int, int) { cout << "f(int, int)" << endl; }
void f(char, char) { cout << "f(char, char)" << endl; }

template <class T1, class T2>
void f(T1, T2)
{
   cout << "void f(T1, T2)" << endl;
};

int main()
{
   f(1, 1);   // Equally good match; choose the nontemplate function.
   f('a', 1); // Chooses the template function.
   f<int, int>(2, 2);  // Template arguments explicitly specified.
}
```

```Output
f(int, int)
void f(T1, T2)
void f(T1, T2)
```

## <a name="example-exact-match-template-function-preferred"></a>Przykład: preferowana funkcja szablonu dokładnego dopasowania

W następnym przykładzie pokazano, że preferowana jest dokładna funkcja szablonu, jeśli funkcja niebędąca szablonem wymaga konwersji.

```cpp
// template_name_resolution10.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

void f(int, int) { cout << "f(int, int)" << endl; }

template <class T1, class T2>
void f(T1, T2)
{
   cout << "void f(T1, T2)" << endl;
};

int main()
{
   long l = 0;
   int i = 0;
   // Call the template function f(long, int) because f(int, int)
   // would require a conversion from long to int.
   f(l, i);
}
```

```Output
void f(T1, T2)
```

## <a name="see-also"></a>Zobacz też

[Rozpoznawanie nazw](../cpp/templates-and-name-resolution.md)<br/>
[typename](../cpp/typename.md)
