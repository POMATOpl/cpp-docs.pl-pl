---
description: 'Dowiedz się więcej na temat: _variant_t:: Attach'
title: _variant_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
ms.openlocfilehash: de13b1e8138eb24971e52165ee84fc92d97ca3d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116655"
---
# <a name="_variant_tattach"></a>_variant_t::Attach

**Specyficzne dla firmy Microsoft**

Dołącza `VARIANT` obiekt do obiektu **_variant_t** .

## <a name="syntax"></a>Składnia

```cpp
void Attach(VARIANT& varSrc);
```

#### <a name="parameters"></a>Parametry

*varSrc*<br/>
`VARIANT`Obiekt, który ma zostać dołączony do tego obiektu **_variant_t** .

## <a name="remarks"></a>Uwagi

Przejmuje własność `VARIANT` przez hermetyzację. Ta funkcja członkowska zwalnia wszystkie istniejące hermetyzowane `VARIANT` , a następnie kopiuje podane dane `VARIANT` i ustawia `VARTYPE` je do VT_EMPTY, aby upewnić się, że jego zasoby mogą być wydane tylko przez destruktor **_variant_t** .

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _variant_t](../cpp/variant-t-class.md)
