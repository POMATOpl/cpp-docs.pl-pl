---
description: 'Dowiedz się więcej o: kategorie ustawień regionalnych'
title: Kategorie regionalne
ms.date: 11/04/2016
f1_keywords:
- LC_MAX
- LC_MIN
- LC_MONETARY
- LC_TIME
- LC_NUMERIC
- LC_COLLATE
- LC_CTYPE
- LC_ALL
helpviewer_keywords:
- LC_MIN constant
- LC_MONETARY constant
- LC_CTYPE constant
- locale constants
- LC_MAX constant
- LC_ALL constant
- LC_TIME constant
- LC_NUMERIC constant
- LC_COLLATE constant
ms.assetid: 868f1493-fe5d-4722-acab-bfcd374a063a
ms.openlocfilehash: 2c6bfa4b2d1d0b76520043ee5568d51cf28a23c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246386"
---
# <a name="locale-categories"></a>Kategorie regionalne

## <a name="syntax"></a>Składnia

```
#include <locale.h>
```

## <a name="remarks"></a>Uwagi

Kategorie ustawień regionalnych są stałymi manifestu używanymi przez procedury lokalizacyjne, aby określić, która część informacji o ustawieniach regionalnych programu zostanie użyta. Ustawienia regionalne odnoszą się do lokalizacji lokalnej (lub kraju/regionu), dla której można dostosować niektóre aspekty programu. Obszary zależne od ustawień regionalnych obejmują na przykład formatowanie dat lub format wyświetlania wartości pieniężnych.

|Kategoria ustawień regionalnych|Uwzględnione części programu|
|---------------------|-------------------------------|
|`LC_ALL`|Wszystkie zachowania specyficzne dla ustawień regionalnych (wszystkie kategorie)|
|`LC_COLLATE`|Zachowanie `strcoll` funkcji i `strxfrm`|
|`LC_CTYPE`|Zachowanie funkcji obsługi znaków (z wyjątkiem `isdigit` , `isxdigit` , `mbstowcs` , i `mbtowc` , których nie dotyczy)|
|`LC_MAX`|Tak samo jak `LC_TIME`|
|`LC_MIN`|Tak samo jak `LC_ALL`|
|`LC_MONETARY`|Informacje o formatowaniu pieniężnym zwracane przez `localeconv` funkcję|
|`LC_NUMERIC`|Znak dziesiętny dla sformatowanych procedur danych wyjściowych (na przykład `printf` ), procedur konwersji danych i informacji o formatowaniu niepieniężnych zwracanych przez `localeconv` funkcję|
|`LC_TIME`|Zachowanie `strftime` funkcji|

Zobacz [setlocaling, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) na przykład.

## <a name="see-also"></a>Zobacz też

[localeconv](../c-runtime-library/reference/localeconv.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[Funkcje strcoll —](../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)
