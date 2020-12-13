---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4101'
title: Ostrzeżenie kompilatora (poziom 3) C4101
ms.date: 11/04/2016
f1_keywords:
- C4101
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
ms.openlocfilehash: c5e358bea4e9a584242376ed86d1bb5af2deb734
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150634"
---
# <a name="compiler-warning-level-3-c4101"></a>Ostrzeżenie kompilatora (poziom 3) C4101

"Identyfikator": niereferencyjna zmienna lokalna

Zmienna lokalna nie jest nigdy używana. To ostrzeżenie będzie miało miejsce w oczywistej sytuacji:

```cpp
// C4101a.cpp
// compile with: /W3
int main() {
int i;   // C4101
}
```

Jednak to ostrzeżenie również występuje podczas wywoływania **`static`** funkcji składowej za pomocą wystąpienia klasy:

```cpp
// C4101b.cpp
// compile with:  /W3
struct S {
   static int func()
   {
      return 1;
   }
};

int main() {
   S si;   // C4101, si is never used
   int y = si.func();
   return y;
}
```

W tej sytuacji kompilator używa informacji o `si` dostępie do **`static`** funkcji, ale wystąpienie klasy nie jest konieczne do wywołania **`static`** funkcji; w związku z tym ostrzeżenie. Aby rozwiązać ten problem, możesz:

- Dodaj Konstruktor, w którym kompilator będzie używać wystąpienia elementu `si` w wywołaniu `func` .

- Usuń **`static`** słowo kluczowe z definicji `func` .

- Wywołaj **`static`** funkcję jawnie: `int y = S::func();` .
