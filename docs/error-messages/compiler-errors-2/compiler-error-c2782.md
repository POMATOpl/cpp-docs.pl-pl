---
title: Błąd kompilatora C2782 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2782
dev_langs:
- C++
helpviewer_keywords:
- C2782
ms.assetid: 8b685422-294d-4f64-9f3d-c14eaf03a93d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01d6b5abebb765642046f2ad6e9d5f342af8e3d4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037765"
---
# <a name="compiler-error-c2782"></a>Błąd kompilatora C2782

"deklaracją": parametr szablonu 'Identyfikator' jest niejednoznaczny

Kompilator nie może określić typu argumentu szablonu.

Poniższy przykład spowoduje wygenerowanie C2782:

```
// C2782.cpp
template<typename T>
void f(T, T) {}

int main() {
   f(1, 'c');   // C2782
   // try the following line instead
   // f<int>(1, 'c');
}
```

C2782 może również wystąpić, gdy za pomocą typów ogólnych:

```
// C2782b.cpp
// compile with: /clr
generic<typename T> void gf(T, T) { }

int main() {
   gf(1, 'c'); // C2782
   // try the following line instead
   // gf<int>(1, 'c');
}
```