---
description: 'Dowiedz się więcej o: błąd kompilatora C3394'
title: Błąd kompilatora C3394
ms.date: 11/04/2016
f1_keywords:
- C3394
helpviewer_keywords:
- C3394
ms.assetid: 4e025d79-27ba-43c8-b0d9-839ecef98126
ms.openlocfilehash: ea805ef8ff9bf6e19498135ae6fcd9ba7e3ff9e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313362"
---
# <a name="compiler-error-c3394"></a>Błąd kompilatora C3394

Błąd składniowy w klauzuli ograniczenia: znaleziono element "identifier" Oczekiwano typu

Ograniczenie zostało źle sformułowane.  Aby uzyskać więcej informacji, zobacz [ograniczenia dotyczące parametrów typu ogólnego (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3394:

```cpp
// C3394.cpp
// compile with: /clr /c
ref class MyClass {};
ref class R {
   generic<typename T>
   where T : static   // C3394
   // try the following line instead
   // where T : MyClass
   void f() {}
};
```
