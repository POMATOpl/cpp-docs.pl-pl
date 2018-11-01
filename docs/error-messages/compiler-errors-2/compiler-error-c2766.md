---
title: Błąd kompilatora C2766
ms.date: 11/04/2016
f1_keywords:
- C2766
helpviewer_keywords:
- C2766
ms.assetid: 8032f4ca-6827-4f04-9c61-c44643c85cc4
ms.openlocfilehash: 87ea9f693265080d744746c6a8014b2b8b6db13a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50446492"
---
# <a name="compiler-error-c2766"></a>Błąd kompilatora C2766

jawna specjalizacja; "specjalizacja" został już zdefiniowany

Zduplikowane jawne specjalizacje nie są dozwolone. Aby uzyskać więcej informacji, zobacz [jawna specjalizacja szablonów funkcji](../../cpp/explicit-specialization-of-function-templates.md).

Poniższy przykład spowoduje wygenerowanie C2766:

```
// C2766.cpp
// compile with: /c
template<class T>
struct A {};

template<>
struct A<int> {};

template<>
struct A<int> {};   // C2766
// try the following line instead
// struct A<char> {};
```