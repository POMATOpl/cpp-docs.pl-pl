---
description: Dowiedz się więcej o strukturze IsBaseOfStrict
title: IsBaseOfStrict — Struktura
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
- internal/Microsoft::WRL::Details::IsBaseOfStrict::value
helpviewer_keywords:
- Microsoft::WRL::Details::IsBaseOfStrict structure
- Microsoft::WRL::Details::IsBaseOfStrict::value constant
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
ms.openlocfilehash: bcdab9c4b6b5a2ab108b59d3127c08b53589e16a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298958"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict — Struktura

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
template <typename Base, typename Derived>
struct IsBaseOfStrict;

template <typename Base>
struct IsBaseOfStrict<Base, Base>;
```

### <a name="parameters"></a>Parametry

*Opiera*<br/>
Typ podstawowy.

*Pochodne*<br/>
Typ pochodny.

## <a name="remarks"></a>Uwagi

Testuje, czy jeden typ jest podstawą innego.

Pierwszy szablon testuje, czy typ pochodzi od typu podstawowego, co może powieść **`true`** lub **`false`** . Drugi szablon testuje, czy typ pochodzi od samego siebie, co zawsze jest wynikiem **`false`** .

## <a name="members"></a>Elementy członkowskie

### <a name="public-constants"></a>Stałe publiczne

Nazwa                            | Opis
------------------------------- | --------------------------------------------------
[IsBaseOfStrict:: value](#value) | Wskazuje, czy jeden typ jest podstawą innego.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`IsBaseOfStrict`

## <a name="requirements"></a>Wymagania

**Nagłówek:** Internal. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="isbaseofstrictvalue"></a><a name="value"></a> IsBaseOfStrict:: value

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
static const bool value = __is_base_of(Base, Derived);
```

### <a name="remarks"></a>Uwagi

Wskazuje, czy jeden typ jest podstawą innego.

`value` jest **`true`** Jeśli typ `Base` jest klasą bazową typu `Derived` , w przeciwnym razie **`false`** .
