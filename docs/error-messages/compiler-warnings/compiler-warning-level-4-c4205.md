---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4205'
title: Ostrzeżenie kompilatora (poziom 4) C4205
ms.date: 11/04/2016
f1_keywords:
- C4205
helpviewer_keywords:
- C4205
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
ms.openlocfilehash: d4a9250ad84f45a9e2ce40e6f103904ce7f8722e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173236"
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
