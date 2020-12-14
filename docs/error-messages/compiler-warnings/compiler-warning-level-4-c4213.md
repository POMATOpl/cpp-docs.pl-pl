---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4213'
title: Ostrzeżenie kompilatora (poziom 4) C4213
ms.date: 11/04/2016
f1_keywords:
- C4213
helpviewer_keywords:
- C4213
ms.assetid: 59fc3f61-ebd2-499e-99d7-f57bec11eda1
ms.openlocfilehash: 400cd650542bfd7a71640947467e8340f63bb3df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297346"
---
# <a name="compiler-warning-level-4-c4213"></a>Ostrzeżenie kompilatora (poziom 4) C4213

użyto niestandardowego rozszerzenia: Rzutowanie na wartość l

Przy użyciu domyślnych rozszerzeń Microsoft (/ze) można użyć rzutowania po lewej stronie instrukcji przypisania.

## <a name="example"></a>Przykład

```c
// C4213.c
// compile with: /W4
void *a;
void f()
{
   int   i[3];
   a = &i;
   *(( int * )a )++ = 3;  // C4213
}

int main()
{
}
```

Takie Rzutowanie jest nieprawidłowe pod kątem zgodności ze standardem ANSI ([/za](../../build/reference/za-ze-disable-language-extensions.md)).
