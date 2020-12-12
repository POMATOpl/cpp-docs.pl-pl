---
description: 'Dowiedz się więcej na temat: _variant_t:: ChangeType'
title: _variant_t::ChangeType
ms.date: 11/04/2016
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
ms.openlocfilehash: 32ce43f1d9afb388c97e5271927113c71d31bb92
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116629"
---
# <a name="_variant_tchangetype"></a>_variant_t::ChangeType

**Specyficzne dla firmy Microsoft**

Zmienia typ `_variant_t` obiektu na wskazany `VARTYPE` .

## <a name="syntax"></a>Składnia

```cpp
void ChangeType(
   VARTYPE vartype,
   const _variant_t* pSrc = NULL
);
```

#### <a name="parameters"></a>Parametry

*VARTYPE*<br/>
`VARTYPE`Dla tego `_variant_t` obiektu.

*pSrc*<br/>
Wskaźnik do `_variant_t` obiektu do przekonwertowania. Jeśli ta wartość jest RÓWNa NULL, konwersja jest wykonywana na miejscu.

## <a name="remarks"></a>Uwagi

Ta funkcja członkowska konwertuje `_variant_t` obiekt na wskazany `VARTYPE` . Jeśli *pSrc* ma wartość null, konwersja jest wykonywana, w przeciwnym razie ten `_variant_t` obiekt jest kopiowany z *pSrc* , a następnie konwertowany.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _variant_t](../cpp/variant-t-class.md)
