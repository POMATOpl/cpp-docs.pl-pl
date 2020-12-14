---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4297'
title: Ostrzeżenie kompilatora (poziom 1) C4297
ms.date: 11/04/2016
f1_keywords:
- C4297
helpviewer_keywords:
- C4297
ms.assetid: ba92fcdc-9f70-4f60-abe6-281f9582ca59
ms.openlocfilehash: ef330302702ee9e7a8fa55128a6f1f61732552f2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311737"
---
# <a name="compiler-warning-level-1-c4297"></a>Ostrzeżenie kompilatora (poziom 1) C4297

"Function": funkcja założono, że nie zgłosić wyjątku, ale

Deklaracja funkcji zawiera specyfikator (prawdopodobnie niejawny) **`noexcept`** , pusty **`throw`** specyfikator wyjątku lub atrybut [__declspec (nothrow)](../../cpp/nothrow-cpp.md) , a definicja zawiera jedną lub więcej instrukcji [throw](../../cpp/try-throw-and-catch-statements-cpp.md) . Aby rozwiązać C4297, nie należy podejmować prób zgłaszania wyjątków w funkcjach, które są zadeklarowane `__declspec(nothrow)` `noexcept(true)` lub `throw()` . Alternatywnie, Usuń **`noexcept`** `throw()` specyfikację,, lub `__declspec(nothrow)` .

Domyślnie kompilator generuje niejawne `noexcept(true)` specyfikatory dla destruktorów zdefiniowanych przez użytkownika i funkcji dealokacji oraz specjalnych funkcji składowych generowanych przez kompilator. Jest to zgodne ze standardem ISO C++ 11. Aby zapobiec generowaniu niejawnych specyfikatorów noexcept i przywrócić kompilator do niestandardowych zachowań Visual Studio 2013, użyj opcji **/Zc: implicitNoexcept-** Compiler. Aby uzyskać więcej informacji, zobacz [/Zc: implicitNoexcept (niejawne specyfikatory wyjątków)](../../build/reference/zc-implicitnoexcept-implicit-exception-specifiers.md).

Aby uzyskać więcej informacji dotyczących specyfikacji wyjątków, zobacz [specyfikacje wyjątków (throw)](../../cpp/exception-specifications-throw-cpp.md). Ponadto zobacz [/EH (model obsługi wyjątków)](../../build/reference/eh-exception-handling-model.md) , aby uzyskać informacje na temat modyfikowania zachowania obsługi wyjątków w czasie kompilacji.

To ostrzeżenie jest również generowane dla funkcji __declspec ([dllexport](../../cpp/dllexport-dllimport.md)) oznaczonych jako extern "C", nawet jeśli są one funkcjami języka C++.

Poniższy przykład generuje C4297:

```cpp
// C4297.cpp
// compile with: /W1 /LD
void __declspec(nothrow) f1()   // declared nothrow
// try the following line instead
// void f1()
{
   throw 1;   // C4297
}
```
