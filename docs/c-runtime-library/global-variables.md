---
description: Dowiedz się więcej o zmiennych globalnych
title: Zmienne globalne
ms.date: 11/04/2016
f1_keywords:
- c.variables
helpviewer_keywords:
- global variables
- variables, global
- global variables, Microsoft run-time library
ms.assetid: 01d1551c-2f0c-4f72-935c-6442caccf84f
ms.openlocfilehash: 8029f058b39cb2e069c83279b361b79f3c8f5515
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229889"
---
# <a name="global-variables"></a>Zmienne globalne

Biblioteka wykonawcza języka Microsoft C udostępnia następujące zmienne globalne lub makra. Niektóre z tych zmiennych globalnych lub makr zostały zaniechane na rzecz bardziej bezpiecznych wersji funkcjonalnych, które zalecamy użycie zamiast zmiennych globalnych.

|Zmienna|Opis|
|--------------|-----------------|
|[__argc, \_ _argv, \_ _wargv](../c-runtime-library/argc-argv-wargv.md)|Zawiera argumenty wiersza polecenia.|
|[_daylight, _dstbias, _timezone, i _tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)|Przestarzałe. Zamiast tego należy użyć `_get_daylight` , `_get_dstbias` , `_get_timezone` , i `_get_tzname` .<br /><br /> Dostosowuje czas lokalny; używane w niektórych funkcjach daty i godziny.|
|[errno, _doserrno, _sys_errlist, and _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)|Przestarzałe. Zamiast tego należy używać `_get_errno` , `_set_errno` ,, `_get_doserrno` `_set_doserrno` , `perror` i `strerror` .<br /><br /> Przechowuje kody błędów i powiązane informacje.|
|[_environ, _wenviron](../c-runtime-library/environ-wenviron.md)|Przestarzałe. Zamiast tego należy używać `getenv_s` ,,,, `_wgetenv_s` `_dupenv_s` `_wdupenv_s` `_putenv_s` , i `_wputenv_s` .<br /><br /> Wskaźniki do tablic wskaźników do ciągów środowiska przetwarzania; zainicjowany podczas uruchamiania.|
|[_fmode](../c-runtime-library/fmode.md)|Przestarzałe. Zamiast tego należy użyć `_get_fmode` lub `_set_fmode` .<br /><br /> Ustawia domyślny tryb translacji plików.|
|[_iob](../c-runtime-library/iob.md)|Tablica struktur formantów we/wy dla konsoli, plików i urządzeń.|
|[_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)|Zawiera informacje używane przez funkcje klasyfikacji znaków.|
|[_pgmptr, _wpgmptr](../c-runtime-library/pgmptr-wpgmptr.md)|Przestarzałe. Zamiast tego należy użyć `_get_pgmptr` lub `_get_wpgmptr` .<br /><br /> Zainicjowany przy uruchamianiu programu do w pełni kwalifikowana lub względna ścieżka programu, pełna nazwa programu lub nazwa programu bez rozszerzenia nazwy pliku, w zależności od sposobu wywołania programu.|

## <a name="see-also"></a>Zobacz też

[Dokumentacja biblioteki środowiska uruchomieniowego języka C](../c-runtime-library/c-run-time-library-reference.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)<br/>
[__argc, \_ _argv, \_ _wargv](../c-runtime-library/argc-argv-wargv.md)<br/>
[_get_daylight](../c-runtime-library/reference/get-daylight.md)<br/>
[_get_dstbias](../c-runtime-library/reference/get-dstbias.md)<br/>
[_get_timezone](../c-runtime-library/reference/get-timezone.md)<br/>
[_get_tzname](../c-runtime-library/reference/get-tzname.md)<br/>
[pError](../c-runtime-library/reference/perror-wperror.md)<br/>
[strerror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)<br/>
[_get_doserrno](../c-runtime-library/reference/get-doserrno.md)<br/>
[_set_doserrno](../c-runtime-library/reference/set-doserrno.md)<br/>
[_get_errno](../c-runtime-library/reference/get-errno.md)<br/>
[_set_errno](../c-runtime-library/reference/set-errno.md)<br/>
[_dupenv_s, _wdupenv_s](../c-runtime-library/reference/dupenv-s-wdupenv-s.md)<br/>
[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)<br/>
[getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)<br/>
[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)<br/>
[_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)<br/>
[_get_fmode](../c-runtime-library/reference/get-fmode.md)<br/>
[_set_fmode](../c-runtime-library/reference/set-fmode.md)
