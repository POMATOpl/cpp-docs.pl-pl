---
description: 'Dowiedz się więcej na temat: Klasa CSimpleMapEqualHelper'
title: Klasa CSimpleMapEqualHelper
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
ms.openlocfilehash: 2b8ff742bf24b6c6c4354cef652e3fc697ffb1d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140611"
---
# <a name="csimplemapequalhelper-class"></a>Klasa CSimpleMapEqualHelper

Ta klasa jest pomocnikiem dla klasy [CSimpleMap](../../atl/reference/csimplemap-class.md) .

## <a name="syntax"></a>Składnia

```
template <class TKey, class TVal>
class CSimpleMapEqualHelper
```

#### <a name="parameters"></a>Parametry

*TKey*<br/>
Element klucza.

*TVal*<br/>
Wartość elementu.

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|Ruchom Testuje dwa klucze pod kątem równości.|
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|Ruchom Testuje dwie wartości pod kątem równości.|

## <a name="remarks"></a>Uwagi

Ta klasa cech jest uzupełnieniem `CSimpleMap` klasy. Zapewnia metody do porównywania dwóch `CSimpleMap` elementów obiektów (w odniesieniu do składników klucza i wartości) dla równości. Domyślnie klucze i wartości są porównywane przy użyciu **operatora = = ()**, ale jeśli mapa zawiera złożone typy danych, które nie mają własnego operatora równości, ta klasa może zostać przesłonięta w celu zapewnienia dodatkowych wymaganych funkcji.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlsimpcoll. h

## <a name="csimplemapequalhelperisequalkey"></a><a name="isequalkey"></a> CSimpleMapEqualHelper::IsEqualKey

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

## <a name="csimplemapequalhelperisequalvalue"></a><a name="isequalvalue"></a> CSimpleMapEqualHelper::IsEqualValue

Testuje dwie wartości pod kątem równości.

```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```

### <a name="parameters"></a>Parametry

*wersjach*<br/>
Pierwsza wartość.

*v2*<br/>
Druga wartość.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość true, jeśli wartości są równe, w przeciwnym razie false.

## <a name="see-also"></a>Zobacz też

[Klasa CSimpleMapEqualHelperFalse](../../atl/reference/csimplemapequalhelperfalse-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
