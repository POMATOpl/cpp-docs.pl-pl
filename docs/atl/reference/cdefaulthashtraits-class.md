---
description: 'Dowiedz się więcej na temat: Klasa CDefaultHashTraits'
title: Klasa CDefaultHashTraits
ms.date: 11/04/2016
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
helpviewer_keywords:
- CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
ms.openlocfilehash: 85cc881466be03931d435d91a48548456d74305b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141885"
---
# <a name="cdefaulthashtraits-class"></a>Klasa CDefaultHashTraits

Ta klasa udostępnia funkcję statyczną do obliczania wartości skrótu.

## <a name="syntax"></a>Składnia

```
template<typename T>
class CDefaultHashTraits
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ danych, które mają być przechowywane w kolekcji.

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDefaultHashTraits:: hash](#hash)|Ruchom Wywołaj tę funkcję, aby obliczyć wartość skrótu dla danego elementu.|

## <a name="remarks"></a>Uwagi

Ta klasa zawiera pojedynczą funkcję statyczną zwracającą wartość skrótu dla danego elementu. Ta klasa jest wykorzystywana przez [klasę CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md).

Aby uzyskać więcej informacji, zobacz [klasy kolekcji ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcoll. h

## <a name="cdefaulthashtraitshash"></a><a name="hash"></a> CDefaultHashTraits:: hash

Wywołaj tę funkcję, aby obliczyć wartość skrótu dla danego elementu.

```
static ULONG Hash(const T& element) throw();
```

### <a name="parameters"></a>Parametry

*postaci*<br/>
Element.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość skrótu.

### <a name="remarks"></a>Uwagi

Domyślny algorytm wyznaczania wartości skrótu jest bardzo prosty: wartość zwracana jest numerem elementu. Przesłoń tę funkcję, jeśli jest wymagany bardziej skomplikowany algorytm.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
