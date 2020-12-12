---
description: Dowiedz się więcej na temat klasy is_trivially_copy_constructible
title: is_trivially_copy_constructible — klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
ms.openlocfilehash: c247e81f52ad98e546a840bb38938fe15bc9b302
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118527"
---
# <a name="is_trivially_copy_constructible-class"></a>is_trivially_copy_constructible — klasa

Testuje, czy typ ma Konstruktor prostego kopiowania.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct is_trivially_copy_constructible;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *T* jest klasą, która ma Konstruktor kopiujący, w przeciwnym razie ma wartość false.

Konstruktor kopiujący dla klasy *t* jest uproszczony, jeśli jest niejawnie zadeklarowany, Klasa *t* nie ma żadnych funkcji wirtualnych ani wirtualnych baz danych, wszystkie bezpośrednie bazy klasy *t* mają konstruktory prostej kopii, klasy wszystkich niestatycznych elementów członkowskich typu klasy mają konstruktory prostej kopii, a klasy wszystkich niestatycznych elementów członkowskich danych typu Array klasy mają konstruktory proste kopiujące.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
