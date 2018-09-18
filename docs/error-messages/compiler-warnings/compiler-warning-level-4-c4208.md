---
title: Kompilator ostrzeżenie (poziom 4) C4208 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4208
dev_langs:
- C++
helpviewer_keywords:
- C4208
ms.assetid: 5cb0a36e-3fb5-422f-a5f9-e40b70776c27
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ee87ad1d43b20c4d0a72b877b05b1ba4c084a1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064626"
---
# <a name="compiler-warning-level-4-c4208"></a>Kompilator ostrzeżenie (poziom 4) C4208

użyto niestandardowego rozszerzenia: delete [exp] - exp obliczono, ale zignorowano

Rozszerzenia Microsoft (/Ze), możesz usunąć tablicy przy użyciu wartości w nawiasach z [delete operator](../../cpp/delete-operator-cpp.md). Wartość jest ignorowana.

```
// C4208.cpp
// compile with: /W4
int main()
{
   int * MyArray = new int[18];
   delete [18] MyArray;      // C4208
   MyArray = new int[18];
   delete [] MyArray;        // ok
}
```

Wartości te są nieprawidłowe w obszarze zgodności ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).