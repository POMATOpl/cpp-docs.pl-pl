---
title: Ostrzeżenie kompilatora (poziom 1) C4180
ms.date: 11/04/2016
f1_keywords:
- C4180
helpviewer_keywords:
- C4180
ms.assetid: 40c91bd4-37f1-4d59-a4f3-d5ddab68239b
ms.openlocfilehash: 4a153d2ec5d2cc8850f3c27390862d3cd0e70bed
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214480"
---
# <a name="compiler-warning-level-1-c4180"></a>Ostrzeżenie kompilatora (poziom 1) C4180

kwalifikator stosowany do typu funkcji nie ma znaczenia; Ignoruj

Kwalifikator, taki jak **`const`** , jest stosowany do typu funkcji zdefiniowanego przez **`typedef`** .

## <a name="example"></a>Przykład

```cpp
// C4180.cpp
// compile with: /W1 /c
typedef int FuncType(void);

// the const qualifier cannot be applied to the
// function type FuncType
const FuncType f;   // C4180
```
