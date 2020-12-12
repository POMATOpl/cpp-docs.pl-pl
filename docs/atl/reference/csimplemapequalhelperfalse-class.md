---
description: 'Dowiedz się więcej na temat: Klasa CSimpleMapEqualHelperFalse'
title: Klasa CSimpleMapEqualHelperFalse
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
ms.openlocfilehash: 5bad8232dc1a96fc743a3526acdb86b839601d9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140585"
---
# <a name="csimplemapequalhelperfalse-class"></a>Klasa CSimpleMapEqualHelperFalse

Ta klasa jest pomocnikiem dla klasy [CSimpleMap](../../atl/reference/csimplemap-class.md) .

## <a name="syntax"></a>Składnia

```
template <class TKey, class TVal>
class CSimpleMapEqualHelperFalse
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|Ruchom Testuje dwa klucze pod kątem równości.|
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|Ruchom Zwraca wartość false.|

## <a name="remarks"></a>Uwagi

Ta klasa cech jest uzupełnieniem `CSimpleMap` klasy. Zapewnia metodę do porównywania dwóch elementów zawartych w `CSimpleMap` obiekcie, w przypadku dwóch elementów wartości lub dwóch kluczowych elementów.

Porównanie wartości zawsze zwróci wartość false, a ponadto wywoła `ATLASSERT` argument FAŁSZ, jeśli jest kiedykolwiek wywoływana. W sytuacjach, gdy test równości nie jest wystarczająco zdefiniowany, ta klasa umożliwia poprawne działanie mapy zawierającej pary klucz/wartość w przypadku większości metod, ale niepowodzenie w dobrze zdefiniowany sposób dla metod, które są zależne od porównania, takie jak [CSimpleMap:: FindVal](../../atl/reference/csimplemap-class.md#findval).

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlsimpcoll. h

## <a name="csimplemapequalhelperfalseisequalkey"></a><a name="isequalkey"></a> CSimpleMapEqualHelperFalse::IsEqualKey

Testuje dwa klucze pod kątem równości.

```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```

### <a name="parameters"></a>Parametry

*K1*<br/>
Pierwszy klucz.

*K2*<br/>
Drugi klucz.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość true, jeśli klucze są równe, w przeciwnym razie false.

### <a name="remarks"></a>Uwagi

Ta metoda wywołuje [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md).

## <a name="csimplemapequalhelperfalseisequalvalue"></a><a name="isequalvalue"></a> CSimpleMapEqualHelperFalse::IsEqualValue

Zwraca wartość false.

```
static bool IsEqualValue(const TVal&, const TVal&);
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość false.

### <a name="remarks"></a>Uwagi

Ta metoda zawsze zwraca wartość false i wywołuje `ATLASSERT` z argumentem false, jeśli jest kiedykolwiek wywoływana. Celem `CSimpleMapEqualHelperFalse::IsEqualValue` jest wymuszenie stosowania przez metody porównania metod niepowodzenia w dobrze zdefiniowany sposób, gdy testy równości nie zostały prawidłowo zdefiniowane.

## <a name="see-also"></a>Zobacz też

[Klasa CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
