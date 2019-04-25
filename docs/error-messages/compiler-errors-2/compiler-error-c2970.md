---
title: Błąd kompilatora C2970
ms.date: 11/04/2016
f1_keywords:
- C2970
helpviewer_keywords:
- C2970
ms.assetid: 21d90348-20d3-438c-b278-efdbfb93a7d2
ms.openlocfilehash: 425d1bf50d56c4455ccd9292b300e744625d34c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256339"
---
# <a name="compiler-error-c2970"></a>Błąd kompilatora C2970

"class": parametr szablonu "param": "arg": wyrażenie obejmujące obiekty z wewnętrznym powiązaniem nie można użyć jako argument bez typu

Nie można użyć nazwy lub adresu zmienną statyczną, jako argument szablonu. Klasa szablonu oczekuje stałej wartości, które mogą być obliczane w czasie kompilacji.

Poniższy przykład spowoduje wygenerowanie C2970:

```
// C2970.cpp
// compile with: /c
static int si;
// could declare nonstatic to resolve all errors
// int si;

template <int i>
class X {};

template <int *pi>
class Y {};

X<si> anX;   // C2970 cannot use static variable in templates

// this would also work
const int i = 10;
X<i> anX2;
```