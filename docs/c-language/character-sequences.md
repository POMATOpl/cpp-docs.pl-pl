---
description: 'Dowiedz się więcej o programie: sekwencje znaków'
title: Sekwencje znaków
ms.date: 11/04/2016
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
ms.openlocfilehash: ac5642371389047bd8ce3a83e02dc13802167dc0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305081"
---
# <a name="character-sequences"></a>Sekwencje znaków

**3.8.2 ANSI** Mapowanie sekwencji znaków pliku źródłowego

Instrukcje preprocesora używają tego samego zestawu znaków jako instrukcji pliku źródłowego z wyjątkiem tego, że sekwencje ucieczki nie są obsługiwane.

Aby określić ścieżkę do pliku dołączanego, należy użyć tylko jednego ukośnika odwrotnego:

```
#include "path1\path2\myfile"
```

W ramach kodu źródłowego wymagane są dwa ukośniki odwrotne:

```
fil = fopen( "path1\\path2\\myfile", "rt" );
```

## <a name="see-also"></a>Zobacz też

[Dyrektywy przetwarzania wstępnego](../c-language/preprocessing-directives.md)
