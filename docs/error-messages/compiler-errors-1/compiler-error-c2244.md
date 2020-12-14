---
description: 'Dowiedz się więcej o: błąd kompilatora C2244'
title: Błąd kompilatora C2244
ms.date: 11/04/2016
f1_keywords:
- C2244
helpviewer_keywords:
- C2244
ms.assetid: d9911c12-ceb5-4f93-ac47-b44a485215c2
ms.openlocfilehash: 9f541eca155b9d728f0bbf7cb1578a6e3424c49c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302246"
---
# <a name="compiler-error-c2244"></a>Błąd kompilatora C2244

"Identyfikator": nie można dopasować definicji funkcji do istniejącej deklaracji

Nietypowe użycie operatora jednoargumentowego + zostało użyte przed wywołaniem funkcji, które nie ma nawiasów.

Ten błąd występuje tylko w projektach języka C++.

Poniższy przykład generuje C2244:

```cpp
// C2244.cpp
int func(char) {
   return 0;
}

int func(int) {
   return 0;
}

int main() {
   +func;   // C2244
}
```

C2244 może również wystąpić, gdy do funkcji składowej szablonu klasy jest używany nieprawidłowy podpis funkcji.

```cpp
// C2244b.cpp
// compile with: /c
template<class T>
class XYZ {
   void func(T t);
};

template<class T>
void XYZ<T>::func(int i) {}   // C2244 wrong function signature
// try the following line instead
// void XYZ<T>::func(T t) {}
```

C2244 może również wystąpić, gdy dla szablonu funkcji składowej użyto nieprawidłowej sygnatury funkcji.

```cpp
// C2244c.cpp
// compile with: /c
class ABC {
   template<class T>
   void func(int i, T t);
};

template<class T>
void ABC::func(int i) {}   // C2244 wrong signature
// try the following line instead
// void ABC::func(int i, T t) {}
```

Nie można częściowo specjalizacji szablonu funkcji.

```cpp
// C2244d.cpp
template<class T, class U>
class QRS {
   void func(T t, U u);
};

template<class T>
void QRS<T,int>::func(T t, int u) {}   // C2244
```
