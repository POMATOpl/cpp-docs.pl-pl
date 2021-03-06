---
description: 'Dowiedz się więcej na temat: _memccpy'
title: _memccpy
ms.date: 11/04/2016
api_name:
- _memccpy
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
- api-ms-win-crt-string-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _memccpy
helpviewer_keywords:
- _memccpy function
- memccpy function
ms.assetid: 9a2337df-6e85-4eba-b247-dd0532f45ddb
ms.openlocfilehash: f3cbfbd1e112c724d6223a6c6d28f0915dcd7ca0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240094"
---
# <a name="_memccpy"></a>_memccpy

Kopiuje znaki z buforu.

## <a name="syntax"></a>Składnia

```C
void *_memccpy(
   void *dest,
   const void *src,
   int c,
   size_t count
);
```

### <a name="parameters"></a>Parametry

*dest*<br/>
Wskaźnik do miejsca docelowego.

*src*<br/>
Wskaźnik do źródła.

*s*<br/>
Ostatni znak do skopiowania.

*liczbą*<br/>
Liczba znaków.

## <a name="return-value"></a>Wartość zwracana

Jeśli znak *c* jest kopiowany, **_memccpy** zwraca wskaźnik do znaku w elemencie *docelowy* , który bezpośrednio następuje po znaku. Jeśli *c* nie jest kopiowana, zwraca **wartość null**.

## <a name="remarks"></a>Uwagi

Funkcja **_memccpy** kopiuje 0 lub więcej znaków *src* do miejsca *docelowego*, zatrzymuje się po skopiowaniu znaku *c* lub po skopiowaniu *liczby* znaków, w zależności od tego, co nastąpi wcześniej.

**Uwaga dotycząca zabezpieczeń** Upewnij się, że bufor docelowy ma ten sam rozmiar lub większy niż bufor źródłowy. Aby uzyskać więcej informacji, zobacz [unikanie przekroczeń buforu](/windows/win32/SecBP/avoiding-buffer-overruns).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_memccpy**|\<memory.h> lub \<string.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Wszystkie wersje [bibliotek uruchomieniowych języka C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Przykład

```C
// crt_memccpy.c

#include <memory.h>
#include <stdio.h>
#include <string.h>

char string1[60] = "The quick brown dog jumps over the lazy fox";

int main( void )
{
   char buffer[61];
   char *pdest;

   printf( "Function: _memccpy 60 characters or to character 's'\n" );
   printf( "Source: %s\n", string1 );
   pdest = _memccpy( buffer, string1, 's', 60 );
   *pdest = '\0';
   printf( "Result: %s\n", buffer );
   printf( "Length: %d characters\n", strlen( buffer ) );
}
```

### <a name="output"></a>Dane wyjściowe

```Output
Function: _memccpy 60 characters or to character 's'
Source: The quick brown dog jumps over the lazy fox
Result: The quick brown dog jumps
Length: 25 characters
```

## <a name="see-also"></a>Zobacz też

[Manipulowanie buforem](../../c-runtime-library/buffer-manipulation.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
