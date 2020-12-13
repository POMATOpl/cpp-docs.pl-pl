---
description: 'Dowiedz się więcej na temat: Klasa CPrimitiveElementTraits'
title: Klasa CPrimitiveElementTraits
ms.date: 11/04/2016
f1_keywords:
- CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits::INARGTYPE
- ATLCOLL/ATL::CPrimitiveElementTraits::OUTARGTYPE
helpviewer_keywords:
- CPrimitiveElementTraits class
ms.assetid: 21c1cea8-2c5a-486c-b65c-85490f3ed4e6
ms.openlocfilehash: a9a47d9e6268ee6cc858d85e9236b00c270e8841
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141079"
---
# <a name="cprimitiveelementtraits-class"></a>Klasa CPrimitiveElementTraits

Ta klasa dostarcza domyślne metody i funkcje dla klasy kolekcji, która składa się z typów danych pierwotnych.

## <a name="syntax"></a>Składnia

```
template <typename T>
class CPrimitiveElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ danych, które mają być przechowywane w obiekcie klasy kolekcji.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|[CPrimitiveElementTraits::INARGTYPE](#inargtype)|Typ danych, który ma być używany do dodawania elementów do obiektu klasy kolekcji.|
|[CPrimitiveElementTraits::OUTARGTYPE](#outargtype)|Typ danych, który ma być używany do pobierania elementów z obiektu klasy kolekcji.|

## <a name="remarks"></a>Uwagi

Ta klasa zawiera domyślne funkcje statyczne i metody służące do przesuwania, kopiowania, porównywania i mieszania elementów pierwotnych typu danych przechowywanych w obiekcie klasy kolekcji.

Aby uzyskać więcej informacji, zobacz [klasy kolekcji ATL](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CPrimitiveElementTraits`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcoll. h

## <a name="cprimitiveelementtraitsinargtype"></a><a name="inargtype"></a> CPrimitiveElementTraits::INARGTYPE

Typ danych, który ma być używany do dodawania elementów do obiektu klasy kolekcji.

```
typedef T INARGTYPE;
```

## <a name="cprimitiveelementtraitsoutargtype"></a><a name="outargtype"></a> CPrimitiveElementTraits::OUTARGTYPE

Typ danych, który ma być używany do pobierania elementów z obiektu klasy kolekcji.

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>Zobacz też

[Klasa CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
