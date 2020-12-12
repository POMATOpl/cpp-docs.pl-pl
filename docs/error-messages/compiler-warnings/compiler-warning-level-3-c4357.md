---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4357'
title: Ostrzeżenie kompilatora (poziom 3) C4357
ms.date: 11/04/2016
f1_keywords:
- C4357
helpviewer_keywords:
- C4357
ms.assetid: 9259c633-3c02-4900-b94a-2d8d366d61cd
ms.openlocfilehash: 89446d131d62134c181c691d8103f75b8cdbe4a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274245"
---
# <a name="compiler-warning-level-3-c4357"></a>Ostrzeżenie kompilatora (poziom 3) C4357

argument tablicy parametrów na liście formalnych argumentów dla delegata "del" został zignorowany podczas generowania "Function"

`ParamArray`Atrybut został zignorowany i `function` nie można go wywołać za pomocą argumentów zmiennych.

Poniższy przykład generuje C4357:

```cpp
// C4357.cpp
// compile with: /clr /W3 /c
using namespace System;
public delegate void f(int i, ... array<Object^>^ varargs);   // C4357

public delegate void g(int i, array<Object^>^ varargs);   // OK
```
