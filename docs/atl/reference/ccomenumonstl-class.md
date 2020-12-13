---
description: 'Dowiedz się więcej na temat: Klasa CComEnumOnSTL'
title: Klasa CComEnumOnSTL
ms.date: 11/04/2016
f1_keywords:
- CComEnumOnSTL
- atlcom/ATL::CComEnumOnSTL
helpviewer_keywords:
- CComEnumOnSTL class
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
ms.openlocfilehash: 1ff73796d7e3eefa76cbecdeb6d997bede2d2be5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146669"
---
# <a name="ccomenumonstl-class"></a>Klasa CComEnumOnSTL

Ta klasa definiuje obiekt modułu wyliczającego COM na podstawie standardowej kolekcji biblioteki języka C++.

## <a name="syntax"></a>Składnia

```
template <class Base,
    const IID* piid, class T, class Copy, class CollType, class ThreadModel = CComObjectThreadModel>
class ATL_NO_VTABLE CComEnumOnSTL : public IEnumOnSTLImpl<Base, piid,
T,
    Copy,
CollType>,
    public CComObjectRootEx<ThreadModel>
```

#### <a name="parameters"></a>Parametry

*Opiera*<br/>
Moduł wyliczający COM. Zapoznaj się z przykładem [IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring) .

*piid*<br/>
Wskaźnik do identyfikatora interfejsu w interfejsie modułu wyliczającego.

*T*<br/>
Typ elementu uwidocznionego przez interfejs modułu wyliczającego.

*Kopiuj*<br/>
Klasa [zasad kopiowania](../../atl/atl-copy-policy-classes.md) .

*CollType*<br/>
Klasa kontenera standardowej biblioteki języka C++.

## <a name="remarks"></a>Uwagi

`CComEnumOnSTL` definiuje obiekt modułu wyliczającego COM na podstawie standardowej kolekcji biblioteki języka C++. Ta klasa może być używana samodzielnie lub w połączeniu z [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md). Typowe kroki dotyczące korzystania z tej klasy przedstawiono poniżej. Aby uzyskać więcej informacji, zobacz [zestawy ATL i moduły wyliczające](../../atl/atl-collections-and-enumerators.md).

## <a name="to-use-this-class-with-icollectiononstlimpl"></a>Aby użyć tej klasy z ICollectionOnSTLImpl:

- **`typedef`** Specjalizacja tej klasy.

- Użyj **`typedef`** jako argumentu końcowego szablonu w specjalizacji `ICollectionOnSTLImpl` .

Zobacz [Kolekcje ATL i moduły wyliczające](../../atl/atl-collections-and-enumerators.md) na przykład.

## <a name="to-use-this-class-independently-of-icollectiononstlimpl"></a>Aby użyć tej klasy niezależnie od ICollectionOnSTLImpl:

- **`typedef`** Specjalizacja tej klasy.

- Użyj **`typedef`** jako argumentu szablonu w specjalizacji `CComObject` .

- Utwórz wystąpienie `CComObject` specjalizacji.

- Zainicjuj obiekt Enumerator przez wywołanie [IEnumOnSTLImpl:: init](../../atl/reference/ienumonstlimpl-class.md#init).

- Zwróć interfejs modułu wyliczającego do klienta.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CComObjectRootBase`

`Base`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

[IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)

`CComEnumOnSTL`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcom. h

## <a name="example"></a>Przykład

Poniższy kod zawiera funkcję generyczną do obsługi tworzenia i inicjowania obiektu modułu wyliczającego:

[!code-cpp[NVC_ATL_COM#34](../../atl/codesnippet/cpp/ccomenumonstl-class_1.h)]

Ta funkcja szablonu może służyć do implementowania `_NewEnum` Właściwości interfejsu kolekcji, jak pokazano poniżej:

[!code-cpp[NVC_ATL_COM#35](../../atl/codesnippet/cpp/ccomenumonstl-class_2.h)]

Ten kod tworzy **`typedef`** dla `CComEnumOnSTL` , który uwidacznia wektor `CComVariant` s przy użyciu `IEnumVariant` interfejsu. `CVariantCollection`Klasa jest po prostu wyspecjalizowana `CreateSTLEnumerator` do pracy z obiektami modułu wyliczającego tego typu.

## <a name="see-also"></a>Zobacz też

[IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)<br/>
[Przykład ATLCollections: demonstruje ICollectionOnSTLImpl, CComEnumOnSTL i niestandardowe klasy zasad kopiowania](../../overview/visual-cpp-samples.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)<br/>
[Klasa CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)<br/>
[Klasa IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)
