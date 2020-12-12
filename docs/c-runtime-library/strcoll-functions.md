---
description: 'Dowiedz się więcej na temat: funkcje strcoll —'
title: strcoll — Funkcje
ms.date: 11/04/2016
api_location:
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- strcoll
helpviewer_keywords:
- code pages, using for string comparisons
- string comparison [C++], culture-specific
- strcoll functions
- strings [C++], comparing by code page
ms.assetid: c09eeff3-8aba-4cfb-a524-752436d85573
ms.openlocfilehash: 8a0b146bff2eab8927733923367b0ae49ecea4c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235687"
---
# <a name="strcoll-functions"></a>strcoll — Funkcje

Każda z tych `strcoll` `wcscoll` funkcji i porównuje dwa ciągi zgodnie z `LC_COLLATE` ustawieniem kategorii aktualnie używanej strony kodowej. Każda z `_mbscoll` funkcji porównuje dwa ciągi zgodnie z aktualnie używaną stroną kodową. Użyj `coll` funkcji dla porównania ciągów, gdy istnieje różnica pomiędzy kolejnością zestawu znaków i kolejnością znaków leksykograficznych w bieżącej stronie kodowej, a różnica jest istotna dla porównania. Używaj odpowiednich `cmp` funkcji do testowania tylko dla równości ciągów.

### <a name="strcoll-functions"></a>strcoll — Funkcje

|ZNAKÓW|Unicode|MBCS|Opis|
|----------|-------------|----------|-----------------|
|[strcoll —](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[wcscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[_mbscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|Sortuj dwa ciągi|
|[_stricoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|[_wcsicoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|[_mbsicoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|Sortuj dwa ciągi (bez uwzględniania wielkości liter)|
|[_strncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[_wcsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[_mbsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|Sortuj pierwsze `count` znaki dwóch ciągów|
|[_strnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[_wcsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[_mbsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|Sortuj pierwsze `count` znaki dwóch ciągów (bez uwzględniania wielkości liter)|

## <a name="remarks"></a>Uwagi

Wersje jednobajtowe znaku (SBCS) tych funkcji ( `strcoll` , `stricoll` , `_strncoll` i `_strnicoll` ) porównują `string1` i zgodnie z `string2` `LC_COLLATE` ustawieniem kategorii dla bieżących ustawień regionalnych. Funkcje te różnią się od odpowiednich `strcmp` funkcji, w których `strcoll` funkcje używają informacji o stronie kodowej ustawień regionalnych, które udostępniają sekwencje sortowania. W przypadku porównywania ciągów w parametrach lokalnych, w których kolejność zestawu znaków i kolejność znaków leksykograficznych są różne, `strcoll` należy użyć funkcji zamiast odpowiednich `strcmp` funkcji. Aby uzyskać więcej informacji na temat `LC_COLLATE` , zobacz [setlocals](../c-runtime-library/reference/setlocale-wsetlocale.md).

W przypadku niektórych stron kodowych i odpowiednich zestawów znaków kolejność znaków w zestawie znaków może różnić się od kolejności znaków leksykograficznych. W ustawieniach regionalnych języka C nie jest to przypadek: kolejność znaków w zestawie znaków ASCII jest taka sama jak kolejność leksykograficznych znaków. Jednak w niektórych europejskich stronach kodowych, na przykład, znak "a" (wartość 0x61) poprzedza znak "ä" (wartość 0xE4) w zestawie znaków, ale znak "ä" poprzedza znak "a" lexicographically. Aby wykonać leksykograficznych porównanie w takim wystąpieniu, użyj `strcoll` zamiast `strcmp` . Alternatywnie możesz użyć `strxfrm` oryginalnych ciągów, a następnie użyć `strcmp` na ciągach wyników.

`strcoll`, `stricoll` , `_strncoll` i `_strnicoll` automatycznie obsługują ciągi znaków wielobajtowych zgodnie z aktualnie używaną stroną kodową, tak jak ich odpowiedniki dwubajtowe (Unicode). Wersje wielobajtowe (MBCS) tych funkcji, jednak sortują ciągi na podstawie znaku zgodnie z aktualnie używaną stroną kodową.

Ponieważ `coll` funkcje sortują ciągi lexicographically do porównania, podczas gdy `cmp` funkcje po prostu testują dla równości ciągów, `coll` funkcje są znacznie wolniejsze niż odpowiednie `cmp` wersje. W związku z tym `coll` funkcje powinny być używane tylko wtedy, gdy istnieje różnica pomiędzy kolejnością zestawu znaków i kolejnością znaków leksykograficznych w bieżącej stronie kodowej, a różnica jest istotna dla porównania ciągów.

## <a name="see-also"></a>Zobacz też

[Ustawienie](../c-runtime-library/locale.md)<br/>
[Manipulowanie ciągami](../c-runtime-library/string-manipulation-crt.md)<br/>
[localeconv](../c-runtime-library/reference/localeconv.md)<br/>
[_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l](../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[strcmp, wcscmp, _mbscmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)
