---
description: 'Dowiedz się więcej na temat: makra obsługi wyjątków'
title: Makra obsługi wyjątków
ms.date: 11/04/2016
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
ms.openlocfilehash: 8d5e6564dec5769fb172c66b3102677e58cbd788
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139831"
---
# <a name="exception-handling-macros"></a>Makra obsługi wyjątków

Te makra zapewniają obsługę wyjątków.

|Nazwa|Opis|
|-|-|
|[_ATLCATCH](#_atlcatch)|Instrukcje do obsługi błędów występujących w skojarzonym elemencie `_ATLTRY` .|
|[_ATLCATCHALL](#_atlcatchall)|Instrukcje do obsługi błędów występujących w skojarzonym elemencie `_ATLTRY` .|
|[_ATLTRY](#_atltry)|Oznacza sekcję chronionego kodu, w której może wystąpić błąd.|

## <a name="requirements"></a>Wymagania:

**Nagłówek:** atldef. h

## <a name="_atlcatch"></a><a name="_atlcatch"></a> _ATLCATCH

Instrukcje do obsługi błędów występujących w skojarzonym elemencie `_ATLTRY` .

```
_ATLCATCH(e)
```

### <a name="parameters"></a>Parametry

*adres*<br/>
Wyjątek do przechwycenia.

### <a name="remarks"></a>Uwagi

Używane w połączeniu z `_ATLTRY` . Rozpoznaje do języka C++ [catch (CAtlException e)](../../cpp/try-throw-and-catch-statements-cpp.md) do obsługi danego typu wyjątków C++.

## <a name="_atlcatchall"></a><a name="_atlcatchall"></a> _ATLCATCHALL

Instrukcje do obsługi błędów występujących w skojarzonym elemencie `_ATLTRY` .

```
_ATLCATCHALL
```

### <a name="remarks"></a>Uwagi

Używane w połączeniu z `_ATLTRY` . Jest rozpoznawana jako catch języka C++ [(...)](../../cpp/try-throw-and-catch-statements-cpp.md) w celu obsługi wszystkich typów wyjątków C++.

## <a name="_atltry"></a><a name="_atltry"></a> _ATLTRY

Oznacza sekcję chronionego kodu, w której może wystąpić błąd.

```
_ATLTRY
```

### <a name="remarks"></a>Uwagi

Używane w połączeniu z [_ATLCATCH](#_atlcatch) lub [_ATLCATCHALL](#_atlcatchall). Jest rozpoznawany [jako symbol języka](../../cpp/try-throw-and-catch-statements-cpp.md)C++.

## <a name="see-also"></a>Zobacz też

[Makra](../../atl/reference/atl-macros.md)
