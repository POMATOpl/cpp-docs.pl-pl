---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4161'
title: Ostrzeżenie kompilatora (poziom 3) C4161
ms.date: 08/27/2018
f1_keywords:
- C4161
helpviewer_keywords:
- C4161
ms.assetid: 03d3be61-83f1-4009-8310-8758ab67055f
ms.openlocfilehash: 6bb96fbee367751533fba769a6c56f01f94df19c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272191"
---
# <a name="compiler-warning-level-3-c4161"></a>Ostrzeżenie kompilatora (poziom 3) C4161

> #<a name="pragma-pragmapop--more-pops-than-pushes"></a>pragma *pragma*(pop...): więcej punktów obecności niż wypychanie

## <a name="remarks"></a>Uwagi

Ponieważ kod źródłowy zawiera jeszcze jeden punkt wyskakujący niż wypchnięcia *dla dyrektywy pragma, stos* może nie zachowywać się zgodnie z oczekiwaniami. Aby uniknąć ostrzeżenia, należy się upewnić, że liczba punktów obecności nie przekracza liczby wypchnięciów.

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
