---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4490'
title: Ostrzeżenie kompilatora (poziom 1) C4490
ms.date: 11/04/2016
f1_keywords:
- C4490
helpviewer_keywords:
- C4490
ms.assetid: f9b03ecf-41a1-4f4d-a74c-2c1e88234ccc
ms.openlocfilehash: 8216075e481e85f362e85cf158375a6d8b076772
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310879"
---
# <a name="compiler-warning-level-1-c4490"></a>Ostrzeżenie kompilatora (poziom 1) C4490

"override": Niepoprawne użycie specyfikatora override; Funkcja "Function" nie pasuje do metody bazowej klasy referencyjnej

Specyfikator przesłonięcia został niepoprawnie użyty. Na przykład nie przesłaniasz funkcji interfejsu, zaimplementujmy ją.

Aby uzyskać więcej informacji, zobacz [specyfikatory przesłonięć](../../extensions/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C4490.

```cpp
// C4490.cpp
// compile with: /clr /c /W1

interface struct IFace {
   void Test();
};

ref struct Class1 : public IFace {
   virtual void Test() override {}   // C4490
   // try the following line instead
   // virtual void Test() {}
};
```
