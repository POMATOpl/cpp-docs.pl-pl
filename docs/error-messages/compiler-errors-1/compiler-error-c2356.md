---
description: 'Dowiedz się więcej o: błąd kompilatora C2356'
title: Błąd kompilatora C2356
ms.date: 11/04/2016
f1_keywords:
- C2356
helpviewer_keywords:
- C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
ms.openlocfilehash: c0e2d179bb41e6cbae674d92976674ab90f05c0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328332"
---
# <a name="compiler-error-c2356"></a>Błąd kompilatora C2356

segment inicjalizacji nie może ulec zmianie podczas jednostki tłumaczenia

Możliwe przyczyny:

- `#pragma init_seg` poprzedzone kodem inicjalizacji segmentu

- `#pragma init_seg` poprzedzony innym `#pragma init_seg`

Aby rozwiązać ten problem, Przenieś kod inicjalizacji segmentu na początek modułu. Jeśli trzeba zainicjować wiele obszarów, przenieś je do oddzielnych modułów.

Poniższy przykład generuje C2356:

```cpp
// C2356.cpp
#pragma warning(disable : 4075)

int __cdecl myexit(void (__cdecl *)());
int __cdecl myexit2(void (__cdecl *)());

#pragma init_seg(".mine$m",myexit)
#pragma init_seg(".mine$m",myexit2)   // C2356
```
