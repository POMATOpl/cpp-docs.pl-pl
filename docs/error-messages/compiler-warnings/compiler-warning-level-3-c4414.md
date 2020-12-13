---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4414'
title: Ostrzeżenie kompilatora (poziom 3) C4414
ms.date: 11/04/2016
f1_keywords:
- C4414
helpviewer_keywords:
- C4414
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
ms.openlocfilehash: c753852d40a044e99b91aa8a5976811aab52c5ab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177175"
---
# <a name="compiler-warning-level-3-c4414"></a>Ostrzeżenie kompilatora (poziom 3) C4414

"Function": Krótki przeskok do funkcji konwertowanej na blisko

Krótkie uskoki generują kompaktową instrukcję, która oddziałuje do adresu w ograniczonym zakresie od instrukcji. Instrukcja zawiera krótkie przesunięcie, które reprezentuje odległość między skokiem a adresem docelowym, definicję funkcji. Podczas łączenia funkcji można przenieść lub przyczynić się do optymalizacji w czasie konsolidacji, która powoduje, że funkcja jest przenoszona z zakresu dostępnego od krótkiego przesunięcia. Kompilator musi generować specjalny rekord dla skoku, który wymaga, aby instrukcja element JMP była niemal lub bliska. Kompilator wykonał konwersję.

Na przykład poniższy kod generuje C4414:

```cpp
// C4414.cpp
// compile with: /W3 /c
// processor: x86
int DoParityEven();
int DoParityOdd();
unsigned char global;
int __declspec(naked) DoParityEither()
{
   __asm
   {
      test global,0
      jpe SHORT DoParityEven  // C4414
      jmp SHORT DoParityOdd   // C4414
   }
}
```
