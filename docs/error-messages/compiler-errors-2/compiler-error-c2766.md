---
description: 'Dowiedz się więcej o: błąd kompilatora C2766'
title: Błąd kompilatora C2766
ms.date: 11/04/2016
f1_keywords:
- C2766
helpviewer_keywords:
- C2766
ms.assetid: 8032f4ca-6827-4f04-9c61-c44643c85cc4
ms.openlocfilehash: bace06c6dc4392fa023317d9711005837d156aa2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239496"
---
# <a name="compiler-error-c2766"></a>Błąd kompilatora C2766

Jawna specjalizacja; "specjalizacja" została już zdefiniowana

Zduplikowane jawne specjalizacje są niedozwolone. Aby uzyskać więcej informacji, zobacz [Jawna specjalizacja szablonów funkcji](../../cpp/explicit-specialization-of-function-templates.md).

Poniższy przykład generuje C2766:

```cpp
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
