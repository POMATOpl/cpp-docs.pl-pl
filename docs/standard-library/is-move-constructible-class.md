---
description: Dowiedz się więcej na temat klasy is_move_constructible
title: is_move_constructible, klasa
ms.date: 10/24/2019
f1_keywords:
- type_traits/std::is_move_constructible
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
ms.openlocfilehash: 05ef640b2841eb3ab66f6d5a6d3b8ede7acf2754
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323636"
---
# <a name="is_move_constructible-class"></a>is_move_constructible, klasa

Testuje, czy typ można utworzyć przy użyciu operacji przenoszenia.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do obliczenia.

## <a name="remarks"></a>Uwagi

Predykat typu, który jest obliczany w **`true`** przypadku, gdy typ *T* może być skonstruowany przy użyciu operacji przenoszenia. Ten predykat jest odpowiednikiem `is_constructible<T, T&&>` . Typ *T* , który nie ma konstruktora Move, ale ma Konstruktor kopiujący, który akceptuje `const T&` argument, jest zgodny `std::is_move_constructible` .

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
