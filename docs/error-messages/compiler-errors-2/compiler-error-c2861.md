---
description: 'Dowiedz się więcej o: błąd kompilatora C2861'
title: Błąd kompilatora C2861
ms.date: 11/04/2016
f1_keywords:
- C2861
helpviewer_keywords:
- C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
ms.openlocfilehash: 82a4ed7d4b157bc141e9d437fa0f1d575759b48e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151128"
---
# <a name="compiler-error-c2861"></a>Błąd kompilatora C2861

"nazwa funkcji": nie można zdefiniować funkcji składowej interfejsu

Kompilator napotkał słowo kluczowe interfejsu lub wywnioskuje strukturę jako interfejs, a następnie odnalazł definicję funkcji składowej.  Interfejs nie może zawierać definicji funkcji składowej.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2861:

```cpp
// C2861.cpp
// compile with: /c
#include <objbase.h>   // required for IUnknown definition
[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IMyInterface : IUnknown {
   HRESULT mf(int a);
};

HRESULT IMyInterface::mf(int a) {}   // C2861
```
