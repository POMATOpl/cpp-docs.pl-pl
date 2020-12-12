---
description: 'Dowiedz się więcej o: błąd kompilatora C2603'
title: Błąd kompilatora C2603
ms.date: 11/04/2016
f1_keywords:
- C2603
helpviewer_keywords:
- C2603
ms.assetid: 9ca520d0-f082-4b65-933d-17c3bcf8b02c
ms.openlocfilehash: e28ea581c4c1417972cddc0ce558bd518acb8889
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208791"
---
# <a name="compiler-error-c2603"></a>Błąd kompilatora C2603

> "*Function*": zbyt wiele statycznych obiektów w zakresie bloku z konstruktorem/destruktorami w funkcji

W wersjach kompilatora Microsoft C++ przed Visual Studio 2015 lub w przypadku wybrania opcji [/Zc: threadSafeInit-](../../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) Compiler obowiązuje limit 31 dla liczby statycznych obiektów, które mogą znajdować się w widocznej zewnętrznie funkcji wbudowanej.

Aby rozwiązać ten problem, zalecamy wdrożenie nowszej wersji zestawu narzędzi kompilatora języka Microsoft C++ lub, jeśli to możliwe, należy usunąć opcję/Zc: threadSafeInit-Compiler. Jeśli nie jest to możliwe, należy rozważyć połączenie obiektów statycznych. Jeśli obiekty są tego samego typu, rozważ użycie pojedynczej statycznej tablicy tego typu i odwołuje się do poszczególnych elementów członkowskich zgodnie z potrzebami.

## <a name="example"></a>Przykład

Poniższy kod generuje C2603 i pokazuje jeden ze sposobów rozwiązania tego problemu:

```cpp
// C2603.cpp
// Compile by using: cl /W4 /c /Zc:threadSafeInit- C2603.cpp
struct C { C() {} };
extern inline void f1() {
    static C C01, C02, C03, C04, C05, C06, C07, C08, C09, C10;
    static C C11, C12, C13, C14, C15, C16, C17, C18, C19, C20;
    static C C21, C22, C23, C24, C25, C26, C27, C28, C29, C30, C31;
    static C C32;   // C2603 Comment this line out to avoid error
}
```
