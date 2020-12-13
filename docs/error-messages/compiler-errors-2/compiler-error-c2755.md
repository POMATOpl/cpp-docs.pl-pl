---
description: 'Dowiedz się więcej o: błąd kompilatora C2755'
title: Błąd kompilatora C2755
ms.date: 11/04/2016
f1_keywords:
- C2755
helpviewer_keywords:
- C2755
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
ms.openlocfilehash: dcf597505afb170aaf87644a7482a56dc2fdc73c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336208"
---
# <a name="compiler-error-c2755"></a>Błąd kompilatora C2755

"param": parametr niebędący typem częściowej specjalizacji musi być prostym identyfikatorem

Parametr niebędący typem musi być prostym identyfikatorem, co kompilator może rozpoznać w czasie kompilacji do jednego identyfikatora lub wartości stałej.

Poniższy przykład generuje C2755:

```cpp
// C2755.cpp
template<int I, int J>
struct A {};

template<int I>
struct A<I,I*5> {};   // C2755
// try the following line instead
// struct A<I,5> {};
```
