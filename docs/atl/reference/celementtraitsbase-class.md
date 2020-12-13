---
description: 'Dowiedz się więcej na temat: Klasa CElementTraitsBase'
title: Klasa CElementTraitsBase
ms.date: 11/04/2016
f1_keywords:
- CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase::INARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::OUTARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::CopyElements
- ATLCOLL/ATL::CElementTraitsBase::RelocateElements
helpviewer_keywords:
- CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
ms.openlocfilehash: a200517e378cc3c3ca854ff60e9a49ac8e43d215
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141781"
---
# <a name="celementtraitsbase-class"></a>Klasa CElementTraitsBase

Ta klasa udostępnia domyślne metody kopiowania i przenoszenia dla klasy kolekcji.

## <a name="syntax"></a>Składnia

```
template<typename T>
class CElementTraitsBase
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ danych, które mają być przechowywane w kolekcji.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|[CElementTraitsBase::INARGTYPE](#inargtype)|Typ danych, który ma być używany do dodawania elementów do obiektu klasy kolekcji.|
|[CElementTraitsBase::OUTARGTYPE](#outargtype)|Typ danych, który ma być używany do pobierania elementów z obiektu klasy kolekcji.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CElementTraitsBase::CopyElements](#copyelements)|Wywołaj tę metodę, aby skopiować elementy przechowywane w obiekcie klasy kolekcji.|
|[CElementTraitsBase::RelocateElements](#relocateelements)|Wywołaj tę metodę, aby przemieścić elementy przechowywane w obiekcie klasy kolekcji.|

## <a name="remarks"></a>Uwagi

Ta klasa bazowa definiuje metody kopiowania i lokalizowania elementów w klasie kolekcji. Jest on używany przez klasy [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md), [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)i [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).

Aby uzyskać więcej informacji, zobacz [klasy kolekcji ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcoll. h

## <a name="celementtraitsbasecopyelements"></a><a name="copyelements"></a> CElementTraitsBase::CopyElements

Wywołaj tę metodę, aby skopiować elementy przechowywane w obiekcie klasy kolekcji.

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

## <a name="celementtraitsbaseinargtype"></a><a name="inargtype"></a> CElementTraitsBase::INARGTYPE

Typ danych, który ma być używany do dodawania elementów do kolekcji.

```
typedef const T& INARGTYPE;
```

## <a name="celementtraitsbaseoutargtype"></a><a name="outargtype"></a> CElementTraitsBase::OUTARGTYPE

Typ danych, który ma być używany do pobierania elementów z kolekcji.

```
typedef T& OUTARGTYPE;
```

## <a name="celementtraitsbaserelocateelements"></a><a name="relocateelements"></a> CElementTraitsBase::RelocateElements

Wywołaj tę metodę, aby przemieścić elementy przechowywane w obiekcie klasy kolekcji.

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

Ta metoda wywołuje [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), co jest wystarczające dla większości typów danych. Jeśli obiekty, które są przenoszone, zawierają wskaźniki do ich własnych elementów członkowskich, ta metoda będzie musiała zostać przesłonięta.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
