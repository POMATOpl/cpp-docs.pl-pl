---
title: '`__restrict`'
description: Opisuje `__restrict` słowo kluczowe Microsoft Visual C++.
ms.date: 11/6/2020
f1_keywords:
- __restrict_cpp
- __restrict
- _restrict
helpviewer_keywords:
- __restrict keyword [C++]
ms.openlocfilehash: f23574f49712928e0095f29a3b88b0c05b185eab
ms.sourcegitcommit: 3f0c1dcdcce25865d1a1022bcc5b9eec79f69025
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/09/2020
ms.locfileid: "94381574"
---
# `__restrict`

Podobnie jak modyfikator **`__declspec` ( [`restrict`](../cpp/restrict.md) )** , **`__restrict`** słowo kluczowe (dwa wiodące znaki podkreślenia "_") wskazuje, że symbol nie jest aliasem w bieżącym zakresie. **`__restrict`** Słowo kluczowe różni się od `__declspec (restrict)` modyfikatora w następujący sposób:

- **`__restrict`** Słowo kluczowe jest prawidłowe tylko dla zmiennych i `__declspec (restrict)` jest prawidłowe tylko w deklaracjach i definicjach funkcji.

- **`__restrict`** jest podobna do języka [`restrict`](../c-language/type-qualifiers.md#restrict) C, począwszy od C99, ale **`__restrict`** może być używany w programach C++ i C.

- Gdy **`__restrict`** jest używany, kompilator nie propaguje właściwości No-alias zmiennej. Oznacza to, że jeśli zmienna zostanie przypisana **`__restrict`** do **`__restrict`** niezmiennej, kompilator nadal zezwoli na aliasowanie zmiennej nie__restrictj. Różni się to od zachowania słowa kluczowego C99 języka C **`restrict`** .

Ogólnie rzecz biorąc, jeśli chcesz mieć wpływ na zachowanie całej funkcji, użyj **`__declspec (restrict)`** zamiast słowa kluczowego.

W celu zapewnienia zgodności z poprzednimi wersjami, **`_restrict`** jest synonimem, **`__restrict`** Jeśli opcja kompilatora [ `/Za` \( disable rozszerzenia języka](../build/reference/za-ze-disable-language-extensions.md) nie jest określona.

W programie Visual Studio 2015 i nowszych **`__restrict`** można używać odwołań do języka C++.

> [!NOTE]
> W przypadku użycia na zmiennej, która ma także [`volatile`](../cpp/volatile-cpp.md) słowo kluczowe, **`volatile`** pierwszeństwo ma.

## <a name="example"></a>Przykład

```cpp
// __restrict_keyword.c
// compile with: /LD
// In the following function, declare a and b as disjoint arrays
// but do not have same assurance for c and d.
void sum2(int n, int * __restrict a, int * __restrict b,
          int * c, int * d) {
   int i;
   for (i = 0; i < n; i++) {
      a[i] = b[i] + c[i];
      c[i] = b[i] + d[i];
    }
}

// By marking union members as __restrict, tell compiler that
// only z.x or z.y will be accessed in any given scope.
union z {
   int * __restrict x;
   double * __restrict y;
};
```

## <a name="see-also"></a>Zobacz także

[Słowa kluczowe](../cpp/keywords-cpp.md)
