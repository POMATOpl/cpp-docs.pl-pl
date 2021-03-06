---
description: 'Dowiedz się więcej o: argumenty do głównej'
title: Argumenty dla metody main
ms.date: 11/04/2016
ms.assetid: 39824fef-05ad-461d-ae82-49447dda8060
ms.openlocfilehash: 5c837477e03c2e58e8b8dbe616cd31c63d5f5977
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280095"
---
# <a name="arguments-to-main"></a>Argumenty dla metody main

**2.1.2.2.1 ANSI** Semantyka argumentów dla głównej

W programie Microsoft C funkcja wywoływana przy uruchamianiu programu jest nazywana **Main**. Nie istnieje prototyp zadeklarowany dla elementu **Main** i można go zdefiniować za pomocą wartości zero, dwa lub trzy parametry:

```
int main( void )
int main( int argc, char *argv[] )
int main( int argc, char *argv[], char *envp[] )
```

Trzeci wiersz powyżej, gdzie **Main** przyjmuje trzy parametry, to rozszerzenie firmy Microsoft do standardu ANSI C. Trzeci parametr, **envp**, jest tablicą wskaźników do zmiennych środowiskowych. Tablica **envp** jest zakończona przez wskaźnik o wartości null. Zobacz [Główne funkcje i wykonywanie programu](../c-language/main-function-and-program-execution.md) , aby uzyskać więcej informacji na temat **głównych** i **envp**.

Zmienna **argc** nigdy nie utrzymuje wartości ujemnej.

Tablica ciągów kończąca się na **argv [argc]**, która zawiera wskaźnik o wartości null.

Wszystkie elementy tablicy **argv** są wskaźnikami do ciągów.

Program wywoływany bez argumentów wiersza polecenia otrzyma wartość jedną dla **argc**, ponieważ nazwa pliku wykonywalnego jest umieszczana w **argv [0]**. (W wersjach systemu MS-DOS wcześniejszych niż 3,0 nazwa pliku wykonywalnego jest niedostępna. Litera "C" jest umieszczana w **argv [0]**.) Ciągi wskazywane przez **argv [1]** do **argv [argc-1]** przedstawiają parametry programu.

Parametry **argc** i **argv** są modyfikowalne i zachowują ostatnio przechowywane wartości między uruchomieniem programu a zakończeniem działania programu.

## <a name="see-also"></a>Zobacz też

[Środowisko](../c-language/environment.md)
