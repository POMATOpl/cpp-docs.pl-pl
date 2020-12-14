---
description: 'Dowiedz się więcej o: błąd kompilatora C3646'
title: Błąd kompilatora C3646
ms.date: 06/14/2018
f1_keywords:
- C3646
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
ms.openlocfilehash: 0c6f731a09612e6c128756de8d0690c922047e49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203786"
---
# <a name="compiler-error-c3646"></a>Błąd kompilatora C3646

> "specyfikator": nieznany specyfikator przesłonięcia

## <a name="remarks"></a>Uwagi

Kompilator znalazł token w pozycji, gdzie oczekiwano, aby znaleźć specyfikator przesłonięcia, ale token nie został rozpoznany przez kompilator.

Na przykład jeśli nierozpoznany *specyfikator* jest **_NOEXCEPT**, zastąp go słowem kluczowym **`noexcept`** .

Aby uzyskać więcej informacji, zobacz [specyfikatory przesłonięć](../../extensions/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3646 i przedstawia sposób jego rozwiązania:

```cpp
// C3646.cpp
// compile with: /clr /c
ref class C {
   void f() unknown;   // C3646
   // try the following line instead
   // virtual void f() abstract;
};
```
