---
description: 'Dowiedz się więcej na temat: przewiń do tyłu'
title: przewijanie
ms.date: 4/2/2020
api_name:
- rewind
- _o_rewind
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
- rewind
helpviewer_keywords:
- rewind function
- repositioning file pointers
- file pointers [C++], repositioning
- file pointers [C++]
ms.assetid: 1a460ce1-28d8-4b5e-83a6-633dca29c28a
ms.openlocfilehash: 1b66ee84e562ebbb743413c6f76f67071c754a67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250300"
---
# <a name="rewind"></a>przewijanie

Zmienia położenie wskaźnika pliku na początku pliku.

## <a name="syntax"></a>Składnia

```C
void rewind(
   FILE *stream
);
```

### <a name="parameters"></a>Parametry

*produkcyjne*<br/>
Wskaźnik do struktury **pliku** .

## <a name="remarks"></a>Uwagi

Funkcja **przewijania do tyłu** zmienia położenie wskaźnika pliku skojarzonego ze *strumieniem* na początku pliku. Wywołanie przewijania do **tyłu** jest podobne do

**(void) fseek (** _Stream_**, 0L, SEEK_SET);**

Jednak w przeciwieństwie do [fseek](fseek-fseeki64.md), **przewijanie do tyłu** czyści wskaźniki błędów dla strumienia, a także wskaźnik końca pliku. Ponadto, w przeciwieństwie do [fseek](fseek-fseeki64.md), **przewiń** nie zwraca wartości, aby wskazać, czy wskaźnik został pomyślnie przeniesiony.

Aby wyczyścić bufor klawiatury, użyj **przewinięcie do tyłu** ze strumieniem **stdin**, który jest domyślnie skojarzony z klawiaturą.

Jeśli strumień jest **pustym** wskaźnikiem, zostanie wywołana procedura obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, ta funkcja zwraca i **errno** jest ustawiona na **EINVAL**.

Aby uzyskać informacje o tych i innych kodach błędów, zobacz [_doserrno, errno, _sys_errlist i _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**przewijanie**|\<stdio.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Wszystkie wersje [bibliotek uruchomieniowych języka C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Przykład

```C
// crt_rewind.c
/* This program first opens a file named
* crt_rewind.out for input and output and writes two
* integers to the file. Next, it uses rewind to
* reposition the file pointer to the beginning of
* the file and reads the data back in.
*/
#include <stdio.h>

int main( void )
{
   FILE *stream;
   int data1, data2;

   data1 = 1;
   data2 = -37;

   fopen_s( &stream, "crt_rewind.out", "w+" );
   if( stream != NULL )
   {
      fprintf( stream, "%d %d", data1, data2 );
      printf( "The values written are: %d and %d\n", data1, data2 );
      rewind( stream );
      fscanf_s( stream, "%d %d", &data1, &data2 );
      printf( "The values read are: %d and %d\n", data1, data2 );
      fclose( stream );
   }
}
```

### <a name="output"></a>Dane wyjściowe

```Output
The values written are: 1 and -37
The values read are: 1 and -37
```

## <a name="see-also"></a>Zobacz też

[We/Wy strumienia](../../c-runtime-library/stream-i-o.md)<br/>
