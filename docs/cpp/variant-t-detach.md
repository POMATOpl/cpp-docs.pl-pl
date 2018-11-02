---
title: _variant_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
ms.openlocfilehash: 4b19e3c1615912550cdf1eb6a2b0b3f906ee4af9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522333"
---
# <a name="varianttdetach"></a>_variant_t::Detach

**Microsoft Specific**

Odłącza zhermetyzowany `VARIANT` obiektu z tego `_variant_t` obiektu.

## <a name="syntax"></a>Składnia

```
VARIANT Detach( );
```

## <a name="return-value"></a>Wartość zwracana

Zhermetyzowany `VARIANT`.

## <a name="remarks"></a>Uwagi

Wyodrębnia i zwraca zhermetyzowany `VARIANT`, powoduje to wyczyszczenie `_variant_t` obiektu bez niszczenia samego go. Ta funkcja członkowska usuwa `VARIANT` z hermetyzacji i zestawy `VARTYPE` tego `_variant_t` obiektu VT_EMPTY. To pozwala zwolnić zwracanego `VARIANT` przez wywołanie metody [VariantClear](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantclear) funkcji.

**END specyficzny dla Microsoft**

## <a name="see-also"></a>Zobacz także

[_variant_t, klasa](../cpp/variant-t-class.md)