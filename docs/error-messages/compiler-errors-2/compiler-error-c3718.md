---
title: Błąd kompilatora C3718 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3718
dev_langs:
- C++
helpviewer_keywords:
- C3718
ms.assetid: 346b5205-c44d-49d3-b66a-96417d3d6986
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb5965ee0c6f19c31a459b14ea9ebcb83fe5f32d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098410"
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