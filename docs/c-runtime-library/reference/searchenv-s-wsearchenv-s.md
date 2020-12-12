---
description: 'Dowiedz się więcej na temat: _searchenv_s, _wsearchenv_s'
title: _searchenv_s, _wsearchenv_s
ms.date: 4/2/2020
api_name:
- _wsearchenv_s
- _searchenv_s
- _o__searchenv_s
- _o__wsearchenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _searchenv_s
- _wsearchenv_s
- wsearchenv_s
- searchenv_s
helpviewer_keywords:
- tsearchenv_s function
- files [C++], finding
- buffers [C++], buffer overruns
- environment paths, searching for files
- wsearchenv_s function
- searchenv_s function
- _tsearchenv_s function
- buffer overruns
- buffers [C++], avoiding overruns
- _wsearchenv_s function
- _searchenv_s function
- environment paths
ms.assetid: 47f9fc29-250e-4c09-b52e-9e9f0ef395ca
ms.openlocfilehash: c618840c904bb03eb2f04b9931c7fe7999a278a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288961"
---
# <a name="_searchenv_s-_wsearchenv_s"></a>_searchenv_s, _wsearchenv_s

Wyszukuje plik przy użyciu ścieżek środowiskowych. Te wersje [_searchenv _wsearchenv](searchenv-wsearchenv.md) mają ulepszenia zabezpieczeń, zgodnie z opisem w temacie [funkcje zabezpieczeń w CRT](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Tego interfejsu API nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows. Aby uzyskać więcej informacji, zobacz [funkcje CRT nieobsługiwane w aplikacjach platforma uniwersalna systemu Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Składnia

```C
errno_t _searchenv_s(
   const char *filename,
   const char *varname,
   char *pathname,
   size_t numberOfElements
);
errno_t _wsearchenv_s(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t *pathname,
   size_t numberOfElements
);
template <size_t size>
errno_t _searchenv_s(
   const char *filename,
   const char *varname,
   char (&pathname)[size]
); // C++ only
template <size_t size>
errno_t _wsearchenv_s(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t (&pathname)[size]
); // C++ only
```

### <a name="parameters"></a>Parametry

*Nazwa pliku*<br/>
Nazwa pliku do wyszukania.

*nazwa_zmiennej*<br/>
Środowisko do wyszukania.

*ścieżki*<br/>
Bufor do przechowywania pełnej ścieżki.

*numberOfElements*<br/>
Rozmiar buforu *nazw* .

## <a name="return-value"></a>Wartość zwracana

Zero, jeśli pomyślne; kod błędu w przypadku niepowodzenia.

Jeśli *Nazwa pliku* jest pustym ciągiem, wartość zwracana to **ENOENT**.

### <a name="error-conditions"></a>Warunki błędów

|*Nazwa pliku*|*nazwa_zmiennej*|*ścieżki*|*numberOfElements*|Wartość zwracana|Zawartość *nazwy ścieżki*|
|----------------|---------------|----------------|------------------------|------------------|----------------------------|
|dowolny|dowolny|**NULL**|dowolny|**EINVAL**|n/d|
|**NULL**|dowolny|dowolny|dowolny|**EINVAL**|nie zmieniono|
|dowolny|dowolny|dowolny|<= 0|**EINVAL**|nie zmieniono|

Jeśli wystąpi którykolwiek z tych warunków błędów, zostanie wywołana procedura obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, te funkcje ustawiają **errno** na **EINVAL** i zwracają **EINVAL**.

## <a name="remarks"></a>Uwagi

Procedura **_searchenv_s** wyszukuje plik docelowy w określonej domenie. Zmienna *nazwa_zmiennej* może być dowolnego środowiska lub zmiennej zdefiniowanej przez użytkownika, która określa listę ścieżek katalogów, takich jak **Path**, **lib** i **include**. Ponieważ w **_searchenv_s** jest rozróżniana wielkość liter, wartość *nazwa_zmiennej* powinna być zgodna z wielkością liter zmiennej środowiskowej. Jeśli właściwość *nazwa_zmiennej* nie jest zgodna z nazwą zmiennej środowiskowej zdefiniowanej w środowisku procesu, funkcja zwraca zero, a zmienna *PATHNAME* nie jest zmieniana.

Procedura przeszukuje najpierw plik w bieżącym katalogu roboczym. Jeśli plik nie zostanie znaleziony, będzie wyglądał dalej za pomocą katalogów określonych przez zmienną środowiskową. Jeśli plik docelowy znajduje się w jednym z tych katalogów, nowo utworzona ścieżka jest kopiowana do *nazwy ścieżki*. Jeśli plik *filename* nie zostanie znaleziony, *Nazwa ścieżki* zawiera pusty ciąg zakończony znakiem null.

Bufor nazwy powinien mieć co najmniej **_MAX_PATH** *znaków, aby* pomieścić pełną długość ścieżki skonstruowanej. W przeciwnym razie **_searchenv_s** może przekroczyć bufor *nazw* , co spowodowało nieoczekiwane zachowanie.

**_wsearchenv_s** to dwubajtowa wersja **_searchenv_s**; argumenty do **_wsearchenv_s** są ciągami znaków dwubajtowych. **_wsearchenv_s** i **_searchenv_s** zachowują się identycznie w inny sposób.

W języku C++ korzystanie z tych funkcji jest uproszczone przez przeciążenia szablonów; przeciążenia mogą automatycznie wywnioskować długość buforu (eliminując konieczność określenia argumentu rozmiaru) i mogą automatycznie zastąpić starsze, niezabezpieczone funkcje z ich nowszymi, bezpiecznymi odpowiednikami. Aby uzyskać więcej informacji, zobacz [bezpieczne przeciążenia szablonów](../../c-runtime-library/secure-template-overloads.md).

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Mapowania procedur zwykłego tekstu

|Procedura tchar.h|_UNICODE i _MBCS niezdefiniowane|_MBCS zdefiniowano|_UNICODE zdefiniowano|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsearchenv_s**|**_searchenv_s**|**_searchenv_s**|**_wsearchenv_s**|

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_searchenv_s**|\<stdlib.h>|
|**_wsearchenv_s**|\<stdlib.h> lub \<wchar.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

```C
// crt_searchenv_s.c
/* This program searches for a file in
* a directory specified by an environment variable.
*/

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char pathbuffer[_MAX_PATH];
   char searchfile[] = "CL.EXE";
   char envvar[] = "PATH";
   errno_t err;

   /* Search for file in PATH environment variable: */
   err = _searchenv_s( searchfile, envvar, pathbuffer, _MAX_PATH );
   if (err != 0)
   {
      printf("Error searching the path. Error code: %d\n", err);
   }
   if( *pathbuffer != '\0' )
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );
   else
      printf( "%s not found\n", searchfile );
}
```

```Output
Path for CL.EXE:
C:\Program Files\Microsoft Visual Studio 2010\VC\BIN\CL.EXE
```

## <a name="see-also"></a>Zobacz także

[Kontrolka katalogu](../../c-runtime-library/directory-control.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
