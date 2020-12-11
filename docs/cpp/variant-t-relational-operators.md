---
description: 'Dowiedz się więcej o: _variant_t operatory relacyjne'
title: _variant_t — Operatory relacyjne
ms.date: 11/04/2016
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
helpviewer_keywords:
- '!= operator'
- relational operators [C++], _variant_t class
- operator!= [C++], variant
- operator!= [C++], relational operators
- operator != [C++], variant
- operator == [C++], variant
- operator== [C++], variant
- operator != [C++], relational operators
- == operator [C++], with specific Visual C++ objects
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
ms.openlocfilehash: 0a9c339bc67527e258c0d1f69060cde251c8adb9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161432"
---
# <a name="_variant_t-relational-operators"></a>_variant_t — Operatory relacyjne

**Specyficzne dla firmy Microsoft**

Porównaj dwa `_variant_t` obiekty pod kątem równości lub nierówności.

## <a name="syntax"></a>Składnia

```
bool operator==(
   const VARIANT& varSrc) const;
bool operator==(
   const VARIANT* pSrc) const;
bool operator!=(
   const VARIANT& varSrc) const;
bool operator!=(
   const VARIANT* pSrc) const;
```

#### <a name="parameters"></a>Parametry

*varSrc*<br/>
Wartość `VARIANT` do porównania z `_variant_t` obiektem.

*pSrc*<br/>
Wskaźnik do `VARIANT` porównania z `_variant_t` obiektem.

## <a name="return-value"></a>Wartość zwracana

Zwraca wartość **`true`** , jeśli porównanie **`false`** ma być przechowywane.

## <a name="remarks"></a>Uwagi

Porównuje `_variant_t` obiekt z `VARIANT` , testowaniem pod kątem równości lub nierówności.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _variant_t](../cpp/variant-t-class.md)
