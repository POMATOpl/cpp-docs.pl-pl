---
description: 'Dowiedz się więcej o: błąd kompilatora C3163'
title: Błąd kompilatora C3163
ms.date: 11/04/2016
f1_keywords:
- C3163
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
ms.openlocfilehash: 53d0135e3083de7727b2a6c7f51a3f75e7314405
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203955"
---
# <a name="compiler-error-c3163"></a>Błąd kompilatora C3163

> "*konstrukcja*": atrybuty niespójne z poprzednią deklaracją

Atrybuty, które są stosowane do definicji, powodują konflikt z atrybutami, które są stosowane do deklaracji.

Jednym ze sposobów na rozwiązanie C3163 jest wyeliminowanie atrybutów deklaracji do przodu. Wszelkie atrybuty deklaracji przesyłania dalej powinny być mniejsze niż atrybuty w definicji lub, w większości, równe.

Możliwa przyczyna błędu C3163 dotyczy języka adnotacji kodu źródłowego firmy Microsoft (SAL). Makra SAL nie rozszerzają się, chyba że kompilujesz projekt przy użyciu **`/analyze`** flagi. Program, który w sposób czysty kompiluje, bez zgłaszania **`/analyze`** C3163, jeśli spróbujesz ponownie skompilować go przy użyciu **`/analyze`** opcji. Aby uzyskać więcej informacji na temat SAL, zobacz [Adnotacje sal](../../c-runtime-library/sal-annotations.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3163.

```cpp
// C3163.cpp
// compile with: /clr /c
using namespace System;

[CLSCompliant(true)] void f();
[CLSCompliant(false)] void f() {}   // C3163
// try the following line instead
// [CLSCompliant(true)] void f() {}
```

## <a name="see-also"></a>Zobacz też

[Adnotacje SAL](../../c-runtime-library/sal-annotations.md)
