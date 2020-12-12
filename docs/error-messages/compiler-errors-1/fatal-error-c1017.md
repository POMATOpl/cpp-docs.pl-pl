---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1017'
title: Błąd krytyczny C1017
ms.date: 11/04/2016
f1_keywords:
- C1017
helpviewer_keywords:
- C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
ms.openlocfilehash: a36a5cb11b10ca3ecca00d0379595060918d6a45
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262389"
---
# <a name="fatal-error-c1017"></a>Błąd krytyczny C1017

nieprawidłowe wyrażenie stałej całkowitej

Wyrażenie w `#if` dyrektywie nie istnieje lub nie zostało oszacowane jako stała.

Stałe zdefiniowane przy użyciu `#define` muszą mieć wartości, które są obliczane do stałej całkowitej, jeśli są używane `#if` w `#elif` dyrektywie, lub `#else` .

Poniższy przykład generuje C1017:

```cpp
// C1017.cpp
#define CONSTANT_NAME "YES"
#if CONSTANT_NAME   // C1017
#endif
```

Możliwe rozwiązanie:

```cpp
// C1017b.cpp
// compile with: /c
#define CONSTANT_NAME 1
#if CONSTANT_NAME
#endif
```

Ponieważ `CONSTANT_NAME` program zwraca ciąg, a nie liczbę całkowitą, `#if` dyrektywa generuje błąd krytyczny C1017.

W innych przypadkach preprocesor oblicza niezdefiniowaną stałą jako zero. Może to spowodować niezamierzone wyniki, jak pokazano w poniższym przykładzie. `YES` jest niezdefiniowany, więc jego wynikiem jest zero. Wyrażenie `#if` `CONSTANT_NAME` daje w wyniku wartość false, a kod, który ma być używany, `YES` jest usuwany przez preprocesor. `NO` jest również niezdefiniowana (zero), dlatego `#elif` `CONSTANT_NAME==NO` zwraca wartość true ( `0 == 0` ), powodując, że preprocesor pozostawia kod w `#elif` części instrukcji — dokładnie odwrotnie od zamierzonego zachowania.

```cpp
// C1017c.cpp
// compile with: /c
#define CONSTANT_NAME YES
#if CONSTANT_NAME
   // Code to use on YES...
#elif CONSTANT_NAME==NO
   // Code to use on NO...
#endif
```

Aby zobaczyć dokładnie, jak kompilator obsługuje dyrektywy preprocesora, należy użyć [/p](../../build/reference/p-preprocess-to-a-file.md), [/e](../../build/reference/e-preprocess-to-stdout.md)lub [/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md).
