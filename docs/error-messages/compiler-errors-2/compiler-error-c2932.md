---
title: Błąd kompilatora C2932 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2932
dev_langs:
- C++
helpviewer_keywords:
- C2932
ms.assetid: c28e88d9-e654-4367-bfb4-13c780bca9bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48c7655703774661ef6a5586f83a05e79585ce9f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043004"
---
# <a name="compiler-error-c2932"></a>Błąd kompilatora C2932

"class": typ klasy identyfikator ponownie definiowana jako składowa danych klasy 'Identyfikator'

Generyczny lub szablonu klasy nie można użyć jako element członkowski danych.

Poniższy przykład spowoduje wygenerowanie C2932:

```
// C2932.cpp
// compile with: /c
template<class T>
struct TC {};

struct MyStruct {
   int TC<int>;   // C2932
   int TC;   // OK
};
```

C2932 może również wystąpić, gdy za pomocą typów ogólnych:

```
// C2932b.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};

struct MyStruct {
   int GC<int>;   // C2932
   int GC;   // OK
};
```