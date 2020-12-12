---
description: 'Dowiedz się więcej o: błąd kompilatora C2156'
title: Błąd kompilatora C2156
ms.date: 11/04/2016
f1_keywords:
- C2156
helpviewer_keywords:
- C2156
ms.assetid: 136f9c67-2c27-4f61-b7e6-ccd202eca697
ms.openlocfilehash: fa9954c52be278442d357dfa69071f83d10e49e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204137"
---
# <a name="compiler-error-c2156"></a>Błąd kompilatora C2156

Pragma musi być poza funkcją

Pragma, która musi być określona na poziomie globalnym (poza treścią funkcji), znajduje się w funkcji.

Poniższy przykład generuje C2156:

```cpp
// C2156.cpp
#pragma optimize( "l", on )   // OK
int main() {
   #pragma optimize( "l", on )   // C2156
}
```
