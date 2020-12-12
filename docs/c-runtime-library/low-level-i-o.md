---
description: 'Dowiedz się więcej na temat: Low-Level we/wy'
title: We/Wy niskiego poziomu
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [CRT], low-level
- I/O [CRT], functions
- low-level I/O routines
- file handles [C++]
- file handles [C++], I/O functions
ms.assetid: 53e11bdd-6720-481c-8b2b-3a3a569ed534
ms.openlocfilehash: 88e159e9f85cd4f893616d3aef935417f5abde52
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164981"
---
# <a name="low-level-io"></a>We/Wy niskiego poziomu

Te funkcje wywołują system operacyjny bezpośrednio dla operacji niższego poziomu niż zapewniane przez we/wy strumienia. Wywołania danych wejściowych i wyjściowych niskiego poziomu nie buforują ani nie formatują danych.

Procedury niskiego poziomu mogą uzyskiwać dostęp do standardowych strumieni otwartych podczas uruchamiania programu przy użyciu następujących wstępnie zdefiniowanych deskryptorów plików.

|Strumień|Deskryptor pliku|
|------------|---------------------|
|**Wejścia**|0|
|**stdout**|1|
|**stderr**|2|

Procedury we/wy niskiego poziomu ustawiają zmienną globalną [errno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) w przypadku wystąpienia błędu. Musisz dołączyć STDIO. H użycie funkcji niskiego poziomu tylko wtedy, gdy program wymaga stałej, która jest zdefiniowana w STDIO. H, na przykład wskaźnik końca pliku (**eof**).

## <a name="low-level-io-functions"></a>Low-Level funkcje we/wy

|Funkcja|Zastosowanie|
|--------------|---------|
|[_close](../c-runtime-library/reference/close.md)|Zamknij plik|
|[_commit](../c-runtime-library/reference/commit.md)|Opróżnianie pliku na dysk|
|[_creat, _wcreat](../c-runtime-library/reference/creat-wcreat.md)|Utwórz plik|
|[_dup](../c-runtime-library/reference/dup-dup2.md)|Zwróć następny dostępny deskryptor pliku dla danego pliku|
|[_dup2](../c-runtime-library/reference/dup-dup2.md)|Utwórz drugi deskryptor dla danego pliku|
|[_eof](../c-runtime-library/reference/eof.md)|Testuj pod kątem końca pliku|
|[_lseek, _lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)|Zmień położenie wskaźnika pliku na podaną lokalizację|
|[_open, _wopen](../c-runtime-library/reference/open-wopen.md)|Otwórz plik|
|[_read](../c-runtime-library/reference/read.md)|Odczytaj dane z pliku|
|[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md), [_sopen_s _wsopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Otwórz plik do udostępniania plików|
|[_tell, _telli64](../c-runtime-library/reference/tell-telli64.md)|Pobierz bieżącą pozycję wskaźnika pliku|
|[_umask](../c-runtime-library/reference/umask.md), [_umask_s](../c-runtime-library/reference/umask-s.md)|Ustaw maskę uprawnień pliku|
|[_write](../c-runtime-library/reference/write.md)|Zapisz dane do pliku|

**_dup** i **_dup2** są zwykle używane do kojarzenia wstępnie zdefiniowanych deskryptorów plików z różnymi plikami.

## <a name="see-also"></a>Zobacz też

[Wejście i wyjście](../c-runtime-library/input-and-output.md)<br/>
[Procedury środowiska uruchomieniowego języka Universal C według kategorii](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Wywołania systemowe](../c-runtime-library/system-calls.md)<br/>
