---
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
ms.openlocfilehash: a7dd7d74992aeddffead1c6ef0d52cbc69848dad
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957285"
---
# <a name="___setlc_active_func-___unguarded_readlc_active_add_func"></a>___setlc_active_func, ___unguarded_readlc_active_add_func

OBSOLETE. CRT eksportuje te funkcje wewnętrzne tylko w celu zachowania zgodności binarnej.

## <a name="syntax"></a>Składnia

```cpp
int ___setlc_active_func(void);
int * ___unguarded_readlc_active_add_func(void);
```

## <a name="return-value"></a>Wartość zwracana

Zwracana wartość nie jest znacząca.

## <a name="remarks"></a>Uwagi

Mimo że wewnętrzne funkcje `___setlc_active_func` CRT i `___unguarded_readlc_active_add_func` są przestarzałe i nie są już używane, są eksportowane przez bibliotekę CRT w celu zachowania zgodności binarnej. Pierwotny cel `___setlc_active_func` miał zwrócić liczbę obecnie aktywnych wywołań `setlocale` funkcji. Pierwotny cel `___unguarded_readlc_active_add_func` miał zwrócić liczbę funkcji, do których odwołują się ustawienia regionalne bez blokowania.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|brak|

## <a name="see-also"></a>Zobacz także

[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)
