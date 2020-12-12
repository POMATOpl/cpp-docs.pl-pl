---
description: 'Dowiedz się więcej na temat: _variant_t::D etach'
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
ms.openlocfilehash: 502903f73f9b149a5f85a6eb1be44687aab20664
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204696"
---
# <a name="_variant_tdetach"></a>_variant_t::Detach

**Specyficzne dla firmy Microsoft**

Odłącza obiekt hermetyzowany `VARIANT` z tego `_variant_t` obiektu.

## <a name="syntax"></a>Składnia

```
VARIANT Detach( );
```

## <a name="return-value"></a>Wartość zwracana

Hermetyzowane `VARIANT` .

## <a name="remarks"></a>Uwagi

Wyodrębnia i zwraca hermetyzowane `VARIANT` , a następnie czyści ten `_variant_t` obiekt bez jego niszczenia. Ta funkcja członkowska usuwa `VARIANT` hermetyzację i ustawia `VARTYPE` ten `_variant_t` obiekt na VT_EMPTY. Można zwolnić zwrócone `VARIANT` przez wywołanie funkcji [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear) .

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _variant_t](../cpp/variant-t-class.md)
