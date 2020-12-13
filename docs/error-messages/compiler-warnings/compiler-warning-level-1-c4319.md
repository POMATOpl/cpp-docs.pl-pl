---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4319'
title: Ostrzeżenie kompilatora (poziom 1) C4319
ms.date: 01/18/2018
f1_keywords:
- C4319
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
ms.openlocfilehash: af38714ab506fad389d9d2407b5a83aebf01f7c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340063"
---
# <a name="compiler-warning-level-1-c4319"></a>Ostrzeżenie kompilatora (poziom 1) C4319

> "~": zero rozszerzające wartość "*Type1*" na "*Type2*" o większym rozmiarze

Wynik **~** operatora (deuzupełnienie bitowe) jest niepodpisany, a następnie zostanie przedłużony zero, gdy zostanie on przekonwertowany na większy typ.

## <a name="example"></a>Przykład

W poniższym przykładzie `~(a - 1)` jest oceniane jako 32-bitowe wyrażenie długie bez znaku, a następnie konwertowane do 64 bitów przez zero. Może to prowadzić do nieoczekiwanych wyników operacji.

```cpp
// C4319.cpp
// compile with: cl /W4 C4319.cpp
int main() {
   unsigned long a = 0;
   unsigned long long q = 42;
   q = q & ~(a - 1);    // C4319 expected
}
```
