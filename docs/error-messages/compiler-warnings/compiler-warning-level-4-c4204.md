---
title: Ostrzeżenie kompilatora (poziom 4) C4204
ms.date: 11/04/2016
f1_keywords:
- C4204
helpviewer_keywords:
- C4204
ms.assetid: 298d2880-6737-448e-b711-15572d540200
ms.openlocfilehash: ecbe8bddd3f868070470555e79608ac1ecce380a
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541672"
---
# <a name="compiler-warning-level-4-c4204"></a>Ostrzeżenie kompilatora (poziom 4) C4204

użyto niestandardowego rozszerzenia: inicjator agregacji niestałej

Za pomocą rozszerzeń Microsoft (/ze) można inicjować typy agregacji (tablice, struktury, Unii i klasy) z wartościami, które nie są stałymi.

## <a name="example"></a>Przykład

```c
// C4204.c
// compile with: /W4
int func1()
{
   return 0;
}
struct S1
{
   int i;
};

int main()
{
   struct S1 s1 = { func1() };   // C4204
   return s1.i;
}
```

Takie inicjalizacje są nieprawidłowe pod kątem zgodności ANSI ([/za](../../build/reference/za-ze-disable-language-extensions.md)).