---
description: 'Dowiedz się więcej o: błąd kompilatora C3201'
title: Błąd kompilatora C3201
ms.date: 11/04/2016
f1_keywords:
- C3201
helpviewer_keywords:
- C3201
ms.assetid: ec19cd64-1789-40a3-b2db-dff2852b9d98
ms.openlocfilehash: 3cd6e037cd9dbb0638040e2f3eca61dab1dabb46
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330653"
---
# <a name="compiler-error-c3201"></a>Błąd kompilatora C3201

Lista parametrów szablonu dla szablonu klasy "template" nie jest zgodna z listą parametrów szablonu dla parametru szablonu "template"

W argumencie nie przeszedł szablonu klasy, który nie przyjmuje parametru szablonu lub przeszedł niezgodną liczbę argumentów szablonu dla domyślnego argumentu szablonu.

```cpp
// C3201.cpp
template<typename T1, typename T2>
class X1
{
};

template<template<typename T> class U = X1>   // C3201
class X2
{
};

template<template<typename T, typename V> class U = X1>   // OK
class X3
{
};
```
