---
description: 'Dowiedz się więcej o: błąd kompilatora C3136'
title: Błąd kompilatora C3136
ms.date: 10/03/2018
f1_keywords:
- C3136
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
ms.openlocfilehash: 4203eaa1f41603075bbb8162b7156783c8f2680a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239379"
---
# <a name="compiler-error-c3136"></a>Błąd kompilatora C3136

"Interface": interfejs COM może dziedziczyć tylko po innym interfejsie COM, interfejs nie jest interfejsem COM

Interfejs, do którego zastosowano [atrybut interfejsu](../../windows/attributes/interface-attributes.md) , dziedziczy z interfejsu, który nie jest interfejsem com. Interfejs COM ostatecznie dziedziczy z `IUnknown` . Każdy interfejs poprzedzony atrybutem interfejsu jest interfejsem COM.

Poniższy przykład generuje C3136:

```cpp
// C3136.cpp
#include "unknwn.h"

__interface A   // C3136
// try the following line instead
// _interface A : IUnknown
{
   int a();
};

[object]
__interface B : A
{
   int aa();
};
```
