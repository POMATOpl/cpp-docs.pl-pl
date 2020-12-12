---
description: 'Dowiedz się więcej o: błąd kompilatora C2665'
title: Błąd kompilatora C2665
ms.date: 11/04/2016
f1_keywords:
- C2665
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
ms.openlocfilehash: 784fe5ef0f24cd9e5fba99465d46f378b2b517fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210806"
---
# <a name="compiler-error-c2665"></a>Błąd kompilatora C2665

"Function": żadne z przeciążeń Liczba1 nie może konwertować parametru liczba2 z typu "Type"

Nie można przekonwertować parametru przeciążonej funkcji na wymagany typ.  Możliwe rozwiązania:

- Podaj Operator konwersji.

- Użyj konwersji jawnej.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2665.

```cpp
// C2665.cpp
void func(short, char*){}
void func(char*, char*){}

int main() {
   func(0, 1);   // C2665
   func((short)0, (char*)1);   // OK
}
```
