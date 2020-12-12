---
description: 'Dowiedz się więcej o: makra Environment-Variable'
title: Makra zmiennych środowiskowych
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, environment variable macros
- environment variables, macros in NMAKE
- macros, environment-variable
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
ms.openlocfilehash: b7beaf8f3e98ea7447d798041f7531ed5da671ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192593"
---
# <a name="environment-variable-macros"></a>Makra zmiennych środowiskowych

NMAKE dziedziczy definicje makr dla zmiennych środowiskowych, które istnieją przed rozpoczęciem sesji. Jeśli zmienna została ustawiona w środowisku systemu operacyjnego, jest dostępna jako makro NMAKE. Dziedziczone nazwy są konwertowane na wielkie litery. Dziedziczenie następuje przed przetwarzaniem wstępnego. Użyj opcji/E, aby spowodować, że makra dziedziczone ze zmiennych środowiskowych zastępują wszystkie makra o tej samej nazwie w pliku reguł programu make.

Makra zmiennych środowiskowych mogą być ponownie zdefiniowane w sesji i zmiana odpowiadającej jej zmiennej środowiskowej. Możesz również zmienić zmienne środowiskowe za pomocą polecenia SET. Użycie polecenia SET do zmiany zmiennej środowiskowej w sesji nie powoduje jednak zmiany odpowiedniego makra.

Na przykład:

```
PATH=$(PATH);\nonesuch

all:
    echo %%PATH%%
```

W tym przykładzie zmiana `PATH` odpowiedniej zmiennej środowiskowej jest `PATH` dołączana `\nonesuch` do ścieżki.

Jeśli zmienna środowiskowa jest zdefiniowana jako ciąg, który w pliku reguł programu make ma niepoprawną składnię, żadne makro nie zostanie utworzone i nie zostanie wygenerowane ostrzeżenie. Jeśli wartość zmiennej zawiera znak dolara ($), NMAKE interpretuje ją jako początek wywołania makra. Użycie makra może spowodować nieoczekiwane zachowanie.

## <a name="see-also"></a>Zobacz też

[Specjalne makra NMAKE](special-nmake-macros.md)
