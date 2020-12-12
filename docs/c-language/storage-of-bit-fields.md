---
description: 'Dowiedz się więcej o: przechowywanie pól bitowych'
title: Magazynowanie pól bitowych
ms.date: 11/04/2016
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
ms.openlocfilehash: 43066fe648bc380a8278168f336ebcf10cbbbdf5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205307"
---
# <a name="storage-of-bit-fields"></a>Magazynowanie pól bitowych

**3.5.2.1 ANSI** Kolejność alokacji pól bitowych w ramach int

Pola bitowe są przypisywane w postaci liczby całkowitej od najmniej znaczącej do najbardziej znaczącego bitu. W poniższym kodzie

```
struct mybitfields
{
   unsigned a : 4;
   unsigned b : 5;
   unsigned c : 7;
} test;

int main( void )
{
   test.a = 2;
   test.b = 31;
   test.c = 0;
}
```

bity można rozmieścić w następujący sposób:

```
00000001 11110010
cccccccb bbbbaaaa
```

Ponieważ procesory 80x86 przechowują niską liczbę wartości całkowitych przed bajtem, liczba całkowita 0x01F2 powyżej byłaby przechowywana w pamięci fizycznej jako 0xF2, a po nim 0x01.

## <a name="see-also"></a>Zobacz też

[Struktury, złożenia, wyliczenia i pola bitowe](../c-language/structures-unions-enumerations-and-bit-fields.md)
