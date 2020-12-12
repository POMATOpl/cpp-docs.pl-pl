---
description: 'Dowiedz się więcej na temat: Jawna specjalizacja szablonów funkcji'
title: Jawna specjalizacja szablonów funkcji
ms.date: 11/04/2016
helpviewer_keywords:
- overriding, functions
- function templates, specialization
- explicit specialization of function templates
- declaring functions [C++], specialization of function template
- specialization of function templates
ms.assetid: eb0fcb73-eaed-42a1-9b83-14b055a34bf8
ms.openlocfilehash: c77ebce3383ba2051ac010c39a7dd0eb37b8111a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181504"
---
# <a name="explicit-specialization-of-function-templates"></a>Jawna specjalizacja szablonów funkcji

Za pomocą szablonu funkcji można zdefiniować specjalne zachowanie dla określonego typu, podając jawną specjalizację (przesłonięcie) szablonu funkcji dla tego typu. Na przykład:

```cpp
template<> void MySwap(double a, double b);
```

Ta deklaracja umożliwia zdefiniowanie innej funkcji dla **`double`** zmiennych. Podobnie jak w przypadku funkcji innych niż szablony, stosowane są standardowe konwersje typów (takie jak promowanie zmiennej typu **`float`** do **`double`** ).

## <a name="example"></a>Przykład

```cpp
// explicit_specialization.cpp
template<class T> void f(T t)
{
};

// Explicit specialization of f with 'char' with the
// template argument explicitly specified:
//
template<> void f<char>(char c)
{
}

// Explicit specialization of f with 'double' with the
// template argument deduced:
//
template<> void f(double d)
{
}
int main()
{
}
```

## <a name="see-also"></a>Zobacz także

[Szablony funkcji](../cpp/function-templates.md)
