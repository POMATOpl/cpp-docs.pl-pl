---
description: 'Dowiedz się więcej o: Inicjowanie ciągów'
title: inicjowanie ciągów
ms.date: 11/04/2016
helpviewer_keywords:
- character arrays, initializing
- strings [C++], initializing
- initializing arrays, strings
ms.assetid: 0ab8079d-d0d3-48f9-afd1-36a7bb439b29
ms.openlocfilehash: 145fc55eaccd64b30bae2736dd78317dc5db7d7d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137582"
---
# <a name="initializing-strings"></a>inicjowanie ciągów

Można inicjować tablicę znaków (lub szerokich znaków) za pomocą literału ciągu (lub szerokiego literału ciągu). Na przykład:

```
char code[ ] = "abc";
```

Inicjuje `code` się jako tablicę składającą się z czterech elementów. Czwarty element jest znakiem null, który kończy wszystkie literały ciągu.

Lista identyfikatorów może być tylko tak długo, jak liczba identyfikatorów do zainicjowania. Jeśli określisz rozmiar tablicy, który jest krótszy niż ciąg, dodatkowe znaki zostaną zignorowane. Na przykład następująca deklaracja inicjuje `code` się jako tablicę znaków trzech elementów:

```
char code[3] = "abcd";
```

Tylko trzy pierwsze znaki inicjatora są przypisane do `code` . Znak `d` i znak kończący null są odrzucane. Należy zauważyć, że spowoduje to utworzenie niekończącego ciągu (czyli jednego bez wartości 0 w celu oznaczenia jego końca) i wygenerowanie komunikatu diagnostycznego wskazującego ten warunek.

Deklaracja

```
char s[] = "abc", t[3] = "abc";
```

jest taka sama jak

```
char s[]  = {'a', 'b', 'c', '\0'},
     t[3] = {'a', 'b', 'c' };
```

Jeśli ciąg jest krótszy niż określony rozmiar tablicy, pozostałe elementy tablicy są inicjowane do wartości 0.

**Specyficzne dla firmy Microsoft**

W Microsoft C, literały ciągu mogą mieć długość do 2048 bajtów.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Inicjalizacja](../c-language/initialization.md)
