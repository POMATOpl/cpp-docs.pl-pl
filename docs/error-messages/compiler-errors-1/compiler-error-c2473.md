---
description: 'Dowiedz się więcej o: błąd kompilatora C2473'
title: Błąd kompilatora C2473
ms.date: 11/04/2016
f1_keywords:
- C2473
helpviewer_keywords:
- C2473
ms.assetid: 6bb7dbf5-b198-490f-860e-fd64d0c2a284
ms.openlocfilehash: c81e1329e17c03b3bd8f857d2f8ceddcc1a9f264
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164461"
---
# <a name="compiler-error-c2473"></a>Błąd kompilatora C2473

"Identyfikator": wygląda jak definicja funkcji, ale nie ma listy parametrów.

Kompilator wykrył, co wyglądało jak funkcja, bez listy parametrów.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2473.

```cpp
// C2473.cpp
// compile with: /clr /c
class A {
   int i {}   // C2473
};

class B {
   int i() {}   // OK
};
```
