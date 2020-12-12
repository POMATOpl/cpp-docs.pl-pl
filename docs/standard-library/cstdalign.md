---
description: 'Dowiedz się więcej na temat: &lt; cstdalign&gt;'
title: '&lt;cstdalign&gt;'
ms.date: 07/11/2019
f1_keywords:
- <cstdalign>
- cstdalign
- __alignas_is_defined
- __alignof_is_defined
helpviewer_keywords:
- cstdalign header
- __alignas_is_defined
- __alignof_is_defined
ms.assetid: 9d570924-d299-4225-9a58-8c4c820f5903
ms.openlocfilehash: 149893b33ead3e66223b9124ff7c1b6346929799
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324751"
---
# <a name="ltcstdaligngt"></a>&lt;cstdalign&gt;

W niektórych implementacjach standardowej biblioteki C++ ten nagłówek zawiera nagłówek standardowej biblioteki C \<stdalign.h> i dodaje skojarzone nazwy do `std` przestrzeni nazw. Ponieważ ten nagłówek nie jest zaimplementowany w MSVC, \<cstdalign> nagłówek definiuje makra zgodności `__alignas_is_defined` i `__alignof_is_defined` .

> [!NOTE]
> Ponieważ \<stdalign.h> nagłówek definiuje makra, które są słowami kluczowymi w języku C++, w tym nie ma żadnego wpływu. \<stdalign.h>Nagłówek jest przestarzały w języku C++. \<cstdalign>Nagłówek jest przestarzały w języku c++ 17 i został usunięty z wersji Standard c++ 20.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<cstdalign>

**Przestrzeń nazw:** std

## <a name="macros"></a>Makra

| Makro | Opis |
| - | - |
| `__alignas_is_defined` | Makro zgodności C, które rozwija się do stałej całkowitej 1. |
| `__alignof_is_defined` | Makro zgodności C, które rozwija się do stałej całkowitej 1. |

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](cpp-standard-library-header-files.md)\
[Omówienie standardowej biblioteki języka C++](cpp-standard-library-overview.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](thread-safety-in-the-cpp-standard-library.md)
