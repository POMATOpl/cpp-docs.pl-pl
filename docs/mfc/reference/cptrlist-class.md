---
description: 'Dowiedz się więcej na temat: Klasa CPtrList'
title: Klasa CPtrList
ms.date: 11/04/2016
f1_keywords:
- CPtrList
helpviewer_keywords:
- lists, generic
- CPtrList class [MFC]
- generic lists
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
ms.openlocfilehash: 27849db4687860ab68feb548de1ed8ad209b73a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343254"
---
# <a name="cptrlist-class"></a>Klasa CPtrList

Obsługuje listy wskaźników typu void.

## <a name="syntax"></a>Składnia

```
class CPtrList : public CObject
```

## <a name="members"></a>Elementy członkowskie

Funkcje składowe `CPtrList` są podobne do funkcji składowych klasy [CObList](../../mfc/reference/coblist-class.md). W związku z tym podobieństwem można użyć `CObList` dokumentacji referencyjnej dla specyficznych dla funkcji składowych. Wszędzie tam, gdzie widzisz `CObject` wskaźnik jako parametr funkcji lub wartość zwracana, Zastąp wskaźnik do **`void`** .

`CObject*& CObList::GetHead() const;`

na przykład tłumaczy na

`void*& CPtrList::GetHead() const;`

## <a name="remarks"></a>Uwagi

`CPtrList` obejmuje makro IMPLEMENT_DYNAMIC do obsługi dostępu do typu w czasie wykonywania i zrzucania do `CDumpContext` obiektu. Jeśli potrzebujesz zrzutu poszczególnych elementów listy wskaźników, musisz ustawić głębokość kontekstu zrzutu na 1 lub większą.

Listy wskaźników nie mogą być serializowane.

Po `CPtrList` usunięciu obiektu lub po usunięciu jego elementów zostaną usunięte tylko te wskaźniki, a nie jednostki, do których się odwołują.

Aby uzyskać więcej informacji na temat korzystania z programu `CPtrList` , zobacz [kolekcje](../../mfc/collections.md)artykułów.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CPtrList`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxcoll. h

## <a name="see-also"></a>Zobacz też

[Klasa CObject](../../mfc/reference/cobject-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CObList](../../mfc/reference/coblist-class.md)
