---
description: 'Dowiedz się więcej na temat: Klasa CAutoPtrArray'
title: Klasa CAutoPtrArray
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
ms.openlocfilehash: 55f9382c82a1e242342d0d740c369a571c43f9ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152583"
---
# <a name="cautoptrarray-class"></a>Klasa CAutoPtrArray

Ta klasa zapewnia metody przydatne podczas konstruowania tablicy inteligentnych wskaźników.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```cpp
template <typename E>
class CAutoPtrArray : public CAtlArray<
                        ATL::CAutoPtr<E>,
                        CAutoPtrElementTraits<E>>
```

### <a name="parameters"></a>Parametry

*Adres*<br/>
Typ wskaźnika.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAutoPtrArray::CAutoPtrArray](#cautoptrarray)|Konstruktor.|

## <a name="remarks"></a>Uwagi

Ta klasa udostępnia Konstruktor i dziedziczy metody z [CAtlArray](../../atl/reference/catlarray-class.md) i [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) , aby ułatwić tworzenie obiektów klasy kolekcji przechowujących inteligentne wskaźniki.

Aby uzyskać więcej informacji, zobacz [klasy kolekcji ATL](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CAtlArray`

`CAutoPtrArray`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcoll. h

## <a name="cautoptrarraycautoptrarray"></a><a name="cautoptrarray"></a> CAutoPtrArray::CAutoPtrArray

Konstruktor.

```cpp
CAutoPtrArray() throw();
```

### <a name="remarks"></a>Uwagi

Inicjuje tablicę inteligentnych wskaźników.

## <a name="see-also"></a>Zobacz też

[Klasa CAtlArray](../../atl/reference/catlarray-class.md)<br/>
[Klasa CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[Klasa CAutoPtrList](../../atl/reference/cautoptrlist-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
