---
description: 'Dowiedz się więcej o: błąd kompilatora C2910'
title: Błąd kompilatora C2910
ms.date: 11/04/2016
f1_keywords:
- C2910
helpviewer_keywords:
- C2910
ms.assetid: 09c50e6a-e099-42f6-8ed6-d80e292a7a36
ms.openlocfilehash: d4bb87b054f28e0eab5bc1eef815fd1770d45809
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270631"
---
# <a name="compiler-error-c2910"></a>Błąd kompilatora C2910

"Function": nie może być jawnie wyspecjalizowany

Kompilator wykrył próbę jawnej specjalizacji funkcji.

Poniższy przykład generuje C2910:

```cpp
// C2910.cpp
// compile with: /c
template <class T>
struct S;

template <> struct S<int> { void f() {} };
template <> void S<int>::f() {}   // C2910 delete this specialization
```

C2910 można również wygenerować, jeśli spróbujesz jawnie specjalizację niebędącego członkiem szablonu. Oznacza to, że można jawnie specjalizacji szablonu funkcji.

Poniższy przykład generuje C2910:

```cpp
// C2910b.cpp
// compile with: /c
template <class T> struct A {
   A(T* p);
};

template <> struct A<void> {
   A(void* p);
};

template <class T>
inline A<T>::A(T* p) {}

template <> A<void>::A(void* p){}   // C2910
// try the following line instead
// A<void>::A(void* p){}
```

Ten błąd zostanie również wygenerowany w wyniku działania kompilatora, który został wykonany w programie Visual Studio .NET 2003:.

Kod będzie prawidłowy w wersjach programu Visual Studio .NET 2003 i Visual Studio .NET Visual C++, Usuń `template <>` .

Poniższy przykład generuje C2910:

```cpp
// C2910c.cpp
// compile with: /c
template <class T> class A {
   void f();
};

template <> class A<int> {
   void f();
};

template <> void A<int>::f() {}   // C2910
// try the following line instead
// void A<int>::f(){}   // OK
```
