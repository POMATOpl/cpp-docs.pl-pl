---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4840'
title: Ostrzeżenie kompilatora (poziom 4) C4840
ms.date: 09/13/2018
f1_keywords:
- C4840
helpviewer_keywords:
- C4840
ms.openlocfilehash: a365dc38aff1ab9811407924f7f6e554d91c6f1e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330464"
---
# <a name="compiler-warning-level-4-c4840"></a>Ostrzeżenie kompilatora (poziom 4) C4840

> nieprzenośne użycie klasy "*Type*" jako argumentu funkcji wariadyczne

## <a name="remarks"></a>Uwagi

Klasy lub struktury, które są przenoszone do funkcji wariadyczne, muszą być proste do skopiowania. Podczas przekazywania takich obiektów kompilator po prostu wykonuje kopię bitową i nie wywołuje konstruktora ani destruktora.

To ostrzeżenie jest dostępne począwszy od programu Visual Studio 2017.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4840 i pokazuje, jak to naprawić:

```cpp
// C4840.cpp
// compile by using: cl /EHsc /W4 C4840.cpp
#include <stdio.h>

int main()
{
    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);

    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                       // as an argument to a variadic function
    // To correct the error, you can perform a static cast
    // to convert the object before passing it:
    printf("%i\n", static_cast<int>(s));
}
```

W przypadku ciągów skompilowanych i zarządzanych przy użyciu `CStringW` , dostarczone, `operator LPCWSTR()` powinno być używane do rzutowania `CStringW` obiektu na wskaźnik ciągu w stylu C oczekiwany przez ciąg formatu:

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```
