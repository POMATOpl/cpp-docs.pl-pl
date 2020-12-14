---
description: 'Dowiedz się więcej o: makra i C++'
title: Makra i język C++
ms.date: 08/29/2019
helpviewer_keywords:
- macros, C++
- macros
ms.assetid: 83a344c1-73c9-4ace-8b93-cccfb62c6133
ms.openlocfilehash: 2ec4db1e36bf18c23567c8c513bdc5e15ec613a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333437"
---
# <a name="macros-and-c"></a>Makra i język C++

Język C++ oferuje nowe możliwości, a niektóre z nich supplant, które są oferowane przez preprocesor ANSI C. Te nowe funkcje rozszerzają bezpieczeństwo typów i przewidywalność języka:

- W języku C++ obiekty zadeklarowane jako **`const`** mogą być używane w wyrażeniach stałych. Umożliwia to programom deklarowanie stałych, które mają informacje o typie i wartości. Mogą deklarować wyliczenia, które mogą być wyświetlane symbolicznie z debugerem. W przypadku używania dyrektywy preprocesora `#define` do definiowania stałych nie jest to dokładne i nie jest bezpieczna pod względem typów. Nie przydzielono żadnego magazynu dla **`const`** obiektu, chyba że program zawiera wyrażenie, które pobiera jego adres.

- Funkcja funkcji wbudowanych języka C++ wypierają wcześniejszą makra typu Function. Zalety korzystania z funkcji wbudowanych przez makra to:

  - Bezpieczeństwo typu. Funkcje wbudowane podlegają takie samomu sprawdzaniu typu jak normalne funkcje. Makra nie są bezpieczne dla typów.

  - Poprawna obsługa argumentów z efektami ubocznymi. Funkcje wbudowane obliczają wyrażenia dostarczone jako argumenty przed wprowadzeniem treści funkcji. W związku z tym nie istnieje prawdopodobieństwo, że wyrażenie z efektami ubocznymi nie będzie bezpieczne.

Aby uzyskać więcej informacji na temat funkcji wbudowanych, zobacz [inline, __inline, \_ _forceinline](../cpp/inline-functions-cpp.md).

W celu zapewnienia zgodności z poprzednimi wersjami wszystkie obiekty preprocesora, które istniały w ANSI C i we wcześniejszych specyfikacjach języka C++, są zachowywane w programie Microsoft C++.

## <a name="see-also"></a>Zobacz też

[Wstępnie zdefiniowane makra](../preprocessor/predefined-macros.md)\
[Makra (C/C++)](../preprocessor/macros-c-cpp.md)
