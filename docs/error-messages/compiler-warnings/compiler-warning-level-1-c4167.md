---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4167'
title: Ostrzeżenie kompilatora (poziom 1) C4167
ms.date: 11/04/2016
f1_keywords:
- C4167
helpviewer_keywords:
- C4167
ms.assetid: 74a420bd-9371-4167-b1ee-74dd8680f97b
ms.openlocfilehash: 8d0b08ea4d97c6e85f5e07ce4844abdae7afafbd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266991"
---
# <a name="compiler-warning-level-1-c4167"></a>Ostrzeżenie kompilatora (poziom 1) C4167

Funkcja: dostępna tylko jako wewnętrzna funkcja

**Funkcja #pragma** próbuje wymusić użycie przez kompilator konwencjonalnego wywołania funkcji, która musi być używana w formie wewnętrznej. Pragma jest ignorowana.

Aby uniknąć tego ostrzeżenia, Usuń **funkcję #pragma**.

## <a name="example"></a>Przykład

```cpp
// C4167.cpp
// compile with: /W1
#include <malloc.h>
#pragma function(_alloca )   // C4167: _alloca() is intrinsic only
int main(){}
```
