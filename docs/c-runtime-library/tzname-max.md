---
description: 'Dowiedz się więcej na temat: TZNAME_MAX'
title: TZNAME_MAX
ms.date: 10/22/2018
f1_keywords:
- TZNAME_MAX
helpviewer_keywords:
- TZNAME_MAX constant
ms.assetid: e2286cb8-751d-4557-9650-5c4b98a8f7be
ms.openlocfilehash: 1c426c82bd198998169c385366ae5188cabd02d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162160"
---
# <a name="tzname_max"></a>TZNAME_MAX

**Przestarzałe**. Maksymalna dopuszczalna długość ciągu dla zmiennej nazwy strefy czasowej. To makro zostało zdefiniowane w \<limits.h> programie Visual Studio 2012 i jego wcześniejszych wersjach. Nie jest on zdefiniowany w Visual Studio 2013 i nowszych wersjach. Aby uzyskać długość wymaganą do przechowywania bieżącej nazwy strefy czasowej, użyj [_get_tzname](../c-runtime-library/reference/get-tzname.md).

## <a name="syntax"></a>Składnia

```
#include <limits.h>
```

## <a name="see-also"></a>Zobacz też

[Stałe środowiska](../c-runtime-library/environmental-constants.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)<br/>
[_get_tzname](../c-runtime-library/reference/get-tzname.md)
