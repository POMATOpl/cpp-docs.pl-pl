---
title: Kompilator ostrzeżenie (poziom 1) C4174
ms.date: 11/04/2016
f1_keywords:
- C4174
helpviewer_keywords:
- C4174
ms.assetid: 63301e51-24bc-43c4-bb11-252f7d513e9e
ms.openlocfilehash: cc55318c8ef54f7d7f69e93d72717f54578ba576
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391689"
---
# <a name="compiler-warning-level-1-c4174"></a>Kompilator ostrzeżenie (poziom 1) C4174

"name": niedostępny jako składnik #pragma

## <a name="example"></a>Przykład

```
// C4174.cpp
// compile with: /W1
#pragma component(info)  // C4174; unknown
#pragma component(browser, off)  // turn off browse info
int main()
{
}
```