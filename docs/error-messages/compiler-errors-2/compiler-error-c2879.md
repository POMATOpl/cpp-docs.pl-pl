---
description: 'Dowiedz się więcej o: błąd kompilatora C2879'
title: Błąd kompilatora C2879
ms.date: 11/04/2016
f1_keywords:
- C2879
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
ms.openlocfilehash: 6060678f71bf36d0af2e94e380a046ea7916ef05
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194374"
---
# <a name="compiler-error-c2879"></a>Błąd kompilatora C2879

"symbol": tylko istniejąca przestrzeń nazw może mieć nazwę alternatywną przez definicję aliasu przestrzeni nazw

Nie można utworzyć [aliasu przestrzeni nazw](../../cpp/namespaces-cpp.md#namespace_aliases) dla symbolu innego niż przestrzeń nazw.

Poniższy przykład generuje C2879:

```cpp
// C2879.cpp
int main() {
   int i;
   namespace A = i;   // C2879 i is not a namespace
}
```
