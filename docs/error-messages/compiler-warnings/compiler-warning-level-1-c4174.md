---
title: Ostrzeżenie kompilatora (poziom 1) C4174
ms.date: 11/04/2016
f1_keywords:
- C4174
helpviewer_keywords:
- C4174
ms.assetid: 63301e51-24bc-43c4-bb11-252f7d513e9e
ms.openlocfilehash: dfa3c66e31e35cf9dbbd55f29fcd2d511870fdce
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624809"
---
# <a name="compiler-warning-level-1-c4174"></a>Ostrzeżenie kompilatora (poziom 1) C4174

"name": niedostępne jako składnik #pragma

## <a name="example"></a>Przykład

```cpp
// C4174.cpp
// compile with: /W1
#pragma component(info)  // C4174; unknown
#pragma component(browser, off)  // turn off browse info
int main()
{
}
```