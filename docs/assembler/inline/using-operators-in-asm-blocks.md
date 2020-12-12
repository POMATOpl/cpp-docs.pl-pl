---
description: 'Dowiedz się więcej o: Używanie operatorów w blokach __asm'
title: Używanie operatorów w blokach __asm
ms.date: 08/30/2018
helpviewer_keywords:
- brackets [ ]
- brackets [ ], __asm blocks
- __asm keyword [C++], operators
- square brackets [ ], __asm blocks
- operators [C++], using in __asm blocks
- square brackets [ ]
ms.assetid: a26ccfd4-40ae-4a61-952f-c417982aa8dd
ms.openlocfilehash: 266d840e6cb407d45c1d3a49bed6a2390e52aa2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97121852"
---
# <a name="using-operators-in-__asm-blocks"></a>Używanie operatorów w blokach __asm

**Specyficzne dla firmy Microsoft**

**`__asm`** Blok nie może używać operatorów określonych w języku C lub C++, takich jak **<<** operator. Jednak operatory udostępnione przez C i MASM, takie jak \* operator, są interpretowane jako operatory języka asemblera. Na przykład, poza **`__asm`** blokiem, nawiasy kwadratowe (**[]**) są interpretowane jako otaczające indeksy tablicy, które są automatycznie skalowane do rozmiaru elementu w tablicy. Wewnątrz **`__asm`** bloku są one widoczne jako operator MASM index, który powoduje przesunięcie nieskalowanego bajtu z dowolnego obiektu danych lub etykiety (nie tylko tablica). Poniższy kod ilustruje różnicę:

```cpp
int array[10];

__asm mov array[6], bx ;  Store BX at array+6 (not scaled)

array[6] = 0;         /* Store 0 at array+24 (scaled) */
```

Pierwsze odwołanie do `array` nie jest skalowane, ale drugi —. Należy pamiętać, że można użyć operatora **typu** , aby osiągnąć skalowanie na podstawie stałej. Na przykład następujące instrukcje są równoważne:

```cpp
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24

array[6] = 0;                   /* Store 0 at array + 24 */
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Używanie C lub C++ w blokach __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>
