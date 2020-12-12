---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4839'
title: Ostrzeżenie kompilatora (poziom 3) C4839
ms.date: 09/13/2018
f1_keywords:
- C4839
helpviewer_keywords:
- C4839
ms.assetid: f4f99066-9258-4330-81a8-f4a75a1d95ee
ms.openlocfilehash: a8ae0d3e3c74c62d05163edd981679e5390fb184
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332061"
---
# <a name="compiler-warning-level-3-c4839"></a>Ostrzeżenie kompilatora (poziom 3) C4839

> niestandardowe użycie klasy "*Type*" jako argumentu funkcji wariadyczne

Klasy lub struktury, które są przenoszone do funkcji wariadyczne, takie jak, `printf` muszą być w sposób prosty skopiowane. Podczas przekazywania takich obiektów kompilator po prostu wykonuje kopię bitową i nie wywołuje konstruktora ani destruktora.

To ostrzeżenie jest dostępne począwszy od programu Visual Studio 2017.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4839:

```cpp
// C4839.cpp
// compile by using: cl /EHsc /W3 C4839.cpp
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function
                        // note: the constructor and destructor will not be called;
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function
}
```

Aby poprawić błąd, można wywołać funkcję członkowską, która zwraca typ z możliwością kopiowania,

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

W przypadku ciągów skompilowanych i zarządzanych przy użyciu `CStringW` , dostarczone, `operator LPCWSTR()` powinno być używane do rzutowania `CStringW` obiektu na wskaźnik C oczekiwany przez ciąg formatu.

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```
