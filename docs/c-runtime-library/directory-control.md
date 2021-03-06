---
description: 'Dowiedz się więcej o programie: kontrolka katalogu'
title: Kontrola katalogu
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], directory
- directory control routines
ms.assetid: a72dcf6f-f366-4d20-8850-0e19cc53ca18
ms.openlocfilehash: a4115fc127292916f6f5b013f75104ed5771e5ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321238"
---
# <a name="directory-control"></a>Kontrola katalogu

Te procedury służą do uzyskiwania dostępu do informacji o strukturze katalogów oraz ich modyfikowania.

## <a name="directory-control-routines"></a>Procedury Directory-Control

|Procedura|Zastosowanie|
|-------------|---------|
|[_chdir, _wchdir](../c-runtime-library/reference/chdir-wchdir.md)|Zmień bieżący katalog roboczy|
|[_chdrive](../c-runtime-library/reference/chdrive.md)|Zmień bieżący dysk|
|[_getcwd, _wgetcwd](../c-runtime-library/reference/getcwd-wgetcwd.md)|Pobierz bieżący katalog roboczy dla dysku domyślnego|
|[_getdcwd, _wgetdcwd](../c-runtime-library/reference/getdcwd-wgetdcwd.md)|Pobierz bieżący katalog roboczy dla określonego dysku|
|[_getdiskfree](../c-runtime-library/reference/getdiskfree.md)|Wypełnia strukturę **_diskfree_t** informacjami o stacji dysków.|
|[_getdrive](../c-runtime-library/reference/getdrive.md)|Pobieranie bieżącego (domyślnego) dysku|
|[_getdrives](../c-runtime-library/reference/getdrives.md)|Zwraca maskę bitów reprezentującą aktualnie dostępne stacje dysków.|
|[_mkdir, _wmkdir](../c-runtime-library/reference/mkdir-wmkdir.md)|Utwórz nowy katalog|
|[_rmdir, _wrmdir](../c-runtime-library/reference/rmdir-wrmdir.md)|Usuń katalog|
|[_searchenv, _wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md), [_searchenv_s _wsearchenv_s](../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)|Wyszukaj podany plik w określonych ścieżkach|

## <a name="see-also"></a>Zobacz też

[Procedury środowiska uruchomieniowego języka Universal C według kategorii](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Obsługa plików](../c-runtime-library/file-handling.md)<br/>
[Wywołania systemowe](../c-runtime-library/system-calls.md)<br/>
