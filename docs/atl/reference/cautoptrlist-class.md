---
description: 'Dowiedz się więcej na temat: Klasa CAutoPtrList'
title: Klasa CAutoPtrList
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList::CAutoPtrList
helpviewer_keywords:
- CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
ms.openlocfilehash: 51544d464904d0ebfd31b82152088a0dfa638969
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152519"
---
# <a name="cautoptrlist-class"></a>Klasa CAutoPtrList

Ta klasa udostępnia metody przydatne podczas konstruowania listy inteligentnych wskaźników.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template<typename E>
class CAutoPtrList :
   public CAtlList<ATL::CAutoPtr<E>, CAutoPtrElementTraits<E>>
```

#### <a name="parameters"></a>Parametry

*Adres*<br/>
Typ wskaźnika.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAutoPtrList::CAutoPtrList](#cautoptrlist)|Konstruktor.|

## <a name="remarks"></a>Uwagi

Ta klasa udostępnia Konstruktor i dziedziczy metody z [CAtlList](../../atl/reference/catllist-class.md) i [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) , aby pomóc utworzyć obiekt listy przechowujący inteligentne wskaźniki. Klasa [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) zapewnia podobną funkcję dla obiektu Array.

Aby uzyskać więcej informacji, zobacz [klasy kolekcji ATL](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CAtlList](../../atl/reference/catllist-class.md)

`CAutoPtrList`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcoll. h

## <a name="cautoptrlistcautoptrlist"></a><a name="cautoptrlist"></a> CAutoPtrList::CAutoPtrList

Konstruktor.

```
CAutoPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametry

*nBlockSize*<br/>
Rozmiar bloku z wartością domyślną 10.

### <a name="remarks"></a>Uwagi

Rozmiar bloku jest miarą ilości pamięci przydzieloną, gdy wymagany jest nowy element. Większe rozmiary bloków redukują wywołania procedur alokacji pamięci, ale wykorzystują więcej zasobów.

## <a name="see-also"></a>Zobacz też

[Klasa CAtlList](../../atl/reference/catllist-class.md)<br/>
[Klasa CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
