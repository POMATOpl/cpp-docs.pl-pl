---
description: 'Dowiedz się więcej o: błąd kompilatora C3530'
title: Błąd kompilatora C3530
ms.date: 11/04/2016
f1_keywords:
- C3530
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
ms.openlocfilehash: 74cd9ade2805ba26c700d476c53f87ea86a3baba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315377"
---
# <a name="compiler-error-c3530"></a>Błąd kompilatora C3530

nie można łączyć instrukcji "Auto" z jakimkolwiek innym specyfikatorem typu

Specyfikator typu jest używany ze **`auto`** słowem kluczowym.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Nie używaj specyfikatora typu w deklaracji zmiennej, która używa **`auto`** słowa kluczowego.

## <a name="example"></a>Przykład

Poniższy przykład daje C3530, ponieważ zmienna `x` jest zadeklarowana ze **`auto`** słowem kluczowym i typem **`int`** , a ponieważ przykład jest kompilowany z **/Zc:** Auto.

```cpp
// C3530.cpp
// Compile with /Zc:auto
int main()
{
   auto int x;   // C3530
   return 0;
}
```

## <a name="see-also"></a>Zobacz też

[Słowo kluczowe "Autouzupełnianie"](../../cpp/auto-cpp.md)
