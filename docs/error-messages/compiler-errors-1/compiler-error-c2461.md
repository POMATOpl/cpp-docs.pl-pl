---
description: 'Dowiedz się więcej o: błąd kompilatora C2461'
title: Błąd kompilatora C2461
ms.date: 11/04/2016
f1_keywords:
- C2461
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
ms.openlocfilehash: 788c8e475bd38b829ca8426137569a5d8a083f18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341831"
---
# <a name="compiler-error-c2461"></a>Błąd kompilatora C2461

> "*Class*": w składni konstruktora brakuje parametrów formalnych

Konstruktor dla klasy nie określa żadnych formalnych parametrów. Deklaracja konstruktora musi określać formalną listę parametrów. Lista może być pusta.

Aby rozwiązać ten problem, Dodaj parę nawiasów po deklaracji *klasy**::*.*

## <a name="example"></a>Przykład

Poniższy przykład pokazuje, jak naprawić C2461:

```cpp
// C2461.cpp
// compile with: /c
class C {
   C::C;     // C2461
   C::C();   // OK
};
```
