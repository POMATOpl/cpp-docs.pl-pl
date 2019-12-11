---
title: Ostrzeżenie kompilatora (poziom 4) C4515
ms.date: 11/04/2016
f1_keywords:
- C4515
helpviewer_keywords:
- C4515
ms.assetid: 167b5177-3f89-418b-b6c8-7de634f6b28f
ms.openlocfilehash: 442852ba971fb1b9a687d5ccf2b2857aa9deab50
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990725"
---
# <a name="compiler-warning-level-4-c4515"></a>Ostrzeżenie kompilatora (poziom 4) C4515

"Przestrzeń nazw": przestrzeń nazw używa samego siebie

Przestrzeń nazw jest używana cyklicznie.

Poniższy przykład generuje C4515:

```cpp
// C4515.cpp
// compile with: /W4
namespace A
{
   using namespace A; // C4515
}

int main()
{
}
```
