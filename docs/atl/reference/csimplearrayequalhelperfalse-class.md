---
description: 'Dowiedz się więcej na temat: Klasa CSimpleArrayEqualHelperFalse'
title: Klasa CSimpleArrayEqualHelperFalse
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
ms.openlocfilehash: 196f7873f72799408a629bc784cb343966801d79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140728"
---
# <a name="csimplearrayequalhelperfalse-class"></a>Klasa CSimpleArrayEqualHelperFalse

Ta klasa jest pomocnikiem dla klasy [CSimpleArray](../../atl/reference/csimplearray-class.md) .

## <a name="syntax"></a>Składnia

```
template <class T>
class CSimpleArrayEqualHelperFalse
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Klasa pochodna.

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSimpleArrayEqualHelperFalse:: IsEqual](#isequal)|Ruchom Zwraca wartość false.|

## <a name="remarks"></a>Uwagi

Ta klasa cech jest uzupełnieniem `CSimpleArray` klasy. Zawsze zwraca wartość false, a ponadto wywoła `ATLASSERT` argument o wartości false, jeśli jest kiedykolwiek wywoływana. W sytuacjach, gdy test równości nie jest wystarczająco zdefiniowany, ta klasa umożliwia tablicę zawierającą elementy do prawidłowego działania w przypadku większości metod, ale niepowodzenie w dobrze zdefiniowany sposób dla metod, które są zależne od porównań, takich jak [CSimpleArray:: find](../../atl/reference/csimplearray-class.md#find).

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlsimpcoll. h

## <a name="csimplearrayequalhelperfalseisequal"></a><a name="isequal"></a> CSimpleArrayEqualHelperFalse:: IsEqual

Zwraca wartość false.

```
static bool IsEqual(const T&, const T&);
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość false.

### <a name="remarks"></a>Uwagi

Ta metoda zawsze zwraca wartość false i wywołuje `ATLASSERT` z argumentem false, jeśli istnieje odwołanie. Celem `CSimpleArrayEqualHelperFalse::IsEqual` jest wymuszenie stosowania przez metody porównania metod niepowodzenia w dobrze zdefiniowany sposób, gdy testy równości nie zostały prawidłowo zdefiniowane.

## <a name="see-also"></a>Zobacz też

[Klasa CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
