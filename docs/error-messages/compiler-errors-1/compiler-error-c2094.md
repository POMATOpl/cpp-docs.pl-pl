---
description: 'Dowiedz się więcej o: błąd kompilatora C2094'
title: Błąd kompilatora C2094
ms.date: 11/04/2016
f1_keywords:
- C2094
helpviewer_keywords:
- C2094
ms.assetid: 9e4f8f88-f189-46e7-91c9-481bacc7af87
ms.openlocfilehash: 35f67da3259b93eb4ef280d45c8e364df07e9889
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251833"
---
# <a name="compiler-error-c2094"></a>Błąd kompilatora C2094

etykieta "identifier" była niezdefiniowana

Etykieta użyta przez instrukcję [goto](../../cpp/goto-statement-cpp.md) nie istnieje w funkcji.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2094:

```cpp
// C2094.c
int main() {
   goto test;
}   // C2094
```

Możliwe rozwiązanie:

```cpp
// C2094b.c
int main() {
   goto test;
   test:
   {
   }
}
```
