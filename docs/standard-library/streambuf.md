---
description: 'Dowiedz się więcej na temat: &lt; streambuf&gt;'
title: '&lt;streambuf&gt;'
ms.date: 11/04/2016
f1_keywords:
- <streambuf>
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
ms.openlocfilehash: 417b31b919c95d8aef741b2988c576ff6454ce4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183766"
---
# <a name="ltstreambufgt"></a>&lt;streambuf&gt;

Dołącz standardowy nagłówek iostreams \<streambuf> , aby zdefiniować szablon klasy [basic_streambuf](../standard-library/basic-streambuf-class.md), który jest podstawowy dla operacji klas iostreams. Ten nagłówek jest zwykle dołączany przez inny z nagłówków iostreams; rzadko trzeba dołączyć go bezpośrednio.

## <a name="syntax"></a>Składnia

```cpp
#include <streambuf>
```

### <a name="typedefs"></a>Typedefs

|Nazwa typu|Opis|
|-|-|
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|Specjalizacja `basic_streambuf` , która używa **`char`** jako parametrów szablonu.|
|[wstreambuf —](../standard-library/streambuf-typedefs.md#wstreambuf)|Specjalizacja `basic_streambuf` , która używa **`wchar_t`** jako parametrów szablonu.|

### <a name="classes"></a>Klasy

|Klasa|Opis|
|-|-|
|[Klasa basic_streambuf](basic-streambuf-class.md)|Szablon klasy opisuje abstrakcyjną klasę bazową dla tworzenia bufora strumienia, która kontroluje przekazywanie elementów do i z określonej reprezentacji strumienia.|

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Programowanie iostream](../standard-library/iostream-programming.md)\
[Konwencje iostreams](../standard-library/iostreams-conventions.md)
