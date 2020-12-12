---
description: 'Dowiedz się więcej o: błąd kompilatora C3412'
title: Błąd kompilatora C3412
ms.date: 11/04/2016
f1_keywords:
- C3412
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
ms.openlocfilehash: aa0dc6cfeac193afc99d003cd821663bcfc139c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313193"
---
# <a name="compiler-error-c3412"></a>Błąd kompilatora C3412

"template": nie można specialize szablonu w bieżącym zakresie

Szablon nie może być wyspecjalizowany w zakresie klasy, tylko w globalnym lub zakresie przestrzeni nazw.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C3412.

```cpp
// C3412.cpp
template <class T>
struct S {
   template <>
   struct S<int> {};   // C3412 in a class
};
```

Poniższy przykład pokazuje możliwe rozwiązanie.

```cpp
// C3412b.cpp
// compile with: /c
template <class T>
struct S {};

template <>
struct S<int> {};
```
