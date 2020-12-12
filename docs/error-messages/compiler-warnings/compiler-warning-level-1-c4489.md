---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4489'
title: Ostrzeżenie kompilatora (poziom 1) C4489
ms.date: 11/04/2016
f1_keywords:
- C4489
helpviewer_keywords:
- C4489
ms.assetid: 43b51c8c-27b5-44c9-b974-fe4b48f4896f
ms.openlocfilehash: d2865f7f2eba4db72fa4cbf622609b319197f942
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212418"
---
# <a name="compiler-warning-level-1-c4489"></a>Ostrzeżenie kompilatora (poziom 1) C4489

Specyfikator ": niedozwolony dla metody interfejsu" Method "; Specyfikatory przesłonięcia są dozwolone tylko w metodach klasy referencyjnej i klasie wartości

Słowo kluczowe specyfikatora zostało nieprawidłowo użyte w metodzie interfejsu.

Aby uzyskać więcej informacji, zobacz [specyfikatory przesłonięć](../../extensions/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C4489.

```cpp
// C4489.cpp
// compile with: /clr /c /W1
public interface class I {
   void f() new;   // C4489
   virtual void b() override;   // C4489

   void g();   // OK
};
```
