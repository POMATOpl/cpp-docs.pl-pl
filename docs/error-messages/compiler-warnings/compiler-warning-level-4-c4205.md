---
title: Kompilator ostrzeżenie (poziom 4) C4205 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4205
dev_langs:
- C++
helpviewer_keywords:
- C4205
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9847e3c009e132993bcbb6aa94d2064d61e40421
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042367"
---
# <a name="compiler-warning-level-4-c4205"></a>Kompilator ostrzeżenie (poziom 4) C4205

użyto niestandardowego rozszerzenia: deklaracja statycznej funkcji występuje w zakresie funkcji

Z rozszerzeniami firmy Microsoft (/Ze) **statyczne** funkcje mogą być zadeklarowane wewnątrz innej funkcji. Funkcja znajduje się zakresie globalnym.

## <a name="example"></a>Przykład

```
// C4205.c
// compile with: /W4
void func1()
{
   static int func2();  // C4205
};

int main()
{
}
```

Takie inicjalizacje są nieprawidłowe w obszarze zgodności ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).