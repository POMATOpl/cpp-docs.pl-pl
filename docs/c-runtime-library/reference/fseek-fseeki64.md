---
description: 'Dowiedz się więcej na temat: fseek, _fseeki64'
title: fseek, _fseeki64
ms.date: 4/2/2020
api_name:
- _fseeki64
- fseek
- _o__fseeki64
- _o_fseek
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
- fseek
- _fseeki64
helpviewer_keywords:
- _fseeki64 function
- fseeki64 function
- fseek function
- file pointers [C++], moving
- file pointers [C++]
- seek file pointers
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
ms.openlocfilehash: 7e15bd7cd273da2f73a58c2bd012670216c1938c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114328"
---
# <a name="fseek-_fseeki64"></a>fseek, _fseeki64

Przenosi wskaźnik pliku do określonej lokalizacji.

## <a name="syntax"></a>Składnia

```C
int fseek(
   FILE *stream,
   long offset,
   int origin
);
int _fseeki64(
   FILE *stream,
   __int64 offset,
   int origin
);
```

### <a name="parameters"></a>Parametry

*produkcyjne*<br/>
Wskaźnik do struktury **pliku** .

*Przesunięcie*<br/>
Liczba bajtów od *początku*.

*połączenie pierwotne*<br/>
Pozycja początkowa.

## <a name="return-value"></a>Wartość zwracana

Jeśli to się powiedzie, **fseek** i **_fseeki64** zwraca 0. W przeciwnym razie zwraca wartość różną od zera. Na urządzeniach, które nie mogą przeszukiwania, wartość zwracana jest niezdefiniowana. Jeśli *strumień* jest wskaźnikiem typu null lub jeśli *Źródło* nie jest jedną z dozwolonych wartości opisanych poniżej, **fseek** i **_fseeki64** wywołać procedurę obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, te funkcje ustawiają **errno** na **EINVAL** i Return-1.

## <a name="remarks"></a>Uwagi

Funkcje **fseek** i **_fseeki64** przesuwają wskaźnik pliku (jeśli istnieje) skojarzony ze *strumieniem* do nowej lokalizacji, która jest *przesunięta* o bajty od *początku*. Kolejna operacja w strumieniu odbywa się w nowej lokalizacji. W przypadku otwartego strumienia na potrzeby aktualizacji kolejną operacją może być odczyt lub zapis. Pochodzenie  argumentu musi być jedną z następujących stałych zdefiniowanych w stdio. C

|wartość pochodzenia|Znaczenie|
|-|-|
| **SEEK_CUR** | Bieżąca pozycja wskaźnika pliku. |
| **SEEK_END** | Koniec pliku. |
| **SEEK_SET** | Początek pliku. |

Możesz użyć **fseek** i **_fseeki64** , aby zmienić położenie wskaźnika w dowolnym miejscu w pliku. Wskaźnik może być również umieszczony poza końcem pliku. **fseek** i **_fseeki64** czyści wskaźnik końca pliku i wyklucza efekt wszystkich wcześniejszych wywołań [ungetc —](ungetc-ungetwc.md) do *strumienia*.

Gdy plik jest otwierany do dołączania danych, bieżąca pozycja w pliku jest określana przez ostatnią operację we/wy, a nie przez miejsce wystąpienia następnego zapisu. Jeśli nie wykonano jeszcze operacji we/wy na pliku otwartym do dołączenia, pozycja w pliku jest początkiem pliku.

W przypadku strumieni otwartych w trybie tekstowym **fseek** i **_fseeki64** mają ograniczone użycie, ponieważ translacja kanałów powrotu karetki z wiersza może spowodować, że **fseek** i **_fseeki64** generują nieoczekiwane wyniki. Jedyne operacje **fseek** i **_fseeki64** , które gwarantują działanie na strumieniach otwartych w trybie tekstowym, to:

- Wyszukiwanie z przesunięciem równym 0 względem którejkolwiek z wartości pochodzenia.

- Wyszukiwanie od początku pliku z wartością przesunięcia zwracaną z wywołania do [ftell](ftell-ftelli64.md) podczas korzystania z **fseek** lub [_ftelli64](ftell-ftelli64.md) przy użyciu **_fseeki64**.

Ponadto w trybie tekstowym klawisze CTRL + Z są interpretowane jako znak końca pliku na wejściu. W plikach otwartych do odczytu/zapisu, [fopen](fopen-wfopen.md) i wszystkie powiązane procedury sprawdź, czy Ctrl + Z na końcu pliku i usuń go, jeśli to możliwe. Dzieje się tak, ponieważ używanie kombinacji **fseek** i [ftell](ftell-ftelli64.md) lub **_fseeki64** i [_ftelli64](ftell-ftelli64.md)do przenoszenia w pliku, który kończy się za pomocą kombinacji klawiszy Ctrl + Z, może spowodować, że **fseek** lub **_fseeki64** zachowują się nieprawidłowo blisko końca pliku.

Gdy CRT otwiera plik zaczynający się od znaku kolejności bajtów (BOM), wskaźnik pliku jest umieszczony po BOM (czyli na początku rzeczywistej zawartości pliku). Jeśli musisz **fseek** na początku pliku, użyj [ftell](ftell-ftelli64.md) , aby pobrać początkową pozycję i **fseek** do niej, a nie pozycję 0.

Ta funkcja blokuje inne wątki podczas wykonywania i dlatego jest bezpieczna wątkowo. W przypadku wersji, która nie jest blokowana, zobacz [_fseek_nolock, _fseeki64_nolock](fseek-nolock-fseeki64-nolock.md).

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Wymagany nagłówek|
|--------------|---------------------|
|**fseek**|\<stdio.h>|
|**_fseeki64**|\<stdio.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

```C
// crt_fseek.c
// This program opens the file FSEEK.OUT and
// moves the pointer to the file's beginning.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char line[81];
   int  result;

   if ( fopen_s( &stream, "fseek.out", "w+" ) != 0 )
   {
      printf( "The file fseek.out was not opened\n" );
      return -1;
   }
   fprintf( stream, "The fseek begins here: "
                    "This is the file 'fseek.out'.\n" );
   result = fseek( stream, 23L, SEEK_SET);
   if( result )
      perror( "Fseek failed" );
   else
   {
      printf( "File pointer is set to middle of first line.\n" );
      fgets( line, 80, stream );
      printf( "%s", line );
    }
   fclose( stream );
}
```

```Output
File pointer is set to middle of first line.
This is the file 'fseek.out'.
```

## <a name="see-also"></a>Zobacz także

[We/Wy strumienia](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[przewijanie](rewind.md)<br/>
