---
description: 'Dowiedz się więcej na temat: _variant_t:: SetString'
title: _variant_t::SetString
ms.date: 11/04/2016
f1_keywords:
- _variant_t::SetString
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
ms.openlocfilehash: a36bab9189b6046325bb275469dc9dbdb495fc7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161419"
---
# <a name="_variant_tsetstring"></a>_variant_t::SetString

**Specyficzne dla firmy Microsoft**

Przypisuje ciąg do tego `_variant_t` obiektu.

## <a name="syntax"></a>Składnia

```cpp
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>Parametry

*pSrc*<br/>
Wskaźnik do ciągu znaków.

## <a name="remarks"></a>Uwagi

Konwertuje ciąg znaków ANSI na `BSTR` ciąg Unicode i przypisuje go do tego `_variant_t` obiektu.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _variant_t](../cpp/variant-t-class.md)
