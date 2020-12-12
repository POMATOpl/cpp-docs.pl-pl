---
description: 'Dowiedz się więcej o: funkcji memset, wmemset'
title: memset, wmemset
ms.date: 11/04/2016
api_name:
- wmemset
- memset
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- memset
- wmemset
helpviewer_keywords:
- wmemset function
- memset function
ms.assetid: e7ceb01b-df69-49c2-b294-a39358ad4699
ms.openlocfilehash: 547cbbcab4966291ab540b6e57f68d4057995ff8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97171351"
---
# <a name="memset-wmemset"></a>memset, wmemset

Ustawia bufory do określonego znaku.

## <a name="syntax"></a>Składnia

```C
void *memset(
   void *dest,
   int c,
   size_t count
);
wchar_t *wmemset(
   wchar_t *dest,
   wchar_t c,
   size_t count
);
```

### <a name="parameters"></a>Parametry

*dest*<br/>
Wskaźnik do miejsca docelowego.

*s*<br/>
Znak do ustawienia.

*liczbą*<br/>
Liczba znaków.

## <a name="return-value"></a>Wartość zwracana

Wartość miejsca *docelowego*.

## <a name="remarks"></a>Uwagi

Ustawia pierwszą *liczbę* znaków miejsca *docelowego* na znak *c*.

**Uwaga dotycząca zabezpieczeń** Upewnij się, że bufor docelowy ma wystarczającą ilość miejsca dla co najmniej *liczby* znaków. Aby uzyskać więcej informacji, zobacz [unikanie przekroczeń buforu](/windows/win32/SecBP/avoiding-buffer-overruns).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**funkcji memset**|\<memory.h> lub \<string.h>|
|**wmemset**|\<wchar.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Wszystkie wersje [bibliotek uruchomieniowych języka C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Przykład

```C
// crt_memset.c
/* This program uses memset to
* set the first four chars of buffer to "*".
*/

#include <memory.h>
#include <stdio.h>

int main( void )
{
   char buffer[] = "This is a test of the memset function";

   printf( "Before: %s\n", buffer );
   memset( buffer, '*', 4 );
   printf( "After:  %s\n", buffer );
}
```

### <a name="output"></a>Dane wyjściowe

```Output
Before: This is a test of the memset function
After:  **** is a test of the memset function
```

Oto przykład użycia wmemset:

```C
// crt_wmemset.c
/* This program uses memset to
* set the first four chars of buffer to "*".
*/

#include <wchar.h>
#include <stdio.h>

int main( void )
{
   wchar_t buffer[] = L"This is a test of the wmemset function";

   wprintf( L"Before: %s\n", buffer );
   wmemset( buffer, '*', 4 );
   wprintf( L"After:  %s\n", buffer );
}
```

### <a name="output"></a>Dane wyjściowe

```Output
Before: This is a test of the wmemset function
After:  **** is a test of the wmemset function
```

## <a name="see-also"></a>Zobacz też

[Manipulowanie buforem](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[_strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l](strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)<br/>
