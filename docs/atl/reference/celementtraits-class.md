---
description: 'Dowiedz się więcej na temat: Klasa CElementTraits'
title: Klasa CElementTraits
ms.date: 11/04/2016
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
helpviewer_keywords:
- CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
ms.openlocfilehash: 1bcb6c9da2bca733efe68b634eebd7f379ba0d10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141807"
---
# <a name="celementtraits-class"></a>Klasa CElementTraits

Ta klasa jest używana przez klasy kolekcji do udostępniania metod i funkcji na potrzeby operacji przeniesienia, kopiowania, porównywania i tworzenia skrótów.

## <a name="syntax"></a>Składnia

```
template<typename T>
class CElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ danych, które mają być przechowywane w kolekcji.

## <a name="remarks"></a>Uwagi

Ta klasa udostępnia domyślne funkcje statyczne i metody służące do przesuwania, kopiowania, porównywania i mieszania elementów przechowywanych w obiekcie klasy kolekcji. `CElementTraits` jest określony jako domyślny dostawca tych operacji przez klasy kolekcji [CAtlArray](../../atl/reference/catlarray-class.md), [CAtlList](../../atl/reference/catllist-class.md), [CRBMap](../../atl/reference/crbmap-class.md), [CRBMultiMap](../../atl/reference/crbmultimap-class.md)i [CRBTree](../../atl/reference/crbtree-class.md).

Domyślne implementacje będą wystarczające dla prostych typów danych, ale jeśli klasy kolekcji są używane do przechowywania bardziej złożonych obiektów, funkcje i metody muszą zostać przesłonięte przez implementacje dostarczone przez użytkownika.

Aby uzyskać więcej informacji, zobacz [klasy kolekcji ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcoll. h

## <a name="see-also"></a>Zobacz też

[Klasa CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
