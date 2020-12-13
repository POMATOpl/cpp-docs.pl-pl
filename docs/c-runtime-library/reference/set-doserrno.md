---
description: 'Dowiedz się więcej na temat: _set_doserrno'
title: _set_doserrno
ms.date: 4/2/2020
api_name:
- _set_doserrno
- _o__set_doserrno
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _set_doserrno
- set_doserrno
helpviewer_keywords:
- _set_doserrno function
- doserrno global variable
- set_doserrno function
- _doserrno global variable
ms.assetid: 8686c159-3797-4705-a53e-7457869ca6f3
ms.openlocfilehash: c4b7860764505ab7d3388bace6fa86b0726851e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334108"
---
# <a name="_set_doserrno"></a>_set_doserrno

Ustawia wartość zmiennej globalnej [_doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="syntax"></a>Składnia

```C
errno_t _set_doserrno( int error_value );
```

### <a name="parameters"></a>Parametry

*error_value*<br/>
Nowa wartość **_doserrno**.

## <a name="return-value"></a>Wartość zwracana

Zwraca zero, jeśli powodzenie.

## <a name="remarks"></a>Uwagi

Możliwe wartości są zdefiniowane w errno. h.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|Opcjonalny nagłówek|
|-------------|---------------------|---------------------|
|**_set_doserrno**|\<stdlib.h>|\<errno.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[_get_doserrno](get-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
