---
description: 'Dowiedz się więcej na temat: Klasa CStringElementTraitsI'
title: Klasa CStringElementTraitsI
ms.date: 11/04/2016
f1_keywords:
- CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI::INARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::OUTARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::CompareElements
- ATLCOLL/ATL::CStringElementTraitsI::CompareElementsOrdered
- ATLCOLL/ATL::CStringElementTraitsI::Hash
helpviewer_keywords:
- CStringElementTraitsI class
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
ms.openlocfilehash: 0a626677f4a62805933b2effb4811394626374a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140404"
---
# <a name="cstringelementtraitsi-class"></a>Klasa CStringElementTraitsI

Ta klasa udostępnia funkcje statyczne dotyczące ciągów przechowywanych w obiektach klasy kolekcji. Jest to podobne do [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md), ale wykonuje porównania bez uwzględniania wielkości liter.

## <a name="syntax"></a>Składnia

```
template <typename T, class CharTraits = CDefaultCharTraits<T ::XCHAR>>
class CStringElementTraitsI : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ danych, które mają być przechowywane w kolekcji.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|[CStringElementTraitsI::INARGTYPE](#inargtype)|Typ danych, który ma być używany do dodawania elementów do obiektu klasy kolekcji.|
|[CStringElementTraitsI::OUTARGTYPE](#outargtype)|Typ danych, który ma być używany do pobierania elementów z obiektu klasy kolekcji.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CStringElementTraitsI::CompareElements](#compareelements)|Wywołaj tę funkcję statyczną, aby porównać dwa elementy ciągu z równośćmi, ignorując różnice w przypadku.|
|[CStringElementTraitsI::CompareElementsOrdered](#compareelementsordered)|Wywołaj tę funkcję statyczną, aby porównać dwa elementy String, ignorując różnice w przypadku.|
|[CStringElementTraitsI:: hash](#hash)|Wywołaj tę funkcję statyczną, aby obliczyć wartość skrótu dla danego elementu ciągu.|

## <a name="remarks"></a>Uwagi

Ta klasa udostępnia statyczne funkcje do porównywania ciągów i tworzenia wartości skrótu. Te funkcje są przydatne w przypadku używania klasy kolekcji do przechowywania danych opartych na ciągach. Użyj [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) , gdy obiekty String mają być traktowane jako odwołania.

Aby uzyskać więcej informacji, zobacz [klasy kolekcji ATL](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

`CStringElementTraitsI`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcoll. h

## <a name="cstringelementtraitsicompareelements"></a><a name="compareelements"></a> CStringElementTraitsI::CompareElements

Wywołaj tę funkcję statyczną, aby porównać dwa elementy ciągu z równośćmi, ignorując różnice w przypadku.

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>Parametry

*str1*<br/>
Pierwszy element ciągu.

*str2*<br/>
Drugi element ciągu.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość true, jeśli elementy są równe, w przeciwnym razie false.

### <a name="remarks"></a>Uwagi

Porównania uwzględniają wielkość liter.

## <a name="cstringelementtraitsicompareelementsordered"></a><a name="compareelementsordered"></a> CStringElementTraitsI::CompareElementsOrdered

Wywołaj tę funkcję statyczną, aby porównać dwa elementy String, ignorując różnice w przypadku.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>Parametry

*str1*<br/>
Pierwszy element ciągu.

*str2*<br/>
Drugi element ciągu.

### <a name="return-value"></a>Wartość zwracana

Zero, jeśli ciągi są identyczne, < 0 Jeśli wartość *str1* jest mniejsza niż *str2* lub > 0, jeśli *str1* jest większa niż *str2*. Metoda [CStringT:: Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) służy do przeprowadzenia porównania.

### <a name="remarks"></a>Uwagi

Porównania uwzględniają wielkość liter.

## <a name="cstringelementtraitsihash"></a><a name="hash"></a> CStringElementTraitsI:: hash

Wywołaj tę funkcję statyczną, aby obliczyć wartość skrótu dla danego elementu ciągu.

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>Parametry

*str*<br/>
Element String.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość skrótu obliczaną przy użyciu zawartości ciągu.

## <a name="cstringelementtraitsiinargtype"></a><a name="inargtype"></a> CStringElementTraitsI::INARGTYPE

Typ danych, który ma być używany do dodawania elementów do obiektu klasy kolekcji.

```
typedef T::PCXSTR INARGTYPE;
```

## <a name="cstringelementtraitsioutargtype"></a><a name="outargtype"></a> CStringElementTraitsI::OUTARGTYPE

Typ danych, który ma być używany do pobierania elementów z obiektu klasy kolekcji.

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>Zobacz też

[Klasa CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)<br/>
[Klasa CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)
