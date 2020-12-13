---
description: 'Dowiedz się więcej na temat: Klasa CAutoVectorPtrElementTraits'
title: Klasa CAutoVectorPtrElementTraits
ms.date: 11/04/2016
f1_keywords:
- CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CAutoVectorPtrElementTraits class
ms.assetid: 16b81a56-55fb-46ca-b376-66a1884231a6
ms.openlocfilehash: 571b85c1b11968289d372f9c349ffcdb754dc381
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147098"
---
# <a name="cautovectorptrelementtraits-class"></a>Klasa CAutoVectorPtrElementTraits

Ta klasa udostępnia metody, funkcje statyczne i definicje typów przydatne podczas tworzenia kolekcji inteligentnych wskaźników przy użyciu operatorów New i DELETE Vector.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template <typename T>
class CAutoVectorPtrElementTraits :
   public CDefaultElementTraits<ATL::CAutoVectorPtr<T>>
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ wskaźnika.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|[CAutoVectorPtrElementTraits::INARGTYPE](#inargtype)|Typ danych, który ma być używany do dodawania elementów do obiektu klasy kolekcji.|
|[CAutoVectorPtrElementTraits::OUTARGTYPE](#outargtype)|Typ danych, który ma być używany do pobierania elementów z obiektu klasy kolekcji.|

## <a name="remarks"></a>Uwagi

Ta klasa udostępnia metody, funkcje statyczne i definicje typów w celu polepszenia tworzenia obiektów klasy kolekcji zawierających inteligentne wskaźniki. W przeciwieństwie do [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md), ta klasa używa operatorów New i DELETE.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoVectorPtrElementTraits`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcoll. h

## <a name="cautovectorptrelementtraitsinargtype"></a><a name="inargtype"></a> CAutoVectorPtrElementTraits::INARGTYPE

Typ danych, który ma być używany do dodawania elementów do obiektu klasy kolekcji.

```
typedef CAutoVectorPtr<T>& INARGTYPE;
```

## <a name="cautovectorptrelementtraitsoutargtype"></a><a name="outargtype"></a> CAutoVectorPtrElementTraits::OUTARGTYPE

Typ danych, który ma być używany do pobierania elementów z obiektu klasy kolekcji.

```
typedef T*& OUTARGTYPE;
```

## <a name="see-also"></a>Zobacz też

[Klasa CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Klasa CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
