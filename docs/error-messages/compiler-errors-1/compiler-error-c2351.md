---
description: 'Dowiedz się więcej o: błąd kompilatora C2351'
title: Błąd kompilatora C2351
ms.date: 11/04/2016
f1_keywords:
- C2351
helpviewer_keywords:
- C2351
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
ms.openlocfilehash: ae8cf10cff4a345ee067519d250210f72e6690f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145486"
---
# <a name="compiler-error-c2351"></a>Błąd kompilatora C2351

przestarzała składnia inicjalizacji konstruktora C++

Na liście inicjalizacji nowego stylu dla konstruktora należy jawnie nazwać każdą bezpośrednią klasę bazową, nawet jeśli jest jedyną klasą bazową.

Poniższy przykład generuje C2351:

```cpp
// C2351.cpp
// compile with: /c
class B {
public:
   B() : () {}   // C2351
   B() {}   // OK
};
```
