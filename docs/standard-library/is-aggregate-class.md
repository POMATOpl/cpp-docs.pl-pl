---
description: Dowiedz się więcej na temat klasy is_aggregate
title: Klasa is_aggregate
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_aggregate
helpviewer_keywords:
- is_aggregate
ms.openlocfilehash: 6ca27e6edea42b6c0ae3f0c89749a586adac857b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231371"
---
# <a name="is_aggregate-class"></a>Klasa is_aggregate

Testuje, czy typ jest oznaczony typem klasy `aggregate` .

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct is_aggregate;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *T* jest oznaczony jako typ klasy `aggregate` , w przeciwnym razie ma wartość false. Jeśli *T* jest typem klasy, musi być kompletnym typem.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
