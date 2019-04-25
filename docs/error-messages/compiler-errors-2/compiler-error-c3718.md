---
title: Błąd kompilatora C3718
ms.date: 11/04/2016
f1_keywords:
- C3718
helpviewer_keywords:
- C3718
ms.assetid: 346b5205-c44d-49d3-b66a-96417d3d6986
ms.openlocfilehash: 765791499370836f7c99ea7af69cb34bcf1e21fc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328261"
---
# <a name="compiler-error-c3718"></a>Błąd kompilatora C3718

można wywołać tylko "event" w kontekście funkcji składowej klasy odbiorczej

`event` Lze volat pouze z odbieranie klasy.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C3718:

```
// C3718.cpp
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[module(name="test")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface I
{
    HRESULT f();
};

[event_source(com), coclass, uuid("00000000-0000-0000-0000-000000000002")]
struct E
{
    __event __interface I;
};

[event_receiver(com)]
struct R
{
    void b()
    {
        printf_s("B::bar()\n");
    }

    void HookAndRun(E* pE)
    {
        __hook(&I::f, pE->GetUnknown(), &R::b);
        __raise pE->f();
    }
};

int main()
{
    CComObject<E>* pE;
    CComObject<E>::CreateInstance(&pE);

    __hook(&I::f, pE->GetUnknown(), &R::b, &r);   // C3718
    __raise pE->f();
    // try the following lines instead
    // R r;
    // r.HookAndRun(pE);
}
```