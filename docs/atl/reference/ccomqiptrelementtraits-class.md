---
description: 'Dowiedz się więcej na temat: Klasa CComQIPtrElementTraits'
title: Klasa CComQIPtrElementTraits
ms.date: 11/04/2016
f1_keywords:
- CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits::INARGTYPE
helpviewer_keywords:
- CComQIPtrElementTraits class
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
ms.openlocfilehash: 9aa96c5b926263d6ed58125a28f5d0a12d8107d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142340"
---
# <a name="ccomqiptrelementtraits-class"></a>Klasa CComQIPtrElementTraits

Ta klasa udostępnia metody, funkcje statyczne i definicje typów przydatne podczas tworzenia kolekcji wskaźników interfejsu COM.

## <a name="syntax"></a>Składnia

```
template<typename I, const IID* piid=& __uuidof(I)>
class CComQIPtrElementTraits :
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```

#### <a name="parameters"></a>Parametry

*Mam*<br/>
Interfejs COM określający typ wskaźnika, który ma być przechowywany.

*piid*<br/>
Wskaźnik do identyfikatora IID *I*.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|[CComQIPtrElementTraits::INARGTYPE](#inargtype)|Typ danych, który ma być używany do dodawania elementów do obiektu klasy kolekcji.|

## <a name="remarks"></a>Uwagi

Ta klasa dziedziczy metody i udostępnia element typedef, przydatny podczas tworzenia klasy kolekcji obiektów wskaźnika interfejsu [CComQIPtr](../../atl/reference/ccomqiptr-class.md) com. Ta klasa jest używana zarówno przez klasy [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) , jak i [CInterfaceList](../../atl/reference/cinterfacelist-class.md) .

Aby uzyskać więcej informacji, zobacz [klasy kolekcji ATL](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CComQIPtrElementTraits`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcoll. h

## <a name="ccomqiptrelementtraitsinargtype"></a><a name="inargtype"></a> CComQIPtrElementTraits::INARGTYPE

Typ danych, który ma być używany do dodawania elementów do obiektu klasy kolekcji.

```
typedef I* INARGTYPE;
```

## <a name="see-also"></a>Zobacz też

[Klasa CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
