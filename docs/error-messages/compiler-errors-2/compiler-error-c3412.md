---
title: Błąd kompilatora C3412
ms.date: 11/04/2016
f1_keywords:
- C3412
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
ms.openlocfilehash: ad241b656464746333760cfcbc134c91e49bf44e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761419"
---
# <a name="compiler-error-c3412"></a>Błąd kompilatora C3412

"template": nie można specialize szablonu w bieżącym zakresie

Szablon nie może być wyspecjalizowany w zakresie klasy, tylko w globalnym lub zakresie przestrzeni nazw.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3412.

```cpp
// C3412.cpp
template <class T>
struct S {
   template <>
   struct S<int> {};   // C3412 in a class
};
```

## <a name="example"></a>Przykład

Poniższy przykład pokazuje możliwe rozwiązanie.

```cpp
// C3412b.cpp
// compile with: /c
template <class T>
struct S {};

template <>
struct S<int> {};
```
