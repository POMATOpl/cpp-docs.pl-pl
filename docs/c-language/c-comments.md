---
description: Dowiedz się więcej o komentarzach C
title: Komentarze języka C
ms.date: 06/25/2018
helpviewer_keywords:
- code comments, C code
- comments, documenting code
- comments, C code
- /* */ comment delimiters
- comments
ms.assetid: 0f5f2825-e673-49e7-8669-94e2f5294989
ms.openlocfilehash: 64ce3dea188e75545953b3427cd508dac5420a83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284579"
---
# <a name="c-comments"></a>Komentarze języka C

"Komentarz" to sekwencja znaków rozpoczynająca się od kombinacji ukośnik/gwiazdka ( <strong>/\*</strong> ), która jest traktowana jako pojedynczy znak odstępu przez kompilator i jest ignorowana. Komentarz może zawierać dowolną kombinację znaków z zestawu znaków, w tym znaków nowego wiersza, ale z wyłączeniem ogranicznika końcowego komentarza ( <strong>\*/</strong> ). Komentarze mogą zajmować więcej niż jeden wiersz, ale nie mogą być zagnieżdżone.

Komentarze mogą pojawić się wszędzie tam, gdzie dozwolone są odstępy. Ponieważ kompilator traktuje komentarz jako pojedynczy odstęp, nie można dołączać komentarzy w obrębie tokenów. Kompilator ignoruje znaki w komentarzu.

Komentarze służą do dokumentowania kodu. W tym przykładzie występuje komentarz akceptowany przez kompilator:

```C
/* Comments can contain keywords such as
   for and while without generating errors. */
```

Komentarze mogą pojawić się w tym samym wierszu, co instrukcja kodu:

```C
printf( "Hello\n" );  /* Comments can go here */
```

Można poprzedzać funkcje lub moduły programu opisowym blokiem komentarza:

```C
/* MATHERR.C illustrates writing an error routine
* for math functions.
*/
```

Ponieważ komentarze nie mogą zawierać zagnieżdżonych komentarzy, ten przykład wygeneruje błąd:

```C
/* Comment out this routine for testing

   /* Open file */
    fh = _open( "myfile.c", _O_RDONLY );
    .
    .
    .
*/
```

Ten błąd występuje, ponieważ kompilator rozpoznaje pierwsze `*/`, po wyrazach `Open file`, jako koniec komentarza. Próbuje on przetworzyć pozostały tekst i generuje błąd, gdy napotka `*/` poza komentarzem.

Podczas gdy można używać komentarzy do oznaczenia pewnych linii kodu jako nieaktywnych dla celów testowych, dyrektywy preprocesora `#if`, `#endif` i kompilacja warunkowa są przydatną alternatywą dla wykonania tego zadania. Aby uzyskać więcej informacji, zobacz [dyrektywy preprocesora](../preprocessor/preprocessor-directives.md) w *dokumentacji preprocesora*.

**Specyficzne dla firmy Microsoft**

Kompilator firmy Microsoft obsługuje również Komentarze jednowierszowe poprzedzone dwoma ukośnikami ( __//__ ). W przypadku kompilacji z użyciem /Za (standard ANSI), te komentarze spowodują wygenerowanie błędów. Nie można rozszerzać komentarzy do drugiego wiersza.

```C
// This is a valid comment
```

Komentarze zaczynające się od dwóch ukośników ( __//__ ) są kończone przez następny znak nowego wiersza, który nie jest poprzedzony znakiem ucieczki. W następnym przykładzie znak nowego wiersza jest poprzedzony ukośnikiem odwrotnym ( **\\** ), tworząc "sekwencję ucieczki". Ta sekwencja ucieczki powoduje, że kompilator traktuje następny wiersz jako część poprzedniego wiersza. (Aby uzyskać więcej informacji, zobacz [Sekwencje ucieczki](../c-language/escape-sequences.md)).

```C
// my comment \
    i++;
```

W związku z tym instrukcja `i++;` jest opatrzona komentarzem.

Domyślnym ustawieniem dla Microsoft C jest włączenie rozszerzeń Microsoft. Aby wyłączyć te rozszerzenia, użyj /Za.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Tokeny języka C](../c-language/c-tokens.md)
