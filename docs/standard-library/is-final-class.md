---
description: Dowiedz się więcej na temat klasy is_final
title: Klasa is_final
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_final
helpviewer_keywords:
- is_final
ms.assetid: 9dbad82f-6685-4909-94e8-98e4a93994b9
ms.openlocfilehash: 04660309205689e14200cb5d214ce5dc80efb88f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323744"
---
# <a name="is_final-class"></a>Klasa is_final

Testuje, czy typ jest oznaczony typem klasy `final` .

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct is_final;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *T* jest oznaczony jako typ klasy `final` , w przeciwnym razie ma wartość false. Jeśli *T* jest typem klasy, musi być kompletnym typem.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)\
[końcowy specyfikator](../cpp/final-specifier.md)
