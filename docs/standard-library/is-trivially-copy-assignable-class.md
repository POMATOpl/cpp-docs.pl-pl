---
description: Dowiedz się więcej na temat klasy is_trivially_copy_assignable
title: Klasa is_trivially_copy_assignable
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
ms.openlocfilehash: 010e820db570f594568cb60f4edae83b91a997c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271242"
---
# <a name="is_trivially_copy_assignable-class"></a>Klasa is_trivially_copy_assignable

Testuje, czy typ ma operator przypisania prostego kopiowania.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *T* jest klasą, która ma operator przypisania prostego kopiowania, w przeciwnym razie zawiera wartość false.

Konstruktor przypisania dla klasy *t* jest uproszczony, jeśli jest niejawnie określony, Klasa *t* nie ma żadnych funkcji wirtualnych, Klasa *t* nie ma żadnych wirtualnych podstaw, klasy wszystkich niestatycznych elementów członkowskich danych typu klasy mają proste operatory przypisania, a klasy wszystkich niestatycznych elementów członkowskich danych typu Array klasy mają proste operatory przypisania.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
