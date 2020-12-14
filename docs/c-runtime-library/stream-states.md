---
description: 'Dowiedz się więcej o: Stany strumienia'
title: Stany strumieni
ms.date: 11/19/2018
helpviewer_keywords:
- streams, states
ms.assetid: 5f28c968-f132-403f-968c-8417ff315e52
ms.openlocfilehash: c691c1fd01feb9f78ff0929775505f08cb625ecc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224182"
---
# <a name="stream-states"></a>Stany strumieni

Prawidłowe Stany i przejścia stanu dla strumienia są pokazane na poniższej ilustracji.

![Diagram stanu strumienia](../c-runtime-library/media/stream.gif "Diagram stanu strumienia")

Każdy z okręgów oznacza stabilny stan. Każdy wiersz oznacza przejście, które może wystąpić w wyniku wywołania funkcji, które działa w strumieniu. Pięć grup funkcji może spowodować przejście stanu.

Funkcje w pierwszych trzech grupach są deklarowane w \<stdio.h> :

- Funkcja odczytu bajtów — [fgetc](../c-runtime-library/reference/fgetc-fgetwc.md), [fgets](../c-runtime-library/reference/fgets-fgetws.md), [fread](../c-runtime-library/reference/fread.md), [fscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [getc —](../c-runtime-library/reference/getc-getwc.md), [GetChar](../c-runtime-library/reference/getc-getwc.md) [, get](../c-runtime-library/gets-getws.md), [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)i [ungetc —](../c-runtime-library/reference/ungetc-ungetwc.md)

- Funkcje zapisu bajtowego — [fprintf —](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fputc](../c-runtime-library/reference/fputc-fputwc.md), [fputs](../c-runtime-library/reference/fputs-fputws.md), [fwrite](../c-runtime-library/reference/fwrite.md), [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [putc](../c-runtime-library/reference/putc-putwc.md), [putchar](../c-runtime-library/reference/putc-putwc.md), [Put](../c-runtime-library/reference/puts-putws.md), [vfprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)i [vprintf —](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)

- Funkcja Position — [fflush](../c-runtime-library/reference/fflush.md), [fseek](../c-runtime-library/reference/fseek-fseeki64.md), [fsetpos](../c-runtime-library/reference/fsetpos.md)i przewijania do [tyłu](../c-runtime-library/reference/rewind.md)

Funkcje w pozostałych dwóch grupach są deklarowane w \<wchar.h> :

- Szerokie funkcje odczytu — [fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md), [fgetws](../c-runtime-library/reference/fgets-fgetws.md), [fwscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [getwc](../c-runtime-library/reference/getc-getwc.md), [getwchar](../c-runtime-library/reference/getc-getwc.md), [ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md)i [wscanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md),

- Szerokie funkcje zapisu — [fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fputwc](../c-runtime-library/reference/fputc-fputwc.md), [fputws](../c-runtime-library/reference/fputs-fputws.md), [putwc](../c-runtime-library/reference/putc-putwc.md), [putwchar](../c-runtime-library/reference/fputc-fputwc.md), [vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md), [vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)i [wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md),

Diagram stanu pokazuje, że należy wywołać jedną z funkcji położenia między większością operacji zapisu i odczytu:

- Nie można wywołać funkcji odczytu, jeśli Ostatnia operacja w strumieniu była zapisem.

- Nie można wywołać funkcji Write, jeśli Ostatnia operacja w strumieniu była odczytana, chyba że ta operacja odczytu ustawi wskaźnik końca pliku.

Na koniec Diagram stanu pokazuje, że operacja pozycjonowania nigdy nie zmniejsza liczby prawidłowych wywołań funkcji, które mogą wykonać następujące czynności.

## <a name="see-also"></a>Zobacz też

[Pliki i strumienie](../c-runtime-library/files-and-streams.md)
