---
description: 'Dowiedz się więcej na temat: _isatty'
title: _isatty
ms.date: 4/2/2020
api_name:
- _isatty
- _o__isatty
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _isatty
helpviewer_keywords:
- isatty function
- character device checking
- _isatty function
- checking character devices
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
ms.openlocfilehash: 354cb0ba66c0c25291626cf4278935571357d058
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97303625"
---
# <a name="_isatty"></a>_isatty

Określa, czy deskryptor pliku jest skojarzony z urządzeniem znaku.

## <a name="syntax"></a>Składnia

```C
int _isatty( int fd );
```

### <a name="parameters"></a>Parametry

*proces*<br/>
Deskryptor pliku odnoszący się do urządzenia, które ma zostać przetestowane.

## <a name="return-value"></a>Wartość zwracana

**_isatty** zwraca wartość różną od zera, jeśli deskryptor jest skojarzony z urządzeniem znaku. W przeciwnym razie **_isatty** zwraca wartość 0.

## <a name="remarks"></a>Uwagi

Funkcja **_isatty** określa, czy *FD* jest skojarzony z urządzeniem znakowym (terminalem, konsolą, drukarką lub portem szeregowym).

Ta funkcja sprawdza poprawność parametru *FD* . Jeśli *FD* jest nieprawidłowym wskaźnikiem pliku, zostanie wywołana procedura obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, funkcja zwraca wartość 0 i ustawia **errno** na **EBADF**.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_isatty**|\<io.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Wszystkie wersje [bibliotek uruchomieniowych języka C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Przykład

```C
// crt_isatty.c
/* This program checks to see whether
* stdout has been redirected to a file.
*/

#include <stdio.h>
#include <io.h>

int main( void )
{
   if( _isatty( _fileno( stdout ) ) )
      printf( "stdout has not been redirected to a file\n" );
   else
      printf( "stdout has been redirected to a file\n");
}
```

### <a name="sample-output"></a>Przykładowe dane wyjściowe

```Output
stdout has not been redirected to a file
```

## <a name="see-also"></a>Zobacz też

[Obsługa plików](../../c-runtime-library/file-handling.md)<br/>
