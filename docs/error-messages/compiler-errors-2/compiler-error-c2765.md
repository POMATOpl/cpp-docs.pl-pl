---
description: 'Dowiedz się więcej o: błąd kompilatora C2765'
title: Błąd kompilatora C2765
ms.date: 11/04/2016
f1_keywords:
- C2765
helpviewer_keywords:
- C2765
ms.assetid: 47ad86f3-a7e0-47ad-85ff-0f5534458cb9
ms.openlocfilehash: 496f28645dddc0ac426716cc80ee0d6760042ad7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239548"
---
# <a name="compiler-error-c2765"></a>Błąd kompilatora C2765

"Function": Jawna specjalizacja szablonu funkcji nie może mieć żadnych argumentów domyślnych

Argumenty domyślne są niedozwolone w jawnej specjalizacji szablonu funkcji. Aby uzyskać więcej informacji, zobacz [Jawna specjalizacja szablonów funkcji](../../cpp/explicit-specialization-of-function-templates.md).

Poniższy przykład generuje C2765:

```cpp
// C2765.cpp
template<class T> void f(T t) {};

template<> void f<char>(char c = 'a') {}   // C2765
// try the following line instead
// template<> void f<char>(char c) {}
```
