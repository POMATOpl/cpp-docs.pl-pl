---
description: 'Dowiedz się więcej na temat: Klasa CInterfaceList'
title: Klasa CInterfaceList
ms.date: 11/04/2016
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
helpviewer_keywords:
- CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
ms.openlocfilehash: 2612ba4700466bb877f84978c55bfd018f1dd286
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141534"
---
# <a name="cinterfacelist-class"></a>Klasa CInterfaceList

Ta klasa udostępnia metody przydatne podczas konstruowania listy wskaźników interfejsu COM.

## <a name="syntax"></a>Składnia

```
template<class I, const IID* piid =& __uuidof(I)>
class CInterfaceList
   : public CAtlList<ATL::CComQIPtr<I, piid>,
                     CComQIPtrElementTraits<I, piid>>
```

#### <a name="parameters"></a>Parametry

*Mam*<br/>
Interfejs COM określający typ wskaźnika, który ma być przechowywany.

*piid*<br/>
Wskaźnik do identyfikatora IID *I*.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CInterfaceList::CInterfaceList](#cinterfacelist)|Konstruktor dla listy interfejsów.|

## <a name="remarks"></a>Uwagi

Ta klasa udostępnia Konstruktor i metody pochodne do tworzenia listy wskaźników interfejsu COM. Użyj [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) , gdy tablica jest wymagana.

Aby uzyskać więcej informacji, zobacz [klasy kolekcji ATL](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CAtlList](../../atl/reference/catllist-class.md)

`CInterfaceList`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcoll. h

## <a name="cinterfacelistcinterfacelist"></a><a name="cinterfacelist"></a> CInterfaceList::CInterfaceList

Konstruktor dla listy interfejsów.

```
CInterfaceList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametry

*nBlockSize*<br/>
Rozmiar bloku z wartością domyślną 10.

### <a name="remarks"></a>Uwagi

Rozmiar bloku jest miarą ilości pamięci przydzieloną, gdy wymagany jest nowy element. Większe rozmiary bloków redukują wywołania procedur alokacji pamięci, ale wykorzystują więcej zasobów.

## <a name="see-also"></a>Zobacz też

[Klasa CAtlList](../../atl/reference/catllist-class.md)<br/>
[Klasa CComQIPtr](../../atl/reference/ccomqiptr-class.md)<br/>
[Klasa CComQIPtrElementTraits](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
