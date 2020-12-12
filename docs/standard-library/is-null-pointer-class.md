---
description: Dowiedz się więcej na temat klasy is_null_pointer
title: Klasa is_null_pointer
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_null_pointer
helpviewer_keywords:
- is_null_pointer
ms.assetid: f3b3601b-f162-4803-a6e9-dabf5c3876cc
ms.openlocfilehash: 91a8b6a27668af72d7641ce1fe36dafc119f5aa7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230669"
---
# <a name="is_null_pointer-class"></a>Klasa is_null_pointer

Testuje, czy typem jest std:: nullptr_t.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct is_null_pointer;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *T* jest `std::nullptr_t` , w przeciwnym razie ma wartość false.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
