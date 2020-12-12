---
description: 'Dowiedz się więcej o: błąd kompilatora C3358'
title: Błąd kompilatora C3358
ms.date: 11/04/2016
f1_keywords:
- C3358
helpviewer_keywords:
- C3358
ms.assetid: 180b93df-e78f-441a-91fb-1594c681f7f0
ms.openlocfilehash: 44f72336f150f55cb8338fdeaa3edef4e81a601d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150881"
---
# <a name="compiler-error-c3358"></a>Błąd kompilatora C3358

"symbol": nie znaleziono symbolu

Nie znaleziono wymaganego symbolu.

Poniższy przykład generuje C3358:

```cpp
// C3358.cpp
#define __ATLEVENT_H__ 1   // remove this line to resolve the error
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[event_receiver(com)]
struct A   // C3358
{
   void func();
};

int main()
{
}
```
