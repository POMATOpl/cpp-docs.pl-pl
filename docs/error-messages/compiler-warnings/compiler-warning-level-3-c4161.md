---
title: Kompilator ostrzeżenie (poziom 3) C4161
ms.date: 08/27/2018
f1_keywords:
- C4161
helpviewer_keywords:
- C4161
ms.assetid: 03d3be61-83f1-4009-8310-8758ab67055f
ms.openlocfilehash: e1bbc949c298a7cfb6c3a3a061616db3dc4730f4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402271"
---
# <a name="compiler-warning-level-3-c4161"></a>Kompilator ostrzeżenie (poziom 3) C4161

> #<a name="pragma-pragmapop--more-pops-than-pushes"></a>pragma *pragma*(pop...): więcej zdejmowań niż włożeń

## <a name="remarks"></a>Uwagi

Ponieważ kod źródłowy zawiera jeden bardziej pop niż włożeń dla pragmy *pragma*, stosu mogą nie zachowywać się zgodnie z oczekiwaniami. Aby uniknąć ostrzeżenia, upewnij się, że liczba lokalizacji POP nie przekracza liczby wypchnięć.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4161:

```cpp
// C4161.cpp
// compile with: /W3 /LD
#pragma pack(push, id)
#pragma pack(pop, id)
#pragma pack(pop, id)   // C4161, an extra pop

#pragma bss_seg(".my_data1")
int j;

#pragma bss_seg(push, stack1, ".my_data2")
int l;

#pragma bss_seg(pop, stack1)
int m;

#pragma bss_seg(pop, stack1)   // C4161
```