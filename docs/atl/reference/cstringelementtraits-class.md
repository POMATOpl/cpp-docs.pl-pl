---
description: 'Dowiedz się więcej na temat: Klasa CStringElementTraits'
title: Klasa CStringElementTraits
ms.date: 11/04/2016
f1_keywords:
- CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits::INARGTYPE
- CSTRINGT/ATL::CStringElementTraits::OUTARGTYPE
- CSTRINGT/ATL::CStringElementTraits::CompareElements
- CSTRINGT/ATL::CStringElementTraits::CompareElementsOrdered
- CSTRINGT/ATL::CStringElementTraits::CopyElements
- CSTRINGT/ATL::CStringElementTraits::Hash
- CSTRINGT/ATL::CStringElementTraits::RelocateElements
helpviewer_keywords:
- CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
ms.openlocfilehash: 1e3f6a73e71530250d9dd88408165471028a18e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140494"
---
# <a name="cstringelementtraits-class"></a>Klasa CStringElementTraits

Ta klasa udostępnia funkcje statyczne używane przez klasy kolekcji przechowujące `CString` obiekty.

## <a name="syntax"></a>Składnia

```
template <typename T>
class CStringElementTraits
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ danych, które mają być przechowywane w kolekcji.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|[CStringElementTraits::INARGTYPE](#inargtype)|Typ danych, który ma być używany do dodawania elementów do obiektu klasy kolekcji.|
|[CStringElementTraits::OUTARGTYPE](#outargtype)|Typ danych, który ma być używany do pobierania elementów z obiektu klasy kolekcji.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CStringElementTraits::CompareElements](#compareelements)|Ruchom Wywołaj tę funkcję, aby porównać dwa elementy ciągu dla równości.|
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)|Ruchom Wywołaj tę funkcję, aby porównać dwa elementy ciągu.|
|[CStringElementTraits::CopyElements](#copyelements)|Ruchom Wywołaj tę funkcję, aby skopiować `CString` elementy przechowywane w obiekcie klasy kolekcji.|
|[CStringElementTraits:: hash](#hash)|Ruchom Wywołaj tę funkcję, aby obliczyć wartość skrótu dla danego elementu ciągu.|
|[CStringElementTraits::RelocateElements](#relocateelements)|Ruchom Wywołaj tę funkcję, aby przemieścić `CString` elementy przechowywane w obiekcie klasy kolekcji.|

## <a name="remarks"></a>Uwagi

Ta klasa udostępnia funkcje statyczne do kopiowania, przechodzenia i porównywania ciągów oraz do tworzenia wartości skrótu. Te funkcje są przydatne w przypadku używania klasy kolekcji do przechowywania danych opartych na ciągach. Użyj [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) , gdy są wymagane porównania bez uwzględniania wielkości liter. Użyj [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) , gdy obiekty String mają być traktowane jako odwołania.

Aby uzyskać więcej informacji, zobacz [klasy kolekcji ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Wymagania

**Nagłówek:** CStringT. h

## <a name="cstringelementtraitscompareelements"></a><a name="compareelements"></a> CStringElementTraits::CompareElements

Wywołaj tę funkcję statyczną, aby porównać dwa elementy ciągu dla równości.

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>Parametry

*str1*<br/>
Pierwszy element ciągu.

*str2*<br/>
Drugi element ciągu.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość true, jeśli elementy są równe, w przeciwnym razie false.

## <a name="cstringelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a> CStringElementTraits::CompareElementsOrdered

Wywołaj tę funkcję statyczną, aby porównać dwa elementy ciągu.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>Parametry

*str1*<br/>
Pierwszy element ciągu.

*str2*<br/>
Drugi element ciągu.

### <a name="return-value"></a>Wartość zwracana

Zero, jeśli ciągi są identyczne, < 0 Jeśli wartość *str1* jest mniejsza niż *str2* lub > 0, jeśli *str1* jest większa niż *str2*. Metoda [CStringT:: Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) służy do przeprowadzenia porównania.

## <a name="cstringelementtraitscopyelements"></a><a name="copyelements"></a> CStringElementTraits::CopyElements

Wywołaj tę funkcję statyczną, aby skopiować `CString` elementy przechowywane w obiekcie klasy kolekcji.

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Parametry

*pDest*<br/>
Wskaźnik do pierwszego elementu, który będzie otrzymywał skopiowane dane.

*pSrc*<br/>
Wskaźnik na pierwszy element, który ma zostać skopiowany.

*nElements*<br/>
Liczba elementów do skopiowania.

### <a name="remarks"></a>Uwagi

Elementy źródłowe i docelowe nie powinny nakładać się na siebie.

## <a name="cstringelementtraitshash"></a><a name="hash"></a> CStringElementTraits:: hash

Wywołaj tę funkcję statyczną, aby obliczyć wartość skrótu dla danego elementu ciągu.

```
static ULONG Hash(INARGTYPE str);
```

### <a name="parameters"></a>Parametry

*str*<br/>
Element String.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość skrótu obliczaną przy użyciu zawartości ciągu.

## <a name="cstringelementtraitsinargtype"></a><a name="inargtype"></a> CStringElementTraits::INARGTYPE

Typ danych, który ma być używany do dodawania elementów do obiektu klasy kolekcji.

```
typedef T::PCXSTR INARGTYPE;
```

## <a name="cstringelementtraitsoutargtype"></a><a name="outargtype"></a> CStringElementTraits::OUTARGTYPE

Typ danych, który ma być używany do pobierania elementów z obiektu klasy kolekcji.

```
typedef T& OUTARGTYPE;
```

## <a name="cstringelementtraitsrelocateelements"></a><a name="relocateelements"></a> CStringElementTraits::RelocateElements

Wywołaj tę funkcję statyczną, aby przemieścić `CString` elementy przechowywane w obiekcie klasy kolekcji.

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Parametry

*pDest*<br/>
Wskaźnik do pierwszego elementu, który będzie otrzymywać dane z lokalizacji.

*pSrc*<br/>
Wskaźnik do pierwszego elementu do przeniesienia.

*nElements*<br/>
Liczba elementów do przeniesienia.

### <a name="remarks"></a>Uwagi

Ta funkcja statyczna wywołuje [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), co jest wystarczające dla większości typów danych. Jeśli obiekty, które są przenoszone, zawierają wskaźniki do swoich elementów członkowskich, ta funkcja statyczna będzie musiała zostać zastąpiona.

## <a name="see-also"></a>Zobacz też

[Klasa CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)<br/>
[Klasa CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
