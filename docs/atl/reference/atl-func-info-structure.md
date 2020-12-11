---
description: Dowiedz się więcej na temat struktury _ATL_FUNC_INFO
title: Struktura _ATL_FUNC_INFO
ms.date: 11/04/2016
f1_keywords:
- _ATL_FUNC_INFO
- ATL::_ATL_FUNC_INFO
- ATL._ATL_FUNC_INFO
helpviewer_keywords:
- _ATL_FUNC_INFO structure
- ATL_FUNC_INFO structure
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
ms.openlocfilehash: 6368440347672524bb7d1e3aa3068ef91a2c6f09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158858"
---
# <a name="_atl_func_info-structure"></a>Struktura _ATL_FUNC_INFO

Zawiera informacje o typie używane do opisywania metody lub właściwości w dispinterface.

## <a name="syntax"></a>Składnia

```cpp
struct _ATL_FUNC_INFO {
    CALLCONV cc;
    VARTYPE vtReturn;
    SHORT nParams;
    VARTYPE pVarTypes[_ATL_MAX_VARTYPES];
};
```

## <a name="members"></a>Elementy członkowskie

`cc`<br/>
Konwencja wywoływania. W przypadku używania tej struktury z klasą [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) ten element członkowski musi być CC_STDCALL. `CC_CDECL` jest jedyną opcją obsługiwaną w Windows CE dla `CALLCONV` pola `_ATL_FUNC_INFO` struktury. Wszystkie inne wartości są nieobsługiwane w tym przypadku, gdy zachowanie nie jest zdefiniowane.

`vtReturn`<br/>
Typ wariantu zwracanej wartości funkcji.

`nParams`<br/>
Liczba parametrów funkcji.

`pVarTypes`<br/>
Tablica typów wariantów parametrów funkcji.

## <a name="remarks"></a>Uwagi

Wewnętrznie, ATL używa tej struktury do przechowywania informacji uzyskanych z biblioteki typów. Może być konieczne bezpośrednie manipulowanie tą strukturą w przypadku podania informacji o typie dla programu obsługi zdarzeń używanego z klasą [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) i makrem [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) .

## <a name="example"></a>Przykład

Dana metoda dispinterface zdefiniowana w IDL:

[!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]

należy zdefiniować `_ATL_FUNC_INFO` strukturę:

[!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]

## <a name="requirements"></a>Wymagania

Nagłówek: atlcom. h

## <a name="see-also"></a>Zobacz też

[Klasy i struktury](../../atl/reference/atl-classes.md)<br/>
[Klasa IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)
