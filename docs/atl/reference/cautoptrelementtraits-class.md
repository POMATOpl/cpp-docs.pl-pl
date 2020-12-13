---
description: 'Dowiedz się więcej na temat: Klasa CAutoPtrElementTraits'
title: Klasa CAutoPtrElementTraits
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CAutoPtrElementTraits class
ms.assetid: 777c1b14-6ab7-491f-b9a5-be149e71d4a2
ms.openlocfilehash: 2478f8251f0094aaa5cabf1c0dcc873c9c526cd8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147137"
---
# <a name="cautoptrelementtraits-class"></a>Klasa CAutoPtrElementTraits

Ta klasa udostępnia metody, funkcje statyczne i definicje typów przydatne podczas tworzenia kolekcji inteligentnych wskaźników.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template<typename T>
class CAutoPtrElementTraits
    : public CDefaultElementTraits<ATL::CAutoPtr<T>>
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ wskaźnika.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|[CAutoPtrElementTraits::INARGTYPE](#inargtype)|Typ danych, który ma być używany do dodawania elementów do obiektu klasy kolekcji.|
|[CAutoPtrElementTraits::OUTARGTYPE](#outargtype)|Typ danych, który ma być używany do pobierania elementów z obiektu klasy kolekcji.|

## <a name="remarks"></a>Uwagi

Ta klasa udostępnia metody, funkcje statyczne i definicje typów w celu polepszenia tworzenia obiektów klasy kolekcji zawierających inteligentne wskaźniki. Klasy [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) i [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) pochodne od `CAutoPtrElementTraits` . W przypadku kompilowania kolekcji inteligentnych wskaźników, które wymagają operatora Vector New i DELETE, zamiast tego należy użyć [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoPtrElementTraits`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcoll. h

## <a name="cautoptrelementtraitsinargtype"></a><a name="inargtype"></a> CAutoPtrElementTraits::INARGTYPE

Typ danych, który ma być używany do dodawania elementów do obiektu klasy kolekcji.

```
typedef CAutoPtr<T>& INARGTYPE;
```

## <a name="cautoptrelementtraitsoutargtype"></a><a name="outargtype"></a> CAutoPtrElementTraits::OUTARGTYPE

Typ danych, który ma być używany do pobierania elementów z obiektu klasy kolekcji.

```
typedef T *& OUTARGTYPE;
```

## <a name="see-also"></a>Zobacz też

[Klasa CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
