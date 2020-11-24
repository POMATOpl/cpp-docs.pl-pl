---
title: fopen_s, _wfopen_s
description: Opisuje interfejs API dla programu `fopen_s` i `_wfopen_s`
ms.date: 11/20/2020
api_name:
- _wfopen_s
- fopen_s
- _o__wfopen_s
- _o_fopen_s
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
- fopen_s
- _tfopen_s
- _wfopen_s
helpviewer_keywords:
- _wfopen_s function
- opening files, for file I/O
- _tfopen_s function
- tfopen_s function
- wfopen_s function
- fopen_s function
- Unicode [C++], creating files
- Unicode [C++], writing files
- files [C++], opening
- Unicode [C++], files
ms.assetid: c534857e-39ee-4a3f-bd26-dfe551ac96c3
ms.openlocfilehash: 1d6d0b739db1177b903c0e8aa8e6f55e49c1df16
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483168"
---
# <a name="fopen_s-_wfopen_s"></a>`fopen_s`, `_wfopen_s`

Otwiera plik. Te wersje systemu [`fopen, _wfopen`](fopen-wfopen.md) mają ulepszenia zabezpieczeń, zgodnie z opisem w temacie [funkcje zabezpieczeń w CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Składnia

```C
errno_t fopen_s(
   FILE** pFile,
   const char *filename,
   const char *mode
);
errno_t _wfopen_s(
   FILE** pFile,
   const wchar_t *filename,
   const wchar_t *mode
);
```

### <a name="parameters"></a>Parametry

*`pFile`*\
Wskaźnik do wskaźnika pliku, który będzie otrzymywał wskaźnik do otwartego pliku.

*`filename`*\
Nazwa pliku.

*`mode`*\
Dozwolony typ dostępu.

## <a name="return-value"></a>Wartość zwracana

Zero, jeśli pomyślne; kod błędu w przypadku niepowodzenia. Aby uzyskać więcej informacji o tych kodach błędów, zobacz [`errno, _doserrno, _sys_errlist, and _sys_nerr`](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

### <a name="error-conditions"></a>Warunki błędów

|*`pFile`*|*`filename`*|*`mode`*|Wartość zwracana|Zawartość *`pFile`*|
|-------------|----------------|------------|------------------|------------------------|
|**`NULL`**|dowolny|dowolny|**`EINVAL`**|bez zmian|
|dowolny|**`NULL`**|dowolny|**`EINVAL`**|bez zmian|
|dowolny|dowolny|**`NULL`**|**`EINVAL`**|bez zmian|

## <a name="remarks"></a>Uwagi

Pliki, które są otwierane przez program **`fopen_s`** i nie mogą być **`_wfopen_s`** współużytkowane. Jeśli potrzebujesz, aby plik można było udostępniać, użyj [`_fsopen, _wfsopen`](fsopen-wfsopen.md) z odpowiednim stałym trybem udostępniania — na przykład **`_SH_DENYNO`** do udostępniania do odczytu i zapisu.

**`fopen_s`** Funkcja otwiera plik, który jest określony przez *filename*. **`_wfopen_s`** jest wersją znaków dwubajtowych **`fopen_s`** ; argumenty, które **`_wfopen_s`** są ciągami znaków dwubajtowych. **`_wfopen_s`** i **`fopen_s`** zachowują się identycznie w inny sposób.

**`fopen_s`** akceptuje ścieżki, które są prawidłowe w systemie plików w punkcie wykonywania; Ścieżki UNC i ścieżki, które obejmują zamapowane dyski sieciowe, są akceptowane przez **`fopen_s`** cały czas, gdy system, który wykonuje kod, ma dostęp do udziału lub zamapowanego dysku sieciowego w czasie wykonywania. Podczas konstruowania ścieżek dla programu **`fopen_s`** nie należy tworzyć założeń dotyczących dostępności dysków, ścieżek ani udziałów sieciowych w środowisku wykonawczym. Jako separatorów katalogów w ścieżce można użyć ukośników (/) lub ukośników odwrotnych ( \\ ).

Te funkcje sprawdzają poprawność swoich parametrów. Jeśli *`pFile`* , *`filename`* , lub *`mode`* jest wskaźnikiem typu null, te funkcje generują wyjątek nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md).

Zawsze sprawdzaj wartość zwracaną, aby sprawdzić, czy funkcja zakończyła się pomyślnie przed wykonaniem dalszych operacji na pliku. Jeśli wystąpi błąd, kod błędu jest zwracany, a zmienna globalna **`errno`** jest ustawiona. Aby uzyskać więcej informacji, zobacz [`errno, _doserrno, _sys_errlist, and _sys_nerr`](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="unicode-support"></a>Obsługa Unicode

**`fopen_s`** obsługuje strumienie plików w formacie Unicode. Aby otworzyć nowy lub istniejący plik Unicode, należy przekazać flagę *CCS* , która określa żądane kodowanie **`fopen_s`** :

**`fopen_s(&fp, "newfile.txt", "rw, ccs=**_encoding_**");`**

Dozwolone wartości *kodowania* to **`UNICODE`** , **`UTF-8`** i **`UTF-16LE`** . Jeśli nie określono wartości dla *`encoding`* , program **`fopen_s`** używa kodowania ANSI.

Jeśli plik już istnieje i jest otwarty do odczytu lub dołączania, znacznik kolejności bajtów (BOM), jeśli jest obecny w pliku, określa kodowanie. Kodowanie BOM ma pierwszeństwo przed kodowaniem, które jest określone przez *`ccs`* flagę. *`ccs`* Kodowanie jest używane tylko wtedy, gdy nie ma BOM lub jeśli plik jest nowym plikiem.

> [!NOTE]
> BOM — wykrywanie ma zastosowanie tylko do plików, które są otwarte w trybie Unicode; oznacza to, przekazując *`ccs`* flagę.

Poniższa tabela zawiera podsumowanie trybów dla różnych *`ccs`* flag, które są nadawane **`fopen_s`** i dla znaków kolejności bajtów w pliku.

### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>Kodowania używane na podstawie flagi CCS i BOM

|Flaga CCS|Brak BOM (lub nowy plik)|BOM: UTF-8|BOM: UTF-16|
|----------------|----------------------------|-----------------|------------------|
|**`UNICODE`**|**`UTF-16LE`**|**`UTF-8`**|**`UTF-16LE`**|
|**`UTF-8`**|**`UTF-8`**|**`UTF-8`**|**`UTF-16LE`**|
|**`UTF-16LE`**|**`UTF-16LE`**|**`UTF-8`**|**`UTF-16LE`**|

Pliki otwarte do pisania w trybie Unicode mają automatycznie zapisywany BOM.

Jeśli *`mode`* jest **`"a, ccs=` _encoding_ kodowanie `"`**, **`fopen_s`** najpierw próbuje otworzyć plik z dostępem do odczytu i zapisu. Jeśli to się powiedzie, funkcja odczytuje BOM, aby określić kodowanie pliku. Jeśli to się nie powiedzie, funkcja używa domyślnego kodowania dla pliku. W obu przypadkach, **`fopen_s`** a następnie ponownie otwiera plik z dostępem tylko do zapisu. (Dotyczy to **`a`** tylko trybu, a nie **`a+`** .)

### <a name="generic-text-routine-mappings"></a>Mapowania procedur zwykłego tekstu

|Procedura TCHAR.H|Nie zdefiniowano _MBCS _UNICODE &|_MBCS zdefiniowano|_UNICODE zdefiniowano|
|---------------------|------------------------------------|--------------------|-----------------------|
|**`_tfopen_s`**|**`fopen_s`**|**`fopen_s`**|**`_wfopen_s`**|

Ciąg znaków *`mode`* określa rodzaj dostępu żądanego dla pliku, w następujący sposób.

|*`mode`*|Access|
|-|-|
| **`"r"`** | Otwiera do odczytu. Jeśli plik nie istnieje lub nie można go znaleźć, **`fopen_s`** wywołanie zakończy się niepowodzeniem. |
| **`"w"`** | Otwiera pusty plik do zapisu. Jeśli dany plik istnieje, jego zawartość zostaje zniszczona. |
| **`"a"`** | Otwiera do zapisu na końcu pliku (dołączanie) bez usuwania znacznika końca pliku (EOF) przed zapisaniem nowych danych do pliku. Tworzy plik, jeśli nie istnieje. |
| **`"r+"`** | Otwiera zarówno do odczytu, jak i do zapisu. Plik musi istnieć. |
| **"w +"** | Otwiera pusty plik do odczytu i zapisu. Jeśli plik istnieje, jego zawartość zostaje zniszczona. |
| **`"a+"`** | Otwiera do odczytu i dołączania. Operacja dołączania obejmuje usunięcie znacznika EOF przed zapisaniem nowych danych w pliku. Znacznik EOF nie zostanie przywrócony po zakończeniu zapisywania. Tworzy plik, jeśli nie istnieje. |

Gdy plik jest otwierany przy użyciu **`"a"`** **`"a+"`** typu dostępu lub, wszystkie operacje zapisu odbywają się na końcu pliku. Wskaźnik pliku można zmienić przy użyciu [`fseek`](fseek-fseeki64.md) lub [`rewind`](rewind.md) , ale jest on zawsze przenoszony z powrotem do końca pliku przed wykonaniem jakiejkolwiek operacji zapisu, aby nie można było zastąpić istniejących danych.

**`"a"`** Tryb nie usuwa znacznika EOF przed dołączeniem do pliku. Po wystąpieniu operacji dołączania polecenie MS-DOS `TYPE` wyświetla tylko dane do oryginalnego znacznika EOF, a nie wszelkie dane, które są dołączane do pliku. **`"a+"`** Tryb powoduje usunięcie znacznika EOF przed dołączeniem do pliku. Po dołączeniu polecenie systemu MS-DOS `TYPE` wyświetla wszystkie dane w pliku. **`"a+"`** Tryb jest wymagany do dołączania do pliku strumienia, który jest zakończony `CTRL+Z` znacznikiem EOF.

W przypadku **`"r+"`** **`"w+"`** określenia typu,, lub **`"a+"`** dostępu, dozwolone jest odczytywanie i zapisywanie. (Plik jest otwarty dla "Update"). Jednak po przełączeniu się z odczytu do zapisu operacja wejściowa musi znajdować się na znaczniku EOF. Jeśli nie ma znacznika EOF, należy użyć wywołania wywołującego do funkcji położenia pliku. Funkcje pozycjonowania plików to **`fsetpos`** , [`fseek`](fseek-fseeki64.md) , i [`rewind`](rewind.md) . Po przełączeniu się z zapisu do odczytu należy użyć wywołania wywołującego do **`fflush`** lub funkcji pozycjonowania plików.

Oprócz powyższych wartości w *`mode`* celu określenia trybu tłumaczenia znaków nowego wiersza można uwzględnić następujące znaki:

|*`mode`* modyfikator|Tryb tłumaczenia|
|-|-|
| **`t`** | Otwórz w trybie tekst (przetłumaczony). |
| **`b`** | Otwórz w trybie binarnym (nieprzetłumaczony); Tłumaczenia obejmujące znaki powrotu karetki i wysuwu wiersza są pomijane. |

W trybie tekstu (tłumaczone) `CTRL+Z` jest interpretowany jako znak końca pliku na wejściu. W plikach otwartych do odczytu/zapisu w programie **`"a+"`** program **`fopen_s`** sprawdza na `CTRL+Z` końcu pliku i usuwa go, jeśli jest to możliwe. Dzieje się tak, ponieważ używanie [`fseek`](fseek-fseeki64.md) i **`ftell`** Aby poruszać się w pliku, który kończy się znakiem `CTRL+Z` , może spowodować [`fseek`](fseek-fseeki64.md) , że zadziała nieprawidłowo blisko końca pliku.

Ponadto w trybie tekstowym kombinacje powrotu karetki i wysuwu wiersza są tłumaczone na dane wejściowe z pojedynczym wierszem, a znaki wysuwu wiersza są tłumaczone na kombinacje kanałów powrotu karetki liniowej w danych wyjściowych. Gdy funkcja strumienia Unicode we/wy działa w trybie tekstowym (wartość domyślna), zakłada się, że strumień źródłowy lub docelowy jest sekwencją znaków wielobajtowych. Funkcje strumienia Unicode — dane wejściowe konwertują znaki wielobajtowe na znaki szerokie (jak w przypadku wywołania **`mbtowc`** funkcji). Z tego samego powodu funkcje strumienia Unicode-Output przekonwertują szerokie znaki na znaki wielobajtowe (jak w przypadku wywołania **`wctomb`** funkcji).

Jeśli **`t`** lub **`b`** nie jest określony w *`mode`* , domyślny tryb tłumaczenia jest definiowany przez zmienną globalną [_fmode](../../c-runtime-library/fmode.md). Jeśli **`t`** **`b`** argument jest poprzedzony prefiksem, funkcja kończy się niepowodzeniem i zwraca wartość **`NULL`** .

Aby uzyskać więcej informacji na temat używania trybów tekstowych i binarnych w strumieniach Unicode i wielobajtowych — we/wy, zobacz [plik tekstowy i tryb binarny we/wy](../../c-runtime-library/text-and-binary-mode-file-i-o.md) i [strumienia Unicode/o w trybach tekstowych i binarnych](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

|*`mode`* modyfikator|Zachowanie|
|-|-|
| **`c`** | Włącz flagę zatwierdzania dla skojarzonej *nazwy pliku* , aby zawartość bufora plików była zapisywana bezpośrednio na dysk, jeśli **`fflush`** lub **`_flushall`** jest wywoływana. |
| **`n`** | Zresetuj flagę zatwierdzania dla skojarzonej *nazwy pliku* na wartość "No-Commit". Jest to opcja domyślna. Zastępuje ona również globalną flagę zatwierdzania w przypadku łączenia programu z TOWARami. OBJ. Globalna flaga zatwierdzania ma wartość "No-Commit", chyba że jawnie łączysz program z TOWARami. OBJ (zobacz [Opcje linku](../../c-runtime-library/link-options.md)). |
| **`n`** | Określa, że plik nie jest dziedziczony przez procesy podrzędne. |
| **`S`** | Określa, że buforowanie jest zoptymalizowane dla, ale nie ograniczone do, dostęp sekwencyjny z dysku. |
| **`R`** | Określa, że buforowanie jest zoptymalizowane dla, ale nie ograniczone do, losowy dostęp z dysku. |
| **`t`** | Określa plik jako tymczasowy. Jeśli to możliwe, nie jest opróżniony na dysk. |
| **`D`** | Określa plik jako tymczasowy. Jest usuwany, gdy ostatni wskaźnik pliku jest zamknięty. |
| **`ccs=**`_Kody_ | Określa zakodowany zestaw znaków, który ma być używany (jeden z **`UTF-8`** , **`UTF-16LE`** lub **`UNICODE`** ) dla tego pliku. Pozostaw nieokreślony, jeśli chcesz użyć kodowania ANSI. |

Prawidłowe znaki w *`mode`* ciągu używanym w **`fopen_s`** i [`_fdopen`](fdopen-wfdopen.md) odpowiadają *`oflag`* argumentom używanym w [`_open`](open-wopen.md) i [`_sopen`](sopen-wsopen.md) , w następujący sposób.

|Znaki w *`mode`* ciągu|Równoważna *`oflag`* wartość dla `_open`/`_sopen`|
|-------------------------------|----------------------------------------------------|
|**`a`**|**`_O_WRONLY`** &#124; **`_O_APPEND`** (zazwyczaj **`_O_WRONLY`** &#124; **`_O_CREAT`** &#124; **`_O_APPEND`** )|
|**`a+`**|**`_O_RDWR`** &#124; **`_O_APPEND`** (zazwyczaj **`_O_RDWR`** &#124; **`_O_APPEND`** &#124; **`_O_CREAT`** )|
|**`R`**|**`_O_RDONLY`**|
|**`r+`**|**`_O_RDWR`**|
|**`w`**|**`_O_WRONLY`** (zwykle **`_O_WRONLY`** &#124; **`_O_CREAT`** &#124; **_O_TRUNC**)|
|**`w+`**|**`_O_RDWR`** (zwykle **`_O_RDWR`** &#124; **`_O_CREAT`** &#124; **_O_TRUNC**)|
|**`b`**|**`_O_BINARY`**|
|**`t`**|**`_O_TEXT`**|
|**`c`**|Brak|
|**`n`**|Brak|
|**`S`**|**`_O_SEQUENTIAL`**|
|**`R`**|**`_O_RANDOM`**|
|**`t`**|**`_O_SHORTLIVED`**|
|**`D`**|**`_O_TEMPORARY`**|
|**`ccs=UNICODE`**|**`_O_WTEXT`**|
|**`ccs=UTF-8`**|**`_O_UTF8`**|
|**`ccs=UTF-16LE`**|**`_O_UTF16`**|

Jeśli używasz **`rb`** trybu, zamapowane w pamięci pliki Win32 mogą również być opcją, jeśli nie musisz przeszukiwać kodu, musisz odczytywać większość plików lub nie masz opieki dotyczącej wydajności sieci.

## <a name="requirements"></a>Wymagania

|Funkcja|Wymagany nagłówek|
|--------------|---------------------|
|**`fopen_s`**|`<stdio.h>`|
|**`_wfopen_s`**|`<stdio.h>` lub `<wchar.h>`|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Wszystkie wersje [bibliotek uruchomieniowych języka C](../../c-runtime-library/crt-library-features.md).

**`c`** Opcje, **`n`** i **`t`** *`mode`* są rozszerzeniami Microsoft dla **`fopen_s`** i nie [`_fdopen`](fdopen-wfdopen.md) powinny być używane w przypadku, gdy wymagana jest przenośność ANSI.

## <a name="example"></a>Przykład

```C
// crt_fopen_s.c
// This program opens two files. It uses
// fclose to close the first file and
// _fcloseall to close all remaining files.

#include <stdio.h>

FILE *stream, *stream2;

int main( void )
{
   errno_t err;

   // Open for read (will fail if file "crt_fopen_s.c" doesn't exist)
   err  = fopen_s( &stream, "crt_fopen_s.c", "r" );
   if( err == 0 )
   {
      printf( "The file 'crt_fopen_s.c' was opened\n" );
   }
   else
   {
      printf( "The file 'crt_fopen_s.c' was not opened\n" );
   }

   // Open for write
   err = fopen_s( &stream2, "data2", "w+" );
   if( err == 0 )
   {
      printf( "The file 'data2' was opened\n" );
   }
   else
   {
      printf( "The file 'data2' was not opened\n" );
   }

   // Close stream if it isn't NULL
   if( stream )
   {
      err = fclose( stream );
      if ( err == 0 )
      {
         printf( "The file 'crt_fopen_s.c' was closed\n" );
      }
      else
      {
         printf( "The file 'crt_fopen_s.c' was not closed\n" );
      }
   }

   // All other files are closed:
   int numclosed = _fcloseall( );
   printf( "Number of files closed by _fcloseall: %u\n", numclosed );
}
```

```Output
The file 'crt_fopen_s.c' was opened
The file 'data2' was opened
Number of files closed by _fcloseall: 1
```

## <a name="see-also"></a>Zobacz także

[We/wy strumienia](../../c-runtime-library/stream-i-o.md)\
[`fclose, _fcloseall`](fclose-fcloseall.md)\
[`_fdopen, _wfdopen`](fdopen-wfdopen.md)\
[`ferror`](ferror.md)\
[`_fileno`](fileno.md)\
[`freopen, _wfreopen`](freopen-wfreopen.md)\
[`_open, _wopen`](open-wopen.md)\
[`_setmode`](setmode.md)
