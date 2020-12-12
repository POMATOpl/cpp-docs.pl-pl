---
description: 'Dowiedz się więcej o: błąd kompilatora C2158'
title: Błąd kompilatora C2158
ms.date: 11/04/2016
f1_keywords:
- C2158
helpviewer_keywords:
- C2158
ms.assetid: 39028899-e95c-4809-8e65-6111118641ee
ms.openlocfilehash: 02665643b733bb63809696d194574e416cee4707
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181257"
---
# <a name="compiler-error-c2158"></a>Błąd kompilatora C2158

"Type": dyrektywa make_public #pragma jest obecnie obsługiwana tylko dla natywnych typów nienależących do szablonu

[Make_public](../../preprocessor/make-public.md) pragma może zostać zastosowana tylko do natywnego typu niebędącego szablonem.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2158.

```cpp
// C2158.cpp
// compile with: /clr /c
ref class A {};
#pragma make_public(A)   // C2158

template< typename T >
class B {};
#pragma make_public(B)   // C2158
#pragma make_public(B<int>)   // C2158

void C () {}
#pragma make_public(C)   // C2158

class D {};
#pragma make_public(D)   // OK
```
