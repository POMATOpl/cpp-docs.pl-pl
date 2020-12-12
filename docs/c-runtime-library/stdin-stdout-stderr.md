---
description: 'Dowiedz się więcej o: stdin, stdout, stderr'
title: stdin, stdout, stderr
ms.date: 10/23/2018
f1_keywords:
- stdin
- stderr
- stdout
helpviewer_keywords:
- stdout function
- standard output stream
- standard error stream
- stdin function
- standard input stream
- stderr function
ms.assetid: badd4735-596d-4498-857c-ec8b7e670e4c
ms.openlocfilehash: ba31487c472bd714560e919f45ec9e9aa5acd717
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235726"
---
# <a name="stdin-stdout-stderr"></a>stdin, stdout, stderr

## <a name="syntax"></a>Składnia

```
FILE *stdin;
FILE *stdout;
FILE *stderr;
#include <stdio.h>
```

## <a name="remarks"></a>Uwagi

Są to standardowe strumienie danych wejściowych, wyjściowych i błędów.

Domyślnie standardowe dane wejściowe są odczytywane z klawiatury, podczas gdy standardowe wyjście i standardowy błąd są drukowane na ekranie.

Następujące wskaźniki strumienia są dostępne w celu uzyskania dostępu do strumieni standardowych:

|Wskaźnik|Strumień|
|-------------|------------|
|`stdin`|Standardowe dane wejściowe|
|`stdout`|Wyjście standardowe|
|`stderr`|Błąd standardowy|

Te wskaźniki mogą służyć jako argumenty do funkcji. Niektóre funkcje, takie jak [GetChar](../c-runtime-library/reference/getchar-getwchar.md) i [putchar](../c-runtime-library/reference/putchar-putwchar.md), wykorzystują `stdin` i `stdout` automatycznie.

Te wskaźniki są stałymi i nie można przypisać nowych wartości. Funkcja [freopen](../c-runtime-library/reference/freopen-wfreopen.md) może służyć do przekierowywania strumieni do plików dysku lub do innych urządzeń. System operacyjny umożliwia przekierowanie standardowych danych wejściowych i wyjściowych programu na poziomie polecenia.

## <a name="see-also"></a>Zobacz też

[We/Wy strumienia](../c-runtime-library/stream-i-o.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)
