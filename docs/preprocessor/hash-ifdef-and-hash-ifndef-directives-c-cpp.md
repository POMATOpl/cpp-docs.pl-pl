---
description: 'Dowiedz się więcej na temat: dyrektywy #ifdef i #ifndef (C/C++)'
title: '#ifdef i #ifndef, dyrektywy (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#ifndef'
- '#ifdef'
helpviewer_keywords:
- '#ifdef directive'
- preprocessor, directives
- ifdef directive (#ifdef)
- ifndef directive (#ifndef)
- '#ifndef directive'
ms.assetid: 2b0be69d-9e72-45d8-8e24-e4130fb2455b
ms.openlocfilehash: 4888e4516b57465974d99b1c9e8e6393e02f68c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269292"
---
# <a name="ifdef-and-ifndef-directives-cc"></a>dyrektywy #ifdef i #ifndef (C/C++)

Dyrektywy **#ifdef** i **#ifndef** mają taki sam skutek jak dyrektywa [#if](hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md) , gdy jest ona używana ze **zdefiniowanym** operatorem.

## <a name="syntax"></a>Składnia

>  *Identyfikator* #ifdef\
>  *Identyfikator* #ifndef

Dyrektywy te są równoważne:

> **#if zdefiniowany** *Identyfikator*\
> **#if! zdefiniowany** *Identyfikator*

## <a name="remarks"></a>Uwagi

Możesz użyć dyrektyw **#ifdef** i **#ifndef** w dowolnym miejscu `#if` . Instrukcja **#ifdef** *Identifier* jest równoznaczna z, `#if 1` gdy zdefiniowano *Identyfikator* . Jest równoważne `#if 0` , gdy *Identyfikator* nie został zdefiniowany lub został niezdefiniowany przez `#undef` dyrektywę. Te dyrektywy sprawdzają tylko obecność lub brak identyfikatorów zdefiniowanych przy użyciu `#define` , a nie dla identyfikatorów zadeklarowanych w kodzie źródłowym C lub C++.

Dyrektywy te są dostępne tylko w celu zapewnienia zgodności z poprzednimi wersjami tego języka. Preferowane wyrażenie stałej **(** *Identifier* **)** używane z `#if` dyrektywą jest zalecane.

Dyrektywa **#ifndef** sprawdza przeciwieństwo warunku sprawdzonego przez **#ifdef**. Jeśli identyfikator nie został zdefiniowany lub jeśli jego definicja została usunięta z `#undef` , warunek ma wartość true (niezerowa). W przeciwnym razie warunek ma wartość false (0).

**Specyficzne dla firmy Microsoft**

*Identyfikator* można przesłać z wiersza polecenia przy użyciu [/d](../build/reference/d-preprocessor-definitions.md) opcji. Do 30 makr można określić za pomocą `/D` .

Dyrektywa **#ifdef** jest przydatna do sprawdzania, czy definicja istnieje, ponieważ definicja może być przenoszona z wiersza polecenia. Na przykład:

```cpp
// ifdef_ifndef.CPP
// compile with: /Dtest /c
#ifndef test
#define final
#endif
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Dyrektywy preprocesora](../preprocessor/preprocessor-directives.md)
