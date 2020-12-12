---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4683'
title: Ostrzeżenie kompilatora (poziom 1) C4683
ms.date: 08/27/2018
f1_keywords:
- C4683
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
ms.openlocfilehash: e7f2c76e7f15bb7342e60b2aa390cf0bd1a8ce05
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285243"
---
# <a name="compiler-warning-level-1-c4683"></a>Ostrzeżenie kompilatora (poziom 1) C4683

> "*Function*": Źródło zdarzenia ma parametr "parametr"; należy zachować ostrożność podczas podłączania obsługi wielu zdarzeń

## <a name="remarks"></a>Uwagi

Jeśli więcej niż jeden obiekt ujścia zdarzeń nasłuchuje w źródle zdarzeń COM, wartość parametru out może być ignorowana.

Należy pamiętać, że przeciek pamięci wystąpi w następujących sytuacjach:

1. Jeśli metoda ma parametr out przydzielony wewnętrznie, na przykład BSTR *.

2. Jeśli zdarzenie ma więcej niż jeden program obsługi (jest to zdarzenie multiemisji).

Przyczyną przecieku jest to, że parametr out zostanie ustawiony przez więcej niż jedną procedurę obsługi, ale został zwrócony do lokacji wywołania tylko przez ostatnią procedurę obsługi.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4683 i pokazuje, jak to naprawić:

```cpp
// C4683.cpp
// compile with: /W1 /LD
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[ module(name="xx") ];

[ object ]
__interface I {
   HRESULT f([out] int* pi);
   // try the following line instead
   // HRESULT f(int* pi);
};

[ coclass, event_source(com) ]
struct E {
   __event __interface I;   // C4683
};
```
