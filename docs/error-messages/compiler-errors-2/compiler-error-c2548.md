---
description: 'Dowiedz się więcej o: błąd kompilatora C2548'
title: Błąd kompilatora C2548
ms.date: 11/04/2016
f1_keywords:
- C2548
helpviewer_keywords:
- C2548
ms.assetid: 01e9c835-9bf3-4020-9295-5ee448c519f3
ms.openlocfilehash: cf7686191199ec1d0b5c515138f15f2fbf85efa8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204111"
---
# <a name="compiler-error-c2548"></a>Błąd kompilatora C2548

"Class:: member": Brak domyślnego parametru dla parametru parametru

Brak parametru w liście parametrów domyślnych. W przypadku podania domyślnego parametru w dowolnym miejscu listy parametrów należy zdefiniować domyślne parametry dla wszystkich kolejnych parametrów.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2548:

```cpp
// C2548.cpp
// compile with: /c
void func( int = 1, int, int = 3);  // C2548

// OK
void func2( int, int, int = 3);
void func3( int, int = 2, int = 3);
```
