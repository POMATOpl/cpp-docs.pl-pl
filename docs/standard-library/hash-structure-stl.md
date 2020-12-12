---
description: Dowiedz się więcej na temat struktury skrótu (standardowa biblioteka C++)
title: Hash — struktura (standardowa biblioteka C++) | Microsoft Docs
ms.date: 11/04/2016
f1_keywords:
- thread/std::hash
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
ms.openlocfilehash: 095566b6855c837c3ee6049a5cbedfbb087420bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324071"
---
# <a name="hash-structure-c-standard-library"></a>hash, struktura (Standardowa biblioteka C++)

Definiuje funkcję członkowską, która zwraca wartość, która jest jednoznacznie określona przez `Val` . Funkcja członkowska definiuje funkcję [mieszania](../standard-library/hash-class.md) , która jest odpowiednia do mapowania wartości typu `thread::id` na rozkład wartości indeksu.

## <a name="syntax"></a>Składnia

```cpp
template <>
struct hash<thread::id> :
    public unary_function<thread::id, size_t>
{
    size_t operator()(thread::id Val) const;

};
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<thread>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[\<thread>](../standard-library/thread.md)\
[Struktura unary_function](../standard-library/unary-function-struct.md)
