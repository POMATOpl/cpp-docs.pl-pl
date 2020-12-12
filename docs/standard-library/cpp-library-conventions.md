---
description: Dowiedz się więcej na temat Konwencji biblioteki C++
title: Konwencje biblioteki C++
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Standard Library, conventions
- classes [C++]
- functions [C++], library naming conventions
- naming conventions [C++], C++ Standard Library
- conventions [C++], C++ Standard Library
- function names [C++]
- coding conventions, C++ Standard Library
- naming conventions [C++], C++ library
ms.assetid: bf41b79a-2d53-4f46-8d05-779358335146
ms.openlocfilehash: 4426996b7420c056a964378655c72c43b99fcf97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233373"
---
# <a name="c-library-conventions"></a>Konwencje biblioteki C++

Biblioteka języka C++ ma takie same konwencje jak standardowa biblioteka C, a także kilka bardziej opisanych tutaj.

Implementacja ma pewną szerokość geograficzną w sposobie deklarowania typów i funkcji w bibliotece języka C++:

- Nazwy funkcji w standardowej bibliotece C mogą mieć zewnętrzny powiązania "C++" lub "zewnętrzne". Dołącz odpowiedni standardowy nagłówek C zamiast deklarować jednostkę biblioteki jako wbudowaną.

- Nazwa funkcji składowej w klasie biblioteki może mieć dodatkowe sygnatury funkcji w odniesieniu do tych wymienionych w tym dokumencie. Można upewnić się, że opisane tutaj wywołanie funkcji działa zgodnie z oczekiwaniami, ale nie można w sposób niezawodny przyjąć adresu funkcji składowej biblioteki. (Typ nie może być oczekiwany przez użytkownika).

- Klasa biblioteki może mieć niezaudokumentowane (niewirtualne) klasy bazowe. Klasa opisana jako pochodna z innej klasy może w rzeczywistości pochodzić od tej klasy za pośrednictwem innych nieudokumentowanych klas.

- Typ zdefiniowany jako synonim dla niektórych typów całkowitych może być taki sam jak jeden z kilku różnych typów całkowitych.

- Typ maski bitowej można zaimplementować jako typ Integer lub Wyliczenie. W obu przypadkach można wykonywać operacje bitowe (takie jak `AND` i `OR` ) dla wartości tego samego typu maski bitowej. Elementy `A` i `B` typy masek bitowych są wartościami niezerowymi, takimi jak `A`  &  `B` zero.

- Funkcja biblioteki, która nie ma specyfikacji wyjątku, może zgłosić dowolny wyjątek, chyba że jego definicja wyraźnie ogranicza taką możliwość.

Z drugiej strony istnieją pewne ograniczenia:

- W standardowej bibliotece C nie są stosowane żadne makra maskujące. Tylko określone podpisy funkcji są zastrzeżone, a nie nazwy samych funkcji.

- Nazwa funkcji biblioteki poza klasą nie będzie zawierała dodatkowych, nieudokumentowanych sygnatur funkcji. Możesz niezawodnie przyjmować swój adres.

- Klasy podstawowe i funkcje członkowskie opisane jako wirtualne są w sposób gwarantowany wirtualne, natomiast te opisane jako niewirtualne są niewirtualne.

- Dwa typy zdefiniowane przez bibliotekę C++ są zawsze różne, chyba że ten dokument jawnie sugeruje inaczej.

- Funkcje dostarczone przez bibliotekę, w tym domyślne wersje funkcji wymiennych, mogą *zgłaszać najwyżej* te wyjątki wymienione we wszystkich specyfikacjach wyjątków. Brak destruktorów dostarczonych przez bibliotekę zgłasza wyjątki. Funkcje w standardowej bibliotece C mogą propagować wyjątek, tak jak w przypadku `qsort` wywołania funkcji porównania, która zgłasza wyjątek, ale nie zgłasza wyjątków w inny sposób.

## <a name="see-also"></a>Zobacz też

[Omówienie standardowej biblioteki języka C++](../standard-library/cpp-standard-library-overview.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
