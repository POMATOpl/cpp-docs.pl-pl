---
description: 'Dowiedz się więcej o: błąd kompilatora C3208'
title: Błąd kompilatora C3208
ms.date: 11/04/2016
f1_keywords:
- C3208
helpviewer_keywords:
- C3208
ms.assetid: 6d060bfe-52cf-4599-8f70-bdeb5a670df3
ms.openlocfilehash: bd76a209fa3736449e8816473d0dee12daa93a61
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173951"
---
# <a name="compiler-error-c3208"></a>Błąd kompilatora C3208

"Function": Lista parametrów szablonu dla szablonu klasy "Class" jest niezgodna z listą parametrów szablonu dla parametru szablonu szablonu "parameter"

Parametr szablonu szablonu nie ma tej samej liczby parametrów szablonu co podany szablon klasy.

Poniższy przykład generuje C3208:

```cpp
// C3208.cpp
template <template <class T> class TT >
int f();

template <class T1, class T2>
struct S;

template <class T1>
struct R;

int i = f<S>();   // C3208
// try the following line instead
// int i = f<R>();
```
