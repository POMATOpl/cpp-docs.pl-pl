---
title: Compiler Error C2548
ms.date: 11/04/2016
f1_keywords:
- C2548
helpviewer_keywords:
- C2548
ms.assetid: 01e9c835-9bf3-4020-9295-5ee448c519f3
ms.openlocfilehash: 2c680d86a0ea69d67f9e53a481f2f096f4cc7878
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353472"
---
# <a name="compiler-error-c2548"></a>Compiler Error C2548

"class::member": Brak domyślnego parametru dla parametru parametru

Brak parametru w liście parametrów domyślnych. Jeśli podasz domyślnego parametru w dowolnym miejscu na liście parametrów, należy zdefiniować parametry domyślne dla wszystkich kolejnych parametrów.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C2548:

```
// C2548.cpp
// compile with: /c
void func( int = 1, int, int = 3);  // C2548

// OK
void func2( int, int, int = 3);
void func3( int, int = 2, int = 3);
```