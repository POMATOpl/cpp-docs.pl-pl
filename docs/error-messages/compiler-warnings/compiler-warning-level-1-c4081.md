---
title: Ostrzeżenie kompilatora (poziom 1) C4081
ms.date: 11/04/2016
f1_keywords:
- C4081
helpviewer_keywords:
- C4081
ms.assetid: 6f656373-a080-4989-bbc9-e2f894b03293
ms.openlocfilehash: b882fe9c83f072c06a63733870f610549b209691
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200297"
---
# <a name="compiler-warning-level-1-c4081"></a>Ostrzeżenie kompilatora (poziom 1) C4081

Oczekiwano elementu "token1"; znaleziono "token2"

Kompilator oczekiwał innego tokenu w tym kontekście.

## <a name="example"></a>Przykład

```cpp
// C4081.cpp
// compile with: /W1 /LD
#pragma optimize) "l", on )   // C4081
```
