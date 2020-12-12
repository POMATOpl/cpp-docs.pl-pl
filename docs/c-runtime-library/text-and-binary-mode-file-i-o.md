---
description: 'Dowiedz się więcej o: plik tekstowy i tryb binarny we/wy'
title: Operacja We/Wy pliku w trybie binarnym i tekstowym
ms.date: 04/11/2018
helpviewer_keywords:
- files [C++], open functions
- I/O [CRT], text files
- functions [CRT], file access
- binary access, binary mode file I/O
- translation, modes
- I/O [CRT], binary
- text files, I/O
- I/O [CRT], translation modes
- translation modes (file I/O)
- binary access
ms.assetid: 3196e321-8b87-4609-b302-cd6f3c516051
ms.openlocfilehash: de4e7e7ea1792a23aac3507ec191f3433112b8dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326898"
---
# <a name="text-and-binary-mode-file-io"></a>Operacja We/Wy pliku w trybie binarnym i tekstowym

Operacje we/wy na plikach odbywają się w jednym z dwóch trybów translacji, *tekstu* lub danych *binarnych*, w zależności od trybu, w którym plik jest otwarty. Pliki danych są zwykle przetwarzane w trybie tekstowym. Aby sterować trybem tłumaczenia plików, jeden może:

- Zachowywanie bieżącego ustawienia domyślnego i Określanie trybu alternatywnego tylko wtedy, gdy otwierane są wybrane pliki.

- Użyj [_set_fmode](../c-runtime-library/reference/set-fmode.md) funkcji, aby zmienić domyślny tryb dla nowo otwartych plików. Użyj [_get_fmode](../c-runtime-library/reference/get-fmode.md) , aby znaleźć bieżący tryb domyślny. Początkowe ustawienie domyślne to tryb tekstowy (**_O_TEXT**).

- Zmień domyślny tryb tłumaczenia bezpośrednio, ustawiając zmienną globalną [_fmode](../c-runtime-library/fmode.md) w programie. Funkcja **_set_fmode** ustawia wartość tej zmiennej, ale można ją również ustawić bezpośrednio.

Po wywołaniu funkcji otwierania plików, takiej jak [_open](../c-runtime-library/reference/open-wopen.md), [fopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md), [freopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md), [_fsopen](../c-runtime-library/reference/fsopen-wfsopen.md) lub [_sopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md), można zastąpić bieżące domyślne ustawienie **_fmode** , określając odpowiedni argument dla funkcji [_set_fmode](../c-runtime-library/reference/set-fmode.md). Strumienie **stdin**, **stdout** i **stderr** zawsze są domyślnie otwierane w trybie tekstowym; Możesz również zastąpić to ustawienie domyślne podczas otwierania dowolnego z tych plików. Użyj [_setmode](../c-runtime-library/reference/setmode.md) , aby zmienić tryb tłumaczenia przy użyciu deskryptora pliku po otwarciu pliku.

## <a name="see-also"></a>Zobacz też

[Wejście i wyjście](../c-runtime-library/input-and-output.md)<br/>
[Procedury środowiska uruchomieniowego języka Universal C według kategorii](../c-runtime-library/run-time-routines-by-category.md)<br/>
