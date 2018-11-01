---
title: make_signed — Klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_signed
helpviewer_keywords:
- make_signed class
- make_signed
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
ms.openlocfilehash: c9fe9d54d503f1aa1dfb3debfaeb7649f2e5c18d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631650"
---
# <a name="makesigned-class"></a>make_signed — Klasa

Tworzy typ lub najmniejszą podpisem wpisz większa lub równa rozmiarze do typu.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct make_signed;

template <class T>
using make_signed_t = typename make_signed<T>::type;
```

### <a name="parameters"></a>Parametry

*T*<br/>
Typ do modyfikacji.

## <a name="remarks"></a>Uwagi

Wystąpienie modyfikatora typu przechowuje zmodyfikowany typ, który jest *T* Jeśli `is_signed<T>` prawdziwe. W przeciwnym razie jest najmniejszą typ bez znaku `UT` dla którego `sizeof (T) <= sizeof (UT)`.

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<type_traits >

**Namespace:** standardowe

## <a name="see-also"></a>Zobacz także

[<type_traits>](../standard-library/type-traits.md)<br/>
