---
description: Dowiedz się więcej o strukturze InterfaceListHelper —
title: InterfaceListHelper — Struktura
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceListHelper
helpviewer_keywords:
- InterfaceListHelper structure
ms.assetid: 4297e419-c96b-45df-8a00-7568062125ba
ms.openlocfilehash: ca9e13e66acb6f27fba76a7653388305c57146dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249805"
---
# <a name="interfacelisthelper-structure"></a>InterfaceListHelper — Struktura

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
template <
    typename T0,
    typename T1 = Nil,
    typename T2 = Nil,
    typename T3 = Nil,
    typename T4 = Nil,
    typename T5 = Nil,
    typename T6 = Nil,
    typename T7 = Nil,
    typename T8 = Nil,
    typename T9 = Nil
>
struct InterfaceListHelper;

template <typename T0>
struct InterfaceListHelper<T0, Nil, Nil, Nil, Nil, Nil, Nil, Nil, Nil>;
```

### <a name="parameters"></a>Parametry

*T0*<br/>
Wymagany jest parametr szablonu 0.

*T1*<br/>
Parametr szablonu 1, który domyślnie jest nieokreślony.

*T2*<br/>
Parametr szablonu 2, który domyślnie jest nieokreślony. Trzeci parametr szablonu.

*T3*<br/>
Parametr szablonu 3, który domyślnie jest nieokreślony.

*T4*<br/>
Parametr szablonu 4, który domyślnie jest nieokreślony.

*Otrzymując*<br/>
Parametr szablonu 5, który domyślnie jest nieokreślony.

*T6*<br/>
Parametr szablonu 6, który domyślnie jest nieokreślony.

*T7*<br/>
Parametr szablonu 7, który domyślnie jest nieokreślony.

*T8*<br/>
Parametr szablonu 8, który domyślnie jest nieokreślony.

*T9*<br/>
Parametr szablonu 9, który domyślnie jest nieokreślony.

## <a name="remarks"></a>Uwagi

Kompiluje `InterfaceList` Typ przez cykliczne stosowanie określonych argumentów parametrów szablonu.

Szablon **InterfaceListHelper —** używa parametru szablonu *T0* do definiowania pierwszego elementu członkowskiego danych w `InterfaceList` strukturze, a następnie rekursywnie stosuje szablon **InterfaceListHelper —** do wszelkich pozostałych parametrów szablonu. **InterfaceListHelper —** zostaje zatrzymana, gdy nie ma pozostałych parametrów szablonu.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|`TypeT`|Synonim dla typu InterfaceList —.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`InterfaceListHelper`

## <a name="requirements"></a>Wymagania

**Nagłówek:** implementuje. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL::D etails — przestrzeń nazw](microsoft-wrl-details-namespace.md)
