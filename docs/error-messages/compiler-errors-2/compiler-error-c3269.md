---
description: 'Dowiedz się więcej o: błąd kompilatora C3269'
title: Błąd kompilatora C3269
ms.date: 11/04/2016
f1_keywords:
- C3269
helpviewer_keywords:
- C3269
ms.assetid: c575f067-244d-4dd5-bf58-9e7630ea58b7
ms.openlocfilehash: 041a0af061e4ddd1a691c396cdd15e86085124c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113703"
---
# <a name="compiler-error-c3269"></a>Błąd kompilatora C3269

"Function": Funkcja składowa typu zarządzanego lub WinRT nie może być zadeklarowana przy użyciu "..."

Funkcje składowe klasy zarządzanej i WinRT nie mogą deklarować list parametrów o zmiennej długości.

Poniższy przykład generuje C3269 i pokazuje, jak to naprawić:

```cpp
// C3269_2.cpp
// compile with: /clr

ref struct A
{
   void func(int i, ...)   // C3269
   // try the following line instead
   // void func(int i )
   {
   }
};

int main()
{
}
```
