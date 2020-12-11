---
description: Dowiedz się więcej na temat klasy is_trivially_move_assignable
title: Klasa is_trivially_move_assignable
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_move_assignable
helpviewer_keywords:
- is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
ms.openlocfilehash: 3f852bd2b1ccf3647a4aa05bb5996f015341b342
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154334"
---
# <a name="is_trivially_move_assignable-class"></a>Klasa is_trivially_move_assignable

Testuje, czy typ ma operator przypisania prostego przenoszenia.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Parametry

*Br*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *ty* jest klasą, która ma operator przypisania prostego przenoszenia, w przeciwnym razie ma wartość false.

Operator przypisania przenoszenia dla klasy *ty* jest prosty, jeśli:

- jest to niejawnie podane
- Klasa *ty* nie ma żadnych funkcji wirtualnych
- Klasa *ty* nie ma wirtualnych baz.
- klasy wszystkich niestatycznych elementów członkowskich danych typu klasy mają operatory przypisania prostego przenoszenia
- klasy wszystkich niestatycznych składowych danych typu Array klasy mają operatory przypisania prostego przenoszenia

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
