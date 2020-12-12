---
description: 'Dowiedz się więcej o: błąd kompilatora C3273'
title: Błąd kompilatora C3273
ms.date: 11/04/2016
f1_keywords:
- C3273
helpviewer_keywords:
- C3273
ms.assetid: 1d2ce9d9-222b-4cab-94e2-d2c1a9f5ebe0
ms.openlocfilehash: 23216089bb6d4a963f04201e742af2f50818efcc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185768"
---
# <a name="compiler-error-c3273"></a>Błąd kompilatora C3273

nie można użyć __finally w bloku wyjątku w kodzie niezarządzanym.

Poniższy przykład generuje C3273:

```cpp
// C3273.cpp
// compile with: /GX
int main()
{
   try
   {
   }
   catch (int)
   {
   }
   __finally   // C3273, remove __finally clause
   {
   }
}
```
