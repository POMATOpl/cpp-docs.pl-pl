---
title: Ostrzeżenie kompilatora (poziom 4) C4205
ms.date: 11/04/2016
f1_keywords:
- C4205
helpviewer_keywords:
- C4205
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
ms.openlocfilehash: 6e85d4b6382f8d3811585bcf887c08694b86b71a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225270"
---
# <a name="compiler-warning-level-4-c4205"></a>Ostrzeżenie kompilatora (poziom 4) C4205

użyto niestandardowego rozszerzenia: Deklaracja statycznej funkcji w zakresie funkcji

Dzięki rozszerzeniom Microsoft (/ze) **`static`** funkcje mogą być deklarowane wewnątrz innej funkcji. Funkcja jest podanym zakresem globalnym.

## <a name="example"></a>Przykład

```c
// C4205.c
// compile with: /W4
void func1()
{
   static int func2();  // C4205
};

int main()
{
}
```

Takie inicjalizacje są nieprawidłowe pod kątem zgodności ANSI ([/za](../../build/reference/za-ze-disable-language-extensions.md)).
