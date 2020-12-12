---
description: 'Dowiedz się więcej o: błąd kompilatora C3204'
title: Błąd kompilatora C3204
ms.date: 11/04/2016
f1_keywords:
- C3204
helpviewer_keywords:
- C3204
ms.assetid: 06e578da-0262-48c8-b2ae-be1cd6d28884
ms.openlocfilehash: 8e9275cada58988c9dac3942569fb0416ddff0ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285737"
---
# <a name="compiler-error-c3204"></a>Błąd kompilatora C3204

nie można wywołać elementu "_alloca" z wewnątrz bloku catch

Ten błąd występuje, gdy używasz wywołania do [_alloca](../../c-runtime-library/reference/alloca.md) z wewnątrz bloku catch.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3204:

```cpp
// C3204.cpp
// compile with: /EHsc
#include <malloc.h>

void ShowError(void)
{
   try
   {
   }
   catch(...)
   {
      _alloca(1);   // C3204
   }
}
```
