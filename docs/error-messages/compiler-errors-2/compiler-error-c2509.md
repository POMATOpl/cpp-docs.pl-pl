---
description: 'Dowiedz się więcej o: błąd kompilatora C2509'
title: Błąd kompilatora C2509
ms.date: 11/04/2016
f1_keywords:
- C2509
helpviewer_keywords:
- C2509
ms.assetid: 339c1fcd-ec4a-456c-9f18-a9b24d9921af
ms.openlocfilehash: d7b6c2f05aaf525bee9572cd921d1fdffe1b0cf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212964"
---
# <a name="compiler-error-c2509"></a>Błąd kompilatora C2509

"Identyfikator": funkcja członkowska nie została zadeklarowana w elemencie "Class"

Funkcja nie jest zadeklarowana w określonej klasie.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2509.

```cpp
// C2509.cpp
// compile with: /c
struct A {
   virtual int vfunc() = 0;
   virtual int vfunc2() = 0;
};

struct B : private A {
   using A::vfunc;
   virtual int vfunc2();
};

int B::vfunc() { return 1; }   // C2509
int B::vfunc2() { return 1; }   // OK
```
