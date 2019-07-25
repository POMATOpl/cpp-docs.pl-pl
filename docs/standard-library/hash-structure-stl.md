---
title: Struktura skrótu (C++ standardowa biblioteka) | Microsoft Docs
ms.date: 11/04/2016
f1_keywords:
- thread/std::hash
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
ms.openlocfilehash: e6d0cea7bfc8cd745e7276f7fc29d493f178fc9b
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451947"
---
# <a name="hash-structure-c-standard-library"></a>Struktura skrótu (C++ standardowa biblioteka)

Definiuje funkcję członkowską, która zwraca wartość, która jest jednoznacznie określona `Val`przez. Funkcja członkowska definiuje funkcję [mieszania](../standard-library/hash-class.md) , która jest odpowiednia do mapowania wartości typu `thread::id` na rozkład wartości indeksu.

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

**Nagłówek:** \<> wątku

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz także

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[\<> wątku](../standard-library/thread.md)\
[unary_function, struktura](../standard-library/unary-function-struct.md)
