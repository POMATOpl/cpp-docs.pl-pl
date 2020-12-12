---
description: 'Dowiedz się więcej na temat: błąd kompilatora C3200'
title: Błąd kompilatora C3200
ms.date: 11/04/2016
f1_keywords:
- C3200
helpviewer_keywords:
- C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
ms.openlocfilehash: c693878628ff0bd9dddcb2f100ca652910b0fb89
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330666"
---
# <a name="compiler-error-c3200"></a>Błąd kompilatora C3200

"template": nieprawidłowy argument szablonu dla parametru szablonu "parameter", oczekiwano szablonu klasy

Przeszedł nieprawidłowy argument do szablonu klasy. Szablon klasy oczekuje szablonu jako parametru. W poniższym przykładzie wywołanie `Y<int, int> aY` spowoduje wygenerowanie funkcji C3200. Pierwszy parametr musi być szablonem, na przykład `Y<X, int> aY` .

```cpp
// C3200.cpp
template<typename T>
class X
{
};

template<template<typename U> class T1, typename T2>
class Y
{
};

int main()
{
   Y<int, int> y;   // C3200
}
```
