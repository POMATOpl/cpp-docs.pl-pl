---
description: 'Dowiedz się więcej o: błąd kompilatora C2036'
title: Błąd kompilatora C2036
ms.date: 11/04/2016
f1_keywords:
- C2036
helpviewer_keywords:
- C2036
ms.assetid: 895821a9-65d1-44b5-bde1-dae827f3e486
ms.openlocfilehash: 53e036ea1bf27fd9502a3c21353b450962bc0db9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175394"
---
# <a name="compiler-error-c2036"></a>Błąd kompilatora C2036

"Identyfikator": nieznany rozmiar

Operacja na `identifier` wymaga rozmiaru obiektu danych, którego nie można ustalić.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C2036.

```c
// C2036.c
// a C program
struct A* pA;
struct B { int i; } *pB;
int main() {
   pA++;   // C2036, size of A not known
   ((char*)pA)++;   // OK

   pB++;   // OK
}
```

Poniższy przykład generuje C2036.

```cpp
// C2036_2.cpp
// a C++ program
struct A* pA;
int main() {
   pA++;   // C2036, size of A not known
   ((char*&)pA)++;   // OK, if sizeof(A) == sizeof(char)
}
```
