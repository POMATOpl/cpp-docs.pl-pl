---
title: Ostrzeżenie kompilatora (poziom 1) C4096
ms.date: 11/04/2016
f1_keywords:
- C4096
helpviewer_keywords:
- C4096
ms.assetid: abf3cca2-2f21-45d8-b025-6b513b00681e
ms.openlocfilehash: 4f5a45339673b57f946f206e1eaff0d23ec6fee9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163939"
---
# <a name="compiler-warning-level-1-c4096"></a>Ostrzeżenie kompilatora (poziom 1) C4096

"a": interfejs nie jest interfejsem COM; nie będzie emitowany do IDL

Definicja interfejsu, która może być przeznaczona jako interfejs COM, nie została zdefiniowana jako interfejs COM i dlatego nie będzie emitowana do pliku IDL.

Zobacz [atrybuty interfejsu](../../windows/attributes/interface-attributes.md) , aby uzyskać listę atrybutów, które wskazują, że interfejs jest interfejsem com.

Poniższy przykład generuje C4096:

```cpp
// C4096.cpp
// compile with: /W1 /LD
#include "windows.h"
[module(name="xx")];

// [object, uuid("00000000-0000-0000-0000-000000000001")]
__interface a
{
};

[coclass, uuid("00000000-0000-0000-0000-000000000002")]
struct b : a
{
};   // C4096, remove coclass or uncomment object
```
