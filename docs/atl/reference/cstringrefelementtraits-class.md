---
description: 'Dowiedz się więcej na temat: Klasa CStringRefElementTraits'
title: Klasa CStringRefElementTraits
ms.date: 11/04/2016
f1_keywords:
- CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits::CompareElements
- ATLCOLL/ATL::CStringRefElementTraits::CompareElementsOrdered
- ATLCOLL/ATL::CStringRefElementTraits::Hash
helpviewer_keywords:
- CStringRefElementTraits class
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
ms.openlocfilehash: 5523a2a451fc1825c443cf2d2e518b1c8dc2b340
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140390"
---
# <a name="cstringrefelementtraits-class"></a>Klasa CStringRefElementTraits

Ta klasa udostępnia funkcje statyczne dotyczące ciągów przechowywanych w obiektach klasy kolekcji. Obiekty ciągów są rozpatrywane jako odwołania.

## <a name="syntax"></a>Składnia

```
template <typename T>
class CStringRefElementTraits : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ danych, które mają być przechowywane w kolekcji.

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CStringRefElementTraits::CompareElements](#compareelements)|Wywołaj tę funkcję statyczną, aby porównać dwa elementy ciągu dla równości.|
|[CStringRefElementTraits::CompareElementsOrdered](#compareelementsordered)|Wywołaj tę funkcję statyczną, aby porównać dwa elementy ciągu.|
|[CStringRefElementTraits:: hash](#hash)|Wywołaj tę funkcję statyczną, aby obliczyć wartość skrótu dla danego elementu ciągu.|

## <a name="remarks"></a>Uwagi

Ta klasa udostępnia statyczne funkcje do porównywania ciągów i tworzenia wartości skrótu. Te funkcje są przydatne w przypadku używania klasy kolekcji do przechowywania danych opartych na ciągach. W przeciwieństwie do [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) i [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md), `CStringRefElementTraits` powoduje, że `CString` argumenty mają być przekazane jako **`const`** `CString&` odwołania.

Aby uzyskać więcej informacji, zobacz [klasy kolekcji ATL](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

`CStringRefElementTraits`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcoll. h

## <a name="cstringrefelementtraitscompareelements"></a><a name="compareelements"></a> CStringRefElementTraits::CompareElements

Wywołaj tę funkcję statyczną, aby porównać dwa elementy ciągu dla równości.

```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```

### <a name="parameters"></a>Parametry

*element1*<br/>
Pierwszy element ciągu.

*element2*<br/>
Drugi element ciągu.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość true, jeśli elementy są równe, w przeciwnym razie false.

## <a name="cstringrefelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a> CStringRefElementTraits::CompareElementsOrdered

Wywołaj tę funkcję statyczną, aby porównać dwa elementy ciągu.

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

## <a name="cstringrefelementtraitshash"></a><a name="hash"></a> CStringRefElementTraits:: hash

Wywołaj tę funkcję statyczną, aby obliczyć wartość skrótu dla danego elementu ciągu.

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>Parametry

*str*<br/>
Element String.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość skrótu obliczaną przy użyciu zawartości ciągu.

## <a name="see-also"></a>Zobacz też

[Klasa CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
