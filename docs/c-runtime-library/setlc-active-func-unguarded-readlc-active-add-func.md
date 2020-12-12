---
description: 'Dowiedz się więcej na temat: ___setlc_active_func, ___unguarded_readlc_active_add_func'
title: ___setlc_active_func, ___unguarded_readlc_active_add_func
ms.date: 11/04/2016
api_name:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
api_location:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr100.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ___unguarded_readlc_active_add_func
- ___setlc_active_func
helpviewer_keywords:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
ms.openlocfilehash: 85273b52102e9cca2e42ba4401da60b1d292560c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277091"
---
# <a name="___setlc_active_func-___unguarded_readlc_active_add_func"></a>___setlc_active_func, ___unguarded_readlc_active_add_func

Zbędn. CRT eksportuje te funkcje wewnętrzne tylko w celu zachowania zgodności binarnej.

## <a name="syntax"></a>Składnia

```cpp
int ___setlc_active_func(void);
int * ___unguarded_readlc_active_add_func(void);
```

## <a name="return-value"></a>Wartość zwracana

Zwracana wartość nie jest znacząca.

## <a name="remarks"></a>Uwagi

Mimo że wewnętrzne funkcje CRT `___setlc_active_func` i `___unguarded_readlc_active_add_func` są przestarzałe i nie są już używane, są eksportowane przez bibliotekę CRT w celu zachowania zgodności binarnej. Pierwotny cel `___setlc_active_func` miał zwrócić liczbę obecnie aktywnych wywołań `setlocale` funkcji. Pierwotny cel `___unguarded_readlc_active_add_func` miał zwrócić liczbę funkcji, do których odwołują się ustawienia regionalne bez blokowania.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|brak|

## <a name="see-also"></a>Zobacz też

[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)
