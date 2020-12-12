---
description: 'Dowiedz się więcej o: błąd kompilatora C2675'
title: Błąd kompilatora C2675
ms.date: 11/04/2016
f1_keywords:
- C2675
helpviewer_keywords:
- C2675
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
ms.openlocfilehash: 71d52a8da09861078811757ad7af7c757e418e5c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282032"
---
# <a name="compiler-error-c2675"></a>Błąd kompilatora C2675

jednoargumentowy "operator": "Type" nie definiuje tego operatora lub konwersji do typu akceptowalnego dla wstępnie zdefiniowanego operatora

C2675 może również wystąpić podczas używania operatora jednoargumentowego, a typ nie definiuje operatora lub konwersji do typu akceptowalnego dla wstępnie zdefiniowanego operatora. Aby użyć operatora, należy przeciążyć go dla określonego typu lub zdefiniować konwersję do typu, dla którego zdefiniowano operator.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2675.

```cpp
// C2675.cpp
struct C {
   C(){}
} c;

struct D {
   D(){}
   void operator-(){}
} d;

int main() {
   -c;   // C2675
   -d;   // OK
}
```
