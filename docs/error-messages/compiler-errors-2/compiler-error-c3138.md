---
description: 'Dowiedz się więcej o: błąd kompilatora C3138'
title: Błąd kompilatora C3138
ms.date: 11/04/2016
f1_keywords:
- C3138
helpviewer_keywords:
- C3138
ms.assetid: 364ee9e8-9358-410e-bd35-9c4a226a3753
ms.openlocfilehash: 07fa48cc4c14773eeb41420eb63d659028de8caf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304262"
---
# <a name="compiler-error-c3138"></a>Błąd kompilatora C3138

"Interface": interfejs "Attribute" musi dziedziczyć z IDispatch lub z interfejsu, który dziedziczy z IDispatch

Interfejs z atrybutami [Dual](../../windows/attributes/dual.md) lub [dispinterface](../../windows/attributes/dispinterface.md) nie ma `IDispatch` bezpośredniego lub pośredniego interfejsu podstawowego.

Poniższy przykład generuje C3138:

```cpp
// C3138.cpp
#include <unknwn.h>

[ object, uuid("77ac9240-6e9a-11d2-97de-0000f805d73b") ]
__interface IMyCustomInterface
{
   HRESULT mf1(void);
};

[ dispinterface, uuid("3536f8a0-6e9a-11d2-97de-0000f805d73b") ]
__interface IMyDispInterface : IUnknown
{
   [id(1)] HRESULT mf2(void);
};

[ object, dual, uuid("34e90a10-6e9a-11d2-97de-0000f805d73b") ]
__interface IMyDualInterface : IMyCustomInterface  // C3138 expected
{
   HRESULT mf3(void);
};
```
