---
description: 'Dowiedz się więcej na temat: Klasa CSimpleArrayEqualHelper'
title: Klasa CSimpleArrayEqualHelper
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
ms.openlocfilehash: e1a5fd3eea5fd6ef7563febc662c5a7a1bc639c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140767"
---
# <a name="csimplearrayequalhelper-class"></a>Klasa CSimpleArrayEqualHelper

Ta klasa jest pomocnikiem dla klasy [CSimpleArray](../../atl/reference/csimplearray-class.md) .

## <a name="syntax"></a>Składnia

```
template <class T>
class CSimpleArrayEqualHelper
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Klasa pochodna.

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSimpleArrayEqualHelper:: IsEqual](#isequal)|Ruchom Testuje dwa `CSimpleArray` elementy obiektów pod kątem równości.|

## <a name="remarks"></a>Uwagi

Ta klasa cech jest uzupełnieniem `CSimpleArray` klasy. Zapewnia metodę do porównywania dwóch elementów przechowywanych w `CSimpleArray` obiekcie. Domyślnie elementy są porównywane przy użyciu **operatora = ()**, ale jeśli tablica zawiera złożone typy danych, które nie mają własnego operatora równości, należy zastąpić tę klasę.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlsimpcoll. h

## <a name="csimplearrayequalhelperisequal"></a><a name="isequal"></a> CSimpleArrayEqualHelper:: IsEqual

Testuje dwa `CSimpleArray` elementy obiektów pod kątem równości.

```
static bool IsEqual(
    const T& t1,
    const T& t2);
```

### <a name="parameters"></a>Parametry

*połączeń*<br/>
Obiekt typu T.

*T2*<br/>
Obiekt typu T.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość true, jeśli elementy są równe, w przeciwnym razie false.

## <a name="see-also"></a>Zobacz też

[Klasa CSimpleArray](../../atl/reference/csimplearray-class.md)<br/>
[Klasa CSimpleArrayEqualHelperFalse](../../atl/reference/csimplearrayequalhelperfalse-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
