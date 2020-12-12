---
description: 'Dowiedz się więcej o: błąd kompilatora C3205'
title: Błąd kompilatora C3205
ms.date: 11/04/2016
f1_keywords:
- C3205
helpviewer_keywords:
- C3205
ms.assetid: 802d306e-5ff3-4491-8a22-c5f1c072d005
ms.openlocfilehash: bc85a414ee4ef1602f911833928b8f8dc7f49476
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164344"
---
# <a name="compiler-error-c3205"></a>Błąd kompilatora C3205

Brak listy argumentów dla parametru szablonu "parameter"

Brak parametru [szablonu](../../cpp/templates-cpp.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C3205:

```cpp
// C3205.cpp
template<template<class> class T> struct A {
   typedef T unparameterized_type;   // C3205
   // try the following line instead
   // typedef T<int> unparameterized_type;
};

template <class T>
struct B {
   typedef int value_type;
};

int main() {
   A<B> x;
}
```
