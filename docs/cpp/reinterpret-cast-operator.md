---
description: 'Dowiedz się więcej na temat: reinterpret_cast — operator'
title: Operator reinterpret_cast
ms.date: 11/04/2016
f1_keywords:
- reinterpret_cast_cpp
helpviewer_keywords:
- reinterpret_cast keyword [C++]
ms.assetid: eb3283c7-7f88-467e-affd-407d37b46d6c
ms.openlocfilehash: 71b7067321c5af1e81311f7ce036c735c96193d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252444"
---
# <a name="reinterpret_cast-operator"></a>Operator reinterpret_cast

Zezwala na konwersję dowolnego wskaźnika do dowolnego innego typu wskaźnika. Umożliwia także konwersję dowolnego typu całkowitego na dowolny typ wskaźnika i na odwrót.

## <a name="syntax"></a>Składnia

```
reinterpret_cast < type-id > ( expression )
```

## <a name="remarks"></a>Uwagi

Nieprawidłowe użycie **`reinterpret_cast`** operatora może być niebezpieczne. Chyba że żądana konwersja jest z natury niskiego poziomu, należy użyć jednego z innych operatorów rzutowania.

**`reinterpret_cast`** Operatora można używać do konwersji, takich jak **`char*`** do **`int*`** , lub `One_class*` do `Unrelated_class*` , które są niebezpieczne.

Wynik typu **`reinterpret_cast`** nie może być bezpiecznie używany dla niczego innego niż rzutowanie na jego oryginalny typ. Inne zastosowania są, w największej, nieportowe.

**`reinterpret_cast`** Operator nie może rzutować **`const`** atrybutów, **`volatile`** , ani **`__unaligned`** . Aby uzyskać informacje na temat usuwania tych atrybutów, zobacz [Operator const_cast](../cpp/const-cast-operator.md) .

**`reinterpret_cast`** Operator konwertuje wartość wskaźnika o wartości null na wartość wskaźnika o wartości null typu docelowego.

Jednym z praktycznych metod użycia **`reinterpret_cast`** jest funkcja mieszania, która mapuje wartość na indeks w taki sposób, że dwa różne wartości rzadko kończą się tym samym indeksem.

```cpp
#include <iostream>
using namespace std;

// Returns a hash code based on an address
unsigned short Hash( void *p ) {
   unsigned int val = reinterpret_cast<unsigned int>( p );
   return ( unsigned short )( val ^ (val >> 16));
}

using namespace std;
int main() {
   int a[20];
   for ( int i = 0; i < 20; i++ )
      cout << Hash( a + i ) << endl;
}

Output:
64641
64645
64889
64893
64881
64885
64873
64877
64865
64869
64857
64861
64849
64853
64841
64845
64833
64837
64825
64829
```

**`reinterpret_cast`** Umożliwia przetraktowanie wskaźnika jako typu całkowitego. Następnie wynik jest bitowy i XORed, aby utworzyć unikatowy indeks (unikatowy dla wysokiego prawdopodobieństwa). Indeks jest następnie obcinany przez standardowe Rzutowanie w stylu C do zwracanego typu funkcji.

## <a name="see-also"></a>Zobacz też

[Operatory rzutowania](../cpp/casting-operators.md)<br/>
[Słowa kluczowe](../cpp/keywords-cpp.md)
