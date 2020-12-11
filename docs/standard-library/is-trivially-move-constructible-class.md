---
description: Dowiedz się więcej na temat klasy is_trivially_move_constructible
title: Klasa is_trivially_move_constructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_move_constructible
helpviewer_keywords:
- is_trivially_move_constructible
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
ms.openlocfilehash: 30e8be25e74aeed1eafc8fcafbece5c62e4ad999
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154321"
---
# <a name="is_trivially_move_constructible-class"></a>Klasa is_trivially_move_constructible

Testuje, czy typ ma Konstruktor prostego przenoszenia.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>Parametry

*Br*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *ty* jest klasą, która ma prosty Konstruktor przenoszenia, w przeciwnym razie ma wartość false.

Konstruktor przenoszenia dla klasy *ty* jest prosty, jeśli:

jest on niejawnie zadeklarowany

jego typy parametrów są równoważne z niejawną deklaracją

Klasa *ty* nie ma żadnych funkcji wirtualnych

Klasa *ty* nie ma wirtualnych baz.

Klasa nie ma niestatycznych elementów członkowskich danych

wszystkie bezpośrednie bazy klasy *ty* mają konstruktorów prostego przenoszenia

klasy wszystkich niestatycznych składowych danych typu klasy mają konstruktorów prostych przenoszenia

klasy wszystkich niestatycznych składowych danych typu Array klasy mają konstruktorów prostego przenoszenia

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
