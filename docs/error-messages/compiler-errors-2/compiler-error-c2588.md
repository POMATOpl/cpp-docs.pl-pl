---
description: 'Dowiedz się więcej o: błąd kompilatora C2588'
title: Błąd kompilatora C2588
ms.date: 11/04/2016
f1_keywords:
- C2588
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
ms.openlocfilehash: 7f723f826a5d4e609c0766c5287a0fffdee72d18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177578"
---
# <a name="compiler-error-c2588"></a>Błąd kompilatora C2588

":: ~ Identyfikator": niedozwolony destruktor globalny

Destruktor jest zdefiniowany dla elementu innego niż Klasa, struktura lub Unia. Jest to niedozwolone.

Ten błąd może być spowodowany brakującą klasą, strukturą lub nazwą Unii po lewej stronie operatora rozpoznawania zakresu ( `::` ).

Poniższy przykład generuje C2588:

```cpp
// C2588.cpp
~F();   // C2588
```
