---
description: 'Dowiedz się więcej na temat: ftell, _ftelli64'
title: ftell, _ftelli64
ms.date: 4/2/2020
api_name:
- _ftelli64
- ftell
- _o__ftelli64
- _o_ftell
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
- _ftelli64
- ftell
helpviewer_keywords:
- ftell function
- ftelli64 function
- _ftelli64 function
- file pointers [C++], getting current position
- file pointers [C++]
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
ms.openlocfilehash: f3fec98cb9d90c8b63072a8e618f58246a6b0147
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334240"
---
# <a name="ftell-_ftelli64"></a>ftell, _ftelli64

Pobiera bieżącą pozycję wskaźnika pliku.

## <a name="syntax"></a>Składnia

```C
long ftell(
   FILE *stream
);
__int64 _ftelli64(
   FILE *stream
);
```

### <a name="parameters"></a>Parametry

*produkcyjne*<br/>
Struktura **pliku** docelowego.

## <a name="return-value"></a>Wartość zwracana

**ftell** i **_ftelli64** zwracają bieżącą pozycję pliku. Wartość zwrócona przez **ftell** i **_ftelli64** może nie odzwierciedlać fizycznego przesunięcia bajtu dla strumieni otwartych w trybie tekstowym, ponieważ tryb tekstowy powoduje translację kanału powrotu karetki. Użyj **ftell** z [fseek](fseek-fseeki64.md) lub **_ftelli64** z [_fseeki64](fseek-fseeki64.md) , aby poprawnie wrócić do lokalizacji plików. W przypadku błędu, **ftell** i **_ftelli64** Wywołaj procedurę obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, te funkcje zwracają wartość-1L i ustawiają **errno** na jedną z dwóch stałych, zdefiniowanych w errno. H. Stała **EBADF** oznacza, że argument *strumienia* nie jest prawidłową wartością wskaźnika pliku lub nie odwołuje się do otwartego pliku. **EINVAL** oznacza, że do funkcji przekazano nieprawidłowy argument *strumienia* . Na urządzeniach bez możliwości wyszukiwania (takich jak terminale i drukarki) lub gdy *strumień* nie odwołuje się do otwartego pliku, wartość zwracana jest niezdefiniowana.

Aby uzyskać więcej informacji na temat tych i innych kodów powrotu, zobacz [_doserrno, errno, _sys_errlist i _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Uwagi

Funkcje **ftell** i **_ftelli64** pobierają bieżącą pozycję wskaźnika pliku (jeśli istnieje) skojarzoną ze *strumieniem*. Pozycja jest wyrażona jako przesunięcie względem początku strumienia.

Należy pamiętać, że gdy plik jest otwierany do dołączania danych, bieżąca pozycja w pliku jest określana przez ostatnią operację we/wy, a nie przez miejsce wystąpienia następnego zapisu. Na przykład, jeśli plik jest otwarty do dołączenia, a Ostatnia operacja była odczytana, pozycja w pliku to punkt, w którym rozpocznie się następna operacja odczytu, a nie w miejscu, w którym rozpocznie się następny zapis. (Po otwarciu pliku do dołączenia, pozycja pliku jest przenoszona na koniec pliku przed jakąkolwiek operacją zapisu). Jeśli nie wykonano jeszcze operacji we/wy na pliku otwartym do dołączenia, pozycja w pliku jest początkiem pliku.

W trybie tekstowym klawisze CTRL + Z są interpretowane jako znak końca pliku na wejściu. W plikach otwartych do odczytu/zapisu, **fopen** i wszystkie powiązane procedury sprawdź, czy Ctrl + Z na końcu pliku i usuń go, jeśli to możliwe. Dzieje się tak, ponieważ używanie kombinacji **ftell** i [fseek](fseek-fseeki64.md) lub **_ftelli64** i [_fseeki64](fseek-fseeki64.md)do przenoszenia w pliku, który kończy się za pomocą kombinacji klawiszy Ctrl + Z, może spowodować, że **ftell** lub **_ftelli64** zachowują się nieprawidłowo blisko końca pliku.

Ta funkcja blokuje wątek wywołujący podczas wykonywania i w związku z tym jest bezpieczny wątkowo. W przypadku wersji, która nie jest blokowana, zobacz **_ftell_nolock**.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Wymagany nagłówek|Opcjonalne nagłówki|
|--------------|---------------------|----------------------|
|**ftell**|\<stdio.h>|\<errno.h>|
|**_ftelli64**|\<stdio.h>|\<errno.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

```C
// crt_ftell.c
// This program opens a file named CRT_FTELL.C
// for reading and tries to read 100 characters. It
// then uses ftell to determine the position of the
// file pointer and displays this position.

#include <stdio.h>

FILE *stream;

int main( void )
{
   long position;
   char list[100];
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )
   {
      // Move the pointer by reading data:
      fread( list, sizeof( char ), 100, stream );
      // Get position after read:
      position = ftell( stream );
      printf( "Position after trying to read 100 bytes: %ld\n",
              position );
      fclose( stream );
   }
}
```

```Output
Position after trying to read 100 bytes: 100
```

## <a name="see-also"></a>Zobacz także

[We/Wy strumienia](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
