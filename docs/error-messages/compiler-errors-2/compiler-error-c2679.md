---
description: 'Dowiedz się więcej o: błąd kompilatora C2679'
title: Błąd kompilatora C2679
ms.date: 11/04/2016
f1_keywords:
- C2679
helpviewer_keywords:
- C2679
ms.assetid: 1a5f9d00-9190-4aa6-bc72-949f68ec136f
ms.openlocfilehash: 3e2df2e54e729d2242bdc95a062f6c5dcf74f19d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177448"
---
# <a name="compiler-error-c2679"></a>Błąd kompilatora C2679

Binary "operator": nie znaleziono żadnego operatora, który pobiera operand z prawej strony typu "Type" (lub nie istnieje akceptowalna konwersja)

Aby użyć operatora, należy przeciążyć go dla określonego typu lub zdefiniować konwersję do typu, dla którego zdefiniowano operator.

Poniższy przykład generuje C2679:

```cpp
// C2679.cpp
class C {
public:
   C();   // no constructor with an int argument
} c;

class D {
public:
   D(int) {}
   D(){}
} d;

int main() {
   c = 10;   // C2679
   d = 10;   // OK
}
```
