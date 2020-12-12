---
description: 'Dowiedz się więcej o: błąd kompilatora C2432'
title: Błąd kompilatora C2432
ms.date: 11/04/2016
f1_keywords:
- C2432
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
ms.openlocfilehash: 392108e0fd16952bc8bcf43682dc163c664171ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190019"
---
# <a name="compiler-error-c2432"></a>Błąd kompilatora C2432

niedozwolone odwołanie do 16-bitowych danych w "identyfikatorze"

Rejestr 16-bitowy jest używany jako indeks lub rejestr podstawowy. Kompilator nie obsługuje przywołujących się do 16-bitowych danych. rejestry 16-bitowe nie mogą być używane jako indeksy ani rejestry bazowe podczas kompilowania kodu 32-bitowego.

Poniższy przykład generuje C2432:

```cpp
// C2432.cpp
// processor: x86
int main() {
   _asm mov eax, DWORD PTR [bx]   // C2432
}
```
