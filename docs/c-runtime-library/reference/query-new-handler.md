---
description: 'Dowiedz się więcej na temat: _query_new_handler'
title: _query_new_handler
ms.date: 11/04/2016
api_name:
- _query_new_handler
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _query_new_handler
- query_new_handler
helpviewer_keywords:
- query_new_handler function
- handler routines
- error handling
- _query_new_handler function
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
ms.openlocfilehash: 8479ad1ffc6ec03d3cff82df645255fc69b16257
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137153"
---
# <a name="_query_new_handler"></a>_query_new_handler

Zwraca adres bieżącej nowej procedury obsługi.

## <a name="syntax"></a>Składnia

```C
_PNH _query_new_handler(
   void
);
```

## <a name="return-value"></a>Wartość zwracana

Zwraca adres bieżącej nowej procedury obsługi ustawionej przez **_set_new_handler**.

## <a name="remarks"></a>Uwagi

Funkcja C++ **_query_new_handler** zwraca adres bieżącej funkcji obsługi wyjątków ustawionej przez funkcję [_set_new_handler](set-new-handler.md) języka c++. **_set_new_handler** służy do określania funkcji obsługi wyjątków, która ma uzyskać kontrolę, jeśli **`new`** operator nie może przydzielić pamięci. Aby uzyskać więcej informacji, zobacz Omówienie [operatorów New i DELETE](../../cpp/new-and-delete-operators.md) w dokumentacji języka C++.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_query_new_handler**|\<new.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Wszystkie wersje [bibliotek uruchomieniowych języka C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Zobacz też

[Alokacja pamięci](../../c-runtime-library/memory-allocation.md)<br/>
[zwolniony](free.md)<br/>
