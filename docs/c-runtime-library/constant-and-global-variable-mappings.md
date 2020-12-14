---
description: 'Dowiedz się więcej na temat: stałe i globalne mapowania zmiennych'
title: Mapowania zmiennych globalnych i stałych
ms.date: 11/04/2016
f1_keywords:
- _tenviron
- _TEOF
- _tfinddata_t
helpviewer_keywords:
- tfinddatat function
- tenviron function
- TEOF type
- _TEOF type
- generic-text mappings
- _tenviron function
- _tfinddata_t function
ms.assetid: 3af4fd3e-9ed5-4ed9-96fd-7031e5126fd1
ms.openlocfilehash: 6078564a5f9d6ef28de704f4991264b5de58041b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195765"
---
# <a name="constant-and-global-variable-mappings"></a>Mapowania zmiennych globalnych i stałych

Te stałe, zmienne globalne i mapowania typu standardowego są zdefiniowane w używanie TCHAR. H i zależy od tego, czy stała `_UNICODE` lub `_MBCS` została zdefiniowana w programie.

### <a name="generic-text-constant-and-global-variable-mappings"></a>Generic-Text stałe i globalne mapowania zmiennych

|Nazwa obiektu ogólnego-text|SBCS (_UNICODE, _MBCS nie zdefiniowany)|_MBCS zdefiniowano|_UNICODE zdefiniowano|
|----------------------------------|--------------------------------------------|--------------------|-----------------------|
|`_TEOF`|`EOF`|`EOF`|`WEOF`|
|`_tenviron`|`_environ`|`_environ`|`_wenviron`|
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|

## <a name="see-also"></a>Zobacz też

[Mapowania tekstu ogólnego](../c-runtime-library/generic-text-mappings.md)<br/>
[Mapowania typów danych](../c-runtime-library/data-type-mappings.md)<br/>
[Mapowania procedur](../c-runtime-library/routine-mappings.md)<br/>
[Przykładowy program Generic-Text](../c-runtime-library/a-sample-generic-text-program.md)<br/>
[Używanie mapowań Generic-Text](../c-runtime-library/using-generic-text-mappings.md)
