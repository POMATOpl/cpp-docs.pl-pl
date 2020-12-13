---
description: Dowiedz się więcej na temat klasy type_index
title: type_index — Klasa
ms.date: 11/04/2016
f1_keywords:
- typeindex/std::type_index
helpviewer_keywords:
- type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
ms.openlocfilehash: 4e9156420811d2712a5b9331d0ece0e7847103e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142691"
---
# <a name="type_index-class"></a>type_index — Klasa

`type_index`Klasa zawija wskaźnik do [klasy type_info](../cpp/type-info-class.md) , aby ułatwić indeksowanie według takich obiektów.

Klasa type_index {Public: type_index (const type_info& tInfo); const char * Name () const; size_t hash_code () const; operator bool = = (const type_info& Right) const; operator bool! = (const type_info& Right) const; operator bool< (const type_info& Right) const; operator bool \<=(const type_info& right) const;
   bool operator> (const type_info& Right) const; operator logiczny>= (const type_info& Right) const;};

Konstruktor inicjuje `ptr` się do `&tinfo` .

`name` Zwraca wartość `ptr->name()` .

`hash_code` typu `ptr->hash_code().`

`operator==` Zwraca wartość `*ptr == right.ptr` .

`operator!=` Zwraca wartość `!(*this == right)` .

`operator<` Zwraca wartość `*ptr->before(*right.ptr)` .

`operator<=` typu `!(right < *this).`

`operator>` Zwraca wartość `right < *this` .

`operator>=` Zwraca wartość `!(*this < right)` .

## <a name="see-also"></a>Zobacz też

[Informacje o typie w czasie wykonywania](../cpp/run-time-type-information.md)\
[\<typeindex>](../standard-library/typeindex.md)
