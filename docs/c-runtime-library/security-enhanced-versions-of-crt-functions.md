---
description: 'Dowiedz się więcej na temat: Security-Enhanced wersje funkcji CRT'
title: Wersje funkcji CRT z rozszerzonymi zabezpieczeniami
ms.date: 03/21/2018
helpviewer_keywords:
- security [CRT]
- security-enhanced CRT
- CRT, security enhancements
ms.assetid: f87e5a01-4cb2-4379-9e8f-d4693828c55a
ms.openlocfilehash: 95e94eb7790ef589fee3287b6cee8997faac7ab6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277209"
---
# <a name="security-enhanced-versions-of-crt-functions"></a>Wersje funkcji CRT z rozszerzonymi zabezpieczeniami

Dostępne są bardziej bezpieczne wersje procedur biblioteki wykonawczej. Aby uzyskać więcej informacji na temat ulepszeń zabezpieczeń w CRT, zobacz [funkcje zabezpieczeń w CRT](../c-runtime-library/security-features-in-the-crt.md).

## <a name="secure-functions"></a>Funkcje bezpieczne

|Funkcja CRT|Ulepszona funkcja zabezpieczeń|Zastosowanie|
|------------------|--------------------------------|---------|
|[_access, _waccess](../c-runtime-library/reference/access-waccess.md)|[_access_s, _waccess_s](../c-runtime-library/reference/access-s-waccess-s.md)|Określanie uprawnienia dostępu do pliku|
|[_alloca](../c-runtime-library/reference/alloca.md)|[_malloca](../c-runtime-library/reference/malloca.md)|Przydzielanie pamięci na stosie|
|[asctime, _wasctime](../c-runtime-library/reference/asctime-wasctime.md)|[asctime_s, _wasctime_s](../c-runtime-library/reference/asctime-s-wasctime-s.md)|Konwertuj czas od typu `struct tm` na ciąg znaków|
|[bsearch](../c-runtime-library/reference/bsearch.md)|[bsearch_s](../c-runtime-library/reference/bsearch-s.md)|Wykonaj wyszukiwanie binarne posortowanej tablicy|
|[_cgets, _cgetws](../c-runtime-library/cgets-cgetws.md)|[_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|Pobieranie ciągu znaków z konsoli programu|
|[_chsize](../c-runtime-library/reference/chsize.md)|[_chsize_s](../c-runtime-library/reference/chsize-s.md)|Zmiana rozmiaru pliku|
|[clearerr](../c-runtime-library/reference/clearerr.md)|[clearerr_s](../c-runtime-library/reference/clearerr-s.md)|Zresetuj wskaźnik błędu dla strumienia|
|[_control87, _controlfp, \_ _control87_2](../c-runtime-library/reference/control87-controlfp-control87-2.md)|[_controlfp_s](../c-runtime-library/reference/controlfp-s.md)|Pobierz i ustaw słowo sterujące zmiennoprzecinkowe|
|[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|[_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)|Formatowanie i drukowanie do konsoli|
|[_cscanf, _cscanf_l, _cwscanf, _cwscanf_l](../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)|[_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l](../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)|Odczytywanie sformatowanych danych z konsoli|
|[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)|[_ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s _wctime64_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)|Konwertuj czas od typu `time_t` `__time32_t` lub `__time64_t` na ciąg znaków|
|[_ecvt](../c-runtime-library/reference/ecvt.md)|[_ecvt_s](../c-runtime-library/reference/ecvt-s.md)|Konwertuj **`double`** liczbę na ciąg|
|[_fcvt](../c-runtime-library/reference/fcvt.md)|[_fcvt_s](../c-runtime-library/reference/fcvt-s.md)|Konwertuje liczbę zmiennoprzecinkową na ciąg.|
|[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)|[fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|Otwieranie pliku|
|[fprintf, _fprintf_l, fwprintf, _fwprintf_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|Drukowanie sformatowanych danych do strumienia|
|[fread](../c-runtime-library/reference/fread.md)|[fread_s](../c-runtime-library/reference/fread-s.md)|Odczytaj z pliku|
|[_fread_nolock](../c-runtime-library/reference/fread-nolock.md)|[_fread_nolock_s](../c-runtime-library/reference/fread-nolock-s2.md)|Odczytaj z pliku bez użycia blokady zapisu wielowątkowego|
|[freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)|[freopen_s, _wfreopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|Ponownie otwórz plik|
|[fscanf, _fscanf_l, fwscanf, _fwscanf_l](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l](../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)|Odczytywanie sformatowanych danych ze strumienia|
|[_ftime, _ftime32, _ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md)|[_ftime_s, _ftime32_s, _ftime64_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)|Pobierz bieżącą godzinę|
|[_gcvt](../c-runtime-library/reference/gcvt.md)|[_gcvt_s](../c-runtime-library/reference/gcvt-s.md)|Przekonwertuj wartość zmiennoprzecinkową na ciąg i Zapisz ją w buforze.|
|[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)|[getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|Pobierz wartość z bieżącego środowiska.|
|[Pobiera, getws](../c-runtime-library/gets-getws.md)|[gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md)|Pobierz wiersz ze `stdin` strumienia|
|[gmtime, _gmtime32, _gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)|[_gmtime32_s, _gmtime64_s](../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)|Konwertuj czas od typu `time_t` do `struct tm` lub z typu `__time64_t` na `struct tm`|
|[itoa, _itoa, ltoa, _ltoa, ultoa, _ultoa, _i64toa, _ui64toa, _itow, _ltow, _ultow, _i64tow, _ui64tow](../c-runtime-library/reference/itoa-itow.md)|[_itoa_s, _ltoa_s, _ultoa_s, _i64toa_s, _ui64toa_s, _itow_s, _ltow_s, _ultow_s, _i64tow_s, _ui64tow_s](../c-runtime-library/reference/itoa-s-itow-s.md)|Konwertuj typ całkowity na ciąg|
|[_lfind](../c-runtime-library/reference/lfind.md)|[_lfind_s](../c-runtime-library/reference/lfind-s.md)|Wykonaj wyszukiwanie liniowe dla określonego klucza|
|[localtime, _localtime32, _localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md)|[localtime_s, _localtime32_s, _localtime64_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)|Konwertuj czas od typu `time_t` do `struct tm` lub z typu `__time64_t` na typ `struct tm` z korektą lokalną|
|[_lsearch](../c-runtime-library/reference/lsearch.md)|[_lsearch_s](../c-runtime-library/reference/lsearch-s.md)|Wykonaj wyszukiwanie liniowe dla wartości; dodaje do końca listy, jeśli nie została znaleziona|
|[_makepath, _wmakepath](../c-runtime-library/reference/makepath-wmakepath.md)|[_makepath_s, _wmakepath_s](../c-runtime-library/reference/makepath-s-wmakepath-s.md)|Utwórz nazwę ścieżki ze składników|
|[_mbccpy, _mbccpy_l](../c-runtime-library/reference/mbccpy-mbccpy-l.md)|[_mbccpy_s, _mbccpy_s_l](../c-runtime-library/reference/mbccpy-s-mbccpy-s-l.md)|Kopiowanie znaku wielobajtowego z jednego ciągu do innego|
|[_mbsnbcat, _mbsnbcat_l](../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)|[_mbsnbcat_s, _mbsnbcat_s_l](../c-runtime-library/reference/mbsnbcat-s-mbsnbcat-s-l.md)|Dołącz, co najwyżej, pierwsze *n* bajtów z jednego ciągu znaków wielobajtowych do innego|
|[_mbsnbcpy, _mbsnbcpy_l](../c-runtime-library/reference/mbsnbcpy-mbsnbcpy-l.md)|[_mbsnbcpy_s, _mbsnbcpy_s_l](../c-runtime-library/reference/mbsnbcpy-s-mbsnbcpy-s-l.md)|Kopiuj *n* bajtów ciągu do ciągu docelowego|
|[_mbsnbset, _mbsnbset_l](../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)|[_mbsnbset_s, _mbsnbset_s_l](../c-runtime-library/reference/mbsnbset-s-mbsnbset-s-l.md)|Ustaw pierwsze *n* bajtów ciągu do określonego znaku|
|[mbsrtowcs](../c-runtime-library/reference/mbsrtowcs.md)|[mbsrtowcs_s](../c-runtime-library/reference/mbsrtowcs-s.md)|Konwertuj ciąg znaków wielobajtowych na odpowiadający ciąg znaków szeroki|
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)|[mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Konwertuj sekwencję znaków wielobajtowych na odpowiadającą sekwencję szerokich znaków|
|[memcpy, wmemcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)|[memcpy_s, wmemcpy_s](../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)|Kopiuj znaki między buforami|
|[memmove, wmemmove](../c-runtime-library/reference/memmove-wmemmove.md)|[memmove_s, wmemmove_s](../c-runtime-library/reference/memmove-s-wmemmove-s.md)|Przenieś jeden bufor do innego|
|[_mktemp, _wmktemp](../c-runtime-library/reference/mktemp-wmktemp.md)|[_mktemp_s, _wmktemp_s](../c-runtime-library/reference/mktemp-s-wmktemp-s.md)|Utwórz unikatową nazwę pliku|
|[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|Drukuj sformatowane dane wyjściowe do standardowego strumienia wyjściowego|
|[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)|[_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|Tworzenie, modyfikowanie lub usuwanie zmiennych środowiskowych|
|[qsort](../c-runtime-library/reference/qsort.md)|[qsort_s](../c-runtime-library/reference/qsort-s.md)|Wykonaj szybkie sortowanie|
|[Rand](../c-runtime-library/reference/rand.md)|[rand_s](../c-runtime-library/reference/rand-s.md)|Generuj numer pseudolosowych|
|[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)|[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)|Odczytywanie sformatowanych danych ze standardowego strumienia wejściowego|
|[_searchenv, _wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md)|[_searchenv_s, _wsearchenv_s](../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)|Wyszukiwanie pliku przy użyciu ścieżek środowiskowych|
|[snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|[_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)|Zapisz sformatowane dane w ciągu|
|[_snscanf, _snscanf_l, _snwscanf, _snwscanf_l](../c-runtime-library/reference/snscanf-snscanf-l-snwscanf-snwscanf-l.md)|[_snscanf_s, _snscanf_s_l, _snwscanf_s, _snwscanf_s_l](../c-runtime-library/reference/snscanf-s-snscanf-s-l-snwscanf-s-snwscanf-s-l.md)|Odczytaj sformatowane dane o określonej długości z ciągu.|
|[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)|[_sopen_s, _wsopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Otwórz plik do udostępnienia|
|[_splitpath, _wsplitpath](../c-runtime-library/reference/splitpath-wsplitpath.md)|[_splitpath_s, _wsplitpath_s](../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)|Przerwij nazwę ścieżki w składnikach|
|[sprintf —, _sprintf_l, swprintf, _swprintf_l, \_ _swprintf_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|[sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|Zapisz sformatowane dane w ciągu|
|[sscanf, _sscanf_l, swscanf, _swscanf_l](../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)|[sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)|Odczytywanie sformatowanych danych z ciągu|
|[strcat, wcscat, _mbscat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)|[strcat_s, wcscat_s, _mbscat_s](../c-runtime-library/reference/strcat-s-wcscat-s-mbscat-s.md)|Dołącz ciąg|
|[strcpy, wcscpy, _mbscpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|[strcpy_s, wcscpy_s, _mbscpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)|Kopiuj ciąg|
|[_strdate, _wstrdate](../c-runtime-library/reference/strdate-wstrdate.md)|[_strdate_s, _wstrdate_s](../c-runtime-library/reference/strdate-s-wstrdate-s.md)|Zwróć bieżącą datę systemową jako ciąg|
|[strerror, _strerror, _wcserror, \_ _wcserror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)|[strerror_s, _strerror_s, _wcserror_s \_ _wcserror_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)|Pobierz komunikat o błędzie systemu ( `strerror` , `_wcserror` ) lub wydrukuj komunikat o błędzie dostarczony przez użytkownika ( `_strerror` , `__wcserror` )|
|[_strlwr, _wcslwr, _mbslwr, _strlwr_l, _wcslwr_l, _mbslwr_l](../c-runtime-library/reference/strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md)|[_strlwr_s, _strlwr_s_l, _mbslwr_s, _mbslwr_s_l, _wcslwr_s, _wcslwr_s_l](../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)|Konwertuj ciąg na małe litery|
|[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)|Dołącz znaki do ciągu|
|[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)|[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)|Kopiuj znaki jednego ciągu do innego|
|[_strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l](../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)|[_strnset_s, _strnset_s_l, _wcsnset_s, _wcsnset_s_l, _mbsnset_s, _mbsnset_s_l](../c-runtime-library/reference/strnset-s-strnset-s-l-wcsnset-s-wcsnset-s-l-mbsnset-s-mbsnset-s-l.md)|Ustaw pierwsze n znaków ciągu do określonego znaku|
|[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|[_strset_s, _strset_s_l, _wcsset_s, _wcsset_s_l, _mbsset_s, _mbsset_s_l](../c-runtime-library/reference/strset-s-strset-s-l-wcsset-s-wcsset-s-l-mbsset-s-mbsset-s-l.md)|Ustaw wszystkie znaki ciągu w określonym znaku|
|[_strtime, _wstrtime](../c-runtime-library/reference/strtime-wstrtime.md)|[_strtime_s, _wstrtime_s](../c-runtime-library/reference/strtime-s-wstrtime-s.md)|Zwróć bieżącą godzinę systemową jako ciąg|
|[strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l](../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md)|[strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md)|Znajdowanie następnego tokenu w ciągu, przy użyciu bieżących ustawień regionalnych lub przekazaniu ustawień regionalnych|
|[_strupr, _strupr_l, _mbsupr, _mbsupr_l, _wcsupr_l, _wcsupr](../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md)|[_strupr_s, _strupr_s_l, _mbsupr_s, _mbsupr_s_l, _wcsupr_s, _wcsupr_s_l](../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)|Konwertuj ciąg na wielkie litery|
|[tmpfile](../c-runtime-library/reference/tmpfile.md)|[tmpfile_s](../c-runtime-library/reference/tmpfile-s.md)|Utwórz plik tymczasowy|
|[_tempnam, _wtempnam, tmpnam, _wtmpnam](../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|[tmpnam_s, _wtmpnam_s](../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md)|Generuj nazwy, których można użyć do tworzenia plików tymczasowych|
|[_umask](../c-runtime-library/reference/umask.md)|[_umask_s](../c-runtime-library/reference/umask-s.md)|Ustaw domyślną maskę uprawnień plików|
|[_vcprintf, _vcprintf_l, _vcwprintf, _vcwprintf_l](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)|[_vcprintf_s, _vcprintf_s_l, _vcwprintf_s, _vcwprintf_s_l](../c-runtime-library/reference/vcprintf-s-vcprintf-s-l-vcwprintf-s-vcwprintf-s-l.md)|Zapisz sformatowane dane wyjściowe do konsoli za pomocą wskaźnika do listy argumentów|
|[vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|[vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l](../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)|Zapisz sformatowane dane wyjściowe przy użyciu wskaźnika do listy argumentów|
|[vfscanf, vfwscanf](../c-runtime-library/reference/vfscanf-vfwscanf.md)|[vfscanf_s, vfwscanf_s](../c-runtime-library/reference/vfscanf-s-vfwscanf-s.md)|Odczytywanie sformatowanych danych ze strumienia|
|[vprintf, _vprintf_l, vwprintf, _vwprintf_l](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|[vprintf_s, _vprintf_s_l, vwprintf_s, _vwprintf_s_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|Zapisz sformatowane dane wyjściowe przy użyciu wskaźnika do listy argumentów|
|[vscanf, vwscanf](../c-runtime-library/reference/vscanf-vwscanf.md)|[vscanf_s, vwscanf_s](../c-runtime-library/reference/vscanf-s-vwscanf-s.md)|Odczytywanie sformatowanych danych ze standardowego strumienia wejściowego|
|[vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md)|[vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)|Zapisz sformatowane dane wyjściowe przy użyciu wskaźnika do listy argumentów|
|[vsprintf, _vsprintf_l, vswprintf, _vswprintf_l, \_ _vswprintf_l](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)|[vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|Zapisz sformatowane dane wyjściowe przy użyciu wskaźnika do listy argumentów|
|[vsscanf, vswscanf](../c-runtime-library/reference/vsscanf-vswscanf.md)|[vsscanf_s, vswscanf_s](../c-runtime-library/reference/vsscanf-s-vswscanf-s.md)|Odczytywanie sformatowanych danych z ciągu|
|[wcrtomb](../c-runtime-library/reference/wcrtomb.md)|[wcrtomb_s](../c-runtime-library/reference/wcrtomb-s.md)|Konwertuj znak dwubajtowy na reprezentację znaku wieloznacznego|
|[wcsrtombs](../c-runtime-library/reference/wcsrtombs.md)|[wcsrtombs_s](../c-runtime-library/reference/wcsrtombs-s.md)|Konwertuj ciąg znaków dwubajtowych na reprezentację w postaci ciągu znaków|
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md)|[wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Konwertuj sekwencję szerokich znaków do odpowiedniej sekwencji znaków wielobajtowych|
|[wctomb, _wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md)|[wctomb_s, _wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Konwertuj znak szeroki do odpowiedniego znaku wielobajtowego|

## <a name="see-also"></a>Zobacz też

[Funkcje biblioteki CRT](../c-runtime-library/crt-library-features.md)
