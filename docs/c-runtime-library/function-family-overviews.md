---
title: Omówienie rodziny funkcji
description: Omówienie funkcji środowiska uruchomieniowego języka Microsoft C według rodziny.
ms.date: 10/05/2020
ms.assetid: b05a2755-9d11-4ea9-ab97-d00a4e872e16
ms.openlocfilehash: de5192cd03c3821afc646241d75a3e8c6c8c12e3
ms.sourcegitcommit: 8caaf5e00aeb727741a273aecafa15de293426cf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/07/2020
ms.locfileid: "91806516"
---
# <a name="function-family-overview"></a>Omówienie rodziny funkcji

W tej sekcji przedstawiono procedury biblioteki środowiska uruchomieniowego języka C według rodziny funkcji.

## <a name="crt-library-routine-families"></a>Rodziny procedur biblioteki CRT

[_exec, _wexec](exec-wexec-functions.md)\
Funkcje do ładowania i uruchamiania nowego procesu.

[Funkcje wyszukiwania nazw plików](filename-search-functions.md)\
Funkcje do wyszukiwania określonych nazw plików i zamykania wyszukiwania.

[Składnia specyfikacji formatu dla `printf` i `wprintf`](format-specification-syntax-printf-and-wprintf-functions.md)\
Opisuje ciąg formatu i argumenty dla `printf` i `wprintf` .

[Znaki pola specyfikacji formatu: `scanf` i `wscanf`](format-specification-fields-scanf-and-wscanf-functions.md)\
Opisuje pola specyfikacji formatu umożliwiające analizowanie strumienia wejściowego dla całej `scanf` rodziny funkcji.

[`is`, `isw` funkcje](is-isw-routines.md)\
Funkcje służące do testowania znaków w taki sposób, że są to wielkie litery, ASCII, cyfry, znaki interpunkcyjne i tak dalej.

[`_ismbb` obowiązki](ismbb-routines.md)\
Funkcja do testowania wartości całkowitej określająca, czy reprezentuje znak alfanumeryczny, pusty znak, znak Print i tak dalej.

[`_ismbc` obowiązki](ismbc-routines.md)\
Funkcje do testowania znaku wielobajtowego, który reprezentuje znak alfanumeryczny, pusty znak, znak Print i tak dalej.

[— operator `delete` (CRT)](delete-operator-crt.md)\
Począwszy od Visual Studio 2013, uniwersalne środowisko uruchomieniowe C (UCRT) nie obsługuje już funkcji usuwania operatorów specyficznych dla języka C++. Jest teraz częścią standardowej biblioteki języka C++.

[— operator `new` (CRT)](new-operator-crt.md)\
Począwszy od Visual Studio 2013, uniwersalne środowisko uruchomieniowe C (UCRT) nie obsługuje już funkcji operatora specyficznego dla języka C++. Jest teraz częścią standardowej biblioteki języka C++.

[`printf` funkcje parametrów pozycyjnych](printf-p-positional-parameters.md)\
Parametry pozycyjne określają według liczby, która z argumentów ma zostać zastąpiona w polu ciągu formatu.

[`scanf` znaki pola typu](scanf-type-field-characters.md)\
Znak typu określa, czy skojarzony argument jest interpretowany jako znak, ciąg lub liczba dla którejkolwiek z `scanf` rodzin funkcji, w tym bezpiecznych wersji, takich jak `scanf_s` .

[`scanf` Specyfikacja szerokości](scanf-width-specification.md)\
Pole width jest dodatnią liczbą całkowitą dziesiętną, która określa maksymalną liczbę znaków do odczytania dla tego pola. Dotyczy którejkolwiek z `scanf` rodzin funkcji, w tym bezpiecznych wersji, takich jak `scanf_s` .

[_spawn, funkcje _wspawn](spawn-wspawn-functions.md)\
Funkcja do tworzenia i wykonywania nowego procesu.

[`strcoll` obowiązki](strcoll-functions.md)\
`strcoll`Funkcje i `wcscoll` porównują dwa ciągi zgodnie z `LC_COLLATE` ustawieniem kategorii na stronie kodowej ustawień regionalnych.

[Funkcje ciągu do wartości numerycznych](string-to-numeric-value-functions.md)\
`strtod`Rodzina funkcji konwertuje ciąg zakończony znakiem null na wartość liczbową.

[`vprintf` obowiązki](vprintf-functions.md)\
`vprintf`Funkcja przyjmuje wskaźnik do listy argumentów, sformatuje ją i zapisuje wynik do określonego miejsca docelowego. Funkcje te różnią się w wykonaniu walidacji parametrów, niezależnie od tego, czy mają one ciągi znaków dwubajtowych, miejsce docelowe danych wyjściowych i obsługę określania kolejności, w której parametry są używane w ciągu formatu.

## <a name="see-also"></a>Zobacz też

[Dokumentacja biblioteki środowiska uruchomieniowego języka C](c-run-time-library-reference.md)