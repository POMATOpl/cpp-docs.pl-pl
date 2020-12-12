---
description: 'Dowiedz się więcej na temat: void (C++)'
title: void (C++)
ms.date: 11/04/2016
f1_keywords:
- void_cpp
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
ms.openlocfilehash: e49dfa03e289cdbace50a24cf6854d25c51b3426
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213354"
---
# <a name="void-c"></a>void (C++)

W przypadku użycia jako zwracanego typu funkcji **`void`** słowo kluczowe Określa, że funkcja nie zwraca wartości. W przypadku użycia dla listy parametrów funkcji **`void`** określa, że funkcja nie przyjmuje żadnych parametrów. Gdy jest używany w deklaracji wskaźnika, **`void`** określa, że wskaźnik jest "uniwersalny".

Jeśli typ wskaźnika to **void \* *_, wskaźnik może wskazywać wszelkie zmienne, które nie są zadeklarowane za pomocą _* `const`** lub **`volatile`** słowo kluczowe. Nie można usunąć odwołania wskaźnika **void \** _, chyba że jest rzutowany na inny typ. Wskaźnik _*void \**_ można przekonwertować na dowolny inny typ wskaźnika danych.

Wskaźnik _ *`void`* * może wskazywać na funkcję, ale nie do składowej klasy w języku C++.

Nie można zadeklarować zmiennej typu **`void`** .

## <a name="example"></a>Przykład

```cpp
// void.cpp
void vobject;   // C2182
void *pv;   // okay
int *pint; int i;
int main() {
   pv = &i;
   // Cast optional in C required in C++
   pint = (int *)pv;
}
```

## <a name="see-also"></a>Zobacz także

[Słowa kluczowe](../cpp/keywords-cpp.md)<br/>
[Typy wbudowane](../cpp/fundamental-types-cpp.md)
