---
description: Dowiedz się więcej na temat przechowywania typów podstawowych
title: Magazyn typów podstawowych
ms.date: 10/02/2019
helpviewer_keywords:
- specifiers [C++], type
- integral types, storage
- storage [C++], types
- floating-point numbers, storage
- type specifiers [C++], sizes
- arithmetic operations [C++], types
- int data type
- short data type
- signed types [C++], storage
- long double keyword [C], storage
- long keyword [C]
- double data type, storage
- types [C], arithmetic
- integral types
- data types [C], specifiers
- storing types [C++]
- unsigned types [C++], storage
- data types [C], storage
ms.assetid: bd1f33c1-c6b9-4558-8a72-afb21aef3318
ms.openlocfilehash: c8ae057de19e04327491fd73e45bcd32c1db7738
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296644"
---
# <a name="storage-of-basic-types"></a>Magazyn typów podstawowych

Poniższa tabela zawiera podsumowanie magazynu skojarzonego z każdym typem podstawowym.

## <a name="sizes-of-fundamental-types"></a>Rozmiary typów podstawowych

|Typ|Przechowywanie|
|----------|-------------|
|**`char`**, **`unsigned char`**, **`signed char`**|1 bajt|
|**`short`**, **`unsigned short`**|2 bajty|
|**`int`**, **`unsigned int`**|4 bajty|
|**`long`**, **`unsigned long`**|4 bajty|
|**`long long`**, **`unsigned long long`**|8 bajtów|
|**`float`**|4 bajty|
|**`double`**|8 bajtów|
|**`long double`**|8 bajtów|

Typy danych języka C są podzielone na kategorie ogólne. *Typy całkowite* obejmują **`int`** ,, **`char`** , **`short`** **`long`** , i **`long long`** . Te typy mogą być kwalifikowane przy użyciu **`signed`** lub **`unsigned`** , i **`unsigned`** mogą być używane jako skróty dla **`unsigned int`** . Typy wyliczeniowe ( **`enum`** ) również są traktowane jako typy całkowite w większości celów. *Typy przestawne* obejmują **`float`** , **`double`** , i **`long double`** . *Typy arytmetyczne* obejmują wszystkie typy zmiennoprzecinkowe i całkowite.

## <a name="see-also"></a>Zobacz też

[Deklaracje i typy](../c-language/declarations-and-types.md)
