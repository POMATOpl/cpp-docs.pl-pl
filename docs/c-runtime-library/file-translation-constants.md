---
description: 'Dowiedz się więcej na temat: stałe tłumaczenia plików'
title: Stałe tłumaczenia pliku
ms.date: 11/04/2016
helpviewer_keywords:
- translation constants
- file translation [C++], constants
- translation, file translation constants
- translation, constants
- constants [C++], file translation mode
- file translation [C++]
ms.assetid: 49b13bf3-442e-4d19-878b-bd1029fa666a
ms.openlocfilehash: 75bb54c7e038efd41ed22ec941d871f6fbc54b7c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332981"
---
# <a name="file-translation-constants"></a>Stałe tłumaczenia pliku

## <a name="syntax"></a>Składnia

```
#include <stdio.h>
```

## <a name="remarks"></a>Uwagi

Te stałe określają tryb tłumaczenia (**"b"** lub **"t"**). Tryb jest dołączony do ciągu określającego typ dostępu (**"r"**, **"w"**, **"a"**, **"r +"**, **"w +"**, **"a +"**).

Tryby tłumaczenia są następujące:

- **&**

   Otwiera w trybie tekst (przetłumaczony). W tym trybie kombinacje wysuwu wiersza (CR-LF) są tłumaczone na znaki wysuwu wiersza (LF) na wejściu, a sygnały LF są tłumaczone na kombinacje CR-LF w danych wyjściowych. Ponadto CTRL + Z jest interpretowany jako znak końca pliku na wejściu. W plikach otwartych do odczytu lub odczytu i zapisu program `fopen` sprawdza, czy Ctrl + Z na końcu pliku i usuwa go, jeśli jest to możliwe. Dzieje się tak, ponieważ używanie `fseek` `ftell` funkcji i do poruszania się w pliku kończącym się na klawiaturze Ctrl + z może spowodować `fseek` zachowanie nieprawidłowego końca pliku.

   > [!NOTE]
   > Opcja **t** nie jest częścią standardu ANSI dla `fopen` i `freopen` . Jest to rozszerzenie firmy Microsoft i nie powinno być używane w przypadku potrzeby przenoszenia w formacie ANSI.

- **b**

   Otwiera w trybie binarnym (nieprzetłumaczonym). Powyższe tłumaczenia są pomijane.

Jeśli **t** lub **b** nie jest określony w *trybie*, tryb tłumaczenia jest definiowany przez zmienną trybu domyślnego [_fmode](../c-runtime-library/fmode.md). Aby uzyskać więcej informacji na temat używania trybów tekstowych i binarnych, zobacz [plik tekstowy i tryb binarny we/wy](../c-runtime-library/text-and-binary-mode-file-i-o.md).

## <a name="see-also"></a>Zobacz też

[_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)<br/>
[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)<br/>
[freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)<br/>
[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)
