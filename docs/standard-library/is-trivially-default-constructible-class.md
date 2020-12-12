---
description: Dowiedz się więcej na temat klasy is_trivially_default_constructible
title: is_trivially_default_constructible — klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_default_constructible
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
ms.openlocfilehash: 3686dab86b8bf04fe7629b53651988d7ccef161e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118410"
---
# <a name="is_trivially_default_constructible-class"></a>is_trivially_default_constructible — klasa

Testuje, czy typ ma prosty Konstruktor domyślny.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
struct is_trivially_default_constructible;
```

### <a name="parameters"></a>Parametry

*Br*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *ty* jest klasą, która ma prosty Konstruktor, w przeciwnym razie ma wartość false.

Domyślny konstruktor dla klasy *ty* jest prosty, jeśli:

- jest to niejawnie zadeklarowany Konstruktor domyślny

- Klasa *ty* nie ma żadnych funkcji wirtualnych

- Klasa *ty* nie ma wirtualnych baz.

- wszystkie bezpośrednie bazy klasy *ty* mają uproszczone konstruktory

- klasy wszystkich niestatycznych składowych danych typu klasy mają proste konstruktory

- klasy wszystkich niestatycznych składowych danych typu Array klasy mają proste konstruktory

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
