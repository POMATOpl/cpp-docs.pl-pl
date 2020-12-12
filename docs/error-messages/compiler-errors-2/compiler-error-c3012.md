---
description: 'Dowiedz się więcej o: błąd kompilatora C3012'
title: Błąd kompilatora C3012
ms.date: 11/04/2016
f1_keywords:
- C3012
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
ms.openlocfilehash: fff986a984acb62f770d02ff2b7b08c40e8511e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286010"
---
# <a name="compiler-error-c3012"></a>Błąd kompilatora C3012

> "*wewnętrzna*": wewnętrzna funkcja nie jest dozwolona bezpośrednio w ramach równoległego regionu

Funkcja [wewnętrzna kompilatora](../../intrinsics/compiler-intrinsics.md) nie jest dozwolona w `omp parallel` regionie. Aby rozwiązać ten problem, Przenieś wewnętrzne elementy z regionu lub zastąp je odpowiednikami niewewnętrznym.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3012 i pokazuje jeden ze sposobów rozwiązania tego problemu:

```cpp
// C3012.cpp
// compile with: /openmp
#ifdef __cplusplus
extern "C" {
#endif
void* _ReturnAddress();
#ifdef __cplusplus
}
#endif

int main()
{
   #pragma omp parallel
   {
      _ReturnAddress();   // C3012
   }
   _ReturnAddress();      // OK
}
```
