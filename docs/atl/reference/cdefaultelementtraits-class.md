---
description: 'Dowiedz się więcej na temat: Klasa CDefaultElementTraits'
title: Klasa CDefaultElementTraits
ms.date: 11/04/2016
f1_keywords:
- CDefaultElementTraits
- atlcoll/ATL::CDefaultElementTraits
helpviewer_keywords:
- CDefaultElementTraits class
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
ms.openlocfilehash: f4dd1bae67ef626ef793ecee946d88879a07f194
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141898"
---
# <a name="cdefaultelementtraits-class"></a>Klasa CDefaultElementTraits

Ta klasa dostarcza domyślne metody i funkcje dla klasy kolekcji.

## <a name="syntax"></a>Składnia

```
template <typename T>
class CDefaultElementTraits : public CElementTraitsBase<T>,
    public CDefaultHashTraits<T>,
    public CDefaultCompareTraits<T>
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ danych, które mają być przechowywane w kolekcji.

## <a name="remarks"></a>Uwagi

Ta klasa udostępnia domyślne funkcje statyczne i metody służące do przesuwania, kopiowania, porównywania i mieszania elementów przechowywanych w obiekcie klasy kolekcji. Ta klasa dziedziczy funkcje i metody z [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md), [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)i [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)i jest wykorzystywane przez [CElementTraits](../../atl/reference/celementtraits-class.md), [CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md)i [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md).

Aby uzyskać więcej informacji, zobacz [klasy kolekcji ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcoll. h

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
