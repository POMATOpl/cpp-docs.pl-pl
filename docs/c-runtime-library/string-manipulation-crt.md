---
title: Manipulowanie ciągami (CRT)
ms.date: 11/04/2016
f1_keywords:
- c.strings
helpviewer_keywords:
- strings [C++], manipulating
- string manipulation
- manipulating strings
ms.assetid: 6545861a-59e7-408d-9d29-2ec9134fc91a
ms.openlocfilehash: fce14ff3e7cd83be0414ccf3e9db7ba2171d0ca7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464873"
---
# <a name="string-manipulation-crt"></a>Manipulowanie ciągami (CRT)

Procedury te działają na ciągi znaków dwubajtowych i znaków wielobajtowych przerwany wartością null znaków jednobajtowych. Użyj procedur manipulowanie buforem, opisanego w [manipulowanie buforem](../c-runtime-library/buffer-manipulation.md), aby pracować z tablic znaków, które nie kończą się znakiem null.

## <a name="string-manipulation-routines"></a>Procedury manipulowania ciągami

|Procedura|Zastosowanie|
|-------------|---------|
|[strcoll —, wcscoll —, _mbscoll —, _strcoll_l —, _wcscoll_l —, _mbscoll_l](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md), [_stricoll —, _wcsicoll —, _mbsicoll —, _stricoll_l —, _wcsicoll_l, _mbsicoll_l —](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md), [_strncoll —, _wcsncoll —, _mbsncoll —, _strncoll_l —, _ wcsncoll_l —, _mbsncoll_l —](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md), [_strnicoll —, _wcsnicoll —, _mbsnicoll —, _strnicoll_l —, _wcsnicoll_l —, _mbsnicoll_l —](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|Porównuje dwa ciągi znaków, przy użyciu informacje o stronie kodowej (**_mbsicoll —** i **_mbsnicoll —** jest rozróżniana wielkość liter)|
|[_strdec, _wcsdec, _mbsdec, _mbsdec_l](../c-runtime-library/reference/strdec-wcsdec-mbsdec-mbsdec-l.md)|Przenoszenie ciągu wskaźnik wstecz o jeden znak|
|[_strinc, _wcsinc, _mbsinc, _mbsinc_l](../c-runtime-library/reference/strinc-wcsinc-mbsinc-mbsinc-l.md)|Rozwijaj wskaźnik ciągu o jeden znak|
|[_mbsnbcat —, _mbsnbcat_l —](../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md), [_mbsnbcat_s —, _mbsnbcat_s_l —](../c-runtime-library/reference/mbsnbcat-s-mbsnbcat-s-l.md)|Dołącz, co najwyżej, pierwsze *n* bajty ciągu o jeden znak do innego|
|[_mbsnbcmp, _mbsnbcmp_l](../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)|Porównaj najpierw *n* bajtów dwa ciągi znaków|
|[_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l](../c-runtime-library/reference/strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)|Zwróć liczbę bajtów znaków w ciągu znaków podana liczba|
|[_mbsnbcpy —, _mbsnbcpy_l —](../c-runtime-library/reference/mbsnbcpy-mbsnbcpy-l.md), [_mbsnbcpy_s —, _mbsnbcpy_s_l —](../c-runtime-library/reference/mbsnbcpy-s-mbsnbcpy-s-l.md)|Kopiuj *n* bajty ciągu|
|[_mbsnbicmp, _mbsnbicmp_l](../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)|Porównaj *n* bajtów dwa ciągi znaków, bez uwzględnienia wielkości liter|
|[_mbsnbset, _mbsnbset_l](../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)|Najpierw ustaw *n* bajtów ciąg znaków do określonego znaku|
|[_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l](../c-runtime-library/reference/strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)|Zwróć liczbę znaków w ciągu liczby podany bajtu|
|[_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l](../c-runtime-library/reference/strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)|Znajdź następny znak w ciągu|
|[_strninc, _wcsninc, _mbsninc, _mbsninc_l](../c-runtime-library/reference/strninc-wcsninc-mbsninc-mbsninc-l.md)|Wskaźnik ciągu wcześniejszym przez *n* znaków|
|[_strspnp, _wcsspnp, _mbsspnp, _mbsspnp_l](../c-runtime-library/reference/strspnp-wcsspnp-mbsspnp-mbsspnp-l.md)|Zwracany wskaźnik do pierwszego znaku w danym ciągu, który jest nie w innym danym ciągu|
|[_scprintf, _scprintf_l, _scwprintf, _scwprintf_l](../c-runtime-library/reference/scprintf-scprintf-l-scwprintf-scwprintf-l.md)|Zwróć liczbę znaków ciągu w formacie|
|[_snscanf —, _snscanf_l —, _snwscanf —, _snwscanf_l —](../c-runtime-library/reference/snscanf-snscanf-l-snwscanf-snwscanf-l.md), [_snscanf_s —, _snscanf_s_l —, _snwscanf_s —, _snwscanf_s_l —](../c-runtime-library/reference/snscanf-s-snscanf-s-l-snwscanf-s-snwscanf-s-l.md)|Odczyt sformatowanych danych o określonej długości ze standardowego strumienia wejściowego.|
|[sscanf —, _sscanf_l —, swscanf —, _swscanf_l —](../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md), [sscanf_s —, _sscanf_s_l —, swscanf_s —, _swscanf_s_l —](../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)|Odczyt sformatowanych danych o określonej długości ze standardowego strumienia wejściowego.|
|[sprintf, _sprintf_l —, swprintf, _swprintf_l —, \__swprintf_l —](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md), [sprintf_s —, _sprintf_s_l —, swprintf_s —, _swprintf_s_l —](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md), [_sprintf_p —, _sprintf_p_l —, _swprintf_p —, _swprintf_p_l —](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|Wpisz sformatowane dane do ciągu|
|[strcat —, wcscat —, _mbscat —](../c-runtime-library/reference/strcat-wcscat-mbscat.md), [strcat_s wcscat_s —, _mbscat_s —](../c-runtime-library/reference/strcat-s-wcscat-s-mbscat-s.md)|Dołączyć jednego ciągu do innego|
|[strchr, wcschr, _mbschr, _mbschr_l](../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md)|Znajdź pierwsze wystąpienie określonego znaku w ciągu|
|[strcmp, wcscmp, _mbscmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)|Porównuje dwa ciągi|[System::String::CompareOrdinal](https://msdn.microsoft.com/library/system.string.compareordinal.aspx)|
|[strcoll —, wcscoll —, _mbscoll —, _strcoll_l —, _wcscoll_l —, _mbscoll_l](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md), [_stricoll —, _wcsicoll —, _mbsicoll —, _stricoll_l —, _wcsicoll_l, _mbsicoll_l —](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md), [_strncoll —, _wcsncoll —, _mbsncoll —, _strncoll_l —, _ wcsncoll_l —, _mbsncoll_l —](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md), [_strnicoll —, _wcsnicoll —, _mbsnicoll —, _strnicoll_l —, _wcsnicoll_l —, _mbsnicoll_l —](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|Porównuje dwa ciągi przy użyciu bieżących ustawień regionalnych kodu strony informacji (**_stricoll —**, **_wcsicoll —**, **_strnicoll —**, i **_wcsnicoll —** są bez uwzględniania wielkości liter)|
|[strcpy, wcscpy —, _mbscpy —](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md), [strcpy_s wcscpy_s —, _mbscpy_s —](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)|Kopiuj jednego ciągu do innego|
|[strcspn, wcscspn, _mbscspn, _mbscspn_l](../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)|Znajdź pierwsze wystąpienie ciągu znaków z określonego zestawu znaków w ciągu|
|[_strdup —, _wcsdup —, _mbsdup —](../c-runtime-library/reference/strdup-wcsdup-mbsdup.md), [_strdup_dbg —, _wcsdup_dbg —](../c-runtime-library/reference/strdup-dbg-wcsdup-dbg.md)|Duplikowanie ciągów|
|[strerror, _strerror —, _wcserror —, \__wcserror —](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md), [strerror_s —, _strerror_s —, _wcserror_s —, \__wcserror_s —](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)|Numer błędu mapy wiadomości ciąg|
|[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)|Format ciągu daty i godziny|
|[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)|Porównuje dwa ciągi bez uwzględniania wielkości liter|
|[strlen —, wcslen —, _mbslen —, _mbslen_l —, _mbstrlen —, _mbstrlen_l —](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md), [strnlen —, strnlen_s —, wcsnlen —, wcsnlen_s —, _mbsnlen —, _mbsnlen_l —, _mbstrnlen —, _mbstrnlen_l —](../c-runtime-library/reference/strnlen-strnlen-s.md)|Znajdź długość ciągu|
|[_strlwr, _wcslwr —, _mbslwr —, _strlwr_l —, _wcslwr_l —, _mbslwr_l —](../c-runtime-library/reference/strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md), [_strlwr_s —, _strlwr_s_l —, _mbslwr_s —, _mbslwr_s_l —, _wcslwr_s —, _wcslwr_s_l —](../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)|Konwertuj ciąg na małe litery.|
|[strncat —, _strncat_l, wcsncat —, _wcsncat_l, _mbsncat —, _mbsncat_l —](../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md), [strncat_s —, _strncat_s_l, wcsncat_s —, _wcsncat_s_l, _mbsncat_s —, _mbsncat_s_l —](../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)|Dołącz z ciągu znaków|
|[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|Porównaj z dwóch ciągów znaków|
|[strncpy —, _strncpy_l —, wcsncpy —, _wcsncpy_l —, _mbsncpy —, _mbsncpy_l —](../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md), [strncpy_s —, _strncpy_s_l —, wcsncpy_s —, _wcsncpy_s_l —, _mbsncpy_s, _mbsncpy_s_l](../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)|Kopiowanie znaków jednego ciągu do innego|
|[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)|Porównywanie znaków z dwóch ciągów bez uwzględniania wielkości liter|
|[_strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l](../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)|Najpierw ustaw *n* znaki ciągu do określonego znaku|[System::String::replace](https://msdn.microsoft.com/library/system.string.replace.aspx)|
|[strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l](../c-runtime-library/reference/strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)|Znajdź pierwszego wystąpienia znaku z jednego ciągu w innym ciągu|
|[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)|Znajdowanie ostatniego wystąpienia danego znaku w ciągu|
|[_strrev, _wcsrev, _mbsrev, _mbsrev_l](../c-runtime-library/reference/strrev-wcsrev-mbsrev-mbsrev-l.md)|Odwróć ciągu|
|[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|Ustaw wszystkie znaki ciągu do określonego znaku|
|[strspn, wcsspn, _mbsspn, _mbsspn_l](../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)|Znajduje pierwsze wystąpienie w ciągu znaków, nie można odnaleźć w innym ciągu|
|[strstr, wcsstr, _mbsstr, _mbsstr_l](../c-runtime-library/reference/strstr-wcsstr-mbsstr-mbsstr-l.md)|Znajdź pierwsze wystąpienie określonego ciągu w innym ciągu|
|[strtok —, _strtok_l —, wcstok —, _wcstok_l —, _mbstok —, _mbstok_l —](../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md), [strtok_s —, _strtok_s_l —, wcstok_s —, _wcstok_s_l —, _mbstok_s —, _mbstok_s_l —](../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md)|Znajdź następny token w ciągu|
|[_strupr —, _strupr_l —, _mbsupr —, _mbsupr_l —, _wcsupr_l —, _wcsupr —](../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md), [_strupr_s —, _strupr_s_l —, _mbsupr_s —, _mbsupr_s_l —, _wcsupr_s —, _wcsupr_s_l —](../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)|Konwertuj ciąg na wielkie litery|
|[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|Przekształć ciąg w postaci sortowany w oparciu o informacje specyficzne dla ustawień regionalnych|
|[vsprintf —, _vsprintf_l —, vswprintf —, _vswprintf_l —, \__vswprintf_l —](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md), [vsprintf_s —, _vsprintf_s_l —, vswprintf_s —, _vswprintf_s_l —](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md), [_vsprintf_p —, _vsprintf_p_l —, _vswprintf_p —, _ vswprintf_p_l —](../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)|Zapis sformatowane wyniki za pomocą wskaźnika do listy argumentów|
|[vsnprintf —, _vsnprintf —, _vsnprintf_l —, _vsnwprintf —, _vsnwprintf_l —](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md), [vsnprintf_s —, _vsnprintf_s —, _vsnprintf_s_l —, _vsnwprintf_s —, _vsnwprintf_s_l —](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)|Zapis sformatowane wyniki za pomocą wskaźnika do listy argumentów|

## <a name="see-also"></a>Zobacz też

[Procedury czasu wykonywania języka Universal C według kategorii](../c-runtime-library/run-time-routines-by-category.md)<br/>
