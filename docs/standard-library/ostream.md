---
description: 'Dowiedz się więcej na temat: &lt; ostream&gt;'
title: '&lt;ostream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <ostream>
- ostream/std::<ostream>
- std::<ostream>
helpviewer_keywords:
- ostream header
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
ms.openlocfilehash: 3b17ff221e08b9fc709f1d2c32c5862f6075e451
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193035"
---
# <a name="ltostreamgt"></a>&lt;ostream&gt;

Definiuje [basic_ostream](../standard-library/basic-ostream-class.md)szablonu klasy, który koryguje wstawienia dla iostreams. Nagłówek definiuje również kilka powiązanych manipulowania. (Ten nagłówek jest zazwyczaj dołączany przez inny iostreams nagłówków. Rzadko trzeba dołączyć go bezpośrednio.

## <a name="syntax"></a>Składnia

```cpp
#include <ostream>
```

### <a name="typedefs"></a>Typedefs

|Nazwa typu|Opis|
|-|-|
|[ostream](../standard-library/ostream-typedefs.md#ostream)|Tworzy typ `basic_ostream` , który jest wyspecjalizowany **`char`** i `char_traits` wyspecjalizowany w **`char`** .|
|[wostream —](../standard-library/ostream-typedefs.md#wostream)|Tworzy typ `basic_ostream` , który jest wyspecjalizowany **`wchar_t`** i `char_traits` wyspecjalizowany w **`wchar_t`** .|

### <a name="manipulators"></a>Manipulatory

|Nazwa|Opis|
|-|-|
|[endl](../standard-library/ostream-functions.md#endl)|Kończy wiersz i opróżnia bufor.|
|[celów](../standard-library/ostream-functions.md#ends)|Kończy ciąg.|
|[opróżnianie](../standard-library/ostream-functions.md#flush)|Opróżnia bufor.|
|[wymiany](../standard-library/ostream-functions.md#swap)|Wymienia wartości `basic_ostream` parametru lewego obiektu dla tych z `basic_ostream` parametrem właściwego obiektu.|

### <a name="operators"></a>Operatory

|Operator|Opis|
|-|-|
|[<<operatora ](../standard-library/ostream-operators.md#op_lt_lt)|Zapisuje różne typy w strumieniu.|

### <a name="classes"></a>Klasy

|Klasa|Opis|
|-|-|
|[basic_ostream](../standard-library/basic-ostream-class.md)|Szablon klasy opisuje obiekt, który kontroluje Wstawianie elementów i zakodowanych obiektów do buforu strumienia.|

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Programowanie iostream](../standard-library/iostream-programming.md)\
[Konwencje iostreams](../standard-library/iostreams-conventions.md)
