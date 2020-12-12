---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4939'
title: Ostrzeżenie kompilatora (poziom 1) C4939
ms.date: 11/04/2016
f1_keywords:
- C4939
helpviewer_keywords:
- C4939
ms.assetid: 07096008-ba47-436c-a84c-2b03ad90d0b3
ms.openlocfilehash: e31d59321ee5c2f6f154ebcaac4b74054db2604e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328032"
---
# <a name="compiler-warning-level-1-c4939"></a>Ostrzeżenie kompilatora (poziom 1) C4939

\#pragma vtordisp jest przestarzała i zostanie usunięta w przyszłej wersji Visual C++

Pragma [vtordisp](../../preprocessor/vtordisp.md) zostanie usunięta w przyszłej wersji Visual C++.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4939.

```cpp
// C4939.cpp
// compile with: /c /W1
#pragma vtordisp(off)   // C4939
```
