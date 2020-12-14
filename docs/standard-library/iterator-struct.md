---
description: Dowiedz się więcej na temat struktury iteratora
title: iterator — Struktura
ms.date: 11/04/2016
f1_keywords:
- xutility/std::iterator
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
ms.openlocfilehash: 81a35fd749b3393a0235fdac8c4bf13a1ef5af79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254329"
---
# <a name="iterator-struct"></a>iterator — Struktura

Pusta struktura podstawowa używana do upewnienia się, że Klasa iteratora zdefiniowana przez użytkownika działa prawidłowo z `iterator_trait` s.

## <a name="syntax"></a>Składnia

```cpp
struct iterator {
   typedef Category iterator_category;
   typedef Type value_type;
   typedef Distance difference_type;
   typedef Distance distance_type;
   typedef Pointer pointer;
   typedef Reference reference;
   };
```

## <a name="remarks"></a>Uwagi

Struktura szablonu służy jako typ podstawowy dla wszystkich iteratorów. Definiuje typy elementów członkowskich

- `iterator_category` (synonim dla parametru szablonu `Category` ).

- `value_type` (synonim dla parametru szablonu `Type` ).

- `difference_type` (synonim dla parametru szablonu `Distance` ).

- `distance_type` (synonim dla parametru szablonu `Distance` )

- `pointer` (synonim dla parametru szablonu `Pointer` ).

- `reference` (synonim dla parametru szablonu `Reference` ).

Należy zauważyć, że `value_type` nie powinien być typem stałym, nawet jeśli `pointer` punkty w obiekcie **`const`** `Type` i Reference wyznaczają obiekt **`const`** `Type` .

## <a name="example"></a>Przykład

Zobacz [iterator_traits](../standard-library/iterator-traits-struct.md) , aby zapoznać się z przykładem sposobu deklarowania typów w klasie bazowej iteratora i korzystania z nich.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<iterator>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[\<iterator>](../standard-library/iterator.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Dokumentacja standardowej biblioteki języka C++](../standard-library/cpp-standard-library-reference.md)
